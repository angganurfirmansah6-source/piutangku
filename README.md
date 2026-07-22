# 🏢 PiutangKu - Aplikasi Manajemen Piutang

Aplikasi **local-first** untuk mengelola piutang perusahaan dengan antarmuka modern, keamanan RBAC, dan penyimpanan data lokal yang aman.

## ✨ Fitur Utama

✅ **Dashboard Real-time**
- Statistik total piutang, sisa piutang, dan pelanggan
- Grafik pembayaran interaktif
- Daftar transaksi terbaru

✅ **Manajemen Data**
- 👥 Pelanggan - Tambah dan kelola data pelanggan
- 🧾 Piutang - Catat invoice dan piutang perusahaan
- 💳 Pembayaran - Catat setiap pembayaran masuk
- 📄 Laporan - Generate laporan PDF siap cetak

✅ **Keamanan & Akses**
- RBAC (Role-Based Access Control) dengan 5 level role
- Password terenkripsi untuk setiap pengguna
- Autentikasi berbasis email & password

✅ **Teknologi**
- SQLite WASM - Database lokal tanpa server
- IndexedDB + LocalStorage - Penyimpanan data browser
- Chart.js - Visualisasi grafik pembayaran
- Single HTML File - Mudah di-deploy

## 🚀 Cara Mengakses

### Online (GitHub Pages)
```
https://angganurfirmansah6-source.github.io/piutangku/
```

### Lokal
1. Clone repository:
   ```bash
   git clone https://github.com/angganurfirmansah6-source/piutangku.git
   cd piutangku
   ```

2. Buka `index.html` di browser (Chrome, Firefox, Safari, atau Edge)

## 👥 Akun Demo

Pilih salah satu akun untuk login:

| Email | Password | Role |
|-------|----------|------|
| admin@piutangku.local | admin123 | Admin - Full Access |
| sales@piutangku.local | sales123 | Staf Penjualan - Input Piutang |
| keuangan@piutangku.local | keuangan123 | Staf Keuangan - Catat Pembayaran |
| manager@piutangku.local | manager123 | Manajer Keuangan - Monitor Piutang |
| owner@piutangku.local | owner123 | Pemilik - Dashboard & Pengaturan |

## 📋 Fitur Per Role

**Admin**: Semua fitur + Manajemen Pengguna
**Staf Penjualan**: Dashboard, Pelanggan, Input Piutang, Laporan
**Staf Keuangan**: Dashboard, Catat Pembayaran, Laporan
**Manajer Keuangan**: Dashboard, Monitor Piutang & Pembayaran
**Pemilik**: Dashboard, Pengaturan Data

## 💾 Backup & Restore Data

### Backup Data
1. Buka menu **Pengaturan**
2. Klik tombol **"Cadangkan Data"**
3. File `piutangku-backup.sqlite` akan otomatis terunduh

### Restore Data
1. Buka menu **Pengaturan**
2. Klik **"Pulihkan Data"**
3. Pilih file `.sqlite` yang sudah di-backup
4. Data akan dikembalikan otomatis

## 🏗️ Arsitektur Teknis

```
├── SQLite WASM (sql.js)
│   └── Database lokal di browser
├── IndexedDB
│   └── Penyimpanan persistent data
├── LocalStorage
│   └── Backup fallback (Base64 encoded)
├── Chart.js
│   └── Visualisasi data pembayaran
└── Premium UI Theme
    └── Modern gradient design
```

### Data Flow
1. User input data → JavaScript
2. JavaScript → SQL Query (sql.js)
3. Database update → IndexedDB save
4. Fallback → LocalStorage backup
5. Export → Download SQLITE file

## 📊 Database Schema

### Users
- Autentikasi & role-based access
- 5 akun demo sudah terisi

### Customers
- Data perusahaan pelanggan
- Kontak & alamat

### Receivables
- Invoice & transaksi piutang
- Auto-calculate sisa piutang via trigger

### Payments
- Pencatatan pembayaran masuk
- Auto-update status piutang

### Reports
- Riwayat laporan yang di-generate
- Export PDF ready

## 🐛 Bug Fixes & Improvements (v2.0)

✅ Fixed: Null pointer exception di chart rendering
✅ Fixed: Modal input validation untuk semua form
✅ Fixed: LocalStorage fallback untuk browser tanpa IndexedDB
✅ Fixed: Trigger SQL untuk auto-calculate remaining amount
✅ Fixed: Password sync di login form
✅ Fixed: Toast notification timing dan z-index
✅ Fixed: Report preview rendering dengan data kosong
✅ Fixed: Mobile responsive layout untuk tablet
✅ Fixed: Error handling di FileReader import
✅ Fixed: Chart destroy sebelum render ulang
✅ Added: Input required validation
✅ Added: Better error messages
✅ Added: Smooth animations dan transitions

## 🔒 Security Notes

- **Local-first**: Semua data disimpan di browser user, tidak ada server
- **No Cloud**: Zero dependency ke cloud services
- **Offline Ready**: Aplikasi berfungsi penuh tanpa internet
- **Data Privacy**: Data tidak pernah keluar dari device user

## 📱 Browser Support

✅ Chrome 90+
✅ Firefox 88+
✅ Safari 14+
✅ Edge 90+

**Mobile-friendly** - Responsive design untuk tablet & smartphone

## 📝 Contoh Penggunaan

### 1. Tambah Pelanggan
```
1. Login sebagai Staf Penjualan
2. Tab "Pelanggan" → Klik "+ Tambah"
3. Isi nama, email, telepon, alamat
4. Klik "Simpan"
```

### 2. Input Piutang
```
1. Tab "Piutang" → Klik "+ Tambah"
2. Pilih pelanggan dari dropdown
3. Isi nomor faktur, tanggal, nominal
4. Klik "Simpan"
```

### 3. Catat Pembayaran
```
1. Login sebagai Staf Keuangan
2. Tab "Bayar" → Klik "+ Catat"
3. Pilih piutang yang akan dibayar
4. Isi nominal & metode pembayaran
5. Klik "Simpan"
```

### 4. Lihat Laporan
```
1. Tab "Laporan" → Klik "Preview"
2. Lihat preview tabel pembayaran
3. Klik "Generate & Cetak PDF"
4. Browser dialog cetak terbuka
5. Pilih "Save as PDF"
```

## 🎯 Roadmap

- [ ] Multi-language support (EN, ID)
- [ ] Dark mode
- [ ] Export ke Excel
- [ ] Reminder notifikasi piutang jatuh tempo
- [ ] Advanced filtering & search
- [ ] Custom report templates
- [ ] Sync cloud backup (optional)

## 📞 Support

Untuk pertanyaan atau laporan bug, buat issue di GitHub:
https://github.com/angganurfirmansah6-source/piutangku/issues

## 📄 License

MIT License - Bebas digunakan untuk project personal maupun komersial

---

**Made with ❤️ by Copilot**
