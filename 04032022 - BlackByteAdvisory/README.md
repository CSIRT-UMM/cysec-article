
![thumbBanner](https://github.com/CSIRT-UMM/cysec-article/blob/main/04032022%20-%20BlackByteAdvisory/blackbyte.png)
# FBI dan USSS Rilis Rekomendasi Mitigasi BlackByte Ransomware

The Federal Bureau of Investigation (FBI) dan United States Secret Service (USSS) telah merilis Cybersecurity Advisory (CSA) yang mengidentifikasi indikator peretasan yang terkait dengan ransomware "BlackByte". "BlackByte" adalah grup "Ransomware-as-a-Service" yang mengenkripsi file pada sistem host Windows yang disusupi, termasuk server fisik dan virtual.

"Certified Information Systems Auditor" (CISA) mendorong organisasi untuk meninjau FBI-USSS CSA dan menerapkan mitigasi yang direkomendasikan.

## Rincian Teknis
Eksekusi BlackByte meninggalkan catatan ransom di semua direktori tempat enkripsi terjadi.
Catatan ransom mencakup situs .onion yang berisi instruksi untuk membayar uang tebusan dan menerima kunci dekripsi. Beberapa korban melaporkan bahwa pelaku menggunakan kerentanan Microsoft Exchange Server yang dikenal sebagai sarana untuk mendapatkan akses ke jaringan mereka. Sekalinya masuk,
pelaku dapat menyebarkan alat untuk bergerak secara lateral melintasi jaringan dan melakukan privilege escalation sebelum mengekstrak dan mengenkripsi file. Dalam beberapa kasus, pelaku ransomware BlackByte hanya memiliki sebagian file yang dienkripsi. Dalam kasus di mana dekripsi tidak memungkinkan, beberapa pemulihan data dapat terjadi. Versi BlackByte ransomware sebelumnya mengunduh file .png dari alamat IP 185.93.6.31 dan 45.9.148.114 sebelum enkripsi. Versi yang lebih baru mengenkripsi tanpa berkomunikasi dengan alamat IP eksternal apa pun. Ransomware BlackByte menjalankan executable
dari c:\windows\system32\ dan C:\Windows\. Injeksi proses telah diamati pada proses yang dibuatnya.

## Indicators of Compromise
Indicators of Compromise (IOC) berikut dinilai terkait dengan aktivitas BlackByte:
| File mencurigakan ditemukan di lokasi berikut:  |
|---|
|Windows\Microsoft.NET\Framework64\v4.0.30319\Temporary ASP.NET  |
|Files\root\e22c2559\92c7e946  |
|inetpub\wwwroot\aspnet_client
|Program  Files\Microsoft\Exchange Server\V15\FrontEnd\HttpProxy\owa\auth  |
|Program Files\Microsoft\Exchange Server\V15\FrontEnd\HttpProxy\owa\auth\Current|
|Program Files\Microsoft\Exchange  |
|Server\V15\FrontEnd\HttpProxy\owa\auth\Current\themes |
|Program Files\Microsoft\Exchange  |
|Server\V15\FrontEnd\HttpProxy\owa\auth\Current\scripts  |
|Program Files\Microsoft\Exchange  |
|Server\V15\FrontEnd\HttpProxy\owa\auth\Current\scripts\premium|

Nama file untuk file ASPX yang mencurigakan nampaknya memiliki penamaan sebagai berikut:
- <5 random alphabetical characters>.aspx
- error<2 capital letters>.aspx
- iismeta<4 random numbers>.aspx

Di bawah ini adalah daftar hash file mencurigakan yang telah diamati pada sistem yang terpengaruh oleh ransomware BlackByte:

| MD5 | MD5 |
|--|--|
|4d2da36174633565f3dd5ed6dc5033c4 | 959a7df5c465fcd963a641d87c18a565|
|cd7034692d8f29f9146deb3641de7986 | 5f40e1859053b70df9c0753d327f2cee|
|d63a7756bfdcd2be6c755bf288a92c8b | df7befc8cdc3c5434ef27cc669fb1e4b|
|eed7357ab8d2fe31ea3dbcf3f9b7ec74 | 51f2cf541f004d3c1fa8b0f94c89914a|
|695e343b81a7b0208cbae33e11f7044c | d9e94f076d175ace80f211ea298fa46e|
|296c51eb03e70808304b5f0e050f4f94 | 8320d9ec2eab7f5ff49186b2e630a15f|
|0c7b8da133799dd72d0dbe3ea012031e | cea6be26d81a8ff3db0d9da666cd0f8f|
|a77899602387665cddb6a0f021184a2b | 31f818372fa07d1fd158c91510b6a077|
|1473c91e9c0588f92928bed0ebf5e0f4 | d9e94f076d175ace80f211ea298fa46e|
|28b791746c97c0c04dcbfe0954e7173b | a9cf6dce244ad9afd8ca92820b9c11b9|
|52b8ae74406e2f52fd81c8458647acd8 | 7139415fecd716bec6d38d2004176f5d|
|1785f4058c78ae3dd030808212ae3b04 | c13bf39e2f8bf49c9754de7fb1396a33|
|b8e24e6436f6bed17757d011780e87b9 | 5c0a549ae45d9abe54ab662e53c484e2|
|8dfa48e56fc3a6a2272771e708cdb4d2 | ad29212716d0b074d976ad7e33b8f35f|
|4ce0bdd2d4303bf77611b8b34c7d2883 | d4aa276a7fbe8dcd858174eeacbb26ce|
|c010d1326689b95a3d8106f75003427c | 9344afc63753cd5e2ee0ff9aed43dc56|
|ae6fbc60ba9c0f3a0fef72aeffcd3dc7 | e2eb5b57a8765856be897b4f6dadca18
|405cb8b1e55bb2a50f2ef3e7c2b28496 | 58e8043876f2f302fbc98d00c270778b|
|11e35160fc4efabd0a3bd7a7c6afc91b | d2a15e76a4bfa7eb007a07fc8738edfb|
|659b77f88288b4874b5abe41ed36380d | e46bfbdf1031ea5a383040d0aa598d45|
|151c6f04aeff0e00c54929f25328f6f7 |—|

## Mitigasi
- Terapkan pencadangan rutin semua data untuk disimpan sebagai salinan offline yang dilindungi kata sandi. Pastikan salinan ini tidak dapat diakses untuk dimodifikasi atau dihapus dari sistem mana pun tempat data asli berada.
- Terapkan segmentasi jaringan, sehingga semua mesin di jaringan Anda tidak dapat diakses dari setiap mesin lainnya.
- Instal dan perbarui perangkat lunak antivirus secara teratur di semua host, dan aktifkan deteksi realtime.
- Instal pembaruan/tambalan sistem operasi, perangkat lunak, dan firmware segera setelah pembaruan/tambalan dirilis.
- Tinjau pengontrol domain, server, stasiun kerja, dan direktori aktif untuk akun pengguna baru atau yang tidak dikenal.
- Audit akun pengguna dengan hak administratif dan konfigurasikan kontrol akses dengan mempertimbangkan hak istimewa paling sedikit. Jangan berikan semua pengguna administratif.
- Nonaktifkan port akses jarak jauh/Protokol Desktop Jarak Jauh (RDP) yang tidak digunakan dan pantau akses jarak jauh/log RDP untuk aktivitas yang mencurigakan.
- Pertimbangkan untuk menambahkan email banner kepada email yang diterima dari luar organisasi.
- Nonaktifkan hyperlink di email yang diterima.
- Gunakan otentikasi ganda saat masuk ke akun atau layanan.
- Pastikan audit rutin dilakukan untuk semua akun.
- Pastikan semua IOC yang teridentifikasi dimasukkan ke dalam jaringan SIEM untuk pemantauan dan peringatan berkelanjutan.

Sources:<br>
https://www.cisa.gov/uscert/ncas/current-activity/2022/02/15/fbi-and-usss-release-advisory-blackbyte-ransomware<br>
https://www.ic3.gov/Media/News/2022/220211.pdf<br>
