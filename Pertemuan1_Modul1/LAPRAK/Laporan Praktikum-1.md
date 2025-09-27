# <h1 align="center">Laporan Praktikum Modul 1 - Codeblocks IDE & Pengenalan Bahas C++ (Bagian Pertama)</h1>
<p align="center">Muhammad Fauzan - 103112400064</p>

## Dasar Teori




## Guided 

### 1. Input/Output Dasar

```C++
#include<iostream>
using namespace std;

int main() {
    int angka;
    cout << "Masukkan angka pertama: ";
    cin >> angka;
    cout << "Masukkan yang dimaskukan adalah " << angka << endl;
    return 0;
}
```
Program C++ sederhana yang meminta pengguna untuk memasukkan sebuah angka. Setelah angka dimasukkan, program akan menampilkan kembali angka tersebut ke layar

### 2. Kalkulator Aritmatika Dasar

```C++
#include<iostream>
using namespace std;

int main() {
    int angka1, angka2;
    cout << "Masukkan angka pertama: ";
    cin >> angka1;
    cout << "Masukkan angka kedua: ";
    cin >> angka2;

    cout << "penjumlahan: " << angka1 + angka2 << endl;
    cout << "pengurangan: " << angka1 - angka2 << endl;
    cout << "perkalian: " << angka1 * angka2 << endl;
    cout << "pembagian: " << angka1 / angka2 << endl;
    cout << "modulus: " << angka1 % angka2 << endl;

    return 0;
}
```
Kalkulator sederhana yang melakukan operasi aritmatika dasar

### 3. Percabangan If/Else & Switch Menu

```C++
#include<iostream>
using namespace std;

int main() {
    int angka1, angka2;
    cout << "Masukkan angka pertama: ";
    cin >> angka1;
    cout << "Masukkan angka kedua: ";
    cin >> angka2;

    if (angka1 > angka2 ) {
        cout << angka1 << " kurang dari " << angka2 << endl;
    } else {
        cout << angka1 << " lebih dari " << angka2 << endl;
    }

    if (angka1 == angka2) {
        cout << angka1 << " sama dengan " << angka2 << endl;
    } else if (angka1 != angka2) {
        cout << " angka berbeda " << endl;
    }

     int pilihan;
    cout << "MENU" << endl;
    cout << "1. Penjumlahan" << endl;
    cout << "2. Pengurangan" << endl;
    cout << "masukan pilihan: ";
    cin >> pilihan;

    switch (Pilihan){
        case 1:
        cout << "Penjumlahan :" << angka1 + angka2 << endl;
        cout << endl;
        break; 
        case 2:
        cout << "Pengurangan :" << angka1 - angka2 << endl;
        cout << endl;
        break;
        default:
        cout << "Pilihan Salah" << endl;

    }
    return 0;
}
```
Program C++ yang menunjukkan cara kerja pengambilan keputusan dalam kode

### 4. Tiga Jenis Perulangan

```C++
#include <iostream>
using namespace std;

 int main(){
    int angka1;
    cout << "masukan angka1 : ";
    cin >> angka1;

    for (int i = 0; i  < angka1; i++){
      cout << i << " - ";
    }
    cout << endl;

    int j = 10;
    while (j > angka1){
      cout << j << " - ";
      j--;
    }

    cout << endl;
    int k = 10;
    do {
      cout << k << " - ";
    }while (k < angka1);

     return  0;
    
 }
```
Sebuah program C++ yang mendemonstrasikan tiga jenis perulangan (loop) dasar: for, while, dan do-while

### 5. Array & Struct Rapor Siswa

```C++
#include<iostream>
using namespace std;

int main(){
    const int MAX = 5;
    struct rapot{
        string nama;
        float nilai;
    };
    rapot siswa[MAX];

    for(int i = 0; i < MAX; i++){
        cout << "masukkan nama siswa : ";
        cin >> siswa[i].nama;
        cout << endl;
        cout << "masukkan nilai siswa : ";
        cin >> siswa[i].nilai;
    }

    int j = 0;
    while(j < MAX){
        cout << "nama siswa : " << siswa[j].nama << ", nilai : " << siswa[j].nilai << endl;
        j++;
    }
    return 0;
}

```
Program C++ yang dirancang untuk menyimpan dan menampilkan data rapor sederhana untuk beberapa siswa

## Unguided 

### 1. Kalkulator Empat Operasi

```C++
#include<iostream>
using namespace std;

int main() {
    float angka1, angka2;
    cout << "Masukkan angka pertama: ";
    cin >> angka1;
    cout << "Masukkan angka kedua: ";
    cin >> angka2;

    cout << "penjumlahan: " << angka1 + angka2 << endl;
    cout << "pengurangan: " << angka1 - angka2 << endl;
    cout << "perkalian: " << angka1 * angka2 << endl;
    cout << "pembagian: " << angka1 / angka2 << endl;

    return 0;
}
```
### Output Unguided 1 :

##### Output 1
![Output Program 1](https://github.com/mhmmdffzz/103112400064_Muhammad-Fauzan/blob/main/Pertemuan-1_Modul1/LAPRAK/Muhammad_Fauzan-Output-Unguided1.png)

program C++ ini adalah sebuah kalkulator sederhana yang melakukan empat operasi matematika dasar (tambah, kurang, kali, bagi) terhadap dua angka yang dimasukkan oleh pengguna

### 2. Konversi Bilangan 0–100 menjadi Teks

```C++
#include <iostream>
#include <string> 
using namespace std;

int main() {
    int n;
    cout << "Masukkan angka (0 s.d 100): ";
    cin >> n;

    if (n < 0 || n > 100) {
        cout << "luar jangkauan!" << endl;
        return 0;
    }

    string hasil;
    // Indeks 0 dikosongkan agar indeks array sesuai dengan angkanya (misal: satuan[1] untuk "satu")
    string satuan[] = {"", "satu", "dua", "tiga", "empat", "lima", "enam", "tujuh", "delapan", "sembilan"};
    // indeks 0 untuk sepuluh, indeks 1 untuk sebelas
    string belasan[] = {"sepuluh", "sebelas", "dua belas", "tiga belas", "empat belas", "lima belas", "enam belas", "tujuh belas", "delapan belas", "sembilan belas"};
    // Indeks 0 dan 1 dikosongkan karena puluhan dimulai dari 20
    string puluhan[] = {"", "", "dua puluh", "tiga puluh", "empat puluh", "lima puluh", "enam puluh", "tujuh puluh", "delapan puluh", "sembilan puluh"};

    if (n == 100) {
        hasil = "seratus";
    } else if (n == 0) {
        hasil = "nol";
    } else if (n < 10) {
        hasil = satuan[n];
    } else if (n < 20) {
        hasil = belasan[n - 10];
    } else { // n >= 20
        hasil = puluhan[n / 10];
        if (n % 10 != 0) {
            hasil += " " + satuan[n % 10];
        }
    }

    cout << hasil << endl;

    return 0;
}
```
### Output Unguided 2 :

##### Output 1
![Output Program 2](https://github.com/mhmmdffzz/103112400064_Muhammad-Fauzan/blob/main/Pertemuan-1_Modul1/LAPRAK/Muhammad_Fauzan-Output-Unguided2.png)

Program C++ ini berfungsi untuk mengubah angka menjadi bentuk teks (terbilang)

### 3. Pola Iterasi Bertingkat

```C++
#include <iostream>
using namespace std;

int main() {
    int N;                                  // Variabel untuk menyimpan tinggi pola
    cout << "Masukkan angka: ";
    cin >> N;                               // Meminta input

    // Loop untuk mencetak bagian utama pola, dari baris teratas (r=N) hingga (r=1)
    for (int r = N; r >= 1; --r) {
        // Cetak spasi di awal setiap baris untuk membuat bentuk segitiga dan alignment
        // Jumlah spasi adalah 2 * (N - r) agar posisi bintang (*) selalu di tengah
        for (int sp = 0; sp < 2 * (N - r); ++sp) {
            cout << " ";
        }

        // Cetak angka secara menurun dari r hingga 1
        for (int i = r; i >= 1; --i) {
            cout << i << " ";
        }

        // Cetak bintang (*) di tengah baris
        cout << "*";

        // Cetak angka secara menaik dari 1 hingga r
        for (int i = 1; i <= r; ++i) {
            cout << " " << i;
        }
        cout << endl;       // Pindah ke baris baru setelah satu baris selesai
    }

    // Cetak bagian bawah pola (garis vertikal dari bintang)
    // Cetak spasi untuk menempatkan bintang di kolom tengah
    for (int s = 0; s < 2 * N; ++s) {
        cout << " ";
    }
    cout << "*" << endl;                    // Cetak bintang terakhir

    return 0;                               // Mengakhiri program
}
```
### Output Unguided 3 :

##### Output 1
![Output Program 3](https://github.com/mhmmdffzz/103112400064_Muhammad-Fauzan/blob/main/Pertemuan-1_Modul1/LAPRAK/Muhammad_Fauzan-Output-Unguided3.png)

Program C++ ini berfungsi untuk mencetak pola angka dan bintang berbentuk seperti piramida terbalik di terminal

## Kesimpulan
. . .


## Referensi
[1]  
<br>[2] 
<br>...
