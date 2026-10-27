# RPL-PasarKita

PasarKita adalah aplikasi kasir & manajemen UMKM berbasis **HTML statis** (tanpa backend) untuk demo lokal.

## Menjalankan aplikasi

> Disarankan melalui localhost/HTTPS agar Service Worker aktif.

### Opsi 1: Python
```bash
cd /home/runner/work/RPL-PasarKita/RPL-PasarKita
python -m http.server 8080
```
Lalu buka `http://localhost:8080`.

### Opsi 2: VS Code Live Server
Jalankan `index.html` memakai Live Server (`http://127.0.0.1:*` atau `http://localhost:*`).

## Fitur utama

- **Autentikasi lokal (prototype)**: Login, Sign Up, Logout, sesi aktif per browser, role **Admin**, **Penjual**, dan **Pembeli**, plus akun demo.
- **Manajemen toko**: penjual dapat membuat/mengubah toko miliknya, menambahkan produk, dan mengubah stok sendiri. Admin dapat mengelola semua toko, produk, dan stok.
- **Belanja berbasis toko**: pembeli memilih toko, memilih produk dari toko tersebut, checkout, lalu melihat lokasi dan tautan direksi.
- **Peta toko**: admin dapat melihat semua lokasi toko; peta juga tersedia bagi pembeli dan penjual.
- **Tema**: tombol mode terang/gelap dengan preferensi tersimpan di browser.
- **Keuangan (Admin)**: ringkasan pemasukan/pengeluaran/arus kas, catat pengeluaran, filter riwayat, tren 6 bulan.
- **Data lokal**: backup JSON, restore backup dengan normalisasi aman, reset data transaksi (akun tetap aman).
- **Offline dasar**: service worker untuk cache halaman statis inti.

## Hak akses role

- **Admin** dapat mengelola semua toko dan stok, melihat peta semua toko, memakai kasir, serta mengakses keuangan dan backup.
- **Penjual** hanya dapat membuat/mengubah toko miliknya, menambahkan produk ke toko sendiri, dan menambah stok produk sendiri.
- **Pembeli** dapat memilih toko, memilih produk, checkout, melihat lokasi/direksi, dan melihat riwayat pembelian sendiri.

## Akun demo

- Admin: `admin@pasarkita.local` / `Admin123!`
- Penjual: `penjual@pasarkita.local` / `Penjual123!`
- Pembeli: `pembeli@pasarkita.local` / `Pembeli123!`

Anda tetap bisa membuat akun baru dari form **Sign Up**.

## Batasan

- Semua data disimpan di **localStorage browser** (per perangkat/per browser), tidak sinkron antar perangkat.
- Sistem autentikasi dan hashing password ini hanya untuk **demo/prototipe lokal** tanpa backend, tidak aman untuk produksi.
- Pesanan dan pembayaran masih simulasi lokal; tautan direksi membuka layanan peta eksternal.
- Ringkasan arus kas bukan laporan laba rugi lengkap.
