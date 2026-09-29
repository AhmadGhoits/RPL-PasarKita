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

- **Autentikasi lokal (prototype)**: Login, Sign Up, Logout, sesi aktif per browser, role **Admin** dan **Konsumer**, plus akun demo.
- **Kasir/Dashboard**: pencarian produk, keranjang, ubah kuantitas, validasi stok, pembayaran tunai (admin), dan riwayat transaksi.
- **Produk & Stok (Admin)**: tambah/edit/hapus produk, restock, indikator stok menipis/habis, validasi input angka & teks.
- **Belanja Konsumer**: katalog, keranjang, checkout sederhana (nama pembeli + metode bayar simulasi), order ID, status, dan riwayat pembelian per akun.
- **Titik Titip**: daftar pedagang contoh, pemesanan draft lokal, serta fallback saat peta tidak tersedia/offline.
- **Keuangan (Admin)**: ringkasan pemasukan/pengeluaran/arus kas, catat pengeluaran, filter riwayat, tren 6 bulan.
- **Data lokal**: backup JSON, restore backup dengan normalisasi aman, reset data transaksi (akun tetap aman).
- **Offline dasar**: service worker untuk cache halaman statis inti.

## Hak akses role

- **Admin**
  - Dapat mengakses Dashboard/Kasir, Produk & Stok, Titik Titip, dan Keuangan.
  - Dapat tambah/edit/hapus produk, tambah stok, catat pengeluaran, backup/restore/reset data transaksi.
  - Tetap dapat menggunakan alur belanja/kasir.
- **Konsumer**
  - Dapat mengakses Beranda/Katalog, Keranjang, Riwayat Pembelian, dan Titik Titip.
  - Dapat checkout pembelian, melihat riwayat miliknya sendiri.
  - Tidak dapat mengakses kontrol admin (tambah/edit/hapus/restock, pengeluaran, backup/restore/reset, area keuangan/produk admin).

## Akun demo

- Admin: `admin@pasarkita.local` / `Admin123!`
- Konsumer: `konsumer@pasarkita.local` / `Konsumer123!`

Anda tetap bisa membuat akun baru dari form **Sign Up**.

## Batasan

- Semua data disimpan di **localStorage browser** (per perangkat/per browser), tidak sinkron antar perangkat.
- Sistem autentikasi dan hashing password ini hanya untuk **demo/prototipe lokal** tanpa backend, tidak aman untuk produksi.
- Draft titik titip bersifat simulasi, tidak mengirim pesanan ke pedagang nyata.
- Ringkasan arus kas bukan laporan laba rugi lengkap.
