# SQL Injection Techniques: Extracting Columns and Tables Using Python

Proyek ini adalah alat Python inovatif yang dirancang untuk mengeksplorasi kerentanan SQL Injection dan memanfaatkan kerentanan tersebut untuk mengekstraksi metadata database, termasuk nama tabel dan kolom. Alat ini menggabungkan teknik eksploitasi SQL dengan pemrosesan Python untuk memberikan keluaran yang terstruktur dan mudah dipahami.

Kode ini memanfaatkan berbagai pustaka Python seperti **`requests`**, **`BeautifulSoup`**, dan **`PrettyTable`** untuk mempermudah pengambilan data dari server yang rentan, memformat hasil, dan menampilkan informasi dengan rapi.

---

## 1. Key Features

- **Ekstraksi Metadata Database**  
  Alat ini mampu mengekstrak informasi kunci seperti nama database, nama pengguna, versi, direktori data, dan nama host melalui hasil eksploitasi SQL Injection.

- **Pendeteksian Struktur Tabel dan Kolom**  
  Alat ini secara otomatis memisahkan nama tabel dan kolom dari data hasil injeksi SQL, sehingga menghasilkan laporan tabel yang terstruktur.

- **Visualisasi Data yang Terorganisir**  
  Menggunakan pustaka **`PrettyTable`**, data ditampilkan dalam bentuk tabel yang terstruktur dengan kolom dan baris untuk memudahkan analisis.

- **Pemrosesan Data HTML Otomatis**  
  HTML hasil respons server diproses dengan pustaka **`BeautifulSoup`**, yang secara efektif mengekstrak teks untuk analisis lebih lanjut.

- **Kesesuaian untuk Pendidikan Keamanan Siber**  
  Alat ini dirancang untuk tujuan pembelajaran dan penelitian keamanan, memberikan wawasan praktis tentang teknik eksploitasi SQL Injection.

---

## 2. Explanation of New Features

- **Penggunaan SQL Injection Berdasarkan Parameter Query URL**  
  Kode ini menggunakan parameter URL untuk memasukkan payload SQL Injection, memungkinkan pengguna menyesuaikan serangan mereka berdasarkan target spesifik.

- **Ekstraksi Multi-Level Data**  
  Alat ini secara otomatis memetakan data dari `information_schema` untuk mengeksplorasi tabel dan kolom dengan cara iteratif dan terstruktur.

- **Tampilan Metadata Database yang Diperluas**  
  Informasi seperti `database()`, `user()`, `version()`, dan direktori database ditampilkan untuk memberikan wawasan lebih luas tentang lingkungan target.

---

## 3. Installation Steps

Untuk menginstal dan menjalankan alat ini, ikuti langkah-langkah berikut:

1. **Clone Repository**  
```bash
   git clone https://github.com/lamcodeofpwnosec/SQL-Extraction.git
   cd SQL-Extraction
```
2. Persyaratan Sistem
Pastikan Anda memiliki Python `3.x` terinstal.
3. Instalasi Dependensi
Jalankan perintah berikut untuk menginstal pustaka yang diperlukan:
```
pip install requests beautifulsoup4 prettytable
```
4. Konfigurasi URL Target
Edit variabel `url` dalam skrip Python dengan URL target yang mengandung kerentanan SQL Injection.

## 4. Usage of Features
Setelah instalasi selesai, alat dapat dijalankan langsung menggunakan perintah berikut:
```
python sql_extraction.py
```
- Penggunaannya:
  * Skrip akan mengirim permintaan HTTP ke URL target yang berisi payload SQL Injection.
  * Data respons akan diproses untuk mengekstrak metadata dan struktur tabel database.
- Contoh Output Metadata:
```
=== Database Metadata ===
+-------------------+-----------------------------------+
| Property          | Value                             |
+-------------------+-----------------------------------+
| Database          | target_database                   |
| User              | root@localhost                   |
| Version           | 5.7.33-log                       |
| Hostname          | target_host                      |
| Data dir          | /var/lib/mysql/                  |
+-------------------+-----------------------------------+
```
- Contoh Output Struktur Tabel:
```
=== Table: users ===
+--------------+--------------+
| Column Index | Column Name  |
+--------------+--------------+
| 1            | id           |
| 2            | username     |
| 3            | password     |
+--------------+--------------+
```
## 5. Explanation of Generated Output Files
Proyek ini tidak menghasilkan file output tetapi menyajikan data langsung di terminal dalam format tabel. Untuk menyimpan hasil, Anda dapat mengarahkan output ke file teks menggunakan:
```
python sql_extraction.py > output.txt
```
File yang dihasilkan dapat digunakan untuk analisis mendalam lebih lanjut.

[![asciicast](https://asciinema.org/a/693706.svg)](https://asciinema.org/a/693706)
Skrip ini sangat cocok untuk penguji penetrasi untuk menghitung basis data & mengekstrak kolom secara efisien. 🚀

&copy; [PT. Pwn0Sec DIGITAL TECHNOLOGIES LTD.](https://www.pwn0sec.com/) 
