# Menggunakan RESTful Endpoint dengan GET
---

**RESTful API / REST API** merupakan implementasi dari API (Application Programming Interface). REST (Representional State Transfer) adalah suatu arsitektur metode komunikasi yang menggunakan protokol HTTP untuk pertukaran data dan metode ini sering diterapkan dalam pengembangan aplikasi. Dimana tujuannya adalah untuk menjadikan sistem yang memiliki performa yang baik, cepat dan mudah untuk di kembangkan (scale) terutama dalam pertukaran dan komunikasi data.
![](https://github.com/Apriliana2424/tct/blob/master/minggu%20ke-06/images/1.jpg)

RESTful API memiliki 4 komponen penting di dalamnya diantaranya adalah
1. URL Design
2. HTTP Verbs
3. HTTP Response Code
4. Format Response

*URL Design*
RESTful API diakses menggunakan protokol HTTP. Penamaan dan struktur URL yang konsisten akan menghasilkan API yang baik dan mudah untuk dimengerti developer. URL API biasa disebut endpoint dalam pemanggilannya. Contoh penamaan URL / endpoint yang baik adalah seperti berikut :
* /users
* /users/1234
* /users/1234/photos
* /users/1234/photos/abc

*HTTP Verbs*
Setiap request yang dilakukan terdapat metode yang dipakai agar server mengerti apa yang sedang di request client, diantaranya yang umum dipakai adalah :

*GET*

GET adalah metode HTTP Request yang paling simpel, metode ini digunakan untuk membaca atau mendapatkan data dari sumber.
Contoh :
GET /users : Mengembalikan daftar user
GET /users/1234 : Mengembalikan data user dengan ID 1234

---

Pada pertemuan ini akan membahas tentang menampilkan data yang diambil dari respon dari json.
Untuk script yang digunakan seperti :
```javascript
const express = require('express')
const app = express()
const port = 3000

app.get('/', function (req, res) {
res.jsonp({ user: 'April' });
})

app.listen(port, () => console.log(`Example app listening on port ${port}!`))
```

Sebelum mencoba untuk menampilkan data diatas yaitu User : April. Maka langkah yang pertama adalah install Node Js terlebih dahulu.
1. Silahkan download NodeJs versi stable di halaman https://nodejs.org/en/
2. Jika sudah, maka klik install nodejs dengan klik nodejs.exe lalu klik next next next pada setiap langkahnya.
![](https://github.com/Apriliana2424/tct/blob/master/minggu%20ke-06/images/2.jpg)

*Mengecek Instalasi NodeJs*

Setelah menginstal NodeJs, untuk mengetahui apakah NodeJs sudah terpasang di computer langkah yang harus dilakukan adalah
1. Dengan membuat sebuah file berekstensi .js di direktori apa saja dan diberi nama terserah 
2. Tuliskan code seperti dibawah ini dalam file
```javascript
var http = require('http');
http.createServer(function (req, res) {
	res.writeHead(200, {'Content-Type': 'text/plain'});
	res.end('Hello : ZEN\n');
}).listen(1337, '127.0.0.1');
console.log('Server running at http://127.0.0.1:1337/');
```

3. Setelah itu panggil file tersebut melalui command promt dengan cara
```javascript
c:\nodejs>node file.js
Server running at http://127.0.0.1:1337/
```

4. Kemudian panggil di browser dengn memasukkan alamat localhost:1337 (sesuai pada port yang sudah dituliskan di file file.js) pada address bar.

![](https://github.com/Apriliana2424/tct/blob/master/minggu%20ke-06/images/3.png)

5.	Jika sudah tampil seperti di atas berarti NodeJs sudah bisa dijalankan dan sudah aktif untuk file file.js 

*Menginstal framework express*
Setelah mengintsal node js kemudian melakukan penginstalan framework express di windows. Berikut langkah langkahnya
1. Menentukan dimana kita akan menginstal express, disni saya menggunakan direktori G:\teknik informatika\NodeJs\ untuk meletakkan hasil instalasi express
2. Memasukkan perintah instalan express dengan menggunakan npm : npm install -g express
---

Setelah file.js sudah aktif berjalan maka senjutnya saya akan mengganti script program untuk memanggil data yang dijalankan untuk json :
Program yang digunakan untuk respone json :
```javascript
const express = require('express')
const app = express()
const port = 3000

app.get('/', function (req, res) {
res.jsonp({ user: 'April' });
})

app.listen(port, () => console.log(`Example app listening on port ${port}!`))
```

Setelah program diatas dibuat untuk menjalankan file js tersebut maka pada cmd diberi perintah node a.js (karena nama file tersebut a.js)
```javascript
c:\nodejs>node a.js
Example app listening on port 3000!
```

Setelah muncul perintah diatas maka dapat dicoba di web browser : dengan perintah localhost:3000
![](https://github.com/Apriliana2424/tct/blob/master/minggu%20ke-06/images/4.png)

---

> copyright@ 2018. Apriliana Puspitasari