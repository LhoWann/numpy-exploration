# **ELEMENTWISE FUNCTION**

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
