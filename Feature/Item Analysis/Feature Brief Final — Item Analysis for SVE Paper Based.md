## Feature Name
Item Analysis

## Objective
Menyediakan fitur **Item Analysis** untuk assessment **SVE Paper Based** pada level **Upper Primary**, agar sekolah dapat menganalisis kualitas setiap soal berdasarkan performa siswa.

## Business Goal
- Membantu teacher melakukan analisis kualitas soal per item.
- Menampilkan tingkat kesulitan soal melalui **Facility Index (FI)**.
- Menampilkan daya pembeda soal melalui **Discrimination Index (DI)**.
- Mendukung analisis untuk soal **MCQ** dan **Open Ended** dalam paper yang sama.
- Mempermudah input setup dan hasil melalui **import Excel**.

## Scope
- Level akademik: **Upper Primary**
- Assessment type: **SVE Paper Based**
- Analisis dilakukan berdasarkan **SVE Component** yang dipilih pada setup
- 1 paper dapat memiliki:
  - 1 section **MCQ**
  - 1 section **Open Ended**
- Output ditampilkan dalam bentuk **tabel per item**
- Hasil dapat **export ke Excel**

## Users & Access

### Teacher Portal
- Teacher dapat menginput dan melihat item analysis
- Semua teacher dapat mengakses selama berada dalam **kampus yang sama**
- Pada konteks **SVE Menu**, expert dapat akses melalui **SVE Assignment sebagai expert**

### Admin Portal
- Dapat diakses oleh:
  - **Principal**
  - **AB Board**

## Main Workflow

### 1. Setup Analysis Source
User memilih:
- SVE Component yang akan dianalisis
- Paper yang terkait

### 2. Setup Question Structure
Setup dapat dilakukan melalui:
- **upload Excel template**
- **edit langsung di sistem**

Data setup per item mencakup:
- item number
- section
- question type
- max mark / bobot
- correct answer untuk MCQ

### 3. Upload / Input Student Result
Hasil siswa dapat dimasukkan melalui:
- **import Excel**
- **edit langsung di sistem**

#### MCQ
- input jawaban siswa menggunakan **A / B / C / D**
- tujuan utama: mencatat benar / salah per item

#### Open Ended
- input berupa **score saja**

### 4. Auto Calculation
Setelah data hasil masuk atau diubah:
- sistem **langsung auto calculate**
- jika ada perubahan data, hasil analysis **auto ter-update**

### 5. View Result
Sistem menampilkan hasil analisis dalam **tabel per item**

### 6. Export Result
User dapat **export hasil item analysis ke Excel**

## Supported Question Types

### MCQ
- jawaban opsi: **A, B, C, D**
- memiliki correct answer
- sistem menghitung benar / salah berdasarkan jawaban siswa vs correct answer

### Open Ended
- input berupa skor
- tidak perlu simpan teks jawaban siswa

## Business Rules

### Grouping Rule
- Gunakan **konstanta 27%** untuk semua jumlah populasi
- **Upper Group** = 27% siswa dengan ranking tertinggi
- **Lower Group** = 27% siswa dengan ranking terendah
- Jika hasil desimal `.5`, maka **round up**

> Contoh: 24.5 menjadi 25

### MCQ Calculation
#### Facility Index (FI)
`FI = jumlah siswa menjawab benar / jumlah seluruh siswa yang ikut test`

#### Discrimination Index (DI)
`DI = FI Upper Group - FI Lower Group`

### Open Ended Calculation
#### Average Score per Item
- dihitung dari rata-rata skor siswa pada item tersebut

#### Facility Index (FI)
`FI = average score / question mark`

#### Discrimination Index (DI)
`DI = FI Upper Group - FI Lower Group`

## Result Table per Item
Setiap item minimal menampilkan:
- item number
- section
- question type
- correct answer
- jumlah siswa peserta
- ukuran upper group
- ukuran lower group
- distribusi jawaban MCQ
- average score untuk open ended
- FI
- DI

## Import / Export Requirement

### Import Excel
Harus tersedia template standar untuk:
1. **setup item**
   - item number
   - question type
   - section
   - max mark
   - correct answer

2. **student result**
   - student identifier
   - jawaban MCQ
   - score open ended

### Edit in System
- Data hasil import tetap bisa diedit di sistem

### Export Excel
- Hasil item analysis per paper dapat diexport ke Excel

## Functional Requirements

### FR-01
Sistem harus menyediakan setup item analysis untuk **SVE Paper Based**.

### FR-02
Sistem harus memungkinkan user memilih **SVE Component** yang akan dianalisis.

### FR-03
Sistem harus mendukung paper dengan section **MCQ** dan **Open Ended**.

### FR-04
Sistem harus mendukung upload Excel untuk setup item.

### FR-05
Sistem harus mendukung upload Excel untuk hasil jawaban / skor siswa.

### FR-06
Sistem harus memungkinkan user mengedit data setup dan hasil langsung di sistem setelah import.

### FR-07
Sistem harus menghitung hasil analysis otomatis setelah data tersimpan atau diperbarui.

### FR-08
Sistem harus menghitung **FI** dan **DI** untuk setiap item.

### FR-09
Sistem harus menampilkan hasil dalam bentuk **tabel per item**.

### FR-10
Sistem harus memungkinkan export hasil ke **Excel**.

### FR-11
Sistem harus membatasi akses teacher ke data dalam **kampus yang sama**.

### FR-12
Sistem harus menyediakan akses hasil analysis di:
- **Teacher Portal**
- **Admin Portal**

## Grade Classification per Item

Sistem harus menentukan **grade** untuk setiap item berdasarkan nilai **FI** dan **DI**.

### Formula
`Grade = IF(DI < 0, "F", IF(DI = 0, "E", IF(FI > 0.8, "A", IF(FI > 0.3, "B", IF(FI > 0.2, "C", "D")))))`

Keterangan:
- `FI` = Facility Index
- `DI` = Discrimination Index

### Grade Rules
- **F**
  - jika `DI < 0`
- **E**
  - jika `DI = 0`
- **A**
  - jika `DI > 0` dan `FI > 0.8`
- **B**
  - jika `DI > 0` dan `FI > 0.3` sampai `0.8`
- **C**
  - jika `DI > 0` dan `FI > 0.2` sampai `0.3`
- **D**
  - jika `DI > 0` dan `FI <= 0.2`

## Grade Descriptor

| Grade | Descriptor |
| --- | --- |
| A | Easy item, place at the beginning of test |
| B | Item of average difficulty |
| C | Very Difficult item which discriminates well, use sparingly |
| D | Very difficult item, may be testing specialized or obscure knowledge |
| E | Discard, does not contribute reliability |
| F | Check for mis-key or wrong acceptable answers. If there is no mis-keying, perhaps then the upper group learned the materials either incompletely or entirely incorrectly, and improvement should be towards the instruction/teaching |

## Additional Result Requirement per Item

Selain data analysis per item yang sudah ada, sistem juga harus menampilkan:
- grade item
- grade descriptor

## Grade Summary

Sistem harus menyediakan **summary distribusi grade** untuk seluruh item dalam paper.

### Summary Columns
- **Grade**
- **Desc**
- **Item**
- **Score**
- **%**
- **Standard**

### Summary Definitions
- **Item** = jumlah soal yang masuk ke grade tersebut
- **Score** = total mark dari semua soal yang masuk ke grade tersebut
- **%** = persentase jumlah soal pada grade tersebut terhadap total soal
- **Standard** = target standar distribusi per grade

### Standard Distribution
- **A** = 30%
- **B** = 50%
- **C** = 20%
- **D** = 0%
- **E** = 0%
- **F** = 0%

### Summary Total
Sistem harus menampilkan baris **Total** yang menjumlahkan:
- total item
- total score
- total percentage = 100%

## Additional Functional Requirements

### FR-13
Sistem harus menentukan **grade per item** secara otomatis berdasarkan formula FI dan DI.

### FR-14
Sistem harus menampilkan **grade descriptor** untuk setiap item.

### FR-15
Sistem harus menghasilkan **summary distribusi grade** untuk seluruh paper.

### FR-16
Sistem harus menghitung **Item**, **Score**, dan **%** pada setiap grade summary secara otomatis.

### FR-17
Sistem harus menampilkan **standard distribution** per grade pada summary.

## Assumption
- **Score** pada summary diasumsikan sebagai **akumulasi max mark** dari item-item yang masuk ke grade tersebut.
- Jika definisi **Score** berbeda, perlu dikonfirmasi lagi.

## Non-Functional / UX Notes
- Import template harus sederhana dan konsisten
- Hasil kalkulasi harus cepat karena auto-calculate
- Tabel hasil harus mudah dibaca untuk review akademik
- Perubahan data harus langsung tercermin pada hasil analysis

## Assumptions / Pending Clarification

### A. Dasar ranking untuk Upper Group dan Lower Group
Masih perlu dipastikan ranking siswa dibentuk berdasarkan:
- total score seluruh paper
- total score subject
- total score section

**Asumsi sementara:** gunakan **total score seluruh paper**.

### B. Blank / No Answer pada MCQ
Masih perlu dipastikan apakah blank answer dihitung sebagai:
- salah
- kategori kosong terpisah

**Asumsi sementara:** blank answer dihitung sebagai **salah**, tetapi tetap bisa ditampilkan dalam data mentah bila diperlukan.

### C. Formulasi lanjutan
Ada catatan bahwa akan ada **formulasi lanjutan** untuk interpretasi hasil, namun detailnya belum didefinisikan dalam brief ini.

## Out of Scope for This Phase
- Secondary
- Junior College
- filter / sorting lanjutan
- penyimpanan text jawaban open ended
- analysis di luar SVE Paper Based

