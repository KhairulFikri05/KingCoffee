# ☕ SIM-C KING COFFEE

Aplikasi Sistem Informasi Manajemen Kafe berbasis web, dibangun dengan Laravel 12 dan Filament Admin v3. Proyek ini dikembangkan untuk membantu kafe mengelola menu, pesanan pelanggan, integrasi pembayaran digital, dan pelaporan melalui panel admin yang modern, elegan, dan responsif.

## 🚀 Fitur Utama

* **Katalog Menu & Pemesanan Publik:** Pelanggan dapat melihat menu dan memasukkannya ke keranjang.
* **Checkout & Integrasi Payment Gateway:** Pembayaran otomatis menggunakan Midtrans API.
* **Pilih Nomor Meja:** Pelanggan dapat menentukan meja secara mandiri saat *checkout*.
* **Dashboard Admin berbasis Filament:** Manajemen data yang interaktif untuk pemilik atau admin kafe.
* **Desain Fully Responsive:** Tampilan UI/UX disesuaikan dengan tema estetika *coffee shop* (mobile & desktop).

## 👨‍💼 Developer

* **Nama:** Khairul Fikri
* **NPM:** 2408107010032
* **Program Studi:** Informatika, Universitas Syiah Kuala

## 🛠️ Teknologi yang Digunakan

* Laravel 12
* Filament Admin (v3)
* Blade Template & Livewire
* Midtrans API (Payment Gateway)
* Tailwind CSS & Bootstrap 5
* MySQL

## 🧑‍🍳 Cara Instalasi (Localhost)

Ikuti langkah berikut untuk menjalankan aplikasi:

1. **Clone Repository:**
Jalankan perintah `git clone https://github.com/username-lu/nama-repo-lu.git` di terminal.
2. **Install Dependency Composer:**
Jalankan perintah `composer install`. Pastikan PHP 8.2+ sudah terpasang.
3. **Install Dependency Frontend:**
Jalankan perintah `npm install && npm run build`.
4. **Konfigurasi Environment:**
Salin file `.env.example` menjadi `.env`.
5. **Generate Key Aplikasi:**
Jalankan perintah `php artisan key:generate`.
6. **Konfigurasi Database:**
Sesuaikan file `.env`, contoh:
```env
APP_NAME="SIM-C KING COFFEE"
APP_URL=http://127.0.0.1:8000
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=sim_c
DB_USERNAME=root
DB_PASSWORD=

```


7. **Migrasi Data:**
Buat database `sim_c` via phpMyAdmin, lalu jalankan `php artisan migrate`.
8. **Jalankan Server:**
Jalankan perintah `php artisan serve`.
9. **Akses Aplikasi:**
Buka `http://127.0.0.1:8000` di browser.

## 🔑 Akses Admin

* **URL:** `http://127.0.0.1:8000/admin`
* **Email:** admin@simc.com
* **Password:** password

Jika user admin belum ada, buat manual via Tinker (`php artisan tinker`):

```php
\App\Models\User::create(['name' => 'Admin Kafe', 'email' => 'admin@simc.com', 'password' => bcrypt('password')]);

```

## 🪠 Troubleshooting

| Masalah | Solusi |
| --- | --- |
| **Class not found saat migrate** | Jalankan `composer dump-autoload` |
| **Gagal konek ke database** | Periksa `DB_DATABASE`, `DB_USERNAME`, dan `DB_PASSWORD` di `.env` |
| **Akses /admin/login tapi kosong** | Pastikan file konfigurasi Filament aman dan user admin sudah dibuat. |
| **Halaman blank / Error 500** | Periksa log di `storage/logs/laravel.log` |
| **Error pop-up Midtrans tidak muncul** | Pastikan `MIDTRANS_SERVER_KEY` dan `MIDTRANS_CLIENT_KEY` di `.env` sudah terisi dengan benar. |

## 📦 Perintah Composer & Artisan yang Berguna

```bash
composer install          # Install dependency PHP
npm install               # Install dependency Node.js
php artisan storage:link  # Buat symbolic link untuk menampilkan gambar menu
php artisan serve         # Jalankan server lokal

```

## 📸 Screenshot Tampilan Aplikasi

*(Tambahkan gambar screenshot Halaman Utama, Keranjang Pesanan, dan Dashboard Filament di sini)*
