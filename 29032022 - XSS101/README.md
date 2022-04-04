
![thumbBanner](https://github.com/CSIRT-UMM/cysec-article/blob/main/29032022%20-%20XSS101/xss.png)

## Pembuatan Cross Site Scripting (XSS)

Cross Site Scripting (XSS) adalah kerentanan luas yang memengaruhi banyak aplikasi web. Serangan XSS terdiri dari menyuntikkan skrip sisi klien berbahaya ke situs web dan menggunakan situs web sebagai metode propagasi.

Risiko di balik XSS adalah memungkinkan penyerang untuk menyuntikkan konten ke situs web dan mengubah cara tampilannya, memaksa browser korban untuk mengeksekusi kode yang diberikan oleh penyerang saat memuat halaman.

### Contoh Kerentanan XSS

Bayangkan Anda berada di panel wp-admin WordPress Anda menambahkan posting baru. Jika Anda menggunakan plugin dengan kerentanan XSS tersimpan yang dieksploitasi oleh peretas, itu dapat memaksa browser Anda untuk membuat pengguna admin baru saat Anda berada di panel wp-admin atau dapat mengedit posting dan melakukan tindakan serupa lainnya .

Kerentanan XSS memberi penyerang kendali penuh atas perangkat lunak terpenting komputer saat ini: browser.

Kembali pada tahun 2017, tim peneliti kami mengungkapkan kerentanan XSS yang tersimpan di inti situs web WordPress. Penyerang jarak jauh dapat menggunakan kerentanan ini untuk merusak posting acak di situs WordPress dan menyimpan kode JavaScript berbahaya di dalamnya.

### Jenis XSS

Menurut OWASP Top 10, ada tiga jenis skrip lintas situs:

- **Reflected XSS**: Aplikasi atau API menyertakan input pengguna yang tidak divalidasi dan tidak lolos sebagai bagian dari output HTML. Serangan yang berhasil dapat memungkinkan penyerang untuk mengeksekusi HTML dan JavaScript sewenang-wenang di browser korban. Biasanya pengguna perlu berinteraksi dengan beberapa tautan berbahaya yang mengarah ke halaman yang dikendalikan penyerang, seperti situs web berbahaya, iklan, atau sejenisnya.
    
- **Stored XSS**: Aplikasi atau API menyimpan input pengguna yang tidak bersih yang dilihat di lain waktu oleh pengguna atau administrator lain. XSS yang disimpan sering dianggap sebagai risiko tinggi atau kritis.
    
- **DOM XSS**: Kerangka kerja JavaScript, aplikasi satu halaman, dan API yang secara dinamis menyertakan data yang dapat dikontrol penyerang ke halaman rentan terhadap DOM XSS. Idealnya, aplikasi tidak akan mengirim data yang dapat dikontrol penyerang ke API JavaScript yang tidak aman. Serangan XSS yang umum termasuk pencurian sesi, pengambilalihan akun, bypass MFA, penggantian atau perusakan simpul DOM (seperti panel login Trojan), serangan terhadap browser pengguna seperti unduhan perangkat lunak berbahaya, keylogging, dan serangan sisi klien lainnya.
    

### Mengurangi Risiko XSS

Ada teknologi seperti [Sucuri Firewall](https://sucuri.net/website-firewall/) yang dirancang untuk membantu mengurangi serangan XSS. Jika Anda seorang pengembang, berikut adalah beberapa wawasan tentang cara mengidentifikasi dan menjelaskan kelemahan ini.

### Cara Mencegah Kerentanan XSS

Tindakan pencegahan untuk mengurangi kemungkinan serangan XSS harus mempertimbangkan pemisahan data yang tidak tepercaya dari konten browser yang aktif. Pedoman OWASP memberikan beberapa tip praktis tentang cara mencapainya:

- Menggunakan kerangka kerja yang secara otomatis keluar dari XSS berdasarkan desain, seperti Ruby on Rails terbaru, React JS. Pelajari batasan perlindungan XSS setiap kerangka kerja dan tangani kasus penggunaan yang tidak tercakup dengan tepat.
- Melarikan diri dari data permintaan HTTP yang tidak tepercaya berdasarkan konteks dalam output HTML (tubuh, atribut, JavaScript, CSS, atau URL) akan menyelesaikan kerentanan XSS yang Tercermin dan Tersimpan. 
- Menerapkan pengkodean peka konteks saat memodifikasi dokumen browser di sisi klien bertindak melawan DOM XSS. Jika hal ini tidak dapat dihindari, teknik pelolosan peka konteks serupa dapat diterapkan ke API browser seperti yang dijelaskan dalam.
- Mengaktifkan kebijakan keamanan konten (CSP) adalah kontrol mitigasi pertahanan mendalam terhadap XSS. Ini efektif jika tidak ada kerentanan lain yang memungkinkan penempatan kode berbahaya melalui file lokal yang disertakan.

Sources:<br>
https://owasp.org/www-project-top-ten/2017/A7_2017-Cross-Site_Scripting_(XSS)
