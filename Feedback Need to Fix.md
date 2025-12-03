[[2025-12-03]]
1. Add student classroom on export excel / Generate XLX in discipline report
   https://admin.smartbag.binabangsaschool.com/discipline?query=%7B%7D&pageSize=10&page=0&disciplineFormStatus=REPORTED&formType=DISCIPLINE_FORM
2. Add classroom on UI system table, and add generate XLX on Tardiness
   https://admin.smartbag.binabangsaschool.com/tardiness?query=%7B%7D&pageSize=10&page=0&formType=TARDINESS_FORM
[[2025-11-25]]
3. Add function to clear set exam time on timetable, so can set time null again
   ![](https://i.imgur.com/eaHr2hz.png)
4. List Bug BBS https://docs.google.com/spreadsheets/d/1FJXruGdBUqPaZ7pzBq4lUbjz1kyiufgyz118sdYiKdk/edit?gid=0#gid=0

[[2025-11-24]]
2. Have issue grade locked, on term berjalan
   ![](https://i.imgur.com/omkAYMI.png)

3. 
[[2025-11-21]]
3. Enhancement delete student from class in year, untuk enhancement, kalo bisa pas delete student dari kelasnya, jangan delete row di class year student2, tapi set statusnya jadi prospect dan current classyearnya di null in, karena jejaknya jadi ilang,
   Impact of this, calculating on attendance must be aware with student status
4. Saat calculating attendance perlu aware student status, yg prospect jangan dihitung
   ![](https://i.imgur.com/aF7gktx.png)


[7:23 AM](https://mattermost.klabs.dev/klabs/pl/hyou3oyfopyj8cfhuftgjtq7he)
	1. issue double name student udh fix semua harusnya di primary, jadi ga nunggu by report
[[2025-11-19]]
4. Saat Print schedule Papernya tidak muncul di jadwal
   ![](https://i.imgur.com/assDlR4.png)
   ![](https://i.imgur.com/xYz5FnL.png)
   kalo ada Papernya
   ![](https://i.imgur.com/5CE36uT.png)
   Paper 1 = P1, Paper 2 = P2
   ![](https://i.imgur.com/APr9WlM.png)




[[2025-11-18]]
2. Tambahkan filter academic Year, di header, dan by default filter current AY, di discipline report
   ![](https://i.imgur.com/oogbzHT.png)
   ![](https://i.imgur.com/83VflMn.png)
3. ada fungsi di table, 
   ![](https://i.imgur.com/d8FoDgP.png)
   Tapi kalo di column, dia bisa nambah, tapi ga bisa hapus, untuk hapus column
   ![](https://i.imgur.com/tLzSSD9.png)

[[2025-11-17]]
2. SVE Deadline Urutan, default urutan column, Assign → Printing Request  (Change Label from Printing Deadline to Printing Request Deadline) → Uploading → Timetable
3. Delete row table di ga bisa di delete, dan di buat fungsi full screen si document editor
   ![](https://i.imgur.com/CaQtV1E.png)
4. Add SVE Report, another Report, 
	1. Printing Details ✅  
	2. ❓ 
5. Printing Details
	1. Add Tanggal cetak di footernya (Printed On)
	2. Setiap halaman Ada header
	3. Untuk Paper yg ada Insert, ditambahkan kolom baru di bawahnya langsung dengan pembeda, Level, Component
	4. Insert jadiin Baris
	   case:
	   1 B Indo - Primary 3 - Paper 1
	   2 B Indo - Primary 3 - Paper 1 (INSERT) → Insert ambil dari QP → Marking Scheme NULL → Answer Sheet NULL
	   
	   ![](https://i.imgur.com/56yXAy2.png)
	5. Report Title → Primary / Secondary FYE (Printing Details)
	   ![](https://i.imgur.com/WP6CN60.png)
6. Untuk Label, concern di space antar Kotak
   ![](https://i.imgur.com/i0NRRJp.png)
   ![](https://i.imgur.com/hPTH2jz.png)
	1. Untuk text yg panjang auto di kecilin sizenya
	2. Cut Component from Paper 1 - Nama Component → Paper 1 (ambil sebelum space -)
	3. Cek Penamaan Programme Code
	   ![](https://i.imgur.com/c71SF9o.png)
7. Misclenous Label
   ![](https://i.imgur.com/SUiGnvp.png)
   ![](https://i.imgur.com/icrBGKR.png)
   Take Out Setter & Vetter Column
   Change Expert → Enclosed = isinya Nama Additional Component
   Script Enclosed Jumlah yang diinput

[[2025-11-13]]
3. Extra Printing Request langsung d tambahin (ini sample KJ)
   ![](https://i.imgur.com/efQTugJ.png)
   ![](https://i.imgur.com/razAxpA.png)
   disini masih 30

[[2025-11-11]]
2. Printing Details SVE
   Penambahan field Answer Sheet pada saat Printing request, sesuai dengan additional Component yg di set di SVE Component
   ![](https://i.imgur.com/DLPc0No.png)
   maka printing details akan kalkulasi dari sana, dan akan muncul kolom pada printing request
3. Column yg muncul sesuai dengan additional Paper yg di tick di SVE Component
   ![](https://i.imgur.com/BWIYvVW.png)
   ![](https://i.imgur.com/5O7jz94.png)
4. Nilai term 2 keunlock, saat nilai term 1 belum diisi, tapi saat ke term 1nya ga ke unlock, perlu di unlock subjectnya → **need kevin**
   → sebelumnya kalo nilai term 1 selalu open kalo null, ga aware sama lock subject
	1. Case: user: christly.pik | Primary 3 Initiative / Science | Liu Hehao
5. Rename Label Printing Deadline → Printing Request Deadline
   ![](https://i.imgur.com/8qrmViK.png)
   ![](https://i.imgur.com/B2TNWot.png)
6. Cek rootcause, daily_attendance double
   ![](https://i.imgur.com/zJcjPzR.png)
   https://mattermost.klabs.dev/klabs/pl/ttiqqda8zbnafr9kixgdq8e9nc
7. Impersonate for Admin Portal
   ![](https://i.imgur.com/JDiXR8v.png)

	   
[[2025-11-07]]
5. Discipline Report ✅  
	1. Number of report must be aware with Academic Year
	   Case: Student : Oliver Princeton Chamber, number of form is 4
	   ![](https://i.imgur.com/IVyhnl1.png)
	   if check on data detail
	   ![](https://i.imgur.com/DB8ogeH.png)
	   3 on ay 24/25
	   1 on ay 25/26
	   ![](https://i.imgur.com/daNFipw.png)
	   so it must be, when AY 24/25 number form is 3
	   when AY 25/26 number must be 1
   6. Data Export on Excel & PDF must be aware with filter data, if possible do all filter,
      if not filter by student, status, form issued, AY, and term
7. On tardiness Report, when select student, change student ID to Current Class Year ✅  
   ![](https://i.imgur.com/2o1pYYb.png)


[[2025-10-22]]
2. login error EmployeeDevice ✅  
   ![](https://i.imgur.com/S9vyUnb.png)
3. Check filter assignment ✅  
   ![](https://i.imgur.com/MOKjgfl.png)
   ![](https://i.imgur.com/Z8eJ0Oo.png)




[[2025-10-21]]
2. BMT file show, padahal blum d approve ✅  
   ![](https://i.imgur.com/93H0Xls.png)
   ![](https://i.imgur.com/h7vQ0W9.png)


[[2025-10-13]]
2. error create new parent ✅  
   ![](https://i.imgur.com/iraFTBQ.png)

[[2025-10-08]]
2. Move Attendace, saat promote, kalo ada attendance di kelas origin, di move ke kelas destination ✅  
3. Lock Unlock LO in Year ✅  
   ![](https://i.imgur.com/UWRAiqg.png)

[[2025-10-07]]
3. Login to account mr terence, create new test lesson,  ✅  
   ![](https://i.imgur.com/Kk92a1S.png)
   it show assign 2 student, 
   ![](https://i.imgur.com/u84DXqu.png)
   but when check no student selected, it make lesson cant delete
   ![](https://i.imgur.com/cUPEqib.png)
4. Pagination pagenya, ga ada di file sharing academic departments, replace pake component table yg di pake sama SOW, ini masih pake bbs table yg lama
   dan tambahkan departementnya di table, jadi fileName | AcademicDepartment ❗ 
   ![](https://i.imgur.com/lIUTgaZ.png)
   



[[2025-10-06]]
2. Daily attendance, not complete, akun maria rhea. udh di cek semua tapi ga complete, ini case apaan yg ga kehandle ya ✅  
   ![](https://i.imgur.com/JO4OlnY.png)
3. Change auto term to active term, jadi auto to active term ✅  
   ![](https://i.imgur.com/Oh8YLfA.png)
4. Error when create class_year ✅  
   ![](https://i.imgur.com/RVL4gAk.png)
5. Recheck waktu promote mindahin student campus apa enggak, hipotesa student dari pik Pre School, waktu di promote jadi Primary ✅  

[[2025-10-01]]
2. Disable auto open newtab link ✅  
[[2025-09-30]]
3. Pindah kelas sekalian bawa nilai dari kelas sebelumnya ✅  
   ![](https://i.imgur.com/8aDa9bD.png)
4. Late Printing Request Label ✅  
   ![](https://i.imgur.com/JBru4fb.png)
   ![](https://i.imgur.com/rWJUp8x.png)


[[2025-09-25]]
3. Value on dicipline overview ngaco, tapi di detailnya bener, di teacher di attendance summary juga salah, (impact on admin and teacher) ✅  
   ![](https://i.imgur.com/je9aHPK.png)
   ![](https://i.imgur.com/UPhnBYd.png)
4. Di LO saat diiisi nilai 0, di ga ngebaca BDCPnya
   ![](https://i.imgur.com/7QnPt6b.png)


[[2025-09-24]]
2. Tardiness not show, sample on student "Kennan Rhys Ng"
   ![](https://i.imgur.com/ClNdDij.png)
   ![](https://i.imgur.com/BqeM48W.png)
   Already update report
   List of complain
   Cayla Tiffany Lie: Tardiness = 1 ✅  
   Eleanor Esther Sucipto: Tardiness = 1 ✅  
   Eric Denant Astrianto: Tardiness = 1 ❌ Late 1 Absent 2, show absent only
   Geng Chen: Tardiness = 2 ❌ 
   Kennan Rhys Ng: Tardiness = 3 ❌ 
   Tristan Nathaniel Au: Tardiness = 2 ❌ 
   
   Issue not pattern
PIK, KJ, MLG, SMG, BDG, BPN

[[2025-09-23]]
2. List student always order by name
   ![](https://i.imgur.com/D1GKa6Y.png)
   ![](https://i.imgur.com/9dssdK9.png)
3. Epic Moment
   ![](https://i.imgur.com/EN4pSRV.png)
4. Template e-report dan print report di term 1 dan 3 ga sama templatenya
   **LO Report**
   E-Report
   ![](https://i.imgur.com/U9jymSF.png)
   Print Report
   ![](https://i.imgur.com/YP7qUT6.png)
   **P3-6 Report**
   E-Report
   ![](https://i.imgur.com/QQqj7Ba.png)
   Print Report
   ![](https://i.imgur.com/EQhsFik.png)
5. add filter CCA name on CCA Grade Setting
   ![](https://i.imgur.com/xLVWwoh.png)
6. Add default Value when create cca Grade setting to, 16,11,7,2 on each term
   ![](https://i.imgur.com/rnXpXxr.png)




[[2025-09-22]]
2. Hapus . (titik di courtesy)
   ![](https://i.imgur.com/2S2vTyH.png)
3. Print pdfnya kepotong
   https://teacher.smartbag.binabangsaschool.com/gradebook/101681
4. Saat ngisi academic week data, nyusahin, ga bisa validasinya ga terlalu strict? diisi cuma 1 week dlu aja gpp, jadi 1 1
   ![](https://i.imgur.com/EBcSi46.png)
5. Order Subject di Progres Report Belum Sesuai, order by category, lalu priority ✅  Belum update report
   ![](https://i.imgur.com/yN0TZUm.png)
6. Student Report Class Yearnya 0 , sync classyear, studentnya ga ada di class_year_student_student
   ![](https://i.imgur.com/eAAolWx.png)

7. 
[[2025-09-19]]
ELEARNING DAY PROBLEM
7. some case teacher select term 2, on chapter, so assignment is not show (not bug)
   ![](https://i.imgur.com/OWhxF2C.png)

8. Chinese Language Need to trace → wrong use of fill in the blank
   ![](https://i.imgur.com/G8sDjQZ.png)
9. Jumlah siswa ga sesuai di report di ftp sudah sesuai
   ![](https://i.imgur.com/AgFPMIc.png)
10. This morning down because need to update version of library → 

[[2025-09-17]]
2. saat scan attendance kelasnya salah: Ini Annabella saat ini sudah p5 G tapi ketika di scan masih di P4
   ![](https://i.imgur.com/C3pIX5g.png)
3. asd


[[2025-09-15]]
1. Saat di set HOD, semua subject muncul, belum aware subject di bawa master subjectnya, kadang muncul semua, kadang bener
   ![](https://i.imgur.com/MO4u298.png)
2. Upload erratum ga muncul
   ![](https://i.imgur.com/9ZwiuwZ.png)


[[2025-09-12]]
Cover page Template
2. Filter Programme di coverpage template error, ✅  
3. Tambahin font arial ✅  
4. Linenya dibuat lebih tebel (horizontal rule) ✅  
5. tinggi editornya, untuk view 50% 
[[2025-09-11]]
6. Add entry by saat ngisi nilai ftp / ebadges, supaya ke track siapa yg ngasih nilai
   ![](https://i.imgur.com/qviMhfc.png)
7. Copy cover page from select academic year, do able on each cover paper, not generate all ✅  

[[2025-09-10]]
1. Ini edit double ✅  
   ![](https://i.imgur.com/hpuKRQu.png)
2. Add info Level ✅  
   ![](https://i.imgur.com/6ANe2Zo.png)
3. 

[[2025-09-02]]
1. Check when send erratum, it need to email to all subject teacher (Teacher Portal)
2. SVE List detail still show all paper type, need to adjust show only for BMT and not BMT (Admin Portal)
   ![](https://i.imgur.com/QI4tvtk.png)
3. Implement HOD function on SVE Menu, using RBAC SVE Manage, but only show their subject based on master subject (Admin Portal)
	1. If user not HOD have access right manage SVE, it show all subject (Admin Portal)
4. Split RBAC SVE (Admin Portal)
	1. SVE Printing Request (its for Principal)
5. SVE Past Paper (Teacher Portal)
	1. can select all files exept current academic year
	2. and show all file like curren sve list, but for past AY
	3. Only show for SVE only, not for subject teacher
6. Final Menu (Teacher Portal)
	1. SVE List -> SVE Assignment  
	2. SVE File -> BMT File Download  
	3. Exam Supporting Files Download (HOD Access)
7. Change SVE Files to → BMT Files (Teacher Portal)
	1. Only show file for BMT, BMT 1 & 2
	2. Subject teacher show for based on subject their teach, spesific subject & level
	3. HOD show based on ther master subject, subject and all level
8. Exam Supporting Files Download (Teacher Portal)
	1. Show file for another BMT, to show audio File on H - 7 Exam date & H + 1 Exam date to show QP and MS
9. Recheck HOD can access to teacher portal, then when move to menu resource, can access subject based on their master subject, are it already implement or not?
	1. Because is related to HOD Files, so HOD can access to teacher portal & admin portal, to see SVE process, and, see SVE Result and resource created with teacher

[[2025-09-01]]
1. File BMT not show on teacher, file is already BMT ✅  
2. When bmt is in week, erratum file not open, it need to open on week -1 untul D-Week, and disable all upload when W + 1 ✅  
3. file download is sometimes not best quality, make blurry ✅  

[[2025-08-29]]
1.  Change on Report
   ![](https://i.imgur.com/dNWvc2k.png)
   make setting Attendance Detail (LO & GradeBook )
   Attendance 49
   Number of School Days: 50 | Absent: 3 Gabung W& Wo | Tardy: (Ambil Late)
2. Ukurannya se, apply di term 1 & 3 dulu
   ![](https://i.imgur.com/bClja67.png)

[[2025-08-27]]
1. Edit LO year, additionalnya kena pagination ✅  
   ![](https://i.imgur.com/sgbojDD.png)
2. file not show on submission summary & add printed on di submission summary
   ![](https://i.imgur.com/P9yB1FW.png)


[[2025-08-26]]
1. Component blum masuk ke coverpage
   ![](https://i.imgur.com/c1s5YYE.png)
2. SVE Cover page juga sort by subject, level, paper, seperti yang lainnya
   ![](https://i.imgur.com/rSdXmnh.png)
3. order di printing detail juga
   ![](https://i.imgur.com/xh1eKep.png)
4. Sort di pdf file BMT subject & level
   ![](https://i.imgur.com/cwArKVw.png)

5. Insert bukan dikanan, jumlahnya sama
   ![](https://i.imgur.com/AhGsUdM.png)
   ![](https://i.imgur.com/IlDNjnj.png)



[[2025-08-25]]
3. Generate coverpage & admin can edit result generate Coverpage ✅  
   ![](https://i.imgur.com/uSFAPKU.png)
4. [Enhance Feature] SVE Deadline di buat support special case level primary 6 seperti notes
   ![](https://i.imgur.com/x36BuXA.png)
5. Lengkapin SVE exam typenya di sve list detail, BMT 1 atau 2, bukan BMT aja
   ![](https://i.imgur.com/8LIxEqa.png)


[[2025-08-22]]
3. Open weekend on attendance, and make function can delete attendance ✅  
![](https://i.imgur.com/WKwiNJm.png)
4. error disticntAlias, di SVEList, BMTWeek & ErataList ✅  
![](https://i.imgur.com/JDSGtYD.png)
5. Show Student ID on db ✅  
   ![](https://i.imgur.com/ttafvmR.png)
   ![](https://i.imgur.com/fVLY1h6.png)




[[2025-08-19]]
1. Revert back feature, show pickup list when student checkout ✅  
   ![](https://i.imgur.com/YwYdkjd.png)

[[2025-08-18]]
2. On sve exam time table, add sort on apps (Default Sort: Subject, Level, Paper, date) and make user can change order on (Subject, Level, Component, Date) order asc and desc. ✅  
   ![](https://i.imgur.com/xWkLoif.png)
3. Field mata_pelajaran yang ada di DB belum muncul di UI frontend ✅  
   ![](https://i.imgur.com/n1UGOBK.png)
4. Syntax error near ( when hit campuses endpoint), also happen when edit employee ✅  
   ![](https://i.imgur.com/w8a8E9A.png)
   ![](https://i.imgur.com/bWZO3f6.png)




[[2025-08-11]]
Special meeting for enhancement primary function
1. Add force user change password, for still use default password ✅  
2. Add otp function if detect change from latest devices ✅  
[[2025-08-11]]
3. Take out Paper Name Initial ✅  
   ![](https://i.imgur.com/Cbs4Evn.png)
   ![](https://i.imgur.com/aiTtYcj.png)
4. Take out Primary 1 & 2 dari schedule ✅  
   ![](https://i.imgur.com/cEXjnt3.png)
5. Primary 6 Punya session & notes sendiri ✅  
   ![](https://i.imgur.com/3oE4qaS.png)
6. Subject Code saja yg d print schedule ✅  
   ![](https://i.imgur.com/TKwgemP.png)


7. edit parent error cause duplicate phone number, show error to not make user confuse ✅  
   ![](https://i.imgur.com/awzbNXn.png)
8. Sylabus Code not Mandatory ✅  
   ![](https://i.imgur.com/o0GCDcn.png)


[[2025-08-06]]
1. Filter student di class in year tidak jalan ✅  
   ![](https://i.imgur.com/2a9SGNc.png)

[[2025-08-05]]
2. [Enhance Feature] make enroll all on banding enroll, student assign to banding teacher ✅  
   ![](https://i.imgur.com/Vy5AGtd.png)
3. Detail when assign time table, add level ✅  
   ![](https://i.imgur.com/K9hzu2b.png)



[[2025-08-04]]
1. Grade tahun lewat masih bisa diedit ✅  
   ![](https://i.imgur.com/GffXzzs.png)
2. Exam Time Table ✅  
   ![](https://i.imgur.com/WYBzPDV.png)
   ![](https://i.imgur.com/eO7QsEx.png)
   ![](https://i.imgur.com/zkpKFYQ.png)

3. Can set week to null / no assign week ✅  
   ![](https://i.imgur.com/nvQxdPW.png)
4. BMT Weeklist download file format: AY_EXAMTYPE-SVE_BMTWeek_BMT Topic, contoh: **2526_BMT1-SVE & add BMT 1 / 2 di title ✅  
   ![](https://i.imgur.com/zOP3UtM.png)
   add Level di File Name
   2526 **Primary** FYE Timetable.

5. SubjectName only ✅  
   ![](https://i.imgur.com/Y99tDDc.png)
6. Penulisan Exam Type di Cover Page CAPS semua ✅   
   ![](https://i.imgur.com/T9VgXUD.png)
7. Position when assign not aware with AY ❗ 
   ![](https://i.imgur.com/EBfuAX5.png)
   ![](https://i.imgur.com/Pg6HQCE.png)
8. Download SVE List untuk BMT add field subject, level, Setter, Vetter, Week, Topic.
   Titlenya Setter-Vetter List (di BMT No Expert), Column Title, Expertnya di delete ❗ 
   ![](https://i.imgur.com/oTC0v3e.png)referensi
   ![](https://i.imgur.com/YVs2Hww.png)





[[2025-07-31]]
1. [Enhance Feature] General File Sharing, Memunculkan file yang di upload dengan 3 Scope, Subject - Academic Department - General (dapat dilihat oleh semua guru, di semua kampus)
   ![](https://i.imgur.com/GyWpZIQ.png) 
2. Take out assign expert on BMT ✅  
   ![](https://i.imgur.com/GDCiJbf.png)


[[2025-07-30]]

1. BMT Subject di week List double, perlu di tambahkan field BMT 1 & BMT 2, serta filter BMT 1 & 2, serta filter Term & Week ✅  
   ![](https://i.imgur.com/SFxuSYp.png)
2. Error when set session , kena forbiden resource, di akun miss lily ✅ ❗ 
   ![](https://i.imgur.com/RqEtxIG.png)
   ![](https://i.imgur.com/S7ghqIE.png)
	1. Set Sessionnya sudah ga forbiden, tapi jam yg di set samaa saat di view lagi gak konsisten ✅  
	   https://www.loom.com/share/08c01a65b0264724a2f6916f975add06?sid=06fdc01b-db10-4d63-bb61-5e139a630f95
	   ![](https://i.imgur.com/HZF2uTc.png) Saat Mau di save --- 
	   ![](https://i.imgur.com/9mHYoOI.png)
	   Setelah di Save


3. Urutan by Subject Name then next by Level, then next by Paper. (ASC), ✅   
   ![](https://i.imgur.com/3514VIM.png)
4. Internal Error saat attach BMT Week (Update relation, 1 Academic Week bisa dipake di banyak Subject BMT) ✅  
   ![](https://i.imgur.com/YU3WmFX.png)
5. Udd info di modal saat set BMT Week, dilengkapi dengan [Level], [Exam_Type], [Primary / Secondary / JC] ✅  
   ![](https://i.imgur.com/N0nIA0g.png)
6. ...







[[2025-07-29]]
1. Add delete row on SVE LIST, want to delete sve list not used (Remove from button Add Exam Type → Remove this,  membuat user bingung, better ada remove di list depan) ✅  ![](https://i.imgur.com/WNvZlGe.png)
   ![](https://i.imgur.com/A7vfoew.png)



[[2025-07-28]] ❗ 
1. Only generate active subject on sve list pdf [Invalid, Set Subject to Inactive, it will not Show] ✅  
   ![](https://i.imgur.com/4evdhe9.png)
2. Non Academic saat term 3 & term 4 diisi -1, nilai FYAnya tetep di bagi 4, harusnya di bagi 2 ✅  
   ![](https://i.imgur.com/NhtpFFv.png)
   ![](https://i.imgur.com/hEfLZ03.png)
3. Student saat promote, tidak bisa punya 2 kelas yang sama di tahun ajaran yang sama 
4. Jumlah mudir per kampus per level per kelas per subject (dashboard)
5. Saat generate report di check, apakah ada di student banding2, kalo tidak ada, tidak di generate. nilai tetep dinilai. ✅  
6. Buka filter AY untuk discipline overview ✅  
   ![](https://i.imgur.com/EqaFIAS.png)
7. Filter data di SOW dan di academic department files, di teacher portal bocor (maria.rhea.pikp & jonas.austria), harusnya muncul sesuai dengan subject yang diajar dan academic departmentnya ✅    
   ![](https://i.imgur.com/yeXLOP6.png)
8. [ENRICHMENT FEATURE] CCA In year, ada update entity & apply cca registration time per campus beda, tidak cukup di handling dengan RBAC, 
	1. Saat waktu registration bisa join, saat waktu habis join di disable
	2. Harus aware untuk click join saat di 23/24 1 slot terakhir, dan di hit 3 orang dalam waktu bersamaan, maka 2 orang yg tidak dpt di berikan modal message maaf registrasi sudah penuh.
	3. Add section cca yang di register, dan available CCA jangan di pagination, buka semua
	4. CCA rules, di set CCA → Category → CCA rules limit per category beda2 per kampus
	5. CCA registration bisa multi week (handling cca tryout untuk secondary, by default 1 week)
	6. Untuk field Description di buat Text Area, Remark dibuat Text Editor WYSWYG (karena ada kebutuhan input link url / link video) Add field price jangan nominal, gunakan Text Area.
   ![](https://i.imgur.com/wSgNfsL.png)
   ![](https://i.imgur.com/ruGS8Pw.png)
   ![](https://i.imgur.com/UllooZo.png)


[[2025-07-25]] ✅  
1. Gradebook ngeblank di teacher portal ✅  
   ![](https://i.imgur.com/EHUgs7U.png)
   
   
[[2025-07-22]] ❗ 
2. List chapter on last academic year, need to show up  ✅  
3. Add filter academic year on all chapter, so teacher can duplicate chapter from previous academic year ✅  
	1. Add filter chapter name and teacher name ✅  
	   ![](https://i.imgur.com/BjQs9jp.png)
4. RBAC not show for BMT Week list, Manage SVE already check ✅  
   ![](https://i.imgur.com/lQdsQ4c.png)
5. Change nationality from indonesia to indonesian 🎯  
   ![](https://i.imgur.com/eJ43sp8.png)

## Legacy Issue

1. Student yang statusnya Inactive, tetap muncul di Report & Certificate, dan Transcript Nilai
2. HOD bisa akses ke teacher portal dan bisa melihat semua subject di bawah academic departmentnnya, impact ke menu Resource