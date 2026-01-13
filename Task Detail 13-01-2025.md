### Objective List:

1. Ensure **“Student Admitted”** in Pupil Particular is taken from the **oldest class history** record, not current class year.
    
2. Provide **“Copy Academic Transcript”** report using **principal signature only**, resolved from the **current academic year** principal (pending approval).
    
3. Include **Student Classroom** in **Discipline Report** Excel export (Generate XLSX).
    
4. Display **Classroom** in **Tardiness** UI table and add **Generate XLSX** export for Tardiness.
    
5. Allow users to **clear/reset exam time to null** in Timetable after it has been set.
    
6. Fix **grade lock/unlock** logic so users can fill **Term 1 and Term 2** appropriately across terms, including after unlock.
    
7. Ensure **Paper (P1/P2)** appears correctly in **Print Schedule**, derived from paper name.
    
8. Add **Academic Year filter** in Discipline Report header with default to **current AY**.
    
9. Enable full **table editing controls** in SVE Cover Page Template (add/delete row/column, borders, etc.), including fixing delete column.
    
10. Set SVE Deadline default column order and rename **Printing Deadline → Printing Request Deadline** consistently.
    
11. Fix SVE Cover Template so **rows can be deleted** and add **fullscreen** editor mode.
    
12. Improve SVE Label formatting: **auto-shrink long text**, standardize component naming (e.g., “Paper 1” only), and validate programme code naming.
    
13. Update SVE Misc Label: **remove Setter/Vetter**, redefine **Enclosed** fields to reflect additional components and quantities.
    
14. Resolve subject lock edge case so **Term 1 remains editable when null**, even when Term 2 is active, unless explicitly locked.
    
15. Improve File Sharing (Academic Department): restore **pagination**, use standard table component, and add **AcademicDepartment** column.
    
16. Fix Learning Outcome scoring so value **0 maps to BDCP “Beginning”** and is treated as valid input.
    
17. Ensure student lists are **always ordered by name (A–Z)** by default.
    
18. Improve Attendance UX so cursor/focus behavior does not get stuck in the text field.
    
19. Prevent SVE editor from **jumping/resetting scroll** after save.
    
20. Ensure **new students can open Term 1** correctly.
    
21. Fix Attendance reliability so data is not **incomplete/missing** intermittently.
    
22. Standardize **pagination across all views** using consistent table/paging behavior.
    
23. Add **page number + generated timestamp** on SVE Timetable PDF output.
    
24. Enable users to **delete incorrect SVE timetable entries** safely (with proper constraints/audit if applicable).
    
25. Enforce SVE List titles to be **specific (Primary/Secondary/JC) + include AY** in UI/PDF.
    
26. In SVE Label/Additional Items, show **only ticked items** and display quantity input **only for subjects/components that have insert**.

## [[2026-01-08]] 1) Pupil Particular – “Student Admitted” source from oldest class history

1. **Problem (Objective)**
    
    - **Problem:** “Student admitted” on **Pupil Particular** is currently taken from **current class year**, which causes inaccurate admission data.
        
    - **Objective:** Ensure “student admitted” is derived from the **earliest/oldest record** in the student’s **class history**, not current class year.
        
2. **Tech Detail**
    
    - Identify data source: `student_class_history` (or equivalent).
        
    - Query rule: select **MIN(start_date / academic_year / created_at)** per student as “admitted”.
        
    - Fallback if history missing: use student master “admission date” (if exists).
        
    - Update backend mapping + UI display field.
        
    - Add test cases: student with multiple history rows; transferred student; missing history.
        

---

## [[2025-12-08]] 2) New Report: “Copy Academic Transcript” + Principal signature rule

1. **Problem (Objective)**
    
    - **Problem:** Need a report named **“Copy Academic Transcript”** with **principal signature** only, and principal must follow **current academic year**. Status: requested but needs approval.
        
    - **Objective:** Provide report output that always uses the **active principal for current AY** and applies **principal sign only** (no other signer).
        
2. **Tech Detail**
    
    - Add new report type: `COPY_ACADEMIC_TRANSCRIPT`.
        
    - Signature source: resolve **Principal** by **Academic Year = current AY** (config/service).
        
    - Enforce signature policy: **principal only** (disable others).
        
    - UI: add to report menu/list; permission gate if “Need approval”.
        
    - Export: PDF (and/or existing export flow).
        
    - Acceptance: switching current AY changes principal signature automatically.
        

---

## [[2025-12-03]] 3) Discipline Report – add “Classroom” on Excel export (Generate XLSX)

1. **Problem (Objective)**
    
    - **Problem:** Export Excel for **Discipline Report** is missing **student classroom** column.
        
    - **Objective:** Include **Classroom** in exported XLSX so schools can filter/report properly.
        
2. **Tech Detail**
    
    - Determine classroom source: student current class assignment by selected AY/term (avoid mismatch).
        
    - Update export generator: add column `Classroom` (format consistent: e.g., “P4 Wisdom”).
        
    - Ensure export respects current filters (status/formType/date range/AY).
        
    - Validate with sample rows from the linked discipline page.
        
    - Add unit/integration tests for export columns and null handling.
        

---

## [[2025-12-03]] 4) Tardiness – add “Classroom” on UI table + add Generate XLSX

1. **Problem (Objective)**
    
    - **Problem:** Tardiness listing UI missing **classroom**, and no **Generate XLSX** export.
        
    - **Objective:** Show classroom on the UI table and enable XLSX export consistent with Discipline module.
        
2. **Tech Detail**
    
    - UI table: add `Classroom` column near Student/Level fields.
        
    - Backend: ensure API returns classroom (or UI fetches classroom mapping).
        
    - Implement XLSX export endpoint / reuse export service.
        
    - Export schema: include Classroom + existing tardiness fields.
        
    - Permissions: align with tardiness access roles.
        
    - Verify pagination + filter compatibility.
        

---

## [[2025-11-25]] 5) Timetable – allow clearing exam time (set to null)

1. **Problem (Objective)**
    
    - **Problem:** Once exam time is set, user cannot clear it back to **null**.
        
    - **Objective:** Provide a clear/reset function so timetable exam time can be removed.
        
2. **Tech Detail**
    
    - UI: add “Clear time” action (button/icon) or allow empty input to save null.
        
    - Backend validation: accept `null` for `exam_time` (and/or start/end).
        
    - Update update-request DTO + database constraints (if `NOT NULL`, revise).
        
    - Audit log: record who cleared time and when (if audit exists).
        
    - Test: set time → clear → re-set.
        

---

## [[2025-11-24]] 6) Subject Scoring – grade locked logic across terms

1. **Problem (Objective)**
    
    - **Problem:** On ongoing term, grades become locked incorrectly. Scenario: **Term 1 empty**, now **Term 2**, user should still be able to fill Term 1 & Term 2; when grade is unlocked, should be editable again.
        
    - **Objective:** Fix locking rules so empty prior-term grades remain editable (subject to unlock), and unlock restores editability.
        
2. **Tech Detail**
    
    - Review lock conditions: by subject / by term / by AY / by student.
        
    - Rule update:
        
        - If Term 1 grade is **null**, allow edit even when current term is Term 2 (unless explicitly locked).
            
        - When unlock action occurs, ensure UI + API allow edits again.
            
    - Ensure lock state is fetched per subject + term, not only current term.
        
    - Add regression tests for: locked subject, null grades, unlock flow.
        

---

## [[2025-11-19]] 7) Print Schedule – Paper not appearing (P1/P2 mapping)

1. **Problem (Objective)**
    
    - **Problem:** When printing schedule, **Paper** (P1/P2) does not appear; schedule should show paper label derived from paper name.
        
    - **Objective:** Display Paper name (e.g., **Paper 1 = P1**, Paper 2 = P2) on schedule output.
        
2. **Tech Detail**
    
    - Identify where schedule print template builds subject rows.
        
    - Fetch paper components for each exam entry.
        
    - Mapping: “Paper 1” → “P1”, “Paper 2” → “P2” (or use before-space/number logic).
        
    - Add to printed schedule layout and ensure no overlap with time/room columns.
        
    - Tests: schedules with and without papers, multi-paper subjects.
        

---

## [[2025-11-18]] 8) Discipline Report – add Academic Year filter (default current AY)

1. **Problem (Objective)**
    
    - **Problem:** Discipline report missing **Academic Year filter**, making results confusing across years.
        
    - **Objective:** Add AY filter in header, default to **Current Academic Year**.
        
2. **Tech Detail**
    
    - UI: AY dropdown in header with default set to current AY from settings/service.
        
    - Backend: API query must accept `academicYearId` and apply to dataset joins (student/classroom/records).
        
    - Ensure export uses the same AY filter value.
        
    - Add test for default load and AY switching.
        

---

## [[2025-11-18]] 9) SVE Cover Page Template – table design features + fix delete column

1. **Problem (Objective)**
    
    - **Problem:** Document editor table can add columns but cannot delete columns; needs standard table property tools.
        
    - **Objective:** Provide full table editing controls (add/delete row/column, borders, cells) in SVE cover template editor.
        
2. **Tech Detail**
    
    - Enhance editor toolbar: table properties modal (rows/cols add/remove, borderlines, merge/split if supported).
        
    - Fix delete-column action to update underlying document model safely.
        
    - Validate minimum 1 row/1 column constraints.
        
    - Ensure saved template renders consistently in PDF output.
        
    - Regression: existing templates remain compatible.
        

---

## [[2025-11-17]] 10) SVE Deadline – reorder columns + rename “Printing Deadline” → “Printing Request Deadline”

1. **Problem (Objective)**
    
    - **Problem:** Deadline columns order and label are not per requirement.
        
    - **Objective:** Set default order: **AY / Programme / Level(s) / Exam Type / Assign / Printing Request / Uploading / Timetable**, and rename label to **Printing Request Deadline**.
        
2. **Tech Detail**
    
    - Update table column configuration (frontend).
        
    - Update any backend label constants/export headers.
        
    - Confirm sorting/filter still works after column reorder.
        
    - Apply same label change consistently across other SVE pages referencing it.
        

---

## [[2025-11-17]] 11) SVE Cover Template – cannot delete row + add fullscreen mode

1. **Problem (Objective)**
    
    - **Problem:** Table row cannot be deleted; editing space is limited.
        
    - **Objective:** Enable delete-row and provide fullscreen editor mode.
        
2. **Tech Detail**
    
    - Implement delete-row in document model + selection context menu.
        
    - Fullscreen toggle UI for editor container.
        
    - Ensure autosave/undo still works in fullscreen.
        
    - Test: delete first/middle/last row; template save & preview.
        

---

## [[2025-11-17]] 12) SVE Label formatting – long text auto-shrink + component naming cleanup

1. **Problem (Objective)**
    
    - **Problem:** Label spacing and long text overflow; component text includes extra description (e.g., “Paper 1 - …”).
        
    - **Objective:** Auto-resize long text to fit label boxes; standardize component naming to “Paper X” only.
        
2. **Tech Detail**
    
    - Add text-fit logic (font-size scaling with min size).
        
    - Component parsing rule: take substring **before “ - ”** (space-hyphen-space).
        
    - Validate across Label, Expert, HOD, Misc label outputs.
        
    - Check “Programme Code” naming rules and apply consistent formatting.
        

---

## [[2025-11-17]] 13) SVE Misc Label – remove Setter/Vetter columns + redefine “Enclosed” fields

1. **Problem (Objective)**
    
    - **Problem:** Misc label contains unnecessary Setter/Vetter columns; “Expert → Enclosed” requirement is different.
        
    - **Objective:** Remove Setter/Vetter columns and change enclosed fields to show **Additional Component name** and **quantity input**.
        
2. **Tech Detail**
    
    - Update label template schema: drop setter/vetter columns.
        
    - “Enclosed” content: list selected additional component(s).
        
    - “Script Enclosed” should display numeric quantity (from input).
        
    - Ensure only ticked/selected additional items appear.
        

---

## [[2025-11-17]] 14) Subject lock edge case – Term 2 unlocked but Term 1 remains locked

1. **Problem (Objective)**
    
    - **Problem:** Term 2 becomes unlocked while Term 1 remains locked even though Term 1 is empty; user must unlock subject but expected auto-open when null (previous behavior).
        
    - **Objective:** Align behavior so Term 1 is editable when grade is null (unless explicitly locked), even if current term is Term 2.
        
2. **Tech Detail**
    
    - Harmonize lock resolver: check per-term grade nullability + explicit lock flags.
        
    - UI: indicate lock reason (term/subject lock) clearly.
        
    - Add regression test using provided case (user/class/subject/student).
        

---

## [[2025-11-17]] 15) File Sharing (Academic Department) – missing pagination + add department column

1. **Problem (Objective)**
    
    - **Problem:** Pagination missing on Academic Department file sharing; still uses old table component; also table missing department column.
        
    - **Objective:** Replace with standard table component (like SOW), restore pagination, and show `fileName | AcademicDepartment`.
        
2. **Tech Detail**
    
    - Swap UI component to shared table with pagination controls.
        
    - API: ensure total count + page params are supported.
        
    - Add `academicDepartment` field in response and render it.
        
    - Verify sort/search and page navigation.
        

---

## [[2025-11-17]] 16) Learning Outcome scoring – score “0” not mapped to BDCP “Beginning”

1. **Problem (Objective)**
    
    - **Problem:** When LO score is entered as **0**, system fails to map BDCP correctly; should map to **Beginning**.
        
    - **Objective:** Ensure value `0` is treated as valid input and maps to correct descriptor.
        
2. **Tech Detail**
    
    - Fix validation: do not treat `0` as falsy/empty.
        
    - Update BDCP mapping logic (0 → Beginning).
        
    - UI: allow saving 0 and display descriptor properly.
        
    - Add tests for 0/1/2/3… and empty/null.
        

---

## [[2025-09-23]] 17) Student list – always order by name

1. **Problem (Objective)**
    
    - **Problem:** Student list ordering is inconsistent.
        
    - **Objective:** Default sort should always be **Name (A–Z)**.
        
2. **Tech Detail**
    
    - Backend: enforce default `ORDER BY student_name ASC` when no sort param.
        
    - Frontend: set default table sort to name; preserve manual sort if user changes.
        
    - Regression: pagination consistency with sorting.
        

---

## 18) Attendance – cursor stays in text field (UX issue)

1. **Problem (Objective)**
    
    - Cursor remains stuck in attendance text field, slowing data entry.
        
    - Objective: smooth navigation (auto-tab / auto-blur) after input.
        
2. **Tech Detail**
    
    - Review focus management; prevent forced re-focus after state update.
        
    - Add keyboard navigation rules (enter → next row).
        
    - Test across browsers.
        

---

## 19) SVE editor – jumping when save

1. **Problem (Objective)**
    
    - SVE view jumps/scroll resets after save.
        
    - Objective: maintain scroll position and selection after save.
        
2. **Tech Detail**
    
    - Preserve scroll offset before save and restore after re-render.
        
    - Avoid full-page refresh; use partial state update.
        
    - Test with large templates.
        

---

## 20) New Students – need to open Term 1

1. **Problem (Objective)**
    
    - New students can’t access/open Term 1 as needed.
        
    - Objective: ensure Term 1 is available for new student records.
        
2. **Tech Detail**
    
    - Review default term initialization logic for new student enrollment.
        
    - Ensure term availability depends on AY + enrollment date rules.
        
    - Add admin override if needed.
        

---

## 21) Attendance incomplete/missing sometimes

1. **Problem (Objective)**
    
    - Attendance data sometimes incomplete or missing.
        
    - Objective: ensure reliability and completeness.
        
2. **Tech Detail**
    
    - Check sync jobs / race conditions / pagination load issues.
        
    - Add data integrity checks and retry mechanism.
        
    - Log and alert for missing segments.
        

---

## 22) General – pagination in every view

1. **Problem (Objective)**
    
    - Some views missing pagination controls.
        
    - Objective: standardize pagination across list views.
        
2. **Tech Detail**
    
    - Adopt shared table component everywhere.
        
    - Ensure APIs support `page/pageSize/total`.
        
    - QA checklist for each module list.
        

---

## 23) SVE Timetable PDF – show page number + generated timestamp

1. **Problem (Objective)**
    
    - PDF output missing page number and generation time metadata.
        
    - Objective: add footer with `Page X of Y` + “Generated at …”. currently only date, need timestamp.
        
2. **Tech Detail**
    
    - Update PDF renderer template footer.
        
    - Use server time + timezone formatting.
        
    - Verify on multi-page PDFs.
        

---

## 24) SVE Timetable – cannot delete wrong input data

1. **Problem (Objective)**
    
    - Users cannot delete incorrectly entered timetable data.
        
    - Objective: enable delete with permission + audit.
        
2. **Tech Detail**
    
    - Add delete action (row-level) with confirmation dialog.
        
    - Backend: soft delete recommended + audit log.
        
    - Prevent deletion if referenced downstream (validate constraints).
        

---

## 25) SVE List title – must specify Primary/Secondary/JC + include AY

1. **Problem (Objective)**
    
    - Titles too generic; need clear level/category and academic year.
        
    - Objective: enforce title format: e.g., “Primary Final Year Examination – Setter/Vetter/Expert List – AY 2025/2026”.
        
2. **Tech Detail**
    
    - Update title builder: include Programme/Level + list type + AY.
        
    - Validate fields are present before generation.
        
    - Apply to PDF headers and UI.
        

---

## 26) [Lily 13-01-2026] SVE Label/Additional Items – show only ticked items + insert quantity boxes only when applicable

1. **Problem (Objective)**
    
    - Title/content still not matching: additional items shown even if not ticked; insert quantity boxes appear for subjects that don’t have insert.
        
    - Objective: render **only selected additional items**, and show quantity input box **only for subjects/components that have insert**.
        
2. **Tech Detail**
    
    - Filter additional items by `isSelected=true`.
        
    - Insert UI: show numeric input only when `component.hasInsert=true`.
        
    - Backend: return proper flags per subject/component.
        
    - Test: subject with no insert, subject with insert, mixed list.