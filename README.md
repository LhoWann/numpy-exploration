# **NUMPY EXPLORATION**

## ELEMENTWISE FUNCTION
NumPy menyediakan banyak **fungsi vektorisasi** yang bekerja secara *elementwise*, artinya operasi dilakukan untuk setiap elemen array secara individu. Fungsi-fungsi ini sangat berguna karena:

* Input: satu atau lebih array (dengan dimensi yang cocok atau bisa  *broadcasted* ).
* Output: array baru dengan bentuk ( *shape* ) yang sama.
* Eksekusi jauh lebih cepat daripada menggunakan loop Python biasa.

> Fungsi element-wise adalah operasi atau fungsi yang diterapkan pada setiap elemen dari sebuah array NumPy secara individual. Hasilnya adalah sebuah array baru dengan bentuk yang sama, di mana setiap elemennya adalah hasil dari penerapan fungsi tersebut pada elemen yang bersesuaian di array input.

Fungsi element-wise merupakan inti dari ekspresi tervektorisasi di NumPy. Alih-alih menulis perulangan `for` manual dalam python untuk memproses setiap nilai satu per satu (yang cenderung lambat), Anda dapat menerapkan satu fungsi ke seluruh array sekaligus. Hal ini menghasilkan kode yang lebih ringkas, mudah dibaca, dan memiliki performa yang jauh lebih tinggi karena operasinya dijalankan oleh kode C atau Fortran yang terkompilasi di latar belakang.

## Contoh Dasar

```
import numpy as np

x = np.linspace(-1, 1, 11)
print(x)
# [-1.  -0.8 -0.6 -0.4 -0.2  0.   0.2  0.4  0.6  0.8  1. ]

y = np.sin(np.pi * x)
print(np.round(y, 4))
# [-0.     -0.5878 -0.9511 -0.9511 -0.5878  0.      0.5878  0.9511  0.9511  0.5878  0.    ]

```

## Elementwise Arithmetic Operators

| Operator     | Deskripsi       |
| ------------ | --------------- |
| `+ , +=`   | Penjumlahan     |
| `- , -=`   | Pengurangan     |
| `* , *=`   | Perkalian       |
| `/ , /=`   | Pembagian       |
| `//,//=`   | Pembagian bulat |
| `** , **=` | Pangkat         |

## Elementary Mathematical Functions

| Fungsi NumPy                           | Deskripsi                    |
| -------------------------------------- | ---------------------------- |
| `np.sin, np.cos, np.tan`             | Fungsi trigonometri          |
| `np.arcsin, np.arccos, np.arctan`    | Fungsi trigonometri invers   |
| `np.sinh, np.cosh, np.tanh`          | Fungsi hiperbolik            |
| `np.arcsinh, np.arccosh, np.arctanh` | Fungsi hiperbolik invers     |
| `np.sqrt`                            | Akar kuadrat                 |
| `np.exp`                             | Eksponensial                 |
| `np.log, np.log2, np.log10`          | Logaritma basis e, 2, dan 10 |

## Mathematical Operations

Fungsi Numpy

| Fungsi NumPy                                    | Deskripsi                                    |
| ----------------------------------------------- | -------------------------------------------- |
| `np.add, np.subtract, np.multiply, np.divide` | Aritmatika dasar dua array                   |
| `np.power`                                    | Pangkat elementwise                          |
| `np.remainder`                                | Sisa pembagian                               |
| `np.reciprocal`                               | Kebalikan (1/x)                              |
| `np.real, np.imag, np.conj`                   | Bagian real, imajiner, dan konjugat kompleks |
| `np.sign, np.abs`                             | Tanda dan nilai absolut                      |
| `np.floor, np.ceil, np.rint, np.round`        | Pembulatan                                   |


## AGREGASI BEBERAPA ARRAY

Agregasi array adalah proses menghitung nilai ringkasan (seperti rata-rata atau jumlah total) dari elemen-elemen di dalam sebuah array. **NumPy menyediakan serangkaian fungsi agregat yang mengambil array sebagai input dan, secara default, mengembalikan sebuah nilai skalar tunggal sebagai output**.

## **Penjelasan Rinci**

Agregasi adalah salah satu operasi paling umum dalam analisis data. NumPy mengimplementasikan fungsi-fungsi ini dengan sangat efisien. Alih-alih Anda menulis perulangan manual untuk menghitung jumlah atau rata-rata, Anda bisa memanggil satu fungsi tunggal.

* **Sintaks Ganda (Fungsi vs. Metode)** : Sebagian besar fungsi agregasi dapat dipanggil dengan dua cara: sebagai fungsi dari modul NumPy (misalnya, `np.sum(data)`) atau sebagai metode dari objek array itu sendiri (misalnya, `data.sum()`). **Keduanya ekuivalen**^2^.
* **Agregasi Sepanjang Sumbu Tertentu (Argumen `axis`)** : Secara default, agregasi dilakukan pada keseluruhan elemen array. **Namun, Anda dapat mengontrol sumbu (dimensi) mana yang akan diagregasi menggunakan argumen kata kunci **
  `<span class="citation-116">axis</span>`^3^. Ini sangat berguna untuk array multi-dimensi.
* Untuk array 2D (matriks), `axis=0` berarti agregasi dilakukan **sepanjang kolom** (menghasilkan satu nilai untuk setiap kolom).
* Untuk array 2D, `axis=1` berarti agregasi dilakukan **sepanjang baris** (menghasilkan satu nilai untuk setiap baris).

## **Contoh Penggunaan**

Mari kita gunakan contoh dari dokumen untuk memperjelas. Pertama, kita buat sebuah array 3x3:

**Python**

```
import numpy as np

data = np.arange(1,10).reshape(3,3)
print(data)
```

```
[[1 2 3]
 [4 5 6]
 [7 8 9]]
```

1. Agregasi Keseluruhan Array (Default)
   Fungsi ini akan menjumlahkan semua elemen dalam array menjadi satu nilai.
   **Python**

   ```
   # Menjumlahkan semua elemen
   print(data.sum())
   ```

   ```
   45
   ```
2. Agregasi Sepanjang Sumbu Kolom (axis=0)
   Fungsi ini akan menjumlahkan elemen-elemen ke bawah (sepanjang kolom), menghasilkan sebuah array baru yang berisi jumlah dari setiap kolom.
   **Python**

   ```
   # Menjumlahkan sepanjang kolom
   # Kolom 1: 1+4+7=12
   # Kolom 2: 2+5+8=15
   # Kolom 3: 3+6+9=18
   print(data.sum(axis=0))
   ```

   ```
   [12 15 18]
   ```
3. Agregasi Sepanjang Sumbu Baris (axis=1)
   Fungsi ini akan menjumlahkan elemen-elemen ke samping (sepanjang baris), menghasilkan sebuah array baru yang berisi jumlah dari setiap baris.
   **Python**

   ```
   # Menjumlahkan sepanjang baris
   # Baris 1: 1+2+3=6
   # Baris 2: 4+5+6=15
   # Baris 3: 7+8+9=24
   print(data.sum(axis=1))
   ```

   ```
   [ 6 15 24]
   ```

## **Tabel Fungsi Agregasi Umum**

Berikut adalah ringkasan fungsi-fungsi agregasi yang tersedia di NumPy, berdasarkan Tabel 2-9 dari dokumen:

| Fungsi NumPy                | Deskripsi                                                            |
| --------------------------- | -------------------------------------------------------------------- |
| `np.mean`                 | **Rata-rata dari semua nilai dalam array.**                 |
| `np.std`                  | **Standar deviasi.**                                        |
| `np.var`                  | **Varians.**                                                |
| `np.sum`                  | **Jumlah dari semua elemen.**                               |
| `np.prod`                 | **Produk dari semua elemen.**                               |
| `np.cumsum`               | **Jumlah kumulatif dari semua elemen.**                    |
| `np.cumprod`              | **Produk kumulatif dari semua elemen.**                    |
| `np.min`,`np.max`       | **Nilai minimum/maksimum dalam sebuah array.**             |
| `np.argmin`,`np.argmax` | **Indeks dari nilai minimum/maksimum dalam sebuah array.** |
| `np.all`                  | **Mengembalikan**                                              |
| `np.any`                  | **Mengembalikan**                                              |
