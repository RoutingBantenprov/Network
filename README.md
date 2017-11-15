# share tentang cara routing static pada mikrotik
### A. Pengertian

Routing static adalah jenis routing yang dilakukan admin/pengelola jaringan untuk mengkonfigurasi informasi tentang jaringan yang dituju secara manual. Ciri-ciri routing statis adalah sebagai berikut:

### 1. jalur spesifik ditentukan oleh admin jaringan
### 2. pengisian tabel routing dilakukan secara manual oleh admin jaringan
### 3. biasanya digunakan untuk jaringan berskala kecil

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
1. Administrator jaringan harus mengetahui semua informasi dari masing masing router yang digunakan
2. Hanya dapat digunakan untuk jaringan berskala kecil
3. Admisnistrasinya cukup rumit dibanding routing dinamis, terlebih jika banyak router yang harus dikonfigurasi secara manual
4. Rentan terhadap kesalahan saat entri data routing statis yang dilakukan secara manual.


## B. Latar Belakang

        Banyak perusahaan yang besar yang membutuhkan jaringan, dan dalam perusaahan tersebut kadang kala tidak hanya terdiri dari satu jaringan karena itu untuk meneruskan data dari jaringan satu k jaringan yang lain kita memerlukan yang namanya routing, dalam routing cara paling simpel dan bisa digunakan agar kita bisa memasukan network secara manual adalah routing static

## C. Maksud dan Tujuan

1. dapat melakukan routing static menggunakan mikrotik
2. dapat menerapkan fungsi routing pada sebuah jaringan
3. dapat mengetahui cara kerja routing static

## C. Alat Pendukung
1. 4 mikrotik 
2. 3 kabel LAN
3. LAPTOP dengan sistem operasi bebas 
4. Aplikasi winbox

## D. Tahapan 
1. sambungkan semua mikrotik menjadi seperti topologi berikut :
   ![diagram](https://1.bp.blogspot.com/-R5zLF7qE_qg/V9GAmo26xdI/AAAAAAAAB3E/bjqKCeSfIs0oHPoWg9qNZsI2na51rmRDACLcB/s1600/Diagram2.png)   
2. Pertama kita sambungkan pada mikrotik pertama setelah itu kita konfigurasi mikrotik menggunakan winbox

3. kita setting IP pada mikrotik pertama dengan masuk ke menu IP setelah itu address :
![](https://3.bp.blogspot.com/-Z8j8mzYQEqc/V9GBmHBcZfI/AAAAAAAAB3Q/5dNRLoT71FAsGEzvRyVn3O_YqBLnOOJXQCLcB/s1600/Screenshot%2Bfrom%2B2016-09-08%2B13-46-34.png)
4. setelah itu klik ikon plus (+) lalu tulis IP sesuai dengan topologi yang sudah di buat di atas :

5. dan hasil nya akan seperti ini jika IP berhasil ditambahkan :

![](https://4.bp.blogspot.com/-rh7HR5myo4s/V9GCAGnm6nI/AAAAAAAAB3U/mdggy6feRWkoQ5GoNri1NPRVsmAT5J0tgCLcB/s1600/Screenshot%2Bfrom%2B2016-09-08%2B13-11-28.png)

6. Setelah itu untuk melakukan routing static kita masuk ke menu IP >> routes 
![](https://1.bp.blogspot.com/-HXWEuqqD6hg/V9GDAMts8qI/AAAAAAAAB3k/2_BqQpp4Gqc0PPdem6dm6TRb3CHRAj5zQCLcB/s1600/Screenshot%2Bfrom%2B2016-09-08%2B13-50-01.png)
7. lalu kita klik ikon plus (+), lalu kita tambahkan IP network yang mau di routing dan gateway nya, sesuai dengan topologi di atas kita tambahkan network 192.168.2.0 dengan gateway 192.168.1.2 :
![](https://4.bp.blogspot.com/-Fgf4yEZ3UXA/V9GDngJqC0I/AAAAAAAAB3s/MqU7rs8bphwuLjULrw-ihssLyENZkjubQCLcB/s1600/Screenshot%2Bfrom%2B2016-09-08%2B13-59-06.png)
8. Lalu kita tambahkan lagi untuk menambahkan network 192.168.3.0, untuk gateway tetap menggunakan 192.168.1.2

9. Dan hasilnya akan seperti ini setalah kita tambahkan dua network tadi ke IP >> route
![](https://3.bp.blogspot.com/-3LGo3Ik_D8k/V9GEL6hhicI/AAAAAAAAB30/M5Jw3dsU4doVsWIYDVu0L47YrJcx0m5kACLcB/s1600/Screenshot%2Bfrom%2B2016-09-08%2B13-59-58.png)
10. Jika pada mikrotik sudah di setting IP sekaligus routing staticnya. sekarang kita masuk ke mikrotik 2
seperti tadi kita tambahkan IP sesuai dengan toplogi, untuk ether 1 kita buat agar satu jaringan dengan mikrotik 1 tadi :

11. Setelah itu kita tambahkan lagi untuk ether 2, setting IP sesuai dengan topologi di atas :
![](https://4.bp.blogspot.com/-Lhs3J94kNY8/V9GE_fxoBWI/AAAAAAAAB4A/vVYAIlq390gRQmFV9oGpm6oxxCjDxafnwCLcB/s1600/Screenshot%2Bfrom%2B2016-09-08%2B13-14-09.png)
12. Dan hasilnya setting IP akan menunjukan seperti berikut :
![](https://2.bp.blogspot.com/-97tN71Rhk3o/V9GFMoZjlOI/AAAAAAAAB4E/Ed9-Vvpo1Y0alj-NOSfaQ7cn50fnNBi8ACLcB/s1600/Screenshot%2Bfrom%2B2016-09-08%2B13-14-28.png)
13. jika IP sudah disetting seperti pada mikrotik 1 tadi kita juga konfigurasi routing static nya pada mikrotik 2 dengan menambahkan network 192.168.3.0 lalu gatewaynya 192.168.2.3
![](https://4.bp.blogspot.com/-1dXndXy7Mgc/V9GGBPYTHkI/AAAAAAAAB4I/SD8acOJw3C8pC8Uw8qOWR1Mq55mA9EGmACLcB/s1600/Screenshot%2Bfrom%2B2016-09-08%2B14-03-55.png)
14. Setelah untuk routing ke mikroik 1 kita gunakan network 0.0.0.0 dengan gateway 192.168.1.1
![](https://4.bp.blogspot.com/-QJz35bcAokA/V9GHEBCXVxI/AAAAAAAAB4U/pOPa0KiGbr0tm79wUEi5SCE0mExPR7VpACLcB/s1600/Screenshot%2Bfrom%2B2016-09-08%2B14-02-56.png)
15. dan hasil dari routing static yang kita tambahkan tadi akan seperti berikut :
![](https://2.bp.blogspot.com/-kOuZPILmqHg/V9GHRONEhVI/AAAAAAAAB4Y/gPomPmSe2aUByXCidfm-sUzBC-iSSfRDQCLcB/s1600/Screenshot%2Bfrom%2B2016-09-08%2B14-04-54.png)
16. Jika pada mikrotik 2 konfigurasi sudah selesai sekarnga kita masuk ke Mikrotik 3
17. Seperti pada mikrotik sebelumnya pertama kita konfigurasi IP nya
18. Pada ether 1 kita setting agar satu jaringan denan ether 2 di mikrotik 2 sesuai dengan topologi di atas tadi :
![](https://1.bp.blogspot.com/-N2MK9mcj-gU/V9GIBA_KLRI/AAAAAAAAB4k/BsS0jA7DlT0sDLA9ERX3YteamkiknZnSACLcB/s1600/Screenshot%2Bfrom%2B2016-09-08%2B13-15-52.png)
19. Lalu tambahkan lagi untuk ether 2 seperti topologi di atas tadi :
![](https://1.bp.blogspot.com/-2iTjkJzE320/V9GIaQR5vbI/AAAAAAAAB4o/oFYg_7rC2V0lZnb8lBrz3VOt8lAql4YIwCLcB/s1600/Screenshot%2Bfrom%2B2016-09-08%2B13-16-21.png)
20. dan hasilnya dari konfigurasi IP tadi akan seperti berikut :
![](https://1.bp.blogspot.com/-CBn5cIOetSM/V9GI40AhA3I/AAAAAAAAB40/LuRdXfUULzs7yz5WUZMQIZNV--iQcltgACLcB/s1600/Screenshot%2Bfrom%2B2016-09-08%2B13-16-31.png)
21. setelah pada konfigurasi IP selesai sekarang kita konfigurasi routing staticnya, dengan hanya menambahkan network 0.0.0.0/0 dan gateway 192.168.2.3
![](https://2.bp.blogspot.com/-GIPwNzpXCGE/V9GJdPkqTAI/AAAAAAAAB44/ed2QS0czkIQiy-IODfnMPzMgzoPsdFRKACLcB/s1600/Screenshot%2Bfrom%2B2016-09-08%2B14-11-13.png)
22. Dan nanti hasilnya akan seperti beriikut :
![](https://4.bp.blogspot.com/-e07Tc_-NjEM/V9GJtUN8C1I/AAAAAAAAB48/SbIOVznbQk4uWplUwrYhRd87J56JEKXMwCLcB/s1600/Screenshot%2Bfrom%2B2016-09-08%2B14-11-22.png)
23. Karena konfigurasi IP dan routing pada mikrotik 3 sudah selesai sekarng kita konfigurasi pada mikrotik 4
24. seperti pada mikrotik yang lain lain pertama kita konfigurasi IPnya terlebih dahulu seperti pada topologi yang di buat tadi :
![](https://2.bp.blogspot.com/-ZQ_TsLpXfj0/V9GK-k3ux-I/AAAAAAAAB5I/czO7ri9sbB0cJ0kmKP_gqlZLa1pP0QGUQCLcB/s1600/Screenshot%2Bfrom%2B2016-09-08%2B14-13-13.png)
25. Dan setelah di OK hasilnya akan seperti berikut :
![](https://4.bp.blogspot.com/-_N0Me1IeYZI/V9GLP2nh6sI/AAAAAAAAB5M/AG34JyRndIo8Ivc2BWDf7hz88hl494oRACLcB/s1600/Screenshot%2Bfrom%2B2016-09-08%2B14-13-22.png)
26. Setelah itu kita lakukan routing staticnya, dengan hanya menambahkan 0.0.0.0/0 dan gateway 192.168.3.3
![](https://3.bp.blogspot.com/-bwd4QVGgY5o/V9GL4u0t1vI/AAAAAAAAB5Q/eUOM9VjKkME0M-Rma8fx20md1ruaJVNqgCLcB/s1600/Screenshot%2Bfrom%2B2016-09-08%2B14-13-54.png)
27. Setelah itu hasil dari yang ditambahakan tadi akan seperti berikut :
![](https://2.bp.blogspot.com/-suQoBhBW20c/V9GM80JRARI/AAAAAAAAB5Y/bclrj-CEzqIOu2zboDP05DekGjzGZ2SkACLcB/s1600/Screenshot%2Bfrom%2B2016-09-08%2B14-38-11.png)
28. sekarang konfigurasi routing static pada 4 miktotik telah selesai, untuk tes kita bisa melakukan ping dari mikroti 4 ke mikrotik 1 atau sebaliknya :
![](https://4.bp.blogspot.com/-UUmYSF0yIR0/V9GOIdD2RbI/AAAAAAAAB5k/oGxbQhLLqFUb-DtaPzA6_uynPSFuStx2gCLcB/s1600/Screenshot%2Bfrom%2B2016-09-08%2B14-14-25.png)

![](https://4.bp.blogspot.com/-3ey_eYwpAn8/V9GOIy78kpI/AAAAAAAAB5o/S3oKbxKK8gYG8AbylMmjiZ_KRuh2V4shQCLcB/s1600/Screenshot%2Bfrom%2B2016-09-08%2B14-24-20.png)

### F. Hasil Kegiatan

        Hasilnya kita berhasil melakukan ping dari mikrotik 4 ke mikrotik 1 atau sebaliknya, walau pun kdu mikrotik itu memiliki IP dengan jaringan yang berbeda dan harus melewati beberapa nexhop tapi tetap bisa berkomunikasi setelah di routing



### G. Kesimpulan

         Kesimpulanya untuk melakukan routing static ini pada mikrotik pertama kita ibaratkan mikrotik paling atas sehingga kita melakukan routing static dengan cara memasukan network yang bebeda satu per satu, sedangkan pada mikrotik 4 kita untuk merouting kita tinggal memasukan network 0.0.0.0/0, disitu bisa dimpulkan untuk menuju ke bawah kita masukan satu per satu network nya sedangkan untuk ke atas kita masukan 0.0.0.0/0

