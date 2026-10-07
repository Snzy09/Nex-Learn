# ML & LLM: Pseudocode dan Flowchart

Pendamping `ml-llm.md`. Dipakai untuk memahami alur, bukan untuk produksi.

## 1. Alur kerja Machine Learning (supervised)

Pseudocode langkah demi langkah, dari data mentah sampai model terpakai:

```text
MULAI
  INPUT: dataset mentah D, daftar label L

  // Tahap 1: siapkan data
  D_bersih = bersihkan(D)          // buang duplikat, isi nilai kosong
  X, y    = pisahkan_fitur_label(D_bersih, L)

  // Tahap 2: bagi data (jangan diacak setelah dibagi)
  X_latih, X_sisa, y_latih, y_sisa = split(X, y, 80%, 20%)
  X_valid, X_uji, y_valid, y_uji   = split(X_sisa, y_sisa, 50%, 50%)

  // Tahap 3: pilih model + hiperparameter lewat validasi
  model_terbaik = TIDAK ADA
  performa_terbaik = 0
  UNTUK setiap kandidat M di [NaiveBayes, SVM, RandomForest]:
      UNTUK setiap hiperparameter H di grid:
          M_latih = latih(M, H, X_latih, y_latih)
          skor    = evaluasi(M_latih, X_valid, y_valid)
          JIKA skor > performa_terbaik:
              model_terbaik   = M_latih
              performa_terbaik = skor

  // Tahap 4: ukur performa akhir (dibuka sekali saja)
  laporan = evaluasi(model_terbaik, X_uji, y_uji)   // precision, recall, F1

  JIKA performa lolos target:
      simpan model_terbaik
      PAKAI ke data baru
  JIKA TIDAK:
      KEMBALI ke Tahap 1   // tambah data, perbaiki fitur, ulangi
SELESAI
```

Catatan penting: data uji (`X_uji`) hanya disentuh di Tahap 4. Kalau dipakai berulang untuk memilih model, hasilnya berhenti jadi pengukur jujur.

## 2. Flowchart alur Machine Learning

```mermaid
flowchart TD
    A[Dataset mentah] --> B[Bersihkan data]
    B --> C[Pisah fitur X dan label y]
    C --> D[Bagi: train / validation / test]
    D --> E[Latih kandidat model<br/>pada data train]
    E --> F[Evaluasi pada data validation]
    F --> G{Performa<br/>memenuhi target?}
    G -- Tidak --> H[Perbaiki data / fitur / model]
    H --> D
    G -- Ya --> I[Uji pada data test<br/>sekali saja]
    I --> J[Simpan model]
    J --> K[Pakai ke data baru]
```

## 3. Flowchart tiga paradigma ML

```mermaid
flowchart TD
    A[Punya data] --> B{Data punya label?}
    B -- Ya, ada jawaban --> C[Supervised learning]
    B -- Tidak --> D[Unsupervised learning]
    C --> C1{Label kategori<br/>atau angka?}
    C1 -- Kategori --> C2[Klasifikasi<br/>contoh: spam / bukan]
    C1 -- Angka --> C3[Regresi<br/>contoh: harga rumah]
    D --> D1[Clustering<br/>contoh: k-means]
    D --> D2[Reduksi dimensi<br/>contoh: PCA]
    D --> D3[Deteksi anomali]
    A --> E{Ada agent<br/>yang berinteraksi?}
    E -- Ya, dapat reward --> F[Reinforcement learning]
    F --> F1[Agent ambil aksi]
    F1 --> F2[Terima reward / penalty]
    F2 --> F3[Perbarui policy]
    F3 --> F1
```

## 4. Alur pelatihan LLM

```text
MULAI
  INPUT: korpus teks raksasa (internet, buku, kode)

  // Tahap 1: ubah teks jadi angka
  token_ids = tokenisasi(korpus)      // kata -> token -> id angka
  embedding = ubah_ke_vektor(token_ids)

  // Tahap 2: pretraining
  ULANGI jutaan langkah:
      prediksi = model(teks_sebelumnya)         // tebak token berikutnya
      error    = bandingkan(prediksi, token_benar)
      perbarui_bobot_model(error)               // backpropagation
  // Hasil: model paham tata bahasa, fakta, gaya penulisan

  // Tahap 3: penyempurnaan
  fine_tuning(model, contoh_instruksi_jawaban)
  rlhf(model, peringkat_jawaban_dari_manusia)

  // Tahap 4: pemakaian (inference)
  INPUT prompt dari pengguna
  ULANGI per token:
      token_baru = model.prediksi_token_berikutnya()
      TAMPILKAN token_baru
  SELESAI SAAT token <akhir> atau batas tercapai
SELESAI
```

## 5. Flowchart pemakaian LLM yang aman

```mermaid
flowchart TD
    A[Pengguna beri prompt] --> B[LLM hasilkan jawaban]
    B --> C{Jawaban berisi<br/>fakta / angka / sitasi?}
    C -- Ya --> D[Verifikasi ke sumber primer]
    D --> E{Benar?}
    E -- Tidak --> F[Jangan pakai.<br/>Minta LLM perbaiki atau kerjakan manual]
    E -- Ya --> G[Pakai, sebutkan sumber]
    C -- Tidak --> G
    G --> H{Keputusan berisiko tinggi?<br/>medis, hukum, keuangan}
    H -- Ya --> I[Libatkan ahli manusia<br/>sebelum bertindak]
    H -- Tidak --> J[Selesai]
    I --> J
```

## Cara membaca dokumen ini

Empat blok di atas saling melengkapi: blok 1–2 menunjukkan siklus kerja ML secara umum, blok 3 memetakan pilihan paradigma, blok 4–5 masuk ke LLM dari sisi training sampai pemakaian yang bertanggung jawab. Untuk belajar, coba gambar ulang flowchart dari ingatan tanpa melihat — kalau alurnya sudah benar, konsepnya sudah melekat.
