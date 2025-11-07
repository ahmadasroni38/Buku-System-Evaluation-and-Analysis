# Bab 8: Studi Kasus Implementasi

## 8.1 Studi Kasus: Evaluasi Sistem Enterprise Resource Planning (ERP)

### Konteks Sistem
PT Manufaktur Maju adalah perusahaan manufaktur skala menengah yang telah mengimplementasikan sistem ERP baru enam bulan lalu untuk mengintegrasikan proses bisnis mereka, mulai dari manajemen inventaris, produksi, hingga distribusi. Setelah implementasi, perusahaan menghadapi beberapa masalah kritis: sistem sering mengalami kelambatan saat mengakses modul inventaris, waktu respons yang lama saat memproses transaksi, dan tingkat adopsi pengguna yang rendah. Manajemen perusahaan menduga ada masalah kinerja dan usability yang signifikan, namun mereka tidak memiliki data yang cukup untuk mengidentifikasi akar masalah dan merumuskan solusi yang tepat.

Tujuan evaluasi ini adalah untuk mengidentifikasi masalah kinerja dan usability pada sistem ERP, menentukan penyebabnya, dan memberikan rekomendasi yang dapat meningkatkan kinerja sistem dan tingkat adopsi pengguna.

### Metodologi Evaluasi
Tim evaluasi menggunakan pendekatan **Mixed Methods** yang menggabungkan metode kuantitatif dan kualitatif untuk mendapatkan pemahaman komprehensif tentang masalah yang ada. Pendekatan ini dipilih karena memungkinkan tim untuk mendapatkan data yang kaya dan mendalam tentang masalah kinerja (kuantitatif) serta persepsi dan pengalaman pengguna (kualitatif).

**Pengumpulan Data Kuantitatif:**
1. **Analisis Log Sistem**: Tim mengumpulkan log sistem selama periode 30 hari untuk menganalisis metrik kinerja seperti **Latency** dan **Throughput**. Analisis ini difokuskan pada modul-modul yang sering dilaporkan bermasalah, terutama modul inventaris dan produksi.
2. **Pengukuran Waktu Respons**: Tim melakukan pengukuran waktu respons untuk transaksi-transaksi kritis pada berbagai waktu sepanjang hari untuk mengidentifikasi pola kinerja.
3. **Pemantauan Sumber Daya**: Tim memantau penggunaan CPU, memori, dan I/O database untuk mengidentifikasi potensi bottleneck sumber daya.

**Pengumpulan Data Kualitatif:**
1. **Survei Kepuasan Pengguna**: Tim menyebarkan survei kepada 150 pengguna sistem ERP yang mencakup aspek usability, kepuasan, dan hambatan dalam penggunaan sistem. Survei ini menggunakan skala Likert 5 poin dan pertanyaan terbuka.
2. **Wawancara Mendalam**: Tim melakukan wawancara mendalam dengan 20 pengguna yang dipilih secara purposif, termasuk staf operasional, supervisor, dan manajer departemen. Wawancara ini difokuskan pada pengalaman pengguna, masalah yang dihadapi, dan saran untuk perbaikan.
3. **Observasi Penggunaan Sistem**: Tim melakukan observasi langsung terhadap 10 pengguna saat mereka menggunakan sistem dalam pekerjaan sehari-hari untuk memahami konteks penggunaan dan masalah usability yang mungkin tidak terungkap dalam survei atau wawancara.

**Analisis Data:**
Data kuantitatif dianalisis menggunakan teknik **analisis statistik** dari Bab 6, termasuk analisis deskriptif dan uji hipotesis untuk membandingkan kinerja antar modul. Data kualitatif dianalisis menggunakan teknik analisis tematik untuk mengidentifikasi pola dan tema yang muncul dari survei, wawancara, dan observasi.

### Hasil Evaluasi
**Hasil Kuantitatif:**
Analisis log sistem menunjukkan bahwa modul inventaris memiliki **Latency** rata-rata 8,2 detik, jauh lebih tinggi dibandingkan dengan modul lain yang rata-rata hanya 1-2 detik. **Throughput** modul inventaris juga hanya mencapai 15 transaksi per menit, sementara modul lain dapat mencapai 50-60 transaksi per menit.

Analisis statistik lebih lanjut menggunakan **ANOVA** menunjukkan perbedaan signifikan (p < 0,001) dalam waktu respons antar modul, dengan modul inventaris sebagai outlier. Analisis regresi mengungkapkan korelasi kuat (r = 0,87) antara jumlah pengguna aktif dan peningkatan latency pada modul inventaris, menunjukkan bahwa modul ini tidak dapat menangani beban pengguna secara efisien.

Pemantauan sumber daya mengidentifikasi bahwa penggunaan CPU pada server database mencapai 95% saat penggunaan modul inventaris puncak, yang menunjukkan adanya bottleneck pada tingkat database. Analisis query mengungkapkan beberapa query yang tidak teroptimasi pada modul inventaris yang menyebabkan beban berlebih pada database.

**Hasil Kualitatif:**
Survei kepuasan pengguna menunjukkan bahwa hanya 35% pengguna yang merasa puas dengan sistem ERP, dengan modul inventaris mendapatkan rating terendah (rata-rata 2,1 dari skala 5). Analisis tematik terhadap data kualitatif mengidentifikasi beberapa tema utama:

1. **Antarmuka Pengguna yang Rumit**: Banyak pengguna mengeluhkan antarmuka modul inventaris yang tidak intuitif dan memerlukan terlalu banyak langkah untuk menyelesaikan tugas sederhana. Seorang staf gudang menyatakan, *"Saya harus melalui lima layar berbeda hanya untuk memasukkan satu item inventaris. Ini sangat memakan waktu dan membingungkan."*

2. **Kinerja yang Lambat**: Pengguna sering mengalami jeda saat menggunakan sistem, terutama saat mengakses modul inventaris. Seorang supervisor produksi mengatakan, *"Saya sering harus menunggu hingga 10 detik hanya untuk melihat status inventaris. Ini sangat mengganggu alur kerja kami."*

3. **Pelatihan yang Tidak Mencukupi**: Banyak pengguna merasa mereka tidak menerima pelatihan yang cukup untuk menggunakan sistem secara efektif. Seorang manajer departemen menyatakan, *"Kami hanya mendapatkan pelatihan satu hari sebelum sistem diluncurkan. Tidak ada pelatihan lanjutan atau dukungan berkelanjutan."*

### Rekomendasi dan Implementasi
Berdasarkan hasil evaluasi, tim mengusulkan beberapa rekomendasi untuk meningkatkan kinerja dan usability sistem ERP:

**Rekomendasi Teknis:**
1. **Optimasi Query Database**: Tim merekomendasikan untuk mengoptimasi query yang tidak efisien pada modul inventaris, termasuk penambahan indeks pada tabel yang sering diakses dan penulisan ulang query yang kompleks.
2. **Peningkatan Kapasitas Server**: Meningkatkan kapasitas server database, terutama CPU dan memori, untuk menangani beban transaksi yang lebih tinggi.
3. **Implementasi Caching**: Menerapkan mekanisme caching untuk data yang sering diakses untuk mengurangi beban pada database.

**Rekomendasi Non-Teknis:**
1. **Redesain Antarmuka Pengguna**: Menyederhanakan antarmuka pengguna modul inventaris untuk mengurangi jumlah langkah yang diperlukan untuk menyelesaikan tugas-tugas umum.
2. **Pelatihan Ulang Pengguna**: Melakukan pelatihan ulang untuk semua pengguna dengan fokus pada modul inventaris, termasuk sesi pelatihan praktis dan materi panduan yang lebih baik.
3. **Dukungan Berkelanjutan**: Membentuk tim dukungan internal yang tersedia untuk membantu pengguna mengatasi masalah dan menjawab pertanyaan.

**Implementasi dan Hasil:**
Perusahaan mengimplementasikan rekomendasi tersebut dalam tiga tahap:

1. **Tahap 1 (Minggu 1-4)**: Optimasi query database dan peningkatan kapasitas server. Setelah implementasi, latency modul inventaris berkurang dari 8,2 detik menjadi 1,5 detik, dan throughput meningkat dari 15 menjadi 55 transaksi per menit.
2. **Tahap 2 (Minggu 5-8)**: Redesain antarmuka pengguna modul inventaris. Antarmuka baru disederhanakan dengan mengurangi jumlah langkah untuk tugas umum dari 5 menjadi 2 langkah.
3. **Tahap 3 (Minggu 9-12)**: Pelatihan ulang pengguna dan pembentukan tim dukungan internal. Semua pengguna menerima pelatihan satu hari penuh dengan fokus pada modul inventaris, dan tim dukungan internal dibentuk dengan 3 anggota.

Tiga bulan setelah implementasi, survei kepuasan pengguna ulang menunjukkan peningkatan signifikan, dengan 78% pengguna melaporkan kepuasan terhadap sistem ERP (rating rata-rata 4,2 dari skala 5). Tingkat adopsi pengguna juga meningkat dari 65% menjadi 92%.

### Contoh Laporan/Dashboard
Tim evaluasi membuat **dashboard interaktif** untuk manajemen yang memungkinkan pemantauan kinerja sistem secara real-time. Dashboard ini dirancang menggunakan prinsip visualisasi data dari Bab 7 dan mencakup:

1. **Grafik Waktu Respons**: Menampilkan latency rata-rata untuk setiap modul dalam grafik garis yang diperbarui setiap 5 menit.
2. **Peta Panas Penggunaan**: Menunjukkan modul mana yang paling sering digunakan dan pada waktu tertentu.
3. **Indikator Kinerja Utama (KPI)**: Menampilkan throughput, error rate, dan tingkat adopsi pengguna dalam format yang mudah dibaca.
4. **Alert Otomatis**: Memberikan notifikasi otomatis kepada tim IT jika latency melebihi ambang batas yang ditentukan atau jika terjadi penurunan kinerja yang signifikan.

Dashboard ini diakses oleh manajemen melalui portal web dan telah menjadi alat penting untuk pemantauan kinerja sistem dan pengambilan keputusan. Manajer IT menyatakan, *"Dashboard ini memungkinkan kami untuk mengidentifikasi masalah kinerja sebelum mereka mempengaruhi pengguna. Kami dapat bersifat proaktif daripada reaktif dalam mengelola sistem ERP."*

## 8.2 Studi Kasus: Evaluasi Sistem IoT untuk Smart Farming

### Konteks Sistem
AgriTech Solutions adalah sebuah startup agrikultur yang telah mengembangkan sistem sensor IoT untuk irigasi otomatis dalam pertanian cerdas (smart farming). Sistem ini terdiri dari ratusan sensor kelembaban tanah, sensor suhu, dan sensor curah hujan yang tersebar di lahan pertanian seluas 50 hektar. Data dari sensor-sensor ini dikirim ke pusat data untuk dianalisis, dan sistem secara otomatis mengaktifkan sistem irigasi ketika kelembaban tanah turun di bawah ambang batas tertentu.

Setelah satu tahun operasi, manajemen AgriTech Solutions ingin mengevaluasi efektivitas sistem mereka. Mereka mendapatkan laporan yang beragam dari petani mitra; beberapa melaporkan penghematan air yang signifikan dan peningkatan hasil panen, sementara yang lain mengeluhkan ketidakkonsistenan dalam irigasi dan kerusakan sensor yang sering terjadi. Tujuan evaluasi ini adalah untuk mengukur keandalan (reliability) sistem, efektivitas dalam penghematan air, dan dampaknya terhadap hasil panen.

### Metodologi Evaluasi
Tim evaluasi mengadopsi pendekatan yang berfokus pada metrik kinerja dan keandalan sistem IoT, dengan mempertimbangkan karakteristik unik dari sistem terdistribusi ini. Evaluasi ini menggabungkan analisis data kuantitatif dari sensor dengan data kualitatif dari pengguna (petani).

**Pengumpulan Data Kuantitatif:**
1. **Analisis Log Sensor**: Tim mengumpulkan log dari semua sensor selama periode 6 bulan untuk menganalisis metrik **Availability** (ketersediaan sensor) dan **MTBF** (Mean Time Between Failures). Log ini mencakup status operasional, frekuensi pengiriman data, dan catatan kesalahan.
2. **Pengukuran Konsumsi Air**: Tim membandingkan data konsumsi air dari sistem irigasi otomatis dengan data historis konsumsi air sebelum implementasi sistem IoT.
3. **Analisis Data Hasil Panen**: Tim mengumpulkan data hasil panen dari lahan yang menggunakan sistem IoT dan membandingkannya dengan lahan kontrol yang menggunakan metode irigasi tradisional.
4. **Pengukuran Akurasi Sensor**: Tim melakukan kalibrasi ulang pada sampel acak sensor untuk memverifikasi akurasi pembacaan kelembaban tanah.

**Pengumpulan Data Kualitatif:**
1. **Wawancara dengan Petani**: Tim melakukan wawancara dengan 15 petani yang menggunakan sistem IoT untuk memahami pengalaman mereka, persepsi tentang efektivitas sistem, dan masalah yang dihadapi.
2. **Observasi Lapangan**: Tim melakukan observasi langsung di 5 lahan pertanian untuk melihat kondisi sensor di lapangan dan bagaimana sistem berinteraksi dengan lingkungan.
3. **Fokus Grup**: Tim mengadakan sesi fokus grup dengan petani untuk mendapatkan umpan balik mendalam tentang sistem dan saran untuk perbaikan.

**Analisis Data:**
Data kuantitatif dianalisis menggunakan teknik **analisis statistik** dari Bab 6, termasuk analisis tren waktu dan **analisis regresi** untuk mengeksplorasi hubungan antara variabel-variabel seperti penggunaan air, kelembaban tanah, dan hasil panen. Tim juga menggunakan **triangulasi data** (Bab 3) dengan membandingkan data sensor dengan data panen manual untuk memvalidasi temuan.

### Hasil Evaluasi
**Hasil Kuantitatif:**
Analisis log sensor menunjukkan bahwa **Availability** rata-rata sensor adalah 87%, dengan variasi yang signifikan antar lokasi. **MTBF** rata-rata adalah 45 hari, yang berarti sensor rata-rata mengalami kegagalan setiap 45 hari. Analisis lebih lanjut mengungkapkan bahwa sensor yang terletak di area dengan paparan sinar matahari langsung memiliki tingkat kegagalan 40% lebih tinggi dibandingkan dengan sensor yang terletak di area teduh.

Analisis konsumsi air menunjukkan penghematan rata-rata 32% dibandingkan dengan metode irigasi tradisional, dengan variasi antar lahan dari 15% hingga 48%. **Analisis regresi** mengungkapkan korelasi positif yang kuat (r = 0,78) antara akurasi pembacaan sensor kelembaban tanah dan tingkat penghematan air.

Data hasil panen menunjukkan peningkatan rata-rata 18% pada lahan yang menggunakan sistem IoT dibandingkan dengan lahan kontrol. Namun, ada korelasi negatif (r = -0,65) antara jumlah kegagalan sensor dan peningkatan hasil panen, menunjukkan bahwa keandalan sistem sangat mempengaruhi efektivitasnya.

**Hasil Kualitatif:**
Wawancara dan observasi lapangan mengungkapkan beberapa temuan penting:

1. **Masalah Ketahanan Sensor**: Banyak petani melaporkan bahwa sensor sering rusak karena kondisi lingkungan yang keras, terutama paparan sinar matahari dan hujan lebat. Seorang petani menyatakan, *"Saya harus mengganti sensor di lahan saya setiap dua bulan karena mereka rusak akibat panas dan hujan. Ini sangat merepotkan dan mahal."*

2. **Ketidakkonsistenan Irigasi**: Beberapa petani mengeluhkan ketidakkonsistenan dalam irigasi, di mana beberapa area mendapatkan terlalu banyak air sementara area lain tidak mendapatkan cukup. Seorang petani mengatakan, *"Terkadang sistem mengaktifkan irigasi meskipun tanah sudah cukup lembab, mungkin karena sensor memberikan pembacaan yang salah."*

3. **Manfaat Nyata**: Meskipun ada masalah, banyak petani mengakui manfaat nyata dari sistem, terutama dalam penghematan air dan peningkatan hasil panen. Seorang petani menyatakan, *"Meskipun ada beberapa masalah dengan sensor, saya melihat peningkatan hasil panen saya sekitar 20% dan penghematan air sekitar 30%. Ini sangat membantu bisnis saya."*

### Rekomendasi dan Implementasi
Berdasarkan hasil evaluasi, tim mengusulkan beberapa rekomendasi untuk meningkatkan keandalan dan efektivitas sistem IoT:

**Rekomendasi Teknis:**
1. **Peningkatan Ketahanan Sensor**: Tim merekomendasikan untuk mengganti sensor yang ada dengan model yang lebih tahan terhadap kondisi lingkungan keras, terutama yang memiliki perlindungan yang lebih baik terhadap sinar matahari dan air.
2. **Penggantian Batch Sensor**: Mengganti semua sensor yang telah beroperasi lebih dari 40 hari secara preventif untuk mengurangi risiko kegagalan tak terduga.
3. **Penyesuaian Algoritma Irigasi**: Menyempurnakan algoritma irigasi untuk mempertimbangkan lebih banyak variabel, seperti curah hujan yang diprediksi dan jenis tanaman, serta menambahkan mekanisme validasi untuk mendeteksi pembacaan sensor yang tidak akurat.
4. **Implementasi Redundansi**: Menambahkan sensor redundan di area kritis untuk memastikan keandalan sistem bahkan jika beberapa sensor gagal.

**Rekomendasi Non-Teknis:**
1. **Pelatihan untuk Petani**: Memberikan pelatihan kepada petani tentang cara merawat sensor dan memahami data yang dihasilkan sistem.
2. **Program Pemeliharaan Preventif**: Membuat jadwal pemeliharaan preventif reguler untuk memeriksa dan mengganti sensor sebelum mereka gagal.
3. **Sistem Umpan Balik**: Membangun sistem umpan balik yang memungkinkan petani melaporkan masalah dengan mudah dan memberikan saran untuk perbaikan.

**Implementasi dan Hasil:**
AgriTech Solutions mengimplementasikan rekomendasi tersebut dalam beberapa tahap:

1. **Tahap 1 (Bulan 1-2)**: Penggantian semua sensor yang ada dengan model yang lebih tahan terhadap kondisi lingkungan keras. Sensor baru memiliki casing yang lebih kuat dan perlindungan UV yang lebih baik.
2. **Tahap 2 (Bulan 3)**: Penyesuaian algoritma irigasi untuk mempertimbangkan lebih banyak variabel dan menambahkan mekanisme validasi. Tim juga mengimplementasikan sistem redundansi di area kritis.
3. **Tahap 3 (Bulan 4)**: Pelatihan untuk petani dan pembentukan program pemeliharaan preventif. Setiap petani menerima pelatihan satu hari tentang cara merawat sensor dan memahami data sistem.
4. **Tahap 4 (Bulan 5-6)**: Implementasi sistem umpan balik dan monitoring berkelanjutan untuk mengevaluasi efektivitas perubahan.

Enam bulan setelah implementasi, evaluasi ulang menunjukkan peningkatan signifikan dalam kinerja sistem:
- **Availability** sensor meningkat dari 87% menjadi 96%.
- **MTBF** meningkat dari 45 hari menjadi 85 hari.
- Penghematan air meningkat dari rata-rata 32% menjadi 41%.
- Peningkatan hasil panen meningkat dari rata-rata 18% menjadi 25%.

### Contoh Laporan/Dashboard
Tim evaluasi membuat **laporan teknis** yang komprehensif untuk tim engineering AgriTech Solutions. Laporan ini dirancang untuk memberikan detail analisis mendalam tentang kinerja sistem dan area yang memerlukan perbaikan. Laporan ini mencakup:

1. **Analisis Kegagalan Sensor**: Bagian ini menganalisis pola kegagalan sensor, termasuk grafik yang menunjukkan hubungan antara lokasi sensor, usia, dan tingkat kegagalan.
2. **Grafik Tren Ketersediaan Sensor**: Visualisasi yang menunjukkan ketersediaan sensor dari waktu ke waktu, dengan pemisahan berdasarkan lokasi dan jenis sensor.
3. **Analisis Regresi**: Grafik scatter plot yang menunjukkan hubungan antara variabel-variabel seperti penggunaan air, kelembaban tanah, dan hasil panen, dengan garis tren dan koefisien korelasi.
4. **Peta Panas Masalah**: Visualisasi geografis yang menunjukkan area dengan masalah sensor yang paling sering terjadi.
5. **Rekomendasi Prioritas**: Daftar rekomendasi yang diprioritaskan berdasarkan potensi dampak dan biaya implementasi.

Kepala tim engineering menyatakan, *"Laporan ini memberikan wawasan yang sangat berharga tentang kinerja sistem kami. Analisis mendalam tentang pola kegagalan sensor membantu kami membuat keputusan yang lebih baik tentang peningkatan perangkat keras, sementara analisis regresi membantu kami menyempurnakan algoritma irigasi kami."*

## 8.3 Studi Kasus: Evaluasi Sistem AI untuk Deteksi Penipuan

### Konteks Sistem
FinSecure adalah perusahaan fintech yang telah mengembangkan model AI untuk deteksi penipuan transaksi keuangan. Model ini dirancang untuk menganalisis pola transaksi dan mengidentifikasi aktivitas yang mencurigakan secara real-time. Sistem ini telah diimplementasikan selama 4 bulan dan telah memproses jutaan transaksi.

Setelah implementasi awal, tim manajemen FinSecure ingin mengevaluasi kinerja model AI mereka. Mereka mendapat laporan dari tim keamanan bahwa model berhasil mendeteksi banyak kasus penipuan, tetapi juga ada kekhawatiran tentang potensi bias dalam model yang mungkin menyebabkan penolakan transaksi yang tidak adil untuk kelompok nasabah tertentu. Tujuan evaluasi ini adalah untuk mengukur akurasi model, mengidentifikasi potensi bias, dan menilai keamanan implementasi model.

### Metodologi Evaluasi
Tim evaluasi mengadopsi pendekatan yang komprehensif untuk menilai kinerja dan keamanan model AI, dengan fokus khusus pada akurasi dan potensi bias. Evaluasi ini menggabungkan analisis kuantitatif dari kinerja model dengan analisis kualitatif dari dampak bisnis dan etika.

**Pengumpulan Data Kuantitatif:**
1. **Analisis Kinerja Model**: Tim mengumpulkan data kinerja model selama periode 4 bulan, termasuk metrik **Precision**, **Recall**, dan **F1-Score** sebagai metrik efektivitas (Bab 4). Data ini dianalisis secara keseluruhan dan berdasarkan segmen demografis nasabah.
2. **Analisis Confusion Matrix**: Tim membuat confusion matrix untuk mengevaluasi kinerja model dalam mengklasifikasikan transaksi sebagai penipuan atau bukan.
3. **Analisis Bias**: Tim menganalisis tingkat kesalahan model (false positive dan false negative) berdasarkan segmen demografis seperti usia, lokasi geografis, dan jenis akun.
4. **Pengujian Keamanan**: Tim melakukan serangkaian pengujian keamanan untuk mengidentifikasi potensi kerentanan dalam implementasi model, termasuk **Security Code Review** (Bab 5) untuk memeriksa kerentanan dalam kode.

**Pengumpulan Data Kualitatif:**
1. **Wawancara dengan Tim Keamanan**: Tim melakukan wawancara dengan anggota tim keamanan yang menggunakan sistem untuk memahami pengalaman mereka dengan model dan masalah yang dihadapi.
2. **Analisis Kasus Penolakan Transaksi**: Tim menganalisis sampel acak kasus penolakan transaksi untuk memahami konteks dan dampaknya terhadap nasabah.
3. **Fokus Grup dengan Nasabah**: Tim mengadakan sesi fokus grup dengan nasabah yang transaksinya ditolak oleh sistem untuk memahami pengalaman dan persepsi mereka.

**Analisis Data:**
Data kuantitatif dianalisis menggunakan teknik **analisis statistik** dari Bab 6, termasuk uji hipotesis untuk membandingkan kinerja model antar segmen demografis. Data kualitatif dianalisis menggunakan teknik analisis tematik untuk mengidentifikasi pola dan tema yang muncul dari wawancara dan fokus grup.

### Hasil Evaluasi
**Hasil Kuantitatif:**
Analisis kinerja model menunjukkan bahwa secara keseluruhan, model memiliki **Precision** sebesar 92%, **Recall** sebesar 85%, dan **F1-Score** sebesar 88%. Ini menunjukkan bahwa model cukup efektif dalam mendeteksi penipuan. Namun, analisis lebih mendalam berdasarkan segmen demografis mengungkapkan perbedaan signifikan:

1. **Berdasarkan Usia**: Model memiliki **F1-Score** 91% untuk nasabah di atas 40 tahun, tetapi hanya 76% untuk nasabah di bawah 25 tahun. Uji hipotesis menunjukkan perbedaan ini signifikan secara statistik (p < 0,001).
2. **Berdasarkan Lokasi Geografis**: Model memiliki **F1-Score** 90% untuk nasabah di area perkotaan, tetapi hanya 79% untuk nasabah di area pedesaan.
3. **Berdasarkan Jenis Akun**: Model memiliki **F1-Score** 90% untuk nasabah dengan akun premium, tetapi hanya 80% untuk nasabah dengan akun standar.

**Confusion matrix** mengungkapkan bahwa model memiliki tingkat false positive yang lebih tinggi untuk nasabah muda dan dari area pedesaan, yang berarti transaksi mereka lebih sering ditolak secara salah. Sebaliknya, model memiliki tingkat false negative yang lebih tinggi untuk nasabah dengan akun premium, yang berarti beberapa penipuan mungkin tidak terdeteksi untuk segmen ini.

**Security Code Review** mengidentifikasi beberapa kerentanan potensial dalam implementasi model, termasuk:
1. Validasi input yang tidak memadai yang dapat dieksploitasi untuk serangan injection.
2. Logging yang tidak lengkap untuk aktivitas model, yang dapat menghambat investigasi keamanan.
3. Enkripsi data yang tidak konsisten dalam penyimpanan dan transmisi.

**Hasil Kualitatif:**
Wawancara dan fokus grup mengungkapkan beberapa temuan penting:

1. **Frustrasi Nasabah Muda**: Banyak nasabah muda melaporkan frustrasi karena transaksi mereka sering ditolak. Seorang nasabah berusia 22 tahun menyatakan, *"Saya sering tidak bisa melakukan pembelian online karena transaksi saya ditolak. Padahal saya tidak pernah melakukan penipuan. Ini sangat menjengkelkan."*

2. **Kekhawatiran Tim Keamanan**: Anggota tim keamanan mengungkapkan kekhawatiran tentang potensi bias dalam model. Seorang analis keamanan menyatakan, *"Kami melihat pola yang mencurigakan di mana transaksi dari nasabah muda dan dari area pedesaan lebih sering ditandai sebagai mencurigakan. Kami khawatir ini mungkin mencerminkan bias dalam data pelatihan atau algoritma."*

3. **Dampak Bisnis**: Manajer bisnis mengungkapkan bahwa penolakan transaksi yang salah telah menyebabkan kehilangan nasabah dan kerusakan reputasi. Seorang manajer menyatakan, *"Kami kehilangan sekitar 5% nasabah muda kami dalam tiga bulan terakhir karena mereka frustrasi dengan transaksi mereka yang sering ditolak. Ini berdampak signifikan pada bisnis kami."*

### Rekomendasi dan Implementasi
Berdasarkan hasil evaluasi, tim mengusulkan beberapa rekomendasi untuk meningkatkan akurasi model, mengurangi bias, dan memperkuat keamanan:

**Rekomendasi Teknis:**
1. **Retraining Model dengan Data yang Lebih Seimbang**: Tim merekomendasikan untuk melakukan retraining model dengan dataset yang lebih seimbang secara demografis untuk mengurangi bias. Ini termasuk pengumpulan data tambahan dari segmen yang terwakili secara tidak memadai dan penggunaan teknik oversampling atau undersampling.
2. **Implementasi Continuous Monitoring**: Menerapkan sistem monitoring berkelanjutan untuk melacak kinerja model dan mendeteksi bias yang muncul dari waktu ke waktu.
3. **Perbaikan Keamanan**: Mengatasi kerentanan yang diidentifikasi melalui Security Code Review, termasuk penerapan validasi input yang lebih kuat, logging yang lebih lengkap, dan enkripsi data yang konsisten.
4. **Implementasi Explainable AI**: Menggunakan teknik Explainable AI untuk meningkatkan transparansi model dan memahami faktor-faktor yang mempengaruhi keputusan model.

**Rekomendasi Non-Teknis:**
1. **Proses Peninjauan Manual**: Membuat proses peninjauan manual untuk transaksi yang ditolak, terutama untuk nasabah dari segmen yang memiliki tingkat false positive tinggi.
2. **Program Komunikasi dengan Nasabah**: Mengembangkan program komunikasi yang lebih baik dengan nasabah yang transaksinya ditolak, termasuk penjelasan yang jelas tentang alasan penolakan dan langkah-langkah yang dapat diambil.
3. **Pelatihan Kesadaran Bias**: Memberikan pelatihan kepada tim pengembang dan analis tentang potensi bias dalam model AI dan cara mengidentifikasi serta menguranginya.

**Implementasi dan Hasil:**
FinSecure mengimplementasikan rekomendasi tersebut dalam beberapa tahap:

1. **Tahap 1 (Minggu 1-4)**: Perbaikan keamanan untuk mengatasi kerentanan yang diidentifikasi. Tim juga mengimplementasikan sistem monitoring berkelanjutan untuk melacak kinerja model.
2. **Tahap 2 (Minggu 5-8)**: Pengumpulan data tambahan dan retraining model dengan dataset yang lebih seimbang. Tim juga mengimplementasikan teknik Explainable AI untuk meningkatkan transparansi model.
3. **Tahap 3 (Minggu 9-10)**: Implementasi proses peninjauan manual untuk transaksi yang ditolak dan pengembangan program komunikasi dengan nasabah.
4. **Tahap 4 (Minggu 11-12)**: Pelatihan kesadaran bias untuk tim pengembang dan analis.

Tiga bulan setelah implementasi, evaluasi ulang menunjukkan peningkatan signifikan dalam kinerja dan keadilan model:
- **F1-Score** keseluruhan meningkat dari 88% menjadi 92%.
- Perbedaan **F1-Score** antar segmen demografis berkurang secara signifikan, dengan perbedaan maksimum hanya 4% (dibandingkan sebelumnya hingga 15%).
- Tingkat kehilangan nasabah berkurang dari 5% menjadi 1,2%.
- Tidak ada kerentanan keamanan baru yang diidentifikasi dalam pengujian ulang.

### Contoh Laporan/Dashboard
Tim evaluasi membuat **laporan eksekutif** yang dirancang untuk menyajikan temuan kunci dan rekomendasi kepada manajemen senior dan dewan direksi. Laporan ini difokuskan pada dampak bisnis dan risiko, serta menggunakan prinsip visualisasi data dari Bab 7 untuk menyajikan informasi secara jelas dan persuasif. Laporan ini mencakup:

1. **Ringkasan Eksekutif**: Bagian singkat yang merangkum temuan utama, rekomendasi, dan potensi dampak bisnis.
2. **Confusion Matrix**: Visualisasi yang menunjukkan kinerja model dalam mengklasifikasikan transaksi, dengan perbandingan antara sebelum dan sesudah perbaikan.
3. **Analisis Dampak Bisnis**: Grafik yang menunjukkan hubungan antara bias model dan tingkat kehilangan nasabah, serta proyeksi ROI dari perbaikan model.
4. **Peta Panas Risiko**: Visualisasi yang menunjukkan area risiko tertinggi dalam hal bias model dan kerentanan keamanan.
5. **Rencana Implementasi**: Tabel yang merangkum rekomendasi, timeline implementasi, dan perkiraan biaya.

CEO FinSecure menyatakan, *"Laporan ini sangat membantu kami memahami tidak hanya masalah teknis dengan model AI kami, tetapi juga dampak bisnis yang lebih luas. Visualisasi yang jelas tentang hubungan antara bias model dan kehilangan nasabah membantu kami memprioritaskan investasi dalam perbaikan model."*

## 8.4 Pembelajaran Kunci dari Studi Kasus

Dari ketiga studi kasus yang telah dibahas, kita dapat menarik beberapa pembelajaran kunci yang dapat diterapkan dalam evaluasi sistem secara umum. Pembelajaran ini mencakup perbandingan tantangan unik dari setiap jenis sistem dan best practices yang dapat diadopsi oleh pembaca.

### Perbandingan Tantangan Unik Setiap Jenis Sistem

| Aspek | Sistem Enterprise (ERP) | Sistem IoT (Smart Farming) | Sistem AI (Deteksi Penipuan) |
|-------|-------------------------|---------------------------|------------------------------|
| **Kinerja** | Tantangan utama pada latency dan throughput, terutama saat beban pengguna tinggi. Bottleneck sering terjadi pada tingkat database. | Tantangan utama pada ketersediaan (availability) dan keandalan sensor di lingkungan yang keras. Konsumsi daya dan bandwidth juga menjadi pertimbangan penting. | Tantangan utama pada akurasi model dan waktu inferensi. Keseimbangan antara precision dan recall sering menjadi pertimbangan kritis. |
| **Skalabilitas** | Skalabilitas vertikal (peningkatan kapasitas server) sering diperlukan untuk menangani pertumbuhan pengguna dan data. | Skalabilitas horizontal (penambahan sensor) sering diperlukan, tetapi harus diimbangi dengan manajemen kompleksitas dan biaya. | Skalabilitas model untuk menangani volume transaksi yang tinggi dan pertumbuhan data pelatihan. |
| **Keamanan** | Fokus pada keamanan data transaksional, akses pengguna, dan integritas data. | Fokus pada keamanan perangkat, komunikasi nirkabel, dan privasi data sensor. | Fokus pada keamanan model, keamanan data, dan potensi serangan adversarial. |
| **Usability** | Antarmuka pengguna yang kompleks sering menjadi hambatan adopsi. Pelatihan pengguna menjadi kunci sukses. | Antarmuka yang sederhana dan intuitif penting untuk pengguna dengan latar belakang teknis yang terbatas. | Transparansi model dan kemampuan untuk menjelaskan keputusan menjadi penting untuk kepercayaan pengguna. |
| **Integrasi** | Integrasi dengan sistem legasi dan proses bisnis yang ada sering menjadi tantangan. | Integrasi dengan perangkat keras (sensor, aktuator) dan sistem eksternal (cuaca, pasar). | Integrasi dengan sistem transaksional, sistem keamanan, dan sistem pelaporan. |
| **Pemeliharaan** | Pemeliharaan rutin diperlukan untuk memastikan kinerja optimal, termasuk optimasi database dan pembaruan perangkat lunak. | Pemeliharaan preventif untuk sensor sangat penting karena kerusakan perangkat keras sering terjadi di lingkungan yang keras. | Pemeliharaan model termasuk retraining periodik dan monitoring drift data. |

### Best Practices dari Studi Kasus

Berdasarkan pengalaman dari ketiga studi kasus, berikut adalah beberapa best practices yang dapat diadopsi dalam evaluasi sistem:

1. **Pendekatan Holistik**: Evaluasi sistem harus mengadopsi pendekatan holistik yang mempertimbangkan tidak hanya aspek teknis, tetapi juga aspek manusia, proses, dan bisnis. Seperti yang terlihat dalam studi kasus ERP, masalah teknis (kinerja database) sering terkait erat dengan masalah non-teknis (pelatihan pengguna).

2. **Metodologi Mixed Methods**: Kombinasi metode kuantitatif dan kualitatif memberikan pemahaman yang lebih kaya dan mendalam tentang masalah yang ada. Dalam studi kasus IoT, analisis data kuantitatif tentang kinerja sensor diperkaya dengan wawancara kualitatif dengan petani untuk memahami konteks penggunaan di lapangan.

3. **Fokus pada Metrik yang Relevan**: Identifikasi dan fokus pada metrik yang paling relevan untuk sistem yang dievaluasi. Dalam studi kasus AI, metrik seperti precision, recall, dan F1-score lebih relevan daripada metrik kinerja tradisional seperti latency atau throughput.

4. **Analisis Berbasis Segmen**: Analisis kinerja sistem berdasarkan segmen pengguna atau konteks penggunaan dapat mengungkapkan ketidakkonsistenan yang mungkin tidak terlihat dalam analisis agregat. Dalam studi kasus AI, analisis berbasis segmen demografis mengungkapkan bias yang signifikan dalam model.

5. **Visualisasi Data yang Efektif**: Visualisasi data yang efektif sangat penting untuk komunikasi temuan kepada pemangku kepentingan. Dalam ketiga studi kasus, visualisasi seperti grafik tren, confusion matrix, dan peta panas membantu menyajikan informasi kompleks secara jelas dan persuasif.

6. **Iteratif dan Berkelanjutan**: Evaluasi sistem harus dilakukan secara iteratif dan berkelanjutan, bukan sebagai aktivitas satu kali. Seperti yang terlihat dalam studi kasus AI, continuous monitoring memungkinkan deteksi dini masalah seperti drift data atau degradasi kinerja model.

7. **Pertimbangan Etika**: Terutama untuk sistem AI dan sistem yang memproses data sensitif, pertimbangan etika harus menjadi bagian integral dari evaluasi. Dalam studi kasus AI, analisis bias bukan hanya pertimbangan teknis, tetapi juga etika dan bisnis.

8. **Keterlibatan Pemangku Kepentingan**: Keterlibatan aktif pemangku kepentingan sepanjang proses evaluasi sangat penting untuk memastikan bahwa evaluasi relevan dan hasilnya dapat diimplementasikan. Dalam studi kasus ERP, keterlibatan manajemen dan pengguna sangat penting untuk keberhasilan implementasi rekomendasi.

9. **Perencanaan Implementasi**: Rekomendasi dari evaluasi harus disertai dengan perencanaan implementasi yang jelas, termasuk prioritas, timeline, dan perkiraan biaya. Dalam studi kasus IoT, implementasi bertahap memungkinkan perusahaan untuk mengelola perubahan secara efektif dan mengukur dampak setiap intervensi.

10. **Pembelajaran Organisasional**: Hasil evaluasi harus digunakan untuk pembelajaran organisasional dan perbaikan proses. Dalam ketiga studi kasus, pelajaran dari evaluasi tidak hanya digunakan untuk memperbaiki sistem yang dievaluasi, tetapi juga untuk meningkatkan proses pengembangan dan evaluasi sistem di masa depan.

### Kesimpulan

Ketiga studi kasus ini menunjukkan bagaimana konsep dan metodologi dari Bab 1 hingga 7 dapat diterapkan dalam evaluasi sistem di dunia nyata. Meskipun setiap jenis sistem memiliki tantangan unik, ada prinsip-prinsip umum yang dapat diterapkan dalam evaluasi sistem apa pun:

- Pendekatan sistematis dan terstruktur
- Kombinasi metode kuantitatif dan kualitatif
- Fokus pada metrik yang relevan
- Analisis berbasis segmen
- Visualisasi data yang efektif
- Iteratif dan berkelanjutan
- Pertimbangan etika
- Keterlibatan pemangku kepentingan
- Perencanaan implementasi
- Pembelajaran organisasional

Dengan menerapkan prinsip-prinsip ini, praktisi dapat melakukan evaluasi sistem yang efektif yang tidak hanya mengidentifikasi masalah, tetapi juga memberikan rekomendasi yang dapat diimplementasikan untuk meningkatkan kinerja, keandalan, dan nilai sistem.

Studi kasus ini juga menunjukkan bahwa evaluasi sistem bukan hanya aktivitas teknis, tetapi juga aktivitas bisnis yang strategis. Hasil evaluasi dapat memiliki dampak signifikan pada kepuasan pengguna, efisiensi operasional, keunggulan kompetitif, dan bahkan keberlanjutan organisasi. Oleh karena itu, evaluasi sistem harus didekati dengan serius dan profesional, dengan menggunakan metodologi yang tepat dan fokus pada pencapaian tujuan bisnis.