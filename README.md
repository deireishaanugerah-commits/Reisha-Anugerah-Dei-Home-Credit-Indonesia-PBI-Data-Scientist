# 📊 Prediksi Risiko Gagal Bayar Nasabah Kredit  
## Home Credit Indonesia — Machine Learning Project

Project ini bertujuan membangun model Machine Learning untuk memprediksi risiko gagal bayar (credit default) nasabah kredit guna membantu pengambilan keputusan kredit yang lebih akurat dan berbasis data.

Project dilakukan dalam kegiatan **Project Based Internship – Data Scientist**.

---

## 📌 Latar Belakang

Home Credit Indonesia menghadapi tantangan dalam menyalurkan kredit secara tepat sasaran tanpa meningkatkan risiko gagal bayar.

Dengan pemanfaatan analisis data dan Machine Learning, sistem credit scoring dapat dioptimalkan sehingga keputusan pemberian pinjaman menjadi lebih akurat dan berkelanjutan.

---

## 🎯 Tujuan Project

- Memprediksi kemungkinan gagal bayar nasabah.
- Membandingkan performa beberapa model Machine Learning.
- Menghasilkan insight bisnis dari data nasabah.
- Mendukung keputusan pemberian kredit berbasis data.

---

## 📂 Dataset

Dataset yang digunakan:

- `application_train`
- `application_test`

### Target Variable

| Target | Keterangan |
|-------|------------|
| 1 | Gagal Bayar (Default) |
| 0 | Kredit Lancar / Tidak Gagal Bayar |

### Karakteristik Data
- Data demografis
- Data pendidikan
- Data pekerjaan
- Data finansial

---

## ⚙️ Metode dan Alur Kerja

### 1. Data Preparation
- Pemeriksaan data duplikat
- Handling missing values:
  - Median (data numerik)
  - "unknown" (data kategorikal)
  - Drop row atau column jika diperlukan

### 2. Feature Encoding
- Label Encoding (kategori biner)
- One-Hot Encoding (multi kategori)

### 3. Exploratory Data Analysis (EDA)
- Analisis distribusi data
- Visualisasi hubungan antar variabel

### 4. Data Splitting
- 80% Data Training
- 20% Data Testing

### 5. Model Machine Learning
Model yang digunakan:
- Logistic Regression
- Random Forest
- LightGBM

### 6. Prediction
Model terbaik digunakan untuk melakukan prediksi pada dataset `application_test`.

---

## 🔍 Insight Utama

### 📘 Insight 1 — Tingkat Pendidikan
Semakin rendah tingkat pendidikan nasabah, semakin tinggi risiko gagal bayar.

**Business Action**
- Kebijakan kredit lebih ketat untuk pendidikan rendah
- Prioritas pemasaran pada pendidikan tinggi
- Pendidikan menjadi variabel utama prediksi risiko

---

### 💰 Insight 2 — Pendapatan Nasabah
Nasabah gagal bayar cenderung memiliki pendapatan lebih rendah dibandingkan nasabah yang tidak gagal bayar.

**Business Action**
- Menentukan limit kredit berdasarkan pendapatan
- Menetapkan ambang minimum pendapatan
- Pendapatan menjadi variabel utama model risiko kredit

---

## 🤖 Evaluasi Model Machine Learning

| Model | Hasil |
|------|------|
| Logistic Regression | Model baseline |
| Random Forest | Recall default = 0 |
| ⭐ LightGBM | ROC-AUC = 0.76 |
|  | Recall Default = 0.68 |

✅ **Model Terbaik: LightGBM**

Alasan:
- ROC-AUC tertinggi
- Kemampuan terbaik mendeteksi nasabah gagal bayar
- Random Forest tidak dipilih karena gagal mendeteksi nasabah gagal bayar (recall = 0)

---

## 📈 Default Prediction Result

Hasil prediksi menggunakan model **LightGBM** pada dataset `application_test`:

| Kategori | Jumlah Nasabah |
|---------|----------------|
| Default (1) | 24.679 |
| Non-Default (0) | 24.065 |
| Total Data | ±48.000 |

### Interpretasi
- Jumlah nasabah berisiko gagal bayar hampir seimbang dengan nasabah aman.
- Model mampu mengidentifikasi kelompok risiko tinggi sejak tahap awal pengajuan kredit.

---

## 💼 Business Recommendation

- Menggunakan skor risiko sebagai tahap awal screening kredit.
- Membantu tim kredit dalam pengambilan keputusan yang lebih objektif.
- Menyesuaikan pemberian kredit berdasarkan profil nasabah.
- Monitoring nasabah berisiko tinggi secara proaktif.

---

## 🛠️ Tech Stack

- Python
- Pandas
- NumPy
- Scikit-learn
- LightGBM
- Matplotlib
- Seaborn

---

## 📁 Struktur Project
