---
title: Branch untuk GH-Pages Databoard
author: Andi
date: '2020-04-26'
slug: branch-github-pages-databoard
categories:
  - catatan
tags:
  - github
  - blogging
  - website
---

Ini ditulis supaya kemudian hari kalau lupa bisa saya buka lagi. Singkat cerita, seperti ini:

<script async src="https://telegram.org/js/telegram-widget.js?8" data-telegram-post="GNURIndonesia/20654" data-width="100%"></script>

Apakah cukup jelas?

Langkah-langkah yang saya pakai secara teknis adalah seperti berikut:

**1. Clone repositori [databoard](https://github.com/akherlan/databoard)**, saya pakai tautan ssh karena nyaman dan aman.

```{bash}
$ mkdir databoard && cd databoard
$ git clone git@github.com:akherlan/databoard.git master
```
Tautan repo copas dari di bagian ini.

![](/post/2020-04-26-pakai-branch-untuk-github-pages_files/clone.png)

**2. Gandakan repositori hasil clone** ke lokal tadi menjadi direktori gh-pages.

```{bash}
$ cp master gh-pages
```

**3. Buat branch baru dengan nama "gh-pages"** dari repo di direktori gh-pages yang nanti akan diunggah ke upstream "origin/gh-pages".

```{bash}
$ cd gh-pages
$ git checkout origin/gh-pages -b gh-pages
```

Ini akan membuat pekerjaan yang dilakukan berpindah dan direkam ke branch "gh-pages" (bukan "master" lagi). Periksa dengan:

```{bash}
$ git branch
```

Tanda bintang ada di branch "gh-pages".

**4. Hapus branch "master" pada direktori gh-pages**

```{bash}
$ git branch -d master
```

**5. Hapus semua isi direktori gh-pages yang ada** KECUALI direktori **.git**

**6. Buat proyek laman web statis di direktori lain**

Saya membuat direktori rproj (sebagai _child_ dari direktori databoard) untuk membangun laman statis ini karena saya membuatnya menggunakan Rmarkdown.

![Jadi ada tiga child dir dalam parent dir databoard](/post/2020-04-26-pakai-branch-untuk-github-pages_files/dir.png)

**7. Copas hasil rendernya ke direktori gh-pages** yang tadi sudah kosong.

Mengapa tidak membuat alamat render langsung ditujukan ke direktori gh-pages? Karena nanti rekaman git-nya hilang. Rmarkdown akan mengganti/menimpa direktori gh-pages yang ada dan mengisinya dengan berkas-berkas baru hasil render.

Sebagai opsi, juga bisa gunakan version control pada direktori rproj ini, kalau diperlukan.

**8. Lakukan commit dan push dari branch "gh-pages"**

```{bash}
$ git add .
$ git commit -m "commit pertama untuk gh-pages"
$ git push origin gh-pages
```

Awas itu setelah `add` ada titiknya.

**9. Atur agar Github Pages dijalankan dari branch "gh-pages"**

![](/post/2020-04-26-pakai-branch-untuk-github-pages_files/gh-pages.png)

Sampai di sini, laman sudah online [di sini](https://akherlan.github.io/databoard).

Berikutnya, direktori master bisa saya hapus/buang saja karena selanjutnya repositori databoard branch "master" langsung terhubung dan dikelola melalui paket `pins` di R.

Saya melakukan ini setelah membaca dua panduan [ini(1)](https://gist.github.com/chrisjacob/833223) dan [ini(2)](https://gist.github.com/cobyism/4730490). Mana tau juga bisa bermanfaat buat teman-teman.

Terima kasih.