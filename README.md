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
Physical Data Model (PDM) merupakan pemodelan data secara teknis yang dirancang untuk mendukung program komputer dan programmer yang menggunakan basis data. PDM bersifat platform-dependent, yaitu tergantung pada hardware, software, dan tool.

Perbedaan CDM vs PDM :  
- CDM : Memodelkan informasi bisnis dan aturan bisnis, platform independent.
- PDM : Memodelkan implementasi teknis, platform dependent.

Fokus perubahan CDM menjadi PDM :  
![image](https://github.com/user-attachments/assets/c433cff5-d00c-4ba0-aa73-f44f2eca7752)  

Entitas Lemah : PRIMARY KEY Entitas Kuat sebagai PRIMARY KEY dan FOREIGN KEY Entitas Lemah  
![image](https://github.com/user-attachments/assets/0fe8273c-e416-4eca-88fc-a5b59271949c)

Relasi One-to-one :  
- Periksa partisipasi dari dua entitas: partisipasi total atau parsial.
Suatu entitas dianggap lebih “berat” timbangannya apabila mempunyai partisipasi total, Suatu entitas dianggap lebih “ringan” timbangannya apabila mempunyai partisipasi parsial.
- Jika partisipasi dua entitas berbeda:
Tambahkan primary key dari sisi yang lebih “ringan” ke sisi (entitas) yang lebih “berat”.
- Jika partisipasi dua entitas sama
dua entitas tersebut boleh digabung menjadi satu tabel

![image](https://github.com/user-attachments/assets/4bd62570-df75-49ee-a10e-00b26d538f5d)  

Relasi One-to-Many :  
- Tambahkan PRIMARY KEY dari Entitas yang memiliki maksimum relasi (Cardinality) one ke Entitas yang memiliki maksimum relasi (Cardinality) many 
- Jadikan (1) sebagai FOREIGN KEY

![image](https://github.com/user-attachments/assets/8a0d0c6f-616e-431b-9101-a65006df5116)  

Relasi Many-to-Many :  
- Untuk setiap relasi binary M:N, buatlah tabel baru R dengan atribut seluruh simple atribut yang terdapat pada relasi biner tersebut. 
- Tambahkan primary key yang terdapat pada kedua sisi ke tabel R. 
- Kedua foreign key yang didapat dari kedua sisi tersebut digabung menjadi satu membentuk primary key dari tabel R

![image](https://github.com/user-attachments/assets/ad035465-2ad1-4f6f-b828-728ab1f642f1)

CDM ke PDM : Secara teknis PDM adalah proses menambahkan constraint FOREIGN KEY ke tabel rujukan.

## BAB 5 Normalisasi
Normalisasi adalah proses pembentukan struktur basis data sehingga sebagian besar ambiguity bisa dihilangkan. Normalisasi biasanya digunakan untuk memastikan bahwa basis data yang dibuat berkualitas baik. Tahap Normalisasi dimulai dari tahap paling ringan (1NF) hingga paling ketat (5NF). Biasanya hanya sampai pada tingkat 3NF atau BCNF karena sudah cukup memadai untuk menghasilkan tabel-tabel yang berkualitas baik.  

Sebuah tabel dikatakan baik (efisien) atau normal jika memenuhi 3 kriteria sbb:  
![image](https://github.com/user-attachments/assets/8ae3951c-c8d4-47af-bfab-da9c2d17f4d9)  

Jika kriteria ketiga (BCNF) tidak dapat terpenuhi, maka paling tidak tabel tersebut tidak melanggar Bentuk Normal tahap ketiga (3rd Normal Form / 3NF).

Tabel Universal (Universal / Star Table) : sebuah tabel yang merangkum semua kelompok data yang saling berhubungan, bukan merupakan tabel yang baik. Jenis tabel ini tidak diinginkan pada konsep Basis Data Relasional. Berikut merupakan contoh tabel universal :  

![image](https://github.com/user-attachments/assets/e3b70311-017b-4a27-9888-f948b3eaad5d)  

Functional Dependency :  
Notasi : A ⭢ B
A dan B adalah atribut dari sebuah tabel. Berarti secara fungsional A menentukan B atau B tergantung pada A, jika dan hanya jika ada 2 baris data dengan nilai A yang sama, maka nilai B juga sama.  
![image](https://github.com/user-attachments/assets/1dd63a29-5793-4dba-b50c-7622434223d2)  

Berikut merupakan contoh Functional Dependency :  
![image](https://github.com/user-attachments/assets/85340c05-7f8a-492e-8d1a-ed159092c910)  
Functional Dependency dari tabel nilai :  
NRP ⭢ namaMhs : karena untuk setiap nilai yang sama, maka nilai namaMhs juga sama.  
{Namakul, nrp} ⭢ NiHuruf : Karena attribut Nihuruf tergantung pada Namakul dan nrp secara bersama-sama. Dalam arti lain untuk Namakul dan nrp yang sama, maka NiHuruf juga sama, karena Namakul dan nrp merupakan key (bersifat unik).  
![image](https://github.com/user-attachments/assets/90ce62d1-90f1-4938-8b47-6bde03695cfb)  

Berikut merupakan bentuk-bentuk normal :  
![image](https://github.com/user-attachments/assets/ce51672e-c408-4d0e-9a9a-33ec033d7933)  

Bentuk Normal Tahap Pertama (1st Normal Form / 1NF) : Bentuk normal 1NF terpenuhi jika sebuah tabel tidak memiliki atribut bernilai banyak (multivalued attribute), atribut composite atau kombinasinya dalam domain data yang sama. Setiap atribut dalam tabel tersebut harus bernilai atomic (tidak dapat dibagi-bagi lagi).  
![image](https://github.com/user-attachments/assets/abbbfb79-2f1b-429d-a468-8df1bdfea816)  
![image](https://github.com/user-attachments/assets/aa3ad704-2eb1-41f8-8912-d6d7ed51f3c5)  
![image](https://github.com/user-attachments/assets/1cff368e-a2d8-4fa1-b002-73cb111c7f15)  

Bentuk Normal Tahap Kedua (2nd Normal Form) : Bentuk normal 2NF terpenuhi dalam sebuah tabel jika telah memenuhi bentuk 1NF, dan semua atribut selain primary key, secara utuh memiliki Functional Dependency pada primary key. Sebuah tabel tidak memenuhi 2NF, jika ada atribut yang ketergantungannya (Functional Dependency) hanya bersifat parsial saja (hanya tergantung pada sebagian dari primary key). Jika terdapat atribut yang tidak memiliki ketergantungan terhadap primary key, maka atribut tersebut harus dipindah atau dihilangkan.  
![image](https://github.com/user-attachments/assets/7a21e14b-00f2-461e-aeae-b9102f8a19b6)  
![image](https://github.com/user-attachments/assets/5c290ad3-842b-4b52-a684-77c66131475d)  

Bentuk Normal Tahap Ketiga (3rd Normal Form /3NF) : Bentuk normal 3NF terpenuhi, jika telah memenuhi bentuk 2NF, dan jika tidak ada atribut yang bukan kunci memiliki ketergantungan transitif (tidak secara langsung) pada primary key.  
![image](https://github.com/user-attachments/assets/47c1a2c4-d7fb-43c8-81d7-348191d81c15)  

![image](https://github.com/user-attachments/assets/70966820-474a-4d7d-9184-d0f2f5e05a44)  

Boyce-Code Normal Form (BCNF) : Bentuk BCNF terpenuhi dalam sebuah tabel, jika untuk setiap functional dependency terhadap setiap atribut atau gabungan atribut dalam bentuk: X ⭢ Y maka X adalah super key. Tabel tersebut harus di-dekomposisi berdasarkan functional dependency yang ada, sehingga X menjadi super key dari tabel-tabel hasil dekomposisi. Setiap tabel dalam BCNF merupakan 3NF. Akan tetapi setiap 3NF belum tentu termasuk BCNF . BCNF merupakan perbaikan bagi 3NF yang anomali.  
![image](https://github.com/user-attachments/assets/eb011f51-7f1e-4d41-8a40-db2e30190f32)  
![image](https://github.com/user-attachments/assets/7029b060-d8be-4c01-9e56-94b236ffe0a0)  
![image](https://github.com/user-attachments/assets/2ffa5cd2-6b39-40ad-82f1-688a2a1026ed)  
![image](https://github.com/user-attachments/assets/8b78bf83-0668-47cf-bf1d-f7cb96d111d2)

## BAB 6 Data Definition Language
SQL adalah singkatan dari Structured Query Language, dalam bahasa inggris dibaca SEQUEL. SQL merupakan bahasa query standar yang digunakan untuk mengakses basis data relasional.  
Query adalah perintah atau instruksi yang digunakan untuk mengambil, memasukkan, memperbarui, atau menghapus data dalam basis data. Dalam konteks SQL, query digunakan untuk berinteraksi dengan database relasional, seperti mengambil data dari tabel dengan perintah `SELECT`, menambahkan data dengan `INSERT`, memperbarui data dengan `UPDATE`, atau menghapus data dengan `DELETE`.  
Syntax dalam pemrograman, termasuk SQL, adalah aturan atau tata cara penulisan kode yang harus diikuti agar komputer bisa memahami dan menjalankan perintah dengan benar. Dalam SQL, sintaks menentukan bagaimana perintah harus ditulis agar bisa dieksekusi oleh database. Jika sintaks salah, maka database akan mengembalikan error.

Penggunaan SQL :  
1. SQL sebagai bahasa administrasi basis data : SQL dipakai oleh Database Administrator untuk menciptakan serta mengendalikan pengaksesan basis data.
2. SQL sebagai bahasa query interaktif : Pengguna dapat memberikan perintah-perintah untuk mengakses data sesuai kebutuhan terutama yang diperlukan saat itu.
3. SQL sebagai bahasa pemrograman basis data : Pemrograman dapat menggunakan perintah-perintah SQL dalam aplikasi yang dibuat, guna mengakses basis data.
4. SQL sebagai bahasa klien : Klien dapat menjalankan aplikasi yang mengakses basis data yang ada di server.

Terdapat 6 Elemen SQL antara lain :  
- Pernyataan : Perintah SQL yang meminta sesuatu tindakan kepada DBMS; contoh: Alter, commit, create, delete, drop, grant, insert, revoke, rollback, select, update.
- Nama : Nama digunakan sebagai identitas bagi objek-objek pada DBMS. Contoh objek: tabel, kolom, pengguna, dll.  Contoh nama tabel: Pegawai.
- Tipe Data : Setiap data memiliki tipe data. Contoh tipe data: Char, integer, numeric, varchar, money, boolean, blob, serial, date, dll.
- Konstanta : Konstanta menyatakan nilai yang tetap. Contoh: 75, Jl. Teknik Kimia 25 Surabaya, dll.
- Ekspresi : Ekspresi adalah segala sesuatu yang menghasilkan nilai. Ekspresi digunakan untuk menghitung nilai. Contoh: harga_total = harga * jumlah_barang.
- Fungsi Bawaan : Fungsi bawaan: sebuah sub program yang menghasilkan suatu nilai jika dipanggil. Contoh: Min, AVG, dll.

Macam-Macam Kelompok Pernyataan SQL :  
1. Data Definition Language (DDL) : Untuk mendefinisikan objek-objek basis data, tabel, atribut, batasan-batasan terhadap atribut, serta hubungan antar tabel. Contoh : CREATE, ALTER, DROP.
2. Data Control Language (DCL) : Untuk mengendalikan pengaksesan data. Contoh : GRANT, REVOKE, LOCK TABLE.
3. Data Manipulation Language (DML) : Untuk memanipulasi data dalam basis data, misalkan untuk pengambilan, pemasukan, pengubahan, dan penghapusan. Contoh : SELECT, INSERT, DELETE, UPDATE.

Data Definition Language (DDL) adalah bahasa dalam DBMS yang digunakan untuk membuat atau mendefinisikan obyek-obyek di dalam database. Secara umum digunakan untuk membuat obyek pada table dan view.  

4 Macam DDL antara lain :  
1. DDL untuk Database, digunakan untuk membuat sebuah basis data.
   Syntax : `create database <nama database>`
   Contoh : `create database akademik`  
3. DDL untuk Tabel
   CREATE TABLE : Digunakan untuk membuat tabel beserta atribut-atributnya (kolom). Berikut merupakan syntax CREATE TABLE :
   ![image](https://github.com/user-attachments/assets/e1058f3d-a285-4519-ba66-fe7fc53b0f0e)
   ![image](https://github.com/user-attachments/assets/40ab7c6d-ccfa-4201-9d00-b499969b4195)

   ALTER TABLE : Digunakan untuk menambah, menghapus dan mengubah atribut (kolom) pada suatu tabel. Berikut merupakan syntax ALTER TABLE :
   ![image](https://github.com/user-attachments/assets/e45da320-3284-48de-9d58-60c372d792ec)
   ![image](https://github.com/user-attachments/assets/536febcc-4ec6-4625-9df4-83882bf21570)  
   ![image](https://github.com/user-attachments/assets/3b1c9656-0c33-49fd-92e9-7e12947cb3d6)
   ![image](https://github.com/user-attachments/assets/a4f42e7c-3a82-4cd0-b638-61f3e071f27c)

   DROP TABLE : Digunakan untuk menghapus tabel. Berikut merupakan syntax DROP TABLE :
   ![image](https://github.com/user-attachments/assets/f1eb26a6-7395-4693-a373-ec4335c62f9e)

5. DDL untuk View
   ![image](https://github.com/user-attachments/assets/b58a78ce-8139-4043-88aa-71de6ddf1ca6)  

7. DDL untuk Trigger / Stored Procedure : Trigger adalah sebuah obyek dalam database yang berupa prosedur yang merespon setiap kali terdapat proses modifikasi pada tabel. Proses modifikasi berupa Insert, Update, dan Delete. Berikut merupakan syntax DDL untuk Trigger :
   ![image](https://github.com/user-attachments/assets/0e18b34b-f9fe-424e-b200-dfccafb20d9e)

RENAME, digunakan untuk merubah nama dari suatu object (table,view,sequence atau synonim). Sebagai contoh, jika kita ingin MERUBAH NAMA tabel dept menjadi detail_dept, maka perintah yang harus dilakukan adalah :  
`RENAME dept TO detail_dept;`  

MEMASUKKAN DATA KE TABEL, jika sebuah tabel sudah selesai di create (terbentuk kolom), maka perlu diisi datanya (barisnya/Recordnya). Dengan menggunakan perintah DML pada SQL yaitu Insert. Berikut merupakan syntaxnya :  
`INSERT INTO tablename(field1, field2, field3,…) VALUES( val1, val2, val3, …..)`  
![image](https://github.com/user-attachments/assets/11900e4d-0dd8-47c3-a1ac-0f35a835502e)  

![image](https://github.com/user-attachments/assets/9da96c5d-86ce-43d6-b135-286619cae0fb)  

## BAB 7 Data Manipulation Language
## BAB 8 Aljabar Relasional dan Join
## BAB 9 Nested Query
