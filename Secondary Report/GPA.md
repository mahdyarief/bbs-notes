# GPA Transcript Report Mapping Matrix
## June & December

## Tujuan
Dokumen ini digunakan sebagai **mapping matrix** untuk proses generate report **GPA Transcript** periode **June** dan **December**.

Fokus dokumen ini:
- menampilkan **nama field yang muncul di report**
- menunjukkan **source data**
- menandai field yang **direct source** dan **derived**
- menjelaskan **rule Final Mark** untuk June dan December

![](https://i.imgur.com/Ft04Zap.png)


---

# 1. Student & School Information

![](https://i.imgur.com/P1ZDJFL.png)

| Report Section | Field in Report | Source Data                        | Type   | Notes                                                                            |
| -------------- | --------------- | ---------------------------------- | ------ | -------------------------------------------------------------------------------- |
| Header         | Report Title    | Static                             | Direct | Fixed as **GPA Transcript**                                                      |
| Header         | Name            | Student Master                     | Direct | Nama siswa                                                                       |
| Header         | Gender          | Student Master                     | Direct | Jenis kelamin siswa                                                              |
| Header         | Date of Birth   | Student Master                     | Direct | Tanggal lahir siswa                                                              |
| Header         | Enrollment Date | Ini belum tau dari mana?           | Direct | Tanggal masuk siswa                                                              |
| Header         | Graduation Date | Master Data Graduation Date        | Direct | Tanggal kelulusan siswa                                                          |
| Header         | Curriculum      | Static                             | Direct | Cambridge IGCSE and International A Levels                                       |
| Header         | CEEB Code       | Campus Identity: Using Campus Code | Direct | Kode CEEB sekolah                                                                |
| Header         | Accredited by   | Static                             | Direct | National Accreditation Board for Schools                                         |
| Header         | Campus          | Campus Master                      | Direct | Nama Campus di gabung ex: '**Pantai Indah Kapuk<br>Secondary & Junior College**' |
| Header         | Campus Address  | Campus / School Profile            | Direct | Alamat campus                                                                    |

---

# 2. Academic Year Information

![](https://i.imgur.com/ym2qZ45.png)
![](https://i.imgur.com/2tbKL3U.png)


| Report Section | Field in Report         | Source Data                              | Type    | Notes                               |
| -------------- | ----------------------- | ---------------------------------------- | ------- | ----------------------------------- |
| Academic Block | Academic Year           | Student Academic History                 | Direct  | Tahun akademik siswa                |
| Academic Block | Level / Grade           | Student Academic History                 | Direct  | Level siswa pada tahun tersebut     |
| Academic Block | Class / Homeroom        | Student Academic History / Class History | Direct  | Kelas di tahun tersebut             |
| Academic Block | 4-Year Academic History | Student Academic History                 | Derived | Tahun berjalan + 3 tahun sebelumnya |

---

# 3. Subject Detail Information

| Report Section | Field in Report  | Source Data                                                      | Type    | Notes                                                                                                                                 |
| -------------- | ---------------- | ---------------------------------------------------------------- | ------- | ------------------------------------------------------------------------------------------------------------------------------------- |
| Subject Table  | Subject          | Student Subject Enrollment / Subject Setup                       | Direct  | Subject yang diambil siswa                                                                                                            |
| Subject Table  | Unit             | Manage Subject Unit, Bobot unit diset per subject level, per AY. | Direct  | Bisa create baru, dengan otomatis ngelist subject secondary yang dipakai di semua kelas di AY berjalan & bisa copy dari AY sebelumnya |
| Subject Table  | Subject Category | Subject Master / Subject Setup                                   | Direct  | Dipakai untuk rule Final Mark                                                                                                         |
| Subject Table  | Final Mark       | Result Sources                                                   | Derived | Mengikuti rule June / December                                                                                                        |

---

# 4. Source Marks Used for Final Mark

| Source Mark | Source Data | Notes |
|---|---|---|
| FYA | Yearly Result | Final Year Assessment |
| SA1 | Semester Result | Semester 1 result |
| AS PUM | External Cambridge Result | Untuk JC2 December academic subject |
| A PUM | External Cambridge Result | Untuk JC2 June |
| IGCSE PUM | External Cambridge Result | Untuk Sec 4 December |

---

# 5. Final Mark Rule Matrix

| Report Period | Student Level | Subject Category | Final Mark Shown in Report | Source Data Used |
|---|---|---|---|---|
| December | JC2 | Academic | Highest of AS PUM and SA1 | AS PUM, SA1 |
| December | JC2 | Non-Academic | SA1 | SA1 |
| December | Sec 4 | All Subjects | Highest of FYA and IGCSE PUM | FYA, IGCSE PUM |
| December | Other Levels | All Subjects | FYA | FYA |
| June | JC2 | All Subjects | Highest of A PUM and FYA | A PUM, FYA |
| June | Other Levels | All Subjects | FYA | FYA |

---

# 6. Simplified Final Mark Mapping

## June Transcript

| Student Level | Subject Category | Final Mark Source |
|---|---|---|
| JC2 | All Subjects | Highest of **A PUM** and **FYA** |
| Other Levels | All Subjects | **FYA** |

## December Transcript

| Student Level | Subject Category | Final Mark Source |
|---|---|---|
| JC2 | Academic | Highest of **AS PUM** and **SA1** |
| JC2 | Non-Academic | **SA1** |
| Sec 4 | All Subjects | Highest of **FYA** and **IGCSE PUM** |
| Other Levels | All Subjects | **FYA** |

---

# 7. GPA & Grading Information

| Report Section | Field in Report | Source Data | Type | Notes |
|---|---|---|---|---|
| Grading Scale | Grade | Grading Scale Master | Direct | Ditampilkan di report |
| Grading Scale | Mark Range | Grading Scale Master | Direct | Contoh: 90–100 |
| Grading Scale | GP Value | Grading Scale Master | Direct | Nilai GPA per grade |
| Summary | GPA | GPA Summary / GPA Calculation | Derived | GPA per academic year |
| Summary | Weighted Cumulative GPA | GPA Summary / GPA Calculation | Derived | GPA kumulatif seluruh tahun di transcript |

Untuk menghitung GPA ada kalkulasi: Final Mark dimapping ke GPA Scale untuk mendapatkan GP Value, kemudian Formulasi GP Value x Unit / total Unit (Bukan total Subject)

---

# 8. Academic Summary Information

| Report Section | Field in Report | Source Data | Type | Notes |
|---|---|---|---|---|
| Summary | GPA | GPA Summary / GPA Calculation | Derived | GPA per tahun |
| Summary | Academic Rank / Class Size | Ranking Summary | Direct | Ranking siswa |
| Summary | Attendance | Attendance Summary | Direct | Format present/total days |
| Summary | Conduct | Conduct Summary | Direct | Contoh: A (Excellent) |
| Summary | Weighted Cumulative GPA | GPA Summary / GPA Calculation | Derived | Akumulasi seluruh tahun |

---

# 9. Signature Information

| Report Section | Field in Report | Source Data | Type | Notes |
|---|---|---|---|---|
| Signature | Principal Name | School Signatory / Campus Profile | Direct | Nama principal |
| Signature | Title | School Signatory / Campus Profile | Direct | Jabatan |
| Signature | Signature | School Signatory | Direct | Tanda tangan jika ada |

---

# 10. Mapping by Report Layout

## A. Header Area

| Field in Report | Source Data |
|---|---|
| GPA Transcript | Static |
| Name | Student Master |
| Gender | Student Master |
| Date of Birth | Student Master |
| Enrollment Date | Student Master |
| Graduation Date | Student Master |
| Curriculum | Student Master / Curriculum Master |
| CEEB Code | Campus / School Profile |
| Accreditation | Campus / School Profile |
| Campus | Campus Master |
| Campus Address | Campus / School Profile |

## B. Per Academic Year Area

| Field in Report | Source Data |
|---|---|
| Academic Year | Student Academic History |
| Level / Grade | Student Academic History |
| Subject | Student Subject Enrollment / Subject Setup |
| Unit | Subject Setup |
| Final Mark | Derived from FYA / SA1 / AS PUM / A PUM / IGCSE PUM based on period rule |

## C. Reference Area

| Field in Report | Source Data |
|---|---|
| Grading Scale | Grading Scale Master |
| Grade | Grading Scale Master |
| Mark Range | Grading Scale Master |
| GP Value | Grading Scale Master |

## D. Bottom Summary Area

| Field in Report | Source Data |
|---|---|
| GPA | GPA Summary / GPA Calculation |
| Academic Rank / Class Size | Ranking Summary |
| Attendance | Attendance Summary |
| Conduct | Conduct Summary |
| Weighted Cumulative GPA | GPA Summary / GPA Calculation |

## E. Signature Area

| Field in Report | Source Data |
|---|---|
| Principal Name | Signatory Master / Campus Profile |
| Title | Signatory Master / Campus Profile |
| Signature | Signatory Master |

---

# 11. Direct Source vs Derived Field

## Direct Source Fields

| Field Group | Source Data |
|---|---|
| Student Information | Student Master |
| School Information | Campus / School Profile |
| Academic Year / Level | Student Academic History |
| Subject Name | Student Subject Enrollment / Subject Setup |
| Unit | Subject Setup |
| Grading Scale | Grading Scale Master |
| Rank / Attendance / Conduct | Related summary modules |
| Principal Info | Signatory Master |

## Derived Fields

| Field in Report | Derived From |
|---|---|
| 4-Year Academic History | Student Academic History |
| Final Mark | FYA / SA1 / AS PUM / A PUM / IGCSE PUM |
| GPA | Final Mark + Unit + Grading Scale |
| Weighted Cumulative GPA | GPA calculation across transcript years |

---

# 12. Critical Mapping for June & December

| Field in Report | June Source | December Source |
|---|---|---|
| Final Mark – JC2 Academic | Highest of A PUM and FYA | Highest of AS PUM and SA1 |
| Final Mark – JC2 Non-Academic | Highest of A PUM and FYA | SA1 |
| Final Mark – Sec 4 | FYA | Highest of FYA and IGCSE PUM |
| Final Mark – Other Levels | FYA | FYA |
| GPA | From final mark + unit + grading scale | From final mark + unit + grading scale |
| Weighted Cumulative GPA | From all included years | From all included years |

---

# 13. Short Version for Handover

| Field in Report | Source |
|---|---|
| Student Biodata | Student Master |
| School Information | Campus / School Profile |
| Academic Year & Level | Student Academic History |
| Subject | Student Subject Enrollment / Subject Setup |
| Unit | Subject Setup |
| Final Mark | FYA / SA1 / AS PUM / A PUM / IGCSE PUM based on June/December rule |
| GPA | GPA Calculation / GPA Summary |
| Weighted Cumulative GPA | GPA Calculation / GPA Summary |
| Rank / Attendance / Conduct | Related summary modules |
| Principal Info | Signatory Master |

---