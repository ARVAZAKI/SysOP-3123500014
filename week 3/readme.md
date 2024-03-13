<div align="center">
  <h1 style="text-align: center;font-weight: bold"><br>Sistem Operasi</h1>
  <h4 style="text-align: center;">Dosen Pengampu : Dr. Ferry Astika Saputra, S.T., M.Sc.</h4>
</div>
<br />
<div align="center">
  <img src="https://upload.wikimedia.org/wikipedia/id/4/44/Logo_PENS.png" alt="Logo PENS">
  <h3 style="text-align: center;">Disusun Oleh : </h3>
  <p style="text-align: center;">
    <strong>Fauzan Abderrasheed (3123500020) </strong><br>
    <strong>Muhammad Rafi Dhiyaulhaq (3123500004) </strong><br>
    <strong>Arva Zaki Fanadzan (3123500014)</strong>
  </p>
<h3 style="text-align: center;line-height: 1.5">Politeknik Elektronika Negeri Surabaya<br>Departemen Teknik Informatika Dan Komputer<br>Program Studi Teknik Informatika<br>2023/2024</h3>
  <hr><hr>
  </div>

  ## Daftar Isi
1. [Soal](#soal)
2. [Perbandingan](#perbandingan)
3. [Analisa](#analisa)
3. [Kesimpulan](#kesimpulan)
### Soal
Jalankan VM Debian anda, lalu lakukan clone https://github.com/ferryastika/flops-iops. Compile dan eksekusi sesuai petunjuk. Sesuiakan jumlah thread dengan jumlah CPU yang ada di VM Debianmu. Catat hasilnya dan jelaskan arti dari hasil ekskusi. Lakukan sebanyak 5 kali. Bandingkan hasilnya antar temanmu. Buat Plot perbandinnga hasil untuk masing-masing PC di tiap kelompokmu. Analisa hasil percobaan tadi dan beri kesimpulan tentang IOPS dan FLOPS.

##### Hasil Running program FLOPS
- Hasil pertama

Running dari program Arva Zaki
![App Screenshot](img/floparva1.jpg)

Running dari program Fauzan Abderrasheed
![App Screenshot](img/flopfauzan1.jpg)

Running dari program Muhammad Rafi Dhiyaulhaq
![App Screenshot](img/flopdhiya1.jpg)

- Hasil kedua
Running dari program Arva Zaki
![App Screenshot](img/floparva2.jpg)
Running dari program Fauzan Abderrasheed
![App Screenshot](img/flopfauzan2.jpg)
Running dari program Muhammad Rafi Dhiyaulhaq
![App Screenshot](img/flopdhiya2.jpg)

- Hasil ketiga
Running dari program Arva Zaki
![App Screenshot](img/floparva3.jpg)
Running dari program Fauzan Abderrasheed
![App Screenshot](img/flopfauzan3.jpg)
Running dari program Muhammad Rafi Dhiyaulhaq
![App Screenshot](img/flopdhiya3.jpg)

- Hasil keempat
Running dari program Arva Zaki
![App Screenshot](img/floparva4.jpg)
Running dari program Fauzan Abderrasheed
![App Screenshot](img/flopfauzan4.jpg)
Running dari program Muhammad Rafi Dhiyaulhaq
![App Screenshot](img/flopdhiya4.jpg)

- Hasil kelima
Running dari program Arva Zaki
![App Screenshot](img/floparva5.jpg)
Running dari program Fauzan Abderrasheed
![App Screenshot](img/flopfauzan5.jpg)
Running dari program Muhammad Rafi Dhiyaulhaq
![App Screenshot](img/flopdhiya5.jpg)


##### Hasil Running program IOPS
- Hasil pertama
Running dari program Arva Zaki
![App Screenshot](img/ioparva1.jpg)
Running dari program Fauzan Abderrasheed
![App Screenshot](img/iopfauzan1.jpg)
Running dari program Muhammad Rafi Dhiyaulhaq
![App Screenshot](img/iopdhiya1.jpg)
- Hasil kedua
Running dari program Arva Zaki
![App Screenshot](img/ioparva2.jpg)
Running dari program Fauzan Abderrasheed
![App Screenshot](img/iopfauzan2.jpg)
Running dari program Muhammad Rafi Dhiyaulhaq
![App Screenshot](img/iopdhiya2.jpg)
- Hasil ketiga
Running dari program Arva Zaki
![App Screenshot](img/ioparva3.jpg)
Running dari program Fauzan Abderrasheed
![App Screenshot](img/iopfauzan3.jpg)
Running dari program Muhammad Rafi Dhiyaulhaq
![App Screenshot](img/iopdhiya3.jpg)
- Hasil keempat
Running dari program Arva Zaki
![App Screenshot](img/ioparva4.jpg)
Running dari program Fauzan Abderrasheed
![App Screenshot](img/iopfauzan4.jpg)
Running dari program Muhammad Rafi Dhiyaulhaq
![App Screenshot](img/iopdhiya4.jpg)
- Hasil kelima
Running dari program Arva Zaki
![App Screenshot](img/ioparva5.jpg)
Running dari program Fauzan Abderrasheed
![App Screenshot](img/iopfauzan5.jpg)
Running dari program Muhammad Rafi Dhiyaulhaq
![App Screenshot](img/iopdhiya5.jpg)

### Perbandingan
<table>
<thead>
<tr>
  <th style="background-color: blue; color: white">Nama</th>
  <th style="background-color: blue; color: white">Jumlah CPU Core</th>
  <th style="background-color: blue; color: white">Max FLOPS (CPU Throughput)</th>
  <th style="background-color: blue; color: white">Max FLOPS (Single Core Throughput)</th>
  <th style="background-color: blue; color: white">Max IOPS (CPU Throughput)</th>
  <th style="background-color: blue; color: white">Max IOPS (Single Core Throughput)</th>
<tr>
</thead>
<tbody>
  <tr>
  <td>Fauzan Abderrasheed</td>
  <td>2</td>
  <td>8.373064</td>
  <td>4.194248</td>
  <td>8.291936</td>
  <td>4.153408</td>
  </tr>
   <tr>
  <td>Arva Zaki Fanadzan</td>
  <td>3</td>
  <td>20.068783</td>
  <td>6.704461</td>
  <td>15.786218</td>
  <td>5.274650</td>
  </tr>
   <tr>
  <td>Muhammad Rafi Dhiyaulhaq</td>
  <td>2</td>
  <td>9.831529</td>
  <td>4.921177</td>
  <td>9.251837</td>
  <td>4.626244</td>
  </tr>
</tbody>
</table>

#### Analisa
program yang dijalankan merupakan program benchmark untuk mengukur FLOPS (Floating-point Operations Per Second) dan IOPS (Input Output Operations per Second) pada CPU. Program dijalankan lima kali, masing-masing dengan jumlah inti CPU yang berbeda: 3, 2, dan 2. Hasilnya menunjukkan bahwa CPU memiliki peringkat FLOPS yang lebih tinggi ketika lebih banyak inti yang digunakan.
Secara keseluruhan, program benchmark menunjukkan bahwa peringkat FLOPS IOPS CPU meningkat seiring dengan meningkatnya jumlah inti CPU yang digunakan. Hal ini karena program ini mampu mendistribusikan beban kerja ke beberapa inti, sehingga memungkinkannya melakukan lebih banyak operasi secara bersamaan.

#### Kesimpulan
FLOPS mengukur jumlah operasi floating-point yang dapat dilakukan oleh unit pemrosesan pusat (CPU) dalam satu detik. Operasi floating-point adalah perhitungan yang melibatkan angka dengan titik desimal.
IOPS mengukur jumlah operasi bilangan bulat yang dapat dilakukan CPU dalam satu detik. Operasi bilangan bulat adalah perhitungan yang melibatkan bilangan bulat.
Kesimpulannya, FLOPS dan IOPS merupakan metrik penting untuk mengukur kinerja CPU. FLOPS penting untuk tugas-tugas yang melibatkan banyak perhitungan floating-point. IOPS penting untuk tugas-tugas yang melibatkan banyak operasi integer.