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

#### Link GNS: https://drive.google.com/file/d/1bWBWaEl5MKJqcg_dxTJgQ0G1PVjeJcYh/view?usp=sharing

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

Agar client yang melalui Switch3 mendapatkan range IP dari yang diminta, maka kita dapat menambahkan konfigurasi:

**dhcp.sh Himmel (DHCP Server)**
```
echo 'INTERFACESv4="eth0"
INTERFACESv6=""' > /etc/default/isc-dhcp-server

echo 'subnet 10.4.1.0 netmask 255.255.255.0 {
}

subnet 10.4.2.0 netmask 255.255.255.0 {
}

subnet 10.4.3.0 netmask 255.255.255.0 {
    range 10.4.3.16 10.4.3.32;
    range 10.4.3.64 10.4.3.80;
    option routers 10.4.3.0;
}
```

### Soal 3
Client yang melalui Switch4 mendapatkan range IP dari [prefix IP].4.12 - [prefix IP].4.20 dan [prefix IP].4.160 - [prefix IP].4.168

Agar client yang melalui Switch4 mendapatkan range IP dari yang diminta, maka kita dapat menambahkan konfigurasi dari soal nomor 2:

**dhcp.sh Himmel (DHCP Server)**
```
echo 'INTERFACESv4="eth0"
INTERFACESv6=""' > /etc/default/isc-dhcp-server

echo 'subnet 10.4.1.0 netmask 255.255.255.0 {
}

subnet 10.4.2.0 netmask 255.255.255.0 {
}

subnet 10.4.3.0 netmask 255.255.255.0 {
    range 10.4.3.16 10.4.3.32;
    range 10.4.3.64 10.4.3.80;
    option routers 10.4.3.0;
}

subnet 10.4.4.0 netmask 255.255.255.0 {
    range 10.4.4.12 10.4.4.20;
    range 10.4.4.160 10.4.4.168;
    option routers 10.4.4.0;
}'>  /etc/dhcp/dhcpd.conf
```

### Soal 4
Client mendapatkan DNS dari Heiter dan dapat terhubung dengan internet melalui DNS tersebut

Agar client mendapatkan DNS dari Heiter, maka perlu menambahkan script pada script yang sudah dibuat pada soal 3. Tambahkan konfigurasi `option broadcast-address` dan `option domain-name-server`: 

**dhcp.sh Himmel (DHCP Server)**
```
subnet 10.4.3.0 netmask 255.255.255.0 {
    range 10.4.3.16 10.4.3.32;
    range 10.4.3.64 10.4.3.80;
    option routers 10.4.3.0;
    option broadcast-address 10.4.3.255;
    option domain-name-servers 10.4.1.2;
}

subnet 10.4.4.0 netmask 255.255.255.0 {
    range 10.4.4.12 10.4.4.20;
    range 10.4.4.160 10.4.4.168;
    option routers 10.4.4.0;
    option broadcast-address 10.4.4.255;
    option domain-name-servers 10.4.1.2;
}'>  /etc/dhcp/dhcpd.conf
```

lalu jalankan juga command berikut:

**dhcp.sh Himmel (DHCP Server)**
```
service isc-dhcp-server restart
service isc-dhcp-server status
```

Pada DHCP Relay, lakukan update dan install `isc-dhcp-relay`

**dhcp.sh Aura (DHCP Relay)**
```
apt-get update
apt-get install isc-dhcp-relay -y
```

Lalu, tambahkan juga konfigurasi berikut pada DHCP Relay:

**dhcp.sh Aura (DHCP Relay)**
```
apt-get update
apt-get install isc-dhcp-relay -y
service isc-dhcp-relay start

echo 'SERVERS="10.4.1.1"
INTERFACES="eth1 eth2 eth3 eth4"
OPTIONS=
' > /etc/default/isc-dhcp-relay
```

Uncomment juga bagian `net.ipv4.ip_forward=1` pada file `sysctl.conf

Hasil:

![Soal4](/images/Soal4/1.jpg)

### Soal 5
Lama waktu DHCP server meminjamkan alamat IP kepada Client yang melalui Switch3 selama 3 menit sedangkan pada client yang melalui Switch4 selama 12 menit. Dengan waktu maksimal dialokasikan untuk peminjaman alamat IP selama 96 menit

Sebelum menambahkan konfigurasi untuk meminjamkan alamat IP kepada Client kita perlu konversi waktu yang dibutuhkan kedalam satuan second:
- 3 m = 180 s
- 12 m = 720 s
- 96 m = 5760 s

Lalu tambahkan konfigurasi `default-lease-time` untuk mengatur waktu peminjaman alamat IP dan `max-lease-team` untuk meminjamkan alamat IP dengan waktu maksimal pada Client:

**dhcp.sh Himmel (DHCP Server)**
```
subnet 10.4.3.0 netmask 255.255.255.0 {
    range 10.4.3.16 10.4.3.32;
    range 10.4.3.64 10.4.3.80;
    option routers 10.4.3.0;
    option broadcast-address 10.4.3.255;
    option domain-name-servers 10.4.1.2;
    default-lease-time 180;
    max-lease-time 5760;
}

subnet 10.4.4.0 netmask 255.255.255.0 {
    range 10.4.4.12 10.4.4.20;
    range 10.4.4.160 10.4.4.168;
    option routers 10.4.4.0;
    option broadcast-address 10.4.4.255;
    option domain-name-servers 10.4.1.2;
    default-lease-time 720;
    max-lease-time 5760;
}'>  /etc/dhcp/dhcpd.conf
```

Hasil:

![Soal5](/images/Soal5/1.jpg)
![Soal5](/images/Soal5/2.jpg)

### Soal 6
Pada masing-masing worker PHP, lakukan konfigurasi virtual host untuk website berikut dengan menggunakan php 7.3.

Sebelum memulai melakukan konfigurasi, perlu untuk melakukan update dan install beberapa hal berikut:

**.bashrc Lawine, Linie, Lugner (PHP Worker)**
```
echo 'nameserver 10.4.1.2' > /etc/resolv.conf
apt-get update
apt-get install nginx -y
apt-get install wget -y
apt-get install unzip -y
apt-get install lynx -y
apt-get install htop -y
apt-get install apache2-utils -y
apt-get install php7.3-fpm php7.3-common php7.3-mysql php7.3-gmp php7.3-curl php7.3-intl php7.3-mbstring php7.3-xmlrpc php7.3-gd php7.3-xml php7.3-cli php7.3-zip -y

service nginx start
service php7.3-fpm start
```

Lakukan download dan unzip pada file yang sudah diberikan soal:

**unzip.sh Lawine, Linie, Lugner (PHP Worker)**
```
wget -O '/var/www/granz.channel.A10.com' 'https://drive.google.com/u/0/uc?id=1ViSkRq7SmwZgdK64eRbr5Fm1EGCTPrU1&export=download'
unzip -o /var/www/granz.channel.A10.com -d /var/www/
rm /var/www/granz.channel.A10.com
mv /var/www/modul-3 /var/www/granz.channel.A10.com
```

Lalu lakukan konfigurasi virtual host untuk website dengan menggunakan php 7.3, seperti berikut:

**nginx.sh Lawine, Linie, Lugner (PHP Worker)**
```
cp /etc/nginx/sites-available/default /etc/nginx/sites-available/granz.channel.A10.com
ln -s /etc/nginx/sites-available/granz.channel.A10.com /etc/nginx/sites-enabled/
rm /etc/nginx/sites-enabled/default

echo 'server {
    listen 80;
    server_name _;

    root /var/www/granz.channel.A10.com;
    index index.php index.html index.htm;

    location / {
        try_files $uri $uri/ /index.php?$query_string;
    }

    location ~ \.php$ {
        include snippets/fastcgi-php.conf;
        fastcgi_pass unix:/run/php/php7.3-fpm.sock; 
        fastcgi_param SCRIPT_FILENAME $document_root$fastcgi_script_name;
        include fastcgi_params;
    }
}' > /etc/nginx/sites-available/granz.channel.A10.com

service nginx restart
```

Hasil:

![Soal6](/images/Soal6/1.jpg)

### Soal 7
Kepala suku dari Bredt Region memberikan resource server sebagai berikut:
- Lawine, 4GB, 2vCPU, dan 80 GB SSD.
- Linie, 2GB, 2vCPU, dan 50 GB SSD.
- Lugner 1GB, 1vCPU, dan 25 GB SSD.
aturlah agar Eisen dapat bekerja dengan maksimal, lalu lakukan testing dengan 1000 request dan 100 request/second

Untuk memulai, lakukan update dan install beberapa hal terlebih dahulu:

**.bashrc Eisen (Load Balancer)**
```
echo 'nameserver 10.4.1.2' > /etc/resolv.conf
apt-get update
apt-get install apache2-utils -y
apt-get install nginx -y
apt-get install lynx -y

service nginx start
```

Pada DNS Server arahkan domain ke IP Load Balancer Eisen

**loadbalancer.sh Heiter (DNS Server)**
```
echo ';
; BIND data file for local loopback interface
;
$TTL    604800
@       IN      SOA     riegel.canyon.A10.com. root.riegel.canyon.A10.com. (
                        2023111401      ; Serial
                         604800         ; Refresh
                          86400         ; Retry
                        2419200         ; Expire
                         604800 )       ; Negative Cache TTL
;
@       IN      NS      riegel.canyon.A10.com.
@       IN      A       10.4.2.2     ; IP Eisen
www     IN      CNAME   riegel.canyon.A10.com.' > /etc/bind/jarkom/riegel.canyon.A10.com

echo '
; BIND data file for local loopback interface
;
$TTL    604800
@       IN      SOA     granz.channel.A10.com. root.granz.channel.A10.com. (
                        2023111401      ; Serial
                         604800         ; Refresh
                          86400         ; Retry
                        2419200         ; Expire
                         604800 )       ; Negative Cache TTL
;
@       IN      NS      granz.channel.A10.com.
@       IN      A       10.4.2.2     ; IP Eisen
www     IN      CNAME   granz.channel.A10.com.' > /etc/bind/jarkom/granz.channel.A10.com
```

Setelah itu, pada Load Balancer Eisen tambahkan konfigurasi nginx seperti berikut:

**nginx.sh Eisen (Load Balancer)**
```
cp /etc/nginx/sites-available/default /etc/nginx/sites-available/lb_php

echo ' upstream worker {
    server 10.4.3.1 weight=4;
    server 10.4.3.2 weight=2;
    server 10.4.3.3 weight=1;
}

server {
    listen 80;
    server_name granz.channel.A10.com www.granz.channel.A10.com;

    root /var/www/html;

    index index.html index.htm index.nginx-debian.html;

    server_name _;

    location / {
        proxy_pass http://worker;
    }
} ' > /etc/nginx/sites-available/lb_php

ln -s /etc/nginx/sites-available/lb_php /etc/nginx/sites-enabled/
rm /etc/nginx/sites-enabled/default

service nginx restart
```

Lalu, lakukan testing dengan 1000 request dan 100 request/second dengan command berikut:
```
ab -n 1000 -c 100 http://www.granz.channel.A10.com/
```

Hasil:

![Soal7](/images/Soal7/1.jpg)
![Soal7](/images/Soal7/2.jpg)

### Soal 8
Karena diminta untuk menuliskan grimoire, buatlah analisis hasil testing dengan 200 request dan 10 request/second masing-masing algoritma Load Balancer dengan ketentuan sebagai berikut:
- Nama Algoritma Load Balancer
- Report hasil testing pada Apache Benchmark
- Grafik request per second untuk masing masing algoritma. 
- Analisis

Testing untuk nomor 8 dapat dilakukan dengan command berikut:

```
ab -n 200 -c 10 http://www.granz.channel.A10.com/
```

Hasil dari testing yang dilakukan seperti berikut:

- Round Robin - dengan hasil Request per second 672.21 [#/sec] (mean)
![Soal8](/images/Soal8/RoundRobin.jpg)
![Soal8](/images/Soal8/RoundRobin2.jpg)

- Least-connection - Request per second 766.14 [#/sec] (mean)
![Soal8](/images/Soal8/LeastConnection.jpg)
![Soal8](/images/Soal8/LeastConnection2.jpg)

- IP Hash - Request per second 778.34 [#/sec] (mean)
![Soal8](/images/Soal8/IPHash.jpg)
![Soal8](/images/Soal8/IPHash2.jpg)

- Generic Hash - Request per second 778.86 [#/sec] (mean)
![Soal8](/images/Soal8/GenericHash.jpg)
![Soal8](/images/Soal8/GenericHash2.jpg)

Grafik yang ditunjukkan sesuai dari Request per Second:

![Soal8](/images/Soal8/RPS.jpg)

Analisis yang didapatkan:
Round Robin merupakan metode distribusi beban yang sederhana. Setiap permintaan dialihkan secara bergantian ke server yang tersedia. Cocok untuk lingkungan di mana server memiliki spesifikasi yang serupa.

Least-connection mengarahkan permintaan ke server dengan jumlah koneksi aktif paling sedikit. Efektif untuk menyeimbangkan beban di antara server yang memiliki kapasitas berbeda.

IP Hash menggunakan alamat IP client untuk mengarahkan permintaan ke server tertentu. Berguna ketika ada kebutuhan agar klien selalu terhubung ke server yang sama.

Generic Hash mirip dengan IP Hash, namun menggunakan informasi tambahan selain alamat IP (misalnya, header HTTP). Memberikan kontrol lebih besar terhadap cara pengalihan dilakukan.

Kesimpulan:
Berdasarkan hasil diatas, Generic Hash memiliki performa tertinggi diikuti oleh IP Hash, Least-connection, dan Round Robin. Generic Hash dikatakan dapat menjadi algoritma yang terbaik dikarenakan oleh RPS yang tinggi, maka semakin banyak juga permintaan yang dapat ditangani oleh suatu sistem dalam satu detiknya. Performa terbaik tergantung pada karakteristik dan kebutuhan spesifik sistem. Misalnya, jika konsistensi sesi adalah prioritas, IP Hash atau Generic Hash dapat lebih cocok.

### Soal 9
Dengan menggunakan algoritma Round Robin, lakukan testing dengan menggunakan 3 worker, 2 worker, dan 1 worker sebanyak 100 request dengan 10 request/second, kemudian tambahkan grafiknya pada grimoire.

Testing untuk nomor 9 dapat dilakukan dengan command berikut:

```
ab -n 100 -c 10 http://www.granz.channel.A10.com/
```

Hasil dari testing yang dilakukan seperti berikut:

- 3 Worker - Request per second 512.20 [#/sec] (mean)
![Soal9](/images/Soal9/3Worker.jpg)
![Soal9](/images/Soal9/3Worker2.jpg)

- 2 Worker - Request per second 790.72 [#/sec] (mean)
![Soal9](/images/Soal9/2Worker.jpg)
![Soal9](/images/Soal9/2Worker2.jpg)

- 1 Worker - Request per second 878.28 [#/sec] (mean)
![Soal9](/images/Soal9/1Worker.jpg)
![Soal9](/images/Soal9/1Worker2.jpg)

Grafik yang ditunjukkan sesuai dari Request per Second:

![Soal9](/images/Soal9/RPS.jpg)

### Soal 10
Selanjutnya coba tambahkan konfigurasi autentikasi di LB dengan dengan kombinasi username: “netics” dan password: “ajkyyy”, dengan yyy merupakan kode kelompok. Terakhir simpan file “htpasswd” nya di /etc/nginx/rahasisakita/

Pertama - tama kita perlu membuat folder sesuai soal :

**auth.sh Eisen (Load Balancer)**
```
mkdir /etc/nginx/rahasisakita
htpasswd -c /etc/nginx/rahasisakita/htpasswd netics
```

Lalu akan diminta untuk input `New password` dan juga `Re-type new password`. Isi input tersebut dengan `ajkA10`

Tambahkan juga konfigurasi berikut:

**auth.sh Eisen (Load Balancer)**
```
echo 'upstream worker {
    server 10.4.3.1;
    server 10.4.3.2;
    server 10.4.3.3;
}

server {
    listen 80;
    server_name granz.channel.A10.com www.granz.channel.A10.com;

    root /var/www/html;
    index index.html index.htm index.nginx-debian.html;

    location / {
        proxy_pass http://worker;
    }

   auth_basic "Restricted Content";
   auth_basic_user_file /etc/nginx/rahasisakita/htpasswd;

}' > /etc/nginx/sites-available/lb_php

service nginx restart
```

Hasil:

![Soal10](/images/Soal10/1.jpg)
![Soal10](/images/Soal10/2.jpg)
![Soal10](/images/Soal10/3.jpg)
![Soal10](/images/Soal10/4.jpg)

### Soal 11
Lalu buat untuk setiap request yang mengandung /its akan di proxy passing menuju halaman https://www.its.ac.id.

Agar setiap request yang mengandung /its akan di proxy passing menuju halaman https://www.its.ac.id, maka perlu menambahkan konfigurasi berikut:

**proxy.sh Eisen (Load Balancer)**
```
echo 'upstream worker {
    server 10.4.3.1;
    server 10.4.3.2;
    server 10.4.3.3;
}

server {
    listen 80;
    server_name granz.channel.A10.com www.granz.channel.A10.com;

    root /var/www/html;
    index index.html index.htm index.nginx-debian.html;

    location / {
        proxy_pass http://worker;
    }

    location ~ /its {
        proxy_pass https://www.its.ac.id;
        proxy_set_header Host www.its.ac.id;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
    }
}' > /etc/nginx/sites-available/lb_php

service nginx restart
```

Dan juga lakukan restart menggunakan command `service nginx restart`

Untuk testing hasilnya dapat dilakukan dengan command berikut:

```
lynx www.granz.channel.A10.com/its
```

Hasil:

![Soal11](/images/Soal11/1.jpg)

### Soal 12
Selanjutnya LB ini hanya boleh diakses oleh client dengan IP [Prefix IP].3.69, [Prefix IP].3.70, [Prefix IP].4.167, dan [Prefix IP].4.168.

Agar LB ini hanya boleh diakses oleh client dengan IP yang sudah ditentukan soal, maka tambahkan konfigurasi berikut:

**proxyip.sh Eisen (Load Balancer)**
```
echo 'upstream worker {
    server 10.4.3.1;
    server 10.4.3.2;
    server 10.4.3.3;
}

server {
    listen 80;
    server_name granz.channel.A10.com www.granz.channel.A10.com;

    root /var/www/html;
    index index.html index.htm index.nginx-debian.html;

    location / {
        allow 10.4.3.69;
        allow 10.4.3.70;
        allow 10.4.4.167;
        allow 10.4.4.168;
        deny all;
        proxy_pass http://worker;
    }

    location /its {
        proxy_pass https://www.its.ac.id;
        proxy_set_header Host www.its.ac.id;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
    }
}' > /etc/nginx/sites-available/lb_php

service nginx restart
```

Hasil:

- IP Deny

![Soal12](/images/Soal12/1.jpg)
![Soal12](/images/Soal12/2.jpg)

- IP Allow

![Soal12](/images/Soal12/IP.jpg)

Dikarenakan oleh IP yang didapatkan random maka dicoba manual menggunakan IP `10.4.3.21`.

![Soal12](/images/Soal12/3.jpg)
![Soal12](/images/Soal12/4.jpg)

### Soal 13
Semua data yang diperlukan, diatur pada Denken dan harus dapat diakses oleh Frieren, Flamme, dan Fern.

Sebelumnya, perlu untuk melakukan update dan install `mariadb-server`:

**.bashrc danken (Database Server)**
```
echo 'nameserver 10.4.1.2' > /etc/resolv.conf
apt-get update
apt-get install mariadb-server -y
service mysql start
```

Lalu jangan lupa untuk mengganti [bind-address] pada file /etc/mysql/mariadb.conf.d/50-server.cnf menjadi 0.0.0.0 dan jangan lupa untuk melakukan restart mysql kembali

Selanjutnya update dan install beberapa hal pada Worker Laravel:

**.bashrc Frieren, Flamme, Fern (Laravel Worker)**
```
echo 'nameserver 10.4.1.2' > /etc/resolv.conf
apt-get update
apt-get install lynx -y
apt-get install mariadb-client -y
dbA10 -e "SHOW DATABASES;"
apt-get install -y lsb-release ca-certificates apt-transport-https software-properties-common gnupg2
curl -sSLo /usr/share/keyrings/deb.sury.org-php.gpg https://packages.sury.org/php/apt.gpg
sh -c 'echo "deb [signed-by=/usr/share/keyrings/deb.sury.org-php.gpg] https://packages.sury.org/php/ $(lsb_release -sc) main" > /etc/apt/sources.list.d/php.list'
apt-get update
apt-get install php8.0-mbstring php8.0-xml php8.0-cli   php8.0-common php8.0-intl php8.0-opcache php8.0-readline php8.0-mysql php8.0-fpm php8.0-curl unzip wget -y
apt-get install nginx -y

service nginx start
service php8.0-fpm start
```

Lalu, jalankan command berikut:

**danken (Database Server)**
```
mysql -u root -p
Enter password:

CREATE USER 'A10'@'%' IDENTIFIED BY ‘passA10';
CREATE USER 'A10'@'localhost' IDENTIFIED BY 'passA10';
CREATE DATABASE dbA10;
GRANT ALL PRIVILEGES ON *.* TO 'A10'@'%';
GRANT ALL PRIVILEGES ON *.* TO 'A10'@'localhost';
FLUSH PRIVILEGES;
```

![Soal13](/images/Soal13/1.jpg)

Dan coba jalankan command berikut pada salah satu Laravel Worker:

```
mariadb --host=10.4.2.1 --port=3306 --user=A10 --password=passA10 dbA10 -e "SHOW DATABASES;"
```

Hasil:

![Soal13](/images/Soal13/2.jpg)

### Soal 14
Frieren, Flamme, dan Fern memiliki Riegel Channel sesuai dengan quest guide berikut. Jangan lupa melakukan instalasi PHP8.0 dan Composer

Lakukan download composer terlebih dahulu pada laravel worker:

**setup.sh Frieren, Flamme, Fern (Laravel Worker)**
```
wget https://getcomposer.org/download/2.0.13/composer.phar
chmod +x composer.phar
mv composer.phar /usr/local/bin/composer
```

Lalu git yang diberikan dapat di clone dan sebelum clone git tersebut, perlu dilakukan git install dahulu

**setup.sh Frieren, Flamme, Fern (Laravel Worker)**
```
apt-get install git -y
cd /var/www && git clone https://github.com/martuafernando/laravel-praktikum-jarkom
cd /var/www/laravel-praktikum-jarkom && composer update
```

Lalu tambahkan pula konfigurasi berikut pada masing-masing worker:

**setup.sh Frieren, Flamme, Fern (Laravel Worker)**
```
cd /var/www/laravel-praktikum-jarkom && cp .env.example .env
echo 'APP_NAME=Laravel
APP_ENV=local
APP_KEY=
APP_DEBUG=true
APP_URL=http://localhost

LOG_CHANNEL=stack
LOG_DEPRECATIONS_CHANNEL=null
LOG_LEVEL=debug

DB_CONNECTION=mysql
DB_HOST=10.4.2.1
DB_PORT=3306
DB_DATABASE=dbA10
DB_USERNAME=A10
DB_PASSWORD=passA10

BROADCAST_DRIVER=log
CACHE_DRIVER=file
FILESYSTEM_DISK=local
QUEUE_CONNECTION=sync
SESSION_DRIVER=file
SESSION_LIFETIME=120

MEMCACHED_HOST=127.0.0.1

REDIS_HOST=127.0.0.1
REDIS_PASSWORD=null
REDIS_PORT=6379

MAIL_MAILER=smtp
MAIL_HOST=mailpit
MAIL_PORT=1025
MAIL_USERNAME=null
MAIL_PASSWORD=null
MAIL_ENCRYPTION=null
MAIL_FROM_ADDRESS="hello@example.com"
MAIL_FROM_NAME="${APP_NAME}"

AWS_ACCESS_KEY_ID=
AWS_SECRET_ACCESS_KEY=
AWS_DEFAULT_REGION=us-east-1
AWS_BUCKET=
AWS_USE_PATH_STYLE_ENDPOINT=false

PUSHER_APP_ID=
PUSHER_APP_KEY=
PUSHER_APP_SECRET=
PUSHER_HOST=
PUSHER_PORT=443
PUSHER_SCHEME=https
PUSHER_APP_CLUSTER=mt1

VITE_PUSHER_APP_KEY="${PUSHER_APP_KEY}"
VITE_PUSHER_HOST="${PUSHER_HOST}"
VITE_PUSHER_PORT="${PUSHER_PORT}"
VITE_PUSHER_SCHEME="${PUSHER_SCHEME}"
VITE_PUSHER_APP_CLUSTER="${PUSHER_APP_CLUSTER}"' > /var/www/laravel-praktikum-jarkom/.env
cd /var/www/laravel-praktikum-jarkom && php artisan key:generate
cd /var/www/laravel-praktikum-jarkom && php artisan config:cache
cd /var/www/laravel-praktikum-jarkom && php artisan migrate
cd /var/www/laravel-praktikum-jarkom && php artisan db:seed
cd /var/www/laravel-praktikum-jarkom && php artisan storage:link
cd /var/www/laravel-praktikum-jarkom && php artisan jwt:secret
cd /var/www/laravel-praktikum-jarkom && php artisan config:clear
chown -R www-data.www-data /var/www/laravel-praktikum-jarkom/storage
```

Lalu tambahkan pula konfigurasi berikut pada nginx:

**nginx.sh Frieren, Flamme, Fern (Laravel Worker)**
```
echo 'server {
    listen [PORT];

    root /var/www/laravel-praktikum-jarkom/public;

    index index.php index.html index.htm;
    server_name _;

    location / {
            try_files $uri $uri/ /index.php?$query_string;
    }

    # pass PHP scripts to FastCGI server
    location ~ \.php$ {
      include snippets/fastcgi-php.conf;
      fastcgi_pass unix:/var/run/php/php8.0-fpm.sock;
    }

    location ~ /\.ht {
            deny all;
    }

    error_log /var/log/nginx/implementasi_error.log;
    access_log /var/log/nginx/implementasi_access.log;
}' > /etc/nginx/sites-available/laravel-worker

ln -s /etc/nginx/sites-available/laravel-worker /etc/nginx/sites-enabled
service nginx restart
```

Lakukan testing pada masing-masing worker dan sesuai port yang sudah dibuat dengan menggunakan command berikut:
```
lynx localhost:[PORT]
```

Hasil:

![Soal14](/images/Soal14/1.jpg)

### Soal 15-17
Riegel Channel memiliki beberapa endpoint yang harus ditesting sebanyak 100 request dengan 10 request/second. Tambahkan response dan hasil testing pada grimoire.

### Soal 15
- POST /auth/register 

Untuk melakukan testing yang diminta maka digunakan Apache Benchmark. Hal pertama yang dapat dilakukan adalah menambahkan username dan password untuk mengirim ke endpoint /register.

```
echo '{"username": "A10", "password": "passA10" }' > register.json
```

Lalu lakukan testing pada Client dengan command berikut:
```
ab -n 100 -c 10 -p register.json -T application/json http://10.4.4.1:8001/api/auth/register
```
Hasil:

![Soal15](/images/Soal15/1.jpg)
![Soal15](/images/Soal15/2.jpg)

Terdapat Failed Request sebanyak 99 request karena username yang diminta harus unik

### Soal 16
- POST /auth/login

Untuk melakukan testing yang diminta maka digunakan Apache Benchmark. Hal pertama yang dapat dilakukan adalah menambahkan username dan password untuk mengirim ke endpoint /login.

```
echo '{"username": "A10", “password": "passA10" }' > login.json
```

Lalu lakukan testing pada Client dengan command berikut:
```
ab -n 100 -c 10 -p login.json -T application/json http://10.4.4.1:8001/api/auth/login
```
Hasil:

![Soal16](/images/Soal16/1.jpg)
![Soal16](/images/Soal16/2.jpg)

Terdapat Failed Request sebanyak 38 request yang dikarenakan satu worker tidak kuat untuk mendapatkan request sebanyak yang diminta pada soal. 

### Soal 17
- GET /me

Perlu untuk mendapatkan token dengan command berikut:

```
curl -X POST -H "Content-Type: application/json" -d @login.json 
http://10.4.4.1:8001/api/auth/login > login_output.txt
```

Lalu lakukan testing pada Client dengan command berikut:
```
ab -n 100 -c 10 -H "Authorization: Bearer $token" http://10.4.4.1:8001/api/me
```
Hasil:

![Soal17](/images/Soal17/1.jpg)
![Soal17](/images/Soal17/2.jpg)

Terdapat Failed Request sebanyak 40 request yang dikarenakan satu worker tidak kuat untuk mendapatkan request sebanyak yang diminta pada soal. 

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

