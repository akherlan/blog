---
title: Memindahkan Repo Git
author: andi
date: '2020-04-05'
slug: memindahkan-repo-git
categories:
  - catatan
tags:
  - git
---

Tempo hari saya memesan mesin baru. _Secondhand_. Masih bagus. Dan impian dari lama. Walau saya harus lakukan _tweak_, untuk pahami beberapa hal, demi optimasi kerja mesin. Tapi ini kita ceritakan nanti saja.

Hal pertama yang saya pikirkan adalah memindahkan semua proyek kerja yang dilakukan dengan version control git.

Pertama kali mencoba copas langsung, dari mesin komputer lama saya langsung berhadapan dengan galat (_error_). Direktori tempat menyimpan proyek dengan git gagal di-_push_ ke awan setelah dilakukan _commit_.

Remote dilakukan melalui ssh untuk tampil _online_, bukan tautan Github https saja.

Usul punya asal, galat terjadi karena kunci yang saya pakai di mesin baru tidak cocok dengan informasi yang disimpan dalam repositori ini, karena kunci di mesin lama tentu berbeda.

Jadi bagaimana mengatasi masalah ini? Apakah haru _clone_ repositori yang sudah _online_ di Github? Tidak perlu kisanak. Itu besar sekali. Habis kuota tathering nanti.

Cara yang saya gunakan untuk mengatasi masalah ini adalah begini:

1. Copy folder/direktori repositori dari mesin lama.
2. Paste ke tempat yang diinginkan di mesin yang baru.
3. Sebelum mulai bekerja dengan repositori ini, lakukan hal berikut:

```{bash}
$ git remote update
```

Ternyata sesimpel itu.

Setelah ini saya bisa lagi pake ssh untuk remote git dari mesin komputer baru. Tentu setelah menambah konfigurasi ssh baru di pengaturan Github.

Thanks.

Kemarin hari yang melelahkan, sekarang saatnya bersantai sejenak. Sruput kopi, bos!