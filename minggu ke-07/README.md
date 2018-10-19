# Menghubungkan RESTful API NodeJS + Express + MySQL serta menampilkan data dari MySQL
---

Pertama sebelum memulai mengerjakan praktikum ini, saya mencoba aplikasi 
nodejs saya dari pertemuan sebelumnya dengan membuka file yang kemarin saya jalankan, 
saya menjalankan pertemuan6.js dan masih berjalan makanya saya menggunakan aplikasi nodejs yang sebelumnya. Seperti gambar dibawah ini :

![1]()

![2]()

Setelah mencoba aplikasi nodejs saya berhasil maka selanjutnya saya menghidupkan database server : MySQL dan web server: apache. Karena disini saya
menggunakan XAMPP maka saya membuat database juga dalam XAMPP, seperti gambar dibawah ini :

*Gambar untuk meng-aktifkan web server dan database server :*

![3]()

*Gambar untuk masuk kedalam direktori mysql di xampp :*

![4]()

*Gambar langkah dalam pembuatan database dan tabel di MySQL :*

![5]()


**Setelah database dibuat selanjutnya saya mengecek database dalam phpmyadmin :**

![6]()
![7]()

---

## Langkah dalam menghubungkan RESTful API NodeJS + Express + MySQL

Pertama install body-parser untuk koneksi ke MySQL, seperti dibawah ini :

![8]()

*Untuk mengecek versi NodeJS nya dapat menggunakan perintah npm init*

**Lalu, Buat file server.js, ini adalah file utama kita dimana bisa dibilang seperti index.php.**
```
var express = require('express'),
    app = express(),
    port = process.env.PORT || 3000,
    bodyParser = require('body-parser'),
    controller = require('./controller');

app.use(bodyParser.urlencoded({ extended: true }));
app.use(bodyParser.json());

var routes = require('./routes');
routes(app);

app.listen(port);
console.log('Learn Node JS April, RESTful API server started on: ' + port);
```
> File diatas ditujukan untuk membuat server atau kinerja awal yang dibutuhkan aplikasi untuk melakukan langkah selanjutnya.

**Oke setelah server.js dijalankan, kita akan ngebuat file koneksi antara database dan aplikasi kita.**
**Membuat sebuah file yang beri nama conn.js sebagai tempat mengkoneksikan aplikasi ke database ketika kita butuh koneksi ke database.**
```
var mysql = require('mysql');

var con = mysql.createConnection({
  host: "localhost",
  user: "root",
  password: "",
  database: "data"
});

con.connect(function (err){
    if(err) throw err;
});

module.exports = con;
```
> File diatas digunakan untuk menghubungkan aplikasi dengan database. Dengan nama database yang saya gunakan : data.

**Membuat file controller.js :**
```
'use strict';

var response = require('./res');
var connection = require('./conn');

exports.users = function(req, res) {
    connection.query('SELECT * FROM lagu', function (error, rows, fields){
        if(error){
            console.log(error)
        } else{
            response.ok(rows, res)
        }
    });
};

exports.index = function(req, res) {
    response.ok("Hello project Apriliana Puspitasari", res)
};
```
> File diatas untuk mengontrol apakah server yang kita gunakan sudah bisa dijalankan dengan baik atau belum. Hasil dari respone ini akan muncul terlebih dahulu sebelum data dari database dipanggil.

**Membuat file res.js :**
```
'use strict';

exports.ok = function(values, res) {
  var data = {
      'status': 200,
      'values': values
  };
  res.json(data);
  res.end();
};
```
> res.json(data) adalah variabel data yang akan dikembalikan value nya jadi json dan res.end() berfungsi untuk menutup koneksi database setelah data ditampilkan oleh json.

**Membuat file routes.js :**
File ini digunakan untuk router atau endpoint yang ada di rest api pada aplikasi saya.
```
'use strict';

module.exports = function(app) {
    var todoList = require('./controller');

    app.route('/')
        .get(todoList.index);

    app.route('/users')
        .get(todoList.users);
};
```
> File ini digunakan untuk menampilkan hasil get dari database untuk ditampilkan dalam bentuk javascript.

---

Untuk mencoba apakah server yang kita buat sudah dapat dijalankan dengan mengecek di CMD dengan perintah :

![9]()

*Setelah berhasil dapat kita coba dalam web browser dengan perintah localhost:3000*

![10]()

*Jika sudah berhasil maka selanjutnya untuk menampilkan isi data dari database mysql dengan perintah seperti dibawah ini :*

![11]()

---

> copyright@ 2018. Apriliana Puspitasari