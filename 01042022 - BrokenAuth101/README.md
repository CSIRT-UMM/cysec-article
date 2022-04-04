
![thumbBanner]()

## Otentikasi Rusak

Kerentanan autentikasi yang rusak dapat memungkinkan penyerang menggunakan metode manual dan/atau otomatis untuk mencoba mendapatkan kendali atas akun apa pun yang mereka inginkan dalam suatu sistem – atau bahkan lebih buruk lagi – untuk mendapatkan kendali penuh atas sistem.

Situs web dengan kerentanan otentikasi yang rusak sangat umum di web. Otentikasi yang rusak biasanya mengacu pada masalah logika yang terjadi pada mekanisme otentikasi aplikasi, seperti manajemen sesi yang buruk yang rentan terhadap enumerasi nama pengguna – ketika aktor jahat menggunakan teknik brute-force untuk menebak atau mengonfirmasi pengguna yang valid dalam suatu sistem.

Untuk meminimalkan risiko autentikasi yang rusak, hindari meninggalkan halaman login agar admin dapat diakses secara publik oleh semua pengunjung situs web:

- /administrator di Joomla!,
- /wp-admin/ di WordPress,
- /index.php/admin di Magento,
- /pengguna/login di Drupal.

Bentuk paling umum kedua dari kelemahan ini adalah memungkinkan pengguna untuk brute force kombinasi nama pengguna/sandi terhadap halaman tersebut.

### Jenis Kerentanan Otentikasi Rusak

Menurut OWASP Top 10, kerentanan ini bisa datang dalam berbagai bentuk. Aplikasi web berisi kerentanan autentikasi yang rusak jika:

- Mengizinkan serangan otomatis seperti isian kredensial, di mana penyerang memiliki daftar nama pengguna dan [sandi] yang valid).
- Memungkinkan brute force atau serangan otomatis lainnya.
- Mengizinkan kata sandi default, lemah, atau terkenal, seperti "Kata Sandi1" atau "admin/admin.″
- Menggunakan pemulihan kredensial yang lemah atau tidak efektif dan proses lupa kata sandi, seperti "jawaban berbasis pengetahuan", yang tidak dapat dibuat aman.
- Menggunakan kata sandi teks biasa, terenkripsi, atau hash lemah.
- Memiliki otentikasi multi-faktor yang hilang atau tidak efektif.
- Mengekspos ID sesi di URL (mis., Penulisan ulang URL).
- Tidak memutar ID sesi setelah login berhasil.
- Tidak membatalkan ID sesi dengan benar. Sesi pengguna atau token autentikasi, khususnya token single sign-on (SSO) yang tidak divalidasi dengan benar selama logout atau periode tidak aktif.

Menulis perangkat lunak yang tidak aman menghasilkan sebagian besar kerentanan ini. Mereka dapat dikaitkan dengan banyak faktor, seperti kurangnya pengalaman dari pengembang. Ini juga bisa menjadi konsekuensi dari kegagalan yang lebih dilembagakan seperti kurangnya persyaratan keamanan atau organisasi yang terburu-buru merilis perangkat lunak, dengan kata lain, memilih perangkat lunak yang berfungsi daripada perangkat lunak yang aman.

### Bagaimana Anda mencegah kerentanan otentikasi yang rusak?

Untuk menghindari kerentanan autentikasi yang rusak, pastikan pengembang menerapkan praktik terbaik keamanan situs web. Dukung mereka dengan menyediakan akses ke audit keamanan eksternal dan waktu yang cukup untuk menguji kode dengan benar sebelum diterapkan ke produksi.

Rekomendasi teknis OWASP adalah sebagai berikut:

- Jika memungkinkan, terapkan autentikasi multi-faktor untuk mencegah serangan otomatis, isian kredensial, kekerasan, dan penggunaan kembali kredensial yang dicuri.
- Jangan mengirim atau menyebarkan dengan kredensial default apa pun, terutama untuk pengguna admin.
- Menerapkan pemeriksaan kata sandi yang lemah, seperti menguji kata sandi baru atau yang diubah terhadap daftar 10.000 kata sandi terburuk.
- Sejajarkan panjang sandi, kompleksitas, dan kebijakan rotasi dengan NIST pedoman 800-63 B di bagian 5.1.1 untuk Rahasia yang Dihafal atau bukti modern lainnya- kebijakan kata sandi berbasis.
- Pastikan pendaftaran, pemulihan kredensial, dan jalur API diperkuat terhadap serangan enumerasi akun dengan menggunakan pesan yang sama untuk semua hasil.
- Batasi atau semakin tunda upaya login yang gagal. Catat semua kegagalan dan peringatkan administrator ketika isian kredensial, kekerasan, atau serangan lainnya terdeteksi.
- Gunakan pengelola sesi built-in sisi server, aman, yang menghasilkan ID sesi acak baru dengan entropi tinggi setelah login. ID sesi tidak boleh ada di URL. Id juga harus disimpan dengan aman dan tidak valid setelah logout, idle, dan timeout absolut.

Sources:<br>
https://owasp.org/Top10/A01_2021-Broken_Access_Control/