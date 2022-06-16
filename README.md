# Praktikum 11: PHP Framework (Codeigniter)

<strong>Repository ini dibuat untuk memenuhi tugas Pemrograman Web</strong>
| <strong>Nama</strong>      | <strong>Riris Naomi Gurning</strong>  |
| ----------- | -----------  |
| <strong>NIM</strong>       | <strong>312010190</strong>            |
| <strong>Kelas</strong>     | <strong>TI.20.A.1</strong>            |

# <b>Langkah-langkah Praktikum</b>
Sebelum memulai menggunakan Framework Codeigniter, perlu dilakukan konfigurasi pada webserver. Beberapa ekstensi PHP perlu diaktifkan untuk kebutuhan
pengembangan Codeigniter 4.
Berikut beberapa ekstensi yang perlu diaktifkan:
<br>• <b>php-json</b> ekstension untuk bekerja dengan JSON;<br>
• <b>php-mysqlnd</b> native driver untuk MySQL;
<br>• <b>php-xml</b> ekstension untuk bekerja dengan XML;</br>
• <b>php-intl</b> ekstensi untuk membuat aplikasi multibahasa;
<br>• <b>libcurl</b> (opsional), jika ingin pakai Curl. Untuk mengaktifkan ekstentsi tersebut,</br>
<p>Untuk mengaktifkan ekstentsi tersebut, melalu <b>XAMPP Control Panel</b>, pada bagian Apache klik <b>Config -> PHP.ini</b></p>

![](Foto/xampp.png)

<p>Setelah klik PHP(php.ini), pada bagian extention, hilangkan tanda ; (titik koma) pada ekstensi yang akan
diaktifkan. Kemudian simpan kembali filenya dan restart Apache web server.

![](Foto/foto1.png)

## Instalasi Codeigniter 4
Untuk melakukan instalasi Codeigniter 4 dapat dilakukan dengan dua cara, yaitu cara
manual dan menggunakan <b>composer</b>. Pada praktikum ini kita menggunakan cara
manual.
<br>• Unduh <b>Codeigniter</b> dari website https://codeigniter.com/download</br>
• Extrak file zip Codeigniter ke direktori <b>htdocs/lab11_php_ci</b>.
<br>• Ubah nama direktory <b>framework-4.x.xx</b> menjadi <b>ci4</b>.</br>
• Buka browser dengan alamat http://localhost/lab11_php_ci/ci4/public/
![](Foto/foto4.png)

## Menjalankan CLI (Command Line Interface)
Codeigniter 4 menyediakan CLI untuk mempermudah proses development. Untuk mengakses CLI buka terminal/command prompt.
![](Foto/foto2.png)

Arahkan lokasi direktori sesuai dengan direktori kerja project dibuat (xampp/<b>htdocs/lab11_ci/ci4/</b>) <p>Setelah itu kita memanggil CLI Codeigniter dengan menjalankan perintah:</p>
```
php spark
```
![](Foto/foto3.png)

## Mengaktifkan Mode Debugging
Codeigniter 4 menyediakan fitur debugging untuk memudahkan developer untuk
mengetahui pesan error apabila terjadi kesalahan dalam membuat kode program.
<p>Secara default fitur ini belum aktif. Ketika terjadi error pada aplikasi akan ditampilkan pesan kesalahan seperti berikut.</p>

![](Foto/foto5.png)

<p>Semua jenis error akan ditampilkan sama. Untuk memudahkan mengetahui jenis errornya, maka perlu diaktifkan mode debugging dengan mengubah nilai konfigurasi pada environment variable <b>CI_ENVIRINMENT</b> menjadi <b>development</b>.</p>

![](Foto/foto6.png)

Ubah nama file env menjadi .env kemudian buka file tersebut dan ubah nilai variable
<b>CI_ENVIRINMENT</b> menjadi <b>development.</b>

<p>Contoh error yang terjadi. Untuk mencoba error tersebut, ubah kode pada file <b>app/Controller/Home.php</b> hilangkan titik koma pada akhir kode.

![](Foto/foto7.png)
<br>Dan inilah Hasilnya</br>
![](Foto/foto8.png)

## Struktur Direktori
Untuk lebih memahami Framework Codeigniter 4 perlu mengetahui struktur direktori
dan file yang ada. Buka pada Windows Explorer atau dari Visual Studio Code ->
Open Folder.
Terdapat beberapa direktori dan file yang perlu dipahami fungsi dan kegunaannya.
<br>• <b>.github</b> folder ini kita butuhkan untuk konfigurasi repo github, seperti konfigurasi untuk build dengan github action;</br>
• <b>app</b> folder ini akan berisi kode dari aplikasi yang kita kembangkan;
<br>• <b>public</b> folder ini berisi file yang bisa diakses oleh publik, seperti file index.php,</br>
robots.txt, favicon.ico, ads.txt, dll;
<br>• <b>tests</b> folder ini berisi kode untuk melakukan testing dengna PHPunit;</br>
• <b>vendor</b> folder ini berisi library yang dibutuhkan oleh aplikasi, isinya juga termasuk
kode core dari system CI.
<br>• <b>writable</b> folder ini berisi file yang ditulis oleh aplikasi. Nantinya, kita bisa pakai untuk menyimpan file yang di-upload, logs, session, dll.
Sedangkan file-file yang berada pada root direktori CI sebagai berikut.<br>
• <b>.env</b> adalah file yang berisi variabel environment yang dibutuhkan oleh aplikasi.
<br>• <b>.gitignore</b> adalah file yang berisi daftar nama file dan folder yang akan diabaikan oleh Git.</br>
• <b>build</b> adalah script untuk mengubah versi codeigniter yang digunakan. Ada versi
release (stabil) dan development (labil).
<br>• <b>composer.json</b> adalah file JSON yang berisi informasi tentang proyek dan daftar library yang dibutuhkannya. File ini digunakan oleh Composer sebagai acuan.</br>
• <b>composer.lock</b> adalah file yang berisi informasi versi dari libraray yang digunakan
aplikasi.
<br>• <b>license.txt</b> adalah file yang berisi penjelasan tentang lisensi Codeigniter;</br>
• <b>phpunit.xml.dist</b> adalah file XML yang berisi konfigurasi untuk PHPunit.
<br>• <b>README.md</b> adalah file keterangan tentang codebase CI. Ini biasanya akan</br>
dibutuhkan pada repo github atau gitlab.
• <b>spark</b> adalah program atau script yang berfungsi untuk menjalankan server,
generate kode, dll.
![](Foto/foto9.png)
<p>Fokus kita pada folder <b>app</b>, dimana folder tersebut adalah area kerja kita untuk
membuat aplikasi. Dan folder <b>public</b> untuk menyimpan aset web seperti css, gambar,
javascript, dll.</p>

## Memahami Konsep MVC
Codeigniter menggunakan konsep MVC. MVC meripakan singkatan dari *Model-View-Controller*. MVC merupakan konsep arsitektur yang umum digunakan
dalam pengembangan aplikasi. Konsep MVC adalah memisahkan kode program
berdasarkan logic proses, data, dan tampilan. Untuk logic proses diletakkan pada
direktori Contoller, Objek data diletakkan pada direktori Model, dan desain tampilan
diletakkan pada direktori View.

<p>Codeigniter menggunakan konsep pemrograman berorientasi objek dalam
mengimplementasikan konsep MVC.</p>

<p><b>Model</b> merupakan kode program yang berisi pemodelan data. Data dapat berupa database ataupun sumber lainnya.</p>

<p><b>View</b> merupakan kode program yang berisi bagian yang menangani terkait tampilan user interface sebuah aplikasi. didalam aplikasi web biasanya pasti akan berhubungan
dengan html dan css.</p>

<p><b>Controller</b> merupakaan kode program yang berkaitan dengan logic proses yang menghubungkan antara view dan model Controller berfungsi untuk menerima request dan data dari user kemudian diproses dengan menghubungkan bagian model dan view.</p>

<p><b>Routing dan Controller</b>
<br>Routing merupakan proses yang mengatur arah atau rute dari request untuk menentukan
fungsi/bagian mana yang akan memproses request tersebut. Pada framework CI4, routing bertujuan untuk menentukan Controller mana yang harus merespon sebuah request. Controller adalah class atau script yang bertanggung jawab merespon sebuah
request.</p>
<p>Pada Codeigniter, request yang diterima oleh file index.php akan diarahkan ke Router untuk meudian oleh router tesebut diarahkan ke Controller.</p>
Router terletak pada file <b>app/config/Routes.php</b>



