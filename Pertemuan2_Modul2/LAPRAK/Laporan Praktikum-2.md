# <h1 align="center">Laporan Praktikum Modul 2 - Pengenalan Bahasa C++ (Bagian Kedua)</h1>
<p align="center">Muhammad Fauzan - 103112400064</p>

## Dasar Teori
...

## Guided 1

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
![Output Program 1](https://github.com/mhmmdffzz/Fzan/blob/main/Pertemuan2_Modul2/LAPRAK/Muhammad_Fauzan-Output-Unguided1-1.png)

##### Output 2
![Output Program 1](https://github.com/mhmmdffzz/FZan/blob/main/Pertemuan2_Modul2/LAPRAK/Muhammad_Fauzan-Output-Unguided1-2.png)

##### Output 3
![Output Program 1](https://github.com/mhmmdffzz/FZan/blob/main/Pertemuan2_Modul2/LAPRAK/Muhammad_Fauzan-Output-Unguided1-3.png)

##### Output 4
![Output Program 1](https://github.com/mhmmdffzz/FZan/blob/main/Pertemuan2_Modul2/LAPRAK/Muhammad_Fauzan-Output-Unguided1-4.png)

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
[1] Dewi, L. J. E. (2010). Media pembelajaran bahasa pemrograman C++. Jurnal Pendidikan Teknologi dan Kejuruan (Undiksha), 7(1), 63–72.
Halaman artikel: https://ejournal.undiksha.ac.id/index.php/JPTK/article/view/31
PDF: https://ejournal.undiksha.ac.id/index.php/JPTK/article/download/31/25/94
<br>[2]Prasetyoadi, E. B., Rokhmawati, R. I., & Wicaksono, S. A. (2019). Pengembangan e-modul pembelajaran “Pemrograman Dasar” dengan metode R&D (Studi SMKN 4 Malang). Jurnal Pengembangan Teknologi Informasi dan Ilmu Komputer (J-PTIIK), 3(10), 10118–10129.
Halaman artikel: https://j-ptiik.ub.ac.id/index.php/j-ptiik/article/view/6646
PDF: https://j-ptiik.ub.ac.id/index.php/j-ptiik/article/download/6646/3193/46603
<br>[3] Asprila, D. A., Wijoyo, S. H., & Az-Zahra, H. M. (2021). Evaluasi usability pada aplikasi Learn C++ (usability testing). Jurnal Pengembangan Teknologi Informasi dan Ilmu Komputer (J-PTIIK), 5(6), 2677–2686.
Halaman artikel: https://j-ptiik.ub.ac.id/index.php/j-ptiik/article/view/9392
PDF: https://j-ptiik.ub.ac.id/index.php/j-ptiik/article/download/9392/4217/66090
<br>[4] Sano, A. N. A. (2020). PENGENALAN CODE::BLOCKS. Academia.edu.
Halaman: https://www.academia.edu/44359359/PENGENALAN_CODE_BLOCKS
<br>[5] Effendi, Q. M. F. Z., dkk. (2024). Penerapan Pemrograman C++ dalam Pengembangan Alat. Jurnal Majemuk, 3(1).
Halaman artikel: https://jurnalilmiah.org/journal/index.php/majemuk/article/view/665