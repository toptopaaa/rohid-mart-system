# Sistem Kasir ROHID MART

Sistem Point of Sale (POS) gratis dan sederhana yang dirancang untuk minimart berbasis pesantren untuk melacak inventaris, stok, dan keuntungan/kerugian harian.

## Fitur

- 📦 **Kelola Produk** - Tambah, edit, hapus produk dengan kategori dan harga
- 🛒 **Catat Pembelian** - Lacak stok masuk dan informasi pemasok
- 💰 **Proses Penjualan** - Catat penjualan dengan pengurangan stok otomatis
- 📊 **Beranda** - Ringkasan real-time operasional harian
- 📆 **Laporan** - Riwayat transaksi detail dengan fungsi ekspor
- 📌 **Saran Stok Ulang** - Rekomendasi cerdas berdasarkan pola penjualan

## Teknologi

- **Frontend**: HTML + TailwindCSS + Vanilla JavaScript
- **Backend**: Supabase (PostgreSQL)
- **Build Tool**: Vite  
- **Deployment**: Siap untuk Vercel/Netlify

## Petunjuk Instalasi

### 1. Clone dan Install

```bash
npm install
```

### 2. Konfigurasi Supabase

1. Buat proyek baru di [supabase.com](https://supabase.com)
2. Salin URL proyek dan anon key Anda
3. Buat file `.env` dari `.env.example`:

```bash
cp .env.example .env
```

4. Perbarui `.env` dengan kredensial Supabase Anda:

```env
VITE_SUPABASE_URL=your_supabase_project_url
VITE_SUPABASE_ANON_KEY=your_supabase_anon_key
```

### 3. Setup Database

1. Buka dashboard proyek Supabase Anda
2. Navigasi ke SQL Editor
3. Salin dan tempel isi dari `supabase/migrations/20250720045937_shy_wood.sql`
4. Jalankan migrasi untuk membuat tabel dan data contoh

### 4. Jalankan Development Server

```bash
npm run dev
```

Kunjungi `http://localhost:5173` untuk melihat sistem kasir Anda!

## Panduan Penggunaan

### Kelola Produk
- Tambah produk baru dengan harga beli/jual
- Atur kategori untuk organisasi yang lebih baik
- Pantau level stok dengan peringatan otomatis

### Catat Pembelian
- Pilih produk dan masukkan jumlah
- Perbarui harga pembelian jika diperlukan
- Lacak pemasok untuk manajemen inventaris yang lebih baik

### Proses Penjualan
- Pemilihan produk cepat dengan validasi stok
- Perhitungan keuntungan otomatis
- Update stok real-time

### Ringkasan Beranda
- Ringkasan penjualan, pembelian, dan keuntungan harian
- Analisis produk terlaris
- Peringatan stok menipis dan rekomendasi

### Laporan & Analitik
- Filter transaksi berdasarkan rentang tanggal
- Ekspor data sebagai CSV untuk analisis eksternal
- Ringkasan keuntungan/kerugian bulanan

### Manajemen Stok Ulang
- Saran stok ulang bertenaga AI
- Berdasarkan rata-rata penjualan 3 hari
- Buat daftar belanja secara otomatis

## Deployment

### Vercel
```bash
npm run build
npx vercel --prod
```

### Netlify
```bash
npm run build
npx netlify deploy --prod --dir=dist
```

## Skema Database

### Tabel Products
- `id`: Identifier unik
- `name`: Nama produk
- `category`: Kategori produk
- `buying_price`: Harga beli (dalam rupiah)
- `selling_price`: Harga jual (dalam rupiah)
- `stock`: Jumlah stok saat ini

### Tabel Purchases
- `id`: Identifier unik
- `product_id`: Referensi ke produk
- `quantity`: Jumlah yang dibeli
- `unit_price`: Harga per unit
- `supplier`: Nama pemasok
- `date`: Tanggal pembelian

### Tabel Sales
- `id`: Identifier unik
- `product_id`: Referensi ke produk
- `quantity`: Jumlah yang dijual
- `date`: Tanggal penjualan
- `remarks`: Catatan opsional

## Kontribusi

1. Fork repository
2. Buat feature branch
3. Buat perubahan Anda
4. Test secara menyeluruh
5. Submit pull request

## Support

Untuk masalah dan pertanyaan:
1. Periksa dokumentasi
2. Cari issue yang sudah ada
3. Buat issue baru dengan informasi detail

## License

Proyek ini adalah open source dan tersedia di bawah MIT License.

---

Dibuat dengan ❤️ untuk komunitas pesantren oleh komunitas open source.