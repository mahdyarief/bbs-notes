---
share_link: https://share.note.sx/99tsyg1a#2v9sY8chkTY36oz6hjsKfV/fsMBtibs8nLCmq1nQpXI
share_updated: 2025-01-20T16:36:36+07:00
---
Prelims
	A Level (JC 2)
	AS Level (JC 2)
	IGCSE (JC 1 → english)
	IGCSE (Sec 4 → on selected Subject)
1. Setup subject using cambridge
2. di assign bareng dengan subject in year, tambahin flag prelims
3. on grading Using Component on sve as TT 1 dll 

4. Component itu ada relasi ke subject
### 0.1 Prelims Grade 
1. Define Treshold to AS Prelim
	1. Subject yg Cambridgenya A Level
	2. Add AS or A 
2. IGCSE → G Grade → have a*
	1. AS Level → Grade E tanpa a*
	2. A Level → Grade E using a*
	3. Rumus a* = Selisih Grade A & Grade B + Grade A
	4. a* itu threshold
3. Ada Threshold → average dari jumlah years
   ![](https://i.imgur.com/jrk0gnW.png)
dan tambahkan syllabus threshold
NEED Rumus untuk menghitung Yearly Average, Yearly average digunakan untuk menghitung nilai akhir threshold
4. di teacher
   ![](https://i.imgur.com/7GeGXJ5.png)
Formula
![](https://i.imgur.com/XIo4RWd.png)
![](https://i.imgur.com/p6njtdE.png)

AS Average:
paper_component: (25 / Total Mark (Highest Year) * 100) * (weighted/100) → ambil dari threshold weight
∑ per component * active paper weighted
![](https://i.imgur.com/xY34RTM.png)

Hasilnya di rounded
![](https://i.imgur.com/lm1KyYP.png)


AS PUM
1. Check Nilai AS Avg, → Compare ke AS Threshold (ambil yang AVG > Grade TH) 
   ((62-62) / (100 -62))20  → Ambil saat compare disini
   ![](https://i.imgur.com/UPld2fR.png)

![](https://i.imgur.com/SVd3mfF.png)

1. Case: Dihitung setelah pembulatan
	1. Grade A* : Case: (((68 - 62) / (100 - Treshholdnya )) * 20) + 90
	2. IF AS AVG → Grade A : Case: (((68 - 62) / (100 - Treshholdnya )) * 20) + 80
	3. Grade B : Case: (((57 - 54) / (TH A - TH B)) * 10) + 70 
	4. Grade C : Case: (((AS AVG - TH C) / (TH B - TH C)) * 10) + 60 
	5. __ sampe E → + 40
	6. Grade U: Case: (((AS AVG - 0) / (TH E - 0)) * 39) 
	7. Hasil akhir di bulatkan

AS Predicted
![](https://i.imgur.com/SyWBImV.png)

Prelims Predicted Grade Setting → Campus (Default Disable) → enum sejumlah threshold


- [ ] Add unlock shortcut to unlock gradebook
    ![](https://i.imgur.com/Z0QnZW2.png)
