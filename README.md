# Segmentasi dan Klasifikasi Nasabah Bank

## Ikhtisar Proyek
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

## Alat dan Teknologi
- **Bahasa Pemrograman**: Python
- **Library**: `pandas`, `numpy`, `scikit-learn`, `matplotlib`, `seaborn`
- **Algoritma**: K-Means Clustering, Decision Tree, Random Forest
