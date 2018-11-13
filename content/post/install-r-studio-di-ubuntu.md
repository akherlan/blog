+++
date = "2018-09-18T12:00:00-00:00"
title = "Menginstall R Studio Di Ubuntu"

+++

Malam ini saya coba menginstall R Studio, yaitu IDE untuk pemrograman R. Ternyata R Studio di GNU/Linux lebih ringan (jauh) dibandingkan dengan R Studio di Windows. Atau mungkin itu cuma perasaan saya saja. Tapi tidak, kelihatannya itu benar. Nanti, kita bisa cari informasi tentang itu. Saat ini saya ingin menuliskan tata cara menginstall R Studio di **Ubuntu Bionic** saya.

Pertama yang saya lakukan adalah mengunduh paket `*.deb` R Studio dari [laman resminya](https://www.rstudio.com/products/rstudio/download/).

Kedua, saya coba install langsung melalui **gdebi**, tapi ternyata dia minta dependensi (paket pendukung tambahan) yaitu `libgstreamer0.10-0`.

Karena gagal menginstall, jadi saya cari paket yang dibutuhkan itu dari internet, sambil cari cara-cara bagaimana menghadapi permasalahan ini dengan benar. Solusinya ditemukan [di forum biasa](http://stackoverflow.com/questions/40413323/ddg#40938717). Biar saya jabarkan saja sekalian dalam tulisan ini:

Install paket dependensi yang dibutuhkan: `libgstreamer0.10-0` dan `libgstreamer-plugins-base0.10-0`, diunduh dari laman [berikut](https://pkgs.org/download/libgstreamer0.10-0) dan laman [berikut juga](https://pkgs.org/download/libgstreamer-plugins-base0.10-0), sesuaikan dengan kebutuhan (saya pakai paket unutk Ubuntu Xenial yang i386 karena pakai Ubuntu 32bit).

```cd Downloads
sudo dpkg -i libgstreamer0.10-0_danseterusnya.deb
sudo dpkg -i libgstreamer-plugins-base0.10-0_danseterusnya.deb
```

Beri tanda pada paket `libgstreamer0` yang terinstall agar tidak "diganggu-gugat"

```sudo apt-mark hold libgstreamer0.10-0
sudo apt-mark hold libgstreamer-plugins-base0.10-0
```

Barulah install paket `.deb` R Studio-nya:

```sudo gdebi rstudio-danseterusnya.deb```

R Studio sudah bisa dipakai. Sekian.
