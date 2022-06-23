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
• <b>README.md</b> adalah file keterangan tentang codebase CI. Ini biasanya akan
dibutuhkan pada repo github atau gitlab.
<br>• <b>spark</b> adalah program atau script yang berfungsi untuk menjalankan server, generate kode, dll.</br>
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

![](Foto/foto10.png)

Pada file tersebut kita dapat mendefinisikan route untuk aplikasi yang kita buat.
Contoh:
```php
$routes->get('/', 'Home::index');
```
Kode tersebut akan mengarahkan rute untuk halaman home.
## Membuat Route Baru.
Tambahkan kode berikut di dalam <b>Routes.php</b>
```php
$routes->get('/about', 'Page::about');
$routes->get('/contact', 'Page::contact');
$routes->get('/faqs', 'Page::faqs');
```
Untuk mengetahui route yang ditambahkan sudah benar, buka CLI dan jalankan perintah berikut.
```php
php spark routes
```
![](Foto/foto11.png)

Selanjutnya coba akses route yang telah dibuat dengan mengakses alamat url
http://localhost/lab11_php_ci/ci4/public/about

![](Foto/foto12.png)

<p>Ketika diakses akan mucul tampilan error 404 file not found, itu artinya file/page tersebut tidak ada. Untuk dapat mengakses halaman tersebut, harus dibuat terlebih
dahulu Contoller yang sesuai dengan routing yang dibuat yaitu Contoller Page.</p>

## Membuat Controller
Selanjutnya adalah membuat Controller Page. Buat file baru dengan nama <b>page.php</b> pada direktori Controller kemudian isi kodenya seperti berikut.
```php
<?php

namespace App\Controllers;

class Page extends BaseController
{
    public function about()
    {
        echo "Ini halaman About";
    }
    
    public function contact()
    {
        echo "Ini halaman Contact";
    }
    
    public function faqs()
    {
        echo "Ini halaman FAQ";
    }
}
```
Selanjutnya refresh Kembali browser http://localhost/lab11_php_ci/ci4/public/page/about , maka akan ditampilkan hasilnya yaitu halaman sudah dapat diakses.
![](Foto/foto13.png)

## Auto Routing
Secara default fitur autoroute pada Codeiginiter sudah aktif. Untuk mengubah status autoroute dapat mengubah nilai variabelnya. Untuk menonaktifkan ubah nilai true menjadi <b>false</b>.
```php
$routes->setAutoRoute(true);
```
Tambahkan method baru pada Controller Page seperti berikut.
```php
public function tos()
{
    echo "ini halaman Term of Services";
}
```
Method ini belum ada pada routing, sehingga cara mengaksesnya dengan menggunakan
alamat: http://localhost/lab11_php_ci/ci4/public/page/tos
![](Foto/foto14.png)

## Membuat View
Selanjutnya adalam membuat view untuk tampilan web agar lebih menarik. Buat file
baru dengan nama about.php pada direktori view (<b>app/view/about.php</b>) kemudian isi
kodenya seperti berikut.
```php
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title><?= $title; ?></title>
</head>
<body>
    <h1><?= $title; ?></h1>
    <hr>
    <p><?= $content; ?></p>
</body>
</html>
```
Ubah method about pada class Controller Page menjadi seperti berikut:
```php
public function about()
{
    return view('about', [
        'title' => 'Halaman Abot',
        'content' => 'Ini adalah halaman abaut yang menjelaskan tentang isi
halaman ini.'
    ]);
}
```
![](Foto/foto15.png)

## Membuat Layout Web dengan CSS
Pada dasarnya layout web dengan css dapat diimplamentasikan dengan mudah pada codeigniter. Yang perlu diketahui adalah, pada Codeigniter 4 file yang menyimpan asset css dan javascript terletak pada direktori public.

<p>Buat file css pada direktori public dengan nama style.css (copy file dari praktikum lab4_layout. Kita akan gunakan layout yang pernah dibuat pada praktikum 4.</p>

![](Foto/foto16.png)
Kemudian buat folder <b>template</b> pada direktori <b>view</b> kemudian buat file <b>header.php</b> dan <b>footer.php</b>

File <b>app/view/template/header.php</b>
```php
<!DOCTYPE html>
<html lang="en">
  <link
    rel="stylesheet"
    href="https://cdn.jsdelivr.net/npm/bootstrap@4.0.0/dist/css/bootstrap.min.css"
    integrity="sha384-Gn5384xqQ1aoWXA+058RXPxPg6fy4IWvTNh0E263XmFcJlSAwiGgFAW/dAiS6JXm"
    crossorigin="anonymous"
  />
  <head>
    <meta charset="UTF-8" />
    <title><?= $title; ?></title>
    <link rel="stylesheet" href="style.css" />
  </head>

  <body>
    <div id="container">
      <header>
        <h1>Layout Sederhana</h1>
      </header>
      <nav>
        <a href="<?= base_url('/'); ?>" class="active">Home</a>
        <a href="<?= base_url('/artikel'); ?>">Artikel</a>
        <a href="<?= base_url('/about'); ?>">About</a>
        <a href="<?= base_url('/contact'); ?>">Kontak</a>
      </nav>
      <section id="wrapper">
        <section id="main"></section>
```
File <b>app/view/template/footer.php</b>
```php 
        </section>
        <aside id="sidebar">
            <div class="widget-box">
                <h3 class="title">Widget Header</h3>
                <ul>
                    <li><a href="#">Widget Link</a></li>
                    <li><a href="#">Widget Link</a></li>
                </ul>
            </div>
            <div class="widget-box">
                <h3 class="title">Widget Text</h3>
                <p>Vestibulum lorem elit, iaculis in nisl volutpat, malesuada
                    tincidunt arcu. Proin in leo fringilla, vestibulum mi porta, faucibus felis.
                    Integer pharetra est nunc, nec pretium nunc pretium ac.</p>
            </div>
        </aside>
    </section>
    <footer>
        <p>&copy; 2022 - <i>riris</i>  </p>
    </footer>
    </div>
</body>
</html>
```
Kemudian ubah file <b>app/view/about.php</b> seperti berikut.
```php
<?= $this->include('template/header'); ?>

<h1><?= $title; ?></h1>
<hr>
<p><?= $content; ?></p>

<?= $this->include('template/footer'); ?>
```
Selanjutnya refresh tampilan pada alamat http://localhost/lab11_php_ci/ci4/public/about

![](Foto/foto.jpeg)

# Praktikum 12: Framework Lanjutan (CRUD)

## <b>Langkah-langkah Praktikum</b>
Untuk memulai membuat aplikasi CRUD sederhana, yang perlu disiapkan adalah
database server menggunakan MySQL. Pastikan MySQL Server sudah dapat dijalankan
melalui XAMPP.
```
Membuat Database
```
![](Foto/foto17.png)
```
Membuat Tabel
```
![](Foto/foto18.png)

## Konfigurasi koneksi database
<p>Selanjutnya membuat konfigurasi untuk menghubungkan dengan database server.</p>
<p>Konfigurasi dapat dilakukan dengan du acara, yaitu pada file app/config/database.php atau menggunakan file .env. Pada praktikum ini kita gunakan konfigurasi pada file .env.</p>

![](Foto/foto19.png)

## Membuat Model
Selanjutnya adalah membuat Model untuk memproses data Artikel. Buat file baru pada
direktori app/Models dengan nama ArtikelModel.php
```php
<?php

namespace App\Models;

use CodeIgniter\Model;

class ArtikelModel extends Model
{
    protected $table = 'artikel';
    protected $primaryKey = 'id';
    protected $useAutoIncrement = true;
    protected $allowedFields = ['judul', 'isi', 'status', 'slug', 'gambar'];
}
```
<p>ini tampilan di VSC</p>

![](Foto/foto22.png)

## Membuat Controller
Buat Controller baru dengan nama Artikel.php pada direktori app/Controllers.
```php
<?php
namespace App\Controllers;
use App\Models\ArtikelModel;
class Artikel extends BaseController
{
    public function index()
    {
        $title = 'Daftar Artikel';
        $model = new ArtikelModel();
        $artikel = $model->findAll();
        return view('artikel/index', compact('artikel', 'title'));
    }
}
```
<p>ini tampilan di VSC</p>

![](Foto/foto20.png)

## Membuat View
Buat direktori baru dengan nama artikel pada direktori app/views, kemudian buat file
baru dengan nama index.php.
```php
<?= $this->include('template/header'); ?>
<?php if($artikel): foreach($artikel as $row): ?>
<article class="entry">
<h2<a href="<?= base_url('/artikel/' . $row['slug']);?>"><?=
$row['judul']; ?></a>
</h2>
<img src="<?= base_url('/gambar/' . $row['gambar']);?>" alt="<?=
$row['judul']; ?>">
<p><?= substr($row['isi'], 0, 200); ?></p>
</article>
<hr class="divider" />
<?php endforeach; else: ?>
<article class="entry">
<h2>Belum ada data.</h2>
</article>
<?php endif; ?>
<?= $this->include('template/footer'); ?>
```
<p>ini tampilan di VSC</p>

![](Foto/foto21.png)
