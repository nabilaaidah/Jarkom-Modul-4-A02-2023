# Jarkom-Modul-4-A02-2023

<table>
    <tr>
        <th colspan=2> Kelompok A02 </th>
    </tr>
    <tr>
        <th>NRP</th>
        <th>Nama Anggota</th>
    </tr>
    <tr>
        <td>5025211032</td>
        <td>Nabila A'idah Diani</td>
    </tr>
</table>


# Topologi

Berikut merupakan topologi yang digunakan pada praktikum modul 4:

![image](https://github.com/nabilaaidah/Jarkom-Modul-4-A02-2023/assets/110476969/11c2e922-b993-46d6-a916-484b7049dbde)


# Rute

Berikut merupakan rute subnet yang digunakan pada praktikum modul 4:

![image](https://github.com/nabilaaidah/Jarkom-Modul-4-A02-2023/assets/110476969/98c66028-a54c-4741-a1b8-f2ef5ac36820)


# Prefix IP

Prefix IP yang digunakan pada kelompok ini adalah `10.0.x.x`


# VLSM

Variable Length Subnet Mask (VLSM) adalah teknik pengalamatan IP yang memungkinkan pengguna untuk menggunakan subnet dengan panjang yang bervariasi dalam jaringan yang sama. Dalam VLSM, subnetting dilakukan dengan memberikan panjang subnet yang berbeda-beda pada setiap area atau subarea jaringan, sehingga memungkinkan pemanfaatan alamat IP secara efisien. Dengan menggunakan VLSM, administrator jaringan dapat mengalokasikan jumlah alamat IP yang sesuai dengan kebutuhan setiap subnet, menghindari pemborosan alamat IP dan meningkatkan efisiensi penggunaan sumber daya jaringan. Teknik ini sangat berguna dalam desain jaringan yang kompleks dan memungkinkan adaptasi yang lebih baik terhadap pertumbuhan atau perubahan kebutuhan jaringan.

## Topologi

Berikut merupakan topologi yang digunakan dalam metode VLSM dengan GNS3:

![image](https://github.com/nabilaaidah/Jarkom-Modul-4-A02-2023/assets/110476969/623b28aa-3964-4e0d-aeff-04d325dd9ba8)


## Tree

Berikut merupakan tree yang digunakan dalam metode VLSM:

![image](https://github.com/nabilaaidah/Jarkom-Modul-4-A02-2023/assets/110476969/ca95fe66-8cae-4475-9d73-747ac9c344d7)


## Pembagian IP

Berikut pembagian IP yang digunakan pada metode VLSM:

![image](https://github.com/nabilaaidah/Jarkom-Modul-4-A02-2023/assets/110476969/45209a63-fa5a-436d-bddd-c26b5d69ab82)


## Konfigurasi Network

- Aura
```
auto eth0
iface eth0 inet dhcp
up iptables -t nat -A POSTROUTING -o eth0 -j MASQUERADE -s 10.0.0.0/16

auto eth1
iface eth1 inet static
	address 10.0.0.1
	netmask 255.255.255.252

auto eth2
iface eth2 inet static
	address 10.0.0.21
	netmask 255.255.255.252

auto eth3
iface eth3 inet static
	address 10.0.0.18
	netmask 255.255.255.252
```

- Frieren
```
auto eth0
iface eth0 inet static
	address 10.0.0.2
	netmask 255.255.255.252

auto eth1
iface eth1 inet static
	address 10.0.0.161
	netmask 255.255.255.224

auto eth2
iface eth2 inet static
	address 10.0.0.5
	netmask 255.255.255.252
```

- Lake Korridor (24 Host)
```
auto eth0
iface eth0 inet static
	address 10.0.0.162
	netmask 255.255.255.224
	gateway 10.0.0.161
```

- Flamme
```
auto eth0
iface eth0 inet static
	address 10.0.0.6
	netmask 255.255.255.252

auto eth1
iface eth1 inet static
	address 10.0.0.9
	netmask 255.255.255.252

auto eth2
iface eth2 inet static
	address 10.0.12.1
	netmask 255.255.252.0

auto eth3
iface eth3 inet static
	address 10.0.0.13
	netmask 255.255.255.252
```

- Fern
```
auto eth0
iface eth0 inet static
	address 10.0.0.10
	netmask 255.255.255.252

auto eth1
iface eth1 inet static
	address 10.0.24.1
	netmask 255.255.248.0
```

- Laub Hills (397 Host)
```
auto eth0
iface eth0 inet static
	address 10.0.24.2
	netmask 255.255.248.0
	gateway 10.0.24.1
```

- Appetit Region (625 Host)
```
auto eth0
iface eth0 inet static
	address 10.0.24.3
	netmask 255.255.248.0
	gateway 10.0.24.1
```

- Rohr Road (1000 Host)
```
auto eth0
iface eth0 inet static
	address 10.0.12.2
	netmask 255.255.252.0
	gateway 10.0.12.1
```

- Himmel
```
auto eth0
iface eth0 inet static
	address 10.0.0.14
	netmask 255.255.255.252

auto eth1
iface eth1 inet static
	address 10.0.0.49
	netmask 255.255.255.248
```

- Schwer Moutains (5 Host)
```
auto eth0
iface eth0 inet static
	address 10.0.0.50
	netmask 255.255.255.248
	gateway 10.0.0.49
```

- Denken
```
auto eth0
iface eth0 inet static
	address 10.0.0.17
	netmask 255.255.255.252

auto eth1
iface eth1 inet static
	address 10.0.8.1
	netmask 255.255.255.0
```

- Royal Capital (63 Host)
```
auto eth0
iface eth0 inet static
	address 10.0.8.2
	netmask 255.255.255.0
	gateway 10.0.8.1
```

- Wille Region (63 Host)
```
auto eth0
iface eth0 inet static
	address 10.0.8.3
	netmask 255.255.255.0
	gateway 10.0.8.1
```

- Eisen
```
auto eth0
iface eth0 inet static
	address 10.0.0.22
	netmask 255.255.255.252

auto eth1
iface eth1 inet static
	address 10.0.0.57
	netmask 255.255.255.248

auto eth2
iface eth2 inet static
	address 10.0.0.33
	netmask 255.255.255.252

auto eth3
iface eth3 inet static
	address 10.0.0.29
	netmask 255.255.255.252

auto eth4
iface eth4 inet static
	address 10.0.0.25
	netmask 255.255.255.252
```

- Richter
```
auto eth0
iface eth0 inet static
	address 10.0.0.58
	netmask 255.255.255.248
	gateway 10.0.0.57
```

- Revolte
```
auto eth0
iface eth0 inet static
	address 10.0.0.59
	netmask 255.255.255.248
	gateway 10.0.0.57
```

- Stark
```
auto eth0
iface eth0 inet static
	address 10.0.0.26
	netmask 255.255.255.252
	gateway 10.0.0.25
```

- Lugner
```
auto eth0
iface eth0 inet static
	address 10.0.0.30
	netmask 255.255.255.252

auto eth1
iface eth1 inet static
	address 10.0.9.1
	netmask 255.255.255.0

auto eth2
iface eth2 inet static
	address 10.0.16.1
	netmask 255.255.252.0
```

- Turk Region (1000 Host)
```
auto eth0
iface eth0 inet static
	address 10.0.16.2
	netmask 255.255.252.0
	gateway 10.0.16.1
```

- Grobe Forest (250 Host)
```
auto eth0
iface eth0 inet static
	address 10.0.9.2
	netmask 255.255.255.0
	gateway 10.0.9.1
```

- Linie
```
auto eth0
iface eth0 inet static
	address 10.0.0.34
	netmask 255.255.255.252

auto eth1
iface eth1 inet static
	address 10.0.0.37
	netmask 255.255.255.252

auto eth2
iface eth2 inet static
	address 10.0.10.1
	netmask 255.255.254.0
```

- Granz Channel (254 Host)
```
auto eth0
iface eth0 inet static
	address 10.0.10.2
	netmask 255.255.254.0
	gateway 10.0.10.1
```

- Lawine
```
auto eth0
iface eth0 inet static
	address 10.0.0.38
	netmask 255.255.255.252

auto eth1
iface eth1 inet static
	address 10.0.2.193
	netmask 255.255.255.192
```

- Bredt Region (25 Host)
```
auto eth0
iface eth0 inet static
	address 10.0.2.194
	netmask 255.255.255.192
	gateway 10.0.2.193
```

- Heiter
```
auto eth0
iface eth0 inet static
	address 10.0.2.195
	netmask 255.255.255.192

auto eth1
iface eth1 inet static
	address 10.0.20.1
	netmask 255.255.252.0
```

- Riegel Canyon (510 Host)
```
auto eth0
iface eth0 inet static
	address 10.0.20.3
	netmask 255.255.252.0
	gateway 10.0.20.1
```

- Sein
```
auto eth0
iface eth0 inet static
	address 10.0.20.2
	netmask 255.255.252.0
	gateway 10.0.20.1
```
