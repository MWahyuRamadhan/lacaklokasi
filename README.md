# lacaklokasi 
====
* Alat untuk mengambil informasi Geolokasi IP
* Didukung oleh [ ip-api ](http://ip-api.com/docs/)


Persyaratan
=====
* Python 3.x
* termcolor
* warna


Unduh/Instalasi
====
* git clone https://github.com/maldevel/IPGeoLocation
* pip3 install -r requirements.txt --user

jika pip3 hilang:
* apt-get install python3-setuptools
* easy_install3 pip
* pip3 install -r requirements.txt


Fitur
====
* Ambil IP atau Geolokasi Domain.
* Ambil Geolokasi IP Anda sendiri.
* Ambil Geolokasi untuk IP atau Domain yang dimuat dari file. Setiap target di baris baru.
* Tentukan string Agen Pengguna kustom Anda sendiri.
* Pilih string User-Agent acak dari file. Setiap string Agen Pengguna di baris baru.
* Dukungan proxy.
* Pilih proxy acak dari file. Setiap URL proxy di baris baru.
* Buka geolokasi IP di Google Maps menggunakan browser bawaan.
* Ekspor hasil ke format csv, xml dan txt.


Informasi Geolokasi
====
* ASN
* Kota
* Negara
* Kode Negara
* ISP
* Lintang
* Garis bujur
* Organisasi
* Kode Wilayah
* Nama Wilayah
* Zona waktu
* Kode Pos


Penggunaan
====
```
$ ./ip2geolocation.py
penggunaan: ipgeolocation.py [-h] [-m] [-t TARGET] [-T file] [-u User-Agent]
                        [-U file] [-g] [--noprint] [-v] [--nolog] [-x PROXY]
                        [-X file] [-e file] [-ec file] [-ex file]
IPGeolocation 2.0.4
--[ Ambil informasi Geolokasi IP dari ip-api.com
--[ Hak Cipta (c) 2015-2016 maldevel (@maldevel)
--[ Layanan ip-api.com akan secara otomatis melarang alamat IP apa pun yang melakukan lebih dari 150 permintaan per menit.
argumen opsional:
  -h, --help tampilkan pesan bantuan ini dan keluar
  -m, --my-ip Dapatkan info Geolokasi untuk alamat IP saya.
  -t TARGET, --target TARGET
                        Alamat IP atau Domain yang akan dianalisis.
  -T file, --tlist file
                        Daftar target IP/Domain, setiap target di baris baru.
  -u User-Agent, --user-agent User-Agent
                        Setel header permintaan Agen-Pengguna (default: IP2GeoLocation 2.0.3).
  -U file, --ulist file
                        Daftar string User-Agent, setiap string di baris baru.
  -g Buka lokasi IP di peta Google dengan browser default.
  --noprint IPGeolocation akan mencetak info IP Geolocation ke terminal. Dimungkinkan untuk memberi tahu IPGeolocation n
ot untuk mencetak hasil ke terminal dengan opsi ini.
  -v, --verbose Mengaktifkan keluaran verbose.
  --nolog IPGeolocation akan menyimpan file .log. Dimungkinkan untuk memberi tahu IPGeolocation untuk tidak menyimpan log itu
file dengan opsi ini.
  -x PROXY, --proxy PROXY
                        Siapkan server proxy (contoh: http://127.0.0.1:8080)
  -X file, --xlist file
                        Daftar proxy, setiap url proxy di baris baru.
  -e file, --txt file Hasil ekspor.
  -ec file, --csv file Ekspor hasil dalam format CSV.
  -ex file, --xml file Ekspor hasil dalam format XML.
```
  

Contoh
====
**Ambil Geolokasi IP Anda**
* ./ip2geolocation.py -m

**Ambil Geolokasi IP**
* ./ip2geolocation.py -t xxxx

**Ambil Geolokasi Domain**
* ./ip2geolocation.py -t example.com

**Jangan simpan file .log**
* ./ip2geolocation.py -t example.com --nolog

**String Agen Pengguna Kustom** 
* ./ip2geolocation.py -t xxxx -u "Mozilla/5.0 (Windows NT 6.3; WOW64; Trident/7.0; rv:11.0) seperti Gecko"

**Menggunakan Proksi**
* ./ip2geolocation.py -t xxxx -x http://127.0.0.1:8080

**Menggunakan Proksi acak**
* ./ip2geolocation.py -t xxxx -X /path/to/proxies/filename.txt

**Pilih string Agen-Pengguna secara acak**
* ./ip2geolocation.py -t xxxx -U /path/to/user/agent/strings/filename.txt

**Ambil geolokasi IP dan buka lokasi di peta Google dengan browser default**
* ./ip2geolocation.py -t xxxx -g

**Ekspor hasil ke file CSV**
* ./ip2geolocation.py -t xxxx --csv /path/to/results.csv

**Ekspor hasil ke file XML**
* ./ip2geolocation.py -t xxxx --xml /path/to/results.xml

**Ekspor hasil ke file TXT**
* ./ip2geolocation.py -t xxxx -e /path/to/results.txt

**Ambil Geolokasi IP untuk banyak target**
* ./ip2geolocation.py -T /path/to/targets/targets.txt

**Ambil Geolokasi IP untuk banyak target dan ekspor hasil ke xml**
* ./ip2geolocation.py -T /path/to/targets/targets.txt --xml /path/to/results.xml

**Jangan mencetak hasil ke terminal**
* ./ip2geolocation.py -m -e /path/to/results.txt --noprint
