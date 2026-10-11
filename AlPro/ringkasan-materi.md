# Materi Algoritma Pemrograman — P1–P8 (Persiapan UTS)

Kode MK: **IF25-11001** · 2 SKS Teori · S1 Teknik Informatika ITERA · Gasal 2026/2027
Sumber: repo `informatika-itera/IF25-11001-Algoritma-Pemrograman` @ `main`, dibaca 2026-10-11.
Pasangan sinergi: **Praktikum Pemrograman (IF25-11002)** — konsep & pseudocode di sini, implementasi C++ di praktikum.

> Mata kuliah ini **berbasis pseudocode & flowchart**, bukan kode C++. UTS = **tutup buku + cheat sheet 1 halaman A4 tulisan tangan**.
> Semua trace table & hasil di dokumen ini sudah **diverifikasi dengan simulasi** (skrip Python, 60+ kasus).

---

## Peta 16 Pertemuan

| P | Topik | Fase |
|:---:|---|---|
| 1 | Computational Thinking | Pondasi |
| 2 | Tipe Data, Variabel dan Ekspresi | Pondasi |
| 3 | Operator dan Precedence | Pondasi |
| 4 | Percabangan (Selection) | Kontrol Alur |
| 5 | Perulangan Bagian 1 | Kontrol Alur |
| 6 | Perulangan Bagian 2 dan Pattern | Kontrol Alur |
| 7 | Review Intensif dan Simulasi UTS | UTS |
| **8** | **UTS** | UTS |
| 9–10 | Array 1D · Array 2D & String | Struktur Data |
| 11–12 | Searching · Sorting | Algoritma Klasik |
| 13–14 | Fungsi & Modularitas · Rekursi & Struct | Abstraksi |
| 15–16 | Review & Simulasi UAS · UAS | UAS |

## Penilaian (per CPMK maks 50, total 100)

| Komponen | Bobot |
|---|---|
| UTS (P8) | 25% |
| UAS (P16) | 25% |
| Tugas Individual | 15% |
| Exit Ticket | 15% |
| PBL#1 Smart Calculator (P3–P6) | 6% |
| PBL#2 Data Analyzer (P9–P12) | 7% |
| PBL#3 Student Record (P13–P15) | 7% |

> **Kelulusan:** nilai minimum per CPMK = **50**. Gagal salah satu → **remedial**.

---

# PERTEMUAN 1 — Computational Thinking

**Inti:** berpikir sistematis sebelum menulis kode; apa itu algoritma; 3 cara merepresentasikannya.

## Definisi & 4 Pilar
**Computational Thinking (CT)** = cara berpikir sistematis memecahkan masalah **kompleks** dengan memecahnya menjadi langkah-langkah jelas yang bisa dieksekusi **manusia maupun komputer**. CT bukan hanya untuk programmer (dipakai dokter, chef, insinyur).

| # | Pilar | Arti | Contoh |
|---|---|---|---|
| 1 | **Decomposition** | Memecah masalah besar → bagian kecil | Aplikasi e-commerce → login, katalog, keranjang, bayar |
| 2 | **Pattern Recognition** | Mencari kesamaan/pola | Semua "telusuri array" punya pola loop sama |
| 3 | **Abstraction** | Fokus hal penting, abaikan detail | Pakai `hitungRata()` tanpa tahu isinya |
| 4 | **Algorithm Design** | Menyusun langkah solusi sistematis | Langkah 1, 2, 3, … |

## Algoritma dan 5 Ciri Wajib
**Algoritma** = urutan **langkah logis dan terbatas** untuk menyelesaikan masalah.

| Ciri | Arti |
|---|---|
| **Finiteness** | Harus **berakhir** setelah sejumlah langkah; tidak boleh jalan selamanya |
| **Definiteness** | Setiap langkah **jelas, tidak ambigu** |
| **Input** | Punya **0 atau lebih** input |
| **Output** | Punya **1 atau lebih** output |
| **Effectiveness** | Setiap langkah sederhana & bisa dieksekusi dalam waktu terbatas |

> **Algoritma ≠ Program.** Algoritma = konsep/logika (bahasa netral). Program = implementasi dalam bahasa pemrograman (C++, Python).

**Jebakan "Algorithm Detective":**
- Loop tanpa henti (`SELAMA i > 0` dengan `i ← i + 1`) → melanggar **Finiteness**.
- "Masak sampai enak" → melanggar **Definiteness** (ambigu).

## 3 Representasi Algoritma
Contoh sama: *cari terbesar dari 2 angka*

**1) Bahasa natural**
> Baca dua angka a dan b. Jika a lebih besar dari b, maka a terbesar. Jika tidak, b terbesar.

**2) Pseudocode**
```
DEKLARASI a, b : integer
READ a, b
JIKA a > b MAKA
    OUTPUT a
SELAINNYA
    OUTPUT b
AKHIR JIKA
```

**3) Flowchart** → MULAI → READ a,b → ◇ a > b? → Ya: OUTPUT a / Tidak: OUTPUT b → SELESAI

## Konvensi Kelas (WAJIB HAFAL)
| Keyword Pseudocode | Arti |
|---|---|
| `DEKLARASI var : tipe` | Deklarasi variabel |
| `READ var` | Baca input |
| `OUTPUT var` / `WRITE` | Tampilkan hasil |
| `←` | Assignment |
| `JIKA...MAKA...AKHIR JIKA` | Percabangan |
| `SELAINNYA` | Cabang alternatif (else) |
| `UNTUK...SAMPAI...AKHIR UNTUK` | Perulangan terbatas (for) |
| `SELAMA...AKHIR SELAMA` | Perulangan bersyarat (while) |
| `LAKUKAN...SELAMA` | do-while |
| `FUNGSI...AKHIR FUNGSI` / `RETURN` | Definisi & nilai balik fungsi |

| Simbol Flowchart | Bentuk | Arti |
|---|---|---|
| Terminal | ⬭ Oval | Mulai / Selesai |
| Proses | ▭ Persegi panjang | Aksi / komputasi |
| Keputusan | ◇ Diamond | Percabangan (JIKA) — **selalu 2 cabang** |
| Input/Output | ▱ Jajar genjang | Baca / tampilkan |
| Panah | → | Arah alur |

## Contoh 1: Tahun Kabisat
Aturan: habis dibagi 4 **DAN** tidak habis dibagi 100, **KECUALI** habis dibagi 400.
```
DEKLARASI tahun : integer
DEKLARASI kabisat : boolean
READ tahun
JIKA (tahun MOD 4 == 0 DAN tahun MOD 100 != 0)
     ATAU (tahun MOD 400 == 0) MAKA
    kabisat ← true
SELAINNYA
    kabisat ← false
AKHIR JIKA
OUTPUT kabisat
```
Cek: 2024 → (0==0 dan 24≠0) → **kabisat** · 1900 → (0==0 tapi 100%100=0, 1900%400≠0) → **bukan** · 2000 → 2000%400==0 → **kabisat**.

## Contoh 2: Terbesar dari 3 Angka
```
DEKLARASI a, b, c, maks : integer
READ a, b, c
maks ← a
JIKA b > maks MAKA
    maks ← b
AKHIR JIKA
JIKA c > maks MAKA
    maks ← c
AKHIR JIKA
OUTPUT maks
```
Trace a=7, b=15, c=3: maks←7 → b=15>7? YA → maks←15 → c=3>15? TIDAK → **OUTPUT 15**.
> Pola ini **sama** dengan cari maksimum di array (P9)!

---

# PERTEMUAN 2 — Tipe Data, Variabel dan Ekspresi

**Inti:** bagaimana data disimpan di memori, trace table, dan jebakan type casting.

## Variabel = Kotak di Memori
Variabel punya **nama**, **tipe**, **alamat** (hex), dan **nilai**. Tipe menentukan **ukuran** kotak.

| Alamat | Nama | Tipe | Nilai | Ukuran |
|---|---|---|---|---|
| 0x1000 | umur | int | 20 | 4 byte |
| 0x1004 | tinggi | float | 170.5 | 4 byte |
| 0x1008 | grade | char | 'A' | 1 byte |
| 0x1009 | lulus | bool | true | 1 byte |

> Komputer hanya mengenal **alamat**, bukan nama variabel. Nama = alias untuk manusia.

## 6 Tipe Data Fundamental
| Tipe | Ukuran | Jangkauan | Contoh |
|---|---|---|---|
| `int` | 4 byte | ±2,1 miliar | 42, -7, 0 |
| `float` | 4 byte | ±3,4×10³⁸ (presisi ~7 digit) | 3.14, -0.5 |
| `double` | 8 byte | ±1,7×10³⁰⁸ (presisi ~15 digit) | 3.14159265 |
| `char` | 1 byte | 0–255 (ASCII) | 'A', 'z', '9' |
| `string` | bervariasi | tergantung panjang | "Budi", "ITERA" |
| `bool` | 1 byte | true / false | true, false |

## Deklarasi vs Inisialisasi vs Assignment
| Konsep | Pseudocode | C++ | Efek memori |
|---|---|---|---|
| **Deklarasi** | `DEKLARASI umur : integer` | `int umur;` | Kotak dibuat, isi = sampah (garbage) |
| **Inisialisasi** | `DEKLARASI umur : integer ← 20` | `int umur = 20;` | Kotak dibuat + diisi 20 |
| **Assignment** | `umur ← 21` | `umur = 21;` | Nilai lama ditimpa |

## Trace Table: Senjata Utama
Tabel mencatat **nilai setiap variabel setelah setiap baris** dieksekusi. Kolom = variabel, baris = langkah.

```
1  DEKLARASI a, b, c : integer
2  a ← 5
3  b ← a + 3
4  c ← a * b
5  a ← c - b
```
| Step | Statement | a | b | c |
|---|---|---|---|---|
| 1 | a ← 5 | 5 | — | — |
| 2 | b ← a + 3 | 5 | 8 | — |
| 3 | c ← a * b | 5 | 8 | 40 |
| 4 | a ← c - b | **32** | 8 | 40 |

> Perhatikan: `a` berubah 5 → **32** di step 4. Assignment **menimpa** nilai lama.

## Pola SWAP (wajib paham)
```
x ← 10
y ← 25
temp ← x        // simpan x dulu
x ← y           // x ditimpa jadi 25
y ← temp        // y diisi 10
OUTPUT x, y     // 25 10
```
> **Tanpa `temp`, nilai x HILANG** saat ditimpa oleh y → `a ← b; b ← a` menghasilkan a=20, b=20 (salah).

## Trace Lanjutan: Precedence & Integer Division
```
1  p ← 12
2  q ← p / 4        // 12/4 = 3
3  r ← p MOD 5      // 12%5 = 2
4  p ← p + q * r    // 12 + (3*2) = 18   ← KALI DULU!
5  q ← r - q + p    // 2 - 3 + 18 = 17   ← kiri ke kanan
OUTPUT p, q, r      // 18 17 2
```
> Kesalahan tersering: menulis `(12+3)×2 = 30`, padahal `12+(3×2) = 18`.

## Type Casting (Jebakan Utama!)
**Implicit (otomatis)** — tipe "kecil" → "besar" (aman):
```
int a = 5;  double b = a;   // b = 5.0
```
**Integer division** — dua `int` dibagi → **desimal dibuang**:
```
int x = 7; int y = 2;
double z = x / y;    // z = 3.0  ← BUKAN 3.5!
```
**Explicit (manual)** — programmer memaksa (bisa kehilangan data):
```
double pi = 3.14;  int x = (int) pi;       // x = 3 (.14 hilang)
double z = (double) 7 / 2;                  // z = 3.5  ← cast DULU, baru bagi
```

**Detective Bug Klasik:**
- `rata ← jumlah / n` dengan jumlah & n `int` → `253/3 = 84` (bukan 84.33). **Fix:** `rata ← (double)jumlah / n`.
- Swap tanpa `temp` → nilai hilang. **Fix:** pakai `temp`.

## Aliran Data & Penamaan
```
INPUT (READ/cin) → PROSES (assignment, ekspresi) → OUTPUT (WRITE/cout)
```
| Aturan Nama Variabel | ✅ Benar | ❌ Salah |
|---|---|---|
| Diawali huruf/underscore | `umur`, `_count` | `1angka`, `3x` |
| Hanya huruf, angka, underscore | `total_nilai` | `total-nilai`, `harga!` |
| Case-sensitive | `Nama ≠ nama ≠ NAMA` | (3 variabel berbeda) |
| Bukan reserved word | `myInt`, `returnValue` | `int`, `return`, `for` |
| Bermakna | `jumlahMahasiswa` | `x`, `temp99` |

---

# PERTEMUAN 3 — Operator dan Precedence

**Inti:** 4 kategori operator, urutan evaluasi, precedence tree, truth table.

## 4 Kategori Operator
| Kategori | Operator | Hasil | Contoh |
|---|---|---|---|
| **Aritmatika** | `+ - * / %` | angka | `7/2=3` · `7%3=1` · `7.0/2=3.5` |
| **Relasional** | `== != < > <= >=` | boolean | `5>3 → true` · `5==5.0 → true` |
| **Logika** | `&& \|\| !` | boolean | `T&&F → F` · `T\|\|F → T` · `!T → F` |
| **Assignment** | `= += -= *= /= %=` | — | `a += 5` sama dengan `a = a + 5` |

> ⚠ **`=` (assignment) vs `==` (perbandingan)** — kesalahan paling sering!

## Tabel Precedence (Tinggi → Rendah)
| Prioritas | Kategori | Operator | Arah |
|:---:|---|---|---|
| 1 (tertinggi) | Tanda kurung | `( )` | Dalam → Luar |
| 2 | Unary / NOT | `! ++ -- (cast)` | Kanan → Kiri |
| 3 | Multiplikatif | `* / %` | Kiri → Kanan |
| 4 | Aditif | `+ -` | Kiri → Kanan |
| 5 | Relasional | `< > <= >=` | Kiri → Kanan |
| 6 | Kesamaan | `== !=` | Kiri → Kanan |
| 7 | AND logika | `&&` | Kiri → Kanan |
| 8 | OR logika | `\|\|` | Kiri → Kanan |
| 9 (terendah) | Assignment | `= += -= *=` | Kanan → Kiri |

## Precedence Tree
Cara menggambar: operator **prioritas terendah** jadi **root**; operand kiri/kanan jadi subtree; evaluasi dari **daun ke akar** (bottom-up).

Contoh `5 + 3 * 2 - 1`: root `-`, kiri `5 + 3*2`, kanan `1`.
① `3*2 = 6` → ② `5+6 = 11` → ③ `11-1 = 10`.

## Evaluasi Step-by-Step (jawaban workshop)
**Soal 1:** `8 + 4 * 3 - 6 / 2`
→ `4*3=12` → `6/2=3` → `8+12=20` → `20-3=` **17**

**Soal 2:** `10 % 3 + 7 * (2 + 1)`
→ `(2+1)=3` → `10%3=1` → `7*3=21` → `1+21=` **22**

**Soal 3:** `(a>5) && (b<10) || !(c==0)` dengan a=3, b=7, c=0
→ `(3>5)=F` → `(7<10)=T` → `(0==0)=T` → `!T=F` → `F && T=F` → `F || F=` **false**
> Urutan: `()` → `!` → relasional → `&&` → `||`

## Truth Table & De Morgan
| A | B | A && B | A \|\| B | !A |
|---|---|---|---|---|
| T | T | T | T | F |
| T | F | F | T | F |
| F | T | F | T | T |
| F | F | F | F | T |

> `&&` hanya TRUE jika **keduanya** true · `||` hanya FALSE jika **keduanya** false.

**De Morgan's Law:**
```
!(A && B) ≡ !A || !B
!(A || B) ≡ !A && !B
```
Bukti lewat truth table: kolom `!(A&&B)` dan `!A||!B` **identik di semua baris**.

**Short-circuit:** `&&` berhenti jika kiri FALSE; `||` berhenti jika kiri TRUE.

## Detective Bug
- `15 - 3 * 4 + 8 / 2` → benar `15 - (3*4) + (8/2) = 15-12+4 =` **7** (bukan 72 — mahasiswa menambah kurung yang tak ada).
- `b ← a + 5 * 2 - 3` dengan a=10 → `10 + (5*2) - 3 =` **17** (bukan 27).
- **Aturan emas:** jangan menebak — evaluasi step-by-step; jika ragu, **tambah kurung**.

---

# PERTEMUAN 4 — Percabangan (Selection)

**Inti:** memilih jalur eksekusi — IF, IF-ELSE, IF-ELSE IF, nested IF, switch-case.

## 3 Jenis Percabangan
**IF (satu arah)** — aksi hanya jika kondisi TRUE:
```
JIKA kondisi MAKA
    aksi
AKHIR JIKA
```
**IF-ELSE (dua arah)** — selalu 2 jalur:
```
JIKA kondisi MAKA
    aksi_1
SELAINNYA
    aksi_2
AKHIR JIKA
```
**IF-ELSE IF-ELSE (multi arah)** — dicek berurutan, **TRUE pertama** dieksekusi:
```
JIKA kondisi_1 MAKA
    aksi_1
SELAINNYA JIKA kondisi_2
    aksi_2
SELAINNYA
    aksi_default
AKHIR JIKA
```

## Decision Tree
Node = kondisi, cabang = TRUE/FALSE, leaf = hasil akhir. Dibaca dari **root (atas)** ke bawah, kiri=TRUE, kanan=FALSE.

Contoh kategori BMI:
```
bmi < 18.5 → Underweight
bmi < 25   → Normal
bmi < 30   → Overweight
else       → Obese
```
Trace berat=70, tinggi=1.75 → bmi=22.86 → `22.86<18.5? F` → `22.86<25? T` → **"Normal"** (sisa tidak dicek).

> **Urutan kondisi penting** — TRUE pertama menang, sisanya dilewat. Cek dari kecil ke besar **atau** besar ke kecil, pilih salah satu.

## Nested IF
```
JIKA kondisi_luar MAKA
    JIKA kondisi_dalam MAKA
        aksi_A
    SELAINNYA
        aksi_B
    AKHIR JIKA
SELAINNYA
    aksi_C
AKHIR JIKA
```
Contoh beasiswa: IPK ≥ 3.5 → (penghasilan < 5jt → FULL / else → PARSIAL) / else → tidak memenuhi.

**Trace `umur` & `punya_SIM`:**
| umur | punya_SIM | Output |
|---|---|---|
| 20 | true | "Boleh mengemudi" |
| 18 | false | "Buat SIM dulu" |
| 15 | true | "Belum cukup umur" |
| 17 | false | "Buat SIM dulu" |

> Kasus umur=15, SIM=true → pengecekan SIM **tidak pernah terjadi** karena kondisi luar (umur≥17) sudah FALSE.

## SWITCH-CASE
```
PILIH (hari)
    KASUS 1: WRITE "Senin"
    KASUS 2: WRITE "Selasa"
    ...
    LAINNYA: WRITE "Weekend"
AKHIR PILIH
```
| | IF-ELSE IF | SWITCH-CASE |
|---|---|---|
| Kondisi | Bebas (range, >, <) | Hanya `==` (exact) |
| Variabel | Bisa beda-beda | Satu variabel |
| Kapan | Rentang/kompleks | Nilai diskrit/pasti |

> **Jangan pakai switch** untuk: kondisi rentang (`≥ 60`), lebih dari satu variabel, atau tipe `float`/`double`.

## 3 Aturan Emas Percabangan
1. Gunakan **ELSE IF** untuk kondisi saling eksklusif — **jangan IF terpisah**.
2. **SELALU** tambahkan blok **ELSE** di akhir — tangani semua kemungkinan.
3. **Trace nilai boundary** (batas): tepat di batas, di bawah, di atas.

**Detective Bug:**
- Dua `IF` terpisah → `total=150000`: IF1 TRUE (diskon 20%), tapi IF2 **juga** dicek → diskon **ditimpa** jadi 10%. Fix: `SELAINNYA JIKA`.
- Tanpa `ELSE` di akhir → `umur=65` semua kondisi FALSE → kategori **undefined**. Fix: tambah `SELAINNYA`.

---

# PERTEMUAN 5 — Perulangan Bagian 1

**Inti:** WHILE, FOR, DO-WHILE; counting & accumulation; 3 bug klasik.

## 3 Jenis Perulangan
| Jenis | Cek kondisi | Minimal iterasi | Kapan dipakai |
|---|---|---|---|
| **WHILE** | **Sebelum** aksi | bisa **0×** | Jumlah iterasi belum diketahui |
| **FOR** | Counter otomatis | pasti (start→end) | Jumlah iterasi **sudah diketahui** |
| **DO-WHILE** | **Setelah** aksi | pasti **≥1×** | Input validasi, menu |

```
SELAMA kondisi              UNTUK i ← 1 SAMPAI 5        LAKUKAN
    aksi                        aksi                        aksi
    update counter          AKHIR UNTUK                     update counter
AKHIR SELAMA                                            SELAMA kondisi
```
> **WHILE** = pre-check (cek dulu) · **DO-WHILE** = post-check (eksekusi dulu).
> ⚠ WHILE harus punya **update counter** di dalam badan, jika tidak → **infinite loop**.

## Trace FOR
`UNTUK i ← 1 SAMPAI 5: OUTPUT i`
| Iterasi | i | i ≤ 5? | Output |
|---|---|---|---|
| 1 | 1 | TRUE | 1 |
| 2 | 2 | TRUE | 2 |
| 3 | 3 | TRUE | 3 |
| 4 | 4 | TRUE | 4 |
| 5 | 5 | TRUE | 5 |
| 6 | 6 | FALSE | keluar loop |

Output `1 2 3 4 5`, total 5 iterasi. Loop berhenti saat `i=6`.

## Pola Counting & Accumulation
**Counting** (menghitung berapa kali):
```
counter ← 0                        // WAJIB inisialisasi SEBELUM loop
UNTUK i ← 1 SAMPAI 10
    JIKA i MOD 2 == 0 MAKA
        counter ← counter + 1
    AKHIR JIKA
AKHIR UNTUK
OUTPUT counter                     // 5
```
**Accumulation** (mengumpulkan total):
```
total ← 0
UNTUK i ← 1 SAMPAI 10
    total ← total + i
AKHIR UNTUK
rata ← total / 10                  // 55 / 10 = 5.5
OUTPUT total, rata                 // 55 5.5
```
> Pola: `counter ← counter + 1` dan `total ← total + nilai`. **Selalu inisialisasi = 0 sebelum loop.**

## Workshop (jawaban)
**Jumlah kuadrat 1..5:**
```
total ← 0; i ← 1
SELAMA i ≤ 5
    total ← total + i * i
    i ← i + 1
AKHIR SELAMA
```
| i | i² | total |
|---|---|---|
| 1 | 1 | 1 |
| 2 | 4 | 5 |
| 3 | 9 | 14 |
| 4 | 16 | 30 |
| 5 | 25 | **55** |

Rumus: Σi² = N(N+1)(2N+1)/6.

**Hitung genap/ganjil 1..8:** genap=4 (2,4,6,8), ganjil=4 (1,3,5,7). Jika 1..9 → genap=4, ganjil=**5**.

## 3 Bug Klasik Loop
| Bug | Contoh | Fix |
|---|---|---|
| **Wrong direction** | `i ← i + 1` pada countdown `SELAMA i > 0` → infinite | `i ← i - 1` |
| **Off-by-one** | `UNTUK i←1 SAMPAI 9` lalu `rata ← total/10` → 45/10=4.5 | ubah `SAMPAI 10` |
| **Missing initialization** | `counter` tidak diisi 0 → garbage | `counter ← 0` sebelum loop |

> **3 hal WAJIB dicek:** (1) inisialisasi counter/total, (2) arah update (+/−), (3) batas loop (`≤` atau `<`).

---

# PERTEMUAN 6 — Perulangan Bagian 2 dan Pattern

**Inti:** nested loop, pola bintang, kompleksitas O(n) vs O(n²).

## Nested Loop
Outer loop = **baris**, inner loop = **kolom**.
```
UNTUK i ← 1 SAMPAI 3
    UNTUK j ← 1 SAMPAI 4
        WRITE "*"
    AKHIR UNTUK
    WRITE newline
AKHIR UNTUK
```
**Aturan penting:**
1. Setiap **1 putaran outer**, inner berputar **penuh**.
2. Total eksekusi inner = **outer_count × inner_count** (3×4 = 12).
3. Variabel outer (`i`) **tetap** selama inner (`j`) berputar.
4. Inner bisa **bergantung** outer: `UNTUK j ← 1 SAMPAI i` → pola segitiga.

## Trace Nested Loop (inner bergantung)
```
UNTUK i ← 1 SAMPAI 3
    UNTUK j ← 1 SAMPAI i
        WRITE j
    AKHIR UNTUK
    WRITE newline
AKHIR UNTUK
```
| i | j range | Output baris |
|---|---|---|
| 1 | 1..1 | `1` |
| 2 | 1..2 | `12` |
| 3 | 1..3 | `123` |

> `j ← 1 s/d i` → **segitiga** (tiap baris beda panjang). `j ← 1 s/d N` → **kotak**.

## 4 Pattern Fundamental
| Pola | Tampilan | Rumus |
|---|---|---|
| **Segitiga kiri** | `*` / `**` / `***` / `****` | `j ← 1 s/d i` |
| **Segitiga kanan** | `   *` / `  **` / ` ***` / `****` | spasi `N-i` + bintang `i` |
| **Segitiga terbalik** | `****` / `***` / `**` / `*` | `j ← 1 s/d (N-i+1)` |
| **Piramida** | `   *` / `  ***` / ` *****` / `*******` | spasi `N-i` + bintang `2i-1` |

```
// Piramida
UNTUK i ← 1 SAMPAI N
    UNTUK j ← 1 SAMPAI N-i
        WRITE " "
    AKHIR UNTUK
    UNTUK j ← 1 SAMPAI 2*i-1
        WRITE "*"
    AKHIR UNTUK
    WRITE newline
AKHIR UNTUK
```

**Trik efisien (1 inner loop + kondisi):**
```
UNTUK j ← 1 SAMPAI N
    JIKA j ≤ N-i MAKA WRITE " " SELAINNYA WRITE "#" AKHIR JIKA
AKHIR UNTUK
```
→ N=5 menghasilkan segitiga kanan `    # /   ## /  ### / #### / #####`.

## Kompleksitas Dasar
| Kasus | Pseudocode | Jumlah operasi | Kompleksitas |
|---|---|---|---|
| Single loop | `FOR i←1 TO N: WRITE "*"` | N | **O(n)** |
| Nested (kotak) | `FOR i←1 TO N: FOR j←1 TO N` | N² | **O(n²)** |
| Segitiga | `FOR i←1 TO N: FOR j←1 TO i` | N(N+1)/2 ≈ N²/2 | **O(n²)** |
| 2 loop berurutan | `FOR i←1 TO N` lalu `FOR j←1 TO N` | 2N | **O(n)** |

> **O(n):** N naik 2× → waktu naik 2×. **O(n²):** N naik 2× → waktu naik **4×**.
> N=1000: O(n) = 1.000 operasi, O(n²) = **1.000.000** operasi (1000× lebih lambat).

## 4 Bug Nested Loop
1. **Missing increment** → infinite loop (khusus WHILE; FOR otomatis aman).
2. **WRITE variabel salah** → `i` dan `j` tertukar.
3. **Inner range tetap vs bergantung** → kotak vs segitiga.
4. **newline di tempat salah** → semua output 1 baris.

---

# PERTEMUAN 7 — Review Intensif dan Simulasi UTS

## Peta Materi P1–P6
| P | Topik | Kunci |
|---|---|---|
| 1 | Computational Thinking | Flowchart, pseudocode, decomposition, abstraction |
| 2 | Tipe Data & Variabel | Memory model, trace table, type casting, naming |
| 3 | Operator & Precedence | 4 kategori, truth table, De Morgan |
| 4 | Percabangan | IF/ELSE, decision tree, nested IF, switch |
| 5 | Perulangan 1 | While/for/do-while, counting, accumulation |
| 6 | Perulangan 2 | Nested loop, pattern, O(n) vs O(n²) |

## GOTCHA yang PASTI Keluar
| Gotcha | Contoh |
|---|---|
| **Integer division** | `7 / 2 = 3` (bukan 3.5); `(double)7/2 = 3.5` |
| **Modulo** | `17 % 5 = 2` (17 = 5×3 + 2) |
| **De Morgan** | `!(A&&B) = !A\|\|!B` |
| **Assignment vs equality** | `x = 5` vs `x == 5`; di pseudocode `←` vs `==` |
| **IF vs ELSE IF** | IF terpisah = **semua** dicek; ELSE IF = berhenti di TRUE pertama |

## Rumus Cepat Pattern
| Pola | Rumus |
|---|---|
| Segitiga kiri | `j ← 1 s/d i` |
| Segitiga terbalik | `j ← 1 s/d (N-i+1)` |
| Segitiga kanan | spasi `(N-i)` + bintang `i` |
| Piramida | spasi `(N-i)` + bintang `(2i-1)` |
| Kotak N×M | `j ← 1 s/d M` (tetap) |

## Latihan Bertingkat (jawaban)
**E1:** `a←15; b←15/4=3; c←15%4=3; a←3*3+1=10` → **OUTPUT a=10, b=3, c=3**
**E2:** nilai=85→"A" · nilai=60→"B" (60≥80?F → 60≥60?T) · nilai=45→"C"
**M1:** (85,90)→"Lulus" · (75,60)→"Mengulang (absen)" · (50,95)→"Tidak Lulus"
**M2:** `total=0`; i=1 odd→−1; i=2 even→+2→1; i=3 odd→−3→−2; i=4 even→+4→2; i=5 odd→−5→**−3**
**H1 (N=4):** kotak berongga
```
****
*  *
*  *
****
```
Total `*` = 4+2+2+4 = **12** · total `" "` = **4** · kompleksitas **O(n²)** → N=100 = 10.000 operasi.

## Simulasi UTS Mini (jawaban)
**Soal 1:** `x←20; y←20%7=6; z←20/7=2; x←6*2-20/4=12-5=7` → `7>0` → **OUTPUT 7 positif**
**Soal 2:** member=Gold, beli=600000 → Gold & ≥500rb → **diskon 30%**
**Soal 3:** `sum` skip kelipatan 3: 1+2+4+5 = **12**
**Soal 4:** `UNTUK i←5 TURUN 1: UNTUK j←1 s/d i: WRITE i`
```
55555
4444
333
22
1
```
Total WRITE = 5+4+3+2+1 = **15**, kompleksitas **O(n²)**
**Soal 5:** pola `5 4 3 2 1 / 4 3 2 1 / 3 2 1 / 2 1 / 1`
```
UNTUK i ← 1 SAMPAI 5
    UNTUK j ← 5 TURUN i
        WRITE j
    AKHIR UNTUK
    WRITE newline
AKHIR UNTUK
```

## Tips & Strategi UTS
1. **Baca semua soal dulu** (2 menit), kerjakan yang mudah dulu.
2. **Trace table wajib rapi** — dosen menilai **proses**, bukan hanya jawaban akhir.
3. **Hati-hati integer division** — jebakan paling sering.
4. **Flowchart lengkap** — START, END, panah, diamond punya 2 cabang.
5. **Nested loop: tulis tabel i × j** — jangan trace di kepala.
6. **Cek boundary** — i=1, i=N, j=1, j=N.

---

# PERTEMUAN 8 — UTS (Format & Kisi-kisi)

**120 menit · tutup buku + cheat sheet 1 lembar A4 tulisan tangan · tanpa HP/laptop/kalkulator**

| Bagian | Materi | Bobot |
|---|---|---|
| A | Trace Table (2 soal) | 30% |
| B | Percabangan — decision tree + pseudocode + trace (2 soal) | 30% |
| C | Perulangan & Pattern (1–2 soal) | 25% |
| D | Desain Algoritma komprehensif (1 soal) | 15% |

## Distribusi Contoh UTS Resmi (P8)
| Soal | Materi | Tingkat | Waktu | Bobot |
|:---:|---|---|:---:|:---:|
| 1 | Tipe Data (trace table) | Mudah | 16' | 15% |
| 2 | Percabangan (bioskop) | Mudah–Sedang | 22' | 20% |
| 3 | Perulangan (accumulation) | Sedang | 24' | 20% |
| 4 | Nested Loop & Pattern | Sedang–Sulit | 29' | 25% |
| 5 | Desain Algoritma (ongkir) | Sulit | 29' | 20% |

## Kisi-kisi
| Topik | P | Indikator |
|---|---|---|
| Flowchart & pseudocode | 1 | simbol benar, konvensi kelas |
| Tipe data & trace table | 2 | assignment, integer division, MOD, precedence |
| Operator & logika | 3 | precedence, truth table, De Morgan |
| Percabangan | 4 | decision tree, nested IF, switch, boundary |
| Perulangan | 5 | while/for/do-while, counting, accumulation |
| Nested loop & kompleksitas | 6 | trace outer×inner, pattern, O(n) vs O(n²) |

---

# KISI-KISI CEPAT: Yang Paling Sering Keluar

## 🔴 Prioritas tinggi
1. **Integer division** — `7/2=3`; `(double)7/2=3.5`; `15/4=3`; `20/7=2`
2. **MOD / sisa bagi** — `17%5=2`; `15%4=3`; `20%7=6`
3. **Precedence** — `5+3*2=11`; `8+4*3-6/2=17`; `10%3+7*(2+1)=22`
4. **Assignment vs equality** — `←` vs `==`
5. **IF terpisah vs ELSE IF** — semua dicek vs berhenti di TRUE pertama
6. **Nested IF** — kondisi luar FALSE → kondisi dalam tak dicek
7. **Trace table** — tulis setiap step, jangan hanya hasil
8. **Counting & accumulation** — inisialisasi 0 sebelum loop
9. **Off-by-one** — `SAMPAI 9` lalu dibagi 10
10. **Nested loop total** = outer × inner
11. **Pattern** — `j←1..i` segitiga; spasi `N-i`, bintang `2i-1` piramida
12. **Kompleksitas** — single O(n), nested O(n²)
13. **Swap butuh temp**
14. **Boundary** — cek tepat di batas, bawah, atas

## 🟡 Tabel nilai cepat
| Ekspresi | Nilai |
|---|---|
| `7 / 2` (int) | 3 |
| `(double) 7 / 2` | 3.5 |
| `17 % 5` | 2 |
| `15 % 4` | 3 |
| `20 / 7` | 2 |
| `5 + 3 * 2` | 11 |
| `8 + 4 * 3 - 6 / 2` | 17 |
| `10 % 3 + 7 * (2 + 1)` | 22 |
| `(5+3)*2 - (10%3) + 1` | 15 |
| `12 + 6/3 - 2*4` | 6 |

## 🟢 Hafalan cepat
- **4 pilar CT:** Decomposition → Pattern Recognition → Abstraction → Algorithm Design
- **5 ciri algoritma:** Finiteness, Definiteness, Input, Output, Effectiveness
- **3 representasi:** bahasa natural, pseudocode, flowchart
- **Precedence:** `()` → `!` → `* / %` → `+ -` → relasional → `== !=` → `&&` → `||` → `=`
- **WHILE** cek dulu (bisa 0×) · **DO-WHILE** eksekusi dulu (min 1×) · **FOR** counter
- **De Morgan:** `!(A&&B) ≡ !A||!B` · `!(A||B) ≡ !A&&!B`
- **O(n)** linear · **O(n²)** kuadratik (N naik 2× → waktu naik 4×)

## ⚠️ Catatan
- UTS = **tutup buku**, hanya **cheat sheet 1 halaman A4 tulisan tangan** (tidak boleh fotokopi).
- Soal resmi tidak dipublikasikan; contoh UTS P8 setara tingkat kesulitannya.
- Mata kuliah ini **pseudocode**, bukan C++ — jangan menulis sintaks C++ kecuali diminta.
