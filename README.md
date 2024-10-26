
# Palindrome Checker Program

Program ini digunakan untuk memeriksa apakah sebuah kata merupakan **palindrome** atau tidak. 
Sebuah kata dikatakan palindrome jika dibaca dari depan maupun belakang tetap sama (misalnya, *"katak"* atau *"malam"*).

## Cara Kerja Program

1. **Input Kata**: Pengguna memasukkan kata yang ingin diperiksa.
2. **Pembalikan Kata**: Program akan membalik urutan huruf kata tersebut menggunakan salah satu dari tiga metode loop: 
   - **`for` loop** (digunakan dalam kode utama)
   - **`while` loop** (opsional, ada dalam komentar)
   - **`do-while` loop** (opsional, ada dalam komentar)
3. **Pengecekan Palindrome**: Setelah kata dibalik, program akan membandingkan kata asli dengan kata yang dibalik.
4. **Output Hasil**: Jika kata sama setelah dibalik, program akan mencetak `"True"`; jika tidak, maka akan mencetak `"false"`.

## Kode

```cpp
#include <iostream>
using namespace std;

int main() {
    string kata, kataBalik;

    cout << "Chek Kata" << "\n";
    cout << "Input Kata : ";
    cin >> kata;

    // Membalik kata menggunakan for loop
    for (int i = kata.length() - 1; i >= 0; i--) {
        kataBalik += kata[i];
    }

    // Alternatif: Membalik kata menggunakan while loop
    // int i = kata.length() - 1;
    // while (i >= 0) {
    //     kataBalik += kata[i];
    //     i--;
    // }

    // Alternatif: Membalik kata menggunakan do-while loop
    // int i = kata.length() - 1;
    // do {
    //     kataBalik += kata[i];
    //     i--;
    // } while (i >= 0);

    // Pengecekan apakah kata palindrome
    string hasil = (kata == kataBalik) ? "True" : "false";
    cout << "hasil : " << hasil;

    return 0;
}
```

## Penjelasan Kode

1. **Input**: Program meminta pengguna untuk memasukkan sebuah kata melalui `cin`.
2. **Proses Pembalikan Kata**:  
   - Pada kode utama, digunakan **`for` loop** untuk mengisi string `kataBalik` dengan huruf-huruf dari belakang ke depan.
   - Terdapat dua alternatif loop lain (`while` dan `do-while`) yang dapat digunakan jika diinginkan.
3. **Pengecekan Palindrome**:  
   - Menggunakan **operator ternary** `(kata == kataBalik) ? "True" : "false";` untuk membandingkan kata asli dan kata yang dibalik.
4. **Output**: Program akan menampilkan hasil apakah kata tersebut palindrome atau bukan.

## Contoh Output

```
Chek Kata
Input Kata : katak
hasil : True
```

```
Chek Kata
Input Kata : rumah
hasil : false
```

## Cara Menjalankan Program

1. Kompilasi program dengan perintah:
   ```
   g++ -o palindrome_checker program.cpp
   ```
2. Jalankan program dengan perintah:
   ```
   ./palindrome_checker
   ```

## Penjelasan Alur Program

dimulai dari line 1 :
```cpp
#include <iostream>
```
menyertakan file heaedr atau library Input-Output Stream atau `<iosstream>`

```cpp
using namespace std;
```
memberitahu compiler agar kita tidak perlu menuliskan awalan `std::` setiap kali menggunakan elemen-elemen dari namespace standar (seperti `std::cout`, `std::cin`, dll.)

`namespace` adalah fitur dalam C++ yang digunakan untuk mengelompokkan fungsi, kelas, atau variabel agar tidak terjadi konflik nama (name conflict).

```cpp
int main(){
   //kode lain nya...
}
```
membuat fungsi main dengan tipe data `int` integer

```cpp
string kata, kataBalik;
```
mendeklarasikan variabel `kata` dan `kataBalik` dengan tipe data `string`

```cpp
cout << "Check Kata" << "\n";
cout << "Input Kata : ";
```
`cout` berfungsi untuk menampilkan `"Check Kata"` dan `"Input Kata : "` di console.

`"\n"` merupakan karakter spesial dalam string yang bertujuan agar tampilan console selanjutnya berada pada bawah teks dan tidak dalam 1 line.


```cpp
cin >> kata;
```
`cin` berfungsi untuk memasuka nilai ke variabel `kata`.


# Pembalik String Menggunakan Looping di C++

Kode ini digunakan untuk membalik urutan karakter dari sebuah **String** dalam bahasa Java. Terdapat tiga jenis implementasi dengan loop berbeda:

1. **`for` loop**  
2. **`while` loop**  
3. **`do-while` loop**

## 1. Pembalik String Menggunakan `for` loop

```java
for(int i = kata.length() - 1; i >= 0; i--) {
    kataBalik += kata[i];
}
```

- **Penjelasan:**
  - Loop dimulai dari indeks terakhir string (`kata.length() - 1`).
  - Loop berjalan mundur sampai indeks 0 (atau selama `i >= 0`).
  - Pada setiap iterasi, karakter pada indeks ke-`i` ditambahkan ke variabel `kataBalik`.

**Kelebihan:**  
`for` loop cocok digunakan jika jumlah iterasi diketahui di awal.

---

## 2. Pembalik String Menggunakan `while` loop

```java
int i = kata.length() - 1;

while(i >= 0) {
    kataBalik += kata[i];
    i--;
}
```

- **Penjelasan:**
  - Deklarasi variabel `i` berada di luar loop dan diinisialisasi dengan nilai indeks terakhir.
  - Loop akan terus berjalan selama `i` lebih besar atau sama dengan 0.
  - Setiap iterasi menambahkan karakter ke `kataBalik` dan menurunkan nilai `i`.

**Kelebihan:**  
`while` loop lebih fleksibel dan cocok untuk kasus di mana kondisi berhenti mungkin tidak diketahui di awal.

---

## 3. Pembalik String Menggunakan `do-while` loop

```java
int i = kata.length() - 1;

do {
    kataBalik += kata[i];
    i--;
} while(i >= 0);
```

- **Penjelasan:**
  - Sama seperti `while` loop, variabel `i` diinisialisasi terlebih dahulu.
  - Perbedaannya, **`do-while`** selalu mengeksekusi blok kode minimal satu kali, bahkan jika kondisi pada awalnya salah.
  - Loop terus berjalan selama kondisi `i >= 0` terpenuhi.

**Kelebihan:**  
`do-while` loop berguna jika Anda ingin memastikan kode dijalankan setidaknya sekali, tanpa memeriksa kondisi terlebih dahulu.

---

## Kesimpulan
Ketiga jenis loop (`for`, `while`, dan `do-while`) memiliki hasil yang sama, yaitu membalikkan urutan karakter dari string. Pilihan loop yang digunakan tergantung pada kebutuhan dan kondisi spesifik program.








