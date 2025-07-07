# Segmentasi dan Klasifikasi Nasabah Bank

## Tujuan Proyek
Proyek ini bertujuan untuk melakukan segmentasi dan klasifikasi nasabah bank menggunakan algoritma machine learning. Segmentasi dilakukan dengan **K-Means Clustering** untuk mengelompokkan nasabah berdasarkan karakteristik mereka, diikuti dengan klasifikasi menggunakan **Decision Tree** dan **Random Forest** pada data yang telah dikelompokkan. Proyek ini memberikan wawasan tentang perilaku nasabah untuk mendukung strategi pemasaran dan pengambilan keputusan bank.

## Alur Kerja Proyek

### 1. Segmentasi Nasabah (K-Means Clustering)
Proses segmentasi bertujuan untuk mengelompokkan nasabah berdasarkan atribut mereka menggunakan algoritma K-Means. Tahapan yang dilakukan adalah:

- **Impor Library**: Memuat library Python seperti `pandas`, `numpy`, `scikit-learn`, dan `matplotlib` untuk pengolahan dan visualisasi data.
- **Memuat Dataset**: Mengimpor dataset nasabah bank yang berisi informasi nasabah.
- **Data Wrangling**: Menangani nilai yang hilang, duplikasi, dan inkonsistensi dalam dataset.
- **Preprocessing Data**: Melakukan penskalaan fitur dan pengkodean data untuk persiapan clustering.
- **Analisis Data**: Melakukan analisis data eksplorasi (EDA) untuk memahami distribusi dan hubungan antar data.
- **Melatih Model**: Menerapkan algoritma K-Means untuk mengelompokkan nasabah ke dalam cluster.
- **Evaluasi Model**: Menggunakan metrik seperti Silhouette Score dan Within-Cluster Sum of Squares (WCSS) untuk mengevaluasi kualitas cluster.
- **Analisis Karakteristik Cluster**: Menganalisis karakteristik setiap cluster untuk mengidentifikasi segmen nasabah yang unik.

### 2. Klasifikasi Nasabah (Decision Tree & Random Forest)
Setelah clustering, data yang telah dikelompokkan digunakan untuk membangun model klasifikasi guna memprediksi segmen nasabah. Tahapan yang dilakukan adalah:

- **Impor Library**: Memuat library yang diperlukan untuk tugas klasifikasi.
- **Memuat Dataset yang Telah Dicluster**: Menggunakan dataset dengan label cluster dari model K-Means.
- **Pemisahan Data**: Membagi data menjadi set pelatihan dan pengujian untuk evaluasi model.
- **Melatih Model**: Melatih dua model klasifikasi:
  - **Decision Tree**: Untuk mengklasifikasikan nasabah berdasarkan fitur mereka.
  - **Random Forest**: Untuk meningkatkan performa klasifikasi dengan pendekatan ensemble.
- **Evaluasi Model**: Mengevaluasi model menggunakan metrik seperti akurasi, presisi, recall, dan F1-score.

## Temuan Utama
- Model K-Means berhasil mengelompokkan nasabah ke dalam segmen-segmen yang berbeda berdasarkan perilaku dan demografi mereka.
- Model Decision Tree dan Random Forest mampu mengklasifikasikan nasabah ke dalam cluster dengan akurat, dengan Random Forest menunjukkan performa lebih baik karena sifat ensemble-nya.
- Analisis cluster menghasilkan wawasan yang dapat ditindaklanjuti, seperti mengidentifikasi nasabah bernilai tinggi atau yang berpotensi churn.

## Deskripsi Dataset
Dataset berisi fitur berikut:
- **Fitur Numerik**:
  - `TransactionAmount`: Jumlah transaksi (dalam satuan asli, misalnya rupiah).
  - `AccountBalance`: Saldo akun pelanggan.
  - `CustomerAge`: Usia pelanggan (dalam tahun).
- **Fitur Kategorikal**:
  - `TransactionType`: Tipe transaksi (Debit/Credit).
  - `Channel`: Kanal transaksi (Branch/ATM/Online).
  - `CustomerOccupation`: Pekerjaan pelanggan (Retired/Student/Doctor/Engineer).

## Analisis Karakteristik Cluster

### Cluster 1: Lansia Pensiunan dengan Preferensi Kanal Tradisional
- **Jumlah Data**: 500 data points (Debit: 392, Credit: 108).
- **Fitur Numerik**:
  - **Rata-rata TransactionAmount**: 50.45  
    Jumlah transaksi rata-rata rendah hingga sedang, menunjukkan transaksi kecil untuk kebutuhan sehari-hari.
  - **Rata-rata AccountBalance**: 50.91  
    Saldo akun moderat, mungkin mencerminkan tabungan pensiun.
  - **Rata-rata CustomerAge**: 64.40  
    Pelanggan adalah lansia (usia rata-rata ~64 tahun), kemungkinan besar pensiunan.
- **Fitur Kategorikal**:
  - **TransactionType**:
    - Debit: 78.4% (392/500)
    - Credit: 21.6% (108/500)  
      Transaksi debit mendominasi, menunjukkan pengeluaran lebih sering daripada penerimaan dana.
  - **Channel**:
    - Branch: 60.0% (300/500)
    - ATM: 40.0% (200/500)
    - Online: 0.0%  
      Pelanggan hanya menggunakan kanal tradisional (cabang dan ATM), mungkin karena keterbatasan teknologi.
  - **CustomerOccupation**:
    - Retired: 81.2% (406/500)
    - Doctor: 17.4% (87/500)
    - Student: 1.4% (7/500)  
      Mayoritas pensiunan, dengan beberapa dokter (mungkin lansia) dan sedikit anomali pelajar.
- **Wawasan**:
  - Cluster ini mewakili **pelanggan lansia yang sudah pensiun**, dengan transaksi kecil hingga sedang dan saldo moderat.
  - Preferensi kuat untuk kanal tradisional menunjukkan kenyamanan dengan interaksi langsung atau teknologi sederhana.
  - Kehadiran dokter mungkin menunjukkan profesional lansia yang masih aktif atau sudah pensiun.
- **Implikasi Bisnis**:
  - Tawarkan produk tabungan pensiun atau deposito dengan akses mudah di cabang.
  - Sediakan layanan bantuan langsung untuk lansia di cabang.
  - Tingkatkan kemudahan penggunaan ATM untuk transaksi sederhana.

### Cluster 2: Pelajar Muda dengan Fleksibilitas Kanal
- **Jumlah Data**: 657 data points (Debit: 518, Credit: 139).
- **Fitur Numerik**:
  - **Rata-rata TransactionAmount**: 50.47  
    Jumlah transaksi rata-rata serupa dengan cluster lain, menunjukkan transaksi kecil.
  - **Rata-rata AccountBalance**: 46.41  
    Saldo akun terendah, mencerminkan pendapatan terbatas pelajar (misalnya, uang saku).
  - **Rata-rata CustomerAge**: 23.09  
    Pelanggan muda (usia rata-rata ~23 tahun), kemungkinan mahasiswa.
- **Fitur Kategorikal**:
  - **TransactionType**:
    - Debit: 78.8% (518/657)
    - Credit: 21.2% (139/657)  
      Dominasi transaksi debit untuk kebutuhan sehari-hari.
  - **Channel**:
    - Branch: 34.6% (227/657)
    - ATM: 33.5% (220/657)
    - Online: 32.0% (210/657)  
      Penggunaan kanal merata, menunjukkan fleksibilitas antara tradisional dan digital.
  - **CustomerOccupation**:
    - Student: 100% (657/657)  
      Seluruhnya pelajar, konsisten dengan usia muda.
- **Wawasan**:
  - Cluster ini mewakili **pelajar muda** dengan saldo rendah dan transaksi kecil.
  - Fleksibilitas kanal (cabang, ATM, online) menunjukkan adaptasi terhadap berbagai metode transaksi.
  - Fokus pada transaksi debit mencerminkan pengeluaran untuk kebutuhan hidup.
- **Implikasi Bisnis**:
  - Kembangkan aplikasi perbankan mobile untuk meningkatkan adopsi kanal online.
  - Tawarkan produk tabungan pelajar dengan biaya rendah.
  - Pastikan ketersediaan ATM di sekitar kampus atau area pelajar.

### Cluster 3: Lansia Aktif Secara Online
- **Jumlah Data**: 422 data points (Debit: 298, Credit: 124).
- **Fitur Numerik**:
  - **Rata-rata TransactionAmount**: 50.05  
    Jumlah transaksi rata-rata rendah hingga sedang, serupa dengan cluster lain.
  - **Rata-rata AccountBalance**: 52.53  
    Saldo akun tinggi, menunjukkan stabilitas finansial.
  - **Rata-rata CustomerAge**: 62.32  
    Pelanggan lansia (usia rata-rata ~62 tahun), mungkin profesional atau pensiunan aktif.
- **Fitur Kategorikal**:
  - **TransactionType**:
    - Debit: 70.6% (298/422)
    - Credit: 29.4% (124/422)  
      Proporsi credit lebih tinggi dibandingkan cluster lain, mungkin penerimaan dana pensiun atau gaji.
  - **Channel**:
    - Online: 77.7% (328/422)
    - ATM: 22.3% (94/422)
    - Branch: 0.0%  
      Dominasi kanal online, menunjukkan kenyamanan dengan teknologi digital (unik untuk lansia).
  - **CustomerOccupation**:
    - Doctor: 46.4% (196/422)
    - Retired: 43.4% (183/422)
    - Engineer: 8.1% (34/422)
    - Student: 2.1% (9/422)  
      Campuran dokter dan pensiunan, dengan sedikit insinyur dan anomali pelajar.
- **Wawasan**:
  - Cluster ini mewakili **lansia yang aktif secara online**, dengan saldo akun tinggi dan transaksi moderat.
  - Preferensi kuat untuk kanal online menunjukkan kelompok lansia yang melek teknologi.
  - Kehadiran dokter dan pensiunan menunjukkan profesional lansia dengan stabilitas finansial.
- **Implikasi Bisnis**:
  - Promosikan layanan perbankan online dengan antarmuka ramah lansia.
  - Tawarkan produk investasi atau wealth management untuk pelanggan dengan saldo tinggi.
  - Edukasi keamanan transaksi online untuk meningkatkan kepercayaan.

### Cluster 4: Profesional Usia Produktif
- **Jumlah Data**: 935 data points (Debit: 743, Credit: 192).
- **Fitur Numerik**:
  - **Rata-rata TransactionAmount**: 49.98  
    Jumlah transaksi rata-rata rendah hingga sedang, konsisten dengan cluster lain.
  - **Rata-rata AccountBalance**: 52.51  
    Saldo akun tinggi, mencerminkan pendapatan stabil dari profesi profesional.
  - **Rata-rata CustomerAge**: 41.19  
    Pelanggan usia produktif (usia rata-rata ~41 tahun), kemungkinan pekerja aktif.
- **Fitur Kategorikal**:
  - **TransactionType**:
    - Debit: 79.5% (743/935)
    - Credit: 20.5% (192/935)  
      Dominasi transaksi debit untuk kebutuhan hidup atau investasi.
  - **Channel**:
    - Branch: 38.5% (360/935)
    - ATM: 33.5% (313/935)
    - Online: 28.0% (262/935)  
      Penggunaan kanal cukup seimbang, menunjukkan fleksibilitas.
  - **CustomerOccupation**:
    - Engineer: 62.8% (587/935)
    - Doctor: 37.0% (346/935)
    - Student: 0.2% (2/935)  
      Mayoritas insinyur dan dokter, dengan anomali pelajar.
- **Wawasan**:
  - Cluster ini mewakili **profesional usia produktif** (insinyur dan dokter) dengan saldo akun tinggi dan transaksi moderat.
  - Fleksibilitas kanal menunjukkan kenyamanan dengan teknologi dan interaksi langsung.
  - Saldo tinggi mencerminkan stabilitas finansial dari profesi bergaji tinggi.
- **Implikasi Bisnis**:
  - Tawarkan produk investasi atau kredit untuk profesional.
  - Kembangkan layanan perbankan yang fleksibel (online dan offline).
  - Sediakan program loyalitas untuk pelanggan dengan saldo tinggi.


## Alat dan Teknologi
- **Bahasa Pemrograman**: Python
- **Library**: `pandas`, `numpy`, `scikit-learn`, `matplotlib`, `seaborn`
- **Algoritma**: K-Means Clustering, Decision Tree, Random Forest
