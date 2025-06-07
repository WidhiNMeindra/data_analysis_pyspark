# data_analysis_pyspark
This repository about Data Engineering &amp; Analisis: Customer Maskapai Penerbangan

## 1. Data Preparation

- **Load** tiga tabel:  
  - `calendar.csv`
  - `customer_flight_activity.csv`
  - `customer_loyalty_history.csv`
- Pastikan tipe data setiap kolom sudah benar.

## 2. Data Cleaning & Verifikasi

- Cek missing values pada setiap tabel.
- Imputasi kolom numerik (misal `points_accumulated` diisi 0 jika missing).
- Imputasi kolom kategorikal (`gender`, `education`, dll.) dengan 'Unknown'.
- Konversi tipe data numerik/string bila perlu.
- Hapus duplikasi jika ada.
- Validasi data antar tabel (`loyalty_number` harus match di seluruh tabel).
- Hapus baris dengan missing pada kolom kunci yang tidak bisa diisi secara logis (misal, waktu pendaftaran/keterangan utama).

## 3. Transformasi Data

- **Join** tabel `customer_flight_activity` dengan `customer_loyalty_history` berdasarkan `loyalty_number` untuk memperkaya data.
- **Agregasi:**  
  - Hitung total penerbangan dan total poin per tahun per pelanggan.
  - Analisis rata-rata flight dan points berdasarkan demografi (`gender`, `education`, dsb).
- **Feature engineering:**  
  - Kolom baru: `avg_points_per_flight`, `net_points`, kategori salary (`salary_group`).
  - Grouping data berdasar segmentasi pelanggan (misal salary group, status loyalitas, dll).

## 4. Analisis & Visualisasi

- **Distribusi rata-rata penerbangan per pelanggan per tahun** (histogram/barplot).
- **Distribusi loyalty points berdasarkan status kartu loyalitas** (barplot).
- **Rata-rata penerbangan per tahun untuk top 20 pelanggan** (bar chart).
- **Distribusi poin berdasarkan kelompok demografi** (boxplot/barplot).
- Pastikan visual memiliki: judul, label sumbu, legend jika perlu, dan tata letak yang rapi.

## 5. Export Hasil

- Simpan DataFrame hasil cleaning dan agregasi ke dalam format `.csv` dan `.parquet` untuk kebutuhan analisis lanjutan.

## 6. Catatan

- Selalu dokumentasikan setiap langkah transformasi dan cleaning (misal, keputusan penghapusan/imputasi data).
- Lakukan sanity check pada data hasil transformasi agar tidak terjadi bias/kehilangan informasi penting.

