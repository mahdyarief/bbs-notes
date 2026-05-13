## Overview
Fitur **GPA Transcript Report** digunakan untuk menghasilkan transcript siswa untuk periode **June** dan **December**.  
Report ini menampilkan informasi siswa, riwayat akademik, subject detail, final mark, GPA, cumulative GPA, dan informasi penandatangan.

## Objective
Menyediakan report transcript yang:
- menampilkan data akademik siswa per tahun
- menampilkan **Final Mark** sesuai rule periode **June / December**
- menghitung **GPA** dan **Weighted Cumulative GPA**
- menampilkan grading reference dan academic summary

## Report Period
- June
- December

## Scope

### 1. Student & School Information
Field yang ditampilkan:
- Report Title: **GPA Transcript**
- Name
- Gender
- Date of Birth
- Enrollment Date
- Graduation Date
- Curriculum
- CEEB Code
- Accredited by
- Campus
- Campus Address

### 2. Academic Year Information
Field yang ditampilkan:
- Academic Year
- Level / Grade
- Class / Homeroom
- 4-Year Academic History

### 3. Subject Detail Information
Field yang ditampilkan:
- Subject
- Unit
- Subject Category
- Final Mark

### 4. Grading & GPA Information
Field yang ditampilkan:
- Grade
- Mark Range
- GP Value
- GPA
- Weighted Cumulative GPA

### 5. Academic Summary Information
Field yang ditampilkan:
- GPA
- Academic Rank / Class Size
- Attendance
- Conduct
- Weighted Cumulative GPA

### 6. Signature Information
Field yang ditampilkan:
- Principal Name
- Title
- Signature

## Data Source Mapping

### Direct Source
- Student Master
- Student Academic History
- Class History
- Student Subject Enrollment
- Subject Setup
- Subject Master
- Manage Subject Unit
- Campus Master
- Campus / School Profile
- Grading Scale Master
- Ranking Summary
- Attendance Summary
- Conduct Summary
- School Signatory / Signatory Master
- Graduation Date Master

### Derived Field
- 4-Year Academic History
- Final Mark
- GPA
- Weighted Cumulative GPA

## Final Mark Source
Source mark yang digunakan:
- FYA
- SA1
- AS PUM
- A PUM
- IGCSE PUM

## Final Mark Rules

### June
| Student Level | Subject Category | Final Mark Rule |
|---|---|---|
| JC2 | All Subjects | Highest of **A PUM** and **FYA** |
| Other Levels | All Subjects | **FYA** |

### December
| Student Level | Subject Category | Final Mark Rule |
|---|---|---|
| JC2 | Academic | Highest of **AS PUM** and **SA1** |
| JC2 | Non-Academic | **SA1** |
| Sec 4 | All Subjects | Highest of **FYA** and **IGCSE PUM** |
| Other Levels | All Subjects | **FYA** |

## GPA Calculation
GPA dihitung dengan mekanisme:
1. **Final Mark** dimapping ke **Grading Scale**
2. Sistem mendapatkan **GP Value**
3. Formula GPA:
   **sum(GP Value × Unit) / total Unit**

Catatan:
- pembagi menggunakan **total Unit**
- bukan total jumlah subject

## Layout Sections
Report terdiri dari:
1. Header Area
2. Per Academic Year Area
3. Reference Area
4. Bottom Summary Area
5. Signature Area

## Business Rules
- Report title selalu **GPA Transcript**
- Transcript mendukung periode **June** dan **December**
- Final Mark harus mengikuti rule berdasarkan:
  - report period
  - student level
  - subject category
- GPA dan Weighted Cumulative GPA dihitung dari Final Mark dan Unit
- Grading Scale ditampilkan sebagai reference pada report

## Dependencies
- Student Master
- Academic History
- Subject Enrollment
- Subject Unit Setup
- Grading Scale
- Ranking
- Attendance
- Conduct
- External Cambridge Result
- Signatory / Campus Profile

## Open Points / Need Confirmation
- **Enrollment Date**: source masih belum confirmed
- **Curriculum**: pada sebagian mapping tertulis static, pada layout tertulis Student Master / Curriculum Master → perlu disepakati
- **CEEB Code / Accreditation / Campus Address**: perlu final confirmation apakah source dari Campus Identity, Campus Master, atau School Profile
- rule **4-Year Academic History** perlu dipastikan apakah selalu tahun berjalan + 3 tahun sebelumnya

## Expected Output
Sistem dapat generate **GPA Transcript Report** yang konsisten untuk June dan December, dengan:
- field mapping yang jelas
- source data yang jelas
- rule Final Mark yang valid
- perhitungan GPA yang konsisten

## Functional Requirements

### FR-01
System must provide **GPA Transcript Report** for student transcript generation.

### FR-02
System must support transcript generation for **June** and **December** reporting periods.

### FR-03
System must display student information in the transcript, including:
- Name
- Gender
- Date of Birth
- Enrollment Date
- Graduation Date

### FR-04
System must display school and campus information in the transcript, including:
- Curriculum
- CEEB Code
- Accredited by
- Campus
- Campus Address

### FR-05
System must display academic year information for each relevant year, including:
- Academic Year
- Level / Grade
- Class / Homeroom

### FR-06
System must display **4-Year Academic History** in the transcript.

### FR-07
System must display subject detail for each academic year, including:
- Subject
- Unit
- Subject Category
- Final Mark

### FR-08
System must determine **Final Mark** based on report period, student level, and subject category according to the defined business rules.

### FR-09
System must support Final Mark source selection from:
- FYA
- SA1
- AS PUM
- A PUM
- IGCSE PUM

### FR-10
For **June** period, system must calculate Final Mark using:
- **JC2**: highest of **A PUM** and **FYA**
- **Other levels**: **FYA**

### FR-11
For **December** period, system must calculate Final Mark using:
- **JC2 Academic subjects**: highest of **AS PUM** and **SA1**
- **JC2 Non-Academic subjects**: **SA1**
- **Sec 4**: highest of **FYA** and **IGCSE PUM**
- **Other levels**: **FYA**

### FR-12
System must map each Final Mark to the applicable **Grading Scale**.

### FR-13
System must display grading reference information, including:
- Grade
- Mark Range
- GP Value

### FR-14
System must calculate **GPA** using the formula:  
`sum(GP Value × Unit) / total Unit`

### FR-15
System must display **GPA** in the transcript.

### FR-16
System must calculate and display **Weighted Cumulative GPA**.

### FR-17
System must display academic summary information, including:
- GPA
- Academic Rank / Class Size
- Attendance
- Conduct
- Weighted Cumulative GPA

### FR-18
System must display signature information, including:
- Principal Name
- Title
- Signature

### FR-19
System must generate the transcript in a structured layout consisting of:
- Header Area
- Per Academic Year Area
- Reference Area
- Bottom Summary Area
- Signature Area

### FR-20
System must use the correct data source mapping for each transcript field based on the approved source configuration.

### FR-21
System must generate transcript output consistently for all supported student levels and periods.

### FR-22
System must ensure transcript data reflects the latest available academic and subject result data at the time of generation.