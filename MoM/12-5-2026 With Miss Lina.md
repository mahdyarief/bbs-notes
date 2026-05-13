
Item Analysis

Input Jawaban Siswa (Upper Primary P3 - P6)
English (Paper Based) (Pilih salah satu paper yang ada di SVE Component)
Math
Science
Chinese
B Indo

(View Teacher)

Semua teacher didalam kampus yang sama
Hint option dari A - D (1 - 4) by type number
![](https://i.imgur.com/s9VpGzZ.png)


Tiap Paper ada Format Jawaban (MCQ & Isian Singkat), 
Setup Section dan jumlah Soal (ada jawaban benar)

Input setup
![](https://i.imgur.com/RJvqfTW.png)

![](https://i.imgur.com/ujNVksL.png)

![](https://i.imgur.com/Sg7tvDA.png)
MCQ ABCD, Short Answer → Open Ended (Choose Type)
![](https://i.imgur.com/JNANkd6.png)
Mark default 1.50 (decimal) 
Facility Index & Determine Index

![](https://i.imgur.com/gJR9zCB.png)

![](https://i.imgur.com/rkl7Hg3.png)

Input result score, misal max mark 2, pilihan input 0.5, 1, 1.5



![](https://i.imgur.com/v8T3yAi.png)

![](https://i.imgur.com/WiBMbpZ.png)

![](https://i.imgur.com/KU0yV82.png)

Beri informasi jawaban benar, jawaban benar yang di bold, 
(Diurut dari tertinggi kerendah) Population Size > dari 20 > constanta 27% dari total population
Case Total student 90, Maka up 24.3, pembulatan jadi 24
Upper Group : 27% tertinggi
Lower Group : 27% Terendah

Population Size <= dari 20. pakai fix 10 // tidak ada yang pake fix

![](https://i.imgur.com/GiGbrwM.png)

Dicari yang ngisi ABCD 

![](https://i.imgur.com/HOFHfQY.png)


Facility Index (Jumlah siswa menjawab benar / jumlah seluruh siswa) (keseluruhan grup)
Discrimination Index (Selisih FI Upper Group - Lower Group)
![](https://i.imgur.com/dzWlZkj.png)



Short Answer → Open Ended
![](https://i.imgur.com/iGtbYvx.png)
average score / item
FI (average score ) → Avg Correct / Q mark → ![](https://i.imgur.com/rzJv88n.png)
DI (selisih FI Upper - Lower)

![](https://i.imgur.com/kmF9h38.png)

Grade

Deadline di 20 - 21 May


formulasi untuk grade dari setiap soal
=IF(N4<0,"F",IF(N4=0,"E",IF(M4>0.8,"A",IF(M4>0.3,"B",IF(M4>0.2,"C","D")))))
M4 = FI ; N4 = DI 

ada grade descriptor
| A   | Easy item, place at the beginning of test                                                                                                                                                                                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| B   | Item of average difficulty                                                                                                                                                                                                           |
| C   | Very Difficult item which discriminates well, use sparingly                                                                                                                                                                          |
| D   | Very difficult item, may be testing specialized or obscure knowledge                                                                                                                                                                 |
| E   | Discard, does not contribute reliability                                                                                                                                                                                             |
| F   | Check for mis-key or wrong acceptable answers. If there is no mis-keying, perhaps then the upper group learned the materials either incompletely or entirely incorrectly, and improvement should be towards the instruction/teaching |



|   |   |   |   |   |   |   |
|---|---|---|---|---|---|---|
|Grade|Desc|Item|Score|%||Standard|
|A|Easy|10|11|22.00%||30%|
|B|Average|31|35|70.00%||50%|
|C|Difficult|1|1|2.00%||20%|
|D|Very Difficult|2|3|6.00%||0%|
|E|Poor Item|0|0|0.00%||0%|
|F|Invalid Item|0|0|0.00%||0%|
|Total|   |44|50|100.00%|||

dan ada summarynya, item = jumlah soal, score = total mark dari semua soal, % adalah soal yang tergolong di grade itu, dan ada standard setiap grade