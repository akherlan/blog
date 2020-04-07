---
title: Lenovo ThinkPad X240 dengan Xubuntu
author: Andi
date: '2020-04-07'
slug: lenovo-thinkpad-x240
categories:
  - catatan
tags:
  - blogging
---

<img src="/post/2020-04-07-lenovo-thinkpad-x240_files/logo_thinkpad.jpg" alt="IBM ThinkPad" width="100%"/>

Pekan lalu saya memesan mesin baru, Lenovo ThinkPad X240. _Secondhand_. Harganya lumayan miring juga dengan spesifikasi nggak jelek-jelek amat:

- Model prosesor Intel® Core™ i5-4300U CPU @ 1.90GHz (artinya multi CPU generasi 4)
- Arsitektur prosesor `x86_64` (artinya dari Intel)
- Memori HDD SATA 500GB (versi lain ada yang pakai SSD)
- Memori RAM 4GB (sebetulnya saya mau pesan yang 8GB)
- VGA Intel Haswell-ULT Integrated Graphics Controller
- Adaptor WiFi
- Adaptor Bluetooth
- Ukuran layar `361x203 mm` (12 inci) dengan resolusi sampai `1366x768 pixel`
- Beratnya nggak tau pasti karena belum ditimbang, tapi termasuk ringan dibanding laptop lama
- Port-nya banyak dan lengkap sampai ada yang saya belum tau fungsinya.

## Kondisi fisik

Kondisinya secara fisik masih bagus. Cuma engsel kanan yang bunyi _krek-krek_ saat dibuka-tutup. Juga baterainya agak sedikit longgar/goyang. Tapi jarang ada kelihatan lecet.

<img src="/post/2020-04-07-lenovo-thinkpad-x240_files/bagian-atas.jpg" alt="Bagian atas" width="100%"/>

## Kelebihan

- Baterainya ada dua, yang tertanam dengan yang bisa dilepas dari luar. Jadi bisa tahan lama saat dibawa bepergian. Sehari-semalam dipakai biasanya cuma saya isi daya 1x.
- _Gesture allowed_ pada TrackPad, ketika dicoba di Windows 10 (OS bawaan toko) dan Xubuntu 18.04, tidak ada bedanya, sama-sama yahood!
- TrackPoint, entah ini kelebihan atau bukan karena sebenarnya jarang saya pakai, ini juga berfungsi dengan baik di Xubuntu 18.04.

<img src="/post/2020-04-07-lenovo-thinkpad-x240_files/trackpoint.jpg" alt="TrackPoint" width="100%"/>

## Kebiasaan

Saya agak _kagok_ dengan papan ketiknya karena belum terbiasa. Bukan ketika mengetik huruf dan angka, tapi ketika menggunakan tombol-tombol seperti:

- `Ctrl` kiri, karena letaknya di posisi kedua dari pojok kiri bawah. Biasanya di laptop lama letak tombol `Ctrl` kiri berada di paling pojok kiri. Jadi sangat mudah ditemukan pakai kelingking kiri. Sekarang saya harus biasakan pakai jari manis.
- `Shift` kiri, lagi-lagi kiri. ThinkPad X240 punya `Shift` kiri yang sangat pendek karena ada tombol karakter tambahan di sebelahnya, antara `Shift` dan `Z`, yaitu tombol `<` / `>` (`Shft + <`). Ddefault keyboard US. Padahal pada tombol ini tertulis `\` atau `|` (default mana ini?).
- Sebaliknya, `Shift` kanan sangat panjang. Mungkin saya harus mulai biasakan diri pakai `Shift` kanan saja.
- `Home` jadi di atas dekat `delete`, bukan di tepi bawah sekitar arrow.
- Apalagi `End`, menggunakannya jadi agak susah karena gabung dengan `Insert` (menekan `End` harus dengan `Fn + Insert`).
- `Enter` (`return`) yang sedikit berbeda bentuknya, walaupun tetap masih lebar, tapi ramping.
- Dan tombol lain yang tertulis berbeda antara teks di stiker dengan yang muncul setelah ditekan (default US). Saya kurang tahu ini stiker default negara mana.
  - `@` tertulis `"` pada tombol numerik `2 + Shift`
  - `#` tertulis `£` pada tombol numerik `3 + Shift`
  - `"` tertulis `@` pata tombol `' + Shift`, sekitar `Enter`

| Tombol 	| +Shift 	| Muncul 	| +Shift 	|             Letak             	|
|:------:	|:------:	|:------:	|:------:	|:-----------------------------:	|
|    \   	|   \|   	|    <   	|    >   	|    di antara `Shift` dan `Z`   	|
|    ~   	|    #   	|    \   	|   \|   	| di samping `Enter` (`Return`) 	|
|        	|        	|        	|        	|                               	|

<img src="/post/2020-04-07-lenovo-thinkpad-x240_files/Fn+Ctrl.jpg" alt="Fn, Ctrl" width="100%"/>

Selain itu malah jadi sangat nyaman:

- `PgUp` dan `PgDn` yang dekat dengan arrow, memudahkan saat membaca dan skrol halaman.
- `Alt` kanan, `PrtSc`, dan `Ctrl` kanan yang berdekatan sehingga mudah untuk ambil tangkapan layar. Saya terbiasa dengan `shortcut` kombinasi tombol-tombol ini.

<img src="/post/2020-04-07-lenovo-thinkpad-x240_files/arrow.jpg" alt="Arrow, PgUp, PgDn" width="100%"/>

<img src="/post/2020-04-07-lenovo-thinkpad-x240_files/ptscn.jpg" alt="Tombol-tombol shortcut tangkapan layar" width="100%"/>

## Informasi Hardware

### Prosesor & memori

```{bash}
~$ cat /proc/cpuinfo
~$ lscpu
```

### Audio & monitor

```{bash}
~$ xdpyinfo | grep "dimensions:"
```

```
dimensions:    1366x768 pixels (361x203 millimeters)
```

```{bash}
~$ lspci -v | grep "VGA" -A 12
```

```
00:02.0 VGA compatible controller: Intel Corporation Haswell-ULT Integrated Graphics Controller (rev 0b) (prog-if 00 [VGA controller])
	Subsystem: Lenovo ThinkPad X240
	Flags: bus master, fast devsel, latency 0, IRQ 48
	Memory at f0000000 (64-bit, non-prefetchable) [size=4M]
	Memory at e0000000 (64-bit, prefetchable) [size=256M]
	I/O ports at 3000 [size=64]
	[virtual] Expansion ROM at 000c0000 [disabled] [size=128K]
	Capabilities: <access denied>
	Kernel driver in use: i915
	Kernel modules: i915

00:03.0 Audio device: Intel Corporation Haswell-ULT HD Audio Controller (rev 0b)
	Subsystem: Lenovo ThinkPad X240
```

Perangkat lainnya...

```{bash}
~$ lspci
```

```
00:00.0 Host bridge: Intel Corporation Haswell-ULT DRAM Controller (rev 0b)
00:02.0 VGA compatible controller: Intel Corporation Haswell-ULT Integrated Graphics Controller (rev 0b)
00:03.0 Audio device: Intel Corporation Haswell-ULT HD Audio Controller (rev 0b)
00:14.0 USB controller: Intel Corporation 8 Series USB xHCI HC (rev 04)
00:16.0 Communication controller: Intel Corporation 8 Series HECI #0 (rev 04)
00:16.3 Serial controller: Intel Corporation 8 Series HECI KT (rev 04)
00:19.0 Ethernet controller: Intel Corporation Ethernet Connection I218-LM (rev 04)
00:1b.0 Audio device: Intel Corporation 8 Series HD Audio Controller (rev 04)
00:1c.0 PCI bridge: Intel Corporation 8 Series PCI Express Root Port 6 (rev e4)
00:1c.1 PCI bridge: Intel Corporation 8 Series PCI Express Root Port 3 (rev e4)
00:1d.0 USB controller: Intel Corporation 8 Series USB EHCI #1 (rev 04)
00:1f.0 ISA bridge: Intel Corporation 8 Series LPC Controller (rev 04)
00:1f.2 SATA controller: Intel Corporation 8 Series SATA Controller 1 [AHCI mode] (rev 04)
00:1f.3 SMBus: Intel Corporation 8 Series SMBus Controller (rev 04)
02:00.0 Unassigned class [ff00]: Realtek Semiconductor Co., Ltd. RTS5227 PCI Express Card Reader (rev 01)
03:00.0 Network controller: Intel Corporation Wireless 7260 (rev 83)
```

Yaa... Begitulah...