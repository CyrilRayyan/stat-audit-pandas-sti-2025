# Statistical Audit of Pandas

**Proyek Audit Statistik STI 2025 - Kelompok 14**

Laporan ini menyajikan analisis statistik komprehensif terhadap repositori **[Link ke GitHub Proyek]**. Tujuan utama proyek ini adalah mengevaluasi kesehatan dan performa repositori melalui pendekatan statistik yang mencakup estimasi parameter, inferensi statistik, pengujian hipotesis, serta simulasi probabilistik.

---

## 1. Deskripsi Proyek

Audit statistik dilakukan terhadap data issue pada repositori GitHub untuk memahami pola produktivitas, validitas model distribusi, dan faktor-faktor yang memengaruhi keterlambatan penyelesaian issue.

Analisis dilakukan menggunakan metode:

- Maximum Likelihood Estimation (MLE)
- Bayesian Estimation (Beta Posterior)
- Confidence Interval Analysis
- Hypothesis Testing (Kolmogorov-Smirnov Test)
- Monte Carlo Simulation
- Markov Chain Monte Carlo (MCMC)
- Bloom Filter Analysis

---

## 2. Tujuan Penelitian

Penelitian ini bertujuan untuk:

1. Mengestimasi laju penyelesaian issue pada repositori.
2. Memvalidasi model distribusi yang menggambarkan durasi penyelesaian issue.
3. Mengidentifikasi bottleneck atau hambatan utama dalam proses penyelesaian issue.
4. Memberikan insight berbasis data untuk meningkatkan produktivitas proyek perangkat lunak.

---

## 3. Anggota Tim & Peran

| Nama | Peran | Tanggung Jawab |
|--------|--------|--------|
| Cyril Alif Ar Rayyan | Data Engineer | Exploratory Data Analysis (EDA), Data Collection |
| Cyril Alif Ar Rayyan | Estimation Analyst | Maximum Likelihood Estimation (MLE), Beta Posterior |
| Cyril Alif Ar Rayyan | Inference Analyst | Confidence Intervals |
| Cyril Alif Ar Rayyan | Hypothesis Analyst | Hypothesis Testing |
| Cyril Alif Ar Rayyan | Computation Analyst | Simulation, MCMC, Bloom Filter |

---

## 4. Research Questions

### Pertanyaan Penelitian

Bagaimana Kualitas data mentah dan proses pembersihannya

#### A. Estimasi
Berapa laju penyelesaian issue ($\lambda$) yang merepresentasikan produktivitas repositori?

#### B. Inferensi
Apakah durasi penyelesaian issue mengikuti distribusi eksponensial secara signifikan sehingga model eksponensial layak digunakan?

#### C. Simulasi
Faktor durasi apa saja yang menjadi bottleneck (hambatan) utama dalam sistem penyelesaian issue?

---

## 5. Metodologi

### Data Collection

Data diperoleh dari GitHub API dan mencakup informasi:

- Issue ID
- Tanggal pembuatan issue
- Tanggal penutupan issue
- Durasi penyelesaian issue
- Status issue

### Estimation

Metode yang digunakan:

- Maximum Likelihood Estimation (MLE)
- Bayesian Estimation menggunakan Beta Posterior

Output utama:

- Estimasi parameter laju penyelesaian issue ($\lambda$)

### Statistical Inference

Metode yang digunakan:

- Confidence Interval Estimation
- Kolmogorov-Smirnov Test (KS-Test)

Tujuan:

- Menguji apakah data mengikuti distribusi eksponensial.

### Simulation

Metode yang digunakan:

- Monte Carlo Simulation
- Markov Chain Monte Carlo (MCMC)

Tujuan:

- Mengidentifikasi pola keterlambatan dan bottleneck dalam repositori.

---

## 6. Workflow

### Cara Menjalankan

#### 1. Clone Repository

```bash
git clone [Link Repository]
cd [Nama Repository]
```

#### 2. Install Dependencies

```bash
pip install pandas numpy scipy matplotlib
```

#### 3. Jalankan Analisis

##### Estimasi Parameter λ

```bash
python estimation.py
```

##### Pengujian Hipotesis (KS-Test)

```bash
python analysis_D.py
```

##### Analisis Bottleneck

```bash
python analysis_E.py
```

---

## 7. Hasil Analisis

### Estimasi Laju Penyelesaian Issue

Hasil estimasi menunjukkan bahwa laju penyelesaian issue repositori adalah:

**λ = [Estimasi Laju Penyelesaian (Lambda/MLE): 0.0301 issue per hari] **

Interpretasi:

- Semakin besar nilai λ, semakin tinggi produktivitas repositori dalam menyelesaikan issue.

---

### Validasi Distribusi

Hasil Kolmogorov-Smirnov Test:

| Parameter | Nilai |
|------------|---------|
| P-Value | 0.0000 |
| Keputusan | Tolak H₀ |

Interpretasi:

Karena nilai p-value lebih kecil dari tingkat signifikansi (α = 0.05), maka hipotesis bahwa durasi penyelesaian issue mengikuti distribusi eksponensial ditolak.

Hal ini menunjukkan bahwa terdapat variasi perilaku penyelesaian issue yang tidak dapat dijelaskan hanya dengan model eksponensial sederhana.

---

### Analisis Bottleneck

Hasil simulasi menunjukkan bahwa terdapat:

**Total issue: 9900
Jumlah issue yang tergolong bottleneck (outlier): 1373
Batas durasi normal: 36.58 hari**

yang tergolong sebagai bottleneck atau outlier berdasarkan durasi penyelesaiannya.

Karakteristik bottleneck:

- Durasi penyelesaian jauh lebih lama dibanding rata-rata.
- Berpotensi menyebabkan keterlambatan progres proyek.
- Memerlukan perhatian khusus dari maintainer repositori.

---

## 8. Temuan Utama (Key Findings)

### Produktivitas Repositori

- Laju penyelesaian issue sebesar **[Estimasi Laju Penyelesaian (Lambda/MLE): 0.0301 issue **.
- Confidence Interval 95% untuk rata-rata durasi: 30.8876 hingga 35.1814 hari

### Validitas Model

- Distribusi eksponensial tidak cukup merepresentasikan data aktual.
- Diperlukan model distribusi yang lebih fleksibel.

### Bottleneck

- Ditemukan **Total issue: 9900
Jumlah issue yang tergolong bottleneck (outlier): 1373
Batas durasi normal: 36.58 hari** yang berpotensi menjadi hambatan utama dalam workflow pengembangan.

---

## 9. Kesimpulan

Berdasarkan audit statistik yang dilakukan, repositori menunjukkan tingkat produktivitas yang dapat diukur melalui estimasi parameter λ. Namun demikian, hasil pengujian hipotesis menunjukkan bahwa pola penyelesaian issue tidak sepenuhnya mengikuti distribusi eksponensial.

Selain itu, simulasi probabilistik berhasil mengidentifikasi sejumlah bottleneck yang berkontribusi terhadap keterlambatan penyelesaian issue. Temuan ini dapat digunakan sebagai dasar pengambilan keputusan untuk meningkatkan efisiensi pengelolaan proyek perangkat lunak.

---

## 10. Langkah Selanjutnya


Kemudian jalankan:

```bash
git add .
git commit -m "Complete Statistical Audit Report"
git push origin main
```

---

## Teknologi yang Digunakan

- Python 3.x
- Pandas
- NumPy
- SciPy
- Matplotlib
- GitHub API
- Gemini

---

## Lisensi

Proyek ini dibuat untuk memenuhi tugas **Statistical Thinking for Informatics (STI) 2025**.
