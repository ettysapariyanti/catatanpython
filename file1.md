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


Contoh Source Code Untuk di sisi server:

```python

# Cara membuat server sederhana
#!/usr/bin/python3

import socket

# Membuat obyek socket

serversocket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)

# mendapatkan nama mesin lokal

host = socket.gethostname()

port = 9999

# bind to the port

serversocket.bind((host,port))

# tampilkan hingga 5 request

serversocket.listen(5)

while True:

  # Membangun koneksi

```




## Pemrograman Jinja 2 untuk Membuat Website Menggunakan Framework Flask


source code yg berhasil menampilkan hasil query dari Mariadb ke Terminal menggunakan Jinja 2 :

```python

#!/usr/bin/python


from jinja2 import Template

import mariadb

import sys



try:

    koneksi = mariadb.connect(user="steven",password="kucing",host="1.1.3.7",port=3306,database="latihan")
    
    
except mariadb.Error as e:

    print(f"Gagal Terhubung Ke Server Mariadb: {e}")
    
    sys.exit(1)
    
    
    
kursor = koneksi.cursor()

kursor.execute("SELECT kodedatabarang,tanggalpendataan,kodebarang FROM datakomputer")

for (kodedatabarang, tanggalpendataan, kodebarang) in kursor:

    kodeDataBarang2=kodedatabarang
    
    tanggalPendataan2=tanggalpendataan
    
    kodeBarang2=kodebarang
    
    

data = {"kodeDataBarang3" : kodeDataBarang2, "tanggalPendataan3" : tanggalPendataan2, "kodeBarang3" : kodeBarang2}


template = """Isi Kolom Kode Data Barang : {{kodeDataBarang3}}

              Isi Kolom Tanggal Pendataan : {{tanggalPendataan3}}"""
            
            
tm = Template(template)


pesan = tm.render(data)


print(pesan)



```





_Salurkan donasi anda sebesar Rp 10.000 melalui : https://saweria.co/simpananfilepenting
Terimakasih_

_Please, send your donation as much as 1 USD through this link: https://paypal.me/ibnuchalid00
Thank you_
