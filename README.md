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
Jawaban : 258040667<br>
- **Soal Nomor 1B :** <br>
Berapakah acknowledge number (raw) pada packet yang menunjukkan aktivitas tersebut?<br>
Jawaban : 1044861039<br>
**Langkah Penyelesaian Soal 1A dan 1B :**
  Awalnya buka **soal1.pcap**, lalu cari pada **display filter -> ketik FTP**. Karena yang dicari yang melakukan aktivitas unggah file, cari packet yang **request : STOR** karena terjadi peng-upload-an file ke FTP server, maka akan didapat filenya adalah : **c75-GrabThePhiser.zip**. Klik pada paket tersebut dan pada bagian bawah pada Transmission Control Protocol terdapat informasi mengenai sequence dan acknowledge number (raw) sebagai berikut :

- **Soal Nomor 1C :** <br>
Berapakah sequence number (raw) pada packet yang menunjukkan response dari aktivitas tersebut<br>
Jawaban : 1044861039<br>
**Langkah Penyelesaian Soal 1C :**
- **Soal Nomor 1D :** <br>
Berapakah acknowledge number (raw) pada packet yang menunjukkan response dari aktivitas tersebut?<br>
Jawaban : 258040696<br>
**Langkah Penyelesaian Soal 1D :**

## **Soal Nomor 2**
Sebutkan web server yang digunakan pada portal praktikum Jaringan Komputer!<br>
Jawaban : <br>
**Langkah Penyelesaian Soal 2 :**

## **Soal Nomor 3**
Dapin sedang belajar analisis jaringan. Bantulah Dapin untuk mengerjakan soal berikut:
- **Soal Nomor 3A :** <br>
Berapa banyak paket yang tercapture dengan IP source maupun destination address adalah 239.255.255.250 dengan port 3702?<br>
Jawaban : 21<br>
**Langkah Penyelesaian Soal 3A :**
- **Soal Nomor 3B :** <br>
Protokol layer transport apa yang digunakan?<br>
Jawaban : UDP<br>
**Langkah Penyelesaian Soal 3B :**

## **Soal Nomor 4**
Berapa nilai checksum yang didapat dari header pada paket nomor 130?<br>
Jawaban : <br>
**Langkah Penyelesaian Soal 4 :**

## **Soal Nomor 5**
Elshe menemukan suatu file packet capture yang menarik. Bantulah Elshe untuk menganalisis file packet capture tersebut.
- **Soal Nomor 5A :** <br>
Berapa banyak packet yang berhasil di capture dari file pcap tersebut?<br>
Jawaban : 60<br>
**Langkah Penyelesaian Soal 5A :**
- **Soal Nomor 5B :** <br>
Port berapakah pada server yang digunakan untuk service SMTP?<br>
Jawaban : 25<br>
**Langkah Penyelesaian Soal 5B :**
- **Soal Nomor 5C :** <br>
Dari semua alamat IP yang tercapture, IP berapakah yang merupakan public IP?<br>
Jawaban : 74.53.140.153<br>
**Langkah Penyelesaian Soal 5C :**

## **Soal Nomor 6**
Seorang anak bernama Udin Berteman dengan SlameT yang merupakan seorang penggemar film detektif. sebagai teman yang baik, Ia selalu mengajak slamet untuk bermain valoranT bersama. suatu malam, terjadi sebuah hal yang tak terdUga. ketika udin mereka membuka game tersebut, laptop udin menunjukkan sebuah field text dan Sebuah kode Invalid bertuliskan "server SOURCE ADDRESS 7812 is invalid". ketika ditelusuri di google, hasil pencarian hanya menampilkan a1 e5 u21. jiwa detektif slamet pun bergejolak. bantulah udin dan slamet untuk menemukan solusi kode error tersebut.<br>
Jawaban : <br>
**Langkah Penyelesaian Soal 6 :**

## **Soal Nomor 7**
Berapa jumlah packet yang menuju IP 184.87.193.88?<br>
Jawaban : 6<br>
**Langkah Penyelesaian Soal 7 :**

## **Soal Nomor 8**
Berikan kueri filter sehingga wireshark hanya mengambil semua protokol paket yang menuju port 80! (Jika terdapat lebih dari 1 port, maka urutkan sesuai dengan abjad)<br>
Jawaban : <br>
**Langkah Penyelesaian Soal 8 :**

## **Soal Nomor 9**
Berikan kueri filter sehingga wireshark hanya mengambil paket yang berasal dari alamat 10.51.40.1 tetapi tidak menuju ke alamat 10.39.55.34!<br>
Jawaban :  ip.src == 10.51.40.1 && ip.dst != 10.39.55.34<br>
**Langkah Penyelesaian Soal 9 :**

## **Soal Nomor 10**
Sebutkan kredensial yang benar ketika user mencoba login menggunakan Telnet<br>
Jawaban : <br>
**Langkah Penyelesaian Soal 10 :**

# **Kendala Selama Pengerjaan**
Berikut merupakan beberapa kendala dan kesulitan yang kami alami dalam pengerjaan Praktikum Modul 1 Jaringan Komputer, yakni :
- Jaringannya sangat lambat yang membuat laman terus-menerus loading sehingga kesulitan mengerjakan dan menjawab soal

# **End of The Line**
