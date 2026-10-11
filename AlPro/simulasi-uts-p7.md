# Simulasi UTS P7 — Pembahasan Soal 1–5

Kode MK: **IF25-11001** · Algoritma Pemrograman · 2 SKS Teori · ITERA
Sumber soal: deck **P7 — Review Intensif dan Simulasi UTS** (halaman 14–15)
5 soal × 20 poin = **100 poin** · saran waktu 25 menit

> Mata kuliah ini berbasis **pseudocode & flowchart** (bukan C++).
> Asumsi **integer division**: `20 / 7 = 2`, `20 / 4 = 5`, `7 / 2 = 3`.
> Semua trace & perhitungan sudah diverifikasi dengan simulasi program.

---

## SOAL 1 — Trace Table + Output + Flowchart (20 pts)

```
DEKLARASI x, y, z : integer
x ← 20
y ← x MOD 7
z ← x / 7
x ← y * z - x / 4
JIKA x > 0 MAKA
    OUTPUT x, " positif"
SELAINNYA
    OUTPUT x, " non-positif"
AKHIR JIKA
```

### (a) Trace Table lengkap — 8 pts

| Step | Statement | x | y | z | Keterangan |
|---|---|---|---|---|---|
| 1 | `x ← 20` | **20** | — | — | inisialisasi |
| 2 | `y ← x MOD 7` | 20 | **6** | — | 20 = 7×2 + **6** (sisa bagi) |
| 3 | `z ← x / 7` | 20 | 6 | **2** | integer division: 20/7 = 2 (bukan 2,857) |
| 4 | `x ← y * z - x / 4` | **7** | 6 | 2 | `6*2 − 20/4 = 12 − 5 = 7` |
| 5 | `x > 0 ?` | 7 | 6 | 2 | **7 > 0 → TRUE** |
| 6 | `OUTPUT x, " positif"` | 7 | 6 | 2 | jalankan blok TRUE |

> ⚠️ **Jebakan:** pada step 4, `x` di ruas kanan **masih bernilai 20** (belum ditimpa).
> Precedence: `*` dan `/` dikerjakan dulu, baru `-`.

### (b) Output program — 6 pts
```
7 positif
```

### (c) Flowchart — 6 pts
```
        ⬭ START
          │
      ▭ x ← 20
          │
      ▭ y ← x MOD 7
          │
      ▭ z ← x / 7
          │
      ▭ x ← y * z - x / 4
          │
       ◇ x > 0 ?
      ┌───┴───┐
   TRUE     FALSE
      │        │
 ▱ OUTPUT x,   ▱ OUTPUT x,
   " positif"   " non-positif"
      │        │
      └───┬────┘
          │
        ⬭ END
```

Checklist flowchart: ada **START & END** (oval), **proses** (kotak), **diamond dengan 2 cabang TRUE/FALSE**, dan **I/O** (parallelogram).

---

## SOAL 2 — Decision Tree + Pseudocode (20 pts)

**Aturan diskon:**
- Member Gold + beli ≥ 500rb → **30%**
- Member Gold + beli < 500rb → **15%**
- Member Silver → **10%**
- Non-member → **0%**

### (a) Decision Tree lengkap — 8 pts
```
                 status = Gold ?
                ┌───────┴───────┐
              TRUE            FALSE
                │                │
        beli ≥ 500rb ?      status = Silver ?
       ┌────┴────┐          ┌────┴────┐
     TRUE      FALSE      TRUE      FALSE
       │          │          │          │
      30%        15%        10%         0%
```

### (b) Pseudocode IF-ELSE IF — 6 pts
```
DEKLARASI status : string
DEKLARASI beli, diskon : integer
READ status, beli

JIKA status == "Gold" DAN beli >= 500000 MAKA
    diskon ← 30
SELAINNYA JIKA status == "Gold" MAKA
    diskon ← 15
SELAINNYA JIKA status == "Silver" MAKA
    diskon ← 10
SELAINNYA
    diskon ← 0
AKHIR JIKA

OUTPUT "Diskon =", diskon, "%"
```

> Alternatif **nested IF** juga sah. Yang penting urutan kondisi dari yang **paling spesifik** ke umum.

### (c) Trace: `member = Gold, beli = 600000` — 6 pts

| Cek | Kondisi | Hasil |
|---|---|---|
| 1 | `status=="Gold" DAN 600000 >= 500000` | **TRUE** ✅ |
| → | `diskon ← 30` | berhenti di TRUE pertama |
| | Blok ELSE IF berikutnya | **tidak dicek** |

**Output:** `Diskon = 30%`

> Karena pakai **ELSE IF**, begitu kondisi 1 TRUE, kondisi berikutnya **tidak dievaluasi** — beda dengan IF terpisah yang mengecek semua.

---

## SOAL 3 — Loop + Accumulation (20 pts)

```
sum ← 0
UNTUK i ← 1 SAMPAI 6
    JIKA i MOD 3 != 0
        sum ← sum + i
    AKHIR JIKA
AKHIR UNTUK
OUTPUT sum
```

### (a) Trace Table — 10 pts

| i | `i MOD 3` | `!= 0` ? | Aksi | sum |
|---|---|---|---|---|
| 1 | 1 | TRUE | `sum ← 0 + 1` | **1** |
| 2 | 2 | TRUE | `sum ← 1 + 2` | **3** |
| 3 | 0 | FALSE | *skip* | 3 |
| 4 | 1 | TRUE | `sum ← 3 + 4` | **7** |
| 5 | 2 | TRUE | `sum ← 7 + 5` | **12** |
| 6 | 0 | FALSE | *skip* | 12 |

### (b) Output — 5 pts
```
sum = 12
```

### (c) Pola skip — 5 pts
Algoritma **melewati bilangan yang habis dibagi 3** → kelipatan 3: **3 dan 6**.
Cek: (1+2+3+4+5+6) − (3+6) = 21 − 9 = **12** ✅

---

## SOAL 4 — Nested Loop Pattern (20 pts)

```
UNTUK i ← 5 TURUN 1
    UNTUK j ← 1 s/d i
        WRITE i
    AKHIR UNTUK
    WRITE newline
AKHIR UNTUK
```

### (a) Output — 8 pts
```
55555
4444
333
22
1
```

> ⚠️ Yang di-WRITE adalah **`i`** (bukan `j`), jadi tiap baris berisi **angka yang sama** sebanyak `i` kali.
> Kalau yang di-WRITE `j`, hasilnya berbeda (`54321 / 4321 / ...`).

### (b) Total WRITE — 6 pts
Jumlah = 5 + 4 + 3 + 2 + 1 = **15 kali**
Rumus: `N(N+1)/2 = 5×6/2 = 15`

### (c) Kompleksitas — 6 pts
**O(n²)** — nested loop dengan total operasi `N(N+1)/2 ≈ ½n²`.
Untuk **N = 100**: `100×101/2 = 5.050` operasi.

---

## SOAL 5 — Desain Algoritma (20 pts)

**Target pola:**
```
5 4 3 2 1
4 3 2 1
3 2 1
2 1
1
```

### (a) Pseudocode — 12 pts
```
DEKLARASI N, i, j : integer
N ← 5

UNTUK i ← N TURUN 1
    UNTUK j ← i TURUN 1
        WRITE j, " "
    AKHIR UNTUK
    WRITE newline
AKHIR UNTUK
```

> **Logika:** baris ke-`i` dimulai dari angka `i` lalu turun sampai 1.
> Karena `i` dari 5 turun ke 1: baris pertama `5 4 3 2 1`, baris terakhir `1`.

### (b) Trace baris 1–2 — 8 pts

| Baris | i | Nilai j (turun) | Output |
|---|---|---|---|
| 1 | **5** | 5 → 4 → 3 → 2 → 1 | `5 4 3 2 1` |
| 2 | **4** | 4 → 3 → 2 → 1 | `4 3 2 1` |
| 3 | 3 | 3 → 2 → 1 | `3 2 1` |
| 4 | 2 | 2 → 1 | `2 1` |
| 5 | 1 | 1 | `1` |

Total angka tercetak = 5+4+3+2+1 = **15** · kompleksitas **O(n²)**.

---

## 📋 Ringkasan Kunci

| Soal | Jawaban Inti |
|---|---|
| **1** | y=6, z=2, x=**7** → output `7 positif` |
| **2** | Decision tree 3 level · pseudocode IF-ELSE IF · Gold+600rb → **30%** |
| **3** | sum = **12** (skip kelipatan 3: 3 & 6) |
| **4** | `55555 / 4444 / 333 / 22 / 1` · total **15** WRITE · **O(n²)** (N=100 → 5.050) |
| **5** | Loop ganda `i` turun N..1, `j` turun i..1 · baris 1 `5 4 3 2 1`, baris 2 `4 3 2 1` |

> 🎯 **Skor total = 100.** Kalau bisa mengerjakan kelimanya tanpa lihat kunci, kamu sudah siap UTS.

---

## ⚠️ Gotcha yang Muncul di Kelima Soal

1. **Integer division** — `20/7 = 2`, `7/2 = 3` (bukan 2,857 / 3,5).
2. **Ruas kanan dihitung dulu** — `x ← y*z - x/4` memakai `x` lama (=20).
3. **Precedence** — `*` `/` `%` sebelum `+` `-`.
4. **ELSE IF berhenti di TRUE pertama** — kondisi berikutnya tak dicek.
5. **WRITE variabel mana** — Soal 4 mencetak `i`, bukan `j` (hasilnya beda!).
6. **Nested loop = O(n²)** — total operasi N(N+1)/2, bukan N.
7. **Trace table dinilai prosesnya** — tulis tiap langkah, jangan langsung hasil akhir.
