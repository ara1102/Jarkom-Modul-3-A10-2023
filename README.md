# Jarkom-Modul-3-A10-2023

## Anggota Kelompok

| NRP        | Name                        |
| ---------- | --------------------------- |
| 5025211081 | Gabriella Natasya Br Ginting|
| 5025211102 | Adhira Riyanti Amanda       |

### Daftar Isi
- [Soal 1](#soal-1)
- [Soal 2](#soal-2)
- [Soal 3](#soal-3)
- [Soal 4](#soal-4)
- [Soal 5](#soal-5)
- [Soal 6](#soal-6)
- [Soal 7](#soal-7)
- [Soal 8](#soal-8)
- [Soal 9](#soal-9)
- [Soal 10](#soal-10)
- [Soal 11](#soal-11)
- [Soal 12](#soal-12)
- [Soal 13](#soal-13)
- [Soal 14](#soal-14)
- [Soal 15](#soal-15)
- [Soal 16](#soal-16)
- [Soal 17](#soal-17)
- [Soal 18](#soal-18)
- [Soal 19](#soal-19)
- [Soal 20](#soal-20)

### Topologi dan Ketentuan Node
![Topologi](/images/topologi/topologimodul3.png)

| Node               | Kategori          | Image Docker                        | Konfigurasi IP | 
|--------------------|-------------------|-------------------------------------|-----------------| 
| Aura               | Router (DHCP Relay)| danielcristh0/debian-buster:1.1     | Dynamic         | 
| Himmel             | DHCP Server       | danielcristh0/debian-buster:1.1     | Static          | 
| Heiter             | DNS Server        | danielcristh0/debian-buster:1.1     | Static          | 
| Denken             | Database Server   | danielcristh0/debian-buster:1.1     | Static          | 
| Eisen              | Load Balancer     | danielcristh0/debian-buster:1.1     | Static          | 
| Frieren            | Laravel Worker    | danielcristh0/debian-buster:1.1     | Static          | 
| Flamme             | Laravel Worker    | danielcristh0/debian-buster:1.1     | Static          | 
| Fern               | Laravel Worker    | danielcristh0/debian-buster:1.1     | Static          | 
| Lawine             | PHP Worker        | danielcristh0/debian-buster:1.1     | Static          | 
| Linie              | PHP Worker        | danielcristh0/debian-buster:1.1     | Static          | 
| Lugner             | PHP Worker        | danielcristh0/debian-buster:1.1     | Static          | 
| Revolte            | Client            | danielcristh0/debian-buster:1.1     | Dynamic         | 
| Richter            | Client            | danielcristh0/debian-buster:1.1     | Dynamic         | 
| Sein               | Client            | danielcristh0/debian-buster:1.1     | Dynamic         | 
| Stark              | Client            | danielcristh0/debian-buster:1.1     | Dynamic         |

### Konfigurasi Node
- Aura (Router / DHCP Relay)

```
auto eth0
iface eth0 inet dhcp

auto eth1
iface eth1 inet static
	address 10.4.1.0
	netmask 255.255.255.0

auto eth2
iface eth2 inet static
	address 10.4.2.0
	netmask 255.255.255.0

auto eth3
iface eth3 inet static
	address 10.4.3.0
	netmask 255.255.255.0

auto eth4
iface eth4 inet static
	address 10.4.4.0
	netmask 255.255.255.0
```

- Himmel (DHCP Server)
```
auto eth0
iface eth0 inet static
	address 10.4.1.1
	netmask 255.255.255.0
	gateway 10.4.1.0
```

- Heiter (DNS Server)
```
auto eth0
iface eth0 inet static
	address 10.4.1.2
	netmask 255.255.255.0
	gateway 10.4.1.0
```

- Denken (Database Server)
```
auto eth0
iface eth0 inet static
	address 10.4.2.1
netmask 255.255.255.0
gateway 10.4.2.0
```

- Eisen (Load Balancer)
```
auto eth0
iface eth0 inet static
	address 10.4.2.2
	netmask 255.255.255.0
	gateway 10.4.2.0
```

- Lugner (PHP Worker)
```
auto eth0
iface eth0 inet static
	address 10.4.3.1
	netmask 255.255.255.0
	gateway 10.4.3.0	
```
- Linie (PHP Worker)
```
auto eth0
iface eth0 inet static
	address 10.4.3.2
	netmask 255.255.255.0
	gateway 10.4.3.0
```

- Lawine (PHP Worker)
```
auto eth0
iface eth0 inet static
	address 10.4.3.3
	netmask 255.255.255.0
	gateway 10.4.3.0
```

- Richter (Client)
```
auto eth0
iface eth0 inet static
	address 10.4.3.4
	netmask 255.255.255.0
	gateway 10.4.3.0
```
- Revolte (Client)
```
auto eth0
iface eth0 inet static
	address 10.4.3.5
	netmask 255.255.255.0
	gateway 10.4.3.0
```

- Sein (Client)
```
auto eth0
iface eth0 inet static
	address 10.4.4.5
	netmask 255.255.255.0
	gateway 10.4.4.0
```
- Stark (Client)
```
auto eth0
iface eth0 inet static
	address 10.4.4.4
	netmask 255.255.255.0
	gateway 10.4.4.0
```

- Frieren (Laravel Worker)
```
auto eth0
iface eth0 inet static
	address 10.4.4.3
	netmask 255.255.255.0
	gateway 10.4.4.0
```

- Flamme (Laravel Worker)
```
auto eth0
iface eth0 inet static
	address 10.4.4.2
	netmask 255.255.255.0
	gateway 10.4.4.0
```

- Fern (Laravel Worker)
```
auto eth0
iface eth0 inet static
	address 10.4.4.1
	netmask 255.255.255.0
	gateway 10.4.4.0
```


### Soal 1
Setelah mengalahkan Demon King, perjalanan berlanjut. Kali ini, kalian diminta untuk melakukan register domain berupa riegel.canyon.yyy.com untuk worker Laravel dan granz.channel.yyy.com untuk worker PHP mengarah pada worker yang memiliki IP [prefix IP].x.1.

Lakukan konfigurasi sesuai dengan peta yang sudah diberikan.

- **.bashrc Aura (Router)**
    ```
    iptables -t nat -A POSTROUTING -o eth0 -j MASQUERADE -s 10.4.0.0/16
    ```

- **.bashrc Heiter (DNS Server)**
    ```
    echo nameserver 192.168.122.1 > /etc/resolv.conf
    apt-get update
    apt-get install bind9 -y
    ```

- **dns.sh Heiter (DNS Server)**
    ```
    echo 'zone "riegel.canyon.A10.com" {
            type master;
            file "/etc/bind/jarkom/riegel.canyon.A10.com";
    };
    zone "granz.channel.A10.com" {
            type master;
            file "/etc/bind/jarkom/granz.channel.A10.com";
    };
    ' > /etc/bind/named.conf.local

    mkdir /etc/bind/jarkom
    cp /etc/bind/db.local /etc/bind/jarkom/riegel.canyon.A10.com
    cp /etc/bind/db.local /etc/bind/jarkom/granz.channel.A10.com

    echo '
    ;
    ; BIND data file for local loopback interface
    ;
    $TTL    604800
    @       IN      SOA    riegel.canyon.A10.com. root.riegel.canyon.A10.com. (
                            2023111401                                                                            ; Serial
                            604800         ; Refresh
                            86400         ; Retry
                            2419200         ; Expire
                            604800 )       ; Negative Cache TTL
    ;
    @       IN      NS      riegel.canyon.A10.com.
    @       IN      A       10.4.4.1	;IP Fern
    www   IN   CNAME  riegel.canyon.A10.com.' > /etc/bind/jarkom/riegel.canyon.A10.com

    echo '
    ;
    ; BIND data file for local loopback interface
    ;
    $TTL    604800
    @       IN      SOA    granz.channel.A10.com. root.granz.channel.A10.com. (
                            2023111401      ; Serial
                            604800         ; Refresh
                            86400         ; Retry
                            2419200         ; Expire
                            604800 )       ; Negative Cache TTL
    ;
    @       IN      NS     granz.channel.A10.com.
    @       IN      A       10.4.3.1	;IP Lugner
    www    IN      CNAME granz.channel.A10.com ' > /etc/bind/jarkom/granz.channel.A10.com

    echo 'options {
        directory "/var/cache/bind";

        forwarders {
                192.168.122.1;
        };

        // dnssec-validation auto;
        allow-query{any;};
        auth-nxdomain no;    # conform to RFC1035
        listen-on-v6 { any; };
    }; ' >/etc/bind/named.conf.options

    service bind9 restart
    ```

### Soal 2
Client yang melalui Switch3 mendapatkan range IP dari [prefix IP].3.16 - [prefix IP].3.32 dan [prefix IP].3.64 - [prefix IP].3.80

### Soal 3
Client yang melalui Switch4 mendapatkan range IP dari [prefix IP].4.12 - [prefix IP].4.20 dan [prefix IP].4.160 - [prefix IP].4.168

### Soal 4
Client mendapatkan DNS dari Heiter dan dapat terhubung dengan internet melalui DNS tersebut

### Soal 5
Lama waktu DHCP server meminjamkan alamat IP kepada Client yang melalui Switch3 selama 3 menit sedangkan pada client yang melalui Switch4 selama 12 menit. Dengan waktu maksimal dialokasikan untuk peminjaman alamat IP selama 96 menit

### Soal 6
Pada masing-masing worker PHP, lakukan konfigurasi virtual host untuk website berikut dengan menggunakan php 7.3.

### Soal 7
Kepala suku dari Bredt Region memberikan resource server sebagai berikut:
- Lawine, 4GB, 2vCPU, dan 80 GB SSD.
- Linie, 2GB, 2vCPU, dan 50 GB SSD.
- Lugner 1GB, 1vCPU, dan 25 GB SSD.
aturlah agar Eisen dapat bekerja dengan maksimal, lalu lakukan testing dengan 1000 request dan 100 request/second

### Soal 8
Karena diminta untuk menuliskan grimoire, buatlah analisis hasil testing dengan 200 request dan 10 request/second masing-masing algoritma Load Balancer dengan ketentuan sebagai berikut:
- Nama Algoritma Load Balancer
- Report hasil testing pada Apache Benchmark
- Grafik request per second untuk masing masing algoritma. 
- Analisis

### Soal 9
Dengan menggunakan algoritma Round Robin, lakukan testing dengan menggunakan 3 worker, 2 worker, dan 1 worker sebanyak 100 request dengan 10 request/second, kemudian tambahkan grafiknya pada grimoire.

### Soal 10
Selanjutnya coba tambahkan konfigurasi autentikasi di LB dengan dengan kombinasi username: “netics” dan password: “ajkyyy”, dengan yyy merupakan kode kelompok. Terakhir simpan file “htpasswd” nya di /etc/nginx/rahasisakita/

### Soal 11
Lalu buat untuk setiap request yang mengandung /its akan di proxy passing menuju halaman https://www.its.ac.id.

### Soal 12
Selanjutnya LB ini hanya boleh diakses oleh client dengan IP [Prefix IP].3.69, [Prefix IP].3.70, [Prefix IP].4.167, dan [Prefix IP].4.168.

### Soal 13
Semua data yang diperlukan, diatur pada Denken dan harus dapat diakses oleh Frieren, Flamme, dan Fern.

### Soal 14
Frieren, Flamme, dan Fern memiliki Riegel Channel sesuai dengan quest guide berikut. Jangan lupa melakukan instalasi PHP8.0 dan Composer

### Soal 15-17
Riegel Channel memiliki beberapa endpoint yang harus ditesting sebanyak 100 request dengan 10 request/second. Tambahkan response dan hasil testing pada grimoire.

### Soal 15
- POST /auth/register 

### Soal 16
- POST /auth/login

### Soal 17
- GET /me

### Soal 18
Untuk memastikan ketiganya bekerja sama secara adil untuk mengatur Riegel Channel maka implementasikan Proxy Bind pada Eisen untuk mengaitkan IP dari Frieren, Flamme, dan Fern.

### Soal 19
Untuk meningkatkan performa dari Worker, coba implementasikan PHP-FPM pada Frieren, Flamme, dan Fern. Untuk testing kinerja naikkan 
- pm.max_children
- pm.start_servers
- pm.min_spare_servers
- pm.max_spare_servers
sebanyak tiga percobaan dan lakukan testing sebanyak 100 request dengan 10 request/second kemudian berikan hasil analisisnya pada Grimoire.

### Soal 20
Nampaknya hanya menggunakan PHP-FPM tidak cukup untuk meningkatkan performa dari worker maka implementasikan Least-Conn pada Eisen. Untuk testing kinerja dari worker tersebut dilakukan sebanyak 100 request dengan 10 request/second.

