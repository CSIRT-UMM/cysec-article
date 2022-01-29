
![Thumb](https://github.com/CSIRT-UMM/cysec-article/blob/main/28012022%20-%20Ubuntu%20overlayfs/ubuntuOverlayfsThumb.png)
# Kerentanan OverlayFS pada Ubuntu Memungkinkan Peretas Untuk Mendapatkan Akses ROOT.

Salah satu exploit yang memanfaatkan kerentanan ini telah beredar secara online dan dengan mudahnya dieksekusi oleh siapapun
dengan hanya meng-<i>compile</i> kode pemrograman C dan menjalankannya sebagai biner, siapapun bisa mendapatkan akses ROOT dan mengkontrol sistem tersebut dengan penuh.

## Respons Ubuntu
"Masalah khusus Ubuntu dalam sistem file overlayfs di kernel Linux yang tidak memvalidasi aplikasi kemampuan sistem file dengan benar sehubungan dengan namespace pengguna. Penyerang lokal dapat menggunakan ini untuk mendapatkan hak akses yang lebih tinggi, karena tambalan yang dibawa di Ubuntu untuk izinkan pemasangan overlay yang tidak diprioritaskan." Kutip Ubuntu Security pada tanggal 15 April 2021.

## Cara Memitigasi Kerentanan
Update package  `linux-image-5.6.0-1054-oem - 5.6.0-1054.58` dan `linux-image-oem-20.04 - 5.6.0.1054.50`<br>
untuk menerima dan menginstall patch sesegera mungkin melalui apt package manager.

## Contoh exploit yang digunakan untuk melakukan serangan
https://github.com/CSIRT-UMM/vulnclass/tree/main/Privilege%20Escalation/Ubuntu%20overlayfs%20CVE-2021-3493

---
Sources:<br>
https://github.com/CSIRT-UMM/vulnclass/tree/main/Privilege%20Escalation/Ubuntu%20overlayfs%20CVE-2021-3493
https://ssd-disclosure.com/ssd-advisory-overlayfs-pe/
https://ubuntu.com/security/CVE-2021-3493
https://ubuntu.com/security/notices/USN-4915-1
https://ubuntu.com/security/notices/USN-4916-1
https://ubuntu.com/security/notices/USN-4917-1
