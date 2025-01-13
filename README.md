# Laporan Proyek Machine Learning - Ferdinanta Ginting

## # Diagnosis Diabetes

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

Data yang digunakan berasal dari kaggle dengan jumlah data 2768 baris dan 10 kolom. Semua data adalah numerik dengan 8 feature adalah int dan 2 lainnya adalah float, target feature adalah feature terakhir yaitu Outcome dengan range data 0-1. 

### Variabel-variabel pada Diabetes dataset adalah sebagai berikut:

- Id : Pengidentifikasi unik untuk setiap entri data.
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
1. Mengambil sample dataset 
2. Pembagian dataset dengan fungsi train_test_split dari library sklearn.
3. Standarisasi.

- Pengambilan sample dataset dimulai dengan index 1651 sampai habis dengan jumlah keseluruhan sample yang diambil adalah 18 baris data
- Pada pembagian dataset data dibagi menjadi data training dan data testing dengan data testing sebesar 10% dan sisanya adalah data training jumlah masing masing kelompok data adalah data training 1485 dan data testing sebesar 166.
- Standarisasi dilakukan agar data memiliki rentang nilai yang normal yaitu dengan rata-rata mendekati 0 dan standart deviasi atau std mendekati 1.
- Tahapan data preparation diperlukan agar data yang digunakan untuk membangun model sudah normal dan optimal sehingga model yang dibangun menjadi lebih akurat dan memiliki performa yang baik.

## Modeling
Model yang dibangun untuk menyelesaikan permasalahan ini dibuat dengan membangun 7 algoritma yang berbeda diantaranya adalah :
1. KNN dengan parameter n_neighbors=7
   tahapan :
   - import library
   - inisialisasi variabel yang menampung algoritma
   - latih model
   - simpan model untuk melihat performa nya setelah semua model selesai dibangun
2. Random Forest dengan parameter n_estimators=40, max_depth=16, random_state=32, n_jobs=-1
   tahapan :
   - import library
   - inisialisasi variabel yang menampung algoritma
   - latih model
   - simpan model untuk melihat performa nya setelah semua model selesai dibangun
3. Gradient Boosting dengan parameter random_state=42,n_estimators=100,learning_rate=0.2
   tahapan :
   - import library
   - inisialisasi variabel yang menampung algoritma
   - latih model
   - simpan model untuk melihat performa nya setelah semua model selesai dibangun
4. SVM dengan parameter random_state=42
   tahapan :
   - import library
   - inisialisasi variabel yang menampung algoritma
   - latih model
   - simpan model untuk melihat performa nya setelah semua model selesai dibangun
5. XGBoost dengan parameter random_state=42
   tahapan :
   - import library
   - inisialisasi variabel yang menampung algoritma
   - latih model
   - simpan model untuk melihat performa nya setelah semua model selesai dibangun
6. Decision Tree dengan parameter random_state=20
   tahapan :
   - import library
   - inisialisasi variabel yang menampung algoritma
   - latih model
   - simpan model untuk melihat performa nya setelah semua model selesai dibangun
7. Neural Network dengan Tensorflow
   tahapan :
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
- Berdasarkan ke-4 metrik yang digunakan setelah di evaluasi maka semua model memiliki performa baik tetapi ada tiga model yang memiliki akurasi dibawah 90% yaitu KNN, SVM, dan Neural Network. 
