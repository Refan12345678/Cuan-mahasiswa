# CuanMahasiswa — REAL MVP

Ini adalah fondasi aplikasi marketplace pekerjaan kecil untuk mahasiswa.
Berbeda dari prototype sebelumnya, **saldo tidak dibuat otomatis dari tombol**.

## Alur uang nyata
1. Pemberi tugas membuat pekerjaan dan menetapkan budget.
2. Pemberi tugas melakukan pembayaran ke rekening/payment gateway milik platform.
3. Admin memverifikasi dana masuk dan mengaktifkan pekerjaan.
4. Mahasiswa mengerjakan dan mengirim hasil.
5. Pemberi tugas/admin menyetujui hasil.
6. Sistem baru mencatat penghasilan mahasiswa sebagai saldo yang berasal dari budget tugas.
7. Mahasiswa membuat permintaan pencairan.
8. Payout dilakukan melalui payment provider yang sudah dimiliki platform atau oleh admin secara manual.

## Penting
Kode ini **tidak mencetak uang** dan tidak mengandung saldo palsu. Agar payout benar-benar mengirim uang ke rekening/e-wallet, pemilik aplikasi harus memiliki akun bisnis/payment provider dan mengisi kredensialnya.

### Menjalankan backend
- Install Node.js 20+
- PostgreSQL 15+
- `cd backend`
- `npm install`
- salin `.env.example` menjadi `.env` dan isi DATABASE_URL + JWT_SECRET
- `npm run db:init`
- `npm start`

Backend default: `http://localhost:3000`

### Android
Buka folder `android` menggunakan Android Studio, ubah `BASE_URL` pada `MainActivity.java` ke URL backend yang sudah di-host, lalu Build APK.

### Status fitur
- Login/register: REAL, database PostgreSQL
- Task marketplace: REAL, database PostgreSQL
- Submission & approval: REAL
- Wallet ledger: REAL (berdasarkan transaksi database)
- Withdrawal request: REAL sebagai request payout
- Transfer bank/e-wallet otomatis: membutuhkan akun merchant/payment provider dan implementasi provider API; kredensial tidak boleh ditanam di APK.
