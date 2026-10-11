# Materi Dasar Teknologi Digital — Fokus P1–P8 (Persiapan UTS)

Kode MK: WI25-00002 · 2 SKS · ITERA · Gasal 2026/2027
Cakupan: **Pertemuan 1–7 (teori) + Pertemuan 8 (UTS)**
Sumber: repo `informatika-itera/dtd` @ `main` (1a660a96), dibaca 2026-10-10.

> Dokumen ini **hanya** memuat materi P1–8. Materi praktikum (P9–14) dan Kuis 2 tidak termasuk.

---

## Peta Materi P1–8

| Pertemuan | Topik | Jenis |
|---|---|---|
| 1 | Pengenalan Dasar Teknologi Digital | Teori |
| 2 | Sistem Bilangan Digital & Logika Digital | Teori |
| 3 | Internet, Website, Basis Data & Media Sosial | Teori |
| 4 | Aplikasi & Etika Teknologi Digital | Teori |
| 5 | Data & Informasi di Era Digital | Teori |
| 6 | Inovasi, AI & Sustainability | Teori |
| 7 | Review, Refleksi, Evaluasi & Kuis 1 (materi 1–6) | Review |
| 8 | **UTS** | Ujian tertulis |

**Struktur UTS:** ujian tertulis, cakupan materi **Pertemuan 1–7**. Kuis 1 (P7) berlangsung maksimal 50 menit dan soalnya diberikan dosen pengampu.

---

# PERTEMUAN 1 — Pengenalan Dasar Teknologi Digital

**Inti:** transformasi digital, sejarah komputer, hardware/software, arsitektur Von Neumann, sistem operasi.

## Konsep kunci
- **Transformasi digital** = integrasi teknologi digital ke **semua** aspek kehidupan. Bukan sekadar alat, tetapi juga **mindset, proses, dan budaya**.
- **Tiga tahap (URUT — sering keluar):**
  1. **Digitisasi** — mengubah **bentuk** analog → digital. Contoh: foto kertas → scan JPG.
  2. **Digitalisasi** — mengubah **proses** manual → digital. Contoh: surat pos → email.
  3. **Transformasi Digital** — perubahan **menyeluruh** model bisnis & budaya. Contoh: ojek pangkalan → Gojek super app.
- **Sejarah singkat:**
  - 1940-an: ENIAC & Colossus (mesin seukuran ruangan, untuk perang & perhitungan ilmiah)
  - 1970–80-an: PC — Apple II, IBM PC, ARPANET
  - 2000-an: Web 2.0, Facebook, YouTube
  - 2020-an: AI, IoT, Cloud
- **Hardware** (perangkat fisik): input · processing (CPU/GPU/RAM) · storage (HDD/SSD) · output · network.
- **Software** (perangkat lunak): sistem operasi · aplikasi · utility · driver · cloud/SaaS.
- **Arsitektur Von Neumann (1945, John von Neumann):** konsep ***stored program*** — program disimpan di memori **bersama** data. Fondasi semua komputer modern.
  - Alur: **Input → CPU (ALU + Control Unit) → Memory (RAM sementara / storage permanen) → Output**
- **Sistem operasi:** mengelola seluruh sumber daya komputer; perantara pengguna ↔ hardware. Contoh: Windows, macOS, Linux, Android, iOS, ChromeOS.
- **Lapisan komputer (dari bawah):** Hardware → OS → Aplikasi → Pengguna.
- **Arduino:** platform mikrokontroler open-source — jembatan dunia digital ↔ fisik.
- **Sensor:** **DHT11** (suhu) · **LDR** (cahaya) · **PIR** (gerakan) · ultrasonik · kelembaban.
- **Dampak:** kesehatan, pendidikan, keuangan, pemerintahan, perdagangan, pertanian.
- **Tantangan:** kesenjangan digital (55,8 juta orang / 19,5% populasi belum terhubung), keamanan data, hoaks, kecanduan, e-waste.

## Angka penting
230 juta pengguna internet Indonesia (2025) · penetrasi **80,5%** · 180 juta pengguna media sosial aktif.

## Jawaban post-test deck P1
1. Transformasi Digital · 2. RAM (bukan bagian CPU) · 3. Keyboard · 4. Mengelola sumber daya komputer

---

# PERTEMUAN 2 — Sistem Bilangan Digital & Logika Digital

**Inti:** mengapa biner, konversi basis, satuan data, gerbang logika.

## Konsep kunci
- **Mengapa biner:** transistor — komponen dasar chip — hanya punya **dua kondisi: ON (1) / OFF (0)**. Sinyal dua level lebih stabil dan tahan noise daripada sinyal multi-level. Satu chip modern = **miliaran transistor**.
- **Biner (basis 2):** tiap posisi berbobot pangkat 2.
  - Contoh: `1101₂` = 1×8 + 1×4 + 0×2 + 1×1 = **13₁₀**
- **Konversi:**
  - **Desimal → biner:** bagi 2 berulang, baca sisa **dari BAWAH ke ATAS**. (13₁₀ → 1101₂)
  - **Biner → desimal:** kalikan tiap digit dengan bobot posisinya (pangkat 2), lalu jumlahkan.
- **Semua data disimpan sebagai biner:**
  - Teks — **ASCII**: "A" = `01000001`
  - Warna — **RGB/heksadesimal**: merah = `FF0000`
  - Gambar — matriks pixel
  - Audio — **44.100 sampel per detik**
- **Satuan data:** bit → **byte (8 bit)** → KB (**1.024 B**) → MB (**1.024 KB**) → GB (**1.024 MB**). Semua naik **×1.024**.
  - 1 karakter ASCII = 1 byte · 1 halaman teks ≈ 2 KB · foto HP ≈ 3–5 MB · film HD ≈ 4 GB
- **Logika digital:** benar (1) / salah (0).
  - **AND** → 1 jika **SEMUA** input bernilai 1
  - **OR** → 1 jika **SALAH SATU** (minimal satu) input bernilai 1
  - **NOT** → membalik nilai (0→1, 1→0)
  - *(Deck review P7 menambahkan **XOR, NAND, NOR** — deck P2 sendiri hanya membahas AND/OR/NOT)*
- **Aplikasi nyata:**
  - Alarm keamanan (pintu **ATAU** jendela terbuka) → **OR**
  - Lampu tangga 2 saklar (beda posisi = nyala) → **XOR**
  - Kalkulator & CPU → kombinasi AND + OR + NOT
  - Absensi digital (wajah cocok **DAN** waktu tepat → Hadir), filter spam

## Jawaban post-test deck P2
1. Transistor hanya punya dua kondisi · 2. 1101 · 3. 1.024 byte · 4. Salah satu input 1

---

# PERTEMUAN 3 — Internet, Website, Basis Data & Media Sosial

**Inti:** cara kerja internet, cloud, website, database, media sosial, literasi digital.

## Konsep kunci
- **Internet** = jaringan global yang terhubung via protokol standar **TCP/IP**.
  - **TCP** — membagi & menyusun ulang data
  - **IP** — alamat pengirim dan tujuan
  - **Port** — jalur layanan (80 = HTTP, 443 = HTTPS)
  - **DNS** — "buku telepon internet": menerjemahkan domain → IP address (google.com → 142.250.x.x)
- **Perjalanan data:** Client → ISP → Router → Server.
  - Data dipecah menjadi **paket-paket kecil** berheader, bisa melewati **jalur berbeda**, lalu **disusun ulang oleh TCP** di tujuan.
  - **Routing** antar-hop; setiap hop = satu router.
- **Cloud computing:** memproses data secara online tanpa install. Contoh: Google Docs, Zoom, Canva. (Bedakan dengan **cloud storage** seperti Google Drive.)
- **Website:** dibangun dari tiga teknologi:
  - **HTML** → struktur
  - **CSS** → presentasi/tampilan
  - **JavaScript** → interaktivitas
  - Rantai arsitektur: **Browser (klien) ⟺ Web Server (Apache/Nginx) ⟺ Database (MySQL/MongoDB)**
- **Database:**
  - **SQL** — relasional, tabel baris/kolom, skema **rigid** → MySQL, PostgreSQL, Oracle
  - **NoSQL** — dokumen/key-value/graf, skema **fleksibel**, skala horizontal → MongoDB, Redis, Cassandra
  - Kapan pakai? Butuh konsistensi ketat → **SQL**. Butuh fleksibilitas & skala besar → **NoSQL**. Banyak sistem modern pakai **keduanya** (*polyglot persistence*).
- **Media sosial — evolusi:** 2004 Facebook → 2006 Twitter → 2010 Instagram → 2011 WhatsApp → 2016 TikTok. **4,9 miliar** pengguna dunia; rata-rata **2,5 jam/hari**, 6+ platform per pengguna.
- **Dampak negatif:** hoaks menyebar **~6× lebih cepat** dari informasi benar, cyberbullying, kecanduan/FOMO, masalah privasi.
- **4 pilar literasi digital:** (1) cari & verifikasi · (2) keamanan digital · (3) etika digital · (4) berpikir kritis (kenali **bias algoritma, filter bubble, echo chamber**).

## Angka penting
230 juta pengguna internet Indonesia · rata-rata **3,5 jam online/hari** · 180 juta pengguna medsos.

## Jawaban post-test deck P3
1. HTTP/HTTPS · 2. Mengubah domain ke IP address · 3. Paket-paket kecil · 4. Gmail

---

# PERTEMUAN 4 — Aplikasi & Etika Teknologi Digital

**Inti:** penerapan teknologi di berbagai bidang + etika & tanggung jawab digital.

## Konsep kunci
- **Pendidikan:** **LMS** (Learning Management System — Moodle, Google Classroom), video conference, MOOC, adaptive learning & AI tutor.
- **E-Government:** Dukcapil Online, e-Filing DJP Online, LPSE/e-Procurement, **LAPOR!/SP4N**.
- **E-Commerce:** marketplace (Tokopedia, Shopee), B2B (Indonetwork, Ralali), fintech (GoPay, OVO, DANA), logistik (JNE, SiCepat).
- **Bidang lain:** kesehatan (**telemedicine**, 20+ juta konsultasi/tahun), pertanian (**precision farming**, +30% hasil panen), transportasi (ride-hailing, 2+ juta mitra).
- **Etika digital:** privasi & keamanan · hak kekayaan intelektual (HAKI) · netiket & anti ujaran kebencian.
- **Hak digital (4):** akses internet setara · kebebasan berekspresi online · privasi & perlindungan data · keamanan dari ancaman siber.
- **Kewajiban digital (4):** menyaring informasi sebelum berbagi · menghargai HAKI · menjaga keamanan akun sendiri · melaporkan konten ilegal.
- **THINK sebelum posting:** **T**rue · **H**elpful · **I**nspiring · **N**ecessary · **K**ind.
- **Etika email (4 langkah):** subjek jelas → salam & perkenalan → isi ringkas & bahasa formal → penutup & tanda tangan.
  - **HURUF KAPITAL SEMUA = berteriak** dalam komunikasi digital.
- **Studi kasus:** penyebaran hoaks (terancam **UU ITE**), plagiarisme akademik (Turnitin), data breach (enkripsi lemah).

## Jawaban post-test deck P4
1. LMS · 2. e-Filing DJP Online · 3. Telemedicine · 4. Menyebarkan foto orang lain tanpa izin

---

# PERTEMUAN 5 — Data & Informasi di Era Digital

**Inti:** hierarki data, format & ukuran, big data, keamanan siber.

## Konsep kunci
- **Hierarki DIKW:**
  - **Data** — fakta mentah, belum berkonteks ("36.5")
  - **Informasi** — data yang sudah diolah + konteks sehingga bermakna ("Suhu tubuh pasien A 36,5°C")
  - **Pengetahuan (knowledge)** — informasi + pengalaman → dipakai untuk mengambil keputusan
- **Format data:** teks (.txt/.pdf/.docx) · gambar (.jpg/.png/.webp) · audio (.mp3/.wav/.flac) · video (.mp4/.mkv/.webm).
- **Hierarki penyimpanan:** Byte → KB → MB → GB → TB → PB (semua **×1.024**).
- **Big Data 3V:** **Volume** (petabyte–exabyte; 500+ juta tweet/hari) · **Velocity** (kecepatan/real-time) · **Variety** (keragaman: terstruktur, semi-terstruktur JSON/XML, tidak terstruktur).
  - *(Deck review P7 menambahkan **Veracity** → **4V**.)*
- **Analytics:** machine learning, data mining, predictive analytics, business intelligence.
- **Keamanan siber:** kerugian global **$8 triliun** (2023) — setara PDB ketiga terbesar dunia.
- **Malware:**
  - **Virus** — menempel pada file, menyebar saat file dieksekusi
  - **Worm** — menyebar otomatis via jaringan tanpa file inang
  - **Trojan** — menyamar sebagai software sah, membuka backdoor
  - **Ransomware** — mengenkripsi file korban, minta tebusan (Bitcoin)
  - **Spyware** — mengintai aktivitas pengguna diam-diam (keystroke, kredensial)
- **Phishing** — email/chat yang menyamar sebagai pihak sah untuk mencuri kredensial/data kartu kredit.
- **Social engineering** — manipulasi psikologis (bukan kelemahan teknis):
  - **Pretexting** — skenario palsu (mengaku dari bank/IT kampus)
  - **Baiting** — umpan USB atau link
  - **Tailgating** — menyusup fisik di belakang karyawan
  - *"Manusia adalah rantai keamanan paling lemah." — Kevin Mitnick*
- **2FA:** **something you know** (password/PIN) + **something you have** (HP/token). **Authenticator app lebih aman dari SMS** (SMS rawan SIM-swap).
- **Backup 3-2-1:** **3** salinan data · **2** jenis media berbeda · **1** salinan di luar lokasi (offsite).

## Angka penting
2,5 kuintiliun byte data/hari · 90% data dunia tercipta dalam 2 tahun terakhir · 5,5 miliar pengguna internet dunia.

## Jawaban post-test deck P5
1. Informasi · 2. Variety · 3. Ransomware · 4. Social Engineering

---

# PERTEMUAN 6 — Inovasi, AI & Sustainability

**Inti:** startup Indonesia, pengantar AI/ML, Industry 4.0/5.0, e-waste.

## Konsep kunci
- **Ekosistem startup Indonesia:** 2.126 startup terdaftar · **8 unicorn & decacorn** · 77% populasi internet aktif · **$8B+** pendanaan (2023). Contoh: GoTo (Gojek+Tokopedia), Bukalapak, OVO/DANA, BCA Digital.
- **Perjalanan startup:** Ideation → **MVP** (Minimum Viable Product — produk minimal yang bisa diuji ke pasar) → Product-Market Fit → Funding (Angel → Series A/B/C → IPO) → Scale-up.
- **AI** = bidang yang membuat mesin meniru kecerdasan manusia (belajar, bernalar, memutuskan).
- **Machine Learning** = **subset AI**; sistem **belajar dari data** tanpa diprogram secara eksplisit.
  - Jenis ML: **Supervised** · **Unsupervised** · **Reinforcement** · **Deep Learning**
- **Cabang AI:** Expert Systems · **NLP** (Natural Language Processing — memahami bahasa manusia) · **Computer Vision** (gambar/video: Face ID, mobil otonom, X-ray) · Robotika · **Fuzzy Logic** (AC otomatis, kontrol kamera) · Genetic Algorithms.
- **Aplikasi:** NLP (asisten virtual, translate) · Computer Vision · sistem rekomendasi (Netflix, Spotify, e-commerce).
- **Industry 4.0** = otomatisasi & IoT, smart factory, fokus **efisiensi**.
  **Industry 5.0** = kolaborasi manusia–mesin (**cobot**), **human-centric** & berkelanjutan.
- **Chatbot:** rule-based (if-then) · AI-powered/LLM (ChatGPT, Gemini) · hybrid (paling umum di industri).
- **Etika AI bagi mahasiswa:** AI = alat bantu belajar, **bukan pengganti proses berpikir**. Pahami jangan menyalin · verifikasi fakta · jaga integritas akademik · lindungi data pribadi · ikuti aturan kampus.
- **E-waste:** **62 juta ton/tahun**, hanya **22% didaur ulang**; siklus ganti HP 3–5 tahun. Prinsip **3R: Reduce, Reuse, Recycle**.

## Jawaban post-test deck P6
1. NLP · 2. 5.0 mengembalikan manusia ke pusat industri · 3. Produk minimal yang bisa diuji pasar · 4. Reduce, Reuse, Recycle

---

# PERTEMUAN 7 — Review, Refleksi, Evaluasi & Kuis 1

- Mengulas materi **Pertemuan 1–6** dalam tiga blok:
  1. **Fondasi digital** — data, biner, sistem bilangan, gerbang logika
  2. **Internet & aplikasi** — web, cloud, media sosial, AI, industri 4.0
  3. **Keamanan & etika digital** — cybersecurity, privasi, tanggung jawab warga digital
- **Refleksi pemantik:** kenapa biner · data apa yang kamu hasilkan di medsos · langkah keamanan konkret · peran etika.
- **Kuis 1:** maksimal **50 menit** — soal diberikan dosen pengampu (tidak ada di deck).
- Catatan review di deck ini menyebut **gerbang logika lengkap: AND, OR, NOT, XOR, NAND, NOR** (deck P2 hanya membahas AND/OR/NOT) — **jadi siapkan juga XOR/NAND/NOR**.

---

# PERTEMUAN 8 — UTS

Ujian **tertulis**, cakupan materi **Pertemuan 1–7**. Tidak ada deck materi untuk pertemuan ini.

---

# KISI-KISI: Konsep yang Paling Sering Keluar

## 🔴 Prioritas tinggi (hafalan + pemahaman)
1. **3 tahap digitalisasi** (digitisasi → digitalisasi → transformasi digital) + contoh tiap tahap
2. **Arsitektur Von Neumann** — stored program, alur Input → CPU → Memory → Output
3. **Konversi biner ↔ desimal** (latih soal!)
4. **Gerbang logika** — tabel kebenaran AND, OR, NOT (+ XOR, NAND, NOR)
5. **Satuan data** — 8 bit = 1 byte, kelipatan **1.024**
6. **TCP vs IP vs DNS** — peran masing-masing
7. **SQL vs NoSQL** — perbedaan & kapan dipakai
8. **Hierarki data → informasi → pengetahuan** + contoh
9. **Big Data 3V/4V** — Volume, Velocity, Variety (+ Veracity)
10. **Jenis malware** — virus, worm, trojan, ransomware, spyware
11. **Social engineering** — pretexting, baiting, tailgating
12. **Backup 3-2-1**
13. **2FA** — dua faktor + kenapa authenticator > SMS
14. **Industry 4.0 vs 5.0**
15. **AI vs ML** + cabang AI (NLP, Computer Vision, dll.)
16. **3R e-waste** + angka 62 juta ton / 22%

## 🟡 Angka yang sering jadi soal
| Angka | Konteks |
|---|---|
| 80,5% / 230 juta | penetrasi & pengguna internet Indonesia (2025) |
| 180 juta | pengguna media sosial Indonesia |
| 4,9 miliar | pengguna media sosial dunia |
| ~6× | hoaks lebih cepat menyebar |
| 44.100 | sampel audio per detik |
| $8 triliun | kerugian serangan siber global (2023) |
| 2,5 kuintiliun | byte data dibuat per hari |
| 90% | data dunia tercipta dalam 2 tahun terakhir |
| 8 | unicorn & decacorn Indonesia |
| 62 juta ton / 22% | e-waste global per tahun / yang didaur ulang |

## 🟢 Hafalan cepat
- **THINK** = True, Helpful, Inspiring, Necessary, Kind
- **3R** = Reduce, Reuse, Recycle
- **3-2-1** = 3 salinan, 2 media, 1 offsite
- **4 hak digital** & **4 kewajiban digital**
- **3V** = Volume, Velocity, Variety
- **Lapisan komputer** = Hardware → OS → Aplikasi → Pengguna
- **Sensor** = DHT11 (suhu), LDR (cahaya), PIR (gerakan)
- **ASCII** "A" = 01000001

## ⚠️ Catatan penting
- Deck review **P7** menambah **XOR/NAND/NOR** dan **Veracity (4V)** yang tidak ada di deck P1–6. **Siapkan keduanya** — bisa keluar di UTS.
- Soal Kuis 1 tidak ada di deck (diberikan dosen), jadi tidak bisa diprediksi persis.

---

## Tips Belajar untuk UTS
1. **Biner wajib bisa hitung manual** — bukan hafalan. Latih konversi dua arah sampai lancar.
2. **Gerbang logika: hafal tabel kebenaran**, lalu latih kasus nyata (alarm, lampu saklar).
3. **Bedakan konsep yang mirip:** digitisasi vs digitalisasi vs transformasi · data vs informasi vs pengetahuan · AI vs ML · virus vs worm vs trojan.
4. **Kaitkan angka dengan konteksnya** — biasanya muncul di soal isian/PG.
5. **Pahami, jangan hafal mentah** — soal UTS cenderung aplikatif (contoh & kasus).
