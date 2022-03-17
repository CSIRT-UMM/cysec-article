
  
![Thumb](https://github.com/CSIRT-UMM/cysec-article/blob/main/17032022%20-%20LinuxDirtyPipe/Thumb.png)

#  Kerentanan DirtyPipe Tingkat Kernel Linux 


Kerentanan ditemukan dalam cara anggota "flags" dari struktur buffer pipa tidak memiliki inisialisasi yang tepat dalam fungsi "copy_page_to_iter_pipe dan push_pipe" di kernel Linux dan dengan demikian dapat berisi nilai basi. Pengguna lokal non-root dapat menggunakan kelemahan ini untuk menulis ke halaman di cache halaman yang didukung oleh file hanya-baca dan dengan demikian meningkatkan hak istimewa mereka pada sistem.


##  Respons Ubuntu

Max Kellermann menemukan bahwa kernel Linux salah menangani pipa Unix. Penyerang lokal berpotensi menggunakan ini untuk memodifikasi file apa pun yang dapat dibuka untuk dibaca.

##  Pernyataan Red Hat

Red Hat Product Security menyadari masalah ini. Pembaruan akan dirilis saat tersedia.

Perhatikan bahwa vektor serangan flag PIPE_BUF_FLAG_CAN_MERGE tidak tersedia di Red Hat Enterprise Linux 8 dan dengan demikian eksploitasi yang diketahui saat ini memanfaatkan flag ini tidak berfungsi. Masalah mendasar (kurangnya inisialisasi struktur pipe_buffer yang tepat) masih ada dan cara-cara baru lainnya yang mengarah pada eksploitasi yang berhasil tidak dapat sepenuhnya dikesampingkan.

## Mitigasi Kerentanan

Update ke Linux 5.16.11, 5.15.25 dan 5.10.102.<br>

##  PoC
WriteUp PoC ditulis oleh Max Kellermann pada website berikut
https://dirtypipe.cm4all.com/

---

Sources:<br>

https://access.redhat.com/security/cve/cve-2022-0847<br>
https://ubuntu.com/security/CVE-2022-0847<br>
https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2022-0847<br>
https://github.com/CYB3RK1D/CVE-2022-0847-POC<br>
https://dirtypipe.cm4all.com/<br>
