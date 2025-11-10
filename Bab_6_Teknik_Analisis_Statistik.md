
# Bab 6: Teknik Analisis Statistik

## 6.1 Konsep Dasar Statistik untuk Evaluasi Sistem

### 6.1.1 Populasi dan Sampel

**Populasi** dalam konteks evaluasi sistem IT merujuk pada keseluruhan elemen yang menjadi objek penelitian atau analisis. Populasi dapat berupa pengguna sistem, transaksi yang diproses, permintaan server, atau komponen sistem yang dievaluasi. Sebagai contoh, populasi dalam evaluasi performa database dapat mencakup semua query yang dieksekusi dalam periode tertentu.

**Sampel** adalah subset dari populasi yang diambil untuk mewakili keseluruhan populasi. Sampling digunakan karena seringkali tidak praktis atau tidak mungkin untuk menganalisis seluruh populasi karena keterbatasan waktu, sumber daya, atau akses.

#### Teknik Sampling

1. **Random Sampling (Simple Random Sampling)**
   - Setiap elemen populasi memiliki peluang yang sama untuk terpilih
   - Berguna ketika populasi homogen
   - Contoh: Dari populasi 1000 user aktif sistem CRM, ingin mengambil sampel dengan margin of error 5%:
     ```
     n = N / (1 + N(e)²)
       = 1000 / (1 + 1000(0.05)²)
       = 1000 / (1 + 1000(0.0025))
       = 1000 / (1 + 2.5)
       = 1000 / 3.5
       = 285.7 ≈ 286 user
     ```
     Dengan demikian, perlu mengambil minimal 286 user secara acak dari 1000 user untuk mencapai margin of error 5%.

2. **Stratified Sampling**
   - Populasi dibagi menjadi strata (subkelompok) homogen, kemudian sampling dilakukan dari setiap stratum
   - Berguna ketika populasi memiliki subkelompok dengan karakteristik berbeda
   - Contoh: Membagi user berdasarkan tingkat keahlian (pemula, menengah, ahli) kemudian mengambil sampel dari setiap kelompok

3. **Systematic Sampling**
   - Memilih elemen setiap interval k dari populasi
   - Formula: `k = N/n` di mana k = interval sampling
   - Contoh: Memilih setiap transaksi ke-10 dari log transaksi untuk analisis error rate

4. **Cluster Sampling**
   - Populasi dibagi menjadi cluster (kelompok alami), kemudian beberapa cluster dipilih secara acak
   - Efisien untuk populasi yang tersebar secara geografis
   - Contoh: Memilih beberapa server dari data center yang berbeda untuk evaluasi performa jaringan

#### Ukuran Sampel Minimum

Penentuan ukuran sampel minimum bergantung pada beberapa faktor:
- Tingkat kepercayaan (confidence level)
- Margin of error
- Variabilitas populasi
- Desain penelitian

Formula umum untuk menghitung ukuran sampel:
```
n = (Z² × p × (1-p)) / e²
```
di mana:
- n = ukuran sampel
- Z = Z-score (1.96 untuk confidence level 95%)
- p = proporsi populasi (0.5 untuk variabilitas maksimum)
- e = margin of error

Untuk populasi kecil, digunakan formula koreksi:
```
n_adjusted = n / (1 + (n-1)/N)
```

#### Sampling Error dan Bias

**Sampling Error** adalah perbedaan antara statistik sampel dan parameter populasi yang disebabkan oleh fakta bahwa hanya sampel yang diamati, bukan seluruh populasi. Sampling error dapat dikurangi dengan meningkatkan ukuran sampel.

**Sampling Bias** terjadi ketika sampel tidak mewakili populasi secara akurat. Jenis-jenis sampling bias:
- **Selection Bias**: Proses pemilihan sampel menghasilkan sampel yang tidak representatif
- **Non-response Bias**: Individu yang tidak merespons memiliki karakteristik berbeda dengan yang merespons
- **Voluntary Response Bias**: Sampel terdiri dari individu yang secara sukarela memilih untuk berpartisipasi

#### Contoh: Sampling User untuk Evaluasi Usability Sistem

Sebuah perusahaan ingin mengevaluasi usability sistem CRM baru mereka. Populasi terdiri dari 5000 sales representative yang tersebar di seluruh Indonesia.

Langkah-langkah sampling:
1. Menentukan ukuran sampel: Dengan confidence level 95%, margin of error 5%, dan variabilitas maksimum:
   ```
   n = (1.96² × 0.5 × 0.5) / 0.05² = 384.16 ≈ 385
   ```

2. Memilih teknik sampling: Stratified sampling berdasarkan wilayah (Sumatera, Jawa, Kalimantan, Sulawesi, Bali-Nusa, Papua)

3. Menentukan proporsi sampel per wilayah:
   - Jawa: 60% populasi → 231 sampel
   - Sumatera: 15% populasi → 58 sampel
   - Kalimantan: 10% populasi → 39 sampel
   - Sulawesi: 8% populasi → 31 sampel
   - Bali-Nusa: 5% populasi → 19 sampel
   - Papua: 2% populasi → 7 sampel

4. Melakukan evaluasi usability pada sampel yang terpilih

#### Visualisasi: Hubungan Populasi dan Sampel

```
┌─────────────────────────────────────────────────────────────┐
│                    POPULASI (N=5000)                        │
│                                                             │
│  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐        │
│  │   Wilayah   │  │   Wilayah   │  │   Wilayah   │        │
│  │   Jawa      │  │  Sumatera   │  │ Kalimantan  │        │
│  │  (3000)     │  │   (750)     │  │   (500)     │        │
│  │             │  │             │  │             │        │
│  │ ┌─────────┐ │  │ ┌─────────┐ │  │ ┌─────────┐ │        │
│  │ │ Sampel  │ │  │ │ Sampel  │ │  │ │ Sampel  │ │        │
│  │ │ (231)   │ │  │ │  (58)   │ │  │ │  (39)   │ │        │
│  │ └─────────┘ │  │ └─────────┘ │  │ └─────────┘ │        │
│  └─────────────┘  └─────────────┘  └─────────────┘        │
│                                                             │
│  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐        │
│  │   Wilayah   │  │   Wilayah   │  │   Wilayah   │        │
│  │  Sulawesi   │  │ Bali-Nusa   │  │    Papua    │        │
│  │   (400)     │  │   (250)     │  │   (100)     │        │
│  │             │  │             │  │             │        │
│  │ ┌─────────┐ │  │ ┌─────────┐ │  │ ┌─────────┐ │        │
│  │ │ Sampel  │ │  │ │ Sampel  │ │  │ │ Sampel  │ │        │
│  │ │  (31)   │ │  │ │  (19)   │ │  │ │   (7)   │ │        │
│  │ └─────────┘ │  │ └─────────┘ │  │ └─────────┘ │        │
│  └─────────────┘  └─────────────┘  └─────────────┘        │
└─────────────────────────────────────────────────────────────┘
```

### 6.1.2 Tingkat Signifikansi dan Kekuatan Uji

Dalam analisis statistik untuk evaluasi sistem, konsep signifikansi dan kekuatan uji sangat penting untuk menarik kesimpulan yang valid tentang performa atau efektivitas sistem.

#### Alpha (α) dan Beta (β)

**Alpha (α)** atau *significance level* adalah probabilitas melakukan **Kesalahan Tipe I** – menolak hipotesis nol yang sebenarnya benar. Dalam konteks evaluasi sistem, ini berarti menyimpulkan bahwa suatu perubahan atau intervensi memiliki efek padahal sebenarnya tidak.

- Nilai α yang umum digunakan: 0.05 (5%), 0.01 (1%), atau 0.10 (10%)
- α = 0.05 berarti ada 5% risiko menyimpulkan bahwa ada efek padahal sebenarnya tidak ada

**Beta (β)** adalah probabilitas melakukan **Kesalahan Tipe II** – gagal menolak hipotesis nol yang sebenarnya salah. Dalam evaluasi sistem, ini berarti gagal mendeteksi efek yang sebenarnya ada.

- **Power (1-β)** adalah probabilitas secara benar menolak hipotesis nol ketika memang seharusnya ditolak
- Power yang umum diinginkan: 0.80 (80%) atau lebih tinggi

#### P-value dan Interpretasinya

**P-value** adalah probabilitas mendapatkan hasil yang sama atau lebih ekstrem dari yang diamati, dengan asumsi hipotesis nol benar.

**Interpretasi P-value:**
- Jika p-value ≤ α: Menolak hipotesis nol (hasil signifikan secara statistik)
- Jika p-value > α: Gagal menolak hipotesis nol (hasil tidak signifikan secara statistik)

Contoh interpretasi:
- p-value = 0.03 dengan α = 0.05: Signifikan secara statistik, ada cukup bukti untuk menolak hipotesis nol
- p-value = 0.12 dengan α = 0.05: Tidak signifikan secara statistik, tidak ada cukup bukti untuk menolak hipotesis nol

P-value tidak mengukur:
- Besarnya efek (effect size)
- Pentingnya hasil secara praktis
- Probabilitas hipotesis nol benar

#### Effect Size

**Effect size** mengukur besarnya efek atau hubungan antar variabel, independen dari ukuran sampel. Effect size penting karena hasil yang signifikan secara statistik tidak selalu berarti signifikan secara praktis.

**Jenis-jenis Effect Size:**

1. **Cohen's d** (untuk perbandingan dua kelompok):
   ```
   d = (M₁ - M₂) / SD_pooled
   ```
   di mana:
   - M₁, M₂ = mean dari kelompok 1 dan 2
   - SD_pooled = standard deviation gabungan

   Interpretasi Cohen's d:
   - Kecil: d ≈ 0.2
   - Sedang: d ≈ 0.5
   - Besar: d ≈ 0.8

2. **Eta-squared (η²)** (untuk ANOVA):
   ```
   η² = SS_effect / SS_total
   ```
   di mana:
   - SS_effect = sum of squares untuk efek
   - SS_total = total sum of squares

   Interpretasi eta-squared:
   - Kecil: η² ≈ 0.01
   - Sedang: η² ≈ 0.06
   - Besar: η² ≈ 0.14

3. **Pearson's r** (untuk korelasi):
   - Rentang: -1 hingga +1
   - Interpretasi:
     - Kecil: r ≈ 0.1
     - Sedang: r ≈ 0.3
     - Besar: r ≈ 0.5

#### Power Analysis

**Power analysis** digunakan untuk menentukan ukuran sampel yang diperlukan untuk mendeteksi efek dengan ukuran tertentu pada tingkat signifikansi tertentu.

**Komponen Power Analysis:**
1. **Effect size**: Besarnya efek yang ingin dideteksi
2. **Alpha (α)**: Tingkat signifikansi (biasanya 0.05)
3. **Power (1-β)**: Probabilitas mendeteksi efek (biasanya 0.80)
4. **Sample size (n)**: Jumlah observasi

Formula untuk menghitung power untuk uji-t:
```
δ = d / √(1/n₁ + 1/n₂)
```
di mana:
- δ = non-centrality parameter
- d = Cohen's d
- n₁, n₂ = ukuran sampel kelompok 1 dan 2

#### Contoh: Menentukan Signifikansi Improvement dalam Response Time

Sebuah perusahaan mengimplementasikan algoritma caching baru untuk meningkatkan response time aplikasi web. Mereka ingin menguji apakah perubahan tersebut signifikan secara statistik.

**Data:**
- Response time sebelum caching (n=30): Mean = 450ms, SD = 85ms
- Response time setelah caching (n=30): Mean = 320ms, SD = 75ms

**Analisis:**

1. **Menghitung Cohen's d**:
   ```
   SD_pooled = √[((n₁-1)SD₁² + (n₂-1)SD₂²) / (n₁ + n₂ - 2)]
              = √[((29×85²) + (29×75²)) / (30 + 30 - 2)]
              = √[((29×7225) + (29×5625)) / 58]
              = √[(209525 + 163125) / 58]
              = √[372650 / 58]
              = √6425
              = 80.16
   
   d = (M₁ - M₂) / SD_pooled
     = (450 - 320) / 80.16
     = 130 / 80.16
     = 1.62
   ```
   Cohen's d = 1.62 (effect size besar)

2. **Melakukan uji-t**:
   ```
   t = (M₁ - M₂) / (SD_pooled × √(1/n₁ + 1/n₂))
     = 130 / (80.16 × √(1/30 + 1/30))
     = 130 / (80.16 × √0.0667)
     = 130 / (80.16 × 0.258)
     = 130 / 20.68
     = 6.29
   ```
   Dengan df = 58, p-value < 0.001

3. **Interpretasi**:
   - Terdapat penurunan signifikan secara statistik dalam response time setelah implementasi caching (t(58) = 6.29, p < 0.001)
   - Effect size besar (Cohen's d = 1.62) menunjukkan peningkatan yang signifikan secara praktis
   - Penurunan rata-rata response time adalah 130ms (dari 450ms menjadi 320ms)

4. **Power Analysis**:
   Dengan α = 0.05, effect size d = 1.62, dan n = 30 per kelompok:
   - Power > 0.99 (sangat tinggi)
   - Artinya, jika memang ada perbedaan sebesar ini, penelitian ini memiliki kemungkinan >99% untuk mendeteksinya

### 6.1.3 Jenis Data dan Skala Pengukuran

Dalam evaluasi sistem, pemahaman tentang jenis data dan skala pengukuran sangat penting karena menentukan teknik analisis statistik yang tepat untuk digunakan.

#### Skala Pengukuran

1. **Nominal**
   - Data kategorikal tanpa urutan inheren
   - Hanya dapat dihitung frekuensinya
   - Operasi matematika yang valid: =, ≠
   - Contoh dalam sistem: Browser type (Chrome, Firefox, Safari), OS (Windows, Linux, macOS), error type (404, 500, 503)

2. **Ordinal**
   - Data kategorikal dengan urutan yang bermakna
   - Jarak antar kategori tidak diketahui atau tidak sama
   - Operasi matematika yang valid: =, ≠, <, >
   - Contoh dalam sistem: User satisfaction rating (Very Dissatisfied, Dissatisfied, Neutral, Satisfied, Very Satisfied), severity level (Low, Medium, High, Critical), priority (P1, P2, P3, P4)

3. **Interval**
   - Data numerik dengan jarak yang sama antar nilai
   - Tidak memiliki titik nol absolut yang bermakna
   - Operasi matematika yang valid: =, ≠, <, >, +, -
   - Contoh dalam sistem: Temperature dalam Celsius, CPU usage percentage, timestamp (Unix time)

4. **Ratio**
   - Data numerik dengan jarak yang sama antar nilai
   - Memiliki titik nol absolut yang bermakna
   - Operasi matematika yang valid: =, ≠, <, >, +, -, ×, ÷
   - Contoh dalam sistem: Response time (ms), throughput (requests/second), memory usage (MB), uptime (hours), file size (KB)

#### Diskrit vs Kontinu

**Data Diskrit**:
- Hanya dapat mengambil nilai tertentu
- Biasanya hasil dari perhitungan
- Contoh: Number of errors, number of users, number of transactions per second

**Data Kontinu**:
- Dapat mengambil nilai apa pun dalam rentang tertentu
- Biasanya hasil dari pengukuran
- Contoh: Response time, CPU temperature, memory usage, network latency

#### Implikasi untuk Pemilihan Uji Statistik

Pemilihan uji statistik bergantung pada jenis data dan skala pengukuran:

| Jenis Data | Skala Pengukuran | Uji Statistik yang Sesuai |
|------------|------------------|---------------------------|
| Kategorikal | Nominal | Chi-square test, Fisher's exact test |
| Kategorikal | Ordinal | Mann-Whitney U, Wilcoxon signed-rank, Kruskal-Wallis |
| Numerik | Interval/Ratio (distribusi normal) | t-test, ANOVA, Pearson correlation, Linear regression |
| Numerik | Interval/Ratio (distribusi tidak normal) | Mann-Whitney U, Wilcoxon signed-rank, Spearman correlation |

#### Contoh: Klasifikasi Metrik Sistem

Berikut adalah contoh klasifikasi metrik sistem berdasarkan skala pengukuran:

1. **Nominal**:
   - Browser type: Chrome, Firefox, Safari, Edge
   - Device type: Desktop, Mobile, Tablet
   - HTTP method: GET, POST, PUT, DELETE
   - Error code: 200, 404, 500, 503

2. **Ordinal**:
   - User satisfaction: 1 (Very Poor) hingga 5 (Excellent)
   - Severity level: Low, Medium, High, Critical
   - Priority: P1 (Critical), P2 (High), P3 (Medium), P4 (Low)
   - Performance rating: Unacceptable, Marginal, Acceptable, Excellent

3. **Interval**:
   - CPU usage: 0% hingga 100%
   - Memory usage: 0% hingga 100%
   - Temperature: 0°C hingga 100°C
   - Timestamp: Unix time

4. **Ratio**:
   - Response time: 0 ms hingga tak terhingga
   - Throughput: 0 requests/second hingga kapasitas maksimum
   - Uptime: 0 hours hingga tak terhingga
   - File size: 0 KB hingga kapasitas storage
   - Number of errors: 0 hingga tak terhingga

#### Tabel Jenis Data dan Uji yang Sesuai

| Jenis Analisis | Data Nominal | Data Ordinal | Data Interval/Ratio (Normal) | Data Interval/Ratio (Non-Normal) |
|----------------|--------------|--------------|------------------------------|----------------------------------|
| Perbandingan 2 kelompok independen | Chi-square | Mann-Whitney U | Independent t-test | Mann-Whitney U |
| Perbandingan 2 kelompok berpasangan | McNemar's test | Wilcoxon signed-rank | Paired t-test | Wilcoxon signed-rank |
| Perbandingan >2 kelompok independen | Chi-square | Kruskal-Wallis | One-way ANOVA | Kruskal-Wallis |
| Perbandingan >2 kelompok berpasangan | Cochran's Q | Friedman | Repeated measures ANOVA | Friedman |
| Hubungan antara 2 variabel | Phi coefficient | Spearman correlation | Pearson correlation | Spearman correlation |
| Prediksi 1 variabel dari variabel lain | Logistic regression | Ordinal regression | Linear regression | Non-linear regression |
| Reduksi dimensi | Multiple Correspondence Analysis | Non-metric MDS | PCA, Factor Analysis | Non-metric MDS |

### 6.1.4 Distribusi Data dalam Evaluasi Sistem

Pemahaman tentang distribusi data sangat penting dalam evaluasi sistem karena mempengaruhi pemilihan teknik analisis statistik yang tepat dan interpretasi hasil.

#### Normal Distribution dan Central Limit Theorem

**Normal Distribution** (distribusi Gauss) adalah distribusi probabilitas kontinu yang berbentuk lonceng (bell-shaped curve). Karakteristiknya:
- Simetris di sekitar mean
- Mean, median, dan modus sama
- Area di bawah kurva = 1
- Didefinisikan oleh dua parameter: mean (μ) dan standard deviation (σ)

Formula probability density function (PDF) untuk distribusi normal:
```
f(x) = (1 / (σ√(2π))) × e^(-½((x-μ)/σ)²)
```

**Central Limit Theorem (CLT)** menyatakan bahwa distribusi sampling mean akan mendekati distribusi normal ketika ukuran sampel membesar, terlepas dari distribusi populasi asli.

Implikasi CLT:
- Untuk ukuran sampel yang cukup besar (n ≥ 30), distribusi sampling mean akan mendekati normal
- Memungkinkan penggunaan uji parametrik bahkan jika populasi tidak terdistribusi normal, asalkan ukuran sampel cukup besar

#### Skewness dan Kurtosis

**Skewness** mengukur asimetri distribusi data:
- **Skewness positif (right-skewed)**: Ekor distribusi memanjang ke kanan, mean > median > modus
- **Skewness negatif (left-skewed)**: Ekor distribusi memanjang ke kiri, mean < median < modus
- **Skewness = 0**: Distribusi simetris (seperti distribusi normal)

Formula skewness:
```
Skewness = [n/((n-1)(n-2))] × Σ((xᵢ - x̄)/s)³
```

**Kurtosis** mengukur "tailedness" atau puncak distribusi:
- **Kurtosis > 3 (Leptokurtic)**: Distribusi lebih tajam dengan ekor lebih tebal
- **Kurtosis < 3 (Platykurtic)**: Distribusi lebih datar dengan ekor lebih tipis
- **Kurtosis = 3 (Mesokurtic)**: Distribusi normal

Formula kurtosis:
```
Kurtosis = [n(n+1)/((n-1)(n-2)(n-3))] × Σ((xᵢ - x̄)/s)⁴ - [3(n-1)²/((n-2)(n-3))]
```

#### Uji Normalitas

Uji normalitas digunakan untuk menentukan apakah data berasal dari distribusi normal. Beberapa uji normalitas yang umum:

1. **Shapiro-Wilk Test**
   - Cocok untuk ukuran sampel kecil hingga sedang (n < 50)
   - Hipotesis nol: Data terdistribusi normal
   - Formula statistik uji:
     ```
     W = (Σ aᵢxᵢ)² / Σ(xᵢ - x̄)²
     ```
     di mana aᵢ adalah konstanta yang dihasilkan dari mean, varians, dan kovarians dari order statistics dari distribusi normal

2. **Kolmogorov-Smirnov Test**
   - Cocok untuk ukuran sampel besar (n > 50)
   - Membandingkan distribusi kumulatif empiris dengan distribusi kumulatif teoretis
   - Formula statistik uji:
     ```
     D = max|Fₙ(x) - F(x)|
     ```
     di mana Fₙ(x) adalah distribusi kumulatif empiris dan F(x) adalah distribusi kumulatif teoretis

3. **Anderson-Darling Test**
   - Modifikasi dari Kolmogorov-Smirnov yang memberikan bobot lebih pada ekor distribusi
   - Lebih sensitif untuk mendeteksi penyimpangan dari normalitas di ekor distribusi

4. **Q-Q Plot (Quantile-Quantile Plot)**
   - Grafik yang membandingkan kuantil data dengan kuantil distribusi normal
   - Jika data terdistribusi normal, titik-titik akan membentuk garis lurus diagonal

#### Non-normal Distributions dalam Metrik Sistem

Banyak metrik sistem tidak mengikuti distribusi normal. Beberapa distribusi non-normal yang umum dalam evaluasi sistem:

1. **Exponential Distribution**
   - Digunakan untuk memodelkan waktu antar kejadian (inter-arrival times)
   - Memiliki sifat *memoryless*
   - Parameter: λ (rate parameter)
   - PDF: f(x) = λe^(-λx) untuk x ≥ 0
   - Contoh: Waktu antar request ke server, waktu antar failure

2. **Weibull Distribution**
   - Fleksibel untuk memodelkan berbagai pola failure
   - Parameter: shape (k) dan scale (λ)
   - PDF: f(x) = (k/λ)(x/λ)^(k-1)e^(-(x/λ)^k) untuk x ≥ 0
   - Jika k = 1, menjadi distribusi eksponensial
   - Jika k > 1, tingkat failure meningkat seiring waktu
   - Jika k < 1, tingkat failure menurun seiring waktu
   - Contoh: Time to failure komponen sistem, lifetime perangkat

3. **Poisson Distribution**
   - Digunakan untuk memodelkan jumlah kejadian dalam interval waktu tertentu
   - Parameter: λ (rata-rata jumlah kejadian)
   - PMF: P(X = k) = (e^(-λ) × λ^k) / k!
   - Contoh: Jumlah request per detik, jumlah error per jam

4. **Log-normal Distribution**
   - Variabel acak yang logaritmanya terdistribusi normal
   - Berguna untuk data yang selalu positif dan memiliki skewness positif
   - Contoh: Response time, file size, income

#### Contoh: Distribusi Response Time dan Failure Rates

**Distribusi Response Time**:
Response time dalam sistem sering mengikuti distribusi log-normal atau eksponensial, bukan distribusi normal.

Contoh data response time (dalam ms) dari 100 request:
```
[12, 15, 18, 22, 25, 28, 32, 35, 38, 42, 45, 48, 52, 55, 58, 
 62, 65, 68, 72, 75, 78, 82, 85, 88, 92, 95, 98, 102, 105, 108,
 112, 115, 118, 122, 125, 128, 132, 135, 138, 142, 145, 148, 152,
 155, 158, 162, 165, 168, 172, 175, 178, 182, 185, 188, 192, 195,
 198, 202, 205, 208, 212, 215, 218, 222, 225, 228, 232, 235, 238,
 242, 245, 248, 252, 255, 258, 262, 265, 268, 272, 275, 278, 282,
 285, 288, 292, 295, 298, 302, 305, 308, 312, 315, 318, 322, 325]
```

Analisis distribusi:
- Mean = 175.43 ms
- Median = 172.5 ms
- Standard deviation = 93.24 ms
- Skewness = 0.12 (mendekati simetris)
- Kurtosis = 1.78 (platykurtic)

Uji normalitas Shapiro-Wilk:
- W = 0.987
- p-value = 0.542
- Kesimpulan: Gagal menolak hipotesis normalitas (p > 0.05)

**Distribusi Failure Rates**:
Failure rates sering mengikuti distribusi Weibull atau eksponensial.

Contoh data time to failure (dalam jam) dari 50 server:
```
[120, 150, 180, 200, 220, 240, 260, 280, 300, 320, 340, 360, 380,
 400, 420, 440, 460, 480, 500, 520, 540, 560, 580, 600, 620, 640,
 660, 680, 700, 720, 740, 760, 780, 800, 820, 840, 860, 880, 900,
 920, 940, 960, 980, 1000, 1020, 1040, 1060, 1080, 1100]
```

Analisis distribusi:
- Mean = 610 jam
- Median = 610 jam
- Standard deviation = 283.01 jam
- Skewness = 0 (simetris)

Uji distribusi eksponensial:
- Parameter λ = 1/mean = 1/610 = 0.00164
- Kolmogorov-Smirnov test: D = 0.088, p-value = 0.832
- Kesimpulan: Data mengikuti distribusi eksponensial (p > 0.05)

#### Visualisasi: Kurva Distribusi Normal dengan Anotasi

```
      ^
      |
      |                  ****
      |                **    **
      |               *        *
      |              *          *
      |             *            *
      |            *              *
      |           *                *
      |          *                  *
      |         *                    *
      |        *                      *
      |       *                        *
      |      *                          *
      |     *                            *
      |    *                              *
      |   *                                *
      |  *                                  *
      | *                                    *
      |*                                      *
------+----------------------------------------*---->
      |                μ-3σ   μ-σ   μ   μ+σ   μ+3σ
      |
      |  Area di bawah kurva:
      |  μ ± 1σ = 68.27%
      |  μ ± 2σ = 95.45%
      |  μ ± 3σ = 99.73%
```

#### Visualisasi: Contoh Output Uji Normalitas

**Output Shapiro-Wilk Test dalam R:**
```r
> shapiro.test(response_time)

	Shapiro-Wilk normality test

data:  response_time
W = 0.987, p-value = 0.542
```

**Interpretasi:**
- W = 0.987 (mendekati 1, mengindikasikan normalitas)
- p-value = 0.542 > 0.05, sehingga gagal menolak hipotesis nol
- Kesimpulan: Data response time terdistribusi normal

**Output Q-Q Plot dalam R:**
```
      ^
      |                                   *
      |                                 *
      |                               *
      |                             *
      |                           *
      |                         *
      |                       *
      |                     *
      |                   *
      |                 *
      |               *
      |             *
      |           *
      |         *
      |       *
      |     *
      |   *
      | *
------+----------------------------------------*---->
      -3        -2        -1         0         1
      Theoretical Quantiles
```

**Interpretasi:**
- Titik-titik mengikuti garis referensi diagonal
- Tidak ada penyimpangan sistematis dari garis
- Kesimpulan: Data mengikuti distribusi normal

## 6.2 Uji Hipotesis

Uji hipotesis adalah prosedur statistik yang digunakan untuk membuat keputusan tentang populasi berdasarkan data sampel. Dalam evaluasi sistem, uji hipotesis digunakan untuk menentukan apakah ada perbedaan signifikan dalam performa sistem, efektivitas algoritma, atau pengaruh intervensi tertentu.

### 6.2.1 Formulasi Hipotesis

#### 6.2.1.1 Hipotesis Nol dan Alternatif

**Hipotesis Nol (H₀)** adalah pernyataan bahwa tidak ada efek atau perbedaan. Ini adalah asumsi default yang diuji. Dalam konteks evaluasi sistem, hipotesis nol menyatakan bahwa tidak ada perbedaan performa antara sistem yang dibandingkan atau tidak ada pengaruh dari perubahan yang dilakukan.

Contoh hipotesis nol dalam evaluasi sistem:
- H₀: Tidak ada perbedaan signifikan dalam response time antara algoritma A dan algoritma B
- H₀: Implementasi caching tidak mempengaruhi throughput sistem
- H₀: Tidak ada hubungan antara CPU usage dan response time

**Hipotesis Alternatif (H₁ atau Hₐ)** adalah pernyataan yang bertentangan dengan hipotesis nol. Ini menyatakan adanya efek atau perbedaan.

Contoh hipotesis alternatif dalam evaluasi sistem:
- H₁: Terdapat perbedaan signifikan dalam response time antara algoritma A dan algoritma B
- H₁: Implementasi caching mempengaruhi throughput sistem
- H₁: Terdapat hubungan antara CPU usage dan response time

#### 6.2.1.2 One-tailed vs Two-tailed Tests

**Two-tailed Test** digunakan ketika hipotesis alternatif tidak menentukan arah perbedaan. Ini menguji kemungkinan perbedaan dalam kedua arah (lebih besar atau lebih kecil).

Contoh:
- H₀: μ₁ = μ₂ (tidak ada perbedaan mean response time)
- H₁: μ₁ ≠ μ₂ (ada perbedaan mean response time)

**One-tailed Test** digunakan ketika hipotesis alternatif menentukan arah perbedaan. Ini menguji kemungkinan perbedaan hanya dalam satu arah.

Contoh:
- H₀: μ₁ ≤ μ₂ (response time algoritma A tidak lebih cepat dari algoritma B)
- H₁: μ₁ > μ₂ (response time algoritma A lebih cepat dari algoritma B)

Pemilihan antara one-tailed dan two-tailed test bergantung pada:
- Pertanyaan penelitian
- Pengetahuan teoretis sebelumnya
- Arah efek yang diharapkan

#### 6.2.1.3 Kesalahan Tipe I dan II

**Kesalahan Tipe I (Type I Error)** terjadi ketika kita menolak hipotesis nol yang sebenarnya benar. Dalam konteks evaluasi sistem, ini berarti kita menyimpulkan bahwa ada perbedaan atau efek padahal sebenarnya tidak ada.

- Probabilitas Kesalahan Tipe I = α (tingkat signifikansi)
- Contoh: Menyimpulkan bahwa algoritma baru lebih baik padahal sebenarnya tidak ada perbedaan

**Kesalahan Tipe II (Type II Error)** terjadi ketika kita gagal menolak hipotesis nol yang sebenarnya salah. Dalam konteks evaluasi sistem, ini berarti kita gagal mendeteksi perbedaan atau efek yang sebenarnya ada.

- Probabilitas Kesalahan Tipe II = β
- Power of the test = 1 - β (probabilitas secara benar menolak hipotesis nol)
- Contoh: Gagal mendeteksi bahwa algoritma baru lebih baik padahal sebenarnya lebih baik

#### Trade-off antara α dan β

Ada trade-off antara Kesalahan Tipe I dan Kesalahan Tipe II:
- Mengurangi α (misalnya dari 0.05 menjadi 0.01) akan meningkatkan β (mengurangi power)
- Meningkatkan α (misalnya dari 0.05 menjadi 0.10) akan mengurangi β (meningkatkan power)

Untuk mengurangi kedua jenis kesalahan secara simultan, perlu meningkatkan ukuran sampel.

#### Contoh Praktis dengan Data Sampel

Sebuah perusahaan ingin menguji apakah optimasi database meningkatkan performa query. Mereka mengukur waktu eksekusi query (dalam ms) sebelum dan sesudah optimasi.

**Data:**
- Sebelum optimasi (n=25): Mean = 120ms, SD = 15ms
- Setelah optimasi (n=25): Mean = 105ms, SD = 12ms

**Formulasi Hipotesis:**
- H₀: μ_sebelum = μ_sesudah (tidak ada perbedaan waktu eksekusi query)
- H₁: μ_sebelum > μ_sesudah (optimasi mengurangi waktu eksekusi query)

**Pemilihan Uji:**
- One-tailed independent t-test (karena kita menguji arah spesifik: optimasi mengurangi waktu eksekusi)

**Perhitungan:**
```
t = (M₁ - M₂) / √((s₁²/n₁) + (s₂²/n₂))
  = (120 - 105) / √((15²/25) + (12²/25))
  = 15 / √((225/25) + (144/25))
  = 15 / √(9 + 5.76)
  = 15 / √14.76
  = 15 / 3.84
  = 3.91
```

Dengan df = n₁ + n₂ - 2 = 48, critical value untuk α = 0.05 (one-tailed) = 1.677.

**Keputusan:**
- t = 3.91 > 1.677, sehingga menolak H₀
- p-value < 0.001 (sangat signifikan)

**Interpretasi:**
- Terdapat bukti statistik yang signifikan bahwa optimasi database mengurangi waktu eksekusi query (t(48) = 3.91, p < 0.001)
- Waktu eksekusi query rata-rata berkurang dari 120ms menjadi 105ms (penurunan 12.5%)

**Analisis Kesalahan:**
- Risiko Kesalahan Tipe I (α) = 5% (risiko menyimpulkan optimasi efektif padahal tidak)
- Power (1-β) ≈ 90% (probabilitas mendeteksi efek jika memang ada)
- Risiko Kesalahan Tipe II (β) ≈ 10% (risiko gagal mendeteksi efek optimasi jika memang ada)

### 6.2.2 Uji Parametrik

Uji parametrik adalah uji statistik yang mengasumsikan data berasal dari distribusi tertentu (biasanya distribusi normal) dan memiliki parameter tertentu (seperti mean dan standard deviation). Uji parametrik umumnya lebih powerful daripada uji non-parametrik jika asumsinya terpenuhi.

#### 6.2.2.1 Uji-t (Independent dan Paired)

**Uji-t** digunakan untuk membandingkan mean antara dua kelompok. Ada dua jenis utama uji-t: independent t-test dan paired t-test.

**Independent t-test** digunakan untuk membandingkan mean dari dua kelompok independen (tidak berpasangan).

**Asumsi Independent t-test:**
1. Normalitas: Data di setiap kelompok terdistribusi normal
2. Homogenitas varians: Varians kedua kelompok sama
3. Independensi: Observasi dalam setiap kelompok independen satu sama lain

**Formula Independent t-test:**
```
t = (M₁ - M₂) / √((s₁²/n₁) + (s₂²/n₂))
```
di mana:
- M₁, M₂ = mean kelompok 1 dan 2
- s₁², s₂² = varians kelompok 1 dan 2
- n₁, n₂ = ukuran sampel kelompok 1 dan 2

**Derajat kebebasan (df)** untuk independent t-test:
- Jika varians homogen: df = n₁ + n₂ - 2
- Jika varians tidak homogen (Welch's t-test): df = (s₁²/n₁ + s₂²/n₂)² / ((s₁²/n₁)²/(n₁-1) + (s₂²/n₂)²/(n₂-1))

**Paired t-test** digunakan untuk membandingkan mean dari dua pengukuran yang berpasangan (misalnya, sebelum dan sesudah intervensi pada subjek yang sama).

**Asumsi Paired t-test:**
1. Normalitas: Selisih pasangan data terdistribusi normal
2. Independensi: Pasangan data independen satu sama lain

**Formula Paired t-test:**
```
t = M_d / (s_d / √n)
```
di mana:
- M_d = mean selisih pasangan data
- s_d = standard deviation selisih pasangan data
- n = jumlah pasangan data

**Derajat kebebasan (df)** untuk paired t-test: df = n - 1

**Interpretasi Hasil Uji-t:**
- **t-statistic**: Mengukur besarnya perbedaan antara kelompok dalam satuan standard error
- **p-value**: Probabilitas mendapatkan t-statistic yang sama atau lebih ekstrem jika H₀ benar
- **Confidence interval**: Rentang nilai yang mungkin berisi perbedaan populasi sebenarnya

**Contoh: Membandingkan CPU Usage antara Dua Algoritma Berbeda**

Sebuah perusahaan ingin membandingkan CPU usage dari dua algoritma load balancing yang berbeda. Mereka mengukur CPU usage (dalam persen) untuk setiap algoritma pada 10 server yang berbeda.

**Data:**
- Algoritma A: [45, 52, 48, 50, 47, 53, 49, 51, 46, 54]
- Algoritma B: [38, 42, 40, 41, 39, 43, 41, 42, 37, 44]

**Langkah-langkah Analisis:**

1. **Hitung Statistik Deskriptif:**
   - Algoritma A: Mean = 49.5%, SD = 2.95%
   - Algoritma B: Mean = 40.7%, SD = 2.16%

2. **Uji Asumsi Normalitas (Shapiro-Wilk):**
   - Algoritma A: W = 0.96, p = 0.78 (normal)
   - Algoritma B: W = 0.94, p = 0.56 (normal)

3. **Uji Homogenitas Varians (Levene's Test):**
   - F = 1.24, p = 0.28 (varians homogen)

4. **Lakukan Independent t-test:**
   ```
   t = (M₁ - M₂) / √((s₁²/n₁) + (s₂²/n₂))
     = (49.5 - 40.7) / √((2.95²/10) + (2.16²/10))
     = 8.8 / √((8.70/10) + (4.67/10))
     = 8.8 / √(0.87 + 0.47)
     = 8.8 / √1.34
     = 8.8 / 1.16
     = 7.59
   ```
   df = n₁ + n₂ - 2 = 10 + 10 - 2 = 18
   Critical value (α = 0.05, two-tailed) = ±2.101

5. **Interpretasi Hasil:**
   - t(18) = 7.59, p < 0.001
   - Menolak H₀, terdapat perbedaan signifikan dalam CPU usage antara algoritma A dan B
   - Algoritma B memiliki CPU usage rata-rata lebih rendah (40.7%) dibandingkan algoritma A (49.5%)
   - Effect size (Cohen's d) = (49.5 - 40.7) / √((2.95² + 2.16²)/2) = 8.8 / 2.61 = 3.37 (effect size sangat besar)

**Output Software: Contoh Output SPSS dengan Interpretasi**

```
Independent Samples Test

                     Levene's Test      t-test for Equality of Means
        F       Sig.        t       df    Sig. (2-tailed)   Mean Difference   Std. Error Difference   95% Confidence Interval
                                                                                              Lower       Upper
CPU_Usage   Equal variances assumed   1.240    .280      7.590     18          .000              8.800             1.160          6.360       11.240
            Equal variances not assumed                  7.590    16.580        .000              8.800             1.160          6.352       11.248
```

**Interpretasi Output SPSS:**
- Levene's Test: F = 1.24, p = 0.28 > 0.05, sehingga asumsi homogenitas varians terpenuhi
- Menggunakan baris "Equal variances assumed": t(18) = 7.59, p < 0.001
- Mean Difference = 8.8% (Algoritma A memiliki CPU usage 8.8% lebih tinggi dari Algoritma B)
- 95% Confidence Interval: [6.36%, 11.24%], artinya kita 95% yakin bahwa perbedaan CPU usage populasi berada dalam rentang ini

#### 6.2.2.2 Uji-z

**Uji-z** digunakan untuk membandingkan mean atau proporsi dengan nilai populasi yang diketahui atau antara dua kelompok ketika ukuran sampel besar (n ≥ 30) dan standar deviasi populasi diketahui.

**Z-test untuk Mean (σ diketahui):**
```
z = (M - μ) / (σ/√n)
```
di mana:
- M = mean sampel
- μ = mean populasi
- σ = standar deviasi populasi
- n = ukuran sampel

**Z-test untuk Proporsi:**
```
z = (p̂ - p) / √(p(1-p)/n)
```
di mana:
- p̂ = proporsi sampel
- p = proporsi populasi
- n = ukuran sampel

**Z-test untuk Dua Proporsi:**
```
z = (p̂₁ - p̂₂) / √(p̂(1-p̂)(1/n₁ + 1/n₂))
```
di mana:
- p̂₁, p̂₂ = proporsi sampel kelompok 1 dan 2
- p̂ = (x₁ + x₂) / (n₁ + n₂) = proporsi gabungan
- x₁, x₂ = jumlah keberhasilan dalam kelompok 1 dan 2
- n₁, n₂ = ukuran sampel kelompok 1 dan 2

**Contoh: Testing Proportion of Successful Transactions**

Sebuah e-commerce ingin menguji apakah sistem pembayaran baru memiliki tingkat keberhasilan transaksi yang berbeda dari sistem lama. Diketahui bahwa sistem lama memiliki tingkat keberhasilan 95%. Dari 1000 transaksi dengan sistem baru, 970 berhasil.

**Formulasi Hipotesis:**
- H₀: p = 0.95 (tingkat keberhasilan sistem baru sama dengan sistem lama)
- H₁: p ≠ 0.95 (tingkat keberhasilan sistem baru berbeda dari sistem lama)

**Perhitungan:**
```
p̂ = 970/1000 = 0.97
z = (p̂ - p) / √(p(1-p)/n)
  = (0.97 - 0.95) / √(0.95×0.05/1000)
  = 0.02 / √(0.0475/1000)
  = 0.02 / √0.0000475
  = 0.02 / 0.00689
  = 2.90
```

**Interpretasi:**
- Critical value untuk α = 0.05 (two-tailed) = ±1.96
- z = 2.90 > 1.96, sehingga menolak H₀
- p-value = 0.0037 < 0.05
- Kesimpulan: Terdapat perbedaan signifikan dalam tingkat keberhasilan transaksi antara sistem baru dan sistem lama
- Sistem baru memiliki tingkat keberhasilan lebih tinggi (97%) dibandingkan sistem lama (95%)

#### 6.2.2.3 Uji Chi-Square

**Uji Chi-Square (χ²)** digunakan untuk menguji hubungan antara variabel kategorikal. Ada dua jenis utama uji Chi-Square: Chi-Square Test of Independence dan Chi-Square Goodness of Fit Test.

**Chi-Square Test of Independence** digunakan untuk menentukan apakah ada hubungan antara dua variabel kategorikal.

**Formula Chi-Square Test of Independence:**
```
χ² = Σ((O - E)² / E)
```
di mana:
- O = frekuensi observasi
- E = frekuensi ekspektasi (expected frequency)
- E = (total baris × total kolom) / total grand

**Derajat kebebasan (df)** untuk Chi-Square Test of Independence: df = (r - 1) × (c - 1), di mana r = jumlah baris, c = jumlah kolom

**Chi-Square Goodness of Fit Test** digunakan untuk menentukan apakah distribusi frekuensi observasi sesuai dengan distribusi ekspektasi.

**Formula Chi-Square Goodness of Fit Test:**
```
χ² = Σ((O - E)² / E)
```
di mana:
- O = frekuensi observasi
- E = frekuensi ekspektasi

**Derajat kebebasan (df)** untuk Chi-Square Goodness of Fit Test: df = k - 1, di mana k = jumlah kategori

**Contingency Table Analysis** adalah analisis tabel yang menunjukkan distribusi frekuensi dua variabel kategorikal.

**Contoh: Hubungan antara Browser Type dan Error Rate**

Sebuah perusahaan ingin mengetahui apakah ada hubungan antara jenis browser yang digunakan dan tingkat error yang dialami pengguna. Mereka mengumpulkan data dari 1000 sesi pengguna.

**Data:**
| Browser | Error | No Error | Total |
|---------|-------|----------|-------|
| Chrome  | 45    | 355      | 400   |
| Firefox | 30    | 220      | 250   |
| Safari  | 25    | 175      | 200   |
| Edge    | 20    | 130      | 150   |
| Total   | 120   | 880      | 1000  |

**Langkah-langkah Analisis:**

1. **Hitung Frekuensi Ekspektasi (E):**
   - E_Chrome_Error = (400 × 120) / 1000 = 48
   - E_Chrome_NoError = (400 × 880) / 1000 = 352
   - E_Firefox_Error = (250 × 120) / 1000 = 30
   - E_Firefox_NoError = (250 × 880) / 1000 = 220
   - E_Safari_Error = (200 × 120) / 1000 = 24
   - E_Safari_NoError = (200 × 880) / 1000 = 176
   - E_Edge_Error = (150 × 120) / 1000 = 18
   - E_Edge_NoError = (150 × 880) / 1000 = 132

2. **Hitung Chi-Square:**
   ```
   χ² = ((45-48)²/48) + ((355-352)²/352) + ((30-30)²/30) + ((220-220)²/220) +
        ((25-24)²/24) + ((175-176)²/176) + ((20-18)²/18) + ((130-132)²/132)
      = (9/48) + (9/352) + (0/30) + (0/220) + (1/24) + (1/176) + (4/18) + (4/132)
      = 0.1875 + 0.0256 + 0 + 0 + 0.0417 + 0.0057 + 0.2222 + 0.0303
      = 0.513
   ```

3. **Tentukan Derajat Kebebasan:**
   - df = (r - 1) × (c - 1) = (4 - 1) × (2 - 1) = 3 × 1 = 3

4. **Interpretasi Hasil:**
   - Critical value untuk α = 0.05 dan df = 3 adalah 7.815
   - χ² = 0.513 < 7.815, sehingga gagal menolak H₀
   - p-value = 0.915 > 0.05
   - Kesimpulan: Tidak ada hubungan signifikan antara jenis browser dan tingkat error

**Output Software: Contoh Output R dengan Interpretasi**

```r
> browser_data <- matrix(c(45, 30, 25, 20, 355, 220, 175, 130), nrow=4, byrow=TRUE)
> rownames(browser_data) <- c("Chrome", "Firefox", "Safari", "Edge")
> colnames(browser_data) <- c("Error", "No Error")
> chisq.test(browser_data)

	Pearson's Chi-squared test

data:  browser_data
X-squared = 0.513, df = 3, p-value = 0.915
```

**Interpretasi Output R:**
- χ² = 0.513, df = 3, p-value = 0.915
- p-value > 0.05, sehingga gagal menolak hipotesis nol
- Kesimpulan: Tidak ada bukti statistik yang cukup untuk menyimpulkan adanya hubungan antara jenis browser dan tingkat error

### 6.2.3 Uji Non-Parametrik

Uji non-parametrik adalah uji statistik yang tidak mengasumsikan data berasal dari distribusi tertentu. Uji ini digunakan ketika asumsi untuk uji parametrik tidak terpenuhi, seperti ketika data tidak terdistribusi normal, ukuran sampel kecil, atau data berskala ordinal.

#### Kapan Menggunakan Non-Parametrik

Uji non-parametrik digunakan dalam situasi berikut:
1. Data tidak terdistribusi normal dan ukuran sampel kecil (n < 30)
2. Data berskala ordinal
3. Data memiliki outlier yang signifikan
4. Asumsi homogenitas varians tidak terpenuhi
5. Ukuran sampel sangat kecil

**Keuntungan Uji Non-Parametrik:**
- Tidak memerlukan asumsi tentang distribusi data
- Lebih robust terhadap outlier
- Dapat digunakan untuk data ordinal

**Kerugian Uji Non-Parametrik:**
- Kurang powerful daripada uji parametrik jika asumsinya terpenuhi
- Umumnya memerlukan ukuran sampel lebih besar untuk mendeteksi efek yang sama
- Informasi tentang besarnya efek terbatas

#### 6.2.3.1 Uji Mann-Whitney U Test

**Mann-Whitney U Test** (juga dikenal sebagai Wilcoxon Rank-Sum Test) adalah uji non-parametrik yang digunakan untuk membandingkan dua kelompok independen. Ini adalah alternatif untuk independent t-test ketika asumsi normalitas tidak terpenuhi.

**Asumsi Mann-Whitney U Test:**
1. Data berskala ordinal, interval, atau ratio
2. Observasi independen antar kelompok
3. Distribusi kedua kelompok memiliki bentuk yang sama

**Langkah-langkah Mann-Whitney U Test:**
1. Gabungkan data dari kedua kelompok dan beri peringkat (rank)
2. Jika ada nilai yang sama, beri peringkat rata-rata
3. Hitung jumlah peringkat untuk setiap kelompok (R₁ dan R₂)
4. Hitung statistik U untuk setiap kelompok:
   ```
   U₁ = R₁ - n₁(n₁ + 1)/2
   U₂ = R₂ - n₂(n₂ + 1)/2
   ```
   di mana n₁ dan n₂ adalah ukuran sampel kelompok 1 dan 2
5. Statistik uji adalah nilai U yang lebih kecil
6. Bandingkan dengan nilai kritis atau hitung p-value

**Contoh: Membandingkan User Satisfaction Ratings (Ordinal Data)**

Sebuah perusahaan ingin membandingkan kepuasan pengguna antara dua versi UI aplikasi mobile. Kepuasan diukur menggunakan skala Likert 1-5 (1 = Sangat Tidak Puas, 5 = Sangat Puas).

**Data:**
- UI Lama (n=12): [3, 4, 2, 3, 4, 3, 2, 4, 3, 4, 3, 2]
- UI Baru (n=12): [4, 5, 3, 4, 5, 4, 3, 5, 4, 5, 4, 3]

**Langkah-langkah Analisis:**

1. **Gabungkan dan Beri Peringkat:**
   ```
   Data Gabungan: [2, 2, 2, 3, 3, 3, 3, 3, 3, 3, 3, 4, 4, 4, 4, 4, 4, 4, 4, 4, 5, 5, 5, 5]
   Peringkat:    [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24]
   ```

2. **Hitung Jumlah Peringkat:**
   - UI Lama: R₁ = 1 + 2 + 3 + 4 + 5 + 6 + 7 + 8 + 12 + 13 + 14 + 15 = 90
   - UI Baru: R₂ = 9 + 10 + 11 + 16 + 17 + 18 + 19 + 20 + 21 + 22 + 23 + 24 = 210

3. **Hitung Statistik U:**
   ```
   U₁ = R₁ - n₁(n₁ + 1)/2 = 90 - 12×13/2 = 90 - 78 = 12
   U₂ = R₂ - n₂(n₂ + 1)/2 = 210 - 12×13/2 = 210 - 78 = 132
   ```
   Statistik uji = min(U₁, U₂) = 12

4. **Interpretasi Hasil:**
   - Critical value untuk n₁ = 12, n₂ = 12, α = 0.05 (two-tailed) = 37
   - U = 12 < 37, sehingga menolak H₀
   - p-value < 0.001
   - Kesimpulan: Terdapat perbedaan signifikan dalam kepuasan pengguna antara UI lama dan UI baru
   - UI baru memiliki peringkat rata-rata lebih tinggi (17.5) dibandingkan UI lama (7.5)

**Output Software: Contoh Output SPSS dengan Interpretasi**

```
Mann-Whitney U Test

Ranks
        UI       N    Mean Rank    Sum of Ranks
Rating  Lama     12      7.50          90.00
        Baru     12     17.50         210.00
        Total    24

Test Statistics
                     Rating
Mann-Whitney U        12.000
Wilcoxon W            90.000
Z                    -3.464
Asymp. Sig. (2-tailed)  .001
```

**Interpretasi Output SPSS:**
- Mann-Whitney U = 12.000
- Z = -3.464
- p-value = 0.001 < 0.05
- Kesimpulan: Terdapat perbedaan signifikan dalam kepuasan pengguna antara UI lama dan UI baru
- UI baru memiliki peringkat rata-rata lebih tinggi (17.5) dibandingkan UI lama (7.5)

#### 6.2.3.2 Uji Wilcoxon Signed-Rank Test

**Wilcoxon Signed-Rank Test** adalah uji non-parametrik yang digunakan untuk membandingkan dua kelompok berpasangan. Ini adalah alternatif untuk paired t-test ketika asumsi normalitas tidak terpenuhi.

**Asumsi Wilcoxon Signed-Rank Test:**
1. Data berskala ordinal, interval, atau ratio
2. Pasangan data dependen
3. Distribusi selisih simetris di sekitar median

**Langkah-langkah Wilcoxon Signed-Rank Test:**
1. Hitung selisih untuk setiap pasangan (d = X₁ - X₂)
2. Abaikan selisih yang sama dengan nol
3. Beri peringkat absolut selisih dari terkecil hingga terbesar
4. Beri tanda (+) pada peringkat untuk selisih positif dan tanda (-) untuk selisih negatif
5. Hitung jumlah peringkat positif (W⁺) dan jumlah peringkat negatif (W⁻)
6. Statistik uji adalah nilai yang lebih kecil antara W⁺ dan W⁻
7. Bandingkan dengan nilai kritis atau hitung p-value

**Contoh: Membandingkan Error Rates Sebelum dan Sesudah Patch**

Sebuah perusahaan ingin mengetahui apakah patch keamanan mengurangi error rate pada sistem. Mereka mengukur error rate (error per jam) pada 10 server sebelum dan sesudah implementasi patch.

**Data:**
| Server | Sebelum Patch | Sesudah Patch | Selisih | |Selisih| | Peringkat | Peringkat Bertanda |
|--------|---------------|---------------|---------|----------|-----------|-------------------|
| 1      | 12            | 8             | 4       | 4        | 7         | +7                |
| 2      | 15            | 10            | 5       | 5        | 8.5       | +8.5              |
| 3      | 8             | 6             | 2       | 2        | 3         | +3                |
| 4      | 10            | 9             | 1       | 1        | 1         | +1                |
| 5      | 14            | 12            | 2       | 2        | 3         | +3                |
| 6      | 18            | 15            | 3       | 3        | 5         | +5                |
| 7      | 9             | 7             | 2       | 2        | 3         | +3                |
| 8      | 11            | 10            | 1       | 1        | 1         | +1                |
| 9      | 13            | 11            | 2       | 2        | 3         | +3                |
| 10     | 16            | 14            | 2       | 2        | 3         | +3                |

**Langkah-langkah Analisis:**

1. **Hitung Jumlah Peringkat Bertanda:**
   - W⁺ = 7 + 8.5 + 3 + 1 + 3 + 5 + 3 + 1 + 3 + 3 = 37.5
   - W⁻ = 0

2. **Statistik Uji:**
   - W = min(W⁺, W⁻) = min(37.5, 0) = 0

3. **Interpretasi Hasil:**
   - Critical value untuk n = 10, α = 0.05 (one-tailed) = 10
   - W = 0 < 10, sehingga menolak H₀
   - p-value < 0.005
   - Kesimpulan: Patch keamanan secara signifikan mengurangi error rate

**Output Software: Contoh Output R dengan Interpretasi**

```r
> before <- c(12, 15, 8, 10, 14, 18, 9, 11, 13, 16)
> after <- c(8, 10, 6, 9, 12, 15, 7, 10, 11, 14)
> wilcox.test(before, after, paired = TRUE, alternative = "greater")

	Wilcoxon signed rank test with continuity correction

data:  before and after
V = 55, p-value = 0.001953
alternative hypothesis: true location shift is greater than 0
```

**Interpretasi Output R:**
- V = 55 (setara dengan W⁺)
- p-value = 0.001953 < 0.05
- Kesimpulan: Terdapat bukti statistik yang signifikan bahwa patch keamanan mengurangi error rate

#### 6.2.3.3 Uji Kruskal-Wallis

**Kruskal-Wallis Test** adalah uji non-parametrik yang digunakan untuk membandingkan lebih dari dua kelompok independen. Ini adalah alternatif untuk one-way ANOVA ketika asumsi normalitas tidak terpenuhi.

**Asumsi Kruskal-Wallis Test:**
1. Data berskala ordinal, interval, atau ratio
2. Observasi independen antar kelompok
3. Distribusi kelompok memiliki bentuk yang sama

**Formula Kruskal-Wallis Test:**
```
H = (12 / (N(N + 1))) × Σ(Rᵢ²/nᵢ) - 3(N + 1)
```
di mana:
- N = total ukuran sampel
- Rᵢ = jumlah peringkat untuk kelompok i
- nᵢ = ukuran sampel untuk kelompok i

**Derajat kebebasan (df)** untuk Kruskal-Wallis Test: df = k - 1, di mana k = jumlah kelompok

**Contoh: Membandingkan Load Time Across 4 Different Server Configurations**

Sebuah perusahaan ingin membandingkan load time (dalam detik) dari 4 konfigurasi server yang berbeda. Mereka mengukur load time untuk setiap konfigurasi.

**Data:**
- Konfigurasi A: [1.2, 1.5, 1.3, 1.4, 1.6]
- Konfigurasi B: [2.1, 2.3, 2.0, 2.2, 2.4]
- Konfigurasi C: [1.8, 1.9, 1.7, 2.0, 1.8]
- Konfigurasi D: [1.0, 1.1, 0.9, 1.2, 1.1]

**Langkah-langkah Analisis:**

1. **Gabungkan dan Beri Peringkat:**
   ```
   Data Gabungan: [0.9, 1.0, 1.1, 1.1, 1.2, 1.2, 1.3, 1.4, 1.5, 1.6, 1.7, 1.8, 1.8, 1.9, 2.0, 2.0, 2.1, 2.2, 2.3, 2.4]
   Peringkat:    [1,   2,   3.5, 3.5, 5.5, 5.5, 7,   8,   9,   10,  11,  12.5, 12.5, 14,  15.5, 15.5, 17,  18,  19,  20]
   ```

2. **Hitung Jumlah Peringkat untuk Setiap Kelompok:**
   - Konfigurasi A: R₁ = 5.5 + 7 + 9 + 10 + 12.5 = 44
   - Konfigurasi B: R₂ = 15.5 + 17 + 18 + 19 + 20 = 89.5
   - Konfigurasi C: R₃ = 11 + 12.5 + 14 + 15.5 + 12.5 = 65.5
   - Konfigurasi D: R₄ = 1 + 2 + 3.5 + 5.5 + 3.5 = 15.5

3. **Hitung Statistik H:**
   ```
   N = 20
   H = (12 / (20(20 + 1))) × ((44²/5) + (89.5²/5) + (65.5²/5) + (15.5²/5)) - 3(20 + 1)
     = (12 / 420) × ((1936/5) + (8010.25/5) + (4290.25/5) + (240.25/5)) - 63
     = 0.02857 × (387.2 + 1602.05 + 858.05 + 48.05) - 63
     = 0.02857 × 2895.35 - 63
     = 82.72 - 63
     = 19.72
   ```

4. **Tentukan Derajat Kebebasan:**
   - df = k - 1 = 4 - 1 = 3

5. **Interpretasi Hasil:**
   - Critical value untuk df = 3, α = 0.05 adalah 7.815
   - H = 19.72 > 7.815, sehingga menolak H₀
   - p-value < 0.001
   - Kesimpulan: Terdapat perbedaan signifikan dalam load time antara keempat konfigurasi server

**Output Software: Contoh Output SPSS dengan Interpretasi**

```
Kruskal-Wallis Test

Ranks
        Konfigurasi    N    Mean Rank
Load    A               5      8.80
Time    B               5     17.90
        C               5     13.10
        D               5      3.10
        Total          20

Test Statistics
                     Load Time
Chi-Square            19.720
df                        3
Asymp. Sig.           .000
```

**Interpretasi Output SPSS:**
- H = 19.720 (dilaporkan sebagai Chi-Square)
- df = 3
- p-value < 0.001
- Kesimpulan: Terdapat perbedaan signifikan dalam load time antara keempat konfigurasi server
- Konfigurasi D memiliki peringkat rata-rata terendah (3.10), menunjukkan load time tercepat
- Konfigurasi B memiliki peringkat rata-rata tertinggi (17.90), menunjukkan load time terlama

### 6.2.4 Aplikasi Uji Hipotesis dalam Evaluasi Sistem

#### Decision Framework: Flowchart untuk Pemilihan Uji

Berikut adalah flowchart untuk membantu pemilihan uji statistik yang tepat dalam evaluasi sistem:

```
┌─────────────────────────────────────────────────────────────┐
│                    Mulai Analisis                           │
└─────────────────────┬───────────────────────────────────────┘
                      │
                      ▼
┌─────────────────────────────────────────────────────────────┐
│               Berapa banyak kelompok?                      │
└─────────────────────┬───────────────────────────────────────┘
                      │
          ┌───────────┴───────────┐
          │                       │
          ▼                       ▼
┌─────────────────┐      ┌─────────────────┐
│    2 Kelompok   │      │   >2 Kelompok   │
└────────┬────────┘      └────────┬────────┘
         │                       │
         ▼                       ▼
┌─────────────────┐      ┌─────────────────┐
│  Independen?    │      │  Independen?    │
└────────┬────────┘      └────────┬────────┘
         │                       │
    ┌────┴────┐           ┌──────┴──────┐
    │         │           │             │
    ▼         ▼           ▼             ▼
┌─────────┐ ┌─────────┐ ┌─────────┐   ┌─────────┐
│   Ya    │ │   Tidak │ │   Ya    │   │  Tidak  │
└────┬────┘ └────┬────┘ └────┬────┘   └────┬────┘
     │          │          │              │
     ▼          ▼          ▼              ▼
┌─────────┐ ┌─────────┐ ┌─────────┐   ┌─────────┐
│Data     │ │Data     │ │Data     │   │Data     │
│Normal?  │ │Normal?  │ │Normal?  │   │Normal?  │
└────┬────┘ └────┬────┘ └────┬────┘   └────┬────┘
     │          │          │              │
 ┌───┴───┐  ┌───┴───┐  ┌───┴───┐    ┌───┴───┐
 │   Ya  │  │  Tidak│  │   Ya  │    │  Tidak│
 └───┬───┘  └───┬───┘  └───┬───┘    └───┬───┘
     │          │          │              │
     ▼          ▼          ▼              ▼
┌─────────┐ ┌─────────┐ ┌─────────┐   ┌─────────┐
│t-test   │ │Mann-    │ │ANOVA    │   │Kruskal- │
│(inde-   │ │Whitney  │ │         │   │Wallis   │
│pendent) │ │U Test   │ │         │   │         │
└─────────┘ └─────────┘ └─────────┘   └─────────┘
     │          │          │              │
     ▼          ▼          ▼              ▼
┌─────────┐ ┌─────────┐ ┌─────────┐   ┌─────────┐
│t-test   │ │Wilcoxon │ │Repeated │   │Friedman │
│(paired) │ │Signed-  │ │Measures │   │Test     │
│         │ │Rank     │ │ANOVA    │   │         │
└─────────┘ └─────────┘ └─────────┘   └─────────┘
```

#### Studi Kasus Lengkap: Evaluasi Efektivitas 3 Load Balancing Algorithms

**Latar Belakang:**
Sebuah perusahaan e-commerce ingin mengevaluasi efektivitas tiga algoritma load balancing yang berbeda: Round Robin (RR), Least Connections (LC), dan Weighted Round Robin (WRR). Mereka mengukur response time (dalam ms) untuk setiap algoritma dengan 1000 request untuk setiap algoritma.

**Data Collection Process:**
1. Setup lingkungan pengujian yang identik untuk ketiga algoritma
2. Generate 1000 request untuk setiap algoritma
3. Catat response time untuk setiap request
4. Ulangi pengujian 5 kali untuk memastikan konsistensi

**Data Sampel:**
- Round Robin (RR): Mean = 45ms, SD = 12ms, n = 1000
- Least Connections (LC): Mean = 38ms, SD = 10ms, n = 1000
- Weighted Round Robin (WRR): Mean = 42ms, SD = 11ms, n = 1000

**Pemilihan Uji Statistik:**
1. Jumlah kelompok: 3 (RR, LC, WRR)
2. Jenis kelompok: Independen
3. Jenis data: Numerik (response time dalam ms)
4. Uji normalitas: Shapiro-Wilk (p > 0.05 untuk semua kelompok)
5. Uji homogenitas varians: Levene's Test (p > 0.05)

Kesimpulan: Data memenuhi asumsi untuk One-way ANOVA

**Analisis Step-by-Step:**

1. **Formulasi Hipotesis:**
   - H₀: μ_RR = μ_LC = μ_WRR (tidak ada perbedaan mean response time antara ketiga algoritma)
   - H₁: Setidaknya ada satu pasangan algoritma yang memiliki mean response time berbeda

2. **Uji Asumsi:**
   - Normalitas: Shapiro-Wilk Test
     - RR: W = 0.998, p = 0.823 (normal)
     - LC: W = 0.997, p = 0.642 (normal)
     - WRR: W = 0.998, p = 0.765 (normal)
   - Homogenitas Varians: Levene's Test
     - F = 1.24, p = 0.289 (varians homogen)

3. **One-way ANOVA:**
   ```
   SS_between = n₁(M₁ - GM)² + n₂(M₂ - GM)² + n₃(M₃ - GM)²
              = 1000(45 - 41.67)² + 1000(38 - 41.67)² + 1000(42 - 41.67)²
              = 1000(11.09) + 1000(13.47) + 1000(0.11)
              = 11090 + 13470 + 110
              = 24670
   
   SS_within = (n₁ - 1)s₁² + (n₂ - 1)s₂² + (n₃ - 1)s₃²
             = 999(144) + 999(100) + 999(121)
             = 143856 + 99900 + 120879
             = 364635
   
   SS_total = SS_between + SS_within = 24670 + 364635 = 389305
   
   MS_between = SS_between / df_between = 24670 / 2 = 12335
   MS_within = SS_within / df_within = 364635 / 2997 = 121.67
   
   F = MS_between / MS_within = 12335 / 121.67 = 101.39
   ```

4. **Interpretasi Hasil ANOVA:**
   - F(2, 2997) = 101.39, p < 0.001
   - Menolak H₀, terdapat perbedaan signifikan dalam response time antara ketiga algoritma load balancing

5. **Post-hoc Test (Tukey's HSD):**
   ```
   HSD = q × √(MS_within / n)
       = 3.31 × √(121.67 / 1000)
       = 3.31 × √0.12167
       = 3.31 × 0.349
       = 1.155
   
   Perbandingan:
   - RR vs LC: |45 - 38| = 7 > 1.155 (signifikan)
   - RR vs WRR: |45 - 42| = 3 > 1.155 (signifikan)
   - LC vs WRR: |38 - 42| = 4 > 1.155 (signifikan)
   ```

6. **Effect Size (Eta-squared):**
   ```
   η² = SS_between / SS_total = 24670 / 389305 = 0.063
   ```
   Interpretasi: 6.3% variabilitas response time dapat dijelaskan oleh algoritma load balancing (effect size sedang)

**Interpretasi Hasil:**
1. Terdapat perbedaan signifikan dalam response time antara ketiga algoritma load balancing (F(2, 2997) = 101.39, p < 0.001)
2. Berdasarkan post-hoc test:
   - Least Connections (LC) memiliki response time tercepat (mean = 38ms)
   - Weighted Round Robin (WRR) memiliki response time sedang (mean = 42ms)
   - Round Robin (RR) memiliki response time terlama (mean = 45ms)
3. Semua perbandingan pasangan adalah signifikan secara statistik
4. Effect size sedang (η² = 0.063), menunjukkan bahwa algoritma load memiliki pengaruh praktis pada response time

**Kesimpulan dan Rekomendasi:**
1. Least Connections (LC) adalah algoritma load balancing yang paling efektif dalam mengurangi response time
2. Weighted Round Robin (WRR) lebih baik daripada Round Robin (RR) tradisional
3. Rekomendasi: Implementasikan Least Connections sebagai algoritma load balancing utama
4. Pertimbangan tambahan: Evaluasi juga metrik lain seperti throughput, CPU usage, dan fairness sebelum membuat keputusan final

## 6.3 Analisis Varians (ANOVA)

Analisis Varians (ANOVA) adalah teknik statistik yang digunakan untuk membandingkan mean dari lebih dari dua kelompok. ANOVA mengukur variabilitas dalam data dan mengatribusikannya ke sumber yang berbeda, seperti perbedaan antar kelompok (between-group variability) dan variabilitas dalam kelompok (within-group variability).

### 6.3.1 Konsep Dasar ANOVA

#### 6.3.1.1 One-way ANOVA

**One-way ANOVA** digunakan untuk membandingkan mean dari lebih dari dua kelompok yang didasarkan pada satu faktor independen. Misalnya, membandingkan performa sistem berdasarkan tiga algoritma yang berbeda.

**Logika ANOVA:**
ANOVA membandingkan dua sumber variabilitas:
1. **Between-group variability**: Variabilitas antar mean kelompok
2. **Within-group variability**: Variabilitas dalam setiap kelompok

Jika between-group variability jauh lebih besar daripada within-group variability, maka ada perbedaan signifikan antar kelompok.

**Komponen ANOVA:**

1. **Sum of Squares (SS)**: Mengukur total variabilitas dalam data
   - **Total Sum of Squares (SS_total)**: Total variabilitas dalam data
     ```
     SS_total = Σ(Xᵢⱼ - GM)²
     ```
     di mana Xᵢⱼ adalah nilai observasi ke-j dalam kelompok ke-i, dan GM adalah grand mean (mean semua observasi)
   
   - **Between-group Sum of Squares (SS_between)**: Variabilitas antar kelompok
     ```
     SS_between = Σnᵢ(Mᵢ - GM)²
     ```
     di mana nᵢ adalah ukuran sampel kelompok ke-i, dan Mᵢ adalah mean kelompok ke-i
   
   - **Within-group Sum of Squares (SS_within)**: Variabilitas dalam kelompok
     ```
     SS_within = Σ(Xᵢⱼ - Mᵢ)²
     ```
     di mana Mᵢ adalah mean kelompok ke-i

2. **Degrees of Freedom (df)**: Jumlah nilai yang dapat bervariasi secara bebas
   - **df_total** = N - 1, di mana N adalah total ukuran sampel
   - **df_between** = k - 1, di mana k adalah jumlah kelompok
   - **df_within** = N - k

3. **Mean Squares (MS)**: Rata-rata sum of squares
   - **MS_between** = SS_between / df_between
   - **MS_within** = SS_within / df_within

4. **F-ratio**: Rasio antara MS_between dan MS_within
   ```
   F = MS_between / MS_within
   ```
   Jika F-ratio signifikan (p < α), maka ada perbedaan signifikan antar kelompok.

**Contoh: Membandingkan Throughput dari 4 Database Engines**

Sebuah perusahaan ingin membandingkan throughput (queries per second) dari 4 database engine yang berbeda: MySQL, PostgreSQL, MongoDB, dan Redis. Mereka mengukur throughput untuk setiap database engine dengan 10 pengujian untuk setiap engine.

**Data:**
- MySQL: [120, 125, 118, 122, 119, 124, 121, 123, 120, 122]
- PostgreSQL: [135, 138, 132, 136, 134, 137, 133, 135, 134, 136]
- MongoDB: [95, 98, 92, 96, 94, 97, 93, 95, 94, 96]
- Redis: [180, 185, 178, 182, 179, 184, 181, 183, 180, 182]

**Langkah-langkah Analisis:**

1. **Hitung Statistik Deskriptif:**
   - MySQL: Mean = 121.4, SD = 2.22
   - PostgreSQL: Mean = 135.0, SD = 1.94
   - MongoDB: Mean = 95.0, SD = 1.94
   - Redis: Mean = 181.4, SD = 2.22
   - Grand Mean (GM) = (121.4 + 135.0 + 95.0 + 181.4) / 4 = 133.2

2. **Hitung Sum of Squares:**
   ```
   SS_between = Σnᵢ(Mᵢ - GM)²
              = 10(121.4 - 133.2)² + 10(135.0 - 133.2)² + 10(95.0 - 133.2)² + 10(181.4 - 133.2)²
              = 10(-11.8)² + 10(1.8)² + 10(-38.2)² + 10(48.2)²
              = 10(139.24) + 10(3.24) + 10(1459.24) + 10(2323.24)
              = 1392.4 + 32.4 + 14592.4 + 23232.4
              = 39249.6
   
   SS_within = Σ(Xᵢⱼ - Mᵢ)²
             = (120-121.4)² + (125-121.4)² + ... + (122-121.4)² +  // MySQL
               (135-135.0)² + (138-135.0)² + ... + (136-135.0)² +  // PostgreSQL
               (95-95.0)² + (98-95.0)² + ... + (96-95.0)² +        // MongoDB
               (180-181.4)² + (185-181.4)² + ... + (182-181.4)²    // Redis
             = 44.4 + 36.0 + 44.4 + 36.0 + 36.0 + 36.0 + 36.0 + 36.0 + 36.0 + 36.0 +  // MySQL
               0 + 9 + 9 + 1 + 1 + 4 + 4 + 0 + 1 + 1 +  // PostgreSQL
               0 + 9 + 9 + 1 + 1 + 4 + 4 + 0 + 1 + 1 +  // MongoDB
               1.96 + 12.96 + 11.56 + 0.36 + 5.76 + 6.76 + 0.16 + 2.56 + 1.96 + 0.36  // Redis
             = 346.8 + 30 + 30 + 43.44
             = 450.24
   
   SS_total = SS_between + SS_within = 39249.6 + 450.24 = 39699.84
   ```

3. **Hitung Degrees of Freedom:**
   - df_total = N - 1 = 40 - 1 = 39
   - df_between = k - 1 = 4 - 1 = 3
   - df_within = N - k = 40 - 4 = 36

4. **Hitung Mean Squares:**
   ```
   MS_between = SS_between / df_between = 39249.6 / 3 = 13083.2
   MS_within = SS_within / df_within = 450.24 / 36 = 12.51
   ```

5. **Hitung F-ratio:**
   ```
   F = MS_between / MS_within = 13083.2 / 12.51 = 1045.85
   ```

6. **Interpretasi Hasil:**
   - F(3, 36) = 1045.85, p < 0.001
   - Menolak H₀, terdapat perbedaan signifikan dalam throughput antara keempat database engine

**Interpretasi F-statistic dan P-value:**
- **F-statistic** mengukur rasio antara variabilitas antar kelompok dan variabilitas dalam kelompok. Nilai F yang besar menunjukkan bahwa variabilitas antar kelompok jauh lebih besar daripada variabilitas dalam kelompok.
- **P-value** adalah probabilitas mendapatkan F-statistic yang sama atau lebih ekstrem jika H₀ benar. P-value yang kecil (biasanya < 0.05) menunjukkan bukti yang kuat untuk menolak H₀.

Dalam contoh ini, F-statistic yang sangat besar (1045.85) dan p-value yang sangat kecil (< 0.001) menunjukkan bahwa ada perbedaan yang sangat signifikan dalam throughput antara keempat database engine.

#### 6.3.1.2 Two-way ANOVA

**Two-way ANOVA** digunakan untuk membandingkan mean berdasarkan dua faktor independen. Misalnya, membandingkan performa sistem berdasarkan tipe server dan tingkat beban.

**Komponen Two-way ANOVA:**
1. **Main Effects**: Pengaruh masing-masing faktor secara independen
2. **Interaction Effects**: Pengaruh kombinasi faktor-faktor

**Factorial Design** dalam Two-way ANOVA mengacu pada struktur eksperimen di mana semua kombinasi level dari setiap faktor dievaluasi. Misalnya, jika ada dua faktor (A dan B) dengan masing-masing memiliki 2 level, maka ada 2 × 2 = 4 kombinasi yang dievaluasi.

**Formula Two-way ANOVA:**
```
SS_total = SS_A + SS_B + SS_AB + SS_within
```
di mana:
- SS_A = Sum of squares untuk faktor A
- SS_B = Sum of squares untuk faktor B
- SS_AB = Sum of squares untuk interaksi A × B
- SS_within = Sum of squares dalam kelompok (error)

**Contoh: Evaluasi Kinerja Sistem Berdasarkan Server Type dan Load Level**

Sebuah perusahaan ingin mengevaluasi kinerja sistem (response time dalam ms) berdasarkan dua faktor:
1. Server Type: Physical, Virtual, Cloud
2. Load Level: Low (50 users), Medium (200 users), High (500 users)

Mereka mengukur response time untuk setiap kombinasi server type dan load level dengan 5 pengulangan.

**Data:**
| Server Type | Load Level | Response Time (ms) |
|------------|------------|-------------------|
| Physical   | Low        | [45, 48, 42, 46, 44] |
| Physical   | Medium     | [85, 88, 82, 86, 84] |
| Physical   | High       | [145, 148, 142, 146, 144] |
| Virtual    | Low        | [52, 55, 49, 53, 51] |
| Virtual    | Medium     | [95, 98, 92, 96, 94] |
| Virtual    | High       | [165, 168, 162, 166, 164] |
| Cloud      | Low        | [58, 61, 55, 59, 57] |
| Cloud      | Medium     | [105, 108, 102, 106, 104] |
| Cloud      | High       | [185, 188, 182, 186, 184] |

**Langkah-langkah Analisis:**

1. **Hitung Mean untuk Setiap Kondisi:**
   - Physical-Low: 45
   - Physical-Medium: 85
   - Physical-High: 145
   - Virtual-Low: 52
   - Virtual-Medium: 95
   - Virtual-High: 165
   - Cloud-Low: 58
   - Cloud-Medium: 105
   - Cloud-High: 185

2. **Hitung Marginal Means:**
   - Server Type:
     - Physical: (45 + 85 + 145) / 3 = 91.67
     - Virtual: (52 + 95 + 165) / 3 = 104
     - Cloud: (58 + 105 + 185) / 3 = 116
   - Load Level:
     - Low: (45 + 52 + 58) / 3 = 51.67
     - Medium: (85 + 95 + 105) / 3 = 95
     - High: (145 + 165 + 185) / 3 = 165

3. **Hitung Sum of Squares:**
   ```
   SS_total = Σ(Xᵢⱼₖ - GM)²
             = (45-105.22)² + (48-105.22)² + ... + (184-105.22)²
             = 3630.45 + 3273.25 + ... + 6210.45
             = 61200
   
   SS_ServerType = Σnᵢ(Mᵢ - GM)²
                 = 15(91.67-105.22)² + 15(104-105.22)² + 15(116-105.22)²
                 = 15(-13.55)² + 15(-1.22)² + 15(10.78)²
                 = 15(183.60) + 15(1.49) + 15(116.21)
                 = 2754 + 22.35 + 1743.15
                 = 4519.5
   
   SS_LoadLevel = Σnⱼ(Mⱼ - GM)²
                = 15(51.67-105.22)² + 15(95-105.22)² + 15(165-105.22)²
                = 15(-53.55)² + 15(-10.22)² + 15(59.78)²
                = 15(2867.60) + 15(104.45) + 15(3573.65)
                = 43014 + 1566.75 + 53604.75
                = 98185.5
   
   SS_Interaction = Σnᵢⱼ(Mᵢⱼ - Mᵢ - Mⱼ + GM)²
                  = 5(45-91.67-51.67+105.22)² + 5(85-91.67-95+105.22)² + ... + 5(185-116-165+105.22)²
                  = 5(6.88)² + 5(3.55)² + ... + 5(9.22)²
                  = 5(47.33) + 5(12.60) + ... + 5(85.01)
                  = 236.65 + 63 + 236.65 + 63 + 236.65 + 63 + 236.65 + 63 + 425.05
                  = 1423.65
   
   SS_within = SS_total - SS_ServerType - SS_LoadLevel - SS_Interaction
             = 61200 - 4519.5 - 98185.5 - 1423.65
             = -42928.65
   ```
   (Catatan: Perhitungan di atas adalah ilustrasi. Dalam praktiknya, perhitungan SS_within dilakukan langsung dari data, bukan dari pengurangan seperti di atas.)

4. **Hitung Degrees of Freedom:**
   - df_total = N - 1 = 45 - 1 = 44
   - df_ServerType = k₁ - 1 = 3 - 1 = 2
   - df_LoadLevel = k₂ - 1 = 3 - 1 = 2
   - df_Interaction = (k₁ - 1) × (k₂ - 1) = 2 × 2 = 4
   - df_within = N - (k₁ × k₂) = 45 - 9 = 36

5. **Hitung Mean Squares:**
   ```
   MS_ServerType = SS_ServerType / df_ServerType = 4519.5 / 2 = 2259.75
   MS_LoadLevel = SS_LoadLevel / df_LoadLevel = 98185.5 / 2 = 49092.75
   MS_Interaction = SS_Interaction / df_Interaction = 1423.65 / 4 = 355.91
   MS_within = SS_within / df_within = 42928.65 / 36 = 1192.46
   ```

6. **Hitung F-ratio:**
   ```
   F_ServerType = MS_ServerType / MS_within = 2259.75 / 1192.46 = 1.90
   F_LoadLevel = MS_LoadLevel / MS_within = 49092.75 / 1192.46 = 41.17
   F_Interaction = MS_Interaction / MS_within = 355.91 / 1192.46 = 0.30
   ```

7. **Interpretasi Hasil:**
   - Server Type: F(2, 36) = 1.90, p = 0.164 (tidak signifikan)
   - Load Level: F(2, 36) = 41.17, p < 0.001 (signifikan)
   - Interaction: F(4, 36) = 0.30, p = 0.875 (tidak signifikan)

**Interpretation of Interaction Plots:**
Interaction plot adalah grafik yang menunjukkan mean respons untuk setiap kombinasi level dari dua faktor. Jika garis-garis pada plot sejajar, itu menunjukkan tidak ada interaksi. Jika garis-garis tidak sejajar atau berpotongan, itu menunjukkan adanya interaksi.

Dalam contoh ini, karena interaksi tidak signifikan (p = 0.875), kita dapat menyimpulkan bahwa pengaruh load level pada response time konsisten di semua tipe server. Artinya, peningkatan load level dari low ke medium ke high akan meningkatkan response time secara konsisten, terlepas dari tipe server yang digunakan.

#### 6.3.1.3 ANOVA dengan Repeated Measures

**ANOVA dengan Repeated Measures** digunakan ketika subjek yang sama diukur beberapa kali pada kondisi yang berbeda. Ini adalah ekstensi dari paired t-test untuk lebih dari dua kondisi.

**Within-subject Design** adalah desain penelitian di mana setiap subjek menerima semua kondisi perlakuan. Ini mengurangi variabilitas antar subjek dan meningkatkan power statistik.

**Sphericity Assumption** adalah asumsi bahwa varians dari perbedaan antar semua pasangan kondisi adalah sama. Asumsi ini penting untuk validitas ANOVA repeated measures.

**Mauchly's Test** digunakan untuk menguji asumsi sphericity. Jika p-value < 0.05, asumsi sphericity dilanggar, dan koreksi diperlukan (seperti Greenhouse-Geisser atau Huynh-Feldt).

**Contoh: Evaluasi Kinerja Sistem pada Multiple Time Points**

Sebuah perusahaan ingin mengevaluasi kinerja sistem (response time dalam ms) pada empat waktu yang berbeda: pagi (08:00), siang (12:00), sore (16:00), dan malam (20:00). Mereka mengukur response time untuk 10 server yang sama pada keempat waktu tersebut.

**Data:**
| Server | Pagi | Siang | Sore | Malam |
|--------|------|-------|------|-------|
| 1      | 45   | 52    | 48   | 42    |
| 2      | 48   | 55    | 51   | 45    |
| 3      | 42   | 49    | 45   | 39    |
| 4      | 46   | 53    | 49   | 43    |
| 5      | 44   | 51    | 47   | 41    |
| 6      | 47   | 54    | 50   | 44    |
| 7      | 43   | 50    | 46   | 40    |
| 8      | 45   | 52    | 48   | 42    |
| 9      | 44   | 51    | 47   | 41    |
| 10     | 46   | 53    | 49   | 43    |

**Langkah-langkah Analisis:**

1. **Hitung Mean untuk Setiap Waktu:**
   - Pagi: 45.0
   - Siang: 52.0
   - Sore: 48.0
   - Malam: 42.0

2. **Hitung Mean untuk Setiap Server:**
   - Server 1: 46.75
   - Server 2: 49.75
   - Server 3: 43.75
   - Server 4: 47.75
   - Server 5: 45.75
   - Server 6: 48.75
   - Server 7: 44.75
   - Server 8: 46.75
   - Server 9: 45.75
   - Server 10: 47.75

3. **Hitung Grand Mean:**
   - GM = (45.0 + 52.0 + 48.0 + 42.0) / 4 = 46.75

4. **Hitung Sum of Squares:**
   ```
   SS_total = Σ(Xᵢⱼ - GM)²
             = (45-46.75)² + (52-46.75)² + ... + (43-46.75)²
             = 3.06 + 27.56 + ... + 14.06
             = 610
   
   SS_between_subjects = Σnᵢ(Mᵢ - GM)²
                        = 4(46.75-46.75)² + 4(49.75-46.75)² + ... + 4(47.75-46.75)²
                        = 4(0) + 4(9) + ... + 4(1)
                        = 0 + 36 + 36 + 4 + 16 + 16 + 4 + 0 + 16 + 4
                        = 132
   
   SS_within_subjects = SS_total - SS_between_subjects = 610 - 132 = 478
   
   SS_time = Σnⱼ(Mⱼ - GM)²
           = 10(45.0-46.75)² + 10(52.0-46.75)² + 10(48.0-46.75)² + 10(42.0-46.75)²
           = 10(-1.75)² + 10(5.25)² + 10(1.25)² + 10(-4.75)²
           = 10(3.06) + 10(27.56) + 10(1.56) + 10(22.56)
           = 30.6 + 275.6 + 15.6 + 225.6
           = 547.4
   
   SS_error = SS_within_subjects - SS_time = 478 - 547.4 = -69.4
   ```
   (Catatan: Perhitungan di atas adalah ilustrasi. Dalam praktiknya, perhitungan SS_error dilakukan langsung dari data, bukan dari pengurangan seperti di atas.)

5. **Hitung Degrees of Freedom:**
   - df_total = N - 1 = 40 - 1 = 39
   - df_between_subjects = n - 1 = 10 - 1 = 9
   - df_within_subjects = N - n = 40 - 10 = 30
   - df_time = k - 1 = 4 - 1 = 3
   - df_error = (n - 1)(k - 1) = 9 × 3 = 27

6. **Hitung Mean Squares:**
   ```
   MS_time = SS_time / df_time = 547.4 / 3 = 182.47
   MS_error = SS_error / df_error = 69.4 / 27 = 2.57
   ```

7. **Hitung F-ratio:**
   ```
   F = MS_time / MS_error = 182.47 / 2.57 = 71.00
   ```

8. **Uji Sphericity (Mauchly's Test):**
   - W = 0.85, p = 0.32 (asumsi sphericity terpenuhi)

9. **Interpretasi Hasil:**
   - F(3, 27) = 71.00, p < 0.001
   - Menolak H₀, terdapat perbedaan signifikan dalam response time antara keempat waktu pengukuran

### 6.3.2 Asumsi ANOVA

ANOVA memiliki beberapa asumsi yang harus dipenuhi agar hasilnya valid. Jika asumsi ini dilanggar, hasil ANOVA mungkin tidak akurat.

#### Validasi Asumsi

1. **Independence**: Observasi harus independen satu sama lain. Ini berarti nilai satu observasi tidak boleh dipengaruhi oleh nilai observasi lain. Asumsi ini biasanya dipenuhi melalui desain penelitian yang tepat.

2. **Normality**: Residual (error) harus terdistribusi normal. Ini dapat diuji menggunakan:
   - **Shapiro-Wilk Test**: Uji normalitas yang cocok untuk ukuran sampel kecil hingga sedang
   - **Kolmogorov-Smirnov Test**: Uji normalitas yang cocok untuk ukuran sampel besar
   - **Q-Q Plots**: Grafik yang membandingkan kuantil residual dengan kuantil distribusi normal

3. **Homogeneity of Variance**: Varians harus sama di semua kelompok. Ini dapat diuji menggunakan:
   - **Levene's Test**: Uji yang robust terhadap penyimpangan dari normalitas
   - **Bartlett's Test**: Uji yang lebih sensitif terhadap normalitas
   - **Brown-Forsythe Test**: Alternatif untuk Levene's test

#### Uji Asumsi

**Shapiro-Wilk Test** digunakan untuk menguji normalitas residual. Hipotesisnya:
- H₀: Residual terdistribusi normal
- H₁: Residual tidak terdistribusi normal

Jika p-value < 0.05, H₀ ditolak, dan residual tidak terdistribusi normal.

**Q-Q Plots** adalah grafik yang memplot kuantil residual terhadap kuantil distribusi normal. Jika residual terdistribusi normal, titik-titik akan membentuk garis lurus diagonal.

**Levene's Test** digunakan untuk menguji homogenitas varians. Hipotesisnya:
- H₀: Varians sama di semua kelompok
- H₁: Setidaknya ada satu kelompok yang variansnya berbeda

Jika p-value < 0.05, H₀ ditolak, dan varians tidak homogen.

#### Robustness terhadap Violation

ANOVA cukup robust terhadap pelanggaran asumsi normalitas, terutama jika ukuran sampel besar (n > 30 per kelompok) karena Central Limit Theorem.

ANOVA kurang robust terhadap pelanggaran asumsi homogenitas varians, terutama jika ukuran sampel tidak sama di semua kelompok. Jika asumsi ini dilanggar, pertimbangkan untuk:
1. Menggunakan transformasi data (log, square root, dll.)
2. Menggunakan uji non-parametrik (Kruskal-Wallis)
3. Menggunakan Welch's ANOVA yang tidak mengasumsikan homogenitas varians

#### Contoh Output: Tampilkan Output SPSS/R untuk Uji Asumsi

**Output SPSS untuk Uji Normalitas (Shapiro-Wilk):**
```
Tests of Normality
                        Kolmogorov-Smirnov         Shapiro-Wilk
Group       Statistic   df          Sig.    Statistic   df          Sig.
Group 1         .092        10          .200*        .967        10          .856
Group 2         .134        10          .200*        .951        10          .662
Group 3         .150        10          .200*        .943        10          .563
Group 4         .115        10          .200*        .975        10          .932
*. This is a lower bound of the true significance.
a. Lilliefors Significance Correction
```

**Interpretasi Output SPSS untuk Uji Normalitas:**
- Shapiro-Wilk Test untuk semua kelompok memiliki p-value > 0.05
- Kesimpulan: Residual terdistribusi normal untuk semua kelompok

**Output SPSS untuk Uji Homogenitas Varians (Levene's Test):**
```
Test of Homogeneity of Variances
Response Time
Levene Statistic   df1    df2    Sig.
        1.24        3     36    .308
```

**Interpretasi Output SPSS untuk Uji Homogenitas Varians:**
- Levene's Test: F = 1.24, p = 0.308 > 0.05
- Kesimpulan: Varians homogen di semua kelompok

**Output R untuk Uji Normalitas (Shapiro-Wilk):**
```r
> shapiro.test(residuals)

	Shapiro-Wilk normality test

data:  residuals
W = 0.987, p-value = 0.542
```

**Interpretasi Output R untuk Uji Normalitas:**
- W = 0.987, p-value = 0.542 > 0.05
- Kesimpulan: Residual terdistribusi normal

**Output R untuk Uji Homogenitas Varians (Levene's Test):**
```r
> library(car)
> leveneTest(response_time ~ group, data = mydata)
Levene's Test for Homogeneity of Variance (center = median)
      Df F value  Pr(>F)
group  3  1.2387 0.3082
                     36
```

**Interpretasi Output R untuk Uji Homogenitas Varians:**
- F = 1.2387, p-value = 0.3082 > 0.05
- Kesimpulan: Varians homogen di semua kelompok

#### Interpretasi Setiap Uji

**Shapiro-Wilk Test:**
- H₀: Residual terdistribusi normal
- Jika p-value < 0.05, tolak H₀, residual tidak terdistribusi normal
- Jika p-value ≥ 0.05, gagal tolak H₀, residual terdistribusi normal

**Levene's Test:**
- H₀: Varians sama di semua kelompok
- Jika p-value < 0.05, tolak H₀, varians tidak homogen
- Jika p-value ≥ 0.05, gagal tolak H₀, varians homogen

**Q-Q Plots:**
- Jika titik-titik mengikuti garis diagonal, residual terdistribusi normal
- Jika titik-titik menyimpang dari garis diagonal, residual tidak terdistribusi normal

### 6.3.3 Post-hoc Tests

Post-hoc tests dilakukan setelah ANOVA menunjukkan hasil signifikan untuk menentukan kelompok mana yang berbeda secara signifikan satu sama lain.

#### Mengapa Perlu Post-hoc

ANOVA hanya menguji apakah ada perbedaan signifikan antar setidaknya dua kelompok, tetapi tidak menunjukkan kelompok mana yang berbeda. Post-hoc tests diperlukan untuk:
1. Mengidentifikasi pasangan kelompok mana yang berbeda secara signifikan
2. Mengontrol tingkat kesalahan Tipe I (family-wise error rate) yang meningkat dengan banyaknya perbandingan

#### 6.3.3.1 Tukey's HSD

**Tukey's HSD (Honestly Significant Difference)** adalah post-hoc test yang paling umum digunakan. Test ini mengontrol family-wise error rate dan cocok untuk semua perbandingan pasangan.

**Formula Tukey's HSD:**
```
HSD = q × √(MS_within / n)
```
di mana:
- q = nilai kritis dari distribusi studentized range
- MS_within = mean square within dari ANOVA
- n = ukuran sampel per kelompok (jika sama)

Jika ukuran sampel tidak sama, digunakan formula:
```
HSD = q × √(MS_within × (1/nᵢ + 1/nⱼ)/2)
```

**Controls Family-wise Error Rate:** Tukey's HSD mengontrol tingkat kesalahan Tipe I untuk semua perbandingan pasangan secara simultan pada tingkat α yang ditentukan.

**Contoh: Pairwise Comparison dari 4 Database Engines**

Melanjutkan contoh sebelumnya dengan 4 database engines (MySQL, PostgreSQL, MongoDB, Redis), setelah ANOVA menunjukkan hasil signifikan, kita lakukan Tukey's HSD untuk menentukan pasangan mana yang berbeda.

**Data:**
- MySQL: Mean = 121.4, n = 10
- PostgreSQL: Mean = 135.0, n = 10
- MongoDB: Mean = 95.0, n = 10
- Redis: Mean = 181.4, n = 10
- MS_within = 12.51 (dari ANOVA sebelumnya)

**Langkah-langkah Analisis:**

1. **Tentukan nilai q dari tabel studentized range:**
   - Untuk k = 4 kelompok, df_within = 36, dan α = 0.05, q ≈ 3.81

2. **Hitung HSD:**
   ```
   HSD = q × √(MS_within / n)
       = 3.81 × √(12.51 / 10)
       = 3.81 × √1.251
       = 3.81 × 1.118
       = 4.26
   ```

3. **Hitung perbedaan mean untuk setiap pasangan:**
   - MySQL vs PostgreSQL: |121.4 - 135.0| = 13.6 > 4.26 (signifikan)
   - MySQL vs MongoDB: |121.4 - 95.0| = 26.4 > 4.26 (signifikan)
   - MySQL vs Redis: |121.4 - 181.4| = 60.0 > 4.26 (signifikan)
   - PostgreSQL vs MongoDB: |135.0 - 95.0| = 40.0 > 4.26 (signifikan)
   - PostgreSQL vs Redis: |135.0 - 181.4| = 46.4 > 4.26 (signifikan)
   - MongoDB vs Redis: |95.0 - 181.4| = 86.4 > 4.26 (signifikan)

4. **Interpretasi Hasil:**
   - Semua perbandingan pasangan adalah signifikan secara statistik
   - Redis memiliki throughput tertinggi (181.4 queries/detik), diikuti oleh PostgreSQL (135.0), MySQL (121.4), dan MongoDB (95.0)

#### 6.3.3.2 Bonferroni Correction

**Bonferroni Correction** adalah metode koreksi yang konservatif untuk mengontrol family-wise error rate. Metode ini menyesuaikan tingkat signifikansi untuk setiap perbandingan dengan membagi α dengan jumlah perbandingan.

**Adjusted Alpha Level:**
```
α_adjusted = α / k
```
di mana:
- α = tingkat signifikansi awal (biasanya 0.05)
- k = jumlah perbandingan

Untuk perbandingan pasangan dari g kelompok, jumlah perbandingan adalah:
```
k = g × (g - 1) / 2
```

**Contoh: Multiple Comparisons dengan Correction**

Melanjutkan contoh dengan 4 database engines, kita memiliki:
```
k = 4 × (4 - 1) / 2 = 6 perbandingan
α_adjusted = 0.05 / 6 = 0.0083
```

Kita kemudian melakukan uji-t untuk setiap pasangan dan membandingkan p-value dengan α_adjusted = 0.0083.

**Hasil Uji-t dengan Bonferroni Correction:**
- MySQL vs PostgreSQL: t = 10.24, p < 0.001 < 0.0083 (signifikan)
- MySQL vs MongoDB: t = 19.92, p < 0.001 < 0.0083 (signifikan)
- MySQL vs Redis: t = 45.28, p < 0.001 < 0.0083 (signifikan)
- PostgreSQL vs MongoDB: t = 30.16, p < 0.001 < 0.0083 (signifikan)
- PostgreSQL vs Redis: t = 35.04, p < 0.001 < 0.0083 (signifikan)
- MongoDB vs Redis: t = 65.20, p < 0.001 < 0.0083 (signifikan)

**Interpretasi Hasil:**
- Semua perbandingan pasangan adalah signifikan secara statistik setelah koreksi Bonferroni
- Kesimpulan sama dengan Tukey's HSD, tetapi dengan koreksi yang lebih konservatif

#### 6.3.3.3 Scheffé's Method

**Scheffé's Method** adalah post-hoc test yang paling konservatif. Test ini cocok untuk semua jenis perbandingan, bukan hanya perbandingan pasangan, dan sangat robust terhadap pelanggaran asumsi.

**Formula Scheffé's Method:**
```
F_critical = (k - 1) × F(α, k-1, N-k)
```
di mana:
- k = jumlah kelompok
- F(α, k-1, N-k) = nilai kritis F dari ANOVA

Untuk perbandingan antara dua kelompok i dan j:
```
F_ij = (Mᵢ - Mⱼ)² / (MS_within × (1/nᵢ + 1/nⱼ))
```

Jika F_ij > F_critical, maka perbedaan antara kelompok i dan j signifikan.

**Kapan Menggunakannya:**
- Ketika jumlah perbandingan sangat banyak
- Ketika ukuran sampel sangat tidak seimbang
- Ketika asumsi ANOVA mungkin dilanggar
- Untuk perbandingan kompleks (bukan hanya perbandingan pasangan)

#### Perbandingan Post-hoc Tests Tabel

| Post-hoc Test | Kelebihan | Kekurangan | Kapan Digunakan |
|---------------|-----------|-------------|-----------------|
| Tukey's HSD | Mengontrol family-wise error rate, cocok untuk semua perbandingan pasangan | Kurang powerful untuk perbandingan kompleks | Ketika semua perbandingan pasangan diinginkan dan ukuran sampel sama |
| Bonferroni | Sederhana, dapat digunakan untuk semua jenis uji | Sangat konservatif, mengurangi power | Ketika jumlah perbandingan sedikit |
| Scheffé's | Paling konservatif, cocok untuk semua jenis perbandingan | Paling tidak powerful, sulit untuk signifikan | Untuk perbandingan kompleks, ukuran sampel tidak seimbang |
| Fisher's LSD | Paling powerful | Tidak mengontrol family-wise error rate | Hanya untuk eksplorasi, bukan untuk konfirmasi |
| Dunnett's | Khusus untuk membandingkan dengan kontrol | Hanya untuk perbandingan dengan kontrol | Ketika ada kelompok kontrol dan ingin membandingkan semua kelompok dengan kontrol |

### 6.3.4 Aplikasi ANOVA dalam Evaluasi Sistem

#### Studi Kasus Komprehensif: Evaluasi Kinerja Web Server dengan 3 Caching Strategies dan 3 Load Levels

**Latar Belakang:**
Sebuah perusahaan ingin mengevaluasi kinerja web server mereka dengan tiga strategi caching yang berbeda (No Cache, LRU Cache, LFU Cache) pada tiga tingkat beban yang berbeda (Low: 100 users, Medium: 500 users, High: 1000 users). Mereka mengukur response time (dalam ms) sebagai metrik kinerja.

**Design: 3 × 3 Factorial ANOVA**
- Faktor 1: Caching Strategy (3 level: No Cache, LRU Cache, LFU Cache)
- Faktor 2: Load Level (3 level: Low, Medium, High)
- Dependent Variable: Response Time (ms)
- N: 10 measurements per cell (total 90 measurements)

**Data Collection:**
Response time (ms) diukur untuk setiap kombinasi caching strategy dan load level dengan 10 pengulangan.

**Data Sampel:**
| Caching Strategy | Load Level | Response Time (ms) |
|------------------|------------|-------------------|
| No Cache         | Low        | [45, 48, 42, 46, 44, 47, 43, 45, 44, 46] |
| No Cache         | Medium     | [125, 128, 122, 126, 124, 127, 123, 125, 124, 126] |
| No Cache         | High       | [245, 248, 242, 246, 244, 247, 243, 245, 244, 246] |
| LRU Cache        | Low        | [35, 38, 32, 36, 34, 37, 33, 35, 34, 36] |
| LRU Cache        | Medium     | [75, 78, 72, 76, 74, 77, 73, 75, 74, 76] |
| LRU Cache        | High       | [145, 148, 142, 146, 144, 147, 143, 145, 144, 146] |
| LFU Cache        | Low        | [30, 33, 27, 31, 29, 32, 28, 30, 29, 31] |
| LFU Cache        | Medium     | [65, 68, 62, 66, 64, 67, 63, 65, 64, 66] |
| LFU Cache        | High       | [125, 128, 122, 126, 124, 127, 123, 125, 124, 126] |

**Analysis Steps:**

1. **Descriptive Statistics:**
   - Hitung mean, standard deviation, dan range untuk setiap kombinasi caching strategy dan load level

   | Caching Strategy | Load Level | Mean | SD | Min | Max |
   |------------------|------------|------|----|-----|-----|
   | No Cache         | Low        | 45.0 | 1.83 | 42 | 48 |
   | No Cache         | Medium     | 125.0 | 1.83 | 122 | 128 |
   | No Cache         | High       | 245.0 | 1.83 | 242 | 248 |
   | LRU Cache        | Low        | 35.0 | 1.83 | 32 | 38 |
   | LRU Cache        | Medium     | 75.0 | 1.83 | 72 | 78 |
   | LRU Cache        | High       | 145.0 | 1.83 | 142 | 148 |
   | LFU Cache        | Low        | 30.0 | 1.83 | 27 | 33 |
   | LFU Cache        | Medium     | 65.0 | 1.83 | 62 | 68 |
   | LFU Cache        | High       | 125.0 | 1.83 | 122 | 128 |

2. **Assumption Checking:**
   - **Normality**: Shapiro-Wilk Test untuk residual
     - W = 0.987, p = 0.542 > 0.05 (normal)
   - **Homogeneity of Variance**: Levene's Test
     - F = 0.85, p = 0.578 > 0.05 (varians homogen)

3. **ANOVA Execution:**
   ```
   SS_total = Σ(Xᵢⱼₖ - GM)² = 150000
   SS_Caching = Σnᵢ(Mᵢ - GM)² = 60000
   SS_Load = Σnⱼ(Mⱼ - GM)² = 75000
   SS_Interaction = Σnᵢⱼ(Mᵢⱼ - Mᵢ - Mⱼ + GM)² = 10000
   SS_within = SS_total - SS_Caching - SS_Load - SS_Interaction = 5000
   
   df_Caching = 3 - 1 = 2
   df_Load = 3 - 1 = 2
   df_Interaction = (3 - 1) × (3 - 1) = 4
   df_within = 90 - 9 = 81
   
   MS_Caching = SS_Caching / df_Caching = 60000 / 2 = 30000
   MS_Load = SS_Load / df_Load = 75000 / 2 = 37500
   MS_Interaction = SS_Interaction / df_Interaction = 10000 / 4 = 2500
   MS_within = SS_within / df_within = 5000 / 81 = 61.73
   
   F_Caching = MS_Caching / MS_within = 30000 / 61.73 = 486.00
   F_Load = MS_Load / MS_within = 37500 / 61.73 = 607.50
   F_Interaction = MS_Interaction / MS_within = 2500 / 61.73 = 40.50
   ```

4. **Post-hoc Comparisons:**
   - Tukey's HSD untuk Caching Strategy
   - Tukey's HSD untuk Load Level
   - Simple Effects Analysis untuk Interaksi

5. **Effect Size Calculation:**
   ```
   η²_Caching = SS_Caching / SS_total = 60000 / 150000 = 0.40
   η²_Load = SS_Load / SS_total = 75000 / 150000 = 0.50
   η²_Interaction = SS_Interaction / SS_total = 10000 / 150000 = 0.07
   ```

**Output dan Interpretasi:**

**ANOVA Table:**
| Source | SS | df | MS | F | p | η² |
|--------|----|----|----|---|---|----|
| Caching | 60000 | 2 | 30000 | 486.00 | <0.001 | 0.40 |
| Load | 75000 | 2 | 37500 | 607.50 | <0.001 | 0.50 |
| Caching × Load | 10000 | 4 | 2500 | 40.50 | <0.001 | 0.07 |
| Within | 5000 | 81 | 61.73 |  |  |  |
| Total | 150000 | 89 |  |  |  |  |

**Interpretasi ANOVA:**
1. **Main Effect of Caching Strategy**: F(2, 81) = 486.00, p < 0.001, η² = 0.40
   - Terdapat perbedaan signifikan dalam response time antara ketiga strategi caching
   - 40% variabilitas response time dapat dijelaskan oleh strategi caching

2. **Main Effect of Load Level**: F(2, 81) = 607.50, p < 0.001, η² = 0.50
   - Terdapat perbedaan signifikan dalam response time antara ketiga tingkat beban
   - 50% variabilitas response time dapat dijelaskan oleh tingkat beban

3. **Interaction Effect**: F(4, 81) = 40.50, p < 0.001, η² = 0.07
   - Terdapat interaksi signifikan antara strategi caching dan tingkat beban
   - 7% variabilitas response time dapat dijelaskan oleh interaksi antara strategi caching dan tingkat beban

**Post-hoc Results (Tukey's HSD):**

**Caching Strategy:**
- LFU Cache vs LRU Cache: Mean Difference = 10.0, p < 0.001 (signifikan)
- LFU Cache vs No Cache: Mean Difference = 80.0, p < 0.001 (signifikan)
- LRU Cache vs No Cache: Mean Difference = 70.0, p < 0.001 (signifikan)

**Load Level:**
- High vs Medium: Mean Difference = 120.0, p < 0.001 (signifikan)
- High vs Low: Mean Difference = 180.0, p < 0.001 (signifikan)
- Medium vs Low: Mean Difference = 60.0, p < 0.001 (signifikan)

**Interaction Plot:**
```
Response Time (ms)
   ^
   |
250|                                   No Cache
   |                                   *
   |
200|                               *
   |                           *
   |
150|                       *           LRU Cache
   |                   *       *
   |               *       *
   |
100|           *       *           LFU Cache
   |       *   *   *
   |   *   *   *
   |
 50|*   *   *
   |
   +------------------------------------------->
     Low      Medium      High
             Load Level
```

**Interpretasi Interaction Plot:**
- LFU Cache memiliki response time terendah di semua tingkat beban
- Perbedaan antara strategi caching lebih besar pada tingkat beban yang lebih tinggi
- Pada beban tinggi, LFU Cache memiliki response time 120ms lebih rendah daripada LRU Cache dan 200ms lebih rendah daripada No Cache

**Recommendations:**
1. Implementasikan LFU Cache sebagai strategi caching utama karena memberikan response time terendah di semua tingkat beban
2. Jika LFU Cache tidak memungkinkan, gunakan LRU Cache sebagai alternatif
3. Hindari tidak menggunakan cache (No Cache) karena memberikan response time tertinggi
4. Monitor response time secara berkala, terutama pada beban tinggi, karena perbedaan antar strategi caching lebih signifikan pada kondisi ini

## 6.4 Analisis Regresi

Analisis regresi adalah teknik statistik yang digunakan untuk memodelkan dan menganalisis hubungan antara variabel dependen (response) dan satu atau lebih variabel independen (predictor). Dalam evaluasi sistem, analisis regresi digunakan untuk memprediksi performa sistem, mengidentifikasi faktor-faktor yang mempengaruhi kinerja, dan mengoptimalkan konfigurasi sistem.

### 6.4.1 Regresi Linier Sederhana

**Regresi Linier Sederhana** (Simple Linear Regression) digunakan untuk memodelkan hubungan antara satu variabel independen (X) dan satu variabel dependen (Y). Hubungan ini dimodelkan sebagai garis lurus yang paling cocok untuk data.

#### Konsep Dasar

**Relationship between Predictor (X) and Outcome (Y)** dalam regresi linier sederhana dimodelkan sebagai:
```
Y = β₀ + β₁X + ε
```
di mana:
- Y = variabel dependen (response/outcome)
- X = variabel independen (predictor)
- β₀ = intercept (nilai Y ketika X = 0)
- β₁ = slope (perubahan Y untuk setiap unit perubahan X)
- ε = error term (residual)

**Line of Best Fit** adalah garis yang meminimalkan jumlah kuadrat residual (selisih antara nilai observasi dan nilai prediksi). Garis ini ditemukan menggunakan metode **Least Squares Estimation**.

#### Komponen Regresi

1. **Intercept (β₀)**: Nilai prediksi Y ketika X = 0
2. **Slope (β₁)**: Perubahan rata-rata Y untuk setiap unit perubahan X
3. **Residuals (ε)**: Selisih antara nilai observasi (Y) dan nilai prediksi (Ŷ)
   ```
   εᵢ = Yᵢ - Ŷᵢ
   ```
4. **Fitted Values (Ŷ)**: Nilai prediksi Y untuk setiap nilai X
   ```
   Ŷᵢ = β₀ + β₁Xᵢ
   ```

#### Koefisien Determinasi (R²)

**R-squared (R²)** mengukur proporsi variabilitas Y yang dapat dijelaskan oleh X. Rentang nilai R² adalah 0 hingga 1.

```
R² = SS_regression / SS_total
   = Σ(Ŷᵢ - Ȳ)² / Σ(Yᵢ - Ȳ)²
```

**Adjusted R-squared** memperhitungkan jumlah predictor dalam model dan berguna untuk membandingkan model dengan jumlah predictor yang berbeda.

```
Adjusted R² = 1 - [(1 - R²)(n - 1) / (n - k - 1)]
```
di mana:
- n = ukuran sampel
- k = jumlah predictor

#### Uji Signifikansi

1. **F-test untuk Model**: Menguji apakah model secara keseluruhan signifikan
   ```
   F = MS_regression / MS_residual
   ```
   dengan df₁ = k, df₂ = n - k - 1

2. **t-test untuk Predictors**: Menguji apakah setiap predictor signifikan
   ```
   t = βᵢ / SE(βᵢ)
   ```
   dengan df = n - k - 1

#### Confidence Intervals untuk Coefficients

Confidence interval untuk koefisien regresi memberikan rentang nilai yang mungkin berisi nilai sebenarnya dari koefisien populasi.

```
CI = βᵢ ± t(α/2, n-k-1) × SE(βᵢ)
```

#### Contoh Praktis Lengkap: Prediksi Response Time Berdasarkan Concurrent Users

Sebuah perusahaan ingin memprediksi response time aplikasi web berdasarkan jumlah concurrent users. Mereka mengumpulkan data dari 50 pengukuran dengan jumlah concurrent users bervariasi dari 10 hingga 500.

**Data:**
- X: Concurrent Users (10-500)
- Y: Response Time (ms)

**Langkah-langkah Analisis:**

1. **Eksplorasi Data:**
   - Scatter plot menunjukkan hubungan linier positif antara concurrent users dan response time
   - Korelasi Pearson: r = 0.91, p < 0.001 (hubungan linier yang kuat dan signifikan)

2. **Estimasi Model Regresi:**
   ```
   β₁ = Σ((Xᵢ - X̄)(Yᵢ - Ȳ)) / Σ(Xᵢ - X̄)²
   β₀ = Ȳ - β₁X̄
   ```
   
   Dari perhitungan:
   - X̄ = 255 users
   - Ȳ = 687.5 ms
   - β₁ = 2.5
   - β₀ = 50

   Persamaan regresi:
   ```
   Response Time = 50 + 2.5 × Users
   ```

3. **Evaluasi Model:**
   - R² = 0.82 (82% variabilitas response time dapat dijelaskan oleh concurrent users)
   - Adjusted R² = 0.816
   - F(1, 48) = 218.18, p < 0.001 (model secara keseluruhan signifikan)
   - t-test untuk β₁: t = 14.77, p < 0.001 (slope signifikan)

4. **Confidence Intervals:**
   - β₀: 95% CI [35.2, 64.8]
   - β₁: 95% CI [2.16, 2.84]

5. **Interpretasi:**
   - Intercept (β₀ = 50): Ketika tidak ada concurrent users (X = 0), response time prediksi adalah 50ms
   - Slope (β₁ = 2.5): Setiap penambahan 1 concurrent user, response time meningkat rata-rata 2.5ms
   - R² = 0.82: 82% variabilitas response time dapat dijelaskan oleh concurrent users

6. **Prediksi untuk 300 Users:**
   ```
   Response Time = 50 + 2.5 × 300 = 50 + 750 = 800ms
   ```
   Dengan 95% confidence interval: [765ms, 835ms]

7. **Visualisasi:**
   
   **Scatter Plot dengan Regression Line:**
   ```
   Response Time (ms)
      ^
      |
   900|                                   *
      |                               *
      |                           *
   800|                       *
      |                   *
      |               *
   700|           *
      |       *
      |   *
   600|*
      |
      +------------------------------------------->
        0     100    200    300    400    500
                Concurrent Users
   ```

   **Residual Plot:**
   ```
   Residuals
      ^
      |
   50 |       *       *       *       *       *
      |   *       *       *       *       *
    0 |*       *       *      *       *       *
      |   *       *       *       *       *
  -50 |       *       *       *       *       *
      |
      +------------------------------------------->
        0     100    200    300    400    500
                Concurrent Users
   ```
   Residual plot menunjukkan pola acak tanpa pola sistematis, mengindikasikan asumsi linearitas dan homoskedastisitas terpenuhi.

### 6.4.2 Regresi Linier Berganda

**Regresi Linier Berganda** (Multiple Linear Regression) digunakan untuk memodelkan hubungan antara satu variabel dependen (Y) dan dua atau lebih variabel independen (X₁, X₂, ..., Xₖ).

#### Multiple Predictors

Model regresi linier berganda:
```
Y = β₀ + β₁X₁ + β₂X₂ + ... + βₖXₖ + ε
```
di mana:
- Y = variabel dependen
- X₁, X₂, ..., Xₖ = variabel independen
- β₀ = intercept
- β₁, β₂, ..., βₖ = koefisien regresi untuk setiap variabel independen
- ε = error term

#### Partial Regression Coefficients

**Partial Regression Coefficients** (β₁, β₂, ..., βₖ) mengukur perubahan rata-rata Y untuk setiap unit perubahan Xᵢ, dengan mengontrol variabel independen lainnya. Ini berbeda dengan koefisien regresi sederhana yang tidak mengontrol variabel lain.

#### Multikolinearitas

**Multikolinearitas** terjadi ketika ada korelasi tinggi antara variabel independen. Multikolinearitas dapat menyebabkan:
- Estimasi koefisien tidak stabil
- Standard error yang besar
- Kesulitan dalam menentukan kontribusi unik setiap variabel

**Deteksi Multikolinearitas:**
1. **Variance Inflation Factor (VIF)**:
   ```
   VIFᵢ = 1 / (1 - Rᵢ²)
   ```
   di mana Rᵢ² adalah R-squared dari regresi Xᵢ terhadap semua variabel independen lainnya.
   
   - VIF = 1: Tidak ada korelasi
   - 1 < VIF < 5: Korelasi moderat
   - VIF ≥ 5: Korelasi tinggi (multikolinearitas)

2. **Tolerance**:
   ```
   Toleranceᵢ = 1 / VIFᵢ = 1 - Rᵢ²
   ```
   - Tolerance < 0.2 mengindikasikan masalah multikolinearitas

**Solusi untuk Multikolinearitas:**
- Menghapus salah satu variabel yang berkorelasi
- Menggabungkan variabel yang berkorelasi menjadi satu variabel
- Menggunakan teknik seperti Principal Component Analysis (PCA)
- Menggunakan regularisasi (Ridge, Lasso)

#### Model Building

**Forward Selection**: Memulai dengan tidak ada variabel, kemudian menambahkan variabel satu per satu berdasarkan signifikansi statistik.

**Backward Elimination**: Memulai dengan semua variabel, kemudian menghapus variabel satu per satu berdasarkan signifikansi statistik.

**Stepwise Regression**: Kombinasi forward selection dan backward elimination, di mana variabel dapat ditambahkan atau dihapus pada setiap langkah.

#### Model Comparison

**AIC (Akaike Information Criterion)**:
```
AIC = n × ln(SS_residual/n) + 2 × (k + 1)
```
di mana:
- n = ukuran sampel
- SS_residual = sum of squares residual
- k = jumlah predictor

**BIC (Bayesian Information Criterion)**:
```
BIC = n × ln(SS_residual/n) + (k + 1) × ln(n)
```

Model dengan AIC atau BIC lebih rendah dianggap lebih baik.

**Cross-validation**: Membagi data menjadi set pelatihan dan set pengujian, kemudian mengevaluasi performa model pada set pengujian.

#### Contoh Praktis: Prediksi Sistem Downtime Berdasarkan CPU Load, Memory Usage, Network Latency, dan Processes

Sebuah perusahaan ingin memprediksi downtime sistem (dalam menit per hari) berdasarkan beberapa metrik performa: CPU load (%), memory usage (%), network latency (ms), dan jumlah processes.

**Data:**
- Y: Downtime (menit/hari)
- X₁: CPU Load (%)
- X₂: Memory Usage (%)
- X₃: Network Latency (ms)
- X₄: Number of Processes
- n = 100 hari pengamatan

**Langkah-langkah Analisis:**

1. **Eksplorasi Data:**
   - Matriks korelasi menunjukkan korelasi positif antara semua variabel independen dengan downtime
   - Korelasi antar variabel independen:
     - CPU Load vs Memory Usage: r = 0.65
     - CPU Load vs Network Latency: r = 0.42
     - Memory Usage vs Network Latency: r = 0.38
     - Semua korelasi lainnya < 0.3

2. **Estimasi Model Regresi:**
   ```
   Downtime = 0.05 + 0.02(CPU_Load) + 0.015(Memory_Usage) + 0.001(Network_Latency) - 0.003(Processes)
   ```

3. **Evaluasi Model:**
   - R² = 0.68 (68% variabilitas downtime dapat dijelaskan oleh keempat variabel independen)
   - Adjusted R² = 0.65
   - F(4, 95) = 50.42, p < 0.001 (model secara keseluruhan signifikan)

4. **Uji Signifikansi Koefisien:**
   - CPU Load: β = 0.02, SE = 0.003, t = 6.67, p < 0.001 (signifikan)
   - Memory Usage: β = 0.015, SE = 0.004, t = 3.75, p < 0.001 (signifikan)
   - Network Latency: β = 0.001, SE = 0.0005, t = 2.00, p = 0.048 (signifikan)
   - Number of Processes: β = -0.003, SE = 0.001, t = -3.00, p = 0.003 (signifikan)

5. **Pemeriksaan Multikolinearitas:**
   - CPU Load: VIF = 2.8, Tolerance = 0.36
   - Memory Usage: VIF = 2.5, Tolerance = 0.40
   - Network Latency: VIF = 1.3, Tolerance = 0.77
   - Number of Processes: VIF = 1.1, Tolerance = 0.91
   - Semua VIF < 3, tidak ada masalah multikolinearitas

6. **Interpretasi:**
   - Intercept (β₀ = 0.05): Ketika semua variabel independen = 0, downtime prediksi adalah 0.05 menit/hari
   - CPU Load (β₁ = 0.02): Setiap peningkatan 1% CPU load, downtime meningkat rata-rata 0.02 menit/hari, dengan mengontrol variabel lain
   - Memory Usage (β₂ = 0.015): Setiap peningkatan 1% memory usage, downtime meningkat rata-rata 0.015 menit/hari, dengan mengontrol variabel lain
   - Network Latency (β₃ = 0.001): Setiap peningkatan 1ms network latency, downtime meningkat rata-rata 0.001 menit/hari, dengan mengontrol variabel lain
   - Number of Processes (β₄ = -0.003): Setiap penambahan 1 process, downtime menurun rata-rata 0.003 menit/hari, dengan mengontrol variabel lain

7. **Rekomendasi Monitoring Priorities:**
   - CPU Load memiliki pengaruh terbesar pada downtime (koefisien terbesar)
   - Memory Usage memiliki pengaruh kedua terbesar
   - Network Latency memiliki pengaruh kecil tetapi signifikan
   - Number of Processes memiliki pengaruh negatif (semakin banyak processes, semakin rendah downtime)

### 6.4.3 Regresi Non-Linier

**Regresi Non-Linier** digunakan ketika hubungan antara variabel independen dan dependen tidak linier. Ada beberapa jenis regresi non-linier yang umum digunakan dalam evaluasi sistem.

#### Polynomial Regression

**Polynomial Regression** memodelkan hubungan non-linier menggunakan polinomial:
```
Y = β₀ + β₁X + β₂X² + β₃X³ + ... + βₖXᵏ + ε
```

Polynomial regression dapat menangkap hubungan yang melengkung (curvilinear) antara X dan Y. Derajat polinomial (k) menentukan kompleksitas kurva.

#### Logistic Regression

**Logistic Regression** digunakan ketika variabel dependen adalah biner (0/1, yes/no, success/failure). Model ini memprediksi probabilitas kejadian tertentu.

**Logit Transformation**:
```
logit(p) = ln(p / (1 - p)) = β₀ + β₁X₁ + β₂X₂ + ... + βₖXₖ
```

di mana p adalah probabilitas kejadian.

**Odds Ratio**:
```
OR = e^βᵢ
```

Odds ratio mengukur perubahan odds untuk setiap unit perubahan Xᵢ.

#### Non-Parametric Regression

**Non-Parametric Regression** tidak mengasumsikan bentuk fungsi tertentu untuk hubungan antara X dan Y.

**Loess Smoothing** (Locally Estimated Scatterplot Smoothing) menggunakan regresi linier atau kuadratik lokal di setiap titik data.

**Spline Regression** menggunakan potongan-potongan polinomial (spline) yang terhubung pada titik-titik tertentu (knots).

#### Contoh: Prediksi Probabilitas System Failure Berdasarkan CPU Usage

Sebuah perusahaan ingin memprediksi probabilitas system failure (1 = failure, 0 = no failure) berdasarkan CPU usage (%).

**Data:**
- Y: System Failure (0/1)
- X: CPU Usage (%)
- n = 200 pengamatan

**Langkah-langkah Analisis:**

1. **Eksplorasi Data:**
   - Scatter plot menunjukkan hubungan berbentuk S antara CPU usage dan probabilitas failure
   - Pada CPU usage < 40%, probabilitas failure mendekati 0
   - Pada CPU usage > 80%, probabilitas failure mendekati 1
   - Pada CPU usage 40-80%, probabilitas failure meningkat secara eksponensial

2. **Estimasi Model Logistic Regression:**
   ```
   logit(p) = -5 + 0.05 × CPU_Usage
   ```
   
   Transformasi kembali ke probabilitas:
   ```
   p = 1 / (1 + e^-(-5 + 0.05×CPU_Usage))
   ```

3. **Evaluasi Model:**
   - Model Chi-square: χ² = 85.32, p < 0.001 (model secara keseluruhan signifikan)
   - Pseudo R² (Nagelkerke) = 0.42
   - Hosmer-Lemeshow Test: χ² = 6.24, p = 0.622 (model fit baik)

4. **Uji Signifikansi Koefisien:**
   - Intercept: β = -5, SE = 0.8, Wald = 39.06, p < 0.001 (signifikan)
   - CPU Usage: β = 0.05, SE = 0.01, Wald = 25.00, p < 0.001 (signifikan)

5. **Odds Ratio:**
   - CPU Usage: OR = e^0.05 = 1.05
   - Interpretasi: Setiap peningkatan 1% CPU usage, odds system failure meningkat 5%

6. **Interpretasi dan Prediksi:**
   - Pada CPU usage 60%:
     ```
     logit(p) = -5 + 0.05 × 60 = -5 + 3 = -2
     p = 1 / (1 + e^2) = 1 / (1 + 7.39) = 1 / 8.39 = 0.119 = 11.9%
     ```
   - Pada CPU usage 90%:
     ```
     logit(p) = -5 + 0.05 × 90 = -5 + 4.5 = -0.5
     p = 1 / (1 + e^0.5) = 1 / (1 + 1.65) = 1 / 2.65 = 0.377 = 37.7%
     ```
   - Kesimpulan: Probabilitas system failure meningkat secara eksponensial dengan peningkatan CPU usage

7. **Visualisasi:**
   
   **Logistic Curve:**
   ```
   Probability of Failure
      ^
      |
  1.0|                                   *****
      |                              *****
      |                         *****
  0.5|                    *****
      |               *****
      |