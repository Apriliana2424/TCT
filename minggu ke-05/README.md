# Mencari Aplikasi Spreadsheet dengan Javascript
---
## jExcel Spreadsheet

### Nama Kelompok :
* Rully Arisandi M. Baba
* Rohmatul Ummah
* Endah Sukma Kuncari
* Apriliana Puspitasari
* Riska Lestari

## jExcel Spreadsheet
**Keuntungan**
* Buat aplikasi web yang kaya
* Tingkatkan pengalaman perangkat lunak klien Anda
* CRUDS yang lebih baik dan UI yang cantik
* Kompatibilitas dengan excel, cukup salin dan tempel
* Kustomisasi yang kuat

### Langkah dalam menggunakan jExcel Spreadsheet :
1. Download source code untuk jExcel Spreadsheet nya terlebih dahulu di [https://jspreadsheets.com](https://jspreadsheets.com/jexcel.html)

Script yang diambil dalam url tersebut :
```
<html>
<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.1.1/jquery.min.js"></script>

<script src="http://cdn.bossanova.uk/js/jquery.jexcel.js"></script>
<link rel="stylesheet" href="http://cdn.bossanova.uk/css/jquery.jexcel.css" type="text/css" />

<div id="my"></div>

<script>
data = [
    ['Google', 1998, 807.80],
    ['Apple', 1976, 116.52],
    ['Yahoo', 1994, 38.66],
];

$('#my').jexcel({ data:data, colWidths: [ 300, 80, 100 ] });
</script>
</html>
```

2. Setelah mengambil source code lalu aktifkan apache web server di cmd (command prompt)
* Pertama buka cmd lalu ketikkan cd xampp\apache\bin , karena apache tersimpan dalam xampp maka dalam cmd buka direktori xampp\apache\bin
* Setelah itu httpd -k install untuk menginstall apache yang akan digunakan.
* Kemudian ketik httpd -k start untuk memulai apache.
* Untuk dapat menjalankan file maka dalam web browser ketik http://localhost/
> Untuk melihat isi direktori di cd xampp\apache\bin bisa menggunakan perintah dir. Untuk melihat isi direktori apakah sudah terdapat httpd.exe atau belum.

***Langkah - langkah yang ada diatas seperti langkah dibawah ini :***
![]()
***Hasil dari aplikasi jExcel Spreadsheet :***
![]()

> copyright@ Apriliana Puspitasari 2018