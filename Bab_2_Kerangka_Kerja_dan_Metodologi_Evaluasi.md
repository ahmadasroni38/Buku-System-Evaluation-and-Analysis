# BAB 2
# KERANGKA KERJA DAN METODOLOGI EVALUASI

## Pendahuluan

Evaluasi sistem informasi memerlukan pendekatan yang terstruktur dan metodologis untuk menghasilkan penilaian yang objektif dan komprehensif. Kerangka kerja evaluasi (evaluation framework) menyediakan struktur konseptual yang memandu evaluator dalam merencanakan, melaksanakan, dan melaporkan hasil evaluasi. Pemilihan kerangka kerja yang tepat sangat menentukan validitas dan reliabilitas hasil evaluasi, serta kesesuaiannya dengan konteks organisasi yang dievaluasi.

Bab ini menguraikan berbagai model evaluasi sistem yang telah teruji dalam praktik industri dan riset akademik, mulai dari Capability Maturity Model Integration (CMMI), ISO/IEC 25000 (SQuaRE), hingga Total Quality Management (TQM). Selain itu, bab ini juga membahas pendekatan metodologis dalam evaluasi, baik kualitatif, kuantitatif, maupun campuran (mixed methods), yang masing-masing memiliki kekuatan dan keterbatasan tersendiri. Pemahaman menyeluruh terhadap kerangka kerja dan metodologi ini akan membekali evaluator dengan kemampuan memilih dan mengadaptasi pendekatan yang paling sesuai dengan tujuan evaluasi dan karakteristik organisasi.

---

## 2.1 Model Evaluasi Sistem

Model evaluasi sistem adalah kerangka konseptual yang menyediakan struktur, kriteria, dan pedoman untuk menilai kualitas, kematangan, dan kinerja sistem informasi. Model-model ini dikembangkan berdasarkan best practices industri dan penelitian akademik yang ekstensif, serta telah divalidasi melalui implementasi di berbagai sektor. Pemahaman terhadap berbagai model evaluasi memungkinkan organisasi untuk memilih pendekatan yang paling sesuai dengan kebutuhan, budaya, dan tingkat kematangan mereka.

Tiga model yang akan dibahas dalam bagian ini—CMMI, ISO/IEC 25000, dan TQM—mewakili pendekatan yang berbeda namun saling melengkapi dalam evaluasi sistem. CMMI berfokus pada kematangan proses dan kemampuan organisasi, ISO/IEC 25000 menekankan pada kualitas produk perangkat lunak, sedangkan TQM mengadopsi perspektif holistik tentang kualitas total dalam organisasi. Ketiga model ini telah menjadi standar de facto dalam industri teknologi informasi global dan banyak diadopsi oleh organisasi yang ingin meningkatkan kualitas sistem informasi mereka secara sistematis.

### 2.1.1 Capability Maturity Model Integration (CMMI)

Capability Maturity Model Integration (CMMI) adalah model perbaikan proses yang dikembangkan oleh Software Engineering Institute (SEI) di Carnegie Mellon University untuk membantu organisasi meningkatkan proses pengembangan dan pemeliharaan produk serta layanan mereka. CMMI menyediakan framework yang komprehensif untuk menilai kematangan proses organisasi dan mengidentifikasi area yang memerlukan perbaikan. Model ini telah berkembang dari fokus awal pada pengembangan perangkat lunak menjadi framework yang lebih luas yang mencakup pengembangan produk, akuisisi, dan layanan.

CMMI dibangun berdasarkan premis bahwa kualitas sistem adalah hasil langsung dari kualitas proses yang digunakan untuk mengembangkan dan memeliharanya. Dengan meningkatkan kematangan proses, organisasi dapat secara sistematis mengurangi variabilitas, meningkatkan prediktabilitas, dan mengoptimalkan kinerja. Model ini telah diadopsi secara luas di berbagai industri, mulai dari teknologi informasi, pertahanan, kesehatan, hingga manufaktur, karena kemampuannya memberikan roadmap yang jelas untuk perbaikan berkelanjutan.

#### 2.1.1.1 Struktur dan Tingkat Kematangan

CMMI menggunakan dua representasi (representation): staged dan continuous. Representasi staged mengklasifikasikan organisasi ke dalam lima tingkat kematangan (maturity levels), sedangkan representasi continuous memungkinkan organisasi untuk mengukur kemampuan (capability) setiap area proses secara independen. Dalam praktik evaluasi sistem, representasi staged lebih sering digunakan karena memberikan gambaran holistik tentang kematangan organisasi secara keseluruhan.

Lima tingkat kematangan dalam CMMI adalah: (1) Initial—proses tidak terprediksi, reaktif, dan seringkali kacau; (2) Managed—proyek dikelola dan prosesnya direncanakan, dilaksanakan, diukur, dan dikontrol; (3) Defined—proses dipahami dengan baik dan dijelaskan dalam standar, prosedur, tools, dan metode; (4) Quantitatively Managed—organisasi menggunakan data kuantitatif untuk memahami kinerja proses dan membuat keputusan; (5) Optimizing—organisasi berfokus pada perbaikan berkelanjutan berdasarkan pemahaman kuantitatif tentang tujuan bisnis dan kebutuhan kinerja. Setiap tingkat membangun fondasi untuk tingkat berikutnya, sehingga organisasi harus mencapai tingkat tertentu sebelum dapat secara efektif berpindah ke tingkat yang lebih tinggi.

Evolusi dari satu tingkat ke tingkat berikutnya memerlukan transformasi fundamental dalam cara organisasi mengelola proses. Misalnya, transisi dari Level 1 ke Level 2 memerlukan pengenalan manajemen proyek dasar dan kontrol komitmen, sedangkan transisi dari Level 3 ke Level 4 memerlukan pengenalan manajemen kuantitatif dan pemikiran statistik. Setiap peningkatan tingkat kematangan menghasilkan peningkatan yang terukur dalam kinerja organisasi, termasuk pengurangan biaya, peningkatan kualitas produk, dan pemenuhan jadwal yang lebih konsisten.

#### 2.1.1.2 Area Proses CMMI

CMMI terdiri dari 22 area proses (process areas) yang dikelompokkan ke dalam empat kategori: Process Management, Project Management, Engineering, dan Support. Setiap area proses mengidentifikasi praktik-praktik yang, ketika dilaksanakan secara kolektif, memenuhi serangkaian tujuan yang dianggap penting untuk membuat perbaikan yang signifikan dalam area tersebut. Area proses tidak bersifat preskriptif dalam implementasinya, melainkan deskriptif tentang karakteristik yang harus ada.

Kategori Process Management mencakup area proses seperti Organizational Process Definition (OPD), Organizational Process Focus (OPF), dan Organizational Training (OT), yang berfokus pada pembentukan dan perbaikan proses organisasi. Kategori Project Management meliputi area seperti Project Planning (PP), Project Monitoring and Control (PMC), dan Integrated Project Management (IPM), yang berkaitan dengan pengelolaan proyek individual. Kategori Engineering mencakup Requirements Management (REQM), Technical Solution (TS), dan Verification (VER), yang berhubungan dengan aktivitas pengembangan teknis. Kategori Support meliputi Configuration Management (CM), Process and Product Quality Assurance (PPQA), dan Measurement and Analysis (MA), yang menyediakan dukungan untuk area lainnya.

Dalam konteks evaluasi sistem, pemahaman terhadap area proses CMMI memungkinkan evaluator untuk mengidentifikasi gap spesifik dalam praktik organisasi. Misalnya, jika organisasi memiliki masalah dengan perubahan requirements yang tidak terkontrol, evaluator dapat fokus pada area proses Requirements Management dan Configuration Management. Setiap area proses memiliki specific goals dan generic goals yang harus dicapai, serta specific practices dan generic practices yang menjelaskan aktivitas yang dapat membantu mencapai tujuan tersebut.

#### 2.1.1.3 Implementasi CMMI dalam Evaluasi Sistem

Implementasi CMMI sebagai kerangka evaluasi sistem dimulai dengan assessment atau appraisal untuk menentukan tingkat kematangan organisasi saat ini. Standard CMMI Appraisal Method for Process Improvement (SCAMPI) adalah metode appraisal resmi yang paling komprehensif, meskipun ada juga metode appraisal yang lebih ringan seperti SCAMPI B dan C. Proses appraisal melibatkan review dokumen, wawancara dengan stakeholder, dan observasi praktik aktual untuk mengumpulkan bukti objektif tentang implementasi praktik CMMI.

Setelah baseline kematangan ditentukan, organisasi dapat mengembangkan roadmap perbaikan yang memprioritaskan area proses yang akan ditingkatkan. Prioritisasi ini harus mempertimbangkan tujuan bisnis organisasi, risiko yang dihadapi, dan ketergantungan antar area proses. Misalnya, organisasi yang baru memulai perjalanan CMMI biasanya fokus pada area proses Level 2 seperti Project Planning, Requirements Management, dan Configuration Management sebelum beralih ke area proses Level 3 yang lebih kompleks.

Implementasi CMMI memerlukan komitmen jangka panjang dan investasi signifikan dalam pelatihan, tools, dan perubahan budaya. Namun, studi empiris menunjukkan bahwa organisasi yang berhasil meningkatkan tingkat kematangan CMMI mengalami return on investment (ROI) yang positif melalui peningkatan produktivitas, pengurangan rework, dan peningkatan kepuasan pelanggan. Dalam konteks evaluasi sistem informasi, CMMI memberikan framework yang terstruktur untuk mengidentifikasi kelemahan proses yang mungkin berdampak pada kualitas, keamanan, atau kinerja sistem.

### 2.1.2 ISO/IEC 25000 (SQuaRE)

ISO/IEC 25000, yang dikenal sebagai Software Product Quality Requirements and Evaluation (SQuaRE), adalah keluarga standar internasional yang menyediakan panduan untuk spesifikasi dan evaluasi kualitas perangkat lunak. SQuaRE dikembangkan untuk menggantikan dan mengintegrasikan dua standar sebelumnya: ISO/IEC 9126 (model kualitas perangkat lunak) dan ISO/IEC 14598 (evaluasi produk perangkat lunak). Standar ini memberikan framework yang komprehensif dan koheren untuk mendefinisikan, mengukur, dan mengevaluasi kualitas produk perangkat lunak dari berbagai perspektif.

Pendekatan SQuaRE bersifat product-oriented, berfokus pada karakteristik kualitas yang dapat diamati dan diukur dari produk perangkat lunak itu sendiri, berbeda dengan CMMI yang berfokus pada proses. Standar ini relevan bagi berbagai stakeholder dalam siklus hidup perangkat lunak, termasuk pengembang yang perlu memenuhi spesifikasi kualitas, pemilik produk yang perlu mendefinisikan requirements kualitas, dan evaluator yang perlu menilai apakah produk memenuhi standar kualitas yang ditetapkan. SQuaRE telah menjadi referensi global dalam procurement perangkat lunak, quality assurance, dan certification.

#### 2.1.2.1 Arsitektur Standar ISO/IEC 25000

Keluarga standar ISO/IEC 25000 diorganisasikan ke dalam lima divisi (division) yang saling terkait, masing-masing memiliki tujuan spesifik dalam framework evaluasi kualitas. Divisi Quality Management (ISO/IEC 2500n) menyediakan overview dan terminology untuk seluruh keluarga standar serta model referensi yang menjelaskan hubungan antar standar. Divisi ini membantu organisasi memahami bagaimana berbagai komponen SQuaRE bekerja bersama-sama dalam sistem manajemen kualitas perangkat lunak.

Divisi Quality Model (ISO/IEC 2501n) mendefinisikan model kualitas untuk computer systems dan software products, termasuk karakteristik kualitas internal, eksternal, dan in-use. Divisi Quality Measurement (ISO/IEC 2502n) menyediakan metrik untuk mengukur karakteristik kualitas yang didefinisikan dalam model kualitas. Divisi Quality Requirements (ISO/IEC 2503n) membantu dalam spesifikasi requirements kualitas, yang dapat digunakan dalam proses elicitation dan definition dari quality requirements untuk produk perangkat lunak. Divisi Quality Evaluation (ISO/IEC 2504n) menyediakan requirements, rekomendasi, dan guidelines untuk evaluasi produk perangkat lunak.

Arsitektur modular ini memungkinkan organisasi untuk mengadopsi komponen SQuaRE yang paling relevan dengan kebutuhan mereka tanpa harus mengimplementasikan seluruh keluarga standar. Misalnya, organisasi yang fokus pada procurement dapat menggunakan divisi Quality Requirements untuk mendefinisikan ekspektasi kualitas dalam kontrak, sementara organisasi yang fokus pada quality assurance dapat lebih intensif menggunakan divisi Quality Measurement dan Quality Evaluation.

#### 2.1.2.2 Model Kualitas Perangkat Lunak ISO/IEC 25010

ISO/IEC 25010 mendefinisikan dua model kualitas yang saling melengkapi: quality in use model dan product quality model. Quality in use model mengukur sejauh mana produk memenuhi kebutuhan pengguna untuk mencapai tujuan spesifik dengan efektivitas, efisiensi, kepuasan, freedom from risk, dan context coverage. Model ini bersifat outcome-oriented dan mengukur dampak penggunaan sistem dalam konteks nyata. Lima karakteristik quality in use—effectiveness, efficiency, satisfaction, freedom from risk, dan context coverage—memberikan perspektif holistik tentang nilai yang diberikan sistem kepada pengguna dan organisasi.

Product quality model mendefinisikan delapan karakteristik kualitas yang dapat digunakan untuk mengevaluasi properti sistem dan perangkat lunak: (1) Functional Suitability—kemampuan produk menyediakan fungsi yang memenuhi kebutuhan; (2) Performance Efficiency—kinerja relatif terhadap jumlah sumber daya yang digunakan; (3) Compatibility—kemampuan produk bertukar informasi dan berbagi sumber daya dengan sistem lain; (4) Usability—kemampuan produk digunakan oleh pengguna untuk mencapai tujuan; (5) Reliability—kemampuan sistem melakukan fungsi yang ditentukan dalam kondisi tertentu; (6) Security—kemampuan melindungi informasi dan data; (7) Maintainability—kemampuan produk dimodifikasi secara efektif dan efisien; (8) Portability—kemampuan ditransfer dari satu lingkungan ke lingkungan lain.

Setiap karakteristik dibagi lagi menjadi sub-karakteristik yang lebih spesifik. Misalnya, Security dibagi menjadi confidentiality, integrity, non-repudiation, accountability, dan authenticity. Struktur hierarkis ini memungkinkan evaluator untuk melakukan analisis detail pada aspek kualitas tertentu yang menjadi prioritas. Dalam praktik evaluasi sistem informasi, pemilihan karakteristik dan sub-karakteristik yang akan dievaluasi harus disesuaikan dengan konteks penggunaan sistem dan prioritas stakeholder.

#### 2.1.2.3 Metrik Kualitas ISO/IEC 2502n

Divisi ISO/IEC 2502n menyediakan metrik kualitas (quality measures) yang dapat digunakan untuk mengukur karakteristik kualitas yang didefinisikan dalam ISO/IEC 25010. Metrik ini dibagi menjadi internal measures (diukur dari produk itu sendiri tanpa eksekusi), external measures (diukur dari perilaku sistem saat dieksekusi), dan quality in use measures (diukur dari pengalaman pengguna dalam konteks penggunaan nyata). Penggunaan metrik yang terstandarisasi memungkinkan komparabilitas hasil evaluasi antar produk dan organisasi.

Contoh metrik internal termasuk cyclomatic complexity untuk mengukur complexity dari kode, comment density untuk mengukur dokumentasi kode, dan coupling between objects untuk mengukur dependencies antar modul. Metrik eksternal mencakup mean time to failure (MTTF) untuk reliability, response time untuk performance efficiency, dan task completion rate untuk usability. Metrik quality in use termasuk task effectiveness, task efficiency, user satisfaction scores, dan freedom from economic risk.

Dalam implementasi praktis, pemilihan metrik harus mempertimbangkan cost-benefit trade-off antara comprehensiveness dan feasibility. Tidak semua metrik dalam standar perlu diukur untuk setiap evaluasi; sebaliknya, evaluator harus memilih subset metrik yang paling relevan dengan tujuan evaluasi dan characteristics yang menjadi prioritas. Metrik yang dipilih harus memiliki validity (mengukur apa yang seharusnya diukur), reliability (konsisten dalam pengukuran berulang), dan practicality (dapat diukur dengan sumber daya yang tersedia).

### 2.1.3 Total Quality Management (TQM)

Total Quality Management (TQM) adalah filosofi manajemen komprehensif yang berfokus pada perbaikan berkelanjutan dan keterlibatan semua anggota organisasi dalam meningkatkan proses, produk, dan layanan. Berbeda dengan CMMI yang berfokus pada kematangan proses atau ISO/IEC 25000 yang berfokus pada kualitas produk, TQM mengadopsi perspektif holistik yang mengintegrasikan kualitas ke dalam semua aspek organisasi. TQM menekankan bahwa kualitas bukan hanya tanggung jawab departemen quality assurance, tetapi merupakan tanggung jawab bersama seluruh organisasi, dari manajemen puncak hingga staf operasional.

Konsep TQM pertama kali dikembangkan dalam konteks manufaktur oleh pionir seperti W. Edwards Deming, Joseph Juran, dan Kaoru Ishikawa, kemudian diadaptasi untuk industri jasa dan teknologi informasi. Dalam konteks sistem informasi, TQM menekankan pentingnya memahami kebutuhan pengguna (customer focus), menggunakan data untuk pengambilan keputusan (fact-based decision making), dan menciptakan budaya di mana setiap anggota tim merasa bertanggung jawab atas kualitas deliverables mereka. Pendekatan ini sangat relevan dalam era Agile dan DevOps, di mana quality built-in dan continuous improvement menjadi prinsip fundamental.

#### 2.1.3.1 Prinsip-prinsip TQM

TQM dibangun di atas beberapa prinsip fundamental yang membentuk fondasi pendekatan ini terhadap kualitas. Prinsip pertama adalah customer focus—organisasi harus memahami kebutuhan pelanggan saat ini dan masa depan, memenuhi persyaratan pelanggan, dan berusaha melampaui ekspektasi pelanggan. Dalam konteks sistem informasi, pelanggan dapat berupa pengguna akhir, business sponsors, atau stakeholder lain yang memiliki kepentingan dalam sistem.

Prinsip kedua adalah leadership—pemimpin menetapkan unity of purpose dan direction organisasi, serta menciptakan dan memelihara lingkungan internal di mana orang dapat sepenuhnya terlibat dalam mencapai tujuan kualitas organisasi. Prinsip ketiga adalah engagement of people—orang di semua tingkat adalah esensi organisasi, dan keterlibatan penuh mereka memungkinkan kemampuan mereka digunakan untuk keuntungan organisasi. Prinsip keempat adalah process approach—hasil yang diinginkan dicapai lebih efisien ketika aktivitas dan sumber daya terkait dikelola sebagai proses.

Prinsip kelima adalah improvement—perbaikan berkelanjutan kinerja organisasi harus menjadi tujuan permanen. Prinsip keenam adalah evidence-based decision making—keputusan efektif didasarkan pada analisis data dan informasi. Prinsip ketujuh adalah relationship management—organisasi dan pemasoknya saling bergantung, dan hubungan yang saling menguntungkan meningkatkan kemampuan kedua belah pihak untuk menciptakan nilai. Prinsip-prinsip ini membentuk framework yang komprehensif untuk menciptakan budaya kualitas dalam organisasi.

#### 2.1.3.2 Penerapan TQM dalam Evaluasi Sistem

Penerapan TQM dalam evaluasi sistem informasi memerlukan transformasi dari pendekatan evaluasi tradisional yang bersifat inspective (menemukan defect setelah produk selesai) menjadi pendekatan preventive (mencegah defect melalui quality assurance yang built-in). Ini berarti evaluasi tidak lagi dipandang sebagai aktivitas terpisah yang dilakukan di akhir siklus pengembangan, tetapi sebagai aktivitas berkelanjutan yang terintegrasi dalam setiap fase development lifecycle.

Dalam praktik, penerapan TQM dalam evaluasi sistem mencakup beberapa aktivitas kunci. Pertama, penetapan quality objectives yang jelas dan terukur yang aligned dengan strategic goals organisasi. Kedua, implementasi quality planning yang mengidentifikasi quality standards relevan dan bagaimana memenuhinya. Ketiga, pelaksanaan quality assurance untuk memastikan bahwa proses yang tepat digunakan. Keempat, quality control untuk memonitor hasil spesifik dan menentukan apakah mereka memenuhi standar kualitas yang relevan.

Tools dan teknik TQM yang umum digunakan dalam evaluasi sistem termasuk cause-and-effect diagrams (fishbone diagrams) untuk analisis akar masalah, Pareto charts untuk memprioritaskan masalah berdasarkan frekuensi atau dampak, control charts untuk memonitor stabilitas proses, dan Plan-Do-Check-Act (PDCA) cycle untuk perbaikan berkelanjutan. Dalam konteks evaluasi sistem informasi modern, tools ini sering dikombinasikan dengan praktik Agile seperti retrospectives dan Lean seperti value stream mapping untuk menciptakan pendekatan evaluasi yang dinamis dan responsif.

#### 2.1.3.3 Perbandingan dengan Model Lain

Perbandingan antara TQM dengan model evaluasi lain seperti CMMI dan ISO/IEC 25000 mengungkapkan perbedaan fundamental dalam filosofi dan pendekatan, meskipun ketiganya bertujuan meningkatkan kualitas sistem. CMMI bersifat prescriptive dan process-centric, menyediakan roadmap terstruktur untuk peningkatan kematangan proses melalui level yang jelas. ISO/IEC 25000 bersifat product-centric, menyediakan framework untuk mendefinisikan dan mengukur karakteristik kualitas produk perangkat lunak. TQM, di sisi lain, bersifat culture-centric dan holistic, menekankan transformasi budaya organisasi dan keterlibatan semua stakeholder dalam pencapaian kualitas.

Dari perspektif implementasi, CMMI memerlukan investasi yang signifikan dalam formal processes, documentation, dan training, serta sering memerlukan konsultan eksternal untuk appraisal. ISO/IEC 25000 lebih fleksibel dalam implementasi, memungkinkan organisasi untuk memilih karakteristik kualitas dan metrik yang paling relevan dengan kebutuhan mereka. TQM memerlukan komitmen jangka panjang untuk perubahan budaya tetapi dapat dimulai dengan investasi yang lebih modest melalui pilot projects dan gradual expansion.

Ketiganya dapat saling melengkapi dalam strategi evaluasi sistem yang komprehensif. Misalnya, organisasi dapat menggunakan CMMI sebagai framework untuk meningkatkan kematangan proses pengembangan, ISO/IEC 25000 untuk mendefinisikan dan mengukur kualitas produk yang dihasilkan, dan TQM sebagai filosofi overarching yang menciptakan budaya continuous improvement dan customer focus. Banyak organisasi mature mengadopsi hybrid approach yang mengintegrasikan elemen dari berbagai model untuk menciptakan evaluation framework yang customized sesuai dengan konteks dan kebutuhan spesifik mereka.

---

## 2.2 Pendekatan Evaluasi Kualitatif

Pendekatan evaluasi kualitatif memberikan pemahaman mendalam tentang konteks, pengalaman pengguna, dan fenomena kompleks yang tidak dapat sepenuhnya ditangkap melalui angka atau metrik kuantitatif. Dalam evaluasi sistem informasi, metode kualitatif sangat berharga untuk mengeksplorasi bagaimana sistem digunakan dalam praktik nyata, mengidentifikasi kebutuhan pengguna yang tidak terartikulasikan, dan memahami faktor sosio-teknis yang mempengaruhi adopsi dan efektivitas sistem. Pendekatan ini menghasilkan rich, detailed data yang memberikan insight tentang "mengapa" dan "bagaimana" di balik pola penggunaan dan kinerja sistem.

Evaluasi kualitatif bersifat interpretive dan naturalistic, berusaha memahami fenomena dalam setting natural mereka dan memaknai fenomena tersebut dari perspektif aktor yang terlibat. Berbeda dengan pendekatan kuantitatif yang berusaha mengukur dan menggeneralisasi, pendekatan kualitatif berusaha memahami dan mengkontekstualisasi. Dalam konteks evaluasi sistem, ini berarti evaluator tidak hanya menanyakan "seberapa cepat sistem merespons?" tetapi juga "bagaimana kecepatan respons mempengaruhi workflow pengguna dan apakah itu memenuhi ekspektasi mereka dalam konteks tugas spesifik?"

### 2.2.1 Metode Kualitatif dalam Evaluasi Sistem

Metode kualitatif yang umum digunakan dalam evaluasi sistem informasi mencakup case studies, ethnographic studies, phenomenological studies, dan grounded theory. Case study adalah investigasi mendalam tentang implementasi sistem dalam konteks organisasi spesifik, mengeksplorasi faktor-faktor yang mempengaruhi success atau failure. Metode ini sangat berguna untuk memahami kompleksitas implementasi sistem dalam setting dunia nyata, di mana banyak variabel berinteraksi dengan cara yang tidak dapat diprediksi atau dikontrol.

Ethnographic studies melibatkan observasi partisipatif jangka panjang tentang bagaimana sistem digunakan dalam praktik sehari-hari. Evaluator menghabiskan waktu dalam lingkungan kerja aktual pengguna, mengamati interaksi mereka dengan sistem, dan memahami konteks sosial dan organisasional penggunaan sistem. Pendekatan ini sangat efektif untuk mengidentifikasi gap antara designed functionality dan actual usage, serta untuk mengungkap workarounds yang dikembangkan pengguna untuk mengatasi keterbatasan sistem.

Phenomenological studies fokus pada pengalaman hidup (lived experience) pengguna dengan sistem, berusaha memahami esensi dan makna dari pengalaman tersebut. Pendekatan ini berguna untuk evaluasi sistem yang memiliki dimensi experiential yang kuat, seperti sistem pembelajaran online atau aplikasi kesehatan digital. Grounded theory adalah pendekatan yang membangun teori dari data yang dikumpulkan, bukan menguji teori yang sudah ada. Dalam evaluasi sistem, grounded theory dapat digunakan untuk mengembangkan model tentang bagaimana pengguna mengadopsi teknologi baru atau bagaimana sistem mempengaruhi proses bisnis.

### 2.2.2 Teknik Pengumpulan Data Kualitatif

Teknik pengumpulan data kualitatif yang paling umum dalam evaluasi sistem adalah in-depth interviews, focus group discussions, observations, dan document analysis. In-depth interviews melibatkan percakapan one-on-one yang terstruktur, semi-terstruktur, atau tidak terstruktur dengan stakeholder kunci seperti pengguna, administrator sistem, business owners, dan technical staff. Interview semi-terstruktur, yang menggunakan interview guide dengan pertanyaan open-ended, paling umum digunakan karena menyeimbangkan konsistensi dengan fleksibilitas untuk mengeksplorasi tema yang muncul.

Focus group discussions melibatkan diskusi kelompok terarah dengan 6-12 partisipan yang memiliki pengalaman atau perspektif relevan tentang sistem yang dievaluasi. Metode ini efektif untuk mengeksplorasi persepsi bersama, mengidentifikasi konsensus atau perbedaan pandangan, dan menghasilkan ide melalui interaksi kelompok. Dalam evaluasi sistem, focus groups dapat digunakan untuk memahami bagaimana tim bekerja bersama menggunakan sistem, mengidentifikasi pain points yang umum, atau mengeksplorasi requirements untuk sistem baru atau upgrade.

Observasi dapat berupa participant observation (evaluator berpartisipasi dalam aktivitas yang diamati) atau non-participant observation (evaluator mengamati tanpa berpartisipasi). Observasi langsung sangat berharga untuk memahami actual usage patterns yang mungkin berbeda dari self-reported behavior dalam interviews atau surveys. Document analysis melibatkan review sistematis terhadap dokumen terkait sistem seperti requirements documents, design specifications, user manuals, training materials, help desk logs, dan meeting minutes. Dokumen-dokumen ini memberikan konteks historis dan insight tentang intended functionality dan evolution sistem.

### 2.2.3 Analisis Data Kualitatif

Analisis data kualitatif adalah proses sistematis untuk mengorganisasi, menginterpretasi, dan memaknai data tekstual atau visual yang dikumpulkan melalui interviews, observations, atau documents. Proses ini biasanya dimulai dengan transcription—mengubah rekaman audio atau video menjadi teks tertulis—yang kemudian menjadi basis untuk analisis lebih lanjut. Transcription harus akurat dan mencakup tidak hanya kata-kata yang diucapkan tetapi juga, jika relevan, aspek paraverbal seperti intonasi, jeda, atau tawa yang dapat memberikan nuansa makna.

Coding adalah teknik analisis kualitatif yang paling fundamental, melibatkan pemberian label (codes) pada segmen data untuk mengkategorisasi dan mengorganisasi informasi. Initial coding atau open coding melibatkan pembacaan data dan identifikasi konsep atau tema yang muncul. Axial coding menghubungkan kategori dengan sub-kategori untuk membangun pemahaman yang lebih terstruktur tentang fenomena. Selective coding mengidentifikasi core category yang menjadi pusat analisis. Proses coding biasanya iteratif, dengan evaluator membaca dan mengkode ulang data beberapa kali untuk refine categories dan ensure comprehensiveness.

Setelah coding, evaluator melakukan thematic analysis untuk mengidentifikasi patterns dan themes yang signifikan dalam data. Themes adalah pola bermakna dalam data yang relevan dengan research questions atau evaluation objectives. Identifikasi themes melibatkan interpretasi yang cermat, mempertimbangkan frequency (seberapa sering theme muncul), salience (seberapa penting theme bagi partisipan), dan relevance (seberapa relevan theme dengan evaluation questions). Tools software seperti NVivo, ATLAS.ti, atau MAXQDA dapat memfasilitasi proses coding dan analisis, terutama untuk dataset yang besar, meskipun pemahaman konseptual dan interpretative judgment evaluator tetap esensial.

### 2.2.4 Validasi Hasil Kualitatif

Validasi atau trustworthiness hasil kualitatif melibatkan demonstrasi credibility, transferability, dependability, dan confirmability dari findings. Credibility (analog dengan internal validity dalam penelitian kuantitatif) mengacu pada seberapa akurat findings merepresentasikan realitas yang diteliti. Teknik untuk meningkatkan credibility termasuk prolonged engagement (menghabiskan waktu yang cukup dalam setting untuk memahami konteks), persistent observation (fokus mendalam pada elemen yang paling relevan), triangulation (menggunakan multiple sources, methods, atau investigators), dan member checking (memverifikasi findings dengan partisipan).

Transferability (analog dengan external validity) mengacu pada sejauh mana findings dapat diterapkan ke konteks lain. Penelitian kualitatif tidak bertujuan untuk generalisasi statistik, tetapi untuk transferability analitik—memberikan thick description yang cukup detail sehingga readers dapat menilai apakah findings relevan dengan konteks mereka. Dalam laporan evaluasi, ini berarti menyediakan deskripsi komprehensif tentang konteks evaluasi, karakteristik partisipan, dan setting di mana data dikumpulkan.

Dependability (analog dengan reliability) mengacu pada konsistensi dan stabilitas findings. Audit trail yang mendokumentasikan setiap langkah proses evaluasi—dari desain awal, pengumpulan data, analisis, hingga interpretasi—membantu memastikan dependability. Confirmability (analog dengan objectivity) mengacu pada sejauh mana findings ditentukan oleh data dan konteks penelitian, bukan oleh bias evaluator. Reflexivity—kesadaran evaluator tentang bagaimana asumsi, pengalaman, dan posisi mereka dapat mempengaruhi interpretasi—adalah komponen penting dari confirmability. Evaluator harus mendokumentasikan reflections mereka sepanjang proses evaluasi untuk meningkatkan transparansi dan trustworthiness.

---

## 2.3 Pendekatan Evaluasi Kuantitatif

Pendekatan evaluasi kuantitatif menggunakan pengukuran numerik dan analisis statistik untuk mengevaluasi aspek-aspek sistem informasi yang dapat dikuantifikasi. Pendekatan ini sangat efektif untuk mengukur performance metrics, user satisfaction levels, system reliability, dan aspek lain yang dapat dinyatakan dalam angka. Kekuatan utama metode kuantitatif terletak pada kemampuannya untuk menghasilkan hasil yang objektif, replicable, dan generalizable, serta memungkinkan perbandingan sistematis antar sistem atau implementasi.

Dalam konteks evaluasi sistem informasi, pendekatan kuantitatif memungkinkan evaluator untuk menjawab pertanyaan seperti "Seberapa cepat sistem merespons?", "Berapa persentase pengguna yang puas dengan sistem?", "Apakah ada perbedaan signifikan dalam produktivitas sebelum dan sesudah implementasi sistem?", dan "Seberapa sering sistem mengalami downtime?" Data kuantitatif memberikan evidensi objektif yang dapat digunakan untuk pengambilan keputusan berbasis fakta dan untuk memenuhi accountability requirements stakeholder.

### 2.3.1 Metode Kuantitatif dalam Evaluasi Sistem

Metode kuantitatif yang umum digunakan dalam evaluasi sistem mencakup surveys, experiments, quasi-experiments, dan analysis of system logs and metrics. Surveys menggunakan kuestioner terstruktur dengan pertanyaan closed-ended untuk mengumpulkan data dari sampel pengguna atau stakeholder yang representatif. Survey instruments yang tervalidasi seperti System Usability Scale (SUS), Technology Acceptance Model (TAM) questionnaire, atau ISO/IEC 25022 quality in use questionnaire sering digunakan karena reliability dan validity mereka telah teruji.

Experiments melibatkan manipulasi satu atau lebih variabel independen untuk mengamati efeknya pada variabel dependen dalam kondisi yang terkontrol. Dalam evaluasi sistem, experiments dapat digunakan untuk membandingkan alternatif desain interface, menguji efektivitas fitur baru, atau mengukur dampak perubahan sistem pada performance. Randomized controlled trials (RCTs), di mana partisipan secara random ditugaskan ke experimental atau control group, adalah gold standard untuk menetapkan causal relationships.

Quasi-experiments mirip dengan experiments tetapi tanpa random assignment, sering digunakan ketika random assignment tidak feasible atau ethical. Pre-test/post-test designs, di mana measurements dilakukan sebelum dan sesudah implementasi sistem, adalah contoh common quasi-experimental design. Analysis of system logs and metrics melibatkan ekstraksi dan analisis data operasional dari sistem itu sendiri, seperti transaction volumes, response times, error rates, atau user activity patterns. Data ini objektif dan comprehensive, tetapi memerlukan tools dan expertise untuk extraction dan interpretation.

### 2.3.2 Teknik Pengumpulan Data Kuantitatif

Pengumpulan data kuantitatif dalam evaluasi sistem memerlukan perhatian cermat pada sampling, instrument design, dan data collection procedures untuk memastikan validity dan reliability. Sampling strategy menentukan siapa yang akan berpartisipasi dalam evaluasi dan bagaimana mereka dipilih. Probability sampling methods (simple random, stratified, cluster) memberikan basis untuk generalisasi statistik ke populasi yang lebih luas, sementara non-probability sampling methods (convenience, purposive, quota) lebih praktis tetapi membatasi generalizability.

Instrument design melibatkan pengembangan kuesioner, performance tests, atau measurement tools yang valid dan reliable. Validity mengacu pada sejauh mana instrument mengukur apa yang seharusnya diukur. Content validity memastikan bahwa instrument mencakup semua aspek relevan dari construct yang diukur. Construct validity memastikan bahwa instrument benar-benar mengukur theoretical construct yang dimaksud. Criterion validity menguji apakah instrument predictions konsisten dengan actual outcomes. Reliability mengacu pada konsistensi measurements, biasanya diukur melalui internal consistency (Cronbach's alpha), test-retest reliability, atau inter-rater reliability.

Data collection procedures harus terstandarisasi untuk meminimalkan bias dan variability. Dalam surveys, ini mencakup standardized instructions, consistent administration conditions, dan quality control untuk memastikan completeness dan accuracy responses. Dalam performance measurements, ini mencakup standardized tasks, controlled environmental conditions, dan calibrated measurement instruments. Automated data collection dari system logs mengurangi bias human tetapi memerlukan validasi untuk memastikan bahwa data captured accurately dan completely.

### 2.3.3 Analisis Statistik Dasar

Analisis statistik dasar dalam evaluasi sistem dimulai dengan descriptive statistics yang merangkum dan menggambarkan karakteristik data. Measures of central tendency (mean, median, mode) memberikan informasi tentang nilai tipikal dalam dataset. Mean adalah rata-rata aritmatik yang sensitif terhadap outliers. Median adalah nilai tengah yang lebih robust terhadap outliers. Mode adalah nilai yang paling sering muncul. Measures of dispersion (range, variance, standard deviation) menggambarkan variability dalam data. Standard deviation menunjukkan seberapa jauh data tersebar dari mean; nilai yang lebih besar mengindikasikan variability yang lebih tinggi.

Inferential statistics digunakan untuk membuat inferences tentang population berdasarkan sample data dan untuk menguji hypotheses. Hypothesis testing melibatkan formulasi null hypothesis (biasanya menyatakan tidak ada efek atau perbedaan) dan alternative hypothesis, kemudian menggunakan data untuk menentukan apakah null hypothesis dapat ditolak. P-value menunjukkan probabilitas mengamati results yang diperoleh (atau lebih ekstrem) jika null hypothesis benar; p-value < 0.05 conventionally dianggap sebagai threshold untuk statistical significance.

T-tests digunakan untuk membandingkan means antara dua grup (misalnya, kepuasan pengguna sistem lama vs. baru). Analysis of Variance (ANOVA) membandingkan means di antara tiga atau lebih grup. Chi-square tests digunakan untuk data categorical untuk menguji apakah ada association antara dua variabel. Correlation analysis (Pearson atau Spearman) mengukur strength dan direction dari relationship antara dua variabel continuous. Regression analysis memungkinkan prediction dari variabel dependen berdasarkan satu atau lebih variabel independen dan dapat mengidentifikasi relative importance dari different predictors.

### 2.3.4 Validasi Hasil Kuantitatif

Validasi hasil kuantitatif melibatkan ensuring bahwa statistical analyses appropriate, assumptions met, dan conclusions justified. Setiap teknik statistik memiliki assumptions yang harus dipenuhi untuk hasil yang valid. Misalnya, many parametric tests mengasumsikan normal distribution dari data, homogeneity of variance, dan independence of observations. Violations dari assumptions ini dapat lead to incorrect conclusions. Evaluator harus melakukan diagnostic checks (seperti normality tests, homoscedasticity tests) dan, jika assumptions violated, menggunakan alternative analyses seperti non-parametric tests atau transformations.

Statistical significance harus dibedakan dari practical significance. Hasil dapat statistically significant (unlikely due to chance) tetapi memiliki effect size yang terlalu kecil untuk practically meaningful. Misalnya, perbedaan 0.1 detik dalam response time mungkin statistically significant dalam large sample tetapi tidak meaningful bagi pengguna. Effect size measures (seperti Cohen's d untuk mean differences atau R-squared untuk regression) memberikan informasi tentang magnitude dari effects dan harus dilaporkan bersama dengan statistical significance.

Replication dan cross-validation meningkatkan confidence dalam findings. Jika memungkinkan, analyses harus direplikasi dengan independent samples atau datasets untuk verify bahwa results consistent. Cross-validation techniques, seperti hold-out validation atau k-fold cross-validation, dapat digunakan untuk assess generalizability dari predictive models. Sensitivity analyses, yang examine bagaimana results berubah dengan different analytical decisions (seperti outlier treatment atau variable transformations), membantu assess robustness dari conclusions.

---

## 2.4 Metodologi Campuran (Mixed Methods)

Metodologi campuran (mixed methods) mengintegrasikan pendekatan kualitatif dan kuantitatif dalam satu studi evaluasi untuk mendapatkan pemahaman yang lebih komprehensif tentang sistem informasi yang dievaluasi. Pendekatan ini mengakui bahwa phenomena kompleks seperti implementasi dan penggunaan sistem informasi memiliki dimensi yang paling baik dipahami melalui kombinasi measurement kuantitatif dan exploration kualitatif. Mixed methods research telah berkembang menjadi paradigma tersendiri dalam metodologi penelitian, dengan philosophical foundations, design typologies, dan quality criteria yang distinct.

Dalam konteks evaluasi sistem informasi, mixed methods sangat powerful karena sistem informasi inherently multifaceted, melibatkan technical performance, human factors, organizational processes, dan business outcomes. Quantitative data dapat menunjukkan "apa" dan "seberapa banyak" (misalnya, system uptime 99.5%, user satisfaction score 7.8/10), sementara qualitative data dapat menjelaskan "mengapa" dan "bagaimana" (misalnya, mengapa pengguna tertentu tidak puas meskipun technical performance baik, atau bagaimana sistem mengubah workflow). Integrasi kedua jenis data ini menghasilkan insights yang tidak dapat diperoleh dari salah satu pendekatan saja.

### 2.4.1 Konsep Metodologi Campuran

Mixed methods research didefinisikan sebagai pendekatan yang mengombinasikan atau mengasosiasikan bentuk kualitatif dan kuantitatif dalam satu studi. Integrasi ini dapat terjadi pada berbagai tahap proses penelitian: dalam formulation dari research questions, dalam data collection, dalam data analysis, atau dalam interpretation dari findings. Philosophical foundation dari mixed methods adalah pragmatism, yang menekankan practical consequences dan real-world applications daripada adherence rigid pada satu paradigma filosofis.

Paradigma pragmatis memungkinkan peneliti untuk use "what works" untuk menjawab research questions, memilih methods berdasarkan appropriateness mereka untuk problem at hand daripada philosophical commitments. Dalam evaluasi sistem, ini berarti evaluator bebas menggunakan surveys untuk mengukur user satisfaction, interviews untuk understand reasons behind satisfaction levels, log analysis untuk assess actual usage patterns, dan observations untuk understand context of use—semua dalam satu comprehensive evaluation.

Tiga karakteristik inti mixed methods research adalah: (1) Collection dan analysis dari both qualitative dan quantitative data; (2) Mixing atau integration dari dua forms of data; (3) Use dari distinct designs yang melibatkan philosophical assumptions dan theoretical frameworks. Integration adalah key distinguishing feature—mixed methods bukan sekadar melakukan qualitative study dan quantitative study secara terpisah, tetapi deliberately merging, integrating, linking, atau embedding mereka untuk produce insights yang lebih dalam.

### 2.4.2 Desain Penelitian Campuran

Typology desain mixed methods yang dikembangkan oleh Creswell dan Plano Clark mengidentifikasi beberapa core designs yang umum digunakan. Convergent parallel design melibatkan concurrent collection dari qualitative dan quantitative data, independent analysis dari kedua datasets, dan kemudian merging results untuk comparison atau integration. Design ini efisien dalam hal waktu karena data collection dapat parallel, dan memberikan well-validated dan substantiated findings melalui triangulation.

Explanatory sequential design dimulai dengan quantitative data collection dan analysis, diikuti oleh qualitative data collection dan analysis yang build pada atau explain quantitative results. Misalnya, evaluator mungkin pertama melakukan survey untuk measure user satisfaction (quantitative), kemudian conduct interviews dengan users yang reported very high atau very low satisfaction untuk understand reasons (qualitative). Design ini sangat useful ketika quantitative results memerlukan explanation atau unexpected findings muncul yang memerlukan exploration lebih dalam.

Exploratory sequential design dimulai dengan qualitative phase untuk explore phenomenon, kemudian uses qualitative findings untuk develop quantitative instruments atau identify variables untuk quantitative testing. Dalam evaluasi sistem, ini berguna ketika evaluator tidak memiliki sufficient prior knowledge untuk develop quantitative measures. Misalnya, evaluator mungkin pertama conduct focus groups untuk identify key quality attributes yang important bagi users, kemudian develop survey instrument berdasarkan identified attributes untuk measure mereka across larger sample.

Embedded design mengintegrasikan satu form of data dalam larger design framework yang didominasi oleh form lainnya. Misalnya, dalam experimental evaluation yang predominantly quantitative, qualitative interviews mungkin embedded untuk understand participant experiences. Multiphase design mengombinasikan sequential dan concurrent strands over program atau multiple studies, common dalam large-scale, long-term evaluation projects.

### 2.4.3 Integrasi Data Kualitatif dan Kuantitatif

Integrasi adalah hallmark dari mixed methods research dan dapat occur pada berbagai points dalam research process. Merging integration melibatkan bringing together qualitative dan quantitative results untuk comparison, often dalam joint display yang presents both types of data side-by-side untuk facilitate comparison. Misalnya, evaluator dapat create matrix yang menampilkan quantitative user satisfaction scores alongside qualitative themes tentang reasons untuk satisfaction atau dissatisfaction.

Connecting integration melibatkan using results dari one method untuk inform data collection atau analysis dalam another method. Dalam explanatory sequential design, quantitative results directly shape qualitative data collection—misalnya, interview participants dipilih berdasarkan survey responses mereka, atau interview questions designed untuk explain quantitative patterns. Dalam exploratory sequential design, qualitative findings inform development dari quantitative instruments.

Embedding integration occurs ketika one form of data support atau provide contextual understanding untuk primary data form. Misalnya, dalam evaluation yang predominantly quantitative, qualitative observations mungkin collected untuk provide context tentang conditions di mana quantitative measurements taken, atau untuk help interpret outliers dalam quantitative data.

Transforming integration involves converting one data type menjadi form lainnya untuk enable integrated analysis. Qualitative data dapat "quantitized" dengan counting frequency dari codes atau themes, atau dengan creating categorical variables dari qualitative descriptions. Quantitative data dapat "qualitized" dengan describing patterns dalam narratives atau dengan identifying cases yang represent different quantitative categories untuk in-depth qualitative examination.

### 2.4.4 Keunggulan dan Tantangan Metodologi Campuran

Keunggulan utama mixed methods adalah comprehensiveness dan depth dari understanding yang dihasilkan. Triangulation—corroboration dari findings menggunakan different methods—meningkatkan validity dan credibility. Complementarity—menggunakan results dari one method untuk elaborate, enhance, atau clarify results dari another—provides richer detail dan deeper understanding. Expansion—extending breadth dan range of inquiry dengan using different methods untuk different inquiry components—enables addressing broader set of evaluation questions.

Mixed methods juga memungkinkan offsetting weaknesses dari individual methods. Quantitative methods strong dalam generalizability tetapi may miss contextual detail; qualitative methods provide rich context tetapi findings may not be widely generalizable. Mengombinasikan keduanya dapat produce evaluations yang both broadly applicable dan deeply insightful. Mixed methods juga particularly valuable untuk addressing practical problems yang inherently complex, seperti evaluasi sistem informasi, di mana multiple perspectives dan types of evidence diperlukan untuk comprehensive understanding.

Namun, mixed methods juga presents significant challenges. Resource intensiveness adalah concern major—conducting both qualitative dan quantitative research requires more time, expertise, dan resources daripada single-method studies. Evaluators need competence dalam both approaches, atau teams harus include members dengan complementary skills. Complexity dalam design, implementation, dan analysis dapat overwhelming, particularly untuk evaluators yang tidak berpengalaman dengan mixed methods.

Challenges dalam integration termasuk determining how untuk meaningfully combine qualitative dan quantitative data, particularly ketika they produce conflicting results. Divergence antara qualitative dan quantitative findings bukan necessarily problematic—dapat indicate important nuances atau multiple dimensions dari phenomenon—tetapi requires thoughtful interpretation. Philosophical tensions dapat arise antara team members atau audiences yang have strong commitments untuk particular paradigms. Managing these tensions requires clear articulation dari pragmatic stance dan focus pada practical benefits dari integration untuk answering evaluation questions.

---

## 2.5 Pemilihan Kerangka Kerja yang Tepat

Pemilihan kerangka kerja evaluasi yang tepat adalah keputusan strategis yang signifikan mempengaruhi effectiveness dan utility dari evaluation effort. Tidak ada single "best" framework yang universal applicable untuk semua situations; sebaliknya, appropriateness dari framework tergantung pada multiple contextual factors termasuk evaluation purposes, organizational characteristics, available resources, dan stakeholder needs. Proses selection harus systematic dan deliberate, mempertimbangkan alignment antara framework capabilities dan evaluation requirements.

Framework selection bukan one-time decision tetapi iterative process yang may require adjustments as evaluation progresses dan understanding tentang system dan context deepens. Evaluators harus maintain flexibility untuk adapt framework atau even switch frameworks jika initial choice proves inappropriate. Namun, changes harus made thoughtfully, dengan clear rationale dan consideration of implications untuk consistency dan comparability dari evaluation results.

### 2.5.1 Faktor Pertimbangan Pemilihan Framework

Pertimbangan pertama dalam framework selection adalah evaluation purpose dan questions. Jika tujuan utama adalah assess maturity dari development processes, CMMI might be most appropriate. Jika focus adalah pada product quality assessment, ISO/IEC 25000 provides comprehensive quality model dan metrics. Jika concern adalah organizational culture dan continuous improvement, TQM principles may be most relevant. Clearly articulated evaluation questions guide framework selection dengan identifying specific aspects dari system yang need assessment.

Organizational maturity dan readiness adalah consideration penting. Organizations dengan low process maturity may struggle dengan implementing comprehensive frameworks seperti CMMI Level 3 dan might benefit dari starting dengan simpler approaches atau focusing pada specific process areas. Organizations dengan established quality culture may be ready untuk more advanced frameworks. Assessment dari current state dan realistic appraisal dari organizational capabilities untuk undertake evaluation activities adalah essential.

Available resources—including time, budget, dan expertise—significantly constrain framework choices. Comprehensive frameworks seperti CMMI require substantial investment dalam training, documentation, dan potentially external consultants untuk formal appraisals. Simpler approaches atau focused evaluations dapat more feasible dengan limited resources. Evaluators must balance comprehensiveness dengan practicality, ensuring bahwa chosen framework dapat realistically implemented dengan available resources.

Stakeholder expectations dan requirements juga shape framework selection. Regulatory requirements, contractual obligations, atau customer demands may mandate specific frameworks atau standards. Stakeholder familiarity dengan certain frameworks dapat facilitate buy-in dan implementation. Conversely, imposing unfamiliar frameworks dapat encounter resistance. Understanding stakeholder perspectives dan negotiating framework selection dengan key stakeholders improves likelihood dari successful evaluation.

### 2.5.2 Kriteria Kesesuaian dengan Konteks Organisasi

Industry context dan domain characteristics mempengaruhi framework appropriateness. Highly regulated industries seperti healthcare atau finance may require frameworks yang address compliance dan security comprehensively, seperti ISO/IEC 25000 dengan emphasis pada security characteristics atau CMMI dengan strong governance focus. Agile organizations may prefer lighter-weight approaches atau frameworks yang compatible dengan agile principles, rather than heavy process documentation.

Organizational size dan structure juga relevant. Large, distributed organizations may benefit dari standardized frameworks yang provide common language dan processes across units. Small organizations may find comprehensive frameworks overly bureaucratic dan prefer tailored, lightweight approaches. Organizational culture—whether hierarchical atau flat, risk-averse atau innovative, process-oriented atau outcome-oriented—affects how well different frameworks akan accepted dan implemented.

System characteristics including complexity, criticality, dan lifecycle stage influence framework selection. Mission-critical systems yang failure could have severe consequences require rigorous evaluation approaches dengan emphasis pada reliability, security, dan safety. Less critical systems may warrant lighter evaluation. Legacy systems mungkin require different evaluation approach daripada new development. Cloud-based atau outsourced systems present unique evaluation challenges yang may require adapted frameworks.

Strategic alignment adalah crucial criterion. Framework harus support organizational strategic objectives, bukan just satisfy immediate evaluation needs. Jika organization strategic goal adalah digital transformation, evaluation framework should assess not just current system quality tetapi also adaptability dan innovation potential. Jika goal adalah operational excellence, framework should emphasize efficiency, reliability, dan continuous improvement.

### 2.5.3 Adaptasi Framework Sesuai Kebutuhan

Framework adaptation atau tailoring adalah common practice yang customizes generic frameworks untuk fit specific organizational contexts. Adaptation dapat involve selecting subset dari framework components yang most relevant, modifying terminology untuk align dengan organizational language, atau adding organization-specific elements. CMMI explicitly supports tailoring, dengan guidance untuk selecting process areas dan practices berdasarkan business objectives.

Adaptation harus balanced carefully. Too much tailoring dapat undermine framework integrity dan comparability dengan benchmarks atau other organizations. Too little dapat result dalam framework yang misaligned dengan organizational realities dan needs. Documentation dari tailoring decisions dan rationale adalah important untuk transparency dan untuk future reference jika framework evolves.

Hybrid approaches yang combine elements dari multiple frameworks dapat powerful tetapi require careful integration. Misalnya, organization might use CMMI untuk process maturity assessment, ISO/IEC 25000 untuk product quality metrics, dan TQM principles untuk overall quality culture. Integration points harus clearly defined untuk avoid duplication atau gaps. Overarching framework atau metamodel dapat help coordinate multiple frameworks dan ensure coherence.

Incremental adoption adalah practical strategy, particularly untuk comprehensive frameworks. Rather than attempting full framework implementation immediately, organizations dapat start dengan pilot projects atau specific areas, gain experience dan demonstrate value, kemudian gradually expand scope. This approach reduces risk, allows learning, dan builds organizational capability progressively.

### 2.5.4 Studi Kasus: Implementasi Framework di Berbagai Industri

**Sektor Perbankan Digital**: Sebuah bank digital terkemuka di Indonesia mengimplementasikan hybrid framework combining ISO/IEC 25000 untuk product quality assessment dengan elements dari CMMI untuk development process improvement. Bank tersebut facing regulatory requirements untuk information security dan reliability, serta competitive pressure untuk rapid innovation. ISO/IEC 25000 security dan reliability characteristics addressed regulatory concerns, sementara CMMI process areas seperti Requirements Management dan Configuration Management improved development predictability. Quantitative metrics dari ISO/IEC 25000 diintegrasikan dengan qualitative user feedback melalui mixed methods approach, enabling comprehensive assessment dari mobile banking application mereka.

**Pendidikan Tinggi**: Universitas yang implementing learning management system (LMS) used primarily qualitative evaluation approach dengan elements dari TQM. Focus adalah pada understanding faculty dan student experiences, identifying adoption barriers, dan continuous improvement. Ethnographic observations revealed gap antara intended use dan actual practices—faculty developed workarounds untuk limitations, students found navigation confusing. Focus groups generated insights tentang needed features. University established continuous feedback loops consistent dengan TQM principles, dengan regular retrospectives dan incremental improvements. Quantitative usage metrics dari system logs complemented qualitative insights dalam mixed methods design.

**E-Government**: Pemerintah kota implementing integrated public services platform adopted CMMI framework untuk ensuring systematic development process, critical given high visibility dan public accountability. City government started dengan CMMI Level 2 focus, establishing basic project management dan requirements management practices. Formal SCAMPI appraisal identified gaps dalam current practices dan provided roadmap untuk improvement. Implementation challenged existing informal culture, requiring significant change management effort. After two years, city achieved CMMI Level 3, resulting dalam measurable improvements dalam on-time delivery dan defect reduction. Evaluation combined quantitative process metrics dengan qualitative stakeholder feedback.

**Healthcare Technology**: Rumah sakit implementing electronic health records (EHR) system used ISO/IEC 25000 sebagai primary framework, dengan particular emphasis pada usability, reliability, dan security characteristics. Given safety-critical nature dari healthcare, rigorous quantitative evaluation dari system reliability dan security adalah essential. However, user acceptance critical untuk success, so qualitative methods including clinician interviews dan observational studies embedded dalam evaluation. Mixed methods revealed technical performance met standards tetapi workflow integration problematic, leading to redesign of certain interfaces. Case demonstrates importance dari combining technical quality assessment dengan human factors evaluation.

---

## Ringkasan Bab

Bab ini telah menguraikan kerangka kerja dan metodologi fundamental yang membentuk basis untuk evaluasi sistem informasi yang sistematis dan komprehensif. Model-model evaluasi seperti CMMI, ISO/IEC 25000, dan TQM masing-masing menawarkan perspektif unik: CMMI berfokus pada kematangan proses organisasi dengan struktur tingkatan yang jelas, ISO/IEC 25000 menyediakan framework komprehensif untuk kualitas produk perangkat lunak dengan karakteristik dan metrik yang terstandarisasi, sementara TQM mengadopsi pendekatan holistik yang menekankan budaya kualitas dan perbaikan berkelanjutan di seluruh organisasi.

Pendekatan metodologis dalam evaluasi—kualitatif, kuantitatif, dan campuran—masing-masing memiliki kekuatan dan keterbatasan yang distinct. Metode kualitatif memberikan rich insights tentang konteks, pengalaman pengguna, dan kompleksitas sosio-teknis yang sulit dikuantifikasi. Metode kuantitatif menyediakan measurements objektif, statistical rigor, dan basis untuk generalization. Metodologi campuran mengintegrasikan kedua pendekatan untuk menghasilkan pemahaman yang lebih komprehensif dan nuanced, particularly valuable untuk fenomena kompleks seperti implementasi sistem informasi.

Pemilihan kerangka kerja dan metodologi yang tepat memerlukan pertimbangan systematic terhadap evaluation purposes, organizational context, available resources, dan stakeholder needs. Tidak ada solusi one-size-fits-all; effective evaluators harus memiliki understanding mendalam tentang berbagai frameworks dan methods, serta judgment untuk memilih, mengadaptasi, dan mengintegrasikan mereka sesuai dengan specific evaluation contexts. Framework adaptation, hybrid approaches, dan incremental implementation adalah strategi praktis untuk customizing evaluations sambil maintaining rigor dan validity.

---

## Pertanyaan Reflektif untuk Mahasiswa

1. **Analisis Komparatif Framework**: Bandingkan CMMI, ISO/IEC 25000, dan TQM dalam konteks evaluasi sistem informasi di sektor yang Anda minati (misalnya, e-commerce, pendidikan, kesehatan). Framework mana yang paling sesuai dan mengapa? Identifikasi minimal tiga faktor spesifik yang mempengaruhi pilihan Anda, dan diskusikan bagaimana keterbatasan framework pilihan Anda dapat dimitigasi melalui adaptasi atau integrasi dengan framework lain.

2. **Integrasi Metodologi Kualitatif-Kuantitatif**: Desain sebuah evaluasi mixed methods untuk sistem informasi akademik (SIAKAD) di universitas Anda. Jelaskan: (a) specific evaluation questions yang akan dijawab oleh qualitative vs. quantitative components; (b) mixed methods design yang akan Anda gunakan (convergent, sequential explanatory, sequential exploratory, atau embedded) beserta justifikasi; (c) bagaimana Anda akan mengintegrasikan qualitative dan quantitative findings untuk menghasilkan comprehensive insights; (d) potential challenges dalam implementation dan strategi untuk mengatasinya.

3. **Framework Selection dan Adaptasi**: Anda adalah konsultan yang ditugaskan mengevaluasi sistem e-government untuk pemerintah daerah dengan resources terbatas, organizational maturity yang rendah, tetapi stakeholder expectations yang tinggi. Jelaskan systematic process yang akan Anda gunakan untuk: (a) memilih framework yang paling appropriate; (b) mengadaptasi framework tersebut agar feasible dengan available resources namun tetap credible dan comprehensive; (c) mendapatkan stakeholder buy-in untuk chosen approach; (d) measuring success dari evaluation effort Anda. Sertakan consideration tentang ethical issues dan potential biases yang mungkin mempengaruhi evaluation.

---

## Studi Kasus Diskusi Kelas

### Konteks Organisasi

**PT Solusi Digital Indonesia** adalah perusahaan fintech yang berkembang pesat dengan 500 karyawan, menyediakan platform pembayaran digital dan pinjaman online. Perusahaan baru saja menyelesaikan pengembangan versi major baru dari platform mereka yang mengintegrasikan artificial intelligence untuk fraud detection dan personalized financial recommendations. Sistem ini critical untuk business operations dan melayani 2 juta active users.

Manajemen menugaskan tim evaluasi untuk melakukan comprehensive assessment dari new platform sebelum full deployment. Evaluation harus address multiple concerns dari different stakeholders:

- **Regulator (Otoritas Jasa Keuangan)**: Memerlukan assurance tentang security, data privacy, dan reliability system, dengan documented evidence of compliance dengan financial technology regulations.

- **Executive Management**: Ingin understand ROI dari development investment, potential business impacts, dan readiness untuk full deployment. Concerned tentang reputational risks if system failures occur after launch.

- **Technology Team**: Interested dalam technical quality metrics, code maintainability, performance benchmarks, dan identification dari technical debt yang perlu addressed.

- **Customer Service**: Concerned tentang usability untuk diverse user demographics (varying digital literacy levels), clarity dari AI-driven recommendations, dan potential increase dalam support requests.

- **End Users**: Expectations untuk fast, intuitive, dan trustworthy system, dengan transparency tentang how AI makes recommendations dan assurance tentang data security.

**Organizational Characteristics**:
- Development process relatively ad-hoc; no formal process framework currently implemented
- Mixed technology stack dengan legacy components dan new microservices
- Agile development culture dengan two-week sprints
- Limited formal quality assurance processes; heavy reliance pada developer testing
- Timeline pressure: Full deployment planned dalam tiga bulan
- Budget untuk evaluation: Rp 500 juta (approximately $35,000 USD)

### Pertanyaan Diskusi

**Kelompok 1 - Framework Selection**:
Mengingat multiple stakeholder concerns dan organizational characteristics, framework evaluation apa yang paling appropriate? Apakah Anda akan recommend single framework, hybrid approach, atau multiple frameworks untuk different aspects? Justify pilihan Anda dengan reference pada specific criteria dari section 2.5. Diskusikan trade-offs antara comprehensiveness dan feasibility.

**Kelompok 2 - Methodological Approach**:
Desain mixed methods evaluation strategy yang addresses all stakeholder concerns. Specify: (a) qualitative methods yang akan used, dengan siapa, dan untuk menjawab pertanyaan apa; (b) quantitative methods dan metrics yang akan dikumpulkan; (c) mixed methods design (convergent, sequential, embedded) dan integration strategy; (d) timeline dan sequencing dari different evaluation activities dalam three-month window.

**Kelompok 3 - Implementation Planning**:
Develop detailed implementation plan untuk chosen evaluation approach, addressing: (a) resource allocation (people, time, budget); (b) stakeholder engagement strategy untuk ensure cooperation dan buy-in; (c) potential barriers atau resistances dan mitigation strategies; (d) quality assurance untuk evaluation process itself—bagaimana Anda akan ensure validity, reliability, dan credibility dari evaluation findings?

**Kelompok 4 - Ethical dan Risk Considerations**:
Identify ethical issues dan risks dalam conducting evaluation, particularly given: (a) system handles sensitive financial data; (b) AI components may have bias implications; (c) evaluation findings could significantly impact livelihoods (project team members, user trust, company reputation); (d) time pressure yang may create shortcuts atau compromises. Propose ethical guidelines dan risk mitigation strategies untuk evaluation.

**Plenary Discussion**:
Setelah each group presents, facilitator leads discussion tentang: How would evaluation approach differ jika organizational context changed—misalnya, if company had CMMI Level 3 certification, atau if deployment timeline was satu tahun instead of tiga bulan, atau if system was untuk healthcare instead of fintech? What does this tell us tentang contingent nature dari evaluation framework selection?

---

**Catatan untuk Instruktur**: Studi kasus ini deliberately includes tensions dan trade-offs yang realistis (comprehensiveness vs. timeline, stakeholder demands vs. resource constraints, technical rigor vs. practical feasibility). Encourage students untuk grapple dengan these tensions rather than seeking "perfect" solution. Effective evaluation dalam real world requires judgment, compromise, dan clear articulation dari what was evaluated dan what limitations exist—these are important skills beyond just knowing frameworks dan methods.

---

**[Akhir Bab 2]**
