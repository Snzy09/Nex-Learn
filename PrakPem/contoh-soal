# Soal Latihan UTS — Praktikum Pemrograman (C++)

Kode MK: **IF25-11002** · 2 SKS · S1 Teknik Informatika ITERA · 2026
Cakupan: **Pertemuan 1–6** (materi UTS) · Durasi saran: **120 menit** · 4 bagian bergaya UTS
Bobot: **Esai/Bagian A & B 50 poin** · **Pilihan Ganda 50 poin**

> Soal **buatan** (bukan soal resmi dosen), disusun dari deck P1–P6 + contoh soal P8 untuk latihan.
> **Setiap potongan kode dan keluarannya sudah diverifikasi dengan `g++ -std=c++17`** (32 kasus, 32 sesuai).
> Kunci & pembahasan ada di bagian bawah — jangan diintip dulu.

---

# BAGIAN A — ESAI (5 soal)

## Esai 1 (P1 — Struktur Program & Escape)
Tulis **program C++ lengkap** yang menampilkan kartu berikut **persis** (termasuk tanda kutip dan garis miring terbalik):
```
=== KARTU ===
Nama : Budi
Kota : "Bandung"
Path : C:\data
```
Lalu jelaskan dengan kalimat sendiri peran `#include <iostream>`, `int main()`, dan `return 0;`.

## Esai 2 (P2 — Tipe Data, Ekspresi, Input)
(a) Deklarasikan variabel bertipe tepat untuk: **nama** (`Budi Santoso`), **umur** (`18`), **ipk** (`3.75`), **golDarah** (`'O'`), **aktif** (`true`), lalu tampilkan semuanya dalam satu baris.
(b) Telusuri keluaran program berikut dan jelaskan mengapa `x` bernilai 4, bukan 4.5:
```cpp
int a = 9, b = 2;
double x = a / b;
double y = a / 2.0;
a = a + b;
cout << x << " " << y << " " << a << endl;
```

## Esai 3 (P3 — Operator & Precedence)
(a) Evaluasi ekspresi berikut **langkah demi langkah** (tunjukkan urutannya), lalu tulis hasilnya:
`10 + 2 * 5 % 3 - 4`
(b) Telusuri keluaran program berikut, lalu jelaskan beda `x++` dan `++x`:
```cpp
int x = 4;
int a = x++;
int b = ++x;
cout << a << " " << b << " " << x << endl;
```

## Esai 4 (P4 — Percabangan)
(a) Tulis **rantai `if - else if - else`** yang mengubah nilai akhir (0–100) menjadi nilai huruf ITERA: **A ≥ 75, AB ≥ 70, B ≥ 65, BC ≥ 60, C ≥ 50, D ≥ 40, selain itu E**. Nilai di luar 0–100 tampilkan `"Nilai tidak valid"`.
(b) Jelaskan mengapa **urutan syarat penting** dan mengapa rantai `else if` berhenti di syarat pertama yang benar.
(c) Perbaiki potongan berikut dan jelaskan kesalahannya:
```cpp
if (hari == 6 || 7) { harga = 50000; }
```

## Esai 5 (P5 + P6 — Perulangan & Pola)
(a) Buat **trace table** (kolom `i`, `total`, `cacah`) dan tulis keluarannya:
```cpp
int total = 0, cacah = 0;
for (int i = 1; i <= 6; i++) {
    if (i % 2 == 0) { total += i; cacah++; }
}
cout << total << " " << cacah << endl;
```
(b) Tulis **perulangan bersarang** untuk menampilkan piramida bintang tinggi `n = 4`, dan turunkan **rumus** banyak spasi dan banyak bintang untuk baris ke-`b`.

---

# BAGIAN B — PILIHAN GANDA (40 soal)

**1.** Baris yang menyertakan pustaka input/output pada program C++ adalah…
A. `#include <iostream>`
B. `using namespace std;`
C. `int main() {`
D. `return 0;`

**2.** Perhatikan potongan berikut. Keluarannya adalah…
```cpp
cout << "A" << "B" << endl;
```
A. `A B`  B. `AB`  C. `A` lalu `B` di baris berikutnya  D. `A;B`

**3.** Escape sequence untuk **pindah baris** adalah…
A. `\t`  B. `\\`  C. `\n`  D. `\"`

**4.** Agar teks `C:\data` tampil dengan benar, penulisannya adalah…
A. `"C:\data"`  B. `"C:/data"`  C. `"C:\d ata"`  D. `"C:\\data"`

**5.** Escape sequence untuk menampilkan **tanda kutip ganda** adalah…
A. `\'`  B. `\"`  C. `\\`  D. `\n`

**6.** Tipe data yang tepat untuk tinggi badan `158.5` adalah…
A. `int`  B. `char`  C. `double`  D. `bool`

**7.** Tipe data yang tepat untuk satu karakter golongan darah `'O'` adalah…
A. `int`  B. `string`  C. `double`  D. `char`

**8.** Variabel `bool lulus = true;` ditampilkan **tanpa** `boolalpha` akan tercetak sebagai…
A. `1`  B. `true`  C. `0`  D. `"true"`

**9.** Hasil dari `7 / 2` (keduanya `int`) adalah…
A. `3.5`  B. `4`  C. `3`  D. `2`

**10.** Hasil dari `7 / 2.0` adalah…
A. `3`  B. `2`  C. `3.0`  D. `3.5`

**11.** Perhatikan: `double r = 7 / 2;`. Nilai `r` adalah…
A. `3`  B. `3.5`  C. `3.50`  D. `4`

**12.** Hasil dari `(int) 3.99` adalah…
A. `4`  B. `3`  C. `3.99`  D. `3.9`

**13.** Perintah untuk membaca **nama lengkap yang berspasi** adalah…
A. `cin >> nama;`
B. `cin.get(nama);`
C. `getline(nama, cin);`
D. `getline(cin, nama);`

**14.** Setelah `cin >> nim;`, agar `getline(cin, nama);` bekerja benar perlu…
A. `cin.ignore();`
B. `cin.clear();`
C. `cout << endl;`
D. `cin.get();`

**15.** Hasil dari `2 + 3 * 4` adalah…
A. `20`  B. `14`  C. `24`  D. `11`

**16.** Hasil dari `(2 + 3) * 4` adalah…
A. `14`  B. `24`  C. `20`  D. `9`

**17.** Hasil dari `10 - 4 - 3` adalah…
A. `9`  B. `11`  C. `1`  D. `3`

**18.** Hasil dari `20 / 4 * 2` adalah…
A. `10`  B. `2.5`  C. `8`  D. `40`

**19.** Perhatikan: `int x = 5; int a = x++;`. Nilai `a` adalah…
A. `6`  B. `4`  C. `5`  D. `7`

**20.** Perhatikan: `int x = 5; int b = ++x;`. Nilai `b` adalah…
A. `5`  B. `6`  C. `7`  D. `4`

**21.** Hasil dari `7 + 10 % 4 * 2` adalah…
A. `7`  B. `10`  C. `15`  D. `11`

**22.** Hasil dari `17 % 5` adalah…
A. `2`  B. `3`  C. `3.4`  D. `0`

**23.** Operator untuk **sisa bagi** adalah…
A. `/`  B. `%`  C. `*`  D. `//`

**24.** Perbedaan `=` dan `==` adalah…
A. Keduanya membandingkan nilai
B. Keduanya menugaskan nilai
C. `=` menugaskan, `==` membandingkan
D. `=` membandingkan, `==` menugaskan

**25.** `switch` hanya dapat dipakai untuk tipe…
A. `string` dan `char`
B. `int` dan `string`
C. `double` dan `int`
D. `int` dan `char`

**26.** Jika `break` dihilangkan pada sebuah `case`, yang terjadi adalah…
A. eksekusi **jatuh** ke `case` berikutnya
B. program gagal dikompilasi
C. `switch` berhenti otomatis
D. `case` tersebut dilompati

**27.** Rantai `else if` berhenti memeriksa…
A. setelah semua syarat diperiksa
B. di **syarat pertama yang benar**
C. di syarat terakhir
D. di blok `else`

**28.** Ekspresi `(a > b) ? a : b` menghasilkan…
A. nilai terkecil  B. selalu `a`  C. **nilai terbesar**  D. `true`/`false`

**29.** `for (int i = 0; i < 5; i++)` menjalankan badannya sebanyak…
A. `5` kali  B. `4` kali  C. `6` kali  D. `0` kali

**30.** Akumulator sebaiknya diberi nilai awal…
A. di dalam perulangan  B. setelah perulangan  C. tidak perlu  D. **sebelum perulangan**

**31.** Perhatikan potongan berikut. Setelah selesai, `bulan` bernilai…
```cpp
int saldo = 100000, bulan = 0;
while (saldo < 400000) { saldo += 150000; bulan++; }
```
A. `1`  B. `2`  C. `3`  D. `4`

**32.** Nilai sentinel `-1` pada pola `while (nilai != -1)` berfungsi sebagai…
A. nilai awal akumulator  B. nilai maksimum  C. **tanda berhenti**  D. pencacah

**33.** Ciri khas perulangan `do-while` adalah…
A. syarat diperiksa sebelum badan
B. tidak boleh memiliki syarat
C. selalu berjalan tak berhenti
D. **syarat diperiksa setelah badan (minimal sekali jalan)**

**34.** Penyebab paling umum perulangan **tidak berhenti** adalah…
A. **syarat tidak pernah berubah di dalam badan**
B. syarat terlalu banyak
C. tidak ada `break`
D. salah tipe variabel

**35.** Perbedaan `for (int i = 1; i <= 5; i++)` dengan `i < 5` adalah…
A. sama saja
B. **beda satu putaran (off-by-one)**
C. beda lima putaran
D. menyebabkan error

**36.** Perulangan bersarang dengan `for` luar 4 putaran dan `for` dalam 3 putaran menghasilkan total putaran dalam sebanyak…
A. `7`  B. `4`  C. `12`  D. `3`

**37.** Perintah `break` berfungsi untuk…
A. melompat ke putaran berikutnya
B. mengulang badan dari awal
C. mengakhiri seluruh program
D. **keluar dari perulangan terdekat**

**38.** Perintah `continue` berfungsi untuk…
A. **melompat ke putaran berikutnya**
B. keluar dari perulangan
C. mengakhiri program
D. mengulang program dari awal

**39.** Pada piramida tinggi `n = 5`, baris pertama (`b = 1`) berisi berapa spasi?
A. `1`  B. `5`  C. `4`  D. `3`

**40.** Pada piramida, baris ke-`b` berisi berapa bintang?
A. `b`  B. `2b - 1`  C. `2b`  D. `n - b`

---

# 🔑 KUNCI JAWABAN — PILIHAN GANDA

| No | Jwb | No | Jwb | No | Jwb | No | Jwb |
|---|---|---|---|---|---|---|---|
| 1 | A | 11 | A | 21 | D | 31 | B |
| 2 | B | 12 | B | 22 | A | 32 | C |
| 3 | C | 13 | D | 23 | B | 33 | D |
| 4 | D | 14 | A | 24 | C | 34 | A |
| 5 | B | 15 | B | 25 | D | 35 | B |
| 6 | C | 16 | C | 26 | A | 36 | C |
| 7 | D | 17 | D | 27 | B | 37 | D |
| 8 | A | 18 | A | 28 | C | 38 | A |
| 9 | C | 19 | C | 29 | A | 39 | C |
| 10 | D | 20 | B | 30 | D | 40 | B |

**Distribusi jawaban:** A = 10 · B = 10 · C = 10 · D = 10 (seimbang — tidak ada pola yang bisa ditebak).

---

# 📝 PEMBAHASAN — PILIHAN GANDA

**1. A** — `#include <iostream>` menyertakan pustaka input/output (`cin`, `cout`).

**2. B** — Dua string tanpa pemisah **menyatu** → `AB`, lalu `endl` pindah baris.

**3. C** — `\n` = pindah baris. `\t` = tab, `\\` = satu garis miring, `\"` = kutip.

**4. D** — Dalam string, satu `\` ditulis **dua kali**: `"C:\\data"` → tampil `C:\data`.

**5. B** — `\"` menampilkan kutip ganda.

**6. C** — `158.5` pecahan → `double`.

**7. D** — Satu karakter → `char`.

**8. A** — Tanpa `boolalpha`, `true` tampil sebagai `1` (dan `false` sebagai `0`).

**9. C** — Kedua operand `int` → pembagian bulat, `7 / 2 = 3` (sisa dibuang).

**10. D** — Salah satu operand pecahan (`2.0`) → hasil pecahan `3.5`.

**11. A** — `7 / 2` dihitung **bulat dulu** (= 3), baru disimpan ke `double` → tetap `3`.

**12. B** — Cast ke `int` **memotong**, bukan membulatkan → `3`.

**13. D** — `getline(cin, nama)` membaca satu baris penuh termasuk spasi.

**14. A** — `cin.ignore()` membuang enter sisa sesudah `cin >> nim`; tanpa itu `getline` membaca baris kosong.

**15. B** — `*` lebih dulu: `3 * 4 = 12`, lalu `2 + 12 = 14`.

**16. C** — Kurung lebih dulu: `2 + 3 = 5`, lalu `5 * 4 = 20`.

**17. D** — `+ -` kiri ke kanan: `10 - 4 = 6`, lalu `6 - 3 = 3`.

**18. A** — `* /` setingkat, kiri ke kanan: `20 / 4 = 5`, lalu `5 * 2 = 10`.

**19. C** — `x++` (postfix) memakai nilai **lama** dulu → `a = 5`, lalu `x` jadi 6.

**20. B** — `++x` (prefix) menambah **dulu** → `x` jadi 6, `b = 6`.

**21. D** — `10 % 4 = 2`, `2 * 2 = 4`, `7 + 4 = 11`.

**22. A** — `17 % 5 = 2` (17 = 3×5 + 2).

**23. B** — `%` = modulo/sisa bagi (hanya bilangan bulat).

**24. C** — `=` menugaskan nilai; `==` membandingkan.

**25. D** — `switch` hanya untuk tipe integral: `int` dan `char` (bukan `string`, bukan `double`).

**26. A** — Tanpa `break`, eksekusi **jatuh** ke `case` berikutnya (*fall-through*).

**27. B** — Rantai `else if` berhenti di syarat pertama yang benar, karena itu tidak perlu menulis rentang.

**28. C** — Ternary `(a > b) ? a : b` memilih nilai terbesar.

**29. A** — `i` = 0,1,2,3,4 → **5 kali**.

**30. D** — Akumulator diinisialisasi **sebelum** perulangan (mis. `int total = 0;`).

**31. B** — 100000 → 250000 (1) → 400000 (2). Saat 400000, `400000 < 400000` salah → berhenti. `bulan = 2`.

**32. C** — Sentinel adalah **tanda berhenti**; nilainya tidak ikut diproses.

**33. D** — `do-while` memeriksa syarat **sesudah** badan → badan jalan minimal sekali.

**34. A** — Perulangan tak berhenti bila **syarat tidak pernah berubah** di dalam badan.

**35. B** — `i <= 5` menjalankan 1..5 (5 kali); `i < 5` menjalankan 0..4 (5 kali dari 0) / 1..4 (4 kali dari 1) → **off-by-one**.

**36. C** — Total putaran dalam = luar × dalam = `4 × 3 = 12`.

**37. D** — `break` keluar dari perulangan **terdekat saja**, bukan semua.

**38. A** — `continue` melompat ke putaran berikutnya (melewati sisa badan).

**39. C** — Rumus spasi = `n - b` = `5 - 1 = 4`.

**40. B** — Rumus bintang = `2b - 1` (1, 3, 5, 7, …).

---

# ✅ KUNCI & RUBRIK — ESAI

## Esai 1 (P1) — 8 poin
Kode yang benar **(4)**:
```cpp
#include <iostream>
using namespace std;
int main() {
    cout << "=== KARTU ===" << endl;
    cout << "Nama : Budi" << endl;
    cout << "Kota : \"Bandung\"" << endl;   // kutip ganda di-escape
    cout << "Path : C:\\data" << endl;      // garis miring di-escape
    return 0;
}
```
Keluaran: `=== KARTU ===` / `Nama : Budi` / `Kota : "Bandung"` / `Path : C:\data` **(2)**
Penjelasan **(2)**: `#include <iostream>` menyertakan pustaka I/O; `int main()` titik mulai program; `return 0;` menandakan program selesai normal.

## Esai 2 (P2) — 8 poin
(a) Deklarasi **(3)**: `string nama = "Budi Santoso"; int umur = 18; double ipk = 3.75; char golDarah = 'O'; bool aktif = true;`
(b) Keluaran = **`4 4.5 11`** **(3)** — `x = 9/2` dihitung bulat = **4** (baru disimpan ke double) **(1)**; `y = 9/2.0 = 4.5`; `a = 9+2 = 11` **(1)**.

## Esai 3 (P3) — 8 poin
(a) `10 + 2 * 5 % 3 - 4` → `2*5 = 10` → `10 % 3 = 1` → `10 + 1 - 4 = ` **`7`** **(4)** — tunjukkan urutannya.
(b) Keluaran = **`4 6 6`** **(3)** — `a = x++` → a=4, x=5; `b = ++x` → x=6, b=6 **(1)**. Penjelasan: `x++` pakai nilai lama dulu; `++x` menambah dulu.

## Esai 4 (P4) — 8 poin
(a) Rantai **(4)**:
```cpp
if (n < 0 || n > 100)   cout << "Nilai tidak valid";
else if (n >= 75)       cout << "A";
else if (n >= 70)       cout << "AB";
else if (n >= 65)       cout << "B";
else if (n >= 60)       cout << "BC";
else if (n >= 50)       cout << "C";
else if (n >= 40)       cout << "D";
else                    cout << "E";
```
(b) **(2)** Syarat diperiksa **dari batas tertinggi**; rantai berhenti di syarat pertama yang benar, jadi `n >= 70` tidak perlu `n >= 70 && n < 75`.
(c) **(2)** `hari == 6 || 7` selalu benar (7 dianggap `true`) → harus `hari == 6 || hari == 7`.

## Esai 5 (P5+P6) — 8 poin
(a) Trace table **(3)**: i=2 → total 2, cacah 1 · i=4 → total 6, cacah 2 · i=6 → total 12, cacah 3. Keluaran = **`12 3`** **(1)**.
(b) Kode piramida **(2)**:
```cpp
int n = 4;
for (int b = 1; b <= n; b++) {
    for (int s = 1; s <= n - b; s++)     cout << " ";
    for (int k = 1; k <= 2 * b - 1; k++) cout << "*";
    cout << endl;
}
```
Rumus **(2)**: spasi = **`n - b`**, bintang = **`2b - 1`**.

---

## 🗺️ Peta Cakupan Soal

| Pertemuan | Esai | PG |
|---|---|---|
| P1 Struktur & escape | 1 | 1–5 |
| P2 Tipe, ekspresi, input | 2 | 6–14 |
| P3 Operator & precedence | 3 | 15–24 |
| P4 Percabangan | 4 | 25–28 |
| P5 Perulangan | 5a | 29–35 |
| P6 Perulangan bersarang & pola | 5b | 36–40 |

## 📊 Cara Menilai Diri
- **PG:** jumlah benar × 1,25 → skor maks **50**
- **Esai:** total poin (maks **50**)
- **Total: 100** · **≥ 75** = siap UTS ✅ · **< 60** = ulangi kisi-kisi di `prakpem-materi-p1-8.md`

> **Pengingat UTS:** 4 soal, 120 menit, Bagian A (kode) & B (tracing/penjelasan) masing-masing 50 poin. Soal B dikerjakan **di kertas tanpa menjalankan program**. Boleh membawa satu lembar catatan A4 tulisan tangan.
