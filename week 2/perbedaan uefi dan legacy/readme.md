<div align="center">
  <h1 style="text-align: center;font-weight: bold">Perbedaan Uefi dan Legacy<br>Sistem Operasi</h1>
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
1. [Pendahuluan](#apa-itu-bios)
2. [Soal](#soal)
3. [Referensi](#referensi)
## apa itu BIOS?
![App Screenshot](img/bios.jpg)
<strong>BIOS </strong>merupakan singkatan dari Basic Input Output System. merupakan suatu software (ditulis dalam bahasa assembly) yang mengatur fungsi dasar dari perangkat keras (hardware) komputer. BIOS tertanam dalam sebuah chip memory (ROM ataupun Flash Memory) berbahan Comlpimentari Metal Oxide Semiconductor (CMOS) yang terdapat pada motherboard. Sebuah baterai yang biasa disebut sebagai baterai CMOS berfungsi untuk menjaga agar tanggal dan settingan lainnya yang telah kita set pada BIOS tidak hilang atau kembali ke konfigurasi awal meskipun komputer dimatikan.
## apa itu UEFI?
![App Screenshot](img/uefi.png)
<strong>UEFI</strong> adalah Unified Extensible Firmware Interface, UEFI merupakan teknologi terbaru yang dibuat untuk penyempurnaan dari BIOS yang lama menjadi BIOS yang memiliki fungsi lebih optimal.
Lantas kapan UEFI ada? kehadiran nya bermula saat ada standard EFI pada komputer sekitar tahun 1990 an, saat itulah UEFI muncul. pada tahun tersebut perusahaan yang sudah memakai standar EFI yaitu Intel dan Hp.
Setelah sekian tahun dan dengan kemajuan teknologi, sistem EFI mulai berkembang supaya dapat dioperasikan di semua perangkat komputer. dari situlah muncul sistem baru yang bernama UEFI atau EFI V2.X ini, namun banyak orang yang mengenal nya dengan sebutan UEFI.
Untuk saat ini sistem UEFI sudah banyak dioperasikan di semua komputer maupun laptop generasi terbaru, karena saat ini perkembangan hardware komputer sudah canggih, BIOS sendiri sudah hampir tidak mampu memberikan support, terutama pada pengguna hardisk dengan kapasitas 2 terabyte.
Jadi fungsi UEFI adalah untuk menggantikan dari kinerja BIOS yang sudah mengalami ketertinggalan zaman
## apa itu LEGACY?
![App Screenshot](img/legacy.png)

<strong>LEGACY </strong>adalah alat yang membantu firmware Bios dalam memproses boot, dimana fungsi dari legacy yaitu untuk menyimpan daftar perangkat penyimpanan yang bisa untuk di boot seperti floopy disk drives, optical disk drive dan hard disk drive,
Saat kamu menyalakan komputer, secara tidak langsung BIOS akan beroperasi dan melakukan Power On Self-Test (POST) yang ditandai dengan bunyi bip dari sistem internal, dimana suara tersebut menandakan booting berjalan dengan normal

Sesudah melakukan proses POST,  firmware tersebut akan mengambil sektor pertama dari setiap perangkat penyimpanan yang sudah dijadikan target dan menyimpannya ke dalam memori,
Di samping itu, firmware akan melakukan pemindaian terhadap MBR (Master Boot Record) yang sudah tervalidasi. Setelah menemukan MBR yang sah, firmware akan melanjutkan untuk  mengeksekusi ke bootloader untuk memilih partisi tempat booting.

Ketika dalam proses booting terdapat bagian yang tidak sesuai atau tidak valid, maka firmware akan meneruskan ke perangkat selanjutnya sesuai dengan urutan prioritas.

### SOAL

## Apa perbedaan UEFY DAN LEGACY?
![App Screenshot](img/legacyuefi.webp)
1. Struktur dan Antarmuka

UEFI memiliki antarmuka yang lebih modern dan grafis dibandingkan dengan Legacy BIOS yang berbasis teks. Hal ini memudahkan pengguna dalam mengatur pengaturan firmware dan memantau berbagai informasi tentang perangkat keras. 📊

2. Kapasitas dan Skalabilitas

UEFI mendukung partisi boot berkapasitas lebih besar dibandingkan dengan Legacy BIOS. UEFI juga didesain dengan kemampuan skala yang lebih baik, sehingga dapat mendukung sistem operasi dan perangkat keras yang lebih modern dan kompleks. 📈

3. Kecepatan Booting

UEFI mampu melakukan proses booting secara lebih cepat dibandingkan dengan Legacy BIOS. Hal ini karena UEFI dapat melakukan inisialisasi perangkat keras secara paralel, sedangkan Legacy BIOS melakukan inisialisasi secara serial. ⏱

4. Keamanan

UEFI memberikan fitur keamanan yang lebih baik dibandingkan dengan Legacy BIOS. UEFI memiliki mekanisme verifikasi digital yang memastikan integritas firmware dan membantu mencegah serangan malware yang merusak atau menggantikan firmware. 🔒

5. Kompatibilitas

Legacy BIOS memiliki tingkat kompatibilitas yang lebih tinggi dengan perangkat keras dan sistem operasi yang sudah ada sejak lama. UEFI, meskipun mendukung mode kompatibilitas dengan Legacy BIOS, tidak dapat berfungsi secara optimal jika digunakan dengan perangkat keras atau sistem operasi yang didesain khusus untuk mode UEFI. 🚀

6. Konfigurasi

UEFI menyediakan antarmuka pengaturan yang lebih lengkap dan mudah digunakan daripada Legacy BIOS. Pengguna dapat mengatur berbagai opsi terkait booting, hardware, dan keamanan dengan lebih fleksibel melalui antarmuka grafis yang intuitif. ⚙

7. Perkembangan dan Dukungan

UEFI merupakan standar industri yang aktif berkembang dan mendapatkan dukungan penuh dari para produsen perangkat keras dan perangkat lunak. Legacy BIOS, meskipun masih digunakan secara luas, sudah tidak lagi mendapatkan pembaruan rutin dan dukungan dari banyak produsen

## Referensi
<ul>
<li><a href = "https://seberkas.com/perbedaan-uefi-dan-legacy/">Apa itu UEFI?</a?></li>
<li><a href = "https://seberkas.com/perbedaan-uefi-dan-legacy/">Apa itu LEGACY?</a?></li>
<li><a href = "https://www.perbedaan.co.id/perbedaan-uefi-dan-legacy/#Pendahuluan">Perbedaan UEFI dan LEGACY?</a?></li>
</ul>