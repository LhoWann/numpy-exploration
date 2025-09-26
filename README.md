# **NUMPY EXPLORATION**

## Pendahuluan

Repositori ini dibuat sebagai bagian dari eksplorasi mandiri materi **Bab 2: Vectors, Matrices, and Multidimensional Arrays** dari buku *Numerical Python* (Robert Johansson).
Tujuan utama eksplorasi ini adalah memahami bagaimana data direpresentasikan dan dimanipulasi menggunakan **NumPy**, library fundamental Python untuk komputasi numerik.

Dengan mempelajari berbagai sintaks dan fungsi dasar NumPy, diharapkan:

* Mampu memahami karakteristik dan tipe data dalam array.
* Menguasai pembuatan array, matriks, dan operasi dasar.
* Terbiasa dengan manipulasi array multidimensi.
* Mampu melakukan operasi aritmatika, logika, serta fungsi **elementwise** dengan efisien.

Repositori ini ditulis dalam format **Markdown** dengan tambahan contoh kode Python agar lebih mudah dipahami dan dipraktikkan.

---

## 📑 Daftar Isi

1. [Mengenali Karakteristik Data](#1-mengenali-karakteristik-data)
2. [Tipe Data](#2-tipe-data)
3. [Membuat Array dengan Berbagai Teknik](#3-membuat-array-dengan-berbagai-teknik)
4. [Membuat Matriks](#4-membuat-matriks)
5. [Manipulasi Matriks dan Operasi Matriks](#5-manipulasi-matriks-dan-operasi-matriks)
6. [Membuat Array Multidimensi](#6-membuat-array-multidimensi)
7. [Mengetahui Index Elemen pada Array](#7-mengetahui-index-elemen-pada-array)
8. [Operasi Logika dengan Boolean](#8-operasi-logika-dengan-boolean)
9. [Operasi Aritmatika](#9-operasi-aritmatika)
10. [Elementwise Functions](#10-elementwise-functions)
11. [Agregasi Beberapa Array](#11-agregasi-beberapa-array)
12. [Operasi dengan Logika Himpunan](#12-operasi-dengan-logika-himpunan)
13. [Manipulasi Array](#13-manipulasi-array)

---

## 1. Mengenali Karakteristik Data

```python
import numpy as np

arr = np.array([1, 2, 3, 4, 5])
print(type(arr))     # <class 'numpy.ndarray'>
print(arr.shape)     # (5,)
print(arr.ndim)      # 1
```

---

## 2. Tipe Data

```python
arr = np.array([1, 2, 3], dtype=np.float32)
print(arr.dtype)   # float32
```

---

## 3. Membuat Array dengan Berbagai Teknik

```python
np.zeros((3,3))
np.ones((2,4))
np.arange(0,10,2)
np.linspace(0,1,5)
```

---

## 4. Membuat Matriks

```python
mat = np.matrix([[1,2],[3,4]])
print(mat)
```

---

## 5. Manipulasi Matriks dan Operasi Matriks

```python
A = np.array([[1,2],[3,4]])
B = np.array([[5,6],[7,8]])

print(A + B)   # Penjumlahan
print(A @ B)   # Perkalian matriks
```

---

## 6. Membuat Array Multidimensi

```python
arr3d = np.array([[[1,2],[3,4]], [[5,6],[7,8]]])
print(arr3d.shape)   # (2,2,2)
```

---

## 7. Mengetahui Index Elemen pada Array

```python
arr = np.array([10, 20, 30, 40])
print(arr[0])   # 10
print(arr[-1])  # 40
```

---

## 8. Operasi Logika dengan Boolean

```python
arr = np.array([1,2,3,4,5])
print(arr > 3)        # [False False False  True  True]
print(arr[arr > 3])   # [4 5]
```

---

## 9. Operasi Aritmatika

```python
a = np.array([1,2,3])
b = np.array([4,5,6])
print(a + b)   # [5 7 9]
print(a * b)   # [ 4 10 18]
```

---

## 10. Elementwise Functions

```python
x = np.linspace(-np.pi, np.pi, 5)
print(np.sin(x))
print(np.exp(x))
print(np.sqrt(np.abs(x)))
```

---

## 11. Agregasi Beberapa Array

```python
arr = np.array([1,2,3,4,5])
print(arr.sum())      # 15
print(arr.mean())     # 3.0
print(arr.max())      # 5
```

---

## 12. Operasi dengan Logika Himpunan

```python
a = np.array([1,2,3,4])
b = np.array([3,4,5,6])

print(np.union1d(a,b))        # gabungan
print(np.intersect1d(a,b))    # irisan
print(np.setdiff1d(a,b))      # selisih
```

---

## 13. Manipulasi Array

```python
arr = np.arange(6).reshape((2,3))
print(arr)

print(arr.T)    # transpose
print(arr.flatten())  # menjadi 1 dimensi
```

---

UNTUK PENJELASAN LEBIH LANNJUT SILAKAN BUKA FILE MD YANG TERLAMPIRKAN PADA REPOSITORI INI !!!
