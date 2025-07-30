[[2025-07-30]]

1. BMT Subject di week List double, perlu di tambahkan field BMT 1 & BMT 2, serta filter BMT 1 & 2, serta filter Term & Week ✅  
   ![](https://i.imgur.com/SFxuSYp.png)
2. Error when set session , kena forbiden resource, di akun miss lily
   ![](https://i.imgur.com/RqEtxIG.png)
   ![](https://i.imgur.com/S7ghqIE.png)
3. Urutan by Subject Name then next by Level, then next by Paper. (ASC),
   ![](https://i.imgur.com/3514VIM.png)
4. Internal Error saat attach BMT Week (Update relation, 1 Academic Week bisa dipake di banyak Subject BMT)
   ![](https://i.imgur.com/YU3WmFX.png)






[[2025-07-29]]
1. Add delete row on SVE LIST, want to delete sve list not used (Remove from button Add Exam Type → Remove this,  membuat user bingung, better ada remove di list depan)
   ![](https://i.imgur.com/WNvZlGe.png)
   ![](https://i.imgur.com/A7vfoew.png)



[[2025-07-28]]
1. Only generate active subject on sve list pdf
   ![](https://i.imgur.com/4evdhe9.png)
2. Non Academic saat term 3 & term 4 diisi -1, nilai FYAnya tetep di bagi 4, harusnya di bagi 2 ✅  
   ![](https://i.imgur.com/NhtpFFv.png)
   ![](https://i.imgur.com/hEfLZ03.png)
3. Student saat promote, tidak bisa punya 2 kelas yang sama di tahun ajaran yang sama 
4. Jumlah mudir per kampus per level per kelas per subject (dashboard)
5. Saat generate report di check, apakah ada di student banding2, kalo tidak ada, tidak di generate. nilai tetep dinilai. ✅  
6. Buka filter AY untuk discipline overview
   ![](https://i.imgur.com/EqaFIAS.png)
7. Filter data di SOW dan di academic department files, di teacher portal bocor (maria.rhea.pikp & jonas.austria), harusnya muncul sesuai dengan subject yang diajar dan academic departmentnya
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
9. 
10. 


[[2025-07-25]]
1. Gradebook ngeblank di teacher portal ✅  
   ![](https://i.imgur.com/EHUgs7U.png)
   
   
[[2025-07-22]]
2. List chapter on last academic year, need to show up  ✅  
3. Add filter academic year on all chapter, so teacher can duplicate chapter from previous academic year ✅  
	1. Add filter chapter name and teacher name
	2. ![](https://i.imgur.com/BjQs9jp.png)
4. RBAC not show for BMT Week list, Manage SVE already check ✅  
   ![](https://i.imgur.com/lQdsQ4c.png)
5. Change nationality from indonesia to indonesian
   ![](https://i.imgur.com/eJ43sp8.png)
6. Next..

## Legacy Issue

1. Student yang statusnya Inactive, tetap muncul di Report & Certificate, dan Transcript Nilai
2. HOD bisa akses ke teacher portal dan bisa melihat semua subject di bawah academic departmentnnya, impact ke menu Resource