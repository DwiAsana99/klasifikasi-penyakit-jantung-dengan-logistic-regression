# Klasifikasi Penyakit Jantung dengan Logistic Regression

Notebook lengkap untuk memprediksi keberadaan penyakit jantung menggunakan **Logistic Regression** pada dataset **Heart Disease UCI** (303 pasien, 14 variabel klinis).

Alur pipeline mencakup seluruh tahapan proyek data science: dari loading data, eksplorasi, preprocessing, pemodelan, evaluasi, hingga **deployment model pada data pasien baru**.

---

## Struktur File

```
├── Klasifikasi_Penyakit_Jantung_Logistic_Regression.ipynb   # Notebook utama
├── heart.csv                                                 # Dataset Heart Disease UCI
├── requirements.txt                                          # Daftar dependensi Python
├── model_logistic_regression.joblib                          # Model tersimpan (output)
├── scaler_standard.joblib                                    # Scaler tersimpan (output)
├── threshold_optimal.joblib                                  # Threshold tersimpan (output)
```

---

## Cara Menggunakan

### Opsi 1 — Google Colab (Tanpa Instalasi)

1. Upload file `Klasifikasi_Penyakit_Jantung_Logistic_Regression.ipynb` ke [Google Colab](https://colab.research.google.com/)
2. Upload file `heart.csv` ke session Colab (atau biarkan notebook mengunduh otomatis dari GitHub)
3. Jalankan semua cell dari atas ke bawah (**Runtime → Run all**)

### Opsi 2 — Lokal dengan Virtual Environment

```bash
# Clone repository
git clone https://github.com/DwiAsana99/klasifikasi-penyakit-jantung-dengan-logistic-regression.git
cd klasifikasi-penyakit-jantung-dengan-logistic-regression

# Buat virtual environment
python -m venv venv

# Aktifkan virtual environment
# Windows:
venv\Scripts\activate
# macOS/Linux:
source venv/bin/activate

# Install dependensi
pip install -r requirements.txt

# Jalankan Jupyter Notebook
jupyter notebook
```

Buka file `Klasifikasi_Penyakit_Jantung_Logistic_Regression.ipynb` dan jalankan semua cell secara berurutan.

---

## Isi Notebook

| Bab | Topik | Highlight |
|-----|-------|-----------|
| 1 | Pengumpulan & Loading Data | Load dataset dari GitHub / file lokal, kamus 14 variabel klinis |
| 2 | Teori Logistic Regression | Visualisasi sigmoid function, penjelasan log-odds & odds ratio |
| 3 | Exploratory Data Analysis | Statistik deskriptif, distribusi target, heatmap korelasi, distribusi fitur per kelas |
| 4 | Preprocessing | Cek missing value, encoding, train-test split 80:20 (stratified), standardisasi |
| 5 | Membangun Model | Fitting model, tabel koefisien & odds ratio, threshold custom (Youden's J = 0.256) |
| 6 | Evaluasi Model | Confusion matrix, accuracy/precision/recall/F1, ROC curve (AUC=0.869), PR curve |
| 7 | Visualisasi & Insight | Coefficient plot, distribusi probabilitas prediksi, ringkasan temuan |
| 8 | **Deployment** | Simpan/muat model (joblib), fungsi prediksi, **3 kasus pasien baru**, visualisasi & narasi hasil |

---

## Requirements

| Package | Versi | Fungsi |
|---------|-------|--------|
| `pandas` | 3.0.3 | Manipulasi dan analisis data tabular |
| `numpy` | 2.4.6 | Komputasi numerik (array, operasi matematika) |
| `scikit-learn` | 1.9.0 | Model Logistic Regression, preprocessing, metrik evaluasi |
| `matplotlib` | 3.11.0 | Visualisasi grafik (ROC curve, histogram, bar chart) |
| `seaborn` | 0.13.2 | Visualisasi statistik (heatmap korelasi) |
| `joblib` | 1.5.3 | Serialisasi model untuk deployment (save/load `.joblib`) |
| `jupyter` | 1.1.1 | Menjalankan notebook secara lokal |

Semua package dapat diinstal sekaligus:

```bash
pip install -r requirements.txt
```

---

## Dataset

**Heart Disease UCI** — subset Cleveland dari UCI Machine Learning Repository (Detrano et al., 1989).

- **303 pasien**, **14 variabel** (13 fitur + 1 target)
- Target: `1` = Ada Penyakit Jantung, `0` = Tidak Ada
- Tidak ada missing value
- Distribusi kelas relatif seimbang (54.5% : 45.5%)

---

## Hasil Model

| Metrik | Threshold Default (0.5) | Threshold Custom (0.256) |
|--------|------------------------|-------------------------|
| Accuracy | 80.3% | 82.0% |
| Precision | 76.9% | 76.2% |
| Recall | 90.9% | **97.0%** |
| F1-Score | 83.3% | 85.3% |
| False Negative | 3 pasien | **1 pasien** |
| AUC | 0.869 | 0.869 |

---

## Bagian dari Ebook Menata Data Lab

Notebook ini adalah **kode pendamping** dari ebook:

> **Klasifikasi Penyakit Jantung dengan Logistic Regression**
> *Seri Praktik Data Science — Tier Pemula · B2*

Ebook ini bagian dari koleksi **17 ebook** dengan konsep: **1 ebook = 1 model ML + 1 bidang penerapan + 1 dataset publik**. Setiap ebook membahas bukan hanya algoritma, tapi juga cara berpikir untuk menerapkannya pada masalah nyata di berbagai industri.

Dapatkan ebook lengkap dan seri lainnya di:

### **[lynk.id/menatadata](https://lynk.id/menatadata)**

[![Instagram](https://img.shields.io/badge/Instagram-@menatadata.lab-E4405F?logo=instagram&logoColor=white)](https://instagram.com/menatadata.lab)
[![TikTok](https://img.shields.io/badge/TikTok-@menata.data-000000?logo=tiktok&logoColor=white)](https://tiktok.com/@menata.data)

---

*© 2026 Menata Data Lab. Seluruh hak cipta dilindungi.*
