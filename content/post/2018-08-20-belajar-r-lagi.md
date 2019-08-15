---
title: Belajar R Lagi
author: andikh
date: '2018-08-20'
slug: belajar-r-lagi
categories: [belajar]
tags: ["rstats", "program"]
---

## Instal Program R

Pagi ini saya coba belajar pemrograman R lagi, tapi tanpa bantuan R Studio, murni hanya dengan terminal di laptop Ubuntu saya. Saya memberanikan diri, karena "kenapa harus takut?". Hal pertama yang saya lakukan tentu saya memasang paket program R melalui Synaptic Package Manager. Sebenarnya juga bisa dengan cara berikut:

``` sudo apt install r-base```

## Instal Library R

Hal pertama yang saya ingin lakukan setelah instal R adalah mengolah data hujan. Tetapi sebelum jauh ke sana, ada beberapa hal yang perlu saya lakukan. Pertama, menentukan lokasi penginstalan **R library**. Saya berpikir seperti itu sebab pada saat instalasi R library yang pertama, program R-nya protes karena tidak diizinkan menyimpan berkas-berkas library ke lokasi default, yaitu `/usr/local/lib/R/site-library`. Apakah harus pakai `sudo`? Saya kira, tentu saja, sebab itu direktori yang harus diakses dengan izin root. Saya tidak mau, saya cari cara di internet untuk tidak menginstal library di direktori "angker" itu.

Singkat cerita saya menemukan cara, beginilah caranya (dari R-cli interface):

```library.packages("gdata", lib="/tempat/saya/menyimpan/r/library/")```

Wah, senang. Saya berhasil menginstal library `gdata`.

## Mengganti Direktori Library

Setelah bisa mengkinstal library kemudian saya menjalankannya. Tapi ternyata tidak bisa! Muncul galat seperti ini:

```Error in library(gdata) : there is no package called ‘gdata’```

Saya pikir lagi. Mungkin saya harus memindahkan lokasi default library ke direktori tempat menginstal `gdata` tadi? Saya coba cari cara memindahkan direktori library dan saya menemukannya [di sini](https://stackoverflow.com/questions/2615128/where-does-r-store-packages). Maka yang saya lakukan adalah:

 ```.libPaths("/tempat/saya/menyimpan/r/library/")```
 
 Alhasil, ketika saya ketikkan perintah untuk menjalankan library `gdata` seperti berikut:

```library(gdata)```

saya mendapat deretan pesan yang menandakan saya telah sukses menjalankannya. Yeay!

Saya mencoba lagi menginstal library lain tanpa menyertakan `lib=` seperti sebelumnya

```library.packages("zoo")```

dan saya berhasil. Selanjutnya, saya harus lebih semangat melanjutkan olah data hujan.

Sampai jumpa!

*Catatan bahan-bahan: Ubuntu Bionic 18.04, R v3.4, terminal emulator*
