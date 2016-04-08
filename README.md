# UTSP KOM206 - Organisasi dan Arsitektur Komputer

## Ketentuan
- Tuliskan Nama (@author :), NIM (@nim : ) dan No. (@no :) di bagian atas setiap jawaban code assembly.
- Peserta `HANYA` diperbolehkan membuka modul praktikum, bukan code" tugas praktikum. `TIDAK DIPERBOLEHKAN` membuka web lain selain Git ini.
- Modul Praktikum dan Template `main.asm` terdapat di Git ini, Anda hanya perlu men-download zip Git ini. Opsi Download ada di bagian kanan atas.
- Peserta yang melanggar ketentuan akan diberikan sanksi nilai UTSP `0` dan nilai UASP `-20`.


## Cara Menjawab
- Buatlah `variabel` sesuai dengan ketentuan tiap soal.
- Simpan `variabel` jawaban atau hasil sesuai dengan ketentuan tiap soal.
- Kesalahan penulisan `variabel` akan menyebabkan jawaban anda salah, karena yang akan dicek adalah `variabel` tersebut.
- Penilaian UTSP berdasarkan hasil perhitungan dari contoh soal dan `test case` lain.

## Soal 1

Pak Orkom ingin sebuah aplikasi penghitung sebuah determinan dari matrix ` g ` berukuran 3x3, tapi dia ingin proses perhitungan yang sangat cepat.
Oleh karena itu, dia ingin meminta anda untuk membuatkannya. Dan anda tahu bahwa dengan menggunakan bahasa `assembly`, proses akan
berlangsung sangat cepat. Bantu Pak Orkom untuk menyelesaikannya.

Matrix `g` memiliki indexing yang terdiri dari baris `i` dan kolom `j` yang dimulai dari `0`.

![alt tag](http://www.cmsc.uwa.edu.au/__data/assets/image/0010/760546/formula-1.gif)

Carilah determinan dari matrix g tersebut dan simpan di variabel ` res `

### `Hint`

Opsional, Anda boleh menggunakan algoritme lain.

Untuk mendapatkan alamat memory dari matrix berdasarkan index baris dan kolom, gunakan perhitungan berikut :
```bash
( ( i * banyak kolom ) + j ) * 4             ; banyak kolom dari matrix 3x3 = 3
```
Catatan : ketika mengakses alamat memory, rumus tersebut tidak bisa langsung digunakan ketika mengakses alamat.
Hitung terlebih dahulu, kemudian baru akses alamat memory nya.

Misal :
```bash
mov ebx, [g + eax]           ; eax adalah hasil perhitungan rumus diatas.
```

Selanjutnya, Anda buat sendiri ketentuan perpindahan index baris dan kolom sesuai dengan Sarrus Algorithm.



## Soal 2

Bu Arkom sedang menjalani psikotest dan dia dihadapkan pada soal mencari bilangan ke-`n` pada deret `fibonacci`. Untuk memudahkannya
menjawab, Bu Arkom membuat program pencarian tersebut dengan menggunakan bahasa `assembly`, tapi dia merasa kesulitan.
Bantulah Bu Arkom membuat program tersebut.

```bash
Misalkan n = 23 . F(n) = 28657
```

## Soal 3

Fulan, seorang mahasiswa penggemar bahasa `assembly`, ingin mengetahui berapakah IP yang ia dapat pada semester ini.
Semester ini ia mengambil 5 mata kuliah yang memiliki SKS nya masing-masing.
Data yang tersedia adalah nilai akhir mata dan SKS mata kuliah tersebut yang terdapat pada array `nilai` dan `sks`, seperti berikut :

`nilai` = {70, 40, 90, 55, 60}

`sks` = {3, 2, 4, 2, 3}


*Ketentuan Huruf Mutu dan Skor nya :*

4 : A >= 75

3 : 60 =< B < 75

2 : 45 =< C < 60

1 : 30 =< D < 45

0 : E < 30

Simpanlah nilai IP Semester Fulan pada variabel `ip` dengan skala `0 - 400` (karena kita belum membahas floating point).
Yang Disimpan adalah hasil bagi nya saja, sisa bagi diabaikan. Misal `234`.