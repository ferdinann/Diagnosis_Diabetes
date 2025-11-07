# Laporan Proyek Machine Learning - Ferdinanta Ginting

##  Diagnosis Diabetes
Diabetes melitus merupakan penyakit kronis yang ditandai dengan tingginya kadar gula darah dalam tubuh. Penyakit ini telah menjadi masalah kesehatan global yang serius, dengan jumlah penderita terus meningkat setiap tahunnya [1]. Jika tidak dikelola dengan baik, diabetes dapat menyebabkan berbagai komplikasi serius, seperti penyakit jantung, stroke, kerusakan ginjal, kebutaan, dan amputasi [1], [2].

Diagnosis dini diabetes sangat penting untuk mencegah terjadinya komplikasi yang parah. Namun, seringkali diabetes terdiagnosis pada tahap lanjut ketika komplikasi sudah mulai muncul. Hal ini disebabkan oleh beberapa faktor, antara lain:

- Gejala awal yang tidak spesifik: Diabetes seringkali tidak menunjukkan gejala yang jelas pada tahap awal, sehingga banyak penderita tidak menyadari kondisi mereka [3].
- Kurangnya kesadaran: Masyarakat masih kurang memahami tentang diabetes dan faktor risiko yang terkait.
- Keterbatasan akses: Tidak semua orang memiliki akses yang mudah ke fasilitas kesehatan untuk melakukan pemeriksaan gula darah secara rutin [1].

Proyek Diagnosis Diabetes dibuat dengan tujuan mengidentifikasi individu yang beresiko terkena diabetes, dengan membuat proyek ini diharapkan dapat membantu peningkatan diagnosis dini dan strategi pengobatan yang dipersonalisasi untuk diabetes.

- Masalah ini harus diselesaikan supaya individu bisa melakukan pengobatan atau penanganan lebih lanjut setelah mengetahui diagnosis diabetes-nya. Masalah ini dapat diselesaikan dengan membuat model prediktif yang akan memberikan persentase individu mengalami diabetes.
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
Pada bagian ini ada lima tahapan yaitu :
1. Mengahpus kolom ID
2. Memfilter data SkinThickness
3. Handling outlier
4. Pembagian dataset dengan fungsi train_test_split dari library sklearn.
5. Standarisasi.


- Menghapus kolom ID karena tidak berpengaruh dan tidak digunakan dalam membuat model prediksi status diabetes.
- Memfilter data SkinThickness yang lebih besar dari 0 karena tidak mungkin ada pasien yang memiliki ketebalan kulit 0 atau lebih kecil.
- Handling outlier dilakukan dengan membuat variabel IQR yang berisi operasi matematika untuk menentukan batas atas dan batas bawah dan mengapus data yang ada di luar dari batas bawah dan atas.
- Pada pembagian dataset data dibagi menjadi data training dan data testing dengan data testing sebesar 20% dan sisanya adalah data training jumlah masing masing kelompok data adalah data training 1335 dan data testing sebesar 334.
- Standarisasi dilakukan agar data memiliki rentang nilai yang normal yaitu dengan rata-rata mendekati 0 dan standart deviasi atau std mendekati 1.
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
- Kelebihan:
   - Implementasi sederhana dan mudah dipahami.
   - Tidak memerlukan asumsi distribusi data.
   - Efektif untuk dataset kecil dengan pola yang jelas.
- Kekurangan:
   - Tidak efisien pada dataset besar karena menghitung jarak ke semua titik data.
   - Sensitif terhadap skala fitur dan keberadaan noise atau outlier.
   - Pemilihan nilai K sangat memengaruhi hasil akurasi.
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
- Kelebihan:
   - Dapat menangani data dengan banyak fitur tanpa overfitting secara signifikan.
   - Memberikan estimasi pentingnya setiap fitur (feature importance).
   - Stabil terhadap noise dan outlier.
- Kekurangan:
   - Interpretasi hasil model sulit karena sifatnya black box.
   - Memerlukan waktu dan memori yang lebih besar dibanding model sederhana.
   - Tidak cocok untuk data real-time karena waktu inferensi relatif lama.
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
- Kelebihan:
   - Memberikan akurasi tinggi pada banyak permasalahan klasifikasi.
   - Mampu menangani data yang tidak seimbang dengan baik.
   - Fleksibel karena dapat menggunakan berbagai fungsi loss.
- Kekurangan:
   - Proses pelatihan relatif lambat.
   - Rentan terhadap overfitting jika jumlah estimator terlalu banyak.
   - Memerlukan tuning parameter yang cermat untuk hasil optimal.
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
- Kelebihan:
   - Efektif pada data berdimensi tinggi.
   - Dapat digunakan dengan berbagai kernel untuk memetakan data non-linear.
   - Memiliki generalisasi yang baik pada dataset dengan margin yang jelas.
- Kekurangan:
   - Kurang efisien pada dataset besar karena waktu komputasi tinggi.
   - Sulit untuk menentukan parameter kernel dan C yang optimal.
   - Kurang cocok untuk data dengan noise tinggi dan tumpang tindih antar kelas.
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
- Kelebihan:
   - Lebih cepat dan efisien dibanding Gradient Boosting konvensional.
   - Mendukung regularisasi (L1 dan L2) untuk mengurangi overfitting.
   - Dapat menangani nilai yang hilang (missing value) secara otomatis.
- Kekurangan:
   - Kompleksitas model tinggi, sulit diinterpretasikan.
   - Membutuhkan sumber daya komputasi besar untuk pelatihan.
   - Parameter tuning cukup rumit dan sensitif terhadap data.
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
- Kelebihan:
   - Mudah dipahami dan diinterpretasikan secara visual.
   - Tidak memerlukan normalisasi data.
   - Mampu menangani data numerik dan kategorikal.
- Kekurangan:
   - Mudah mengalami overfitting jika tidak dilakukan pruning.
   - Perubahan kecil pada data dapat menghasilkan struktur pohon yang berbeda.
   - Kurang stabil jika digunakan tanpa teknik ensemble seperti Random Forest.
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
- Kelebihan:
   - Mampu memodelkan hubungan non-linear yang kompleks.
   - Cocok untuk dataset besar dengan banyak fitur.
   - Dapat melakukan feature learning secara otomatis.
- Kekurangan:
   - Memerlukan waktu pelatihan yang lama dan sumber daya tinggi (GPU/CPU).
   - Sulit diinterpretasikan karena bersifat black box.
   - Membutuhkan tuning banyak parameter (jumlah layer, neuron, learning rate).
     
## Evaluation
Metrik evaluasi yang digunakan adalah antara lain :
1. accuracy
2. precision
3. recall
4. f1

|   | test_accuracy  | test_precision  |  test_recall |  test_f1 |
|---|---|---|---|---|
| KNN  | 0.850299  | 0.793478  |  0.701923 | 0.744898  |
| RF  |  0.988024 | 0.962963  |  1.0 | 0.981132  |
| Boosting  |  0.973054 | 0.952381  |  0.961538 | 0.956938  |
| SVM  | 0.859281  | 0.827586  | 0.692308  | 0.753927  |
| XGB  |  0.997006 | 0.990476  | 1.0  | 0.995215  |
| DT  |  0.991018 | 0.971963  |  1.0 | 0.985782  |
| TF  |  0.838323 | 0.878788  |  0.557692 | 0.682353  |
			
- Penjelasan mengenai metrik yang digunakan
  - akurasi adalah metrik yang mengukur seberapa sering model memprediksi dengan benar
  - precision adalah metrik yang mengukur seberapa akurat model dalam memprediksi kelas positif
  - recall adalah metrik yang Mengukur seberapa baik model dalam mengidentifikasi semua kasus positif yang sebenarnya
  - f1 adalah metrik gabungan antara precision dan recall

- formula metrik yang digunakan
  - Akurasi = (TP + TN) / (TP + TN + FP + FN)
  - Precicion = TP / (TP + FP)
  - Recall = TP / (TP + FN)
  - F1-score = 2 * (precision * recall) / (precision + recall)
- Penjelasan :
  - TP = True Positive
  - TN = True Negative
  - FN = False Negative
  - FP = False Positive
  
    
- Berdasarkan model yang telah dibuat dan di evaluasi maka problem statement yang telah dibuat sebelumnya sudah terjawab dan juga telah mencapai goals yang diharapkan
  - fitur yang paling berkorelasi dengan resiko terkena diabetes adalah glucose, age dan bmi.
  - hubungan resiko terkena diabetes dengan BMI dan usia pasien dapat dilihat bahwa orang yang memiliki BMI diantara 30 - 40 memiliki resiko diabetes tertinggi dan usia dengan rentang 20 - 30 tahun juga memiliki resiko diabetes tertinggi.
  - Berdasarkan ke-4 metrik yang digunakan setelah di evaluasi maka semua model memiliki performa baik tetapi ada tiga model yang memiliki akurasi dibawah 90% yaitu KNN, SVM, dan Neural 
    Network.

- Solution statement yang direncanakan berdampak karena melalui ke-7 model yang dibangun dapat dilihat bahwa setiap model memiliki hasil loss fuctions dan akurasi yang beragam sehingga model yang dibangun bisa di evaluasi dan dibandingkan dengan lainnya sehingga mempermudah pemilihan model yang tepat untuk menyelesaikan permasalahan.

  ## Daftar Pustaka

- [1] World Health Organization, “Diabetes – Fact sheet,” Oct. 2024. [Online]. Available: https://www.who.int/news-room/fact-sheets/detail/diabetes. [Accessed: Nov. 7, 2025].
- [2] M. S. Usman et al., “The Interplay Between Diabetes, Cardiovascular Disease, and Kidney Disease,” NCBI Bookshelf, 2021. [Online]. Available: https://www.ncbi.nlm.nih.gov/books/NBK571718/. [Accessed: Nov. 7, 2025].
- [3] E. Dal Canto et al., “Diabetes as a cardiovascular risk factor: An overview of global evidence,” Eur. J. Prev. Cardiol., vol. 26, Suppl. 2, pp. 25–35, 2019.
