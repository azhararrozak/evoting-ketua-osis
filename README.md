# Aplikasi E-Voting OSIS

Selamat datang di project E-Voting OSIS. Ini adalah aplikasi berbasis website untuk melakukan pemilihan ketua OSIS (atau voting lainnya) secara digital. Aplikasi ini dirancang agar mudah digunakan dan memiliki fitur penghitungan suara secara real-time.

## 📋 Fitur Utama
*   **Halaman Login**: Keamanan akses untuk pemilih dan admin.
*   **Dashboard Admin**: Mengelola data calon, melihat hasil voting, dan menambah kandidat.
*   **Halaman Voting**: Antarmuka pemilihan yang simpel untuk pengguna.
*   **Real-time Result**: Hasil voting dapat dilihat secara langsung tanpa perlu refresh halaman (menggunakan Socket.io).
*   **Pencegahan Pemilih Ganda**: Sistem memastikan satu akun hanya bisa memilih satu kali.

## 💻 Persyaratan Sistem
Sebelum menginstall, pastikan komputer Anda sudah terinstall aplikasi berikut:
1.  **Node.js**: Untuk menjalankan aplikasi website ini. [Download di sini](https://nodejs.org/).
2.  **XAMPP** (atau MySQL Server lainnya): Untuk database penyimpanan data. [Download di sini](https://www.apachefriends.org/index.html).
3.  **Git** (Opsional): Untuk mengunduh project ini.

## 🚀 Cara Install (Langkah demi Langkah)

Ikuti panduan ini untuk menginstall aplikasi di komputer Anda:

### 1. Download Project
Download source code project ini atau clone menggunakan git:
```bash
git clone <url-repository-ini>
```
Lalu masuk ke folder project tersebut.

### 2. Install Dependencies
Buka terminal (Command Prompt atau PowerShell) di dalam folder project, lalu ketik perintah berikut untuk menginstall library yang dibutuhkan:
```bash
npm install
```
Tunggu hingga proses selesai.

### 3. Persiapan Database
Kita perlu menyiapkan database agar aplikasi bisa menyimpan data.
1.  Buka **XAMPP Control Panel** dan nyalakan module **Apache** dan **MySQL** (klik tombol *Start*).
2.  Buka browser dan akses `http://localhost/phpmyadmin`.
3.  Buat database baru dengan nama: `VOTING_OSIS`.
4.  Pilih database yang baru dibuat, lalu klik tab **Import**.
5.  Klik **Choose File** dan cari file `VOTING_OSIS.sql` yang ada di dalam folder `library/` di project ini.
6.  Klik tombol **Go** (atau Kirim) di bagian bawah untuk mengimport tabel dan data dummy.

### 4. Konfigurasi Database (Opsional)
Secara default, aplikasi ini diatur untuk terhubung ke database dengan:
*   Host: `127.0.0.1`
*   User: `root`
*   Password: (kosong)
*   Database: `VOTING_OSIS`

Jika settingan MySQL di komputer Anda berbeda (misalnya ada passwordnya), silakan edit file `src/utils/db.js` dan sesuaikan bagian ini:
```javascript
const db = mysql.createConnection({
    host:'127.0.0.1',
    user:'root',        // Ubah jika user anda bukan root
    password: '',       // Isi jika mysql anda ada passwordnya
    database: 'VOTING_OSIS'
})
```

### 5. Menjalankan Aplikasi
Setelah semua siap, kembali ke terminal di folder project dan jalankan perintah:
```bash
npm start
```
Jika berhasil, akan muncul pesan `listen on port 3000` dan `Connected to database`.

## 📖 Cara Penggunaan

1.  Buka browser (Chrome, Firefox, dll).
2.  Akses alamat: `http://localhost:3000`.
3.  Anda akan diarahkan ke halaman login.

### Akun Login Default
Berikut adalah beberapa akun yang sudah tersedia di database bawaan untuk pengetesan:

**Akun Admin** (Untuk mengelola calon dan melihat hasil):
*   **Username**: `voyager`
*   **Password**: `naughty12`

**Akun Pemilih (User)**:
*   **Username**: `monitu12` | **Password**: `monitu12`
*   **Username**: `badboy` | **Password**: `badboy`
*   **Username**: `niki` | **Password**: `niki`
*   **Username**: `dedi` | **Password**: `dedi`
*   **Username**: `yuri` | **Password**: `yuri`

*(Catatan: Jika user sudah memilih, mereka tidak bisa memilih lagi. Anda bisa mereset data di database jika ingin mencoba ulang).*

## 🛠️ Teknologi yang Digunakan
*   **Backend**: Node.js, Express.js
*   **Database**: MySQL
*   **Real-time Engine**: Socket.io
*   **Frontend**: HTML, CSS, HBS (Handlebars) Templating Engine

---
Dibuat dengan ❤️ untuk pembelajaran dan keperluan OSIS.
