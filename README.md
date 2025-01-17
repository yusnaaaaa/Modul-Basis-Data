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
Proses perancangan database dimulai dengan perancangan konseptual yang terdiri dari 3 tahap :  
1. Investigasi : dalam tahap ini akan dilakukan analisis kebutuhan bisnis dari organisasi/perusahaan, kemudian mengidentifikasi data apa saja yang akan digunakan. Tahap ini merupakan tahap pengumpulan informasi awal.
2. Data Model : dalam tahap ini akan dibuat representasi dari transaksi data dalam proses bisnis dan menggunakan CDM (Conseptual Data Model) Diagram untuk implementasi. CDM menggambarkan hubungan antar entitas secara konseptual.
3. Verifikasi : dalam tahap ini akan dilakukan pengecekan apakah kebutuhan bisnis sudah sesuai dengan data model yang dibuat, kemudian memastikan tidak ada kesalahan dalam pemodelan. Jika ada ketidaksesuaian, maka kembali ke tahap investigasi.  
Ketiga tahap diatas HANYA fokus pada konsep dan kebutuhan bisnis, belum membahas mengenai teknologi (software/hardware) yang akan digunakan.

Langkah - Langkah Perancangan Basis data :  
1. Definisi Kebutuhan : Mengidentifikasi dan mendeskripsikan data yang dibutuhkan user, proses wawancara dengan stakeholder, dan dokumentasi kebutuhan data organisasi.
2. Rancangan Konseptual : Membuat data konseptual, merancang arsitektur informasi, dan menyesuaikan dengan kebutuhan berbagai user dalam organisasi.
3. Rancangan Implementasi : Mengubah model konseptual menjadi logical data model, membuat skema yang bisa diproses DBMS, dan menentukan struktur tabel dan relasi.
4. Rancangan Fisik : Mengimplementasikan struktur database, menentukan cara penyimpanan seperti file dan tabel, dan optimasi performa database.

Berikut merupakan diagram detail mengenai perancangan basis data :  
![image](https://github.com/user-attachments/assets/ffb5ea35-bc29-4160-b79c-93612630ea05)  

Rancangan konseptual dipakai untuk menggambarkan secara detail struktur basis data dalam bentuk logis. Struktur ini independen terhadap semua software maupun struktur data storage tertentu. Berikut merupakan contoh rancangan konseptual :  
![image](https://github.com/user-attachments/assets/bcc9affd-3330-408b-b12b-e9df4d85bed2)  
![image](https://github.com/user-attachments/assets/e3337f61-69d7-44d2-a74e-e32f882dbd33)

Entitas merupakan objek yang mewakili sesuatu dalam dunia nyata dan dapat dibedakan antara satu dengan lainnya (unique). Entitas memiliki atribut yang mendeskripsikan karakteristik dari objek tersebut. Entitas terbagi menjadi dua jenis, yaitu strong entity dan weak entity. Berikut merupakan contoh dari entitas :  
![image](https://github.com/user-attachments/assets/aea0e9c4-283c-49bb-83ca-1afe6d5dc89e)  

Macam-macam tipe atribut :  
- Atribut kunci (primary key), satu atau beberapa atribut yang mempunyai nilai unik sehingga dapat digunakan untuk membedakan data pada suatu baris/record dengan baris lain pada suatu entitas.
- Atribut bernilai tunggal, atribut yang memiliki hanya satu nilai.  
- Atribut bernilai banyak, atribut yang memiliki sekelompok nilai.  
- Atribut komposit, atribut yang terdiri atas beberapa atribut yang lebih kecil.  
- Atribut derivatif, atribut yang diperoleh dari pengolahan / penurunan atribut lain.

Notasi atribut :  
![image](https://github.com/user-attachments/assets/b2afb633-57ca-4e4f-a747-5fd91a17bb7d)  

Macam-macam Primary Key :  
- Superkey: satu atau gabungan beberapa atribut yang dapat membedakan setiap baris data dalam sebuah tabel secara unik.
Contoh Superkey untuk entitas mahasiswa : NIM, Nama, Alamat, Jenis Kelamin.
- Candidat Key: superkey yang jumlah atributnya paling sedikit.
Contoh Candidat Key untuk entitas pegawai : Nama (jika dapat dijamin kalau tidak ada nama yang sama antara satu baris dengan baris yang lain), NIP.
- Primary key: suatu candidat key yang dipilih menjadi kunci utama karena sering dijadikan acuan untuk mencari informasi, ringkas, menjadi keunikan suatu baris.  
Contoh Primary Key untuk entitas mahasiswa : NIM antara satu mahasiswa dengan mahasiswa lain pasti berbeda. 

Relation dan Cardinality  
![image](https://github.com/user-attachments/assets/7592542a-9fae-4e60-afb8-fa46e653329a)  

Relasi adalah hubungan antara beberapa entitas.  
![image](https://github.com/user-attachments/assets/cf1d37d7-f81e-4463-b23b-c350e27db99a)  

Derajat relasi adalah jumlah entitas yang saling berhubungan dalam sebuah relasi. Terdapat 3 macam derajat relasi antara lain :  
- Unary -> 1 entitas  
![image](https://github.com/user-attachments/assets/1036dc92-4cd8-4d0c-a8ea-ab349114e427)

- Binary -> 2 entitas
![image](https://github.com/user-attachments/assets/a86f0686-edc7-4f8e-8d1e-1f01211f25a9)

- Ternary -> lebih dari 2 entitas
![image](https://github.com/user-attachments/assets/dd99c4af-d70d-4102-9b30-b399484275b2)

Kardinalitas One-to-one  
![image](https://github.com/user-attachments/assets/7d2e32f8-d6c6-4381-a2b4-b51acdaf8268)  

Kardinalitas One-to-many  
![image](https://github.com/user-attachments/assets/528e70ae-6ba7-4155-8ca3-bf7e68102656)  

Kardinalitas Many-to-many  
![image](https://github.com/user-attachments/assets/54002aec-c45a-4610-951a-bbd7c91372ab)  

Partisipasi Entitas ada 2 macam, yaitu Partisipasi Total dan Partisipasi Parsial :   
![image](https://github.com/user-attachments/assets/3cb4e35e-531f-4846-9863-4fe11536fe9e)  
![image](https://github.com/user-attachments/assets/1fef2e61-880b-4412-83d0-0cb14cc52916)  

## BAB 4 Physical Data Model
## BAB 5 Normalisasi
## BAB 6 Data Definition Language
## BAB 7 Data Manipulation Language
## BAB 8 Aljabar Relasional dan Join
## BAB 9 Nested Query
