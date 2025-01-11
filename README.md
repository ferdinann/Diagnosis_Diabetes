# Laporan Proyek Machine Learning - Ferdinanta Ginting

## # Diagnosis Diabetes

Pada bagian ini, kamu perlu menuliskan latar belakang yang relevan dengan proyek yang diangkat.
Proyek Diagnosis Diabetes dibuat dengan tujuan mengidentifikasi individu yang beresiko terkena diabetes, dengan membuat proyek ini diharapkan dapat membantu peningkatan diagnosis dini dan strategi pengobatan yang dipersonalisasi untuk diabetes.

Selamat datang di Diabetes Prediction Dataset, sumber daya yang berharga bagi para peneliti, ilmuwan data, dan profesional medis yang tertarik pada bidang penilaian dan prediksi risiko diabetes. Dataset ini berisi berbagai atribut terkait kesehatan, yang dikumpulkan dengan cermat untuk membantu pengembangan model prediktif guna mengidentifikasi individu yang berisiko terkena diabetes. Dengan berbagi dataset ini, kami bertujuan untuk mendorong kolaborasi dan inovasi dalam komunitas ilmu data, yang mengarah pada peningkatan diagnosis dini dan strategi pengobatan yang dipersonalisasi untuk diabetes.

Kolom:

Id: Pengidentifikasi unik untuk setiap entri data.
Kehamilan: Jumlah kali hamil.
Glukosa: Konsentrasi glukosa plasma selama 2 jam dalam tes toleransi glukosa oral.
Tekanan Darah: Tekanan darah diastolik (mm Hg).
Ketebalan Kulit: Ketebalan lipatan kulit trisep (mm).
Insulin: Insulin serum 2 jam (mu U/ml).
BMI: Indeks massa tubuh (berat dalam kg / tinggi dalam m^2).
DiabetesPedigreeFunction: Fungsi silsilah diabetes, skor genetik diabetes.
Usia: Usia dalam tahun.
Hasil: Klasifikasi biner yang menunjukkan keberadaan (1) atau ketiadaan (0) diabetes.
Manfaatkan kumpulan data ini untuk mengeksplorasi hubungan antara berbagai indikator kesehatan dan kemungkinan diabetes. Anda dapat menerapkan teknik pembelajaran mesin untuk mengembangkan model prediktif, strategi pemilihan fitur, dan visualisasi data untuk mengungkap wawasan yang dapat berkontribusi pada penilaian risiko yang lebih akurat. Saat Anda memulai perjalanan dengan kumpulan data ini, ingatlah bahwa penemuan Anda dapat berdampak besar pada pencegahan dan pengelolaan diabetes.
Pastikan Anda mematuhi pedoman etika dan menghormati privasi individu yang terwakili dalam kumpulan data ini. Kutipan yang tepat dan pengakuan sumber kumpulan data ini dihargai untuk mendorong kolaborasi dan berbagi pengetahuan.
Mulailah eksplorasi Anda terhadap Kumpulan Data Prediksi Diabetes hari ini dan berkontribusilah pada upaya berkelanjutan untuk memerangi diabetes melalui wawasan dan inovasi berbasis data.

**Rubrik/Kriteria Tambahan (Opsional)**:
- Jelaskan mengapa dan bagaimana masalah tersebut harus diselesaikan
- Masalah ini harus diselesaikan supaya individu bisa melakukan pengobatan atau penanganan lebih lanjut setelah mengetahui diagnosis diabetes nya. Masalah ini dapat diselesaikan dengan membuat model prediktif yang akan memberikan persentasi individu mengalami diabetes 
- Menyertakan hasil riset terkait atau referensi. Referensi yang diberikan harus berasal dari sumber yang kredibel dan author yang jelas.
  
  Format Referensi: [Judul Referensi](https://scholar.google.com/) 

## Business Understanding

Pada bagian ini, kamu perlu menjelaskan proses klarifikasi masalah.

Bagian laporan ini mencakup:

### Problem Statements

Menjelaskan pernyataan masalah latar belakang:
- Pernyataan Masalah 1
- Pernyataan Masalah 2
- Pernyataan Masalah n

### Goals

Menjelaskan tujuan dari pernyataan masalah:
- Jawaban pernyataan masalah 1
- Jawaban pernyataan masalah 2
- Jawaban pernyataan masalah n

Semua poin di atas harus diuraikan dengan jelas. Anda bebas menuliskan berapa pernyataan masalah dan juga goals yang diinginkan.

**Rubrik/Kriteria Tambahan (Opsional)**:
- Menambahkan bagian “Solution Statement” yang menguraikan cara untuk meraih goals. Bagian ini dibuat dengan ketentuan sebagai berikut: 

    ### Solution statements
    - Mengajukan 2 atau lebih solution statement. Misalnya, menggunakan dua atau lebih algoritma untuk mencapai solusi yang diinginkan atau melakukan improvement pada baseline model dengan hyperparameter tuning.
    - Solusi yang diberikan harus dapat terukur dengan metrik evaluasi.

## Data Understanding
Paragraf awal bagian ini menjelaskan informasi mengenai data yang Anda gunakan dalam proyek. Sertakan juga sumber atau tautan untuk mengunduh dataset. Contoh: [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/Restaurant+%26+consumer+data).

Selanjutnya uraikanlah seluruh variabel atau fitur pada data. Sebagai contoh:  

### Variabel-variabel pada Restaurant UCI dataset adalah sebagai berikut:
- accepts : merupakan jenis pembayaran yang diterima pada restoran tertentu.
- cuisine : merupakan jenis masakan yang disajikan pada restoran.
- dst

**Rubrik/Kriteria Tambahan (Opsional)**:
- Melakukan beberapa tahapan yang diperlukan untuk memahami data, contohnya teknik visualisasi data atau exploratory data analysis.

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

_Catatan:_
- _Anda dapat menambahkan gambar, kode, atau tabel ke dalam laporan jika diperlukan. Temukan caranya pada contoh dokumen markdown di situs editor [Dillinger](https://dillinger.io/), [Github Guides: Mastering markdown](https://guides.github.com/features/mastering-markdown/), atau sumber lain di internet. Semangat!_
- Jika terdapat penjelasan yang harus menyertakan code snippet, tuliskan dengan sewajarnya. Tidak perlu menuliskan keseluruhan kode project, cukup bagian yang ingin dijelaskan saja.
