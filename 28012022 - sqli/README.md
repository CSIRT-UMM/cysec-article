![Thumb](https://github.com/CSIRT-UMM/cysec-article/blob/main/28012022%20-%20sqli/sqliThumb.png)
# Apa Itu SQLInjection dan Bagaimana Pencegahannya?
Serangan SQL Injection adalah serangan yang menyisipkan kueri SQL melalui data input dari klien ke aplikasi. Eksploitasi SQL Injection yang berhasil dapat membaca data sensitif dari database, memodifikasi data database, menjalankan operasi administrasi pada database, dsb. Serangan SQL Injection adalah jenis serangan injeksi, di mana perintah SQL disuntikkan ke input data untuk memengaruhi eksekusi perintah SQL.
<br><br>

## Jenis Kerusakan yang Dapat Disebabkan

### Kerahasiaan
Database SQL umumnya menyimpan data sensitif, dengan bocornya database, data seperti email dan kata sandi dapat tersebar dengan mudah.
### Otentikasi
Jika perintah SQL dapat digunakan untuk meninjau nama pengguna dan kata sandi, peretas dapat terhubung ke sistem menggunakan kredensial pengguna lain. 
### Integritas
Pelaku SQL Injection dapat melakukan perubahan atau bahkan menghapus informasi dalam database melalui sebuah serangan.

---
## Penyebab
SQL Injection umumnya terjadi karena programmer tidak mem-filter karakter-karakter seperti:
<br>&, ;, \`, ‘, \, “, |, *, ?, ~, <, >, ^, (, ), [, ], {, }, $, \n, dan \r yang digunakan dalam sintaks SQL pada form input.
<br>Selain itu serangan SQL Injection juga dapat terjadi apabila developer tidak mengimplementasikan <i>Web Application Firewall</i> (WAF), Intrusion Prevention System (IPS), dan Intrusion Detection System (IDS) pada jaringan tersebut.

## Cara Memitigasi dan Memperbaiki
- Membuat filter terhadap karakter-karakter seperti: &, ;, \`, ‘, \, “, |, *, ?, ~, <, >, ^, (, ), [, ], {, }, $, \n, dan \r.
- Mengenkripsi database password, Sehingga mempersulit peretas untuk mendapatkan sandi kredensial apabila terjadi kebocoran.
- Memasang WAF, IPS, dan IDS dalam jaringan untuk mempersulit percobaan penetrasi database.

---
Sources:<br>
https://cheatsheetseries.owasp.org/cheatsheets/SQL_Injection_Prevention_Cheat_Sheet.html<br>
https://owasp.org/www-community/attacks/SQL_Injection
