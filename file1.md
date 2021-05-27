## Catatan Python 3

Untuk di python, sekarang sedang tertarik mempelajari pemrograman python yang terkait dengan masalah jaringan komputer. Karena untuk mencoba settingan firewall IP Tables di Linux. Nantinya settingan IP Tables ini bisa untuk mengatasi masalah sharing internet antar komputer Linux, sharing internet dari komputer Linux ke Windows, memasang proxy semacam Squid Web Proxy, dan juga untuk memfungsikan linux selayaknya sebuah router seperti Mikrotik.


Berikut ini contoh source code untuk sisi client:

```python
import socket

# create a socket object

s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)

# get local machine name

host = socket.gethostname()

port = 9999

# Koneksi ke hostname dan port

s.connect((host, port))

# Menerima data tidak lebih dari 1024 bytes

msg = s.recv(1024)

s.close()

print (msg.decode('ascii'))

```


_Salurkan donasi anda sebesar Rp 10.000 melalui : https://saweria.co/simpananfilepenting
Terimakasih_

_Please, send your donation as much as 1 USD through this link: https://paypal.me/ibnuchalid00
Thank you_
