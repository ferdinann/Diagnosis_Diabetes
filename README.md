# Laporan Proyek Machine Learning - Ferdinanta Ginting

##  Diagnosis Diabetes

Diabetes melitus merupakan penyakit kronis yang ditandai dengan tingginya kadar gula darah dalam tubuh. Penyakit ini telah menjadi masalah kesehatan global yang serius, dengan jumlah penderita terus meningkat setiap tahunnya. Jika tidak dikelola dengan baik, diabetes dapat menyebabkan berbagai komplikasi serius, seperti penyakit jantung, stroke, kerusakan ginjal, kebutaan, dan amputasi.

Diagnosis dini diabetes sangat penting untuk mencegah terjadinya komplikasi yang parah. Namun, seringkali diabetes terdiagnosis pada tahap lanjut ketika komplikasi sudah mulai muncul. Hal ini disebabkan oleh beberapa faktor, antara lain:

- Gejala awal yang tidak spesifik: Diabetes seringkali tidak menunjukkan gejala yang jelas pada tahap awal, sehingga banyak penderita tidak menyadari kondisi mereka.
- Kurangnya kesadaran: Masyarakat masih kurang memahami tentang diabetes dan faktor risiko yang terkait.
- Keterbatasan akses: Tidak semua orang memiliki akses yang mudah ke fasilitas kesehatan untuk melakukan pemeriksaan gula darah secara rutin.

Proyek Diagnosis Diabetes dibuat dengan tujuan mengidentifikasi individu yang beresiko terkena diabetes, dengan membuat proyek ini diharapkan dapat membantu peningkatan diagnosis dini dan strategi pengobatan yang dipersonalisasi untuk diabetes.

- Masalah ini harus diselesaikan supaya individu bisa melakukan pengobatan atau penanganan lebih lanjut setelah mengetahui diagnosis diabetes nya. Masalah ini dapat diselesaikan dengan membuat model prediktif yang akan memberikan persentasi individu mengalami diabetes 
- [Prediksi Penyakit Diabetes Melitus Menggunakan Metode Support Vector Machine dan Naive Bayes](https://www.researchgate.net/publication/356609443_Prediksi_Penyakit_Diabetes_Melitus_Menggunakan_Metode_Support_Vector_Machine_dan_Naive_Bayes/) 

## Business Understanding

### Problem Statements

- Fitur mana yang paling signifikan dalam memprediksi risiko diabetes? 
- Apakah ada pengaruh pola risiko diabetes kelompok usia atau BMI?
- Bagaimana cara meningkatkan interpretasi model prediksi untuk membantu dokter dalam pengambilan keputusan klinis? 

### Goals

- Mengetahui fitur mana yang paling berkorelasi dengan hasil klasifikasi
- Menampilkan grafik untuk melihat pola resiko diabetes antara kelompok usia atau BMI
- Membuat model machine learning yang dapat memprediksi individu mengalami penyakit diabetes seakurat mungkin dengan fitur-fitur yang ada.

    ### Solution statements
    - Menggunakan 7 algoritma yang berbeda untuk mendapatkan model machine learning terbaik.
    - Melakukan improvement pada baseline model dengan mengcustom parameter secara manual.

## Data Understanding
[Healthcare Diabetes Dataset](https://www.kaggle.com/datasets/nanditapore/healthcare-diabetes/).

Data yang digunakan berasal dari kaggle dengan jumlah data 2768 baris dan 9 kolom. Semua data adalah numerik dengan 7 feature adalah int dan 2 lainnya adalah float, target feature adalah feature terakhir yaitu Outcome dengan range data 0-1. Kondisi data sudah cukup baik tidak ada duplicate dan missing value tetapi ada outlier yang di temui saat dilakukan pengeceken dengan boxplot.

### Variabel-variabel pada Diabetes dataset adalah sebagai berikut:

- Pregnancies : Jumlah kali hamil.
- Glucose : Konsentrasi glukosa plasma selama 2 jam dalam tes toleransi glukosa oral.
- BloodPressure : Tekanan darah diastolik (mm Hg).
- SkinThickness : Ketebalan lipatan kulit trisep (mm).
- Insulin : Insulin serum 2 jam (mu U/ml).
- BMI : Indeks massa tubuh (berat dalam kg / tinggi dalam m^2).
- DiabetesPedigreeFunction : Fungsi silsilah diabetes, skor genetik diabetes.
- Age : Usia dalam tahun.
- Outcome : Klasifikasi biner yang menunjukkan keberadaan (1) atau ketiadaan (0) diabetes.

- Tahapan yang diperlukan untuk memmahami data antara lain menampilkan deskripsi data, memvisualisasikan korelasi antar feature, memeriksa missing value. 

## Data Preparation
Pada bagian ini saya menerapkan tiga tahapan yaitu :
1. Pembagian dataset dengan fungsi train_test_split dari library sklearn.
2. Standarisasi.
3. Handling outlier

- Pada pembagian dataset data dibagi menjadi data training dan data testing dengan data testing sebesar 20% dan sisanya adalah data training jumlah masing masing kelompok data adalah data training 1335 dan data testing sebesar 334.
- Standarisasi dilakukan agar data memiliki rentang nilai yang normal yaitu dengan rata-rata mendekati 0 dan standart deviasi atau std mendekati 1.
- Handling outlier dilakukan dengan membuat variabel IQR yang berisi operasi matematika untuk menentukan batas atas dan batas bawah dan mengapus data yang ada di luar dari batas bawah dan atas.
- Tahapan data preparation diperlukan agar data yang digunakan untuk membangun model sudah normal dan optimal sehingga model yang dibangun menjadi lebih akurat dan memiliki performa yang baik.

## Modeling
Model yang dibangun untuk menyelesaikan permasalahan ini dibuat dengan membangun 7 algoritma yang berbeda diantaranya adalah :
1. KNN
-  Prinsip Kerja: Mengklasifikasikan data baru berdasarkan label dari K data terdekatnya.
- Cara Kerja:
  Hitung jarak antara data baru dengan semua data latih.
  Pilih K data latih terdekat.
  Tentukan label data baru berdasarkan mayoritas label dari K data terdekat.
- Parameter: n_neighbors=7 menentukan jumlah tetangga terdekat yang akan dipertimbangkan.
- tahapan :
   - import library
   - inisialisasi variabel yang menampung algoritma
   - latih model
   - simpan model untuk melihat performa nya setelah semua model selesai dibangun
2. Random Forest dengan parameter n_estimators=40, max_depth=16, random_state=32, n_jobs=-1
- Prinsip Kerja: Ensemble dari banyak pohon keputusan.
- Cara Kerja:
  Buat banyak pohon keputusan secara acak, dengan memilih fitur dan data secara acak pada setiap split.
  Setiap pohon memberikan prediksi, dan prediksi akhir ditentukan berdasarkan voting mayoritas dari semua pohon.
- Parameter:
  n_estimators: Jumlah pohon dalam hutan.
  max_depth: Kedalaman maksimum pohon.
  random_state: Untuk reproduksibilitas.
  n_jobs: Jumlah core prosesor yang digunakan.
- tahapan :
   - import library
   - inisialisasi variabel yang menampung algoritma
   - latih model
   - simpan model untuk melihat performa nya setelah semua model selesai dibangun
3. Gradient Boosting dengan parameter random_state=42,n_estimators=100,learning_rate=0.2
- Prinsip Kerja: Membangun model secara bertahap, dengan setiap model baru mencoba memperbaiki kesalahan model sebelumnya.
- Cara Kerja:
  Mulai dengan model dasar (biasanya pohon keputusan).
  Setiap model baru dilatih untuk meminimalkan residual (selisih antara prediksi dan nilai sebenarnya) dari model sebelumnya.
  Model akhir adalah penjumlahan dari semua model yang dihasilkan.
- Parameter:
  n_estimators: Jumlah pohon.
  learning_rate: Tingkat pengaruh setiap pohon baru terhadap model akhir.
- tahapan :
   - import library
   - inisialisasi variabel yang menampung algoritma
   - latih model
   - simpan model untuk melihat performa nya setelah semua model selesai dibangun
4. SVM dengan parameter random_state=42
- Prinsip Kerja: Mencari hiperplane yang memisahkan data ke dalam kelas yang berbeda dengan margin sebesar-besarnya.
- Cara Kerja:
  Mentransformasi data ke ruang fitur yang lebih tinggi jika diperlukan.
  Mencari hiperplane yang memaksimalkan margin antara kelas positif dan negatif.
  Mengklasifikasikan data baru berdasarkan sisi hiperplane tempat data tersebut berada.
- Parameter:
  kernel: Fungsi kernel yang digunakan untuk transformasi data.
- tahapan :
   - import library
   - inisialisasi variabel yang menampung algoritma
   - latih model
   - simpan model untuk melihat performa nya setelah semua model selesai dibangun
5. XGBoost dengan parameter random_state=42
- Prinsip Kerja: Mirip dengan Gradient Boosting, tetapi lebih efisien dan memiliki lebih banyak parameter tuning.
- Cara Kerja:
  Menggunakan algoritma gradient boosting yang dioptimasi.
  Menawarkan fleksibilitas dalam pemilihan pohon keputusan, fungsi objektif, dan regularisasi.
- tahapan :
   - import library
   - inisialisasi variabel yang menampung algoritma
   - latih model
   - simpan model untuk melihat performa nya setelah semua model selesai dibangun
6. Decision Tree dengan parameter random_state=20
- Prinsip Kerja: Membangun pohon keputusan untuk membuat prediksi.
- Cara Kerja:
  Membagi data secara rekursif berdasarkan nilai fitur terbaik pada setiap node.
  Proses berulang hingga mencapai kondisi berhenti (misalnya, kedalaman maksimum atau kemurnian node).
- Parameter:
  criterion: Kriteria untuk memilih fitur terbaik (misalnya, Gini impurity, entropy).
  max_depth: Kedalaman maksimum pohon.
- tahapan :
   - import library
   - inisialisasi variabel yang menampung algoritma
   - latih model
   - simpan model untuk melihat performa nya setelah semua model selesai dibangun
7. Neural Network dengan Tensorflow
- Prinsip Kerja: Meniru cara kerja otak manusia dengan menggunakan banyak neuron yang saling terhubung.
- Cara Kerja:
  Data masuk melalui lapisan input, diproses oleh beberapa lapisan tersembunyi, dan menghasilkan output pada lapisan output.
  Bobot dan bias pada setiap neuron akan diperbarui selama proses pelatihan untuk meminimalkan kesalahan prediksi.
- Parameter:
  Jumlah lapisan, jumlah neuron per lapisan, fungsi aktivasi, optimizer, loss function.
- tahapan :
   - import library
   - membuat input layers dengan neuron 64 dan activation relu
   - menambahkan dropout dengan nilai 0.5
   - menambahkan hidden layers dengan neuron 32 dan activation relu
   - menambahkan batch normalization
   - menambahkan hidden layers dengan jumlah neuron 16 dan activation relu
   - menambahkan output layers dengan jumlah neuron 2 sesuai jumlah klasifikasi dan activation sigmoid
   - mengcompile model dengan optimasi adam, loss fuctions binary crossentropy dan metriks accuracy
   - menampilkan summary dari model
   - melatih model dengan parameter X_train, y_train, epochs=30, batch_size=32, validation_split=0.1
   - mengevaluasi model untuk melihat akurasi dan loss fuctions nya
     
## Evaluation
Metrik evaluasi yang digunakan adalah antara lain :
1. accuracy
2. precision
3. recall
4. f1

- Penjelasan mengenai metrik yang digunakan
  - akurasi adalah metrik yang mengukur seberapa sering model memprediksi dengan benar
  - precision adalah metrik yang mengukur seberapa akurat model dalam memprediksi kelas positif
  - recall adalah metrik yang Mengukur seberapa baik model dalam mengidentifikasi semua kasus positif yang sebenarnya
  - f1 adalah metrik gabungan antara precision dan recall
    
- Berdasarkan model yang telah dibuat dan di evaluasi maka problem statement yang telah dibuat sebelumnya sudah terjawab dan juga telah mencapai goals yang diharapkan
  - fitur yang paling berkorelasi dengan resiko terkena diabetes adalah glucose, age dan bmi.
  - hubungan resiko terkena diabetes dengan BMI dan usia pasien dapat dilihat bahwa orang yang memiliki BMI diantara 30 - 40 memiliki resiko diabetes tertinggi dan usia dengan rentang 20 - 30 tahun juga memiliki resiko diabetes tertinggi.
  - Berdasarkan ke-4 metrik yang digunakan setelah di evaluasi maka semua model memiliki performa baik tetapi ada tiga model yang memiliki akurasi dibawah 90% yaitu KNN, SVM, dan Neural 
    Network.

- Solution statement yang direncanakan berdampak karena melalui ke-7 model yang dibangun dapat dilihat bahwa setiap model memiliki hasil loss fuctions dan akurasi yang beragam sehingga model yang dibangun bisa di evaluasi dan dibandingkan dengan lainnya sehingga mempermudah pemilihan model yang tepat untuk menyelesaikan permasalahan.
