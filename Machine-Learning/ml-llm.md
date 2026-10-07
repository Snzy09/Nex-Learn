# Machine Learning dan LLM: Pengantar untuk Mahasiswa

## Mengapa topik ini relevan bagi Anda

Apa pun jurusan Anda, Machine Learning (ML) akan Anda temui dalam salah satu bentuk ini: alat yang Anda pakai (Google Translate untuk jurnal berbahasa Inggris, filter spam email kampus), topik skripsi (klasifikasi sentimen, prediksi kelulusan, computer vision), atau syarat pekerjaan yang Anda lamar setelah lulus. Artikel ini memberi fondasi konsep yang cukup untuk membaca paper dasar dan memilih arah spesialisasi.

## Dari pemrograman konvensional ke Machine Learning

Pemrograman konvensional bekerja dengan pola: **data + aturan → jawaban**. Programmer menulis aturan secara eksplisit. Contoh sederhana: sistem penilaian kelulusan mata kuliah — input nilai, aturannya rata-rata ≥ 75, output lulus.

ML membalik polanya menjadi: **data + jawaban → aturan**. Kita tidak menulis aturan. Kita menyerahkan pasangan contoh-jawaban kepada algoritma, dan algoritma menghasilkan *model* — itulah "aturan" hasil pembelajaran.

Konsekuensi penting dari pembalikan ini: **kualitas model dibatasi kualitas data**. Prinsip *garbage in, garbage out* berlaku lebih ketat di ML daripada pemrograman biasa, karena kesalahan data tidak muncul sebagai error di console. Ia bersembunyi di dalam model dan muncul sebagai prediksi yang salah diam-diam.

Definisi klasik yang sering dikutip di mata kuliah, dari Tom Mitchell (1997): sebuah program dikatakan *belajar* jika kinerjanya pada suatu tugas meningkat seiring bertambahnya pengalaman (data).

Istilah yang akan muncul terus:

- **Fitur (feature):** atribut input. Contoh: frekuensi kata dalam email, IP semester mahasiswa.
- **Label:** jawaban benar yang ingin diprediksi. Contoh: spam/bukan, lulus tepat waktu/tidak.
- **Training dan testing:** data dibagi dua. Model belajar dari data latih, lalu diuji pada data uji yang belum pernah dilihat, untuk mengukur kemampuan *generalisasi*.
- **Overfitting:** model terlalu hafal data latih termasuk noise-nya, lalu buruk pada data baru. Masalah paling klasik di mata kuliah ML — dan di skripsi.

## Tiga paradigma Machine Learning

**1. Supervised learning (pembelajaran terbimbing).** Data berupa pasangan input–label. Dua rumpun tugasnya:

- *Klasifikasi*: label berupa kategori. Contoh: mengklasifikasikan ulasan film menjadi positif atau negatif.
- *Regresi*: label berupa angka kontinu. Contoh: memprediksi harga rumah dari luas, lokasi, jumlah kamar.

Algoritma klasik yang wajib Anda kenal: linear regression, logistic regression, decision tree, random forest, support vector machine (SVM).

**2. Unsupervised learning (pembelajaran tak terbimbing).** Data tanpa label. Model mencari struktur laten sendiri:

- *Clustering*: mengelompokkan data serupa. Algoritma populer: k-means.
- *Dimensionality reduction*: merampingkan fitur berdimensi tinggi sambil mempertahankan informasi penting. Contoh: PCA, dipakai untuk visualisasi data atau mempercepat training.
- *Anomaly detection*: menemukan data yang menyimpang dari pola umum.

**3. Reinforcement learning (pembelajaran penguatan).** Sebuah *agent* mengambil aksi di dalam *environment*, menerima *reward* atau *penalty*, lalu memperbarui strateginya (*policy*) agar total reward maksimal. Framework matematisnya, *Markov Decision Process*, akan Anda temui di literatur RL lanjutan. Contoh landmark: AlphaGo mengalahkan juara dunia Go (DeepMind, 2016).

## Konsep yang menentukan berhasil-gagalnya model

**Bias–variance tradeoff.** Model terlalu kaku menghasilkan bias tinggi (*underfit*) — pola tidak tertangkap. Model terlalu fleksibel menghasilkan variance tinggi (*overfit*) — noise ikut dihafal. Memilih kompleksitas model adalah seni menyeimbangkan keduanya. Analogi: mahasiswa yang menghafal soal tahun lalu tanpa paham konsep akan kaget saat soal ujian berbeda.

**Train–validation–test split.** Praktik baku: data dibagi tiga. *Train* untuk melatih, *validation* untuk memilih hiperparameter, *test* untuk mengukur performa akhir — dibuka sesekali saja. Pelanggaran paling umum di skripsi pemula: menguji model dengan data yang pernah dipakai melatih. Hasilnya akurasi tinggi palsu.

**Metrik evaluasi.** Akurasi saja tidak cukup saat data tidak seimbang. Contoh: kalau 99% transaksi tidak curang, model yang selalu menjawab "tidak curang" pun akurasinya 99% — dan sama sekali tidak berguna. Karena itu kenali *precision*, *recall*, dan *F1-score*. Untuk kelas tidak seimbang, ada teknik *oversampling* (misal SMOTE) dan *undersampling*.

## Dari Machine Learning ke LLM

**Neural network.** Fondasi modern ML. Susunan unit sederhana (neuron) berlapis; tiap neuron menghitung kombinasi linear dari inputnya lalu menerapkan fungsi aktivasi non-linear. Dengan cukup banyak lapis, jaringan bisa merepresentasikan fungsi sangat kompleks — dari sinilah istilah *deep learning*.

**Representasi bahasa: dari kata ke angka.** Komputer tidak memahami kata; ia mengoperasikan angka. Kata (atau potongan kata, disebut *token*) diubah menjadi *embedding*: vektor berdimensi tinggi yang disusun sedemikian rupa sehingga kata bermakna mirip berdekatan secara geometris. Dalam ruang embedding, "raja" dan "ratu" berdekatan, dan hubungan semantis bisa muncul sebagai arah vektor.

**Arsitektur Transformer dan attention.** Terobosan tahun 2017 lewat paper *Attention Is All You Need* (Vaswani dkk.) — kutipan wajib kalau Anda menulis karya ilmiah tentang LLM. Mekanisme *self-attention* memungkinkan setiap token "melihat" token lain dan menimbang mana yang relevan. Ini memecahkan kelemahan model bahasa sebelumnya (RNN/LSTM) yang memproses kata berurutan dan mudah kehilangan konteks jarak jauh. Keunggulan kedua Transformer: bisa diproses paralel, sehingga layak dilatih dengan skala masif.

**Cara LLM dilatih.** Tugas latih awalnya terlihat sepele: menebak token berikutnya. Tapi untuk menebak akurat pada triliunan token, model terpaksa mempelajari tata bahasa, fakta dunia, logika sederhana, sampai gaya penulisan. Setelah *pretraining*, model disempurnakan dengan:

- *Fine-tuning / instruction tuning*: melatih dengan contoh instruksi dan jawaban yang diinginkan.
- *RLHF (Reinforcement Learning from Human Feedback)*: manusia memberi peringkat pada jawaban model; model reward dari peringkat itu dipakai mengoptimalkan perilaku agar lebih membantu dan aman.

Kata "large" merujuk skala: jumlah parameter (bisa ratusan miliar), volume data latih, dan biaya komputasi. Temuan penting riset skala: kemampuan model umumnya naik seiring skala, dan beberapa kemampuan baru muncul hanya pada ukuran tertentu (*emergent abilities*).

**Batasan yang wajib Anda sampaikan di karya ilmiah.** LLM bisa *halusinasi*: menghasilkan klaim salah dengan bahasa sangat meyakinkan, termasuk mengarang sitasi. Model juga mewarisi bias data latih dan punya *knowledge cutoff*. Konsekuensinya: output LLM adalah bahan mentah, bukan rujukan. Verifikasi setiap fakta dan sitasi ke sumber primer.

## Contoh kasus untuk konteks akademik

**1. Klasifikasi sentimen ulasan (skripsi paling umum di Indonesia).** Ambil data ulasan aplikasi dari Google Play Store berbahasa Indonesia, beri label positif/negatif/netral, latih model. Alur tipikal: scraping → *preprocessing* (case folding, stopword removal, stemming dengan library Sastrawi) → ekstraksi fitur (TF-IDF atau embedding) → training → evaluasi dengan precision/recall/F1. Perbandingan menarik untuk penelitian: ML klasik (Naive Bayes, SVM) vs fine-tuning model bahasa (IndoBERT). Biasanya model bahasa menang, tapi butuh komputasi jauh lebih berat.

**2. Prediksi kelulusan tepat waktu.** Data mahasiswa angkatan lama (IPK per semester, asal sekolah, durasi tugas akhir) dipasangkan dengan label lulus tepat waktu atau tidak. Model supervised seperti random forest dilatih, lalu dipakai prodi untuk mengidentifikasi mahasiswa berisiko tinggi sejak semester awal. Catatan etika yang perlu dibahas di skripsi: prediksi harus berujung pada intervensi dukungan, bukan stigmatisasi.

**3. Clustering literatur penelitian.** Data publikasi dosen (kata kunci, topik, tahun) dikelompokkan dengan k-means atau topic modeling (LDA) tanpa label awal. Berguna untuk memetakan arah riset laboratorium atau memilih topik tugas akhir yang belum jenuh.

**4. Asisten tanya-jawab dokumen kampus (LLM + RAG).** RAG (*Retrieval-Augmented Generation*) menggabungkan LLM dengan pencarian dokumen: pertanyaan dicocokkan dulu ke dokumen sumber (buku pedoman, informasi akademik), lalu LLM menyusun jawaban dari potongan yang ditemukan. Pola ini mengurangi halusinasi dan menjadi pendekatan umum untuk chatbot berbasis dokumen internal.

**5. Latihan reinforcement learning.** Untuk praktik, *Gymnasium* (dulu OpenAI Gym) adalah lingkungan latihan RL standar di banyak mata kuliah — mulai dari CartPole sebelum menuju lingkungan yang lebih kompleks.

## Peta belajar lanjutan

1. **Fondasi:** matematika (aljabar linear, kalkulus, statistika) dan Python sebagai bahasa standar.
2. **ML dasar:** konsep overfitting, train-test split, evaluasi model. Mata kuliah Machine Learning atau buku *Hands-On Machine Learning* (Aurélien Géron) adalah titik awal yang umum.
3. **Deep learning:** jaringan saraf, lalu arsitektur Transformer.
4. **Praktik:** kompetisi Kaggle, proyek kecil dengan data publik, atau kontribusi riset di lab kampus.

## Ringkasan

ML mengubah cara membangun sistem: dari menulis aturan menjadi menurunkan aturan dari data, dengan tiga paradigma — supervised, unsupervised, reinforcement learning. LLM adalah puncak perkembangannya di domain bahasa: model Transformer raksasa yang dilatih memprediksi token berikutnya. Bagi mahasiswa, pemahaman konsep ini adalah fondasi sekaligus bekal kritis — teknologi ini kuat tetapi tidak sempurna, dan kemampuan menilai batasnya sama pentingnya dengan kemampuan memakainya.

## Rujukan

- Tom Mitchell, *Machine Learning*, McGraw-Hill, 1997.
- Vaswani dkk., "Attention Is All You Need", NeurIPS 2017.
- Aurélien Géron, *Hands-On Machine Learning with Scikit-Learn, Keras & TensorFlow*, O'Reilly.
- Ian Goodfellow dkk., *Deep Learning*, MIT Press, 2016.
