# orange-vs-grapefruit-classification
UTS Machine Learning 

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

### ✅ Kesimpulan

Model terbaik pada kasus ini adalah **Decision Tree** dengan accuracy sebesar **0.9445**, diikuti oleh SVM dan Naive Bayes.

Namun, hasil awal menunjukkan bahwa tanpa preprocessing yang benar, model dapat menghasilkan performa yang sangat buruk. Oleh karena itu, pipeline yang tepat menjadi faktor kunci dalam keberhasilan model machine learning.
