# Laporan Proyek Machine Learning - Ferdinanta Ginting

## # Diagnosis Diabetes

Proyek Diagnosis Diabetes dibuat dengan tujuan mengidentifikasi individu yang beresiko terkena diabetes, dengan membuat proyek ini diharapkan dapat membantu peningkatan diagnosis dini dan strategi pengobatan yang dipersonalisasi untuk diabetes.

Selamat datang di Diabetes Prediction Dataset, sumber daya yang berharga bagi para peneliti, ilmuwan data, dan profesional medis yang tertarik pada bidang penilaian dan prediksi risiko diabetes. Dataset ini berisi berbagai atribut terkait kesehatan, yang dikumpulkan dengan cermat untuk membantu pengembangan model prediktif guna mengidentifikasi individu yang berisiko terkena diabetes. Dengan berbagi dataset ini, kami bertujuan untuk mendorong kolaborasi dan inovasi dalam komunitas ilmu data, yang mengarah pada peningkatan diagnosis dini dan strategi pengobatan yang dipersonalisasi untuk diabetes.


Manfaatkan kumpulan data ini untuk mengeksplorasi hubungan antara berbagai indikator kesehatan dan kemungkinan diabetes. Anda dapat menerapkan teknik pembelajaran mesin untuk mengembangkan model prediktif, strategi pemilihan fitur, dan visualisasi data untuk mengungkap wawasan yang dapat berkontribusi pada penilaian risiko yang lebih akurat. Saat Anda memulai perjalanan dengan kumpulan data ini, ingatlah bahwa penemuan Anda dapat berdampak besar pada pencegahan dan pengelolaan diabetes.
Pastikan Anda mematuhi pedoman etika dan menghormati privasi individu yang terwakili dalam kumpulan data ini. Kutipan yang tepat dan pengakuan sumber kumpulan data ini dihargai untuk mendorong kolaborasi dan berbagi pengetahuan.
Mulailah eksplorasi Anda terhadap Kumpulan Data Prediksi Diabetes hari ini dan berkontribusilah pada upaya berkelanjutan untuk memerangi diabetes melalui wawasan dan inovasi berbasis data.

**Rubrik/Kriteria Tambahan (Opsional)**:
- Masalah ini harus diselesaikan supaya individu bisa melakukan pengobatan atau penanganan lebih lanjut setelah mengetahui diagnosis diabetes nya. Masalah ini dapat diselesaikan dengan membuat model prediktif yang akan memberikan persentasi individu mengalami diabetes 
- Menyertakan hasil riset terkait atau referensi. Referensi yang diberikan harus berasal dari sumber yang kredibel dan author yang jelas.
  
  Format Referensi: [Judul Referensi](https://scholar.google.com/) 

## Business Understanding

### Problem Statements

- Fitur mana yang paling signifikan dalam memprediksi risiko diabetes? 
- Apakah ada perbedaan pola risiko diabetes antara kelompok usia atau jenis kelamin yang berbeda?
- Bagaimana cara meningkatkan interpretasi model prediksi untuk membantu dokter dalam pengambilan keputusan klinis? 

### Goals

- Mengetahui fitur mana yang paling berkorelasi dengan hasil klasifikasi
- Menampilkan grafik untuk melihat pola resiko diabetes antara kelompok usia atau jenis kelamin
- Membuat model machine learning yang dapat memprediksi individu mengalami penyakit diabetes seakurat mungkin dengan fitur-fitur yang ada.

    ### Solution statements
    - Menggunakan 4 algoritma yang berbeda untuk mendapatkan model machine learning terbaik.
    - Melakukan improvement pada baseline model dengan hyperparameter tuning.

## Data Understanding
Paragraf awal bagian ini menjelaskan informasi mengenai data yang Anda gunakan dalam proyek. Sertakan juga sumber atau tautan untuk mengunduh dataset. Contoh: [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/Restaurant+%26+consumer+data).

Data yang digunakan berasal dari kaggle dengan jumlah data 2768 baris dan 10 kolom. Semua data adalah numerik dengan 8 feature adalah int dan 2 lainnya adalah float, target feature adalah feature terakhir yaitu Outcome dengan range data 0-1. 

### Variabel-variabel pada Diabetes dataset adalah sebagai berikut:

- Id : Pengidentifikasi unik untuk setiap entri data.
- Kehamilan : Jumlah kali hamil.
- Glukosa : Konsentrasi glukosa plasma selama 2 jam dalam tes toleransi glukosa oral.
- Tekanan Darah : Tekanan darah diastolik (mm Hg).
- Ketebalan Kulit : Ketebalan lipatan kulit trisep (mm).
- Insulin : Insulin serum 2 jam (mu U/ml).
- BMI : Indeks massa tubuh (berat dalam kg / tinggi dalam m^2).
- DiabetesPedigreeFunction : Fungsi silsilah diabetes, skor genetik diabetes.
- Usia : Usia dalam tahun.
- Hasil : Klasifikasi biner yang menunjukkan keberadaan (1) atau ketiadaan (0) diabetes.

**Rubrik/Kriteria Tambahan (Opsional)**:
- Tahapan yang diperlukan untuk memmahami data antara lain menampilkan deskripsi data, memvisualisasikan korelasi antar feature, memeriksa missing value. 

## Data Preparation
Pada bagian ini Anda menerapkan dan menyebutkan teknik data preparation yang dilakukan. Teknik yang digunakan pada notebook dan laporan harus berurutan.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menjelaskan proses data preparation yang dilakukan
- Menjelaskan alasan mengapa diperlukan tahapan data preparation tersebut.

## Modeling
Tahapan ini membahas mengenai model machine learning yang digunakan untuk menyelesaikan permasalahan. Anda perlu menjelaskan tahapan dan parameter yang digunakan pada proses pemodelan.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menjelaskan kelebihan dan kekurangan dari setiap algoritma yang digunakan.
- Jika menggunakan satu algoritma pada solution statement, lakukan proses improvement terhadap model dengan hyperparameter tuning. **Jelaskan proses improvement yang dilakukan**.
- Jika menggunakan dua atau lebih algoritma pada solution statement, maka pilih model terbaik sebagai solusi. **Jelaskan mengapa memilih model tersebut sebagai model terbaik**.

## Evaluation
Pada bagian ini anda perlu menyebutkan metrik evaluasi yang digunakan. Lalu anda perlu menjelaskan hasil proyek berdasarkan metrik evaluasi yang digunakan.

Sebagai contoh, Anda memiih kasus klasifikasi dan menggunakan metrik **akurasi, precision, recall, dan F1 score**. Jelaskan mengenai beberapa hal berikut:
- Penjelasan mengenai metrik yang digunakan
- Menjelaskan hasil proyek berdasarkan metrik evaluasi

Ingatlah, metrik evaluasi yang digunakan harus sesuai dengan konteks data, problem statement, dan solusi yang diinginkan.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menjelaskan formula metrik dan bagaimana metrik tersebut bekerja.

**---Ini adalah bagian akhir laporan---**
