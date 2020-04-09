---
title: R di Visual Studio Code
author: Andi
date: '2020-04-09'
slug: r-di-visual-studio-code
categories:
  - catatan
  - tutorial
tags:
  - rstats
  - tool
---

OK! Saya akui saya terlena dengan perbincangan tentang menggunakan editor VS Code dari Microsoft untuk bekerja dengan R, di twitter.

<blockquote class="twitter-tweet"><p lang="en" dir="ltr">👏VS <a href="https://twitter.com/code?ref_src=twsrc%5Etfw">@code</a> is now an amazing IDE for R<br><br>The latest improvements to the language server protocol implementation for <a href="https://twitter.com/hashtag/rstats?src=hash&amp;ref_src=twsrc%5Etfw">#rstats</a> offer code completion, go to definitions, info on hover and more. <br><br>I have not been this excited for new R developments in a while:<br>🔗<a href="https://t.co/hWMoLwOzi1">https://t.co/hWMoLwOzi1</a> <a href="https://t.co/X8S5xGffPM">pic.twitter.com/X8S5xGffPM</a></p>&mdash; Jozef Hajnala (@jozefhajnala) <a href="https://twitter.com/jozefhajnala/status/1204496900461912068?ref_src=twsrc%5Etfw">December 10, 2019</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

Berangkat dari tweet di atas, saya melakukan beberapa langkah instalasi di mesin linux saya untuk bisa ikutan dalam keseruan ini. Berikut...

## 1. Siapkan VS Code

Saya [unduh](https://code.visualstudio.com/Download) dan instal VS Code dulu tentunya. Instalasi di linux Ubuntu semudah mengerjakan skripsi: _copas ini saja!_ (ups)

Ganti bagian `~/Downloads/code_x.xx.x-xxxxxx_amd64.deb` dengan direktori tempat teman-teman menyimpan berkas `deb`-nya VS Code.

```{bash}
~$ sudo dpkg -i ~/Downloads/code_x.xx.x-xxxxxx_amd64.deb
```

Lalu, pergi ke menu, cari Visual Studio Code. Atau di terminal ketikkan `code`, enter.

## 2. Cari dan Instal Ekstensi R LSP Client

Cara instal:

- pergi ke bagian extension (nomor 1), 
- ketik "r lsp" di pencarian, 
- pilih **R LSP Client** yang dari REditorSupport (nomor 2), 
- lalu klik "Install".

![instal ekstensi R LSP](../post/2020-04-09-r-di-visual-studio-code_files/vscode-r-lsp-ext.png)

Ketika menginstal ternyata ada pesan error yang muncul:

![terjadi galat](/post/2020-04-09-r-di-visual-studio-code_files/without-languageserver.png)

Ini terjadi karena saya belum instal library `languageserver` untuk R. Itulah mengapa saya juga harus melakukan...

## 3. Instal library languageserver

Instalasinya bisa dari terminal linux, console R di terminal, console R di RStudio, atau terminal yang masuk ke console R dari VS Code.

Pilihan terakhir adalah yang saya pilih, biar gak kemana-mana lagi.

Di bagian bawah, ada TERMINAL, ketik R (tentu saja R sudah terinstal), kemudian ketikkan:

```{R}
install.packages("languageserver")
```

Tunggu sampai selesai instal, ada beberapa dependensinya juga yang diperlukan. Cas-cis-cus...

![instal pustaka languageserver](/post/2020-04-09-r-di-visual-studio-code_files/install-languageserver.png)


Terakhir, tutup dan buka kembali (restart) VS Code, biar afdhol.

## Taraaa....

_Autocompletion_ di VS Code untuk bahasa R.

![berhasil](/post/2020-04-09-r-di-visual-studio-code_files/r-vscode.gif)

Sekian dulu.