
![thumbBanner](https://github.com/CSIRT-UMM/cysec-article/blob/main/01042022%20-%20Windows2Streak0Day/2xwin.png)

# Kelemahan Windows zero-day yang memberikan hak admin mendapat patch tidak resmi, lagi

Kerentanan zero-day eskalasi hak istimewa lokal Windows yang gagal ditangani sepenuhnya oleh Microsoft selama beberapa bulan sekarang, memungkinkan pengguna untuk mendapatkan hak administratif di Windows 10, Windows 11, dan Windows Server.

Kerentanan yang dieksploitasi secara lokal di Layanan Profil Pengguna Windows dilacak sebagai CVE-2021-34484 dan diberi skor CVSS v3 7,8. Sementara eksploitasi telah diungkapkan kepada publik di masa lalu, mereka diyakini tidak dieksploitasi secara aktif di alam liar.

Keunikan dari kasus ini terletak pada kenyataan bahwa Microsoft tidak dapat mengatasi kekurangan tersebut sejak penemuannya musim panas lalu dan telah menandai bug tersebut sebagai diperbaiki dua kali.

Menurut tim 0patch, yang secara tidak resmi menyediakan perbaikan untuk versi Windows yang dihentikan dan beberapa kerentanan yang tidak akan ditangani oleh Microsoft, cacatnya masih nol hari. Faktanya, patch Microsoft gagal memperbaiki bug dan memecahkan patch tidak resmi 0patch sebelumnya.

## LPE yang tidak akan diperbaiki

Peningkatan Kerentanan Privilege Layanan Profil Pengguna Windows, dilacak sebagai CVE-2021-34484, ditemukan oleh peneliti keamanan Abdelhamid Naceri dan diungkapkan kepada Microsoft, yang memperbaikinya sebagai bagian dari Agustus 2021 Patch Selasa.

Segera setelah perbaikan dirilis, Naceri melihat bahwa patch Microsoft tidak lengkap dan menyajikan bukti konsep PoC yang melewatinya di semua versi Windows.

**CVE-2021-34484 Eksploitasi meluncurkan prompt perintah yang ditinggikan dengan hak istimewa SISTEM**
_Sumber: BleepingComputer_

Tim 0patch turun tangan pada saat itu, mengeluarkan pembaruan keamanan tidak resmi untuk semua versi Windows dan membuatnya gratis untuk diunduh untuk semua pengguna terdaftar.

Microsoft juga menanggapi pintasan ini dengan pembaruan keamanan kedua yang dirilis dengan patch Selasa Selasa Januari 2022, memberikan bypass ID pelacakan baru sebagai CVE-2022-21919 dan menandainya sebagai tetap. Namun, Naceri menemukan cara untuk melewati perbaikan itu sambil berkomentar bahwa upaya ini lebih buruk daripada yang pertama.

Saat menguji patch mereka terhadap bypass kedua peneliti, 0patch menemukan bahwa patch mereka ke DLL "profext.dll" masih melindungi pengguna dari metode eksploitasi baru, yang memungkinkan sistem tersebut tetap aman.

Namun, upaya perbaikan kedua Microsoft menggantikan file "profext.dll", yang mengarah pada penghapusan perbaikan tidak resmi dari semua orang yang telah menerapkan pembaruan Windows pada Januari 2022.

0patch sekarang telah memindahkan perbaikan untuk bekerja dengan Patch Maret 2022 Pembaruan hari Selasa dan membuatnya tersedia secara gratis untuk semua pengguna terdaftar.

Versi Windows yang dapat memanfaatkan patch mikro baru adalah sebagai berikut:

- **Windows 10 v21H1** (32 & 64 bit) diperbarui dengan Pembaruan Maret 2022
- **Windows 10 v20H2** (32 & 64 bit) diperbarui dengan Pembaruan Maret 2022
- **Windows 10 v1909** (32 & 64 bit) diperbarui dengan Pembaruan Maret 2022
- **Windows Server 2019** 64 bit diperbarui dengan Pembaruan Maret 2022

Perlu dicatat bahwa Windows 10 1803, Windows 10 1809, dan Windows 10 2004 masih dilindungi oleh patch asli 0patch, karena perangkat tersebut telah mencapai akhir dukungan dan tidak menerima pembaruan Microsoft yang menggantikan DLL.

## Cara menginstal patch mikro

Patch mikro akan tetap tersedia sebagai unduhan gratis untuk pengguna versi Windows di atas selama Microsoft belum merilis perbaikan lengkap untuk masalah LPE tertentu dan semua pintasannya.

Bagi mereka yang tertarik untuk mengambil penawaran itu, perbarui Windows 10 Anda ke level patch terbaru (Maret 2022), buat akun gratis di lalu instal dan daftarkan Agen 0patch dari sini

Melakukan itu akan memulai proses penambalan mikro otomatis tanpa tindakan manual atau reboot yang diperlukan agar peluang diterapkan pada sistem Anda.

Bleeping Computer telah menghubungi Microsoft untuk menanyakan apakah itu berencana untuk meninjau kembali kelemahan tertentu dan mungkin mencoba dan memperbaikinya melalui pembaruan keamanan di masa mendatang,

Sources:<br>
https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-34484<br>
https://www.forbes.com/sites/gordonkelly/2022/03/26/microsoft-windows-11-windows-10-hack-attack-zero-day-new-windows-update/?sh=4d8d7ae27ef8
