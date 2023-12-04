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


## Routing

- Aura

![image](https://github.com/nabilaaidah/Jarkom-Modul-4-A02-2023/assets/110476969/b3832643-8ee3-49ce-8480-b531080cfe57)

- Frieren

![image](https://github.com/nabilaaidah/Jarkom-Modul-4-A02-2023/assets/110476969/0b1de1bf-080f-4b5e-ac54-ca1cecb0cf62)

- Flamme

![image](https://github.com/nabilaaidah/Jarkom-Modul-4-A02-2023/assets/110476969/6d7ba129-d22f-48c8-9b13-c702ade464ae)

- Fern

![image](https://github.com/nabilaaidah/Jarkom-Modul-4-A02-2023/assets/110476969/9d72a8e4-d67f-4627-bf14-5cac52df4f6b)

- Himmel

![image](https://github.com/nabilaaidah/Jarkom-Modul-4-A02-2023/assets/110476969/79bb6f4e-b83f-4300-8dd0-384910a45e9b)

- Denken

![image](https://github.com/nabilaaidah/Jarkom-Modul-4-A02-2023/assets/110476969/e5d363b8-9aba-48ef-8ab7-3dfea1c12e8c)

- Lugner

![image](https://github.com/nabilaaidah/Jarkom-Modul-4-A02-2023/assets/110476969/4a7e0e23-d3a3-4a4b-83e2-dbb21fc7598e)

- Linie

![image](https://github.com/nabilaaidah/Jarkom-Modul-4-A02-2023/assets/110476969/01ae6bd4-6db0-425f-b518-9afdf4c8ca13)

- Lawine

![image](https://github.com/nabilaaidah/Jarkom-Modul-4-A02-2023/assets/110476969/257d6191-ee02-421b-9a62-79565a47a286)

- Heiter

![image](https://github.com/nabilaaidah/Jarkom-Modul-4-A02-2023/assets/110476969/66d43e3b-a8a5-4e20-aab6-3e0ecae93f86)



# CIDR

CIDR, atau Classless Inter-Domain Routing, adalah metode pengalamatan IP yang memungkinkan pengguna untuk mengelompokkan alamat IP ke dalam blok-blok yang lebih besar atau lebih kecil daripada batasan tradisional kelas (Classful addressing). Dalam CIDR, subnetting dilakukan secara fleksibel tanpa harus mematuhi batasan kelas A, B, atau C, sehingga memungkinkan alokasi alamat IP yang lebih efisien. Notasi CIDR menggunakan format "IP address/prefix length," di mana "prefix length" menunjukkan jumlah bit yang digunakan untuk mengidentifikasi jaringan, memungkinkan adanya blok-blok alamat dengan panjang yang bervariasi. CIDR membantu mengatasi masalah habisnya alamat IPv4 dengan memungkinkan penggunaan lebih efisien dan fleksibel dari sumber daya alamat IP yang terbatas.

## Topologi

Berikut merupakan topologi yang digunakan dalam metode CIDR dengan CPT:

![image](https://github.com/nabilaaidah/Jarkom-Modul-4-A02-2023/assets/110476969/4acbae0d-c86a-4526-88a1-89b9445708aa)

## Penggabungan IP

Berikut merupakan penggabungan IP yang dilakukan dalam metode CIDR:

1. Awal Tree

![image](https://github.com/nabilaaidah/Jarkom-Modul-4-A02-2023/assets/110476969/09d6f9d9-6a91-4a1e-a0dc-da17fd1651ef)

2. Penggabungan 1

![image](https://github.com/nabilaaidah/Jarkom-Modul-4-A02-2023/assets/110476969/5e937d9a-edc2-4c29-894e-35988c784c16)

![image](https://github.com/nabilaaidah/Jarkom-Modul-4-A02-2023/assets/110476969/65638906-330a-473d-8afc-f780c41a4bee)

3. Penggabungan 2

![image](https://github.com/nabilaaidah/Jarkom-Modul-4-A02-2023/assets/110476969/0407957b-095a-4766-b7aa-bffa487aff54)

![image](https://github.com/nabilaaidah/Jarkom-Modul-4-A02-2023/assets/110476969/eeacce4f-d4e2-45b1-8202-9a8ba16b5976)

4. Penggabungan 3

![image](https://github.com/nabilaaidah/Jarkom-Modul-4-A02-2023/assets/110476969/9967a5d4-d5ef-4b6a-8f6a-9a8a6e3ecfa6)

![image](https://github.com/nabilaaidah/Jarkom-Modul-4-A02-2023/assets/110476969/9708ecda-57ca-40c8-b015-9eebedec1161)

5. Penggabungan 4

![image](https://github.com/nabilaaidah/Jarkom-Modul-4-A02-2023/assets/110476969/714ead90-d94b-4aef-84a1-d611bc880668)

![image](https://github.com/nabilaaidah/Jarkom-Modul-4-A02-2023/assets/110476969/5501004a-a76f-4334-9353-7916eb54a836)

6. Penggabungan 5



## Tree

Berikut merupakan tree yang digunakan dalam metode CIDR:

![image](https://github.com/nabilaaidah/Jarkom-Modul-4-A02-2023/assets/110476969/b53b7d14-3e73-4220-8b82-56488977a85f)

## Pembagian IP

Berikut pembagian IP yang digunakan pada metode VLSM. Namun, dikarenakan subnet yang digunakan memiliki length `/14` sehingga akan terdapat beberapa node yang dimulai tidak dengan prefix `10.0`

![image](https://github.com/nabilaaidah/Jarkom-Modul-4-A02-2023/assets/110476969/f0d3db83-c392-4969-8d3e-f17cdfbcf5e0)
