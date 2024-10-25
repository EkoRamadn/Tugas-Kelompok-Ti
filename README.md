
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
