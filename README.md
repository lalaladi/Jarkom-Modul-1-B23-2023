# Jarkom-Modul-1-B23-2023
# **Praktikum Modul 1 Jaringan Komputer**
Berikut adalah Repository dari Kelompok B23 untuk pengerjaan Praktikum Modul 1. Dalam Repository ini terdapat daftar anggota kelompok, dokumentasi dan Penjelasan tiap soal, _Screenshot_, dan Kendala yang Dialami. 

# **Anggota Kelompok**
| Nama                      | NRP        | Kelas               |
| ------------------------- | ---------- | ------------------- |
| Armadya Hermawan Sarwono  | 5025211243 | Jaringan Komputer B |
| Dian Lies Seviona Dabukke | 5025211080 | Jaringan Komputer B |

# **Dokumentasi dan Penjelasan Soal**
Berikut adalah dokumentasi yang tiap soal dan penjelasan terkait perintah yang digunakan :
## **Soal Nomor 1**
Buatlah topologi dengan:
Yudhistira – DNS Master
Werkudara – DNS Slave
Arjuna – Load Balancer
Prabukusuma, Abimanyu, dan Wisanggeni – Web Server
Nakula dan Sadewa – Client 
<br>**Langkah Penyelesaian Soal 1 :** <br>
a). 
 

b). Lakukan konfigurasi IP tiap node 
Pandudewanata
auto eth0
iface eth0 inet dhcp

auto eth1
iface eth1 inet static
	address 10.20.1.1
	netmask 255.255.255.0
auto eth2
iface eth2 inet static
	address 10.20.2.1
	netmask 255.255.255.0
auto eth3
iface eth1 inet static
	address 10.20.3.1
	netmask 255.255.255.0
Werkudara 
auto eth0
iface eth0 inet static
	address 10.20.1.5
	netmask 255.255.255.0
	gateway 10.20.1.1

Yudhistira
auto eth0
iface eth0 inet static
	address 10.20.1.4
	netmask 255.255.255.0
	gateway 10.20.1.1

Arjuna 
auto eth0
iface eth0 inet static
	address 10.20.2.2
	netmask 255.255.255.0
	gateway 10.20.2.1
Prabukusuma
		auto eth0
iface eth0 inet static
	address 10.20.3.2
	netmask 255.255.255.0
	gateway 10.20.3.1
 Abimanyu
auto eth0
iface eth0 inet static
	address 10.20.3.3
	netmask 255.255.255.0
	gateway 10.20.3.1
Wisanggeni
auto eth0
iface eth0 inet static
	address 10.20.3.4
	netmask 255.255.255.0
	gateway 10.20.3.1
Nakula
auto eth0
iface eth0 inet static
	address 10.20.1.2
	netmask 255.255.255.0
	gateway 10.20.1.1

Sadewa
auto eth0
iface eth0 inet static
	address 10.20.1.3
	netmask 255.255.255.0
gateway 10.20.1.2
	**Untuk tiap command yang ada dijalankan terlebih dahulu di terminal lalu simpan di /root/**
c). Pada /root/.bashrc  dengan Prefix IP kelompok ini (B23) 
iptables -t nat -A POSTROUTING -o eth0 -j MASQUERADE -s 10.20.0.0/16

d). Agar dapat terhubung ke internet melalui Pandudewanata ketik dalam /root/.bashrc tiap node ubuntu yang dibuat 
 echo nameserver 192.168.122.1 > /etc/resolv.conf
Lalu jika dilakukan ping google.com pada ubuntu yang dipilih akan terlihat seperti berikut 



## **Soal Nomor 2**
Buatlah website utama pada node arjuna dengan akses ke arjuna.yyy.com dengan alias www.arjuna.yyy.com dengan yyy merupakan kode kelompok.

<br>**Langkah Penyelesaian Soal 2 :** <br>
	a). Pada /root/.bashrc  di Yudhistira
apt-get update
		apt-get install bind9 -y
	 b). Pembuatan Domain	
Pada terminal Yudhistira ketik : nano /etc/bind/named.conf.local 
Isi dengan : 
```bash
zone "arjuna.b23.com" {
    type master;
    file "/etc/bind/jarkom/arjuna";
};
```
<br>
Pada terminal :
mkdir /etc/bind/jarkom
cp /etc/bind/db.local /etc/bind/jarkom/arjuna
nano /etc/bind/jarkom/arjuna

<br>
Pada /root/.bashrc  tambahkan: service bind9 restart
Untuk pembuktiannya : 
 Pada /etc/resolv.conf, masukkan nameserver IP Yudhistira 
 nameserver 10.20.1.4
Lalu ping domain dan alias yang telah dibuat

<br>

## **Soal Nomor 3**
Dengan cara yang sama seperti soal nomor 2, buatlah website utama dengan akses ke abimanyu.yyy.com dan alias www.abimanyu.yyy.com.

<br>**Langkah Penyelesaian Soal 3 :** <br>
	a). Pada /root/.bashrc  
apt-get update
		apt-get install bind9 -y
	 b). Pembuatan Domain	
Pada terminal Yudhistira ketik : nano /etc/bind/named.conf.local 
Isi dengan : 
```bash
zone "abimanyu.b23.com" {
    type master;
    file "/etc/bind/jarkom/abimanyu";
};
```
<br>
Pada terminal :
mkdir /etc/bind/jarkom
cp /etc/bind/db.local /etc/bind/jarkom/abimanyu
nano /etc/bind/jarkom/abimanyu


<br>
Pada terminal : service bind9 restart
Untuk pembuktiannya : 
 Pada /etc/resolv.conf, masukkan nameserver IP Yudhistira 
 nameserver 10.20.1.4
Lalu ping domain yang telah dibuat
Bukti : 

## **Soal Nomor 4**
Kemudian, karena terdapat beberapa web yang harus di-deploy, buatlah subdomain parikesit.abimanyu.yyy.com yang diatur DNS-nya di Yudhistira dan mengarah ke Abimanyu.

<br>**Langkah Penyelesaian Soal 4 :** <br>
a). Edit /etc/bind/jarkom/abimanyu di Yudhistira 
	

b). Pada terminal Yudhistira : service bind9 restart
Bukti : 

## **Soal Nomor 5**
Buat juga reverse domain untuk domain utama. (Abimanyu saja yang direverse)

<br>**Langkah Penyelesaian Soal 5 :** <br>

	a). Pada terminal Yudhistira ketik : nano /etc/bind/named.conf.local 
Isi dengan : 
```bash
zone "3.20.10.in-addr.arpa" {
    type master;
    file "/etc/bind/jarkom/reverseabimanyu";
};
```
<br>
b). Copy-kan file db.local : cp /etc/bind/db.local /etc/bind/jarkom/reverseabimanyu
	c). Lalu edit file reverseabimanyu

<br>
d).  Pada terminal : service bind9 restart
e).  Pada terminal Nakula dan tambahkan isi /root/.bashrc : 
apt-get update
apt-get install dnsutils
Bukti : 
	Terminal Nakula ketik : host -t PTR 10.20.3.3


## **Soal Nomor 6**
Agar dapat tetap dihubungi ketika DNS Server Yudhistira bermasalah, buat juga Werkudara sebagai DNS Slave untuk domain utama.

<br>**Langkah Penyelesaian Soal 6 :** <br>
	a).  Pada terminal Yudhistira, edit /etc/bind/named.conf.local 
		```bash
		zone "arjuna.b23.com" {
    type master;
    notify yes;
    also-notify {10.20.1.5 ; };
    allow-transfer { 10.20.1.5 ; }; 
    file "/etc/bind/jarkom/arjuna";
};

zone "abimanyu.b23.com" {
    type master;
    notify yes;
    also-notify {10.20.1.5 ; };
    allow-transfer { 10.20.1.5 ; }; 
    file "/etc/bind/jarkom/abimanyu";
};
```
<br>
	  b). Pada terminal : service bind9 restart
	 c). Konfigurasi Werkudara
 Pada terminal dan simpan di /root : apt-get update
     apt-get install bind9 -y
Tambahkan syntax di /etc/bind/named.conf.local 
	```bash
	zone "arjuna.b23.com" {
    type slave;
    masters {10.20.1.4; };
    file "/var/lib/bind/jarkom/arjuna";

zone "abimanyu.b23.com" {
    type slave;
    masters {10.20.1.4; };
    file "/var/lib/bind/jarkom/abimanyu";
};
```
	<br>
Pada terminal : service bind9 restart
	Bukti : 1. Lakukan  service bind9 stop di Yudhistira
		2. Lakukan pengaturan nameserver dengan menambahkan isi  /etc/resolv.conf di Nakula  : nameserver 10.20.1.4
				    nameserver 10.20.1.5
		3. Lalu ping arjuna atau abimanyu

## **Soal Nomor 7**
Seperti yang kita tahu karena banyak sekali informasi yang harus diterima, buatlah subdomain khusus untuk perang yaitu baratayuda.abimanyu.yyy.com dengan alias www.baratayuda.abimanyu.yyy.com yang didelegasikan dari Yudhistira ke Werkudara dengan IP menuju ke Abimanyu dalam folder Baratayuda.

<br>**Langkah Penyelesaian Soal 7 :** <br>
	a). Konfigurasi pada Yudhistira
edit /etc/bind/jarkom/abimanyu

<br>
Edit  /etc/bind/named.conf.options dengan comment dan tambahkan baris seperti gambar

<br>
Pada terminal : service bind9 restart

b). Konfigurasi pada Werkudara
Edit  /etc/bind/named.conf.options dengan comment dan tambahkan baris seperti gambar

<br>
Tambahkan pada /etc/bind/named.conf.local 
```bash
	zone "baratayuda.abimanyu.b23.com" {
    type master;
    file "/var/lib/bind/delegasi/baratayuda";
};
```
<br>
Pada terminal : 
mkdir /etc/bind/delegasi
cp /etc/bind/db.local /etc/bind/delegasi/baratayuda

<br>
Pada terminal : service bind9 restart

Bukti : 

## **Soal Nomor 8**
Untuk informasi yang lebih spesifik mengenai Ranjapan Baratayuda, buatlah subdomain melalui Werkudara dengan akses rjp.baratayuda.abimanyu.yyy.com dengan alias www.rjp.baratayuda.abimanyu.yyy.com yang mengarah ke Abimanyu.

<br>**Langkah Penyelesaian Soal 8 :** <br>
a). Edit /etc/bind/delegasi/baratayuda di Werkudara
	

b). Pada terminal Werkudara: service bind9 restart

Bukti :  


## **Soal Nomor 9**
Arjuna merupakan suatu Load Balancer Nginx dengan tiga worker (yang juga menggunakan nginx sebagai webserver) yaitu Prabakusuma, Abimanyu, dan Wisanggeni. Lakukan deployment pada masing-masing worker.

<br>**Langkah Penyelesaian Soal 9 ** <br>
Pada 3 Nginx diatas, lakukan hal yang sama:
	a). Pada terminal dan /root/.bashrc : 
		 apt-get update && apt install nginx php php-fpm -y
	c). Pada terminal : 
		 mkdir /var/www/arjuna.b23.com
	d). Masuk ke directory /var/www/arjuna.b23.com dan buat file index.php yang berisi : 
	```bash
	 <?php
 echo "Halo, Kamu berada di Prabukusuma"; #ganti sesuai node
 ?>
```
<br>
e). Masuk ke directory /etc/nginx/sites-available dan nano arjuna dengan isi 
```bash
server {

 	listen 80;

 	root /var/www/arjuna.b23.com;

 	index index.php index.html index.htm;
 	server_name _;

 	location / {
 			try_files $uri $uri/ /index.php?$query_string;
 	}

 	# pass PHP scripts to FastCGI server
 	location ~ \.php$ {
 	include snippets/fastcgi-php.conf;
 	fastcgi_pass unix:/var/run/php/php7.2-fpm.sock;
 	}

 location ~ /\.ht {
 			deny all;
 	}

 	error_log /var/log/nginx/arjuna_error.log;
 	access_log /var/log/nginx/arjuna_access.log;
 }
```
<br>
f). Pada terminal : 
ln -s /etc/nginx/sites-available/arjuna /etc/nginx/sites-enabled
 service nginx restart
Bukti : 
 nginx -t pada tiap nginx worker



	
## **Soal Nomor 10**
Kemudian gunakan algoritma Round Robin untuk Load Balancer pada Arjuna. Gunakan server_name pada soal nomor 1. Untuk melakukan pengecekan akses alamat web tersebut kemudian pastikan worker yang digunakan untuk menangani permintaan akan berganti ganti secara acak. Untuk webserver di masing-masing worker wajib berjalan di port 8001-8003. Contoh
    - Prabakusuma:8001
    - Abimanyu:8002
    - Wisanggeni:8003

<br>**Langkah Penyelesaian Soal 10 ** <br>
	a). Pada terminal Arjuna dan simpan di /root/.bashrc 
		apt-get update
apt-get install nginx
b). Pada terminal : service nginx start
    service nginx status
			    Cd /etc/nginx/sites-available
			    Nsno lb-arjuna :

<br>
c). Pada tiap masing-masing worker : 
Prabukusuma
masuk ke directory /etc/nginx/sites-available dan nano arjuna dengan isi
```bash
server {

 	listen 8001; #sesuai port yang ada di soal

 	root /var/www/arjuna.b23.com;

 	index index.php index.html index.htm;
 	server_name _;

 	location / {
 			try_files $uri $uri/ /index.php?$query_string;
 	}

 	# pass PHP scripts to FastCGI server
 	location ~ \.php$ {
 	include snippets/fastcgi-php.conf;
 	fastcgi_pass unix:/var/run/php/php7.2-fpm.sock;
 	}

 location ~ /\.ht {
 			deny all;
 	}

 	error_log /var/log/nginx/arjuna.log;
 	access_log /var/log/nginx/arjuna_access.log;
 }
```
<br>

Abimanyu
masuk ke directory /etc/nginx/sites-available dan nano arjuna dengan isi
```bash
server {

 	listen 8002; #sesuai port yang ada di soal

 	root /var/www/arjuna.b23.com;

 	index index.php index.html index.htm;
 	server_name _;

 	location / {
 			try_files $uri $uri/ /index.php?$query_string;
 	}

 	# pass PHP scripts to FastCGI server
 	location ~ \.php$ {
 	include snippets/fastcgi-php.conf;
 	fastcgi_pass unix:/var/run/php/php7.2-fpm.sock;
 	}

 location ~ /\.ht {
 			deny all;
 	}

 	error_log /var/log/nginx/arjuna.log;
 	access_log /var/log/nginx/arjuna_access.log;
 }
```
<br>

Wisanggeni
masuk ke directory /etc/nginx/sites-available dan nano arjuna dengan isi
```bash
server {

 	listen 8003; #sesuai port yang ada di soal

 	root /var/www/arjuna.b23.com;

 	index index.php index.html index.htm;
 	server_name _;

 	location / {
 			try_files $uri $uri/ /index.php?$query_string;
 	}

 	# pass PHP scripts to FastCGI server
 	location ~ \.php$ {
 	include snippets/fastcgi-php.conf;
 	fastcgi_pass unix:/var/run/php/php7.2-fpm.sock;
 	}

 location ~ /\.ht {
 			deny all;
 	}

 	error_log /var/log/nginx/arjuna.log;
 	access_log /var/log/nginx/arjuna_access.log;
 }
```
<br>

c). Pada terminal :  
ln -s /etc/nginx/sites-available/lb-arjuna /etc/nginx/sites-enabled
service nginx restart
Bukti : 
Pada Nakula, install lynx dan simpan di /root/.bashrc
apt-get update
apt-get install lynx
Lynx http://10.20.3.1:8001




# **Kendala Selama Pengerjaan**
Berikut merupakan beberapa kendala dan kesulitan yang kami alami dalam pengerjaan Praktikum Modul 1 Jaringan Komputer, yakni :
- Jaringannya sangat lambat yang membuat laman terus-menerus loading sehingga kesulitan mengerjakan dan menjawab soal

# **End of The Line**
