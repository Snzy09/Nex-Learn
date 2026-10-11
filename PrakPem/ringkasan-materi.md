# Materi Praktikum Pemrograman — P1–P8 (Persiapan UTS)

Kode MK: **IF25-11002** · 2 SKS praktikum · S1 Teknik Informatika ITERA · Semester 1 (Ganjil) 2026
Bahasa & alat: **C++17** · GDB Online (kelas) atau `g++` (komputer sendiri)
Sumber: repo `informatika-itera/IF25-11002-Praktikum-Pemrograman` @ `main`, dibaca 2026-10-11.
Pasangan: **Algoritma Pemrograman (IF25-11001)** — topik sama tiap minggu, beda peran.

> Semua keluaran contoh di dokumen ini sudah **diverifikasi dengan `g++ -std=c++17`** (42 potongan kode dikompilasi & dijalankan, 42 sesuai).

---

## Peta 16 Pertemuan

| P | Topik | Tugas |
|---|---|---|
| 1 | Hello World dan Struktur Program C++ | Tugas 1: Kartu Perkenalan Digital |
| 2 | Variabel, Tipe Data, Ekspresi, dan Input | Tugas 2: Pendaftaran Mahasiswa Baru |
| 3 | Operator dan Precedence | Tugas 3: Kalkulator Lengkap |
| 4 | Percabangan | Tugas 4: Sistem Tiket Bioskop |
| 5 | Perulangan Bagian 1 | Tugas 5: Program Statistik Nilai |
| 6 | Perulangan Bagian 2 dan Pola | Tugas 6: Pattern Generator |
| 7 | Review dan Simulasi UTS | — (simulasi) |
| **8** | **Ujian Tengah Semester** | — |
| 9–14 | Array 1D · Array 2D & String · Searching · Sorting · Fungsi · Rekursi & Struct | Tugas 9–14 |
| 15 | Review dan Simulasi UAS | — |
| 16 | UAS | — |

## Cara Penilaian

| Komponen | Pelaksanaan | Bobot |
|---|---|---|
| Exit Ticket | 14 kali (P1–P7, P9–P15) | 25% |
| Tugas | 12 kali (P1–P6, P9–P14) | 25% |
| UTS | P8, 4 soal, 120 menit | 25% |
| UAS | P16, 4 soal, 150 menit | 25% |

Setiap instrumen dibagi rata: **Bagian A** (menulis kode, CPMK0607 "menerapkan") dan **Bagian B** (tracing & penjelasan, CPMK0608 "menjelaskan"). Jadi tiap CPMK menyumbang tepat **50 poin**. Nilai minimum lulus tiap CPMK = **50**.

**Siklus tiap pertemuan (150 menit):** Review 15' → Struggle 25' → Materi 40' → Hands-on 45' → Exit Ticket 25'.

**Aturan AI:** boleh untuk memahami pesan error/konsep, **tidak** untuk minta solusi utuh. Exit Ticket, UTS, UAS tanpa AI.

---

# PERTEMUAN 1 — Hello World dan Struktur Program C++

**Inti:** program pertama, cara compiler membacanya, cara membaca pesan error.

## Struktur program C++
```cpp
#include <iostream>      // menyertakan pustaka input/output
using namespace std;     // memakai nama standar tanpa std::
int main() {             // titik mulai program
    cout << "Hello World!" << endl;
    return 0;            // menandakan program selesai normal
}
```

**Tahap dari kode ke program berjalan:**

| Tahap | Yang terjadi |
|---|---|
| 1. Kode sumber | Menulis instruksi C++ di file `.cpp` |
| 2. Kompilasi | Compiler (`g++`) memeriksa tata bahasa lalu menerjemahkan ke bahasa mesin |
| 3. Executable | Hasil terjemahan, siap dijalankan |
| 4. Jalankan | Program menampilkan keluaran di layar |

## cout, endl, dan `\n`
```cpp
cout << "Hai" << "Dunia";        // HaiDunia   (tanpa spasi, tanpa pindah baris)
cout << "Hai " << "Dunia" << endl; // Hai Dunia + pindah baris
cout << "Baris 1" << endl << "Baris 2\n";
cout << "Baris 3\nBaris 4" << endl;
```
Keluaran:
```
HaiDuniaHai Dunia
Baris 1
Baris 2
Baris 3
Baris 4
```
- `endl` = pindah baris **+** buang isi buffer; `\n` = pindah baris saja.
- Tanpa pemisah, dua string **menyatu** (`"Hai"` `"Dunia"` → `HaiDunia`).

## Escape sequence
| Ditulis | Tampil |
|---|---|
| `\n` | baris baru |
| `\t` | tab |
| `\\` | satu garis miring terbalik `\` |
| `\"` | kutip ganda `"` |

**Contoh jebakan:** `cout << "A" << "B" << endl;` → `AB` · `cout << "C\tD\n" << "E";` → `C   D` lalu `E` · `cout << "\"F\"" << endl;` → `"F"` — hasilnya `E"F"` menyatu di baris ketiga.

## Pesan error yang sering muncul (dari g++)
| Kesalahan | Contoh | Pesan pertama |
|---|---|---|
| Lupa titik koma | `cout << "Hai"` | `error: expected ';' before 'return'` |
| Salah ketik nama | `count << "Hai";` | `error: 'count' was not declared in this scope` |
| Lupa `#include` | tanpa baris 1 | `error: 'cout' was not declared in this scope` |
| Kutip tidak ditutup | `cout << "Hai;` | `error: missing terminating " character` |
| Garis miring tunggal | `"C:\data"` | `warning: unknown escape sequence: '\d'` |

## Contoh lengkap: kartu mahasiswa
```cpp
cout << "========================" << endl;
cout << "    KARTU MAHASISWA" << endl;
cout << "========================" << endl;
cout << "Nama  : Rani Puspita" << endl;
cout << "NIM   : 126140001" << endl;
cout << "Prodi : Teknik Informatika" << endl;
cout << "\tMotto: \"Belajar dari error\"" << endl;
cout << "========================" << endl;
```

**Tugas 1** — kartu perkenalan: header border, nama, NIM, asal kota, hobi (min 2), cita-cita, footer border, minimal satu `\t` dan satu `\"`.

---

# PERTEMUAN 2 — Variabel, Tipe Data, Ekspresi, dan Input

**Inti:** menyimpan data di memori, memilih tipe tepat, membaca masukan.

## Deklarasi dan tipe data dasar
```cpp
int umur = 18;
double ipk = 3.75;
char grade = 'A';
string nama = "Rani";      // perlu #include <string>
bool lulus = true;
cout << nama << " " << umur << " " << ipk << endl;  // Rani 18 3.75
cout << grade << " " << lulus << endl;              // A 1
```
`bool` tampil sebagai **1** (true) atau **0** (false) tanpa `boolalpha`.

| Tipe | Contoh | Dipakai untuk |
|---|---|---|
| `int` | `18`, `-5`, `36000` | bilangan bulat: umur, jumlah, harga rupiah |
| `double` | `3.75`, `36.6` | bilangan pecahan: IPK, suhu, berat |
| `char` | `'A'`, `'O'` | satu karakter: grade, golongan darah |
| `string` | `"Rani Puspita"` | teks: nama, alamat |
| `bool` | `true`, `false` | ya/tidak: lulus, aktif |

## Penugasan: nilai lama ditimpa
```cpp
int a = 5;
int b = a;      // b menyalin NILAI a saat itu (5)
a = a + 3;      // a = 8
b = b * 2;      // b = 10
cout << "a = " << a << ", b = " << b << endl;   // a = 8, b = 10
```
`b = a` menyalin nilai **saat itu**; mengubah `a` sesudahnya **tidak** mengubah `b`.

## Input dengan cin
```cpp
string barang; int harga, jumlah;
cin >> barang;
cin >> harga >> jumlah;
int total = harga * jumlah;
cout << barang << ": " << total << endl;
// masukan: Teh / 5000 2  ->  Teh: 10000
```

## getline: membaca teks berspasi
```cpp
string nama; int nim;
cin >> nim;
cin.ignore();            // buang enter sisa sesudah cin >> nim
getline(cin, nama);
cout << nama << " (" << nim << ")" << endl;
// masukan: 126140001 / Rani Puspita  ->  Rani Puspita (126140001)
```
**Tanpa `cin.ignore()`**, `getline` langsung membaca baris kosong.

## Pembagian bilangan bulat (jebakan utama!)
```cpp
int a = 7, b = 2;
cout << a / b << endl;          // 3     (bulat dibulatkan ke bawah)
cout << a / 2.0 << endl;        // 3.5   (salah satu operand pecahan)
cout << (double) a / b << endl; // 3.5   (cast)
double hasil = a / b;
cout << hasil << endl;          // 3     (dihitung bulat DULU, baru disimpan)
```
Kalau **kedua** operand bulat, hasilnya bulat dan sisanya dibuang — **bahkan bila disimpan ke `double`**.

## Mengatur angka di belakang koma
```cpp
double rata = 82.333333;
cout << rata << endl;                              // 82.3333
cout << fixed << setprecision(2) << rata << endl;  // 82.33
cout << 12.5 << endl;                              // 12.50  (setprecision tetap berlaku)
```
Perlu `#include <iomanip>`; pengaturan berlaku untuk **semua** `cout` sesudahnya.

## Latihan telusur
```cpp
int x = 10, y = 4;
double p = x / y;      // p = 2   (10/4 bulat!)
double q = x / 4.0;    // q = 2.5
x = x + y;             // x = 14
y = x - y;             // y = 10  (pakai x yang SUDAH berubah)
// keluaran: 2 2.5  lalu  14 10
```

## Pesan error sering
| Kesalahan | Pesan |
|---|---|
| Variabel belum dideklarasikan | `error: 'total' was not declared in this scope` |
| Tipe tidak cocok | `error: invalid conversion from 'const char*' to 'int'` |
| Arah `cin` terbalik | `error: no match for 'operator<<'` |
| Deklarasi dua kali | `error: redeclaration of 'int x'` |
| Variabel tidak dipakai | `warning: unused variable 'sisa'` |

**Tugas 2** — pendaftaran mahasiswa baru: nama (getline), tempat lahir, tgl lahir 3 int, asal sekolah, rata-rata double 2 desimal, kartu berborder.

---

# PERTEMUAN 3 — Operator dan Precedence

**Inti:** sisa bagi `%`, urutan operasi, penugasan majemuk, operator relasional & logika.

## Operator modulo `%`
```cpp
int total = 3725;
int jam   = total / 3600;          // 1
int menit = total % 3600 / 60;     // 2   (sisa 3600, lalu dibagi 60)
int detik = total % 60;            // 5
cout << jam << " " << menit << " " << detik << endl;   // 1 2 5
cout << 17 % 5 << " " << 20 % 4 << endl;               // 2 0
```
`%` **hanya untuk bilangan bulat**. `a % b == 0` berarti `a` habis dibagi `b`.

## Precedence (urutan pengerjaan)
| Tingkat | Operator | Arah | Contoh |
|---|---|---|---|
| 1 | `()` | dalam → luar | `(2+3)*4` = 20 |
| 2 | `++ -- !` dan cast | kanan → kiri | `!true` = false |
| 3 | `* / %` | kiri → kanan | `20/4*2` = 10 |
| 4 | `+ -` | kiri → kanan | `10-4-3` = 3 |
| 5 | `< <= > >=` lalu `== !=` | kiri → kanan | `3 < 5 == true` |
| 6 | `&&` lalu `\|\|` | kiri → kanan | `a \|\| b && c` |
| 7 | `= += -= *= /= %=` | kanan → kiri | `a = b = 0` |

> Ragu? Tambahkan kurung. Kurung tidak memperlambat program, tapi membuatnya mudah dibaca.

## Evaluasi ekspresi
```cpp
cout << 2 + 3 * 4 << endl;      // 14
cout << (2 + 3) * 4 << endl;    // 20
cout << 20 / 4 * 2 << endl;     // 10   (kiri ke kanan: 5 * 2)
cout << 10 - 4 - 3 << endl;     // 3    (kiri ke kanan: 6 - 3)
cout << 7 + 10 % 4 * 2 << endl; // 11   (10%4=2, 2*2=4, 7+4)
```

## Penugasan majemuk & increment
```cpp
int x = 5;
x += 3;      // 8
x *= 2;      // 16
x--;         // 15
int a = x++; // a = 15, x = 16   (x++ pakai nilai LAMA dulu)
int b = ++x; // b = 17, x = 17   (++x tambah DULU)
// keluaran: 15 17 17
```
- **`x++`** (postfix): pakai nilai lama, lalu tambah.
- **`++x`** (prefix): tambah dulu, lalu pakai nilai baru.

## Operator relasional & logika
```cpp
int nilai = 78, hadir = 12;
bool lulus = nilai >= 60;   // true
bool aktif = hadir >= 11;   // true
cout << boolalpha;
cout << lulus << " " << aktif << endl;            // true true
cout << (lulus && aktif) << endl;                 // true
cout << (nilai >= 85 || hadir == 14) << endl;     // false
cout << !lulus << endl;                           // false
```
**`==` membandingkan, `=` menugaskan.** Tanpa `boolalpha`, true/false tampil sebagai 1/0.

## Cast dan cmath
```cpp
double d = 3.99;
int i = (int) d;                                  // 3   (memotong, bukan membulatkan)
cout << (double) 7 / 2 << endl;                   // 3.5
cout << sqrt(16.0) << " " << pow(2, 10) << endl;  // 4 1024
cout << round(2.5) << " " << floor(2.7) << endl;  // 3 2
```
Perlu `#include <cmath>`. **Cast ke `int` memotong, tidak membulatkan.**

## Latihan telusur
```cpp
int a = 9, b = 4;
int c = a % b + a / b * 2;   // 1 + (9/4=2) * 2 = 5
a += c;                      // a = 14
b = a-- - b;                 // b = 14 - 4 = 10, lalu a turun jadi 13
// keluaran: 5 13 10   lalu   0   (c == 5, jadi c != 5 salah)
```

## Pesan error sering
| Kesalahan | Pesan |
|---|---|
| `%` pada pecahan | `error: invalid operands of types 'double' and 'int' to binary 'operator%'` |
| Ruas kiri bukan variabel | `error: lvalue required as left operand of assignment` |
| Pembagian nol | `warning: division by zero` |
| Perbandingan tanpa kurung di cout | `error: no match for 'operator>'` |
| `==` tidak dipakai | `warning: statement has no effect` |

**Tugas 3** — kalkulator: `+ - * /`, `%` dari bagian bulat (cast), cek pembagi nol dengan `?:`, dua nilai bool.

---

# PERTEMUAN 4 — Percabangan

**Inti:** program yang memilih jalan — `if`, `else if`, `switch`, ternary.

## if dan if-else
```cpp
int nilai;
cin >> nilai;
if (nilai >= 50) {
    cout << "LULUS" << endl;
} else {
    cout << "TIDAK LULUS" << endl;
}
cout << "Selesai" << endl;
// masukan 45 -> TIDAK LULUS / Selesai
```
Kondisi **selalu** di dalam kurung; kurung kurawal menandai blok.

## Rantai else if
```cpp
double n = 72.5;
if (n >= 75)      { cout << "A"; }
else if (n >= 70) { cout << "AB"; }   // <- berhenti di sini
else if (n >= 65) { cout << "B"; }
else              { cout << "di bawah B"; }
cout << endl;                          // AB
```
Pemeriksaan **berhenti di syarat pertama yang benar**. Karena itu `n >= 70` tidak perlu ditulis `n >= 70 && n < 75`.

## Syarat gabungan
```cpp
int umur = 17; bool punyaKTP = false;
if (umur >= 17 && punyaKTP)     { cout << "Boleh memilih" << endl; }
else if (umur >= 17)            { cout << "Urus KTP dulu" << endl; }
else                            { cout << "Belum cukup umur" << endl; }
// keluaran: Urus KTP dulu
```

## switch-case
```cpp
int pilihan = 2;
switch (pilihan) {
    case 1: cout << "Nasi goreng"; break;
    case 2: cout << "Mie ayam";    break;   // <- Mie ayam
    case 3: cout << "Soto";        break;
    default: cout << "Menu tidak ada";
}
cout << endl;
```
**Tanpa `break`**, eksekusi **jatuh** ke `case` berikutnya. `switch` hanya untuk **`int` dan `char`**, bukan `string` atau rentang nilai.

## Operator ternary
```cpp
int a = 8, b = 13;
int maks = (a > b) ? a : b;                          // 13
cout << "Maks: " << maks << endl;
cout << (b % 2 == 0 ? "genap" : "ganjil") << endl;   // ganjil
```
Pakai ternary hanya untuk pilihan sederhana; bila ragu, `if-else` lebih jelas.

## Data uji dan nilai batas
| Cabang | Data uji biasa | Nilai batas | Harapan |
|---|---|---|---|
| A | 92 | 75 dan 74.9 | 75 → A, 74.9 → AB |
| C | 55 | 50 dan 49.9 | 50 → C, 49.9 → D |
| E | 20 | 0 dan 39.9 | keduanya E |
| Tidak valid | 105 | 100.1 dan -0.1 | keduanya tidak valid |

Kesalahan percabangan paling sering terjadi **tepat di nilai batas** (`>` yang seharusnya `>=`).

## Latihan telusur (indentasi menipu)
```cpp
int x = 7;
if (x > 5)
    cout << "A";
    cout << "B";        // <- SELALU tampil walau indentasinya menipu!
if (x % 2 == 0) { cout << "C"; }
else if (x > 6) { cout << "D"; }
else            { cout << "E"; }
cout << endl;           // keluaran: ABD
```
Tanpa kurung kurawal, hanya `cout << "A"` milik `if` pertama.

## Pesan error sering
| Kesalahan | Pesan |
|---|---|
| `=` di dalam kondisi | `warning: suggest parentheses around assignment used as truth value` |
| `else` tanpa `if` | `error: 'else' without a previous 'if'` |
| `switch` pada string | `error: switch quantity not an integer` |
| `case` ganda | `error: duplicate case value` |
| Kondisi tanpa kurung | `error: expected '(' before 'x'` |

**Tugas 4** — tiket bioskop: switch film & hari, validasi umur (Horror 17+), harga 35000/45000/50000, diskon 20% (<12 & 60+), struk. Data uji batas: umur 11, 12, 16, 17, 59, 60.

---

# PERTEMUAN 5 — Perulangan Bagian 1

**Inti:** `for`, `while`, `do-while` dengan pola pencacah, akumulator, sentinel.

## for
```cpp
for (int i = 1; i <= 5; i++) { cout << i << " "; }
cout << endl;
for (int i = 10; i > 0; i -= 3) { cout << i << " "; }
cout << endl;
// 1 2 3 4 5
// 10 7 4 1
```
Tiga bagian `for`: **nilai awal; syarat lanjut; perubahan**. Syarat diperiksa **sebelum** setiap putaran.

## Pola pencacah & akumulator
```cpp
int jumlah = 0, genap = 0;
for (int i = 1; i <= 10; i++) {
    jumlah += i;              // akumulator
    if (i % 2 == 0) { genap++; }  // pencacah
}
cout << "Jumlah: " << jumlah << endl;  // 55
cout << "Genap : " << genap << endl;   // 5
```
Akumulator & pencacah **selalu diberi nilai awal sebelum** perulangan, bukan di dalamnya.

## while
```cpp
int saldo = 100000, bulan = 0;
while (saldo < 500000) {
    saldo += 150000;
    bulan++;
}
cout << bulan << " bulan, saldo " << saldo << endl;  // 3 bulan, saldo 550000
```
Sesuatu di dalam badan **harus mengubah syarat** — bila tidak, perulangan tak berhenti.

## Nilai sentinel
```cpp
int nilai, banyak = 0, total = 0;
cin >> nilai;                 // baca SEKALI sebelum perulangan
while (nilai != -1) {
    banyak++;
    total += nilai;
    cin >> nilai;             // baca lagi di akhir badan
}
cout << banyak << " data, total " << total << endl;
// masukan 70 85 60 90 -1 -> 4 data, total 305
```
Pola: baca sekali sebelum perulangan, baca lagi di akhir badan → `-1` **tidak ikut dihitung**.

## do-while (minimal sekali jalan)
```cpp
int pin, coba = 0;
do {
    cin >> pin;
    coba++;
} while (pin != 1234 && coba < 3);
cout << (pin == 1234 ? "Masuk" : "Terkunci");
cout << " setelah " << coba << " kali" << endl;
// masukan 1111 1234 -> Masuk setelah 2 kali
```
Syarat diperiksa **sesudah** badan. **Jangan lupa titik koma** setelah `while (...)`.

## Memilih jenis perulangan
| Situasi | Pilihan | Contoh |
|---|---|---|
| Banyak putaran diketahui | `for` | tampilkan 1 sampai n |
| Berhenti karena syarat, bisa nol putaran | `while` | baca sampai sentinel |
| Badan harus jalan minimal sekali | `do-while` | menu, validasi PIN |

## Latihan telusur
```cpp
int x = 0;
for (int i = 0; i < 4; i++) { x += i * 2; }  // 0+2+4+6 = 12
int k = 1;
while (k < 20) { k *= 3; }                    // 3, 9, 27
cout << x << " " << k << endl;                // 12 27
```

## Pesan error sering
| Kesalahan | Pesan |
|---|---|
| Koma di header for | `error: expected ';' before '<' token` |
| Variabel di luar jangkauan | `error: 'i' was not declared in this scope` |
| Lupa `;` sesudah do-while | `error: expected ';' before 'cout'` |
| Badan for kosong | `warning: this 'for' clause does not guard...` |

**Tugas 5** — statistik nilai: validasi n>0, validasi nilai 0–100, tertinggi/terendah/rata-rata, jumlah LULUS (≥75), menu do-while.

---

# PERTEMUAN 6 — Perulangan Bagian 2 dan Pola

**Inti:** perulangan bersarang, `break`/`continue`, menurunkan rumus pola.

## Perulangan bersarang (baris & kolom)
```cpp
for (char b = 'A'; b <= 'C'; b++) {
    for (int k = 1; k <= 4; k++) {
        cout << b << k << " ";
    }
    cout << endl;
}
// A1 A2 A3 A4
// B1 B2 B3 B4
// C1 C2 C3 C4
```
Untuk setiap **satu** putaran `for` luar, `for` dalam berjalan **penuh**. Total putaran dalam: **3 × 4 = 12**.

## Segitiga: batas dalam bergantung pada baris
```cpp
int n = 4;
for (int b = 1; b <= n; b++) {
    for (int k = 1; k <= b; k++) { cout << "*"; }
    cout << endl;
}
// *
// **
// ***
// ****
```
Batas `for` dalam memakai `b` — itulah yang membuat tiap baris beda panjang.

## Menurunkan rumus pola (piramida)
| Baris b | Spasi | Bintang | Tampilan |
|---|---|---|---|
| 1 | 3 | 1 | `*` |
| 2 | 2 | 3 | `***` |
| 3 | 1 | 5 | `*****` |
| 4 | 0 | 7 | `*******` |
| **Rumus** | **n − b** | **2b − 1** | |

```cpp
int n = 4;
for (int b = 1; b <= n; b++) {
    for (int s = 1; s <= n - b; s++)      { cout << " "; }
    for (int k = 1; k <= 2 * b - 1; k++)  { cout << "*"; }
    cout << endl;
}
```

## break dan continue
```cpp
for (int i = 1; i <= 10; i++) {
    if (i % 3 == 0) { continue; }   // lompat ke putaran berikutnya
    if (i > 7)      { break;    }   // keluar dari perulangan
    cout << i << " ";
}
cout << endl;   // 1 2 4 5 7
```
- **`continue`** → melompat ke putaran berikutnya.
- **`break`** → keluar dari perulangan **terdekat saja**, bukan semua perulangan.

## break untuk mencari
```cpp
int x = 91; bool prima = true;
for (int d = 2; d * d <= x; d++) {
    if (x % d == 0) { cout << "Habis dibagi " << d << endl; prima = false; break; }
}
cout << (prima ? "prima" : "bukan prima") << endl;
// Habis dibagi 7
// bukan prima
```

## Latihan telusur bersarang
```cpp
int hitung = 0;
for (int i = 1; i <= 3; i++) {
    for (int j = i; j <= 3; j++) { cout << i << j << " "; hitung++; }
}
cout << endl << hitung << endl;
// 11 12 13 22 23 33
// 6
```
`j` mulai dari `i` → baris luar ke-1 menghasilkan 3 pasangan, ke-2 dua, ke-3 satu. Total **6**.

## Pesan error sering
| Kesalahan | Pesan |
|---|---|
| Variabel luar dideklarasi ulang | `error: redeclaration of 'int i'` |
| `break` di luar perulangan | `error: break statement not within loop or switch` |
| `continue` di luar perulangan | `error: continue statement not within a loop` |
| Kurung kurawal kurang | `error: expected '}' at end of input` |

**Tugas 6** — Pattern Generator: menu 5 pola (segitiga kiri, segitiga kanan, piramida, berlian, persegi berongga), validasi n 1–20, menu berulang.

---

# PERTEMUAN 7 — Review dan Simulasi UTS

Merangkai materi P1–6 dan berlatih soal bergaya UTS.

## Peta materi UTS & jebakannya
| P | Konsep kunci | Jebakan yang sering muncul |
|---|---|---|
| 1 | struktur program, `cout`, escape | garis miring tunggal, lupa titik koma |
| 2 | tipe data, `cin`, `getline` | pembagian bulat, `getline` sesudah `cin` |
| 3 | `%`, precedence, `++`, logika | urutan operasi, `x++` vs `++x` |
| 4 | `if`, `else if`, `switch` | `=` vs `==`, urutan syarat, `break` |
| 5 | `for`, `while`, `do-while` | akumulator tidak diinisialisasi, off-by-one |
| 6 | bersarang, `break`, `continue` | batas dalam, rumus pola |

## Strategi soal A (menulis program)
1. **Rancang dulu** — tulis masukan, proses, keluaran, data uji di kertas.
2. **Bangun bertahap** — baca masukan, tampilkan, kompilasi. Tambah satu bagian, kompilasi lagi.
3. **Uji batas** — jalankan data biasa dan nilai batas. Cocokkan format keluaran.

> Program yang **sebagian benar dan terkompilasi** bernilai lebih baik daripada program lengkap yang **tidak terkompilasi**.

## Strategi soal B (tracing & penjelasan)
1. **Buat tabel** — satu kolom per variabel, satu baris per perubahan nilai.
2. **Ikuti persis** — kerjakan sesuai aturan C++: pembagian bulat, precedence, `break`.
3. **Jelaskan** — pakai istilah tepat: pembagian bulat, nilai batas, akumulator, cabang.

> Jawaban B tanpa langkah hanya dapat sebagian poin, **walaupun hasil akhirnya benar**.

## Contoh tracing gabungan
```cpp
int n = 6, hasil = 0;
for (int i = 1; i <= n; i++) {
    if (i % 2 == 0)      { hasil += i; }
    else if (i % 3 == 0) { hasil -= i; }
}
cout << hasil << endl;   // 9
```
i = 2, 4, 6 menambah; i = 3 mengurangi. i = 6 genap, jadi cabang kedua tidak diperiksa. Hasil: 2 + 4 + 6 − 3 = **9**.

## Pola memecah digit (sering keluar!)
```cpp
int n = 4096, jumlah = 0;
while (n > 0) {
    jumlah += n % 10;   // ambil digit terakhir
    n /= 10;            // buang digit terakhir
}
cout << jumlah << endl;  // 19  (4+0+9+6)
```
`% 10` mengambil digit terakhir, `/ 10` membuangnya. Pola ini muncul di banyak soal.

## Latihan telusur
```cpp
int a = 5, b = 0;
while (a > 0) {
    if (a % 2 == 1) { b += a; } else { b -= 1; }
    a -= 2;
}
cout << a << " " << b << endl;   // -1 9
```
a bernilai 5, 3, 1 (semuanya ganjil) → b = 5 + 3 + 1 = 9. Lalu a = −1 dan perulangan berhenti.

---

# PERTEMUAN 8 — UTS (Kisi-kisi & Format)

**Durasi 120 menit · 4 soal · 100 poin**

| Soal | Bentuk | Bagian | Poin |
|---|---|---|---|
| 1 | Menulis program: masukan, ekspresi, percabangan | A | 25 |
| 2 | Menulis program: perulangan dengan sentinel atau pola | A | 25 |
| 3 | Tracing program dengan percabangan dan perulangan | B | 25 |
| 4 | Menemukan, menjelaskan, dan memperbaiki kesalahan | B | 25 |

## Kisi-kisi
| Topik | P | Indikator | Bagian |
|---|---|---|---|
| Struktur program & keluaran | 1 | keluaran terformat dengan escape | A |
| Variabel, tipe, masukan | 2 | memilih tipe, membaca masukan, pembagian bulat | A, B |
| Operator & precedence | 3 | `/` dan `%`, urutan evaluasi, ekspresi logika | A, B |
| Percabangan | 4 | rantai `else if`, `switch`, nilai batas | A, B |
| Perulangan | 5 | `for`, `while`, sentinel, akumulator | A, B |
| Perulangan bersarang | 6 | pola, `break`, `continue`, tracing bersarang | A, B |

## Tata tertib
- **Boleh:** satu lembar catatan A4 tulisan tangan (dua sisi); GDB Online / `g++` untuk soal A.
- **Tidak boleh:** AI, internet selain GDB Online, catatan elektronik, berdiskusi, membuka file lain.
- **Soal B dikerjakan di kertas tanpa menjalankan program.**

---

# KISI-KISI CEPAT: Yang Paling Sering Keluar

## 🔴 Prioritas tinggi
1. **Pembagian bulat** — `7 / 2 = 3`, `(double) a / b`, `a / 2.0`, `double x = a / b` tetap 3
2. **Escape sequence** — `\n`, `\t`, `\\`, `\"`
3. **`cin.ignore()` sebelum `getline`**
4. **Precedence** — `2 + 3 * 4 = 14`, `10 - 4 - 3 = 3`, `20 / 4 * 2 = 10`
5. **`x++` vs `++x`**
6. **`=` vs `==`** (dan warning g++)
7. **Rantai `else if`** — berhenti di syarat pertama yang benar
8. **`switch` + `break`** — tanpa break jatuh ke case berikutnya
9. **Akumulator harus diinisialisasi** sebelum perulangan
10. **Sentinel** — baca sekali sebelum, baca lagi di akhir badan
11. **Off-by-one** — `i < n` vs `i <= n`
12. **Pola digit** — `n % 10` ambil, `n /= 10` buang
13. **Perulangan bersarang** — total putaran = luar × dalam
14. **Rumus piramida** — spasi `n − b`, bintang `2b − 1`
15. **`break` vs `continue`** — keluar vs lompat

## 🟡 Tabel kebenaran & nilai
| Ekspresi | Nilai |
|---|---|
| `7 / 2` | 3 |
| `7 / 2.0` | 3.5 |
| `(double) 7 / 2` | 3.5 |
| `17 % 5` | 2 |
| `2 + 3 * 4` | 14 |
| `10 - 4 - 3` | 3 |
| `20 / 4 * 2` | 10 |
| `7 + 10 % 4 * 2` | 11 |
| `(int) 3.99` | 3 |
| `round(2.5)` | 3 |
| `floor(2.7)` | 2 |
| `sqrt(16.0)` | 4 |
| `pow(2, 10)` | 1024 |

## 🟢 Hafalan cepat
- **Struktur:** `#include <iostream>` → `using namespace std;` → `int main()` → `return 0;`
- **`endl`** = pindah baris + flush; **`\n`** = pindah baris saja
- **bool tanpa `boolalpha`** → 1 / 0
- **`setprecision`** butuh `#include <iomanip>`; berlaku untuk cout sesudahnya
- **`sqrt`/`pow`/`round`/`floor`** butuh `#include <cmath>`
- **`string`** butuh `#include <string>`
- **`switch`** hanya `int` dan `char`
- **Cast ke int** memotong, bukan membulatkan

## ⚠️ Catatan
- Hands-on `solusi/` disimpan dosen; latihan dikerjakan mandiri lalu dicek dengan `cek.sh`.
- Soal UTS sebenarnya tidak dipublikasikan; contoh soal P8 setara tingkat kesulitannya.
