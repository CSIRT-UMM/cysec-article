![chromeUAFThumb](https://github.com/CSIRT-UMM/cysec-article/blob/main/28012022%20-%20GoogleChromeMultiVuln/chromeUAFThumb.png)

# Perbarui Google Chrome untuk Menambal Eksploitasi <i>Zero-Day</i> Baru!
Google telah meluncurkan perbaikan untuk lima kerentanan pada browser Chrome.
Dilacak sebagai `CVE-2021-4102`, kerentanan tersebut berhubungan dengan bug Use-After-Free dalam JavaScript V8 dan WebAssembly, yang dapat memiliki kerugian besar, mulai dari kerusakan data hingga eksekusi kode arbitrer.

Belum diketahui apakah kerentanan ini disalahgunakan dalam dunia nyata. Namun Google berupaya untuk memastikan bahwa sebagian besar pengguna Chrome diperbarui dengan perbaikan tambalan dan mencegah eksploitasi lebih lanjut oleh pelaku kriminal lainnya.

---
## Cara Memitigasi Kerentanan
Perbarui versi Google Chrome ke versi yang terbaru.
Jangan matikan pembaruan otomatis, agar patch dapat segera tersampaikan dan dipasang secara otomatis.
<br>Pembaruan dapat diakses melalui `Settings > Help > 'About Google Chrome'`

Pada pembaruan kali ini, Google telah mengatasi 17 zero-day vulnerabilities 2021 pada Chrome
```
    CVE-2021-21148 - Heap buffer overflow pada V8
    CVE-2021-21166 - Object recycle issue pada audio
    CVE-2021-21193 - Use-after-free pada Blink
    CVE-2021-21206 - Use-after-free pada Blink
    CVE-2021-21220 - Validasi yang kurang efektif dalam 'untrusted input' pada V8 x86_64
    CVE-2021-21224 - Type confusion pada V8
    CVE-2021-30551 - Type confusion pada V8
    CVE-2021-30554 - Use-after-free pada WebGL
    CVE-2021-30563 - Type confusion pada V8
    CVE-2021-30632 - Out of bounds write pada V8
    CVE-2021-30633 - Use-after-free pada Indexed DB API
    CVE-2021-37973 - Use-after-free pada Portals
    CVE-2021-37975 - Use-after-free pada V8
    CVE-2021-37976 - Kebocoran Informasi pada core
    CVE-2021-38000 - Validasi yang kurang efektif dalam 'untrusted input' pada Intents
    CVE-2021-38003 - Implementasi yang kurang baik pada V8

```

---
Sources:<br>
https://thehackernews.com/2021/12/update-google-chrome-to-patch-new-zero.html<br>
https://cwe.mitre.org/data/definitions/416.html<br>
https://thehackernews.com/2021/09/update-google-chrome-asap-to-patch-2.html
