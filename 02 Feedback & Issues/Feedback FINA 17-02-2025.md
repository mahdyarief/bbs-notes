Font Header: Lora / header Font

add next student class pake level + 1 dari active level [v]
![](https://i.imgur.com/RZDeL2g.png)

Add penalty date due date + 1 [v]
![](https://i.imgur.com/HCz9CN3.png)


add status d discount
![](https://i.imgur.com/2FEy3SX.png)

Add status student admission di menu student discount
![](https://i.imgur.com/4ARnl5y.png)
![](https://i.imgur.com/bniAXEj.png)


Add total overpayment di payment page [v]
![](https://i.imgur.com/Di4SXDk.png)

Bug edit early date, untuk product yg tidak ada earlynya [v]
![](https://i.imgur.com/waKJHlf.png)

RBAC untuk security deposit [v]

Pembayaran menggunakan security deposit, ketika status student = withdraw, → saat sudah dilakukan pembayaran menggunakan secdept / refund secdept, update status student menjadi alumni ⇒ saat withdraw, status student masih active [v]

invoice paid, dapat dilakuan create payment lagi untuk case pembayaran double [v]

tambahkan nama anak pada wallet [v]

Auto add penalty pada create payment ⇒ ambil penalty data di billing masukin ke invoice, relasi ke invoice saat terjadi payment pertama [v]

export billing report, masih membawa billing yg void [v]


## 1 Add variable for new student
1. Add student level, dari data student admission
2. Invoice description add when create invoice
   ![](https://i.imgur.com/p6d01Rc.png)
3. Saat di approve OA tidak membuat invoice, ambil seluruh billing yg statusnya open, dimasukin ke dalam 1 invoice, dan jadi invoice saat approve oa
4. Payment amount di isi saat approve payment - > drop payment dari parent → add partial payment saat approve payment (Disable payment di invoice parent portal)
5. Penalty akan di stop apabila sudah pembayaran 1/3 nilai billing

6. Rumus final price yg di FE diambil dari (finalprice + balance)
   ![](https://i.imgur.com/6dcXiAi.png)
7. Bulk billing di level branch, studentnya ga keget
   ![](https://i.imgur.com/shoU2qn.png)
8. Invoice dengan pembayaran sebagian, saat di tagihkan lagi impact ke invoice sebelumnya
9. Fungsi nge overdue billing invoicenya jadi tidak sesuai nilai final pricenya
10. Casenya: Term 1 bayar Full, Term 2 Kurang Bayar, Term 3 Over, Term 4 hasilnya gimana (Test Case)
11. student inactive muncul di studen billing


Flow Testing:
1. Create new student on admission (25/25) PIK TEST
2. Add registration and dp admission on student
3. Create Invoice → Registration Template, programme tidak ke panggil
   ![](https://i.imgur.com/ofJzhde.png)
   ![](https://i.imgur.com/ghqlZQW.png)
4. Create variable description Invoice → UI when create invoice
   ![](https://i.imgur.com/R1vsSBm.png)
