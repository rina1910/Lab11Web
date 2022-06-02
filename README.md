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

## Menjalankan CLI (Command Line Interface)
Codeigniter 4 menyediakan CLI untuk mempermudah proses development. Untuk mengakses CLI buka terminal/command prompt.
![](Foto/foto2.png)

Arahkan lokasi direktori sesuai dengan direktori kerja project dibuat (xampp/<b>htdocs/lab11_ci/ci4/</b>) <p>Setelah itu kita memanggil CLI Codeigniter dengan menjalankan perintah:</p>
```
php spark
```
