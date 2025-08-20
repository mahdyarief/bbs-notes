[[2025-08-19]]
1. Revert back feature, show pickup list when student checkout
   ![](https://i.imgur.com/YwYdkjd.png)

[[2025-08-18]]
2. On sve exam time table, add sort on apps (Default Sort: Subject, Level, Paper, date) and make user can change order on (Subject, Level, Component, Date) order asc and desc.
   ![](https://i.imgur.com/xWkLoif.png)
3. Field mata_pelajaran yang ada di DB belum muncul di UI frontend
   ![](https://i.imgur.com/n1UGOBK.png)
4. Syntax error near ( when hit campuses endpoint), also happen when edit employee
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