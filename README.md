*I just publish the information.*
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

## Struktur Modul

- `Pelanggan`: pengelolaan data pelanggan dan foto rumah.
- `Tagihan`: pembuatan dan monitoring tagihan bulanan.
- `Pembayaran`: pencatatan pembayaran tunai/deposit.
- `Deposit`: saldo kelebihan pembayaran pelanggan.
- `Pengeluaran`: pencatatan biaya operasional.
- `Laporan`: rekap pemasukan, pengeluaran, piutang, PDF, dan Excel.
- `Lokasi Pelanggan`: visualisasi titik pelanggan pada peta.
- `Pengguna`: manajemen akun admin dan petugas.

## Scheduler

Aplikasi memiliki jadwal otomatis untuk:

- Generate tagihan setiap tanggal 1 pukul 00:00.
- Update status tagihan setiap hari pukul 00:00.
