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
<br>• php-json ekstension untuk bekerja dengan JSON;<br>
• php-mysqlnd native driver untuk MySQL;
<br>• php-xml ekstension untuk bekerja dengan XML;</br>
• php-intl ekstensi untuk membuat aplikasi multibahasa;
<br>• libcurl (opsional), jika ingin pakai Curl. Untuk mengaktifkan ekstentsi tersebut,</br>
<p>Untuk mengaktifkan ekstentsi tersebut, melalu XAMPP Control Panel, pada bagian Apache klik Config -> PHP.ini</p>

![](Foto/xampp.png)

<p>Setelah klik PHP(php.ini), pada bagian extention, hilangkan tanda ; (titik koma) pada ekstensi yang akan
diaktifkan. Kemudian simpan kembali filenya dan restart Apache web server.

![](Foto/foto1.png)

## Instalasi Codeigniter 4
Untuk melakukan instalasi Codeigniter 4 dapat dilakukan dengan dua cara, yaitu cara
manual dan menggunakan composer. Pada praktikum ini kita menggunakan cara
manual.
<br>• Unduh Codeigniter dari website https://codeigniter.com/download</br>
• Extrak file zip Codeigniter ke direktori htdocs/lab11_ci.
<br>• Ubah nama direktory framework-4.x.xx menjadi ci4.</br>
• Buka browser dengan alamat http://localhost/lab11_ci/ci4/public/
