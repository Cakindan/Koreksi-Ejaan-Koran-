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
&nbsp;Proyek kami memberi solusi dari permasalahan sehari-hari dalam hal ejaan EYD Bahasa Indonesia. Melalui proyek tersebut, user dapat memberikan kumpulan kata atau kalimat  sebagai input dari web-app “Koran”. Berdasarkan input tersebut, virtual machine dan beberapa komponen lain dari azure akan menyortir dan memberikan hasil output berupa ejaan yang sesuai dengan EYD Bahasa Indonesia kepada user. Berikut adalah penjelasan prosesnya secara detail.

&nbsp;User dapat mengakses dan menginput data berupa kumpulan kalimat yang ingin dikoreksi ke dalam platform Virtual Network “Koran”. Platform yang diakses user berupa Public Subnet dengan basis Azure Static : Webapps SPA. Guna dari Azure Static : WebApps SPA sendiri dalam proyek kami adalah sebagai wadah hostingan website dengan berbagai keunggulan seperti telah terintegrasi ke dalam API dari Azure Functions yang memiliki fleksibilitas dalam mengubah konten statis seperti dalam bentuk HTML, CSS, JavaScript dan Images untuk menampung data input dari user. Platform ini bertindak sebagai inti front-end dari proyek kami.

&nbsp;Setelah diinput, data tersebut akan diolah dan diproses dengan Function App Azure. Dalam proses pengolahannya, proyek ini akan menggunakan 2 Function App berbeda dengan fungsinya masing-masing. Pertama adalah Function App Trigger Detect Language, fungsi ini merupakan tahap awal pengolahan data sebelum kita lanjut ke pengoreksian kalimat. Dalam fungsi ini, data yang telah diinput akan difilter apakah sesuai dengan ketentuan pengoreksian EYD (dalam hal ini adalah kalimat input merupakan Bahasa Indonesia). Bila gagal diidentifikasi sebagai Bahasa Indonesia, maka data tersebut akan dipindahkan ke dalam Azure Container Service. Azure Container Service sendiri berguna sebagai basis docker yang akan menangkap hasil fungsi input.

&nbsp;Fungsi kedua adalah Function App Trigger AI Spell Check. Fungsi ini merupakan tahapan lanjutan bila data memenuhi ketentuan yang ada. Fungsi Spell Check berfungsi sebagai basis penentuan bagian mana saja dalam kalimat input yang harus dikoreksi. Bila telah ditentukan, maka data tersebut akan dikerahkan ke Virtual Machine melalui Azure Load Balancer untuk diolah dan dikoreksi sesuai dengan EYD Bahasa Indonesia. Load balancer bertugas untuk mengatur beban kerja pada Virtual Machine. Data yang masuk akan diolah otomatis oleh load balancer dan dibagi ke Virtual Machine yang ada sesuai kondisi layanan. Virtual Machine yang tersedia merupakan Private Subnet dari virtual network proyek ini. Setelah selesai diolah dan dikoreksi menggunakan Virtual Machine, maka hasil tersebut akan dikembalikan lagi ke antarmuka Azure Static: Webapps SPA untuk ditampilkan pada user. Seluruh hasil proses pada tahapan proyek ini akan dicatat dalam cache yang tersedia. Basis dari cache yang kami pilih adalah Azure Cosmos DB Log.
