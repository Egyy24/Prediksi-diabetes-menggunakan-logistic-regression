# Diabetics Prediction using Logistic Regression

Proyek ini merupakan tugas praktik klasifikasi menggunakan algoritma **Logistic Regression** untuk memprediksi apakah seorang pasien menderita diabetes atau tidak berdasarkan data medis.

---

## Anggota Kelompok

| Nama | NIM |
|------|-----|
| Qanzul Arays | 23523228 |
| Muhammad Ibnu Rasyid | 23523127 |

---

## Dataset

- **Nama Dataset:** Pima Indians Diabetes Dataset
- **Sumber:** [Kaggle - Diabetes Dataset](https://www.kaggle.com/datasets/kandij/diabetes-dataset)
- **Jumlah Data:** 768 baris, 9 kolom
- **Subjek:** Pasien wanita keturunan suku Pima Indian

### Fitur Input (8 fitur)

| Fitur | Keterangan |
|-------|------------|
| `Pregnancies` | Jumlah kehamilan |
| `Glucose` | Kadar gula darah |
| `BloodPressure` | Tekanan darah |
| `SkinThickness` | Ketebalan lipatan kulit |
| `Insulin` | Kadar insulin dalam darah |
| `BMI` | Indeks massa tubuh |
| `DiabetesPedigreeFunction` | Riwayat diabetes dalam keluarga |
| `Age` | Usia pasien |

### Target Klasifikasi

Kolom `Outcome` dengan dua kelas diskrit:
- **0** = Tidak menderita diabetes (500 data, ~65%)
- **1** = Menderita diabetes (268 data, ~35%)

---

## Alur Proses

1. **Memahami Dataset** — eksplorasi data awal, distribusi kelas, dan tipe data
2. **Preprocessing** — deteksi nilai 0 tidak logis pada kolom `Glucose`, `BloodPressure`, `SkinThickness`, `Insulin`, dan `BMI`, serta standarisasi fitur menggunakan `StandardScaler`
3. **Pembagian Data** — split 80% training dan 20% testing dengan `stratify=y`
4. **Membangun Model** — melatih model `LogisticRegression` dari scikit-learn
5. **Evaluasi Model** — Classification Report dan Confusion Matrix
6. **Perbandingan Prediksi** — menampilkan 20 contoh hasil prediksi vs label sebenarnya

---

## Hasil Evaluasi Model

**Akurasi: 71.43%**

| Kelas | Precision | Recall | F1-Score |
|-------|-----------|--------|----------|
| 0 (Tidak Diabetes) | 0.76 | 0.82 | 0.79 |
| 1 (Diabetes) | 0.61 | 0.52 | 0.56 |

### Confusion Matrix

| | Prediksi 0 | Prediksi 1 |
|---|---|---|
| **Aktual 0** | TN = 82 | FP = 18 |
| **Aktual 1** | FN = 26 | TP = 28 |

---

## Kesimpulan

Model Logistic Regression menunjukkan kinerja yang cukup baik dalam mengklasifikasikan pasien yang tidak menderita diabetes (recall 82%), namun kurang efektif dalam mendeteksi pasien yang benar-benar menderita diabetes (recall hanya 52%). Dalam konteks medis, **False Negative** (pasien diabetes yang tidak terdeteksi) lebih berbahaya karena pasien tidak mendapatkan penanganan yang seharusnya.

---

## Library yang Digunakan

- `pandas` — manipulasi data
- `scikit-learn` — preprocessing, model, dan evaluasi
- `matplotlib` & `seaborn` — visualisasi Confusion Matrix

---

## Cara Menjalankan

1. Upload file `diabetes2.csv` ke Google Colab (`/content/sample_data/`)
2. Buka file `Diabetics_prediction.ipynb` di Google Colab
3. Jalankan semua cell secara berurutan (`Runtime > Run all`)
