# Sistem Keuangan Pengelolaan Sampah
## Desa Sambopinggir Kec. Karangbinangun Kab. Lamongan

Aplikasi web untuk mengelola keuangan iuran sampah, data pelanggan, tagihan bulanan, pembayaran, deposit pelanggan, pengeluaran, laporan, dan lokasi pelanggan.

## Fitur Utama

- Autentikasi pengguna dengan role `Admin` dan `Petugas`.
- Dashboard ringkasan pelanggan, tagihan belum lunas, tunggakan, pemasukan, dan pengeluaran.
- Manajemen data pelanggan, termasuk alamat, RT/RW, koordinat lokasi, status aktif, dan foto rumah.
- Peta lokasi pelanggan menggunakan data latitude dan longitude.
- Pembuatan tagihan pelanggan secara massal per periode.
- Pembayaran tagihan tunai dan/atau menggunakan saldo deposit pelanggan.
- Pengelolaan saldo deposit pelanggan dari kelebihan pembayaran.
- Pencatatan pengeluaran operasional.
- Laporan pemasukan, pengeluaran, dan piutang.
- Export laporan ke PDF dan Excel.
- Command otomatis untuk generate tagihan bulanan dan update status tagihan jatuh tempo.

## Hak Akses

| Role | Akses |
| --- | --- |
| Admin | Dashboard, pelanggan, tagihan, pembayaran, lokasi pelanggan, pengeluaran, laporan, dan pengguna |
| Petugas | Dashboard, tagihan, pembayaran, dan lokasi pelanggan |

## Teknologi

- PHP 8.2+
- Laravel 12
- MySQL atau SQLite
- Blade Template
- Tailwind CSS
- Alpine.js
- Vite
- Laravel DomPDF
- Maatwebsite Excel

## Persyaratan

Pastikan sudah terinstall:

- PHP 8.2 atau lebih baru
- Composer
- Node.js dan npm
- Database MySQL/MariaDB atau SQLite

## Instalasi Lokal

Clone repository:

```bash
git clone https://github.com/username/nama-repository.git
cd nama-repository
```

Install dependency PHP:

```bash
composer install
```

Install dependency frontend:

```bash
npm install
```

Salin file environment:

```bash
cp .env.example .env
```

Generate application key:

```bash
php artisan key:generate
```

Atur koneksi database di file `.env`.

Contoh MySQL:

```env
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=sistem_keuangan_sampah
DB_USERNAME=root
DB_PASSWORD=
```

Jalankan migrasi dan seeder:

```bash
php artisan migrate --seed
```

Buat symbolic link untuk file upload:

```bash
php artisan storage:link
```

Jalankan aplikasi:

```bash
php artisan serve
```

Jalankan Vite untuk asset frontend:

```bash
npm run dev
```

Aplikasi dapat dibuka di:

```text
http://127.0.0.1:8000
```

## Akun Default Seeder

| Role | Username | Password |
| --- | --- | --- |
| Admin | admin | admin123 |
| Petugas | petugas1 | petugas123 |

Segera ubah password default setelah aplikasi digunakan di lingkungan produksi.

## Command Artisan

Generate tagihan bulanan untuk semua pelanggan aktif:

```bash
php artisan tagihan:generate
```

Generate tagihan untuk periode tertentu:

```bash
php artisan tagihan:generate 2026-05
```

Update status tagihan yang melewati jatuh tempo:

```bash
php artisan tagihan:update-status
```

Auto debit saldo deposit untuk tagihan belum lunas:

```bash
php artisan deposit:auto-debit
```

## Scheduler

Aplikasi memiliki jadwal otomatis untuk:

- Generate tagihan setiap tanggal 1 pukul 00:00.
- Update status tagihan setiap hari pukul 00:00.

Untuk menjalankan scheduler Laravel di server, tambahkan cron berikut:

```bash
* * * * * cd /path/to/project && php artisan schedule:run >> /dev/null 2>&1
```

## Build Production

Build asset frontend:

```bash
npm run build
```

Optimasi Laravel:

```bash
php artisan config:cache
php artisan route:cache
php artisan view:cache
```

## Struktur Modul

- `Pelanggan`: pengelolaan data pelanggan dan foto rumah.
- `Tagihan`: pembuatan dan monitoring tagihan bulanan.
- `Pembayaran`: pencatatan pembayaran tunai/deposit.
- `Deposit`: saldo kelebihan pembayaran pelanggan.
- `Pengeluaran`: pencatatan biaya operasional.
- `Laporan`: rekap pemasukan, pengeluaran, piutang, PDF, dan Excel.
- `Lokasi Pelanggan`: visualisasi titik pelanggan pada peta.
- `Pengguna`: manajemen akun admin dan petugas.

## Testing

Jalankan test:

```bash
php artisan test
```

Atau melalui Composer:

```bash
composer test
```

## Lisensi

Proyek ini dibuat untuk kebutuhan pengelolaan keuangan sampah. Silakan sesuaikan lisensi repository sesuai kebutuhan.
