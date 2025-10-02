# <h1 align="center">Laporan Praktikum Modul 2 - Pengenalan Bahasa C++ (Bagian Kedua)</h1>
<p align="center">Muhammad Fauzan - 103112400064</p>

## Dasar Teori
Array atau dalam bahasa Indonesia disebut larik, merupakan sebuah teknik pemrograman dimana array tersebut dianalogikan sebagai wadah untuk menyimpan data-data yang berjumlah banyak dan memiliki tipe data yang sama[1]. Dalam bahasa pemrograman C++, array dideklarasikan dengan tanda [ ] (kurung siku). Setiap data disimpan dalam alamat memori yang berbeda-beda yang disebut dengan elemen array. Setiap elemen mempunyai nilai indeks sesuai dengan urutannya. Nilai indeks dimulai dari 0 dan berfungsi untuk mengakses data-data yang ada didalam array. Array digunakan jika kita memerlukan penyimpanan sementara untuk data-data yang bertipe sama didalam memori, untuk selanjutnya data-data tersebut dimanipulasi (dihitung atau diterapkan oleh proses lainnya)[2]. Array terbagi menjadi beberapa jenis, antara lain sebagai berikut.

### A. Array 1 Dimensi <br/>
Array 1 dimensi merupakan jenis yang paling dasar dalam array. Array jenis ini terdiri dari kumpulan data dengan tipe yang sama yang disusun dalam satu baris atau mewakili bentuk suatu vektor. Array 1 dimensi dideklarasikan sebagai berikut.
```C++
tipe_data nama_array[jumlah_elemen];
```
Sebagai contoh jika ingin mendeklarasikan array dengan tipe data integer dengan nama Arr dan mempunyai lima buah elemen atau dapat menyimpan lima buah data bertipe integer dapat dituliskan sebagai berikut.
```C++
int Arr[5];
```
Atau jika nilai setiap elemennya ingin diinisialisasikan manual saat pendeklarasian array dapat ditulis sebagai berikut.
```C++
int Arr[5] = {1, 2, 3, 4, 5};
```
Contoh array diatas memiliki 5 elemen yaitu 1, 2, 3, 4, dan 5. Elemen-elemen tersebut terurut sesuai indeksnya yang dimulai dari 0. Indeks 0 merujuk pada elemen pertama yaitu bilangan 1 dan berlanjut hingga indeks ke-4 yaitu bilangan 5.

### B. Array 2 Dimensi
Matriks pada umumnya dikenal dengan array 2 dimensi. Pada array 2 dimensi, terdapat 2 buah tanda kurung siku ([ ]) yang masing-masing kurung siku tersebut mendefinisikan baris dan kolom yang ada pada matriks. Berikut bentuk umum deklarasi array dua dimensi (matriks).
```C++
tipe_data nama_array[jumlah elemen baris][jumlah elemen kolom];
```
Sebagai contoh jika ingin mendeklarasikan array dengan tipe data integer dengan nama Arr yang didalamnya terdapat 3 baris dan 4 kolom dapat dituliskan sebagai berikut.
```C++
int Arr[3][3];
```
Sama seperti array 1 dimensi, inisialisasi nilai array 2 dimensi (matriks) tersebut dapat dibuat manual atau diinput oleh pengguna saat program dijalankan. Karena array 2 dimensi mempunyai lebih dari satu bentuk index array, maka dalam inisialisasinya perlu menggunakan tanda kurung kurawal ({ }) untuk membentuk baris array, contohnya sebagai berikut.
```C++
int Arr[3][3] = {{3,4,8},{3,9,2},{6,3,0}};
```
### C. Arrnpointer

Array dan pointer di C++ saling terkait: dalam banyak ekspresi, nama array akan *decay* menjadi pointer ke elemen pertama (tipe `T*`). Akibatnya, ekspresi `arr[i]` setara dengan `*(arr + i)` dan aritmetika pointer (`ptr + k`) melangkah per elemen, bukan per byte. Bedakan `arr` (yang *decay* ke `T*`) dengan `&arr` (pointer ke seluruh array, tipe `T (*)[N]`). Pada parameter fungsi, deklarasi `T arr[]` setara dengan `T*`, sehingga ukuran array tidak ikut terbawa dan perlu dikirim terpisah. Gunakan dengan hati-hati agar tidak terjadi akses di luar batas (*out-of-bounds*). [4]

## Guided

### 1. Array1 dimensi 

```C++
#include<iostream>
using namespace std;
int main(){
    int arr [5];
    for (int i = 0; i < 5; i++){
        cout<<"Masukkan nilai indeks ke-"<<i<<": ";
        cin>>arr[i];
    }
    int j = 0;
    while (j < 5){
        cout<< "Isi indeks ke-"<< j <<" i "<< arr[j]<< endl;
        j++;
    }
    return 0;
}
```
Program C++ sederhana yang 

### 2. Array2 dimensi 

```C++
#include<iostream>
using namespace std;

void tampilkanhasil(int arr[2][2]){
    for (int i = 0; i < 2; i++){
        for (int j = 0; j < 2; j++){
            cout<<arr[i][j]<<" ";
        }
        cout<<endl;
    }
}

int main(){
    int arrA[2][2] = {
        {1, 2},
        {3, 4}
    };
    int arrB[2][2] = {
        {2, 3},
        {4, 5}
    };  
    int arrC[2][2] = {0};
    int arrD[2][2] = {0};
    
    // Penjumlahan matriks 2x2
    for (int i = 0; i < 2; i++){
        for (int j = 0; j < 2; j++){
            arrC[i][j] = arrA[i][j] + arrB[i][j];
        }
    }
    
    cout<<"Hasil Penjumlahan: "<<endl;
    tampilkanhasil(arrC);

    cout<<endl;

    // Perkalian matriks 2x2
    for (int i = 0; i < 2; i++){            //Perulangan baris 
        for (int j = 0; j < 2; j++){        //Perulangan kolom  
            for (int k = 0; k < 2; k++){    //Perulangan perkalian
                arrD[i][j] += arrA[i][k] * arrB[k][j];
            }
        }
    }

    cout<<"Hasil Perkalian: "<<endl;
    tampilkanhasil(arrD);

    return 0;
}
```
Penjelasan

### 3. Arrnpointer

```C++
#include <iostream>
using namespace std;

int main(){
    int arr[]={10,20,30,40,50};
    int*ptr=arr; //pointer yang menunjuk ke elemen pertama array

    //mengakses elemen array menggunakan pointer
    for (int i = 0; i < 5; i++){
        cout<<"elemen array ke-"<< i+1<<" menggunakan pointer: "<<*(ptr+i)<<endl;
    }

    //mengakses elemen array menggunakan indeks
    for (int i = 0; i < 5; i++){
        cout<<"Elemen array ke-"<< i+1 <<" menggunakan indeks: "<<arr[i]<<endl;
    }
    return 0;
}
```
Program C++ yang 

### 4. Fungsi prosedur

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
Sebuah program C++ yang 

## Unguided 

### 1. 

```C++
#include <iostream>
using namespace std;

void jumlahMatriks(int arrA[3][3], int arrB[3][3], int arrC[3][3]){
    for (int i = 0; i < 3; i++){
        for (int j = 0; j < 3; j++){
            arrC[i][j] = arrA[i][j] + arrB[i][j];
        }
    }
    cout << "Hasil Penjumlahan: " << endl;
    for (int i = 0; i < 3; i++){
        for (int j = 0; j < 3; j++){
            cout << arrC[i][j] << " ";
        }
        cout << endl;
    }
}
void kurangMatriks(int arrA[3][3], int arrB[3][3], int arrC[3][3]){
    for (int i = 0; i < 3; i++){
        for (int j = 0; j < 3; j++){
            arrC[i][j] = arrA[i][j] - arrB[i][j];
        }
    }
    cout << "Hasil Pengurangan: " << endl;
    for (int i = 0; i < 3; i++){
        for (int j = 0; j < 3; j++){
            cout << arrC[i][j] << " ";
        }
        cout << endl;
    }
}
void kaliMatriks(int arrA[3][3], int arrB[3][3], int arrC[3][3]){
    for (int i = 0; i < 3; i++){            //Perulangan baris 
        for (int j = 0; j < 3; j++){        //Perulangan kolom  
            for (int k = 0; k < 3; k++){    //Perulangan perkalian
                arrC[i][j] += arrA[i][k] * arrB[k][j];
            }
        }
    }
    cout << "Hasil Perkalian: " << endl;
    for (int i = 0; i < 3; i++){
        for (int j = 0; j < 3; j++){
            cout << arrC[i][j] << " ";
        }
        cout << endl;
    }
}

int main() {
    int arrA[3][3] = {
        {7, 12, 22},
        {31, 6, 41},
        {15, 19, 36}
    };
    int arrB[3][3] = {
        {11, 34, 7},
        {3, 25, 41},
        {5, 18, 33}
    };
    int arrC[3][3] = {0};
    int pilihan;

    do {
        cout << "--- Menu Program Matriks ---" << endl;
        cout << "1. Penjumlahan matriks" << endl;
        cout << "2. Pengurangan matriks" << endl;
        cout << "3. Perkalian matriks" << endl;
        cout << "4. Keluar" << endl;
        cout << "Masukkan pilihan Anda (1-4): ";
        cin >> pilihan;

        switch (pilihan) {
            case 1:
                jumlahMatriks(arrA, arrB, arrC);
                break;
            case 2:
                kurangMatriks(arrA, arrB, arrC);
                break;
            case 3:
                kaliMatriks(arrA, arrB, arrC);
                break;
            case 4:
                cout << "Keluar dari program." << endl;
                break;
            default:
                cout << "Pilihan tidak valid. Silakan coba lagi." << endl;
        }
        cout << endl; // Tambahkan baris kosong untuk pemisah antar menu
    } while (pilihan != 4);

    return 0;
}
```
### Output Unguided 1 :

##### Output 1
![Output Program 1](https://github.com/mhmmdffzz/103112400064_Muhammad-Fauzan/blob/main/Pertemuan2_Modul2/LAPRAK/Muhammad_Fauzan-Output-Unguided1-1.png)

##### Output 2
![Output Program 1](https://github.com/mhmmdffzz/103112400064_Muhammad-Fauzan/blob/main/Pertemuan2_Modul2/LAPRAK/Muhammad_Fauzan-Output-Unguided1-2.png)

##### Output 3
![Output Program 1](https://github.com/mhmmdffzz/103112400064_Muhammad-Fauzan/blob/main/Pertemuan2_Modul2/LAPRAK/Muhammad_Fauzan-Output-Unguided1-3.png)

##### Output 4
![Output Program 1](https://github.com/mhmmdffzz/103112400064_Muhammad-Fauzan/blob/main/Pertemuan2_Modul2/LAPRAK/Muhammad_Fauzan-Output-Unguided1-4.png)

program C++ ini adalah 

### 2. 

```C++
#include <iostream>
using namespace std;

int main() {
    // 1) Buat 3 variabel integer
    int panjang = 10;
    int lebar = 5;
    int luas = 0;
    int keliling = 0;

    // Menampilkan Nilai Awal
    cout << "--- Nilai Awal ---" << endl;
    cout << "Panjang: " << panjang << endl;
    cout << "Lebar: " << lebar << endl;

    // 2) Deklarasikan dua pointer
    int *ptrPanjang = &panjang;
    int *ptrLebar = &lebar;

    // 3) Hitung luas dan keliling menggunakan pointer
    luas = (*ptrPanjang) * (*ptrLebar);
    keliling = 2 * ((*ptrPanjang) + (*ptrLebar));

    // 4) Cetak nilai luas dan keliling
    cout << "\n--- Hasil Perhitungan ---" << endl;
    cout << "Luas Persegi Panjang: " << luas << endl;
    cout << "Keliling Persegi Panjang: " << keliling << endl;

    // 5) Ubah nilai panjang dan lebar melalui pointer
    *ptrPanjang = 12;
    *ptrLebar = 6;

    // Hitung kembali luas dan keliling dengan nilai baru
    luas = (*ptrPanjang) * (*ptrLebar);
    keliling = 2 * ((*ptrPanjang) + (*ptrLebar));

    // 6) Cetak nilai panjang dan lebar yang baru
    cout << "\n--- Nilai Setelah Diubah Melalui Pointer ---" << endl;
    cout << "Panjang Baru: " << panjang << endl;
    cout << "Lebar Baru: " << lebar << endl;
    cout << "Luas Baru: " << luas << endl;
    cout << "Keliling Baru: " << keliling << endl;

    return 0;
}
```
### Output Unguided 2 :

##### Output 1
![Output Program 2](https://github.com/mhmmdffzz/103112400064_Muhammad-Fauzan/blob/main/Pertemuan1_Modul2/LAPRAK/Muhammad_Fauzan-Output-Unguided2.png)

Program C++ ini berfungsi untuk

## Kesimpulan
...

## Referensi
[1] Putra, Muhammad Taufik D., et al. (2022). "BELAJAR DASAR PEMROGRAMAN DENGAN C++". Edited by Damayanti, Evi, CV WIDINA MEDIA UTAMA. Diakses pada 17 Maret 2024 melalui https://repository.penerbitwidina.com/publications/558527/belajar-dasar-pemrograman-dengan-c#cite. 
<br>[2] Indahyati, Uce., Rahmawati Yunianita. (2020). "BUKU AJAR ALGORITMA DAN PEMROGRAMAN DALAM BAHASA C++". Sidoarjo: Umsida Press. Diakses pada 17 Maret 2024 melalui https://doi.org/10.21070/2020/978-623-6833-67-4.
<br>[3] Tou, N., Kom, S., & Kom, M. (2022). Bahan ajar: dasar-dasar pemrograman. Universitas Bangka Belitung. Diakses pada 17 Maret 2024 melalui http://repository.ubb.ac.id/7104/1/Modul%20Dasar-Dasar%20Pemrograman.pdf.
<br>[4] Setiyawan, R. D., Hermawan, D., Abdillah, A. F., Mujayanah, A., & Vindua, R. (2024). Penggunaan struktur data stack dalam pemrograman C++ dengan pendekatan array dan linked list. JUTECH: Journal Education and Technology, 5(2), 484–498. https://doi.org/10.31932/jutech.v5i2.4263
PDF : https://jurnal.stkippersada.ac.id/jurnal/index.php/jutech/article/download/4263/pdf