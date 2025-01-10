# Modul Basis Data
Modul ini disusun untuk memenuhi kebutuhan belajar bersama yang akan membahas mengenai Basis Data

# Daftar Modul dan Materi
- [BAB 1 Pengenalan Basis Data](#bab-1-pengenalan-basis-data)
- [BAB 2 Konsep Basis Data](#bab-2-konsep-basis-data)
- [BAB 3 Perancangan Konseptual dan Pemodelan Data](#bab-3-perancangan-konseptual-dan-pemodelan-data)
- [BAB 4 Physical Data Model](#bab-4-physical-data-model)
- [BAB 5 Normalisasi](#bab-5-normalisasi)
- [BAB 6 Data Definition Language](#bab-6-data-definition-language)
- [BAB 7 Data Manipulation Language](#bab-7-data-manipulation-language)
- [BAB 8 Aljabar Relasional dan Join](#bab-8-aljabar-relasional-dan-join)
- [BAB 9 Nested Query](#bab-9-nested-query)

## BAB 1 Pengenalan Basis Data
*Data* adalah fakta dari suatu objek atau kejadian.  
Data biasanya dinyatakan dalam bentuk simbol seperti teks, angka, gambar, suara, atau video.
Berikut merupakan contoh data :
```
Nama mahasiswa: Andi Prasetya
Tanggal lahir: 27 Juni 2002
Nilai Basis Data: A
```
*Informasi* adalah hasil dari pemrosesan data yang telah dikumpulkan dan diorganisir sedemikian rupa sehingga memiliki makna dan konteks yang jelas. Pada dasarnya, informasi terbentuk ketika data mentah telah melalui proses pengolahan, sehingga menghasilkan suatu output yang memiliki arti dan nilai yang dapat dipahami dalam konteks tertentu.  
Berikut merupakan contoh informasi :
```
Jumlah mahasiswa Teknik Informatika dari Surabaya sebanyak 57 orang
IPS mahasiswa: 3,6
```
Informasi merupakan data yang diambil dari konteks tertentu. Contoh :
```
Mahasiswa yang berasal dari Surabaya ada 5 orang
```
Selain itu, informasi juga dapat berupa : 
- Kategorisasi, contoh :
```
Mahasiswa laki-laki ada 3 orang, mahasiswa perempuan ada 2 orang
```
- Ringkasan data, contoh :
```
Mahasiswa angkatan 2015 ada 5 orang
```
- Perhitungan, contoh :
```
Rata-rata penghasilan ortu mahasiswa adalah 4.100.000
```
Cara mengubah data menjadi informasi adalah sebagai berikut :
![image](https://github.com/user-attachments/assets/86fda107-d63a-4383-9617-6385491b00d5)

Manfaat data dan informasi antara lain : 
1. Data dan informasi merupakan aset yang sangat berharga
2. Data dan informasi penting untuk mendukung pengambilan keputusan

Adapun contoh pemanfaatan data dan informasi adalah sebagai berikut :
![image](https://github.com/user-attachments/assets/7861abfc-c956-4830-b3ec-6eded6070955)

*Pengetahuan* merupakan hasil dari proses memahami dan menginternalisasi informasi secara mendalam. Ini terbentuk ketika seseorang tidak hanya menerima informasi, tetapi juga mengolahnya berdasarkan pengalaman, pembelajaran, dan pemahaman dalam konteks tertentu. Pengetahuan memungkinkan seseorang untuk membuat keputusan dan mengambil tindakan yang tepat karena adanya pemahaman yang menyeluruh tentang suatu hal. 
Berikut merupakan contoh pengetahuan : 
```
Banyak mahasiswa Informatika yang lulus di usia muda (dilihat dari rata-rata usianya)
Banyak mahasiswa Informatika yang pandai (dilihat dari IPKnya)
Banyak mahasiswa Informatika yang berasal dari keluarga kaya (dilihat dari jumlah mobil)
```
Berikut ini merupakan tingkatan dari data menuju pengetahuan :
![image](https://github.com/user-attachments/assets/60e9ab09-9416-45d3-beb4-e50eabdd3f3c)

### Definisi umum Basis Data
- Database adalah koleksi dari data berelasi
- Data adalah fakta yang disimpan dan memiliki arti implisit
- Database Management System (DBMS) merupakan sistem untuk memfasilitasi pembentukan dan pemeliharaan computerized database (kumpulan data yang disimpan, dikelola, dan diakses secara elektronik menggunakan sistem komputer). Contoh dari computerized database antara lain database mahasiswa di universitas dan sistem pemesanan tiket.

Basis data biasanya diperlukan untuk menyimpan data, memudahkan pengorganisasian data, dan mengolah data menjadi informasi.

Fungsi DBMS antara lain :
- Mendefinisikan database : dalam hal tipe data, struktur, constraint
- Memanipulasi database : querying, insertion, deletions dan modifications
- Pemrosesan dan sharing sekaligus dengan satu kelompok pengguna dan program

Terdapat dua jenis DBMS, yaitu Relational Database Management System (RDMS) dan Non-relational Database Management System. Berikut merupakan beberapa contoh DBMS :   
![image](https://github.com/user-attachments/assets/cfc0620b-54fc-4d22-9e27-a3d0d32e8ddc)

## BAB 2 Konsep Basis Data
*Entitas* adalah objek atau kejadian yang ada pada dunia nyata yang membedakan objek tersebut dengan objek lainnya. Sebuah entitas did dalam basis data dideskripsikan menggunakan sekumpulan atribut. Salah satu contoh entitas adalah `karyawan`.  
*Atribut* adalah item data yang menjadi karakteristik dari suatu entitas. Salah satu contoh dari atribut dari entitas `karyawan` antara lain adalah `NIP, Nama, Alamat, No HP, dll`.  
Entitas dapat berupa :  
![image](https://github.com/user-attachments/assets/21c8ecb3-4936-4a95-a9dc-07293c19bbc4)  

Cara menemukan entitas :  
1. Buat ilustrasi/gambaran cerita tentang sistem yang akan dicari entitasnya
2. Tandai setiap objek yang diwakili oleh kata benda yang ada di dalam ilustrasi tersebut
3. Untuk setiap objek tersebut yakinkan bahwa ia memiliki karakteristik yang nanti disebut sebagai atribut
4. Tentukan objek yang merupakan entitas (Jika memang ia memiliki karakteristik jadikan ia sebagai entitas)

*Relationship* merupakan hubungan antara dua buah entitas atau lebih. Berikut merupakan contoh dari relationship :  
![image](https://github.com/user-attachments/assets/d761eafc-9da0-4c03-a429-c43114c7345e)

Tipe Hubungan antar Entitas ada dua macam :  
1. Entitas Kuat (Strong Entity) merupakan entitas yang berdiri sendiri tanpa bergantung pada entitas lain. Selain itu, bisa diidentifikasi secara unik menggunakan atribut-atributnya sendiri, salah satu / beberapa atribut miliknya menjadi `PRIMARY KEY`.
2. Entitas Lemah (Weak Entity) merupakan entitas yang tidak bisa diidentifikasi secara unik melalui atributnya saja, sehingga bergantung pada entitas lain. Weak entity biasanya menggunakan atribut dari entitas lain (foreign key).

Contoh case :  
![image](https://github.com/user-attachments/assets/b7d98dce-7051-4462-9b1c-08a5a122ece2)  

Relasi dari sebuah entitas dapat dikelompokkan menjadi empat jenis :  
![image](https://github.com/user-attachments/assets/bd44b75d-a307-4d22-804c-bad2a523637d)  

![image](https://github.com/user-attachments/assets/f6ecfee2-f76d-46bf-84d0-f189aebe68ce)

![image](https://github.com/user-attachments/assets/1a0014d0-bc6b-4b20-9c24-538fe20577ec)

![image](https://github.com/user-attachments/assets/c46f891a-8ea6-47d2-afa3-622c4a06074e)

![image](https://github.com/user-attachments/assets/9ff3f78c-9553-4b75-8e9b-3a4f34e12a75)

Adapun cara menentukan relasi antara lain :  
1. Dari gambaran cerita sistem, tandai setiap hubungan yang diwakili oleh kata kerja yang ada di dalam ilustrasi tersebut beserta entitas yang berhubungan
2. Identifikasikan rasio kardinalitas dari setiap hubungan
3. Identifikasikan batasan partisipasi dari setiap hubungan yang ada berikut kemungkinan atribut yang muncul dari setiap hubungan
4. Gambarkan hubungan tersebut dalam bentuk notasi diagram dan gabungkan dengan notasi Entitas dan atribut yang dibuat sebelumnya

## BAB 3 Perancangan Konseptual dan Pemodelan Data
## BAB 4 Physical Data Model
## BAB 5 Normalisasi
## BAB 6 Data Definition Language
## BAB 7 Data Manipulation Language
## BAB 8 Aljabar Relasional dan Join
## BAB 9 Nested Query
