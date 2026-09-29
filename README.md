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

- **Kasir/Dashboard**: pencarian produk, keranjang, ubah kuantitas, validasi stok, pembayaran tunai, kembalian, dan riwayat penjualan terbaru.
- **Produk & Stok**: tambah/edit/hapus produk, restock, indikator stok menipis/habis, validasi input angka & teks.
- **Titik Titip**: daftar pedagang contoh, pemesanan draft lokal, serta fallback saat peta tidak tersedia/offline.
- **Keuangan**: ringkasan pemasukan/pengeluaran/arus kas, catat pengeluaran, filter riwayat, tren 6 bulan.
- **Data lokal**: backup JSON, restore backup dengan normalisasi aman, dan reset data.
- **Offline dasar**: service worker untuk cache halaman statis inti.

## Batasan

- Semua data disimpan di **localStorage browser** (per perangkat/per browser), tidak sinkron antar perangkat.
- Draft titik titip bersifat simulasi, tidak mengirim pesanan ke pedagang nyata.
- Ringkasan arus kas bukan laporan laba rugi lengkap.
