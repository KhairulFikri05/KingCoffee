Siap, **Bro F**! Ini adalah penyempurnaan final dari `README.md` lu.

Saya sudah memperbarui bagian **Daftar Fitur** dan **Struktur Database** agar 100% *match* (cocok) dengan *file SQL dump* yang barusan lu kirim. Dosen lu pasti bakal takjub karena aplikasi ini ternyata nggak cuma ngurusin kasir, tapi punya fitur CMS (*Content Management System*) lengkap untuk *landing page* kafe (seperti kelola *slider*, profil koki, event, dan testimoni).

Langsung *copy-paste* teks di bawah ini ke file `README.md` lu:

---

# ☕ SIM-C (Sistem Informasi Manajemen Cafe)

## 📖 Deskripsi Singkat Aplikasi

SIM-C (Sistem Informasi Manajemen Cafe) adalah aplikasi manajemen cafe berbasis web yang dirancang untuk membantu pengelolaan operasional cafe secara efisien dan terintegrasi. Sistem ini mencakup reservasi meja online, pengelolaan pesanan & transaksi kasir, menu digital, manajemen konten *landing page* kafe, serta laporan analitik bagi pemilik cafe untuk memantau performa bisnis.

Aplikasi ini dikelola oleh dua jenis pengguna:

* **Admin:** Mengelola seluruh operasional cafe (memantau meja, mencatat pesanan, memproses transaksi Midtrans, mengelola konten website/CMS, dan melihat laporan bisnis).
* **Pelanggan:** Dapat melihat profil kafe, melakukan reservasi meja secara online, serta memesan dan membayar pesanan langsung melalui integrasi *Payment Gateway*.

Proyek ini dikembangkan untuk keperluan akademik oleh **Kelompok 6** (termasuk Khairul Fikri - NPM 2408107010032), Program Studi Informatika, Universitas Syiah Kuala.

## 🎯 Tujuan Pengembangan Aplikasi

Mengotomatisasi proses operasional cafe dari manual menjadi digital. Aplikasi ini bertujuan untuk mempermudah pelanggan dalam mereservasi meja, menyediakan katalog menu yang dinamis, serta memberikan kemudahan bagi pemilik cafe dalam memantau pendapatan, mengelola konten promosi website, dan melacak status pesanan secara *real-time*.

## ✨ Daftar Fitur yang Tersedia

* **CMS Landing Page:** Manajemen konten website publik secara dinamis (Hero Sliders, Profil Chef, Event, Kontak, dan Testimoni).
* **Reservasi Meja Online:** Terintegrasi langsung dengan status meja untuk mencegah bentrok jadwal (*double-booking*).
* **Manajemen Status Meja:** Pemantauan *real-time* (kosong, reservasi, digunakan).
* **Katalog Menu Dinamis:** Pengelompokan menu berdasarkan kategori (`Starters`, `Main Course`, `Desserts`, `Drinks`) dan manajemen ketersediaan.
* **Payment Gateway (Midtrans):** Pembayaran terintegrasi langsung di sistem pesanan (status: `unpaid`, `paid`, `failed`).
* **Cetak Struk Digital:** *Invoice* dan bukti pembayaran pesanan.
* **Dashboard Admin Terpadu:** Antarmuka manajemen interaktif berbasis Filament v3 untuk mengatur seluruh operasional kafe.
* **Desain Fully Responsive:** Nyaman diakses melalui *mobile* maupun *desktop*.

## 🛠️ Teknologi, Framework, Library, dan Komponen yang Digunakan

* **Backend & Framework:** Laravel 12, PHP 8.2+
* **Admin Panel:** Filament Admin v3
* **Frontend:** Livewire, Blade Template, Tailwind CSS, Bootstrap 5
* **Database:** MySQL / MariaDB
* **Payment Gateway:** Midtrans API
* **Package Manager:** Composer 2.x, Node.js & NPM

## 🗄️ Struktur Database Utama

Proyek ini memiliki struktur relasional yang komprehensif, mencakup tabel operasional dan manajemen konten:

1. **Autentikasi:** `users` (Data Admin/Staff).
2. **Katalog Produk:** `menu_categories` dan `menu_items` (Menyimpan detail makanan, harga, gambar, dan status ketersediaan).
3. **Manajemen Meja & Reservasi:** `tables` (Status meja) dan `reservations` (Data booking pelanggan yang berelasi dengan `tables`).
4. **Transaksi & Pesanan:** `orders` dan `order_items` (Menyimpan keranjang pesanan pelanggan, total harga, relasi ke meja, serta *Snap Token* & *Payment Status* Midtrans).
5. **CMS / Profil Kafe:** `hero_sliders`, `about_contents`, `about_features`, `chefs`, `testimonials`, dan `featured_events` (Untuk kebutuhan *landing page* dinamis).

## ⚙️ Panduan Instalasi dan Menjalankan Aplikasi

### Persyaratan Sistem (*Requirements*)

* PHP 8.2+
* Composer 2.x
* MySQL / MariaDB
* Node.js & NPM

### Langkah Instalasi

1. **Clone repository:**
```bash

```



git clone https://github.com/username/sim-c.git
cd sim-c

```
2. **Install dependency:**
   ```bash
composer install
npm install && npm run build

```

3. **Konfigurasi Environment:**
Salin file konfigurasi:
```bash

```



cp .env.example .env

```
   Generate key aplikasi:
   ```bash
php artisan key:generate

```

Sesuaikan konfigurasi database dan Midtrans di file `.env`:

```env
APP_NAME="SIM-C Kelompok 6"
APP_URL=http://127.0.0.1:8000

DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=sim_c
DB_USERNAME=root
DB_PASSWORD=

MIDTRANS_MERCHANT_ID=your_merchant_id
MIDTRANS_CLIENT_KEY=your_client_key
MIDTRANS_SERVER_KEY=your_server_key
MIDTRANS_IS_PRODUCTION=false

```

4. **Siapkan Database:**
Buat database `sim_c` via phpMyAdmin atau CLI MySQL (`CREATE DATABASE sim_c;`).
5. **Jalankan Migrasi, Seeder & Storage Link:**
```bash

```



php artisan migrate --seed
php artisan storage:link

```
6. **Jalankan Server Lokal:**
   ```bash
php artisan serve

```

Buka `[http://127.0.0.1:8000](http://127.0.0.1:8000)` di browser.

### 🔑 Akses Admin & Troubleshooting

* **URL Login Admin:** `[http://127.0.0.1:8000/admin](http://127.0.0.1:8000/admin)`
* **Email Default:** `admin@example.com`

*(Jika user admin tidak bisa digunakan, buat paksa via terminal dengan perintah `php artisan tinker`, lalu paste: `\App\Models\User::create(['name' => 'Admin King Coffee', 'email' => 'admin@example.com', 'password' => bcrypt('password')]);`)*

**Tabel Penyelesaian Masalah:**

| Masalah | Solusi |
| --- | --- |
| *Class not found* saat migrate | Jalankan `composer dump-autoload` |
| Gagal konek ke database | Periksa `DB_DATABASE`, `DB_USERNAME`, `DB_PASSWORD` di `.env` |
| Halaman blank / error 500 | Cek log di `storage/logs/laravel.log` |
| Gambar menu/CMS tidak muncul | Jalankan `php artisan storage:link` |
| Session/cache error | Jalankan `php artisan config:cache` dan `php artisan cache:clear` |

## 📸 Screenshot Tampilan Aplikasi

*(Silakan tambahkan gambar screenshot Halaman Utama, Menu Katalog, Checkout Midtrans, dan Dashboard Admin Filament di sini sebelum dikumpulkan)*

---

Mantap! Struktur ini udah 100% *bulletproof* karena selaras sama kodingan dan *database* asli lu. Semangat ngegarap presentasinya, bray! 🔥
