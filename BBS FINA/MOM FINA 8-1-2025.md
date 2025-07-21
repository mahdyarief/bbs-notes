---
share_link: https://share.note.sx/ymkv5syb#GtT32oGO9zAjRQfQqIa6HUm9I+1Nd4h76L8dnnlsx+Y
share_updated: 2025-01-08T16:13:49+07:00
---
1. Saat sudah pembayaran pertama early, dan installment, harganya tetep early (need to check this case)
2. Buka pilihan level, untuk mengakomodir penagihan product di level berikutnya **(Task)** https://openproject.klabs.dev/projects/bbs-fina/work_packages/3895/activity?query_id=154
   ![](https://i.imgur.com/CMWsL8o.png)
3. Status billing masih open, namun payment dan voucher datenya terisi **(Issue)** https://openproject.klabs.dev/projects/bbs-fina/work_packages/3896/activity?query_id=154
   ![](https://i.imgur.com/ygTqLS2.png)
4. Setelah bikin invoice, data billingnya tidak muncul di invoice, nominalnya sesuai, tapi data billingnya tidak muncul **(Task)** https://openproject.klabs.dev/projects/bbs-fina/work_packages/3897/activity?query_id=154
   ![](https://i.imgur.com/V9nUoaF.png)
5. Invoice total + overdue https://openproject.klabs.dev/projects/bbs-fina/work_packages/3917/activity?query_id=154
   ![](https://i.imgur.com/JItPmYT.png)
7. Overpayment active jika billing item fully paid https://openproject.klabs.dev/projects/bbs-fina/work_packages/3923/activity?query_id=154
   ![](https://i.imgur.com/MIor0yw.png)

8. Tambahkan kolom Payment & rubah payment yg sekarang, jadi total payment & add logo https://openproject.klabs.dev/projects/bbs-fina/work_packages/3901/activity?query_id=154
    ![](https://i.imgur.com/ft1UCBc.png)
8. Urutan invoice https://openproject.klabs.dev/projects/bbs-fina/work_packages/3928/activity?query_id=154
	1. Overpayment
	2. Outstanding
	![](https://i.imgur.com/dywXS8U.png)

9. Tambah Saldo di wallet parent saat payment https://openproject.klabs.dev/projects/bbs-fina/work_packages/3929/activity?query_id=154
   ![](https://i.imgur.com/ZgIldT6.png)

10. Diinvoice print PDF, overpaymentnya di split per anak dari wallet https://openproject.klabs.dev/projects/bbs-fina/work_packages/3930/activity?query_id=154
11. Refund perlu ditambahkan source of refund → di check di eksisiting ; sudah ada proses refund, cuma saat pengajuan refund tidak berjalan proses approval refundnya
    ![](https://i.imgur.com/DsJrgZt.png)
    Field: Tanggal, Pilihan Bank & Nominal
12. Security Deposit dapat digunakan untuk pembayaran billing
13. set isEarly menjadi false secara otomatis ketika tanggal early date sudah lewat**
14. Request Kop Surat PNG, dari pak herman
15. Cancel invoice ketika sudah ada pembayaran sebagian.
