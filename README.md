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
User melakukan berbagai aktivitas dengan menggunakan protokol FTP. Salah satunya adalah mengunggah suatu file.
- **Soal Nomor 1A :** <br>
Berapakah sequence number (raw) pada packet yang menunjukkan aktivitas tersebut?<br>
Jawaban : 258040667
- **Soal Nomor 1B :** <br>
Berapakah acknowledge number (raw) pada packet yang menunjukkan aktivitas tersebut?<br>
Jawaban : 1044861039<br>
<br>**Langkah Penyelesaian Soal 1A dan 1B :** <br>
  Awalnya buka **soal1.pcap**, lalu cari pada **display filter -> ketik FTP**. Karena yang dicari yang melakukan aktivitas unggah file, cari packet yang **request : STOR** karena terjadi peng-upload-an file ke FTP server atau bisa dengan **ftp contains "STOR"**, maka akan didapat filenya adalah : **c75-GrabThePhiser.zip**. Klik pada paket tersebut dan pada bagian bawah pada Transmission Control Protocol terdapat informasi mengenai sequence dan acknowledge number (raw) sebagai berikut :
![1(a)](https://github.com/lalaladi/Jarkom-Modul-1-B23-2023/assets/90541607/154ccf20-2e70-4e50-911b-2c36244e6f66)
![1(b)](https://github.com/lalaladi/Jarkom-Modul-1-B23-2023/assets/90541607/dee26afd-3c8c-436b-9b4b-85abec561b21) 

- **Soal Nomor 1C :** <br>
Berapakah sequence number (raw) pada packet yang menunjukkan response dari aktivitas tersebut<br>
Jawaban : 1044861039
- **Soal Nomor 1D :** <br>
Berapakah acknowledge number (raw) pada packet yang menunjukkan response dari aktivitas tersebut?<br>
Jawaban : 258040696<br>
<br>**Langkah Penyelesaian Soal 1C dan 1D :** <br>
Setelah ditemukan file yang diunggah, kita dapat mencari packet yang terdapat c75-GrabThePhiser.zip pada response-nya(atau bisa juga dengan mengetikkan pada display **frame constains “GrabThePhiser”**), lalu klik packet itu dan lihat sequence number (raw) dan acknowledge number (raw) di Transmission Control Protocol:
![1(c)](https://github.com/lalaladi/Jarkom-Modul-1-B23-2023/assets/90541607/f2c94288-6446-4abf-a2df-24f484aeb02d)
![1(d)](https://github.com/lalaladi/Jarkom-Modul-1-B23-2023/assets/90541607/e38d081a-79b3-4f3a-a6e8-7b465ce2da7a)

Berikut merupakan hasil jawaban pada terminal :<br>
![jawaban1](https://github.com/lalaladi/Jarkom-Modul-1-B23-2023/assets/90541607/b4c448ba-e5be-4410-8f5b-068df4800907) <br>

## **Soal Nomor 2** <br>
Sebutkan web server yang digunakan pada portal praktikum Jaringan Komputer!<br>
Jawaban : gunicorn<br>
**Langkah Penyelesaian Soal 2 :** <br>

## **Soal Nomor 3**
Dapin sedang belajar analisis jaringan. Bantulah Dapin untuk mengerjakan soal berikut:
- **Soal Nomor 3A :** <br>
Berapa banyak paket yang tercapture dengan IP source maupun destination address adalah 239.255.255.250 dengan port 3702?<br>
Jawaban : 21<br>
<br>**Langkah Penyelesaian Soal 3A :** <br>
  Kita buka **soal3.pcap** dan pada display capture di Wireshark ketik **(ip.src == 239.255.255.250 || ip.dst == 239.255.255.250) && udp.port == 3702** -> pilih Statistics -> Capture File Properties maka akan terlihat pada bagian banyak packet yang tercapture yakni pada Displayed untuk Packets sebagai berikut :
![3(1)](https://github.com/lalaladi/Jarkom-Modul-1-B23-2023/assets/90541607/53f3109b-f58e-4757-b9f5-3b130f9afe3c)
- **Soal Nomor 3B :** <br>
Protokol layer transport apa yang digunakan?<br>
Jawaban : UDP<br>
<br>**Langkah Penyelesaian Soal 3B :** <br>
  Untuk menyelesaikannya kita gunakan perintah ini pada Display Filter **(ip.src == 239.255.255.250 || ip.dst == 239.255.255.250) && udp.port == 3702** sehingga didapatkan:
![3 (2)](https://github.com/lalaladi/Jarkom-Modul-1-B23-2023/assets/90541607/c97c8122-eef0-4924-b7a5-41040b1a0bf0)

Berikut merupakan hasil jawaban pada terminal :<br>
![jawaban3](https://github.com/lalaladi/Jarkom-Modul-1-B23-2023/assets/90541607/f3ab4d0c-dd59-48b6-8230-fa213ba3a035) <br>

## **Soal Nomor 4** <br>
Berapa nilai checksum yang didapat dari header pada paket nomor 130?<br>
Jawaban : 0x18e5 <br>
**Langkah Penyelesaian Soal 4 :** 

## **Soal Nomor 5**
Elshe menemukan suatu file packet capture yang menarik. Bantulah Elshe untuk menganalisis file packet capture tersebut.<br>
Untuk melihat soal no 5 dapat dilakukan dengan beberapa tahap sebagai berikut :<br>
1. Buka file soal5.pcap lalu pilih salah satu packet -> klik kanan-> pada Follow-> TCP Stream, lalu scroll ke bawah sampai anda menemukan suatu **password** sebagai berikut :<br>
![password_soal5](https://github.com/lalaladi/Jarkom-Modul-1-B23-2023/assets/90541607/90d2e506-f0bc-4e1a-9335-a16a1fe21d28)
2. Lalu buka website **base64decode** untuk melakukan decode pada password tadi.
![decode_soal5](https://github.com/lalaladi/Jarkom-Modul-1-B23-2023/assets/90541607/fdae889a-375e-4a37-918f-51da50c9c4c8)
3. Setelah itu download file **zippppfileee.zip** dan lakukan extract file yang nanti akan meminta anda untuk memasukkan password dalam prosesnya. Masukkan kode yang yang telah di-decode  tadi dan buka **/s3crett/connect.txt**. Nantinya kita akan melihat code untuk soal no.5 seperti berikut :<br>
![code_soal5](https://github.com/lalaladi/Jarkom-Modul-1-B23-2023/assets/90541607/c2aee069-75b9-4f68-958c-51f3bc20821e)
- **Soal Nomor 5A :** <br>
Berapa banyak packet yang berhasil di capture dari file pcap tersebut?<br>
Jawaban : 60<br>
**Langkah Penyelesaian Soal 5A :** <br>
Pilih salah satu packet dan pada **statistic -> Capture File Properties** lihat barisan Packets dan pada bagian Captures didapatkan hasilnya sebagai berikut :
![5(a)](https://github.com/lalaladi/Jarkom-Modul-1-B23-2023/assets/90541607/e105e18e-4c0b-4722-8eed-2aba714de703)
<br>
<br>- **Soal Nomor 5B :** <br>
Port berapakah pada server yang digunakan untuk service SMTP?<br>
Jawaban : 25<br>
**Langkah Penyelesaian Soal 5B :** <br>
Untuk soal ini, kita dapat melihatnya pada modul 1 sebagai berikut :<br>
![gbr_modul](https://github.com/lalaladi/Jarkom-Modul-1-B23-2023/assets/90541607/f0d7d0bd-2a0e-4cbb-a4cf-431cd38a31ac)
<br>
<br>- **Soal Nomor 5C :** <br>
Dari semua alamat IP yang tercapture, IP berapakah yang merupakan public IP?<br>
Jawaban : 74.53.140.153<br>
**Langkah Penyelesaian Soal 5C :** <br>
Soal ini dapat dijawab dengan mengambil referensi dari **https://www.geeksforgeeks.org/difference-between-private-and-public-ip-addresses/** yang dimana dikatakan bahwa IP Private memiliki batas yakni:<br>
- 10.0.0.0 – 10.255.255.255<br>
- 172.16.0.0 – 172.31.255.255<br>
- 192.168.0.0 – 192.168.255.255<br>
selain dari range diatas dapat disimpulkan sebagai IP public dan hanya IP 74.53.140.153 yang ditemukan sebagai IP public.
![5(c)](https://github.com/lalaladi/Jarkom-Modul-1-B23-2023/assets/90541607/922ad409-a198-4db5-8f33-7cc6660fa89d)
<br>
Berikut merupakan hasil jawaban pada terminal :<br>
![jawaban5](https://github.com/lalaladi/Jarkom-Modul-1-B23-2023/assets/90541607/71e5b3f2-902a-4e2e-8bec-89451af66ccd)

## **Soal Nomor 6** <br>
Seorang anak bernama Udin Berteman dengan SlameT yang merupakan seorang penggemar film detektif. sebagai teman yang baik, Ia selalu mengajak slamet untuk bermain valoranT bersama. suatu malam, terjadi sebuah hal yang tak terdUga. ketika udin mereka membuka game tersebut, laptop udin menunjukkan sebuah field text dan Sebuah kode Invalid bertuliskan "server SOURCE ADDRESS 7812 is invalid". ketika ditelusuri di google, hasil pencarian hanya menampilkan a1 e5 u21. jiwa detektif slamet pun bergejolak. bantulah udin dan slamet untuk menemukan solusi kode error tersebut.<br>
Jawaban : JDRNJA<br>
**Langkah Penyelesaian Soal 6 :**

## **Soal Nomor 7**
Berapa jumlah packet yang menuju IP 184.87.193.88?<br>
Jawaban : 6<br>
<br>**Langkah Penyelesaian Soal 7 :** <br>
Karena kita ingin menghitung jumlah packet yang **menuju** ke IP 184.87.193.88 maka kita menggunakan  dst(untuk destination) dengan mengetikkan pada Display Filter **ip.dst == 184.87.193.88** -> statistic -> Capture File Properties.
![7](https://github.com/lalaladi/Jarkom-Modul-1-B23-2023/assets/90541607/b74cc045-0c67-45ac-a0a6-3300c6d40375)
<br>
<br>Berikut merupakan hasil jawaban pada terminal :<br>
![jawaban7](https://github.com/lalaladi/Jarkom-Modul-1-B23-2023/assets/90541607/c70b0ded-2068-4947-92da-c3ae441ce525)<br>
## **Soal Nomor 8** <br>
Berikan kueri filter sehingga wireshark hanya mengambil semua protokol paket yang menuju port 80! (Jika terdapat lebih dari 1 port, maka urutkan sesuai dengan abjad)<br>
Jawaban : tcp.dstport == 80 || udp.dstport == 80<br>
**Langkah Penyelesaian Soal 8 :**

## **Soal Nomor 9**
Berikan kueri filter sehingga wireshark hanya mengambil paket yang berasal dari alamat 10.51.40.1 tetapi tidak menuju ke alamat 10.39.55.34!<br>
Jawaban :  ip.src == 10.51.40.1 && ip.dst != 10.39.55.34<br>
<br>**Langkah Penyelesaian Soal 9 :** <br>
Untuk mengambil packet yang berasal dari alamat 10.51.40.1 dilakukan sebagai berikut : <br>**ip.src == 10.51.40.1** dan untuk packet yang tidak menuju ke alamat 10.39.55.34 dilakukan dengan : **ip.dst != 10.39.55**. Lalu, karena diminta untuk menerapkan syarat keduanya maka dapat dituliskan pada Display Filter : **ip.src == 10.51.40.1 && ip.dst != 10.39.55.34**
![9](https://github.com/lalaladi/Jarkom-Modul-1-B23-2023/assets/90541607/8b77f15d-e96e-42c4-8fc0-754cdcc96552)
<br>
<br>Berikut merupakan hasil jawaban pada terminal :<br>
![jawaban9](https://github.com/lalaladi/Jarkom-Modul-1-B23-2023/assets/90541607/659e9755-67e9-465a-bd90-b63c679d6a77) 

## **Soal Nomor 10** <br>
Sebutkan kredensial yang benar ketika user mencoba login menggunakan Telnet<br>
Jawaban : dhafin:kesayangank0k0<br>
**Langkah Penyelesaian Soal 10 :**


# **Kendala Selama Pengerjaan**
Berikut merupakan beberapa kendala dan kesulitan yang kami alami dalam pengerjaan Praktikum Modul 1 Jaringan Komputer, yakni :
- Jaringannya sangat lambat yang membuat laman terus-menerus loading sehingga kesulitan mengerjakan dan menjawab soal

# **End of The Line**
