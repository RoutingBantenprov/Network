share tentang cara routing static pada mikrotik
### A. Pengertian

Routing static adalah jenis routing yang dilakukan admin/pengelola jaringan untuk mengkonfigurasi informasi tentang jaringan yang dituju secara manual. Ciri-ciri routing statis adalah sebagai berikut:

jalur spesifik ditentukan oleh admin jaringan
pengisian tabel routing dilakukan secara manual oleh admin jaringan
biasanya digunakan untuk jaringan berskala kecil

### Cara kerja routing statis ada 3 bagian yaitu:
1. Konfigurasi router yang dilakukan oleh admin jaringan
2. Router melakukan routing berdasarkan informasi yang diterima dari tabel routing
3. Admin Jaringan menggunakan perintah ip route secara manual untuk konfigurasi router dengan routing statis dan routing statis berguna untuk melewatkan paket data yang ada pada jaringan.

### Ada beberapa parameter yang ada pada routing, yakni:
1. Destination, adalah alat tujuan dan network mask dan biasanya diisi dengan 0.0.0.0/0 untuk semua jaringan
2. Gateway adalah datagram yang dapat dicapai melalui antarmuka
3. Pref. Source adalah alamat tujuan paket dan meninggalkan roter melalui alamat IP
4. Distance (0-255) adalah jarak administrator jaringan dari router

### Keuntungan menggunakan Routing static
1. Meringankan kinerja processor router
2. Tidak ada bandwidth yang diguanakn untuk pertukaran informasi dari tabel isi routing pada saat pengiriman paket
3. Routing statis lebih aman dibandingkan routing dinamis
4. Routing Statis kebal dari segala usaha hacker untuk men-spoof dengan tujuan membajak traffik

### Kerugian Menggunakan routing static
Administrator jaringan harus mengetahui semua informasi dari masing masing router yang digunakan
Hanya dapat digunakan untuk jaringan berskala kecil
Admisnistrasinya cukup rumit dibanding routing dinamis, terlebih jika banyak router yang harus dikonfigurasi secara manual
Rentan terhadap kesalahan saat entri data routing statis yang dilakukan secara manual.


## B. Latar Belakang

        Banyak perusahaan yang besar yang membutuhkan jaringan, dan dalam perusaahan tersebut kadang kala tidak hanya terdiri dari satu jaringan karena itu untuk meneruskan data dari jaringan satu k jaringan yang lain kita memerlukan yang namanya routing, dalam routing cara paling simpel dan bisa digunakan agar kita bisa memasukan network secara manual adalah routing static

## C. Maksud dan Tujuan
dapat melakukan routing static menggunakan mikrotik
dapat menerapkan fungsi routing pada sebuah jaringan
dapat mengetahui cara kerja routing static

## D. Jangka Waktu
Sekitar 3 jam

## E. Alat dan Bahan
1. 4 mikrotik 
2. 3 kabel LAN
3. LAPTOP dengan sistem operasi bebas 
4. Aplikasi winbox

## F. Tahapan Pelaksanaan Kegiatan
sambungkan semua mikrotik menjadi seperti topologi berikut :
![diagram](https://1.bp.blogspot.com/-R5zLF7qE_qg/V9GAmo26xdI/AAAAAAAAB3E/bjqKCeSfIs0oHPoWg9qNZsI2na51rmRDACLcB/s1600/Diagram2.png)   
### Pertama kita sambungkan pada mikrotik pertama setelah itu kita konfigurasi mikrotik menggunakan winbox

### kita setting IP pada mikrotik pertama dengan masuk ke menu IP setelah itu address :

setelah itu klik ikon plus (+) lalu tulis IP sesuai dengan topologi yang sudah di buat di atas :
![](https://3.bp.blogspot.com/-Z8j8mzYQEqc/V9GBmHBcZfI/AAAAAAAAB3Q/5dNRLoT71FAsGEzvRyVn3O_YqBLnOOJXQCLcB/s1600/Screenshot%2Bfrom%2B2016-09-08%2B13-46-34.png)
dan hasil nya akan seperti ini jika IP berhasil ditambahkan :

![](https://4.bp.blogspot.com/-rh7HR5myo4s/V9GCAGnm6nI/AAAAAAAAB3U/mdggy6feRWkoQ5GoNri1NPRVsmAT5J0tgCLcB/s1600/Screenshot%2Bfrom%2B2016-09-08%2B13-11-28.png)

Setelah itu untuk melakukan routing static kita masuk ke menu IP >> routes 

![](https://1.bp.blogspot.com/-HXWEuqqD6hg/V9GDAMts8qI/AAAAAAAAB3k/2_BqQpp4Gqc0PPdem6dm6TRb3CHRAj5zQCLcB/s1600/Screenshot%2Bfrom%2B2016-09-08%2B13-50-01.png)
 
lalu kita klik ikon plus (+), lalu kita tambahkan IP network yang mau di routing dan gateway nya, sesuai dengan topologi di atas kita tambahkan network 192.168.2.0 dengan gateway 192.168.1.2 :

Lalu kita tambahkan lagi untuk menambahkan network 192.168.3.0, untuk gateway tetap menggunakan 192.168.1.2

Dan hasilnya akan seperti ini setalah kita tambahkan dua network tadi ke IP >> route

Jika pada mikrotik sudah di setting IP sekaligus routing staticnya. sekarang kita masuk ke mikrotik 2
seperti tadi kita tambahkan IP sesuai dengan toplogi, untuk ether 1 kita buat agar satu jaringan dengan mikrotik 1 tadi :

Setelah itu kita tambahkan lagi untuk ether 2, setting IP sesuai dengan topologi di atas :

Dan hasilnya setting IP akan menunjukan seperti berikut :

jika IP sudah disetting seperti pada mikrotik 1 tadi kita juga konfigurasi routing static nya pada mikrotik 2 dengan menambahkan network 192.168.3.0 lalu gatewaynya 192.168.2.3

Setelah untuk routing ke mikroik 1 kita gunakan network 0.0.0.0 dengan gateway 192.168.1.1

dan hasil dari routing static yang kita tambahkan tadi akan seperti berikut :

Jika pada mikrotik 2 konfigurasi sudah selesai sekarnga kita masuk ke Mikrotik 3
Seperti pada mikrotik sebelumnya pertama kita konfigurasi IP nya
Pada ether 1 kita setting agar satu jaringan denan ether 2 di mikrotik 2 sesuai dengan topologi di atas tadi :
 

 Lalu tambahkan lagi untuk ether 2 seperti topologi di atas tadi :

dan hasilnya dari konfigurasi IP tadi akan seperti berikut :

setelah pada konfigurasi IP selesai sekarang kita konfigurasi routing staticnya, dengan hanya menambahkan network 0.0.0.0/0 dan gateway 192.168.2.3

Dan nanti hasilnya akan seperti beriikut :

Karena konfigurasi IP dan routing pada mikrotik 3 sudah selesai sekarng kita konfigurasi pada mikrotik 4
seperti pada mikrotik yang lain lain pertama kita konfigurasi IPnya terlebih dahulu seperti pada topologi yang di buat tadi :

Dan setelah di OK hasilnya akan seperti berikut :
 

Setelah itu kita lakukan routing staticnya, dengan hanya menambahkan 0.0.0.0/0 dan gateway 192.168.3.3

Setelah itu hasil dari yang ditambahakan tadi akan seperti berikut :

sekarang konfigurasi routing static pada 4 miktotik telah selesai, untuk tes kita bisa melakukan ping dari mikroti 4 ke mikrotik 1 atau sebaliknya :






G. Hasil Kegiatan

        Hasilnya kita berhasil melakukan ping dari mikrotik 4 ke mikrotik 1 atau sebaliknya, walau pun kdu mikrotik itu memiliki IP dengan jaringan yang berbeda dan harus melewati beberapa nexhop tapi tetap bisa berkomunikasi setelah di routing



H. Kesimpulan

         Kesimpulanya untuk melakukan routing static ini pada mikrotik pertama kita ibaratkan mikrotik paling atas sehingga kita melakukan routing static dengan cara memasukan network yang bebeda satu per satu, sedangkan pada mikrotik 4 kita untuk merouting kita tinggal memasukan network 0.0.0.0/0, disitu bisa dimpulkan untuk menuju ke bawah kita masukan satu per satu network nya sedangkan untuk ke atas kita masukan 0.0.0.0/0

