# pweb — Tugas Pemrograman Web (CodeIgniter 3)

Repo tugas mata kuliah **Pemrograman Web**: aplikasi CRUD berbasis
**CodeIgniter 3** dengan modul Mahasiswa, Fakultas, dan Program Studi.

## Fitur

- Login dan autentikasi pengguna (`Auth`)
- Dashboard (`Dashboard`)
- CRUD Mahasiswa (`Mahasiswa`) — modul acuan untuk pola CRUD
- CRUD Fakultas (`Fakultas`)
- CRUD Program Studi (`Prodi`)
  - Program Studi berelasi ke Fakultas lewat dropdown
  - Jenjang strata dipilih lewat radio button
- Modul pendukung: `Dasar`, `Test`

## File Tugas

- `instruksi-tugas-3.md` — instruksi **Tugas 3**: membuat CRUD Fakultas
  dan Program Studi dengan pola yang sama persis seperti fitur Mahasiswa.
- `tugas-3.sql` — skema database untuk Tugas 3.

## Teknologi

- PHP
- CodeIgniter 3
- MySQL
- HTML, CSS, JavaScript

## Struktur

```
pweb/
  application/
    controllers/   ← Auth, Dashboard, Mahasiswa, Fakultas, Prodi, Dasar, Test
    models/        ← MahasiswaModel, FakultasModel, ProdiModel
    views/         ← auth, dashboard, mahasiswa, fakultas, prodi, layout
    config/        ← database.php, config.php, dan konfigurasi lainnya
  system/          ← framework CodeIgniter
  tugas-3.sql      ← skema database Tugas 3
  instruksi-tugas-3.md ← instruksi Tugas 3
  index.php        ← entry point aplikasi
```

## Instalasi

### 1. Clone repo

```bash
git clone https://github.com/gededevadharma/pweb.git
cd pweb
```

### 2. Buat database

Import `tugas-3.sql` ke MySQL, lewat phpMyAdmin atau command line:

```bash
mysql -u root -p -e "CREATE DATABASE pweb"
mysql -u root -p pweb < tugas-3.sql
```

### 3. Atur koneksi database

Edit `application/config/database.php`, sesuaikan dengan MySQL kamu:

```php
'hostname' => 'localhost',
'username' => 'root',
'password' => '',
'database' => 'pweb',
```

### 4. Atur base URL

Edit `application/config/config.php`:

```php
$config['base_url'] = 'http://localhost/pweb/';
```

## Cara Menjalankan

### Opsi A — XAMPP / Laragon (disarankan)

1. Pindahkan folder `pweb` ke `htdocs` (XAMPP) atau `www` (Laragon).
2. Jalankan Apache dan MySQL.
3. Buka `http://localhost/pweb/` di browser.

### Opsi B — PHP built-in server

```bash
php -S localhost:8000
```

Lalu buka `http://localhost:8000/` di browser.

## Cara Pakai

1. Buka aplikasi, lalu login lewat halaman Auth.
2. Menu **Mahasiswa**: tambah, ubah, dan hapus data mahasiswa (tabel
   DataTable + satu form untuk tambah/ubah).
3. Menu **Fakultas**: kelola data fakultas dengan pola yang sama.
4. Menu **Prodi**: kelola program studi — pilih fakultas dari dropdown,
   lalu pilih jenjang strata lewat radio button.

## Lisensi

MIT (lihat `license.txt`).
