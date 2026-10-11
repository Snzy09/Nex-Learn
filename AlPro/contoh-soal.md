# Soal Latihan UTS — Algoritma Pemrograman

Kode MK: **IF25-11001** · 2 SKS Teori · S1 Teknik Informatika ITERA · Gasal 2026/2027
Cakupan: **Pertemuan 1–6** (materi UTS) · Durasi saran: **120 menit** · 5 bagian bergaya UTS
Sifat: **tutup buku + cheat sheet 1 halaman A4 tulisan tangan**

> Soal **buatan** (bukan soal resmi dosen), disusun dari deck P1–P6 + contoh UTS P8 untuk latihan.
> **Semua trace table & perhitungan sudah diverifikasi dengan simulasi** (26 kasus, semua cocok).
> Mata kuliah ini berbasis **pseudocode & flowchart**, bukan C++.
> Kunci & pembahasan ada di bagian bawah — jangan diintip dulu.

---

# BAGIAN A — ESAI (5 soal)

## Esai 1 (P1 — Computational Thinking)
(a) Sebutkan dan jelaskan singkat **4 pilar Computational Thinking** beserta satu contoh.
(b) Sebutkan **5 ciri algoritma yang baik**.
(c) Perhatikan pseudocode berikut — ciri apa yang **dilanggar** dan mengapa?
```
i ← 1
SELAMA i > 0
    OUTPUT i
    i ← i + 1
AKHIR SELAMA
```
(d) Sebutkan **3 cara merepresentasikan algoritma**.

## Esai 2 (P2 — Tipe Data, Variabel, Ekspresi)
(a) Jelaskan perbedaan **deklarasi**, **inisialisasi**, dan **assignment** dengan contoh pseudocode.
(b) Lengkapi **trace table** berikut, lalu tulis output `a`, `b`, `c`:
```
DEKLARASI a, b, c : integer
a ← 9
b ← a / 2
c ← a MOD 2
a ← b * c + a
OUTPUT a, b, c
```
(c) Jelaskan mengapa `double z ← 7 / 2` menghasilkan `3.0` (bukan `3.5`), dan bagaimana memperbaikinya.
(d) Jelaskan mengapa **swap** `a ← b; b ← a` gagal, dan tulis perbaikannya.

## Esai 3 (P3 — Operator dan Precedence)
(a) Evaluasi **langkah demi langkah**: `8 + 4 * 3 - 6 / 2` — tunjukkan urutannya.
(b) Evaluasi **langkah demi langkah**: `10 % 3 + 7 * (2 + 1)`.
(c) Lengkapi **truth table** untuk membuktikan `!(A && B) ≡ !A || !B`:

| A | B | A && B | !(A && B) | !A | !B | !A \|\| !B | ≡? |
|---|---|---|---|---|---|---|---|
| T | T | | | | | | |
| T | F | | | | | | |
| F | T | | | | | | |
| F | F | | | | | | |

(d) Berapa nilai `x` akhir: `x ← 10; x += 5; x *= 2; x -= 3`?

## Esai 4 (P4 — Percabangan)
Sebuah toko buku memberi diskon berdasarkan status dan total belanja:
- Member + belanja ≥ 200rb → diskon 20%
- Member + belanja < 200rb → diskon 10%
- Non-member + belanja ≥ 200rb → diskon 5%
- Non-member + belanja < 200rb → diskon 0%

(a) Gambar **decision tree** lengkap.
(b) Tulis **pseudocode** lengkap dengan IF-ELSE IF (dan nested IF bila perlu).
(c) **Trace** untuk: `member = true, belanja = 250000` → berapa diskon (%)?
(d) Jelaskan mengapa blok `ELSE` di akhir penting, beri contoh kasus yang salah bila dihilangkan.

## Esai 5 (P5 + P6 — Perulangan & Pattern)
(a) Lengkapi **trace table** (kolom `i`, `nilai`, `total`, `maks`, `count`) lalu tulis 3 baris output:
```
DEKLARASI total, maks, count, i, nilai : integer
total ← 0
maks ← 0
count ← 0
UNTUK i ← 1 SAMPAI 7
    nilai ← i * 2 + 1
    total ← total + nilai
    JIKA nilai > maks MAKA
        maks ← nilai
    AKHIR JIKA
    JIKA nilai MOD 3 == 0 MAKA
        count ← count + 1
    AKHIR JIKA
AKHIR UNTUK
OUTPUT "Total =", total
OUTPUT "Maks =", maks
OUTPUT "Kelipatan3 =", count
```
(b) Tulis **pseudocode nested loop** untuk menampilkan piramida bintang tinggi `N = 4`, dan turunkan **rumus** spasi dan bintang untuk baris ke-`i`.
(c) Berapa **total operasi WRITE** dan apa **kompleksitas** algoritma berikut?
```
UNTUK i ← 1 SAMPAI N
    UNTUK j ← 1 SAMPAI i
        WRITE "*"
    AKHIR UNTUK
AKHIR UNTUK
```

---

# BAGIAN B — PILIHAN GANDA (40 soal)

**1.** Pilar Computational Thinking yang memecah masalah besar menjadi bagian kecil disebut…
A. Abstraction  B. Decomposition  C. Pattern Recognition  D. Algorithm Design

**2.** Ciri algoritma "harus berakhir setelah sejumlah langkah" adalah…
A. Finiteness  B. Definiteness  C. Effectiveness  D. Input

**3.** Algoritma "Masak sampai enak" melanggar ciri…
A. Finiteness  B. Output  C. Definiteness  D. Effectiveness

**4.** Simbol **diamond (◇)** pada flowchart berarti…
A. Proses  B. Input/Output  C. Terminal  D. Keputusan

**5.** Simbol **oval** pada flowchart berarti…
A. Mulai/Selesai  B. Proses  C. Keputusan  D. Input/Output

**6.** Perbedaan algoritma dan program adalah…
A. Keduanya sama saja
B. Program = konsep, algoritma = kode
C. Algoritma = konsep/logika, program = implementasi
D. Algoritma hanya untuk matematika

**7.** Hasil `7 / 2` (keduanya `int`) adalah…
A. 3.5  B. 3  C. 4  D. 2

**8.** Hasil `(double) 7 / 2` adalah…
A. 3  B. 3.0  C. 2  D. 3.5

**9.** Hasil `17 MOD 5` adalah…
A. 2  B. 3  C. 3.4  D. 0

**10.** Tipe data untuk satu karakter `'A'` adalah…
A. `int`  B. `string`  C. `char`  D. `bool`

**11.** Setelah `DEKLARASI umur : integer` **tanpa inisialisasi**, isi awalnya adalah…
A. 0  B. sampah (garbage)  C. null  D. −1

**12.** Untuk menukar nilai dua variabel dengan benar dibutuhkan…
A. dua assignment  B. operator `==`  C. loop  D. variabel bantu (`temp`)

**13.** Perhatikan: `a ← 5; b ← a + 3; c ← a * b; a ← c - b`. Nilai akhir `a` adalah…
A. 32  B. 8  C. 40  D. 5

**14.** Ukuran tipe `int` pada umumnya adalah…
A. 1 byte  B. 2 byte  C. 4 byte  D. 8 byte

**15.** Hasil `5 + 3 * 2` adalah…
A. 16  B. 11  C. 13  D. 30

**16.** Hasil `8 + 4 * 3 - 6 / 2` adalah…
A. 21  B. 20  C. 24  D. 17

**17.** Hasil `10 % 3 + 7 * (2 + 1)` adalah…
A. 22  B. 21  C. 13  D. 31

**18.** Operator dengan prioritas **tertinggi** adalah…
A. `*`  B. `+`  C. `( )`  D. `=`

**19.** Menurut De Morgan, `!(A && B)` setara dengan…
A. `!A && !B`  B. `!A || !B`  C. `A || B`  D. `A && B`

**20.** Hasil `15 MOD 4` adalah…
A. 3.75  B. 4  C. 0  D. 3

**21.** `a += 5` sama dengan…
A. `a = a + 5`  B. `a = 5`  C. `a = a - 5`  D. `a = a * 5`

**22.** Ekspresi relasional `5 > 3` menghasilkan nilai bertipe…
A. `integer`  B. `string`  C. `boolean`  D. `char`

**23.** Rantai IF-ELSE IF berhenti mengecek pada…
A. kondisi terakhir  B. kondisi **TRUE pertama**  C. semua kondisi  D. blok ELSE

**24.** Menggunakan dua **IF terpisah** (bukan ELSE IF) menyebabkan…
A. error  B. hanya IF pertama dicek  C. ELSE otomatis dibuat  D. semua kondisi dicek

**25.** Pada **nested IF**, jika kondisi luar FALSE maka…
A. kondisi dalam tidak dicek  B. kondisi dalam tetap dicek  C. error  D. ELSE dalam dijalankan

**26.** SWITCH-CASE hanya cocok untuk kondisi…
A. rentang nilai  B. lebih dari satu variabel  C. nilai diskrit (`==`)  D. `float`

**27.** IF-ELSE IF **tanpa blok ELSE** di akhir, nilai di luar semua kondisi akan…
A. diisi 0  B. tidak terdefinisi (undefined)  C. error kompilasi  D. diisi kondisi terakhir

**28.** Simbol keputusan (diamond) pada flowchart memiliki berapa cabang…
A. 1  B. 3  C. 4  D. 2

**29.** Loop **WHILE** (pre-check) bisa berjalan sebanyak…
A. 0 kali  B. minimal 1 kali  C. selalu 1 kali  D. tak hingga

**30.** Loop **DO-WHILE** pasti berjalan minimal…
A. 0 kali  B. 2 kali  C. 1 kali  D. tak tentu

**31.** Loop **FOR** paling cocok dipakai saat…
A. jumlah iterasi belum diketahui  B. jumlah iterasi sudah diketahui  C. butuh input validasi  D. kondisi kompleks

**32.** Pola **counting** dalam loop ditulis sebagai…
A. `total ← total + nilai`  B. `i ← i * 2`  C. `total ← 0`  D. `counter ← counter + 1`

**33.** Variabel counter/akumulator harus diinisialisasi…
A. sebelum loop  B. di dalam loop  C. setelah loop  D. tidak perlu

**34.** Loop WHILE **tanpa update counter** akan menyebabkan…
A. error  B. loop berhenti  C. infinite loop  D. output 0

**35.** `UNTUK i ← 1 SAMPAI 9: total ← total + i` lalu `rata ← total / 10` menghasilkan…
A. 5.5  B. 4.5  C. 45  D. 5

**36.** Total eksekusi **inner loop** pada nested loop adalah…
A. outer + inner  B. outer − inner  C. inner saja  D. outer × inner

**37.** Inner loop `j ← 1 SAMPAI i` menghasilkan pola…
A. segitiga  B. kotak  C. garis  D. piramida

**38.** Inner loop `j ← 1 SAMPAI N` (tetap) menghasilkan pola…
A. segitiga  B. piramida  C. kotak  D. diamond

**39.** Pada kompleksitas **O(n²)**, jika N naik 2× maka waktu naik…
A. 2×  B. 4×  C. 8×  D. tetap

**40.** Banyak bintang pada baris ke-`i` sebuah piramida adalah…
A. `i`  B. `2i`  C. `N - i`  D. `2i - 1`

---

# 🔑 KUNCI JAWABAN — PILIHAN GANDA

| No | Jwb | No | Jwb | No | Jwb | No | Jwb |
|---|---|---|---|---|---|---|---|
| 1 | B | 11 | B | 21 | A | 31 | B |
| 2 | A | 12 | D | 22 | C | 32 | D |
| 3 | C | 13 | A | 23 | B | 33 | A |
| 4 | D | 14 | C | 24 | D | 34 | C |
| 5 | A | 15 | B | 25 | A | 35 | B |
| 6 | C | 16 | D | 26 | C | 36 | D |
| 7 | B | 17 | A | 27 | B | 37 | A |
| 8 | D | 18 | C | 28 | D | 38 | C |
| 9 | A | 19 | B | 29 | A | 39 | B |
| 10 | C | 20 | D | 30 | C | 40 | D |

**Distribusi jawaban:** A = 10 · B = 10 · C = 10 · D = 10 (seimbang — tidak ada pola yang bisa ditebak).

---

# 📝 PEMBAHASAN — PILIHAN GANDA

**1. B** — Decomposition memecah masalah besar → bagian kecil.

**2. A** — Finiteness = harus berakhir.

**3. C** — "Sampai enak" ambigu → melanggar Definiteness.

**4. D** — Diamond = keputusan (percabangan), selalu 2 cabang.

**5. A** — Oval = terminal (Mulai/Selesai).

**6. C** — Algoritma = konsep/logika; program = implementasi dalam bahasa pemrograman.

**7. B** — Dua `int` → integer division, `7/2 = 3` (desimal dibuang).

**8. D** — Cast ke `double` dulu → `3.5`.

**9. A** — `17 % 5 = 2` (17 = 5×3 + 2).

**10. C** — Satu karakter → `char`.

**11. B** — Deklarasi tanpa inisialisasi → isi = sampah (garbage).

**12. D** — Swap butuh variabel bantu `temp`, jika tidak nilai lama hilang.

**13. A** — `b=8, c=40, a=40-8=` **32**.

**14. C** — `int` umumnya 4 byte.

**15. B** — `3*2=6`, `5+6=11`.

**16. D** — `4*3=12`, `6/2=3`, `8+12-3=17`.

**17. A** — `(2+1)=3`, `10%3=1`, `7*3=21`, `1+21=22`.

**18. C** — Kurung `( )` prioritas tertinggi.

**19. B** — De Morgan: `!(A&&B) ≡ !A || !B`.

**20. D** — `15 % 4 = 3` (15 = 4×3 + 3).

**21. A** — `a += 5` sama dengan `a = a + 5`.

**22. C** — Ekspresi relasional menghasilkan `boolean` (true/false).

**23. B** — ELSE IF berhenti di TRUE pertama.

**24. D** — Dua IF terpisah → **semua** kondisi dicek (bisa saling menimpa).

**25. A** — Kondisi luar FALSE → kondisi dalam **tidak dicek**.

**26. C** — Switch hanya untuk nilai diskrit/pasti (`==`), satu variabel.

**27. B** — Tanpa ELSE → nilai di luar semua kondisi **undefined**.

**28. D** — Diamond selalu 2 cabang (TRUE/FALSE).

**29. A** — WHILE cek dulu → bisa 0 kali.

**30. C** — DO-WHILE eksekusi dulu → minimal 1 kali.

**31. B** — FOR cocok saat jumlah iterasi sudah diketahui.

**32. D** — Counting: `counter ← counter + 1`.

**33. A** — Inisialisasi **sebelum** loop (jika tidak → garbage).

**34. C** — Tanpa update counter → syarat tak pernah berubah → **infinite loop**.

**35. B** — `total = 45` (1..9), `45/10 = 4.5` → **off-by-one**.

**36. D** — Total inner = outer × inner.

**37. A** — `j ← 1..i` → segitiga (tiap baris beda panjang).

**38. C** — `j ← 1..N` → kotak.

**39. B** — O(n²): N naik 2× → waktu naik **4×**.

**40. D** — Bintang baris ke-`i` piramida = `2i - 1`.

---

# ✅ KUNCI & RUBRIK — ESAI

## Esai 1 (P1) — 10 poin
(a) 4 pilar **(4)**: Decomposition (pecah masalah besar), Pattern Recognition (cari pola/kesamaan), Abstraction (fokus hal penting, abaikan detail), Algorithm Design (susun langkah sistematis).
(b) 5 ciri **(3)**: Finiteness, Definiteness, Input, Output, Effectiveness.
(c) **(2)** Melanggar **Finiteness** — `i` terus bertambah dan selalu `> 0`, kondisi `SELAMA i > 0` tak pernah FALSE → loop tak berhenti. Fix: `SELAMA i ≤ 100`.
(d) 3 representasi **(1)**: bahasa natural, pseudocode, flowchart.

## Esai 2 (P2) — 10 poin
(a) **(3)** Deklarasi = membuat variabel (`DEKLARASI umur : integer`); inisialisasi = deklarasi + isi awal (`umur : integer ← 20`); assignment = mengubah nilai (`umur ← 21`).
(b) Trace **(4)**:
| Step | Statement | a | b | c |
|---|---|---|---|---|
| 1 | a ← 9 | 9 | — | — |
| 2 | b ← a / 2 | 9 | 4 | — |
| 3 | c ← a MOD 2 | 9 | 4 | 1 |
| 4 | a ← b * c + a | **13** | 4 | 1 |
OUTPUT: `a=13, b=4, c=1`
(c) **(2)** `7 / 2` keduanya `int` → dihitung bulat dulu (= 3), baru disimpan ke `double` → `3.0`. Fix: `z ← (double) 7 / 2` atau `z ← 7 / 2.0`.
(d) **(1)** `a ← b` menimpa nilai lama `a`; lalu `b ← a` menyalin nilai `b` yang baru → kedua variabel sama. Fix: pakai `temp`: `temp ← a; a ← b; b ← temp`.

## Esai 3 (P3) — 10 poin
(a) **(3)** `4*3=12` → `6/2=3` → `8+12=20` → `20-3=` **17**.
(b) **(3)** `(2+1)=3` → `10%3=1` → `7*3=21` → `1+21=` **22**.
(c) Truth table **(2)**:
| A | B | A && B | !(A && B) | !A | !B | !A \|\| !B | ≡? |
|---|---|---|---|---|---|---|---|
| T | T | T | F | F | F | F | ✅ |
| T | F | F | T | F | T | T | ✅ |
| F | T | F | T | T | F | T | ✅ |
| F | F | F | T | T | T | T | ✅ |
Kolom `!(A&&B)` dan `!A||!B` identik → terbukti setara.
(d) **(2)** `x=10` → `+5=15` → `×2=30` → `−3=` **27**.

## Esai 4 (P4) — 10 poin
(a) Decision tree **(3)**:
```
belanja ≥ 200rb?
 ├─ TRUE → member?
 │          ├─ TRUE  → 20%
 │          └─ FALSE → 5%
 └─ FALSE → member?
            ├─ TRUE  → 10%
            └─ FALSE → 0%
```
(b) Pseudocode **(4)**:
```
DEKLARASI member : boolean
DEKLARASI belanja : integer
READ member, belanja
JIKA belanja ≥ 200000 MAKA
    JIKA member = true MAKA
        diskon ← 20
    SELAINNYA
        diskon ← 5
    AKHIR JIKA
SELAINNYA
    JIKA member = true MAKA
        diskon ← 10
    SELAINNYA
        diskon ← 0
    AKHIR JIKA
AKHIR JIKA
OUTPUT diskon, "%"
```
(c) Trace **(2)**: member=true, belanja=250000 → `250000 ≥ 200000? TRUE` → `member=true? TRUE` → **diskon 20%**.
(d) **(1)** Tanpa ELSE, nilai di luar semua kondisi tidak terisi (undefined). Contoh: diskon tanpa `SELAINNYA` terakhir → non-member belanja kecil tidak punya nilai diskon.

## Esai 5 (P5+P6) — 10 poin
(a) Trace table **(4)**:
| i | nilai = 2i+1 | total | maks | nilai%3==0 | count |
|---|---|---|---|---|---|
| 1 | 3 | 3 | 3 | T | 1 |
| 2 | 5 | 8 | 5 | F | 1 |
| 3 | 7 | 15 | 7 | F | 1 |
| 4 | 9 | 24 | 9 | T | 2 |
| 5 | 11 | 35 | 11 | F | 2 |
| 6 | 13 | 48 | 13 | F | 2 |
| 7 | 15 | **63** | **15** | T | **3** |

OUTPUT: `Total = 63` / `Maks = 15` / `Kelipatan3 = 3`
(b) **(3)** Pseudocode:
```
N ← 4
UNTUK i ← 1 SAMPAI N
    UNTUK j ← 1 SAMPAI N - i
        WRITE " "
    AKHIR UNTUK
    UNTUK j ← 1 SAMPAI 2 * i - 1
        WRITE "*"
    AKHIR UNTUK
    WRITE newline
AKHIR UNTUK
```
Rumus: **spasi = N − i**, **bintang = 2i − 1**.
(c) **(3)** Total WRITE = 1+2+…+N = **N(N+1)/2** ≈ N²/2 → kompleksitas **O(n²)**.

---

## 🗺️ Peta Cakupan Soal

| Pertemuan | Esai | PG |
|---|---|---|
| P1 Computational Thinking | 1 | 1–6 |
| P2 Tipe Data & Ekspresi | 2 | 7–14 |
| P3 Operator & Precedence | 3 | 15–22 |
| P4 Percabangan | 4 | 23–28 |
| P5 Perulangan 1 | 5a | 29–35 |
| P6 Perulangan 2 & Pattern | 5b, 5c | 36–40 |

## 📊 Cara Menilai Diri
- **PG:** jumlah benar × 1,25 → skor maks **50**
- **Esai:** total poin (maks **50**)
- **Total: 100** · **≥ 75** = siap UTS ✅ · **< 60** = ulangi kisi-kisi di `alpro-materi-p1-8.md`

> **Pengingat UTS:** 120 menit · **tutup buku** · boleh **cheat sheet 1 halaman A4 tulisan tangan** (tidak boleh fotokopi) · tanpa HP/laptop/kalkulator · kerjakan soal mudah dulu · trace table dinilai **prosesnya**, bukan hanya hasil akhir.
