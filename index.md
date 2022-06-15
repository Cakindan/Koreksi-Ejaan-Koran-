# Beauty and the Beast

## Anggota

1. Farhan Dzaky Ananda - 19/440886/TK/48680
2. Thoriq Faisal Yahya - 19/444074/TK/49270
3. Attar Husna Fathiya - 19/440304/TK/48631
4. Iman Kahfi Aliza - 19/440887/TK/48681

## Project Senior Project TI

### Departemen Teknologi Elektro dan Teknologi Informasi, Fakultas Teknik, Universitas Gadjah Mada)

# Jawaban Modul 1

### 1. Nama Produk : Koreksi Ejaan (Koran)
# Link: koran.azurewebsites.net

### 2. Jenis Produk : Aplikasi Web

### 3. Latar Belakang : Di dunia digital, perkembangan penulisan berbagai hal seperti artikel, jurnal, dan blog menjadi meningkat dengan cepat. Akan tetapi, dalam penulisan panjang yang lebih dari 1000 kata, menjadi tantangan tersendiri dalam hal spelling check atau pengecekan penulisan ejaan kata. Terlebih lagi KBBI yang diperbarui setiap waktu juga terkadang menyulitkan untuk mencari tahu kata mana yang tepat.

### 4. Rumusan Permasalahan : Bagaimana cara untuk menciptakan aplikasi berbasis web untuk mengecek ejaan yang sesuai dengan KBBI?

### 5. Ide Solusi : Dari permasalahan di atas, kami tertarik untuk mengembangkan aplikasi berbasis website yang berguna untuk melakukan koreksi ejaan terhadap sebuah penulisan. Dari website tersebut dapat digunakan untuk melakukan koreksi ejaan pada sebuah teks atau artikel, cukup dengan paste teks dalam textbox.

### 6. Analisis Kompetitor : 
A. Kompetitor 1 : SIPEBI 
![image](https://user-images.githubusercontent.com/55296421/158182135-97ab1bda-514b-4ca5-b235-0ff7890b5c82.png)
B. Kompetitor 2 : U-TAPIS
![image](https://user-images.githubusercontent.com/55296421/158182259-876edff6-a720-4b22-9cc0-c66589164999.png)
C. Kompetitor 3 : ejaan.id
![image](https://user-images.githubusercontent.com/55296421/158182049-5671d1e9-5542-4ceb-9345-c1c093ee09a2.png)

### SDLC
Metodologi yang digunakan: Waterfall 

Alasan pemilihan metodologi:
Metodologi Waterfall sangat cocok untuk kami implementasikan. Metode ini memberi ruang tim kami untuk memaksimalkan pengembangan aplikasi dalam tiap tahap pengembangan. Tidak hanya itu, metodologi ini juga sesuai dengan timeline Gantt-Chart yang telah dirancang sebelumnya.

1. Tujuan dari Produk:
Aplikasi berbasis website yang berguna untuk melakukan koreksi ejaan terhadap sebuah penulisan. Dari website tersebut dapat digunakan untuk melakukan koreksi ejaan pada sebuah teks atau artikel, cukup dengan paste teks dalam textbox.
2. Pengguna potensial dari produk dan kebutuhan para pengguna tersebut:
Setelah dianalisis, Web Application ini akan berguna dalam pasar yang berhubungan dengan edukasi dan marketing. Dalam pasar tersebut, para pengguna tidak jarang menghadapi tulisan atau literatur yang harus mereka rancang. Untuk meminimalisir kesalahan dalam ejaan, pengguna dapat memaksimalkan fitur dari aplikasi berbasis website ini.
3. Use Case Diagram:
![image](https://user-images.githubusercontent.com/55296421/158185128-7a3c0183-44ff-4776-a09f-2c7124e7b761.png)

4. Functional Requirements:
![image](https://user-images.githubusercontent.com/55296421/158185159-75e9999e-c149-4621-a80b-94d9afc96fcc.png)

5. Entity Relationship Diagram:
![image](https://user-images.githubusercontent.com/55296421/158185200-36d15fe7-32d0-43c8-b9e8-90b5b473d19b.png)

6. Low Fidelity Wireframe
![image](https://user-images.githubusercontent.com/55296421/158185285-d702f083-fac9-4bed-a59c-b7dfc02f5af2.png)
![image](https://user-images.githubusercontent.com/55296421/158185333-0bbddfc4-4070-4144-b9cb-9070e38397b0.png)
![image](https://user-images.githubusercontent.com/55296421/158185376-a6209222-7e82-4291-8aa4-29e880077ba4.png)
https://www.figma.com/file/ZIYHdBiVIufHFXcABgMu44/Koran-UI%2FUX?node-id=0%3A1
7. Gantt-Chart Project
![image](https://user-images.githubusercontent.com/55296421/158185498-e7a7bf28-b6a5-4185-870c-51f55964d47e.png)

### Skematik Arsitektur Layanan Azure:
![azure drawio](https://user-images.githubusercontent.com/55296421/164015934-822c6832-b767-403d-ade4-6e128310ec58.png)

&nbsp;&nbsp;&nbsp;&nbsp;Proyek kami memberi solusi dari permasalahan sehari-hari dalam hal ejaan EYD Bahasa Indonesia. Melalui proyek tersebut, user dapat memberikan kumpulan kata atau kalimat  sebagai input dari web-app “Koran”. Berdasarkan input tersebut, virtual machine dan beberapa komponen lain dari azure akan menyortir dan memberikan hasil output berupa ejaan yang sesuai dengan EYD Bahasa Indonesia kepada user. Berikut adalah penjelasan prosesnya secara detail.

&nbsp;&nbsp;&nbsp;&nbsp;User dapat mengakses dan menginput data berupa kumpulan kalimat yang ingin dikoreksi ke dalam platform Virtual Network “Koran”. Platform yang diakses user berupa Public Subnet dengan basis Azure Static : Webapps SPA. Guna dari Azure Static : WebApps SPA sendiri dalam proyek kami adalah sebagai wadah hostingan website dengan berbagai keunggulan seperti telah terintegrasi ke dalam API dari Azure Functions yang memiliki fleksibilitas dalam mengubah konten statis seperti dalam bentuk HTML, CSS, JavaScript dan Images untuk menampung data input dari user. Platform ini bertindak sebagai inti front-end dari proyek kami.

&nbsp;&nbsp;&nbsp;&nbsp;Setelah diinput, data tersebut akan diolah dan diproses dengan Function App Azure. Dalam proses pengolahannya, proyek ini akan menggunakan 2 Function App berbeda dengan fungsinya masing-masing. Pertama adalah Function App Trigger Detect Language, fungsi ini merupakan tahap awal pengolahan data sebelum kita lanjut ke pengoreksian kalimat. Dalam fungsi ini, data yang telah diinput akan difilter apakah sesuai dengan ketentuan pengoreksian EYD (dalam hal ini adalah kalimat input merupakan Bahasa Indonesia). Bila gagal diidentifikasi sebagai Bahasa Indonesia, maka data tersebut akan dipindahkan ke dalam Azure Container Service. Azure Container Service sendiri berguna sebagai basis docker yang akan menangkap hasil fungsi input.

&nbsp;&nbsp;&nbsp;&nbsp;Fungsi kedua adalah Function App Trigger AI Spell Check. Fungsi ini merupakan tahapan lanjutan bila data memenuhi ketentuan yang ada. Fungsi Spell Check berfungsi sebagai basis penentuan bagian mana saja dalam kalimat input yang harus dikoreksi. Bila telah ditentukan, maka data tersebut akan dikerahkan ke Virtual Machine melalui Azure Load Balancer untuk diolah dan dikoreksi sesuai dengan EYD Bahasa Indonesia. Load balancer bertugas untuk mengatur beban kerja pada Virtual Machine. Data yang masuk akan diolah otomatis oleh load balancer dan dibagi ke Virtual Machine yang ada sesuai kondisi layanan. Virtual Machine yang tersedia merupakan Private Subnet dari virtual network proyek ini. Setelah selesai diolah dan dikoreksi menggunakan Virtual Machine, maka hasil tersebut akan dikembalikan lagi ke antarmuka Azure Static: Webapps SPA untuk ditampilkan pada user. Seluruh hasil proses pada tahapan proyek ini akan dicatat dalam cache yang tersedia. Basis dari cache yang kami pilih adalah Azure Cosmos DB Log.


### Framework: Flask
- Flask adalah kerangka kerja web mikro yang ditulis dengan PythonTeknologi Kecerdasan Buatan dan Pembelajaran Mesin juga akan berkembang
- Termasuk dalam microframework karena tidak memerlukan library tertentu 
- Flask tidak memiliki lapisan abstraksi database, validasi formulir, atau komponen lain di mana library pihak ketiga yang sudah ada menyediakan fungsi umum.
- Namun, Flask mendukung ekstensi yang dapat menambahkan fitur aplikasi seolah-olah diimplementasikan di Flask itu sendiri.

### Algoritma
![Koreksi Ejaan](https://user-images.githubusercontent.com/55296421/173763484-7a5d7275-dd99-479d-a146-49e62e731018.png)

### Pengujian Software
Problem: Penulisan berbagai hal dalam digital terus berkembang pada penulisan yang lebih dari 1000 kata, menjadi tantangan dalam spelling check. selain itu KBBI yang diperbarui setiap waktu juga terkadang menyulitkan untuk mencari tahu kata mana yang tepat. 

Dari problem tersebut kami mengembangkan aplikasi berbasis website yang berguna untuk melakukan koreksi ejaan terhadap sebuah penulisan. Dari website tersebut dapat digunakan untuk melakukan koreksi ejaan pada sebuah teks cukup dengan paste teks dalam textbox.

SOP dalam Tabular Representation: 
![image](https://user-images.githubusercontent.com/55296421/173763970-790992a6-6ce2-4e8a-b609-e91ce0ad4ae2.png)
Persiapan tes
  1. Hitung total test case
    Total Test Case = 
    (Total Working Time) x (Tester) / 
    (Mean Time per Test Case)
    = 45 minutes x 1 / 3 minutes 
    = 15 test case

  2. Hitung Threshold
   Threshold = 0.5 / jumlah test
   = 0.5 / 15
   = 0.0333

Tabel Test Case Estimation & Allocation
![image](https://user-images.githubusercontent.com/55296421/173764262-67e8bce6-9b72-4006-98b8-76fb9caef976.png)

![image](https://user-images.githubusercontent.com/55296421/173765187-8f390589-eed0-4344-8f68-993d4fad030f.png)
![image](https://user-images.githubusercontent.com/55296421/173765251-23bb5a82-0369-45db-9ee6-4f749a6d2288.png)
![image](https://user-images.githubusercontent.com/55296421/173765285-90484f20-0989-4b3e-b232-ee209a2fa575.png)

Tabel Failure Data( Failure data menggunakan Reliability Demo Chart (RDC) dengan FIO: jumlah error / (total test case x mean time per test case) = 4/ (15 x 3 minutes) = 0.0889 failure/1 minute)
![image](https://user-images.githubusercontent.com/55296421/173764386-32b44c89-f452-4ea4-bf23-c7618aa4f683.png)

A. grafik perbandingan plot dari failure number dengan measure yang belum dan sudah dinormalisasi.
![image](https://user-images.githubusercontent.com/55296421/173764469-50685abf-d161-476e-bf92-601a7437a937.png)

B. Reliability Demonstration Chart dengan menggunakan Developers Risk (α) = 10%, Customers Risk (β) = 10%, dan Discrimination (γ) = 2

- Mencari nilai A dan B
A=ln 1- α 	B=ln 1 -  
A=ln 0.11- 0.1     	     B=ln 1 - 0.10.1 
A= -2.197  	     B= 2.197

Mencari batas area accept dengan continue dan batas area reject dengan continue.
Batas area accept dengan continue
Tn=A1-γ- ln  1-γ n

Tn=-2.1971-2- ln 2 1-2 4

Tn= 2.197- (-0.693) 4

Tn= 2.197+ 2.772

Tn= 4.969 

Dari rumus diatas akan diketahui titik batas area accept dengan continue (Tn,n) yaitu (4.969, 4).

Batas area reject dengan continue

Tn=B1-γ- ln  1-γ n

Tn=- 2,1971-2- ln 21-24

Tn= -2.197- (-0.693) 4

Tn= -2.197 + 2.772

Tn= 0.575

Dari rumus diatas akan diketahui titik batas area reject dengan continue (Tn,n) yaitu (0.575, 4).

C. Mencari nilai intersep batas accept dengan garis horizontal n=0 dengan intersep batas reject dengan vertikal Tn=0. 

Nilai dapat dicari menggunakan rumus Tn yang sebelumnya telah dijabarkan. Dengan memasukkan nilai n = 0 untuk batas area accept dengan continue dan Tn = 0 untuk batas area reject dengan continue, maka akan didapatkan

Tn=-2.1971-2  → Tn = 2.197 , untuk batas area accept dengan continue → (2.197, 0)
n=  2.197ln2	→ n = 3.1703 , untuk batas area reject dengan continue → (0, 3.1703)

D. Reliability Demonstration Chart(RDC)
![image](https://user-images.githubusercontent.com/55296421/173764730-152f01a7-cad1-41ea-9a8c-8500b54ca5ce.png)

### Pengujian Kualitas Perangkat Lunak
![image](https://user-images.githubusercontent.com/55296421/173764843-b5eb4fce-05a8-4b15-b467-8ba351d445a2.png)

kelompok kami mengambil 3 karakteristik yakni :
1. Functional Suitability
Karakteristik yang mengukur sejauh mana sistem menyediakan fungsi yang memenuhi kebutuhan ketika digunakan dalam kondisi tertentu.
Mengukur sukses atau gagal, yang mana test case menggunakan skala guttman. Skala ini digunakan untuk mengetahui jawaban yang riil terhadap suatu permasalahan. Dalam pengujian ini software dikatakan baik apabila perhitungan item fungsi mendekati 1 dengan rumus :
X = I / P
I : Jumlah fungsi yang berhasil
P : jumlah fungsi yang dirancang
X = 11 / 15
= 0.733

2. Performance Efficiency
Karakteristik yang mengukur kinerja sistem yang relatif terhadap sumber daya yang digunakan dalam kondisi tertentu dimana terdapat subkarakteristik :
Performa dan rating dari web dapat dipertimbangkan untuk menganalisis skor karakteristik dari aturan Yslow (memeriksa semua komponen kinerja halaman  dan memberikan saran perbaikan) dan Pagespeed (Kecepatan halaman web).
Pada web yang tim kami kembangkan waktu respon webnya stabil selama : 5000ms atau 5 detik.
![image](https://user-images.githubusercontent.com/55296421/173764986-2f68a52b-95b1-41e9-9c65-50c1e9f61cf8.png)

3. Portability
Karakteristik untuk mengukur keefektifan dan efisiensi dimana sebuah sistem terbilang baik apabila dapat berjalan di browser yang berbeda, hardware yang berbeda, dan sistem operasi yang berbeda.
Untuk produk dari tim kami belum dikatakan baik sepenuhnya karena website yang kami kembangkan merupakan website non responsive sehingga ketika dijalankan pada hardware selain desktop dapat berjalan namun tidak maksimal. Contohnya interface pada smartphone seperti gambar di bawah ini.
