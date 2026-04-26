# orange-vs-grapefruit-classification
UTS Machine Learning 

Nama : Nurdiansyah Pratama

NIM : 1237050139

Kelas : C

Dosen Pengampu : Pak H. Aldy Rialdy Atmadja M.T.

📌 Latar Belakang

Klasifikasi buah merupakan salah satu penerapan machine learning dalam pengolahan data berbasis fitur numerik. Pada dataset yang digunakan, terdapat dua jenis buah yaitu orange dan grapefruit, yang memiliki karakteristik fisik yang mirip namun dapat dibedakan melalui atribut seperti diameter, berat, dan warna.

Agar dapat diproses oleh algoritma machine learning, label kategorikal perlu diubah menjadi bentuk numerik. Pada penelitian ini dilakukan proses encoding label dengan skema:

0 = orange
1 = grapefruit

Transformasi ini memungkinkan model untuk melakukan proses pembelajaran secara matematis dalam membedakan kedua kelas berdasarkan pola data yang ada.

Dengan pendekatan ini, diharapkan model mampu melakukan klasifikasi secara akurat dan dapat dibandingkan performanya menggunakan beberapa algoritma yang berbeda.

## 📈 Hasil dan Analisis

### 🔢 Hasil Evaluasi Model

Berikut adalah hasil evaluasi dari tiga model yang digunakan:

| Model         | Accuracy | Precision | Recall | F1-Score |
| ------------- | -------- | --------- | ------ | -------- |
| Decision Tree | 0.9445   | 0.94      | 0.94   | 0.94     |
| Naive Bayes   | 0.92     | 0.92      | 0.92   | 0.92     |
| SVM           | 0.937    | 0.94      | 0.94   | 0.94     |

---

### ⚠️ Temuan Awal (Anomali Model)

Pada percobaan awal, model Decision Tree menghasilkan akurasi yang sangat rendah yaitu sekitar **0.494**.

Analisis terhadap hasil tersebut menunjukkan bahwa:

* Model gagal mengklasifikasikan salah satu kelas (precision = 0.00)
* Model cenderung hanya memprediksi satu kelas saja
* Terjadi ketidakseimbangan prediksi (model collapse)

Hal ini mengindikasikan adanya masalah pada tahap:

* Preprocessing data
* Encoding label
* Pipeline training yang belum konsisten

---

### 🔧 Perbaikan dan Hasil Akhir

Setelah dilakukan perbaikan pada preprocessing dan pipeline training:

* Label encoding diperbaiki
* Data dipastikan sesuai antara fitur dan target
* Model dilatih ulang dengan data yang benar

Hasilnya, performa Decision Tree meningkat signifikan menjadi:

👉 **Accuracy: 0.9445**

Ini menunjukkan bahwa model sudah mampu:

* Membedakan kedua kelas dengan baik
* Tidak bias terhadap satu kelas tertentu
* Memberikan prediksi yang stabil

---

### 📊 Analisis Perbandingan Model

#### 🌳 Decision Tree

* Memiliki performa terbaik (accuracy tertinggi)
* Mudah diinterpretasikan
* Sensitif terhadap perubahan data (terlihat dari anomali awal)

#### 📊 Naive Bayes

* Performa cukup stabil
* Lebih sederhana dan cepat
* Sedikit lebih rendah karena asumsi independensi fitur

#### ⚡ Support Vector Machine (SVM)

* Performa sangat baik dan stabil
* Cocok untuk data dengan pemisahan yang jelas
* Sedikit di bawah Decision Tree dalam kasus ini

---

### 🧠 Insight Penting

Dari hasil eksperimen, dapat disimpulkan bahwa:

* Machine Learning sangat bergantung pada preprocessing data
* Kesalahan kecil dalam pipeline dapat menyebabkan model gagal total
* Evaluasi model tidak cukup hanya melihat accuracy, tetapi juga precision, recall, dan F1-score

---

### 📊 Analisis ROC Curve

ROC Curve digunakan untuk mengevaluasi kemampuan model dalam membedakan antara dua kelas.

Berdasarkan grafik ROC:

* Model dengan nilai AUC tertinggi memiliki performa terbaik
* Kurva yang mendekati sudut kiri atas menunjukkan klasifikasi yang lebih akurat

Hasil menunjukkan bahwa:

* Decision Tree dan SVM memiliki performa yang sangat baik
* Naive Bayes sedikit lebih rendah namun tetap stabil

Hal ini mengindikasikan bahwa sebagian besar model mampu memisahkan kedua kelas dengan baik berdasarkan fitur yang tersedia.


### ✅ Kesimpulan

Model terbaik pada kasus ini adalah **Decision Tree** dengan accuracy sebesar **0.9445**, diikuti oleh SVM dan Naive Bayes.

Namun, hasil awal menunjukkan bahwa tanpa preprocessing yang benar, model dapat menghasilkan performa yang sangat buruk. Oleh karena itu, pipeline yang tepat menjadi faktor kunci dalam keberhasilan model machine learning.
