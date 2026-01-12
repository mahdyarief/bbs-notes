## 1) Background & Problem

Several attendance views show inconsistent counts (Absent/Late) across:

- **Discipline Overview detail** (Admin)
    
- **Teacher/Analytics attendance dashboard** (Teacher-facing)
    
- **Attendance detail list** intermittently loading as **0**
    
- Attendance calculation not respecting **student status = current**
    
- “Complete / Incomplete” indicator not matching what teachers did (“Mark all present” but still incomplete)
    

These issues reduce trust in the dashboard and can cause incorrect follow-ups (discipline actions, teacher reporting).

---

## 2) Goals

1. Attendance counts (Absent/Late) are **consistent** across Admin + Teacher dashboards for the same filters (AY, term, student, date range).
    
2. Attendance detail data reliably loads (no random “0 everything” due to loading failure).
    
3. Attendance calculations and “Mark all / Unmark” logic only affects **current students**.
    
4. Completion status reflects the real marking state and is **easy to understand**.
    

---

## 3) Non-Goals (Out of Scope)

- Redesigning the entire analytics dashboard UI.
    
- Changing historical attendance records or backfilling data (unless clearly wrong due to query bug).
    
- Changing attendance status codes (only mapping/filters/query logic).
    

---

## 4) Users & Use Cases

- **Admin / Discipline team:** Needs accurate absent count per student & term for discipline overview.
    
- **Teachers:** Needs accurate term summary counts + reliable detail list + correct completion indicator while marking attendance.
    

---

## 5) Scope: Issues, Repro Steps, Expected Results, Acceptance Criteria, Technical Hypotheses

### Issue A — Discipline Overview detail absent count mismatch (Attendance)

**Context / evidence:**  
Discipline overview shows incorrect “Jumlah Absent” for student **100308** in AY **26**, programme **22**, term **1**. Note: “Saat AY endnya pas sama tanggal telat, dia ga kebaca”.

**Reproduce Steps**

1. Open:  
    `https://admin.smartbag.binabangsaschool.com/discipline-overview?pageSize=10&page=0&academicYearId=26&programmeId=22&term=1`
    
2. Find student **100308** (Lee Onyu - Primary 2 Faith / ADAM YUMA ARDENTO context).
    
3. Compare displayed absent count vs DB query:
    
    `select * from attendance a join class_year cy on a.class_year_id = cy.id where cy.academic_year_id = 26   and a.student_id = 100308   and a.attendance_status != '1';`
    
4. Verify there is an attendance event on the **AY end date** (or boundary date) that is not counted.
    

**Expected Result**

- Discipline Overview absent/late counts must include all relevant records within the selected **term date range**, including boundary dates.
    

**Acceptance Criteria**

- For AY=26, term=1, student=100308: UI count == DB count using the canonical rules (see “Data Rules” below).
    
- Boundary dates (term start/end, AY start/end) are **inclusive**.
    

**Technical Hypotheses (most likely)**

- **Inclusive/exclusive boundary bug:** query uses `< end_date` instead of `<= end_date`, causing records on end date not counted.
    
- **Timezone/date casting mismatch:** attendance date stored in UTC, UI term filter uses local date and drops boundary day.
    
- **Wrong date source:** using `attendance.created_at` instead of `daily_attendance.date` for term filter.
    
- **Term range mismatch:** term dates derived from AY incorrectly (term 1 end date equals a record date but excluded).
    

---

### Issue B — Teacher attendance counts do not match detail/query (Attendance)

**Context / evidence:**  
Teacher analytics shows totals that don’t match. Query confirms **6 total** (Term1: 1 Late, 1 Absent W, 1 Absent W/O; Term2: 0 Late, 3 Absent W, 1 Absent W/O).

**Reproduce Steps**

1. Open teacher analytics:  
    `https://analytics.binabangsaschool.dev/dashboard/35-absent-late-check?ay=26&date=&nama=`
    
2. Filter/search student **100308** (or use the provided name search).
    
3. Compare numbers shown per term vs SQL:
    
    `select s.full_name,        case when a.attendance_status = '2' then 'LATE'             when a.attendance_status = '3' then 'ABSENT W'             when a.attendance_status = '4' then 'ABSENT W/O'        end as status_label,        a.note,        da."date" from attendance a join class_year cy on a.class_year_id = cy.id join daily_attendance da on a.daily_attendance_id = da.id join student s on s.id = a.student_id where cy.academic_year_id = 26   and a.student_id = 100308   and a.attendance_status != '1'   and a.deleted_at is null order by da."date";`
    

**Expected Result**

- Teacher dashboard counts per term must match the canonical query results (same filters, same term boundaries, exclude deleted).
    

**Acceptance Criteria**

- For the same AY + student, term totals in UI equal totals from canonical query:
    
    - Term 1: Late=1, Absent W=1, Absent W/O=1
        
    - Term 2: Late=0, Absent W=3, Absent W/O=1
        
    - Total = 6
        
- Deleted records (`attendance.deleted_at`) are never counted.
    

**Technical Hypotheses**

- **Term split logic bug:** some records assigned to wrong term due to date boundary or wrong term calendar.
    
- **Filtering mismatch:** UI counts include `attendance_status='1'` or include soft-deleted rows (missing `deleted_at is null`).
    
- **Join mismatch:** teacher dashboard counts based on different join (e.g., joining to wrong class_year/programme) causing under/over count.
    
- **Aggregation bug:** counting distinct daily_attendance instead of attendance rows (or vice versa).
    
- **Caching/stale materialized dataset:** analytics uses cached dataset not refreshed.
    

---

### Issue C — Teacher Attendance Detail sometimes loads as 0 (intermittent)

**Context / evidence:**  
“Attendance Detail di teacher, suka datanya ga ke load, jadi 0 semua (Repro: Refresh sampai data ga ke load)”.

**Reproduce Steps**

1. Open the teacher attendance dashboard/detail page.
    
2. Refresh repeatedly until the detail table shows zeros / empty.
    
3. Observe network calls (API request failures, timeouts, 500, CORS, etc.).
    

**Expected Result**

- Detail data should **always** load correctly; if API fails, UI must show **error state** (not “0”) and provide retry.
    

**Acceptance Criteria**

- No silent fallback to “0”.
    
- On API failure: show error message + retry action.
    
- Add request correlation id / log trace for failures.
    
- Success rate target: **≥ 99.5%** successful loads over 1 week (or agreed window).
    

**Technical Hypotheses**

- **Race condition:** UI renders “0” before async data arrives and state never updates due to cancelled promise / stale state.
    
- **API flaky / timeout:** intermittent 504/502, DB slow query, missing indexes.
    
- **Client-side caching bug:** stale cache returns empty payload for some refreshes.
    
- **Filter param bug:** occasional request sent with empty/invalid ay/term param after refresh.
    

---

### Issue D — Attendance calculation must respect Student Status = current (withdrawn still included)

**Context / evidence:**  
Withdrawn students still appear and are affected by “Unmark”; expected only **current** students.

**Reproduce Steps**

1. Go to attendance marking page (example: Campus KJ test, Primary 3).
    
2. Confirm there are students with status **withdrawn**.
    
3. Use “Mark all present” / “Unmark” action.
    
4. Observe withdrawn students remain in list / impacted by action.
    

**Expected Result**

- Attendance marking and completion calculations only include students whose status is **current** for that class/year/term/date.
    

**Acceptance Criteria**

- Withdrawn students are not counted in:
    
    - expected student list size
        
    - completion calculation
        
    - mark/unmark bulk actions
        
- UI clearly indicates if there are non-current students (optional), but they must not affect completion.
    

**Technical Hypotheses**

- Missing filter `student.status = 'current'` (or equivalent) in:
    
    - roster query
        
    - completion computation query
        
    - bulk update endpoint
        
- Student status is time-bound (effective date) but system checks only latest flag incorrectly.
    

---

### Issue E — “Complete / Incomplete” status confusing / incorrect after “Mark all present”

**Context / evidence:**  
Even after “mark all student present”, status stays **incomplete**.

**Reproduce Steps**

1. Open attendance marking for: “###### Campus KJ TEST PRIMARY ###### Level Primary 3”.
    
2. Click “Mark all student present”.
    
3. Observe status remains “Incomplete”.
    

**Expected Result**

- After all **current** students are marked (present/late/absent states), status becomes **Complete**.
    

**Acceptance Criteria**

- Completion logic uses:
    
    - roster = current students only
        
    - marked count = attendance rows created/updated for that date/session
        
- If all current students have attendance recorded → **Complete**
    
- If any current student missing a mark → **Incomplete**
    
- Status label/tooltips explain rule in 1 sentence.
    

**Technical Hypotheses**

- Completion computed against total roster including withdrawn.
    
- Completion uses wrong “presence” definition (e.g., requires note field, or requires “submitted” flag not set by bulk action).
    
- Bulk action updates UI state but doesn’t persist for all students due to pagination / API limit, leaving some unmarked.
    

---

## 6) Canonical Data Rules (Single Source of Truth)

To prevent future mismatch, define one canonical rule set used by all endpoints:

1. **Date basis for term filtering:** `daily_attendance.date` (not created_at).
    
2. **Include boundary dates:** `term_start_date <= date <= term_end_date`.
    
3. **Exclude soft-deleted attendance:** `attendance.deleted_at is null`.
    
4. **Exclude present status from absent/late counts:** `attendance_status != '1'`.
    
5. **Current-student only:** roster and completion calculations only include students whose status is `current` (or effective-current for that date).
    

---

## 7) Proposed Solution (Product + Engineering)

### Product changes

- Ensure Admin Discipline Overview and Teacher Analytics use the same backend aggregation endpoint (or same shared query module).
    
- Add clear empty/error handling on Teacher detail:
    
    - Loading skeleton
        
    - Error message on failure (not “0”)
        
    - Retry button
        

### Engineering changes

- Consolidate attendance aggregation logic into a shared service/module.
    
- Fix date boundary handling (inclusive) and timezone normalization.
    
- Apply `deleted_at is null` consistently.
    
- Apply `student_status=current` filter to roster, bulk actions, and completion.
    
- Add monitoring:
    
    - API error rate
        
    - slow query logging
        
    - client-side error logging with request params
        

---

## 8) Metrics / Success Criteria

- **Count consistency:** For sampled students across terms, Admin vs Teacher discrepancy rate = **0**.
    
- **Reliability:** Teacher detail load error rate < **0.5%**.
    
- **Support reduction:** Attendance-count related tickets reduced week-over-week after release.
    

---

## 9) QA Test Scenarios (must pass)

1. **Boundary date:** attendance record on term end date counted in both views.
    
2. **Deleted record:** soft-deleted attendance not counted.
    
3. **Term split:** record near term boundary assigned to correct term.
    
4. **Withdrawn student:** excluded from roster, bulk actions, and completion.
    
5. **Mark all present:** status becomes complete immediately and persists after refresh.
    
6. **Intermittent load simulation:** force API 500 → UI shows error state + retry; no “0”.