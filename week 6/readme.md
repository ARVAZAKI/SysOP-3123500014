<div align="center">
  <h1 style="text-align: center;font-weight: bold">praktikum 6<br>Sistem Operasi</h1>
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

### Percobaan 5

1. Cara lain meletakkan job pada background dengan job secara normal (pada foreground),stop dan memulai lagi pada background 
```
$ yes > /dev/null
```
Hentikan sementara job (suspend),bukan menghentikannya (terminate),tetapi menghentikan sementara job sampai di restart. untuk menghentikan sementara menggunakan Ctrl+Z.

![App Screenshot](img/5.1.jpg)

Analisa :     Cara lain meletakkan job pada background dengan memulai job secara normal (pada foreground), stop job dan memulai lagi pada background. Gunakan perintah `yes > /dev/null` untuk memulai job baru. Hentikan sementara job (suspend), bukan menghentikannya (terminate), tetapi menghentikan sementara job sampai di restart. Untuk menghentikan sementara job gunakan *Ctrl + Z*



2. untuk restart job pada foregorund, gunakan perintah fg
```
$ fg
```
![App Screenshot](img/5.2.jpg)

 Analisa : 
    Perintah `fg` disini digunakan untuk me-restart job pada *foreground*.

3. Shell akan menampilkan nama perintah yang diletakkan pada foreground,stop job lagi dengan Ctrl+Z. Kemudian gunakan perintah bg untuk meletakkan job pada backgroud
```
$ bg
```
Job ini tidak bisa dihentikan menggunakan Ctrl+Z,karena job berada pada background. untuk menghentikannya,letakkan job pada foregorund dengan fg dan kemudian Ctrl+Z

![App Screenshot](img/5.3.jpg)

 Analisa : 
    Setelah instruksi `fg`, Shell akan menampilkan nama perintah yang diletakkan di *foreground*. Stop job lagi dengan *Ctrl + Z*. Kemudian gunakan perintah `bg` untuk meletakkan job pada *background*. 
     

4. Job pada background dapat digunakan untuk menampilkan teks pada terminal, dimana dapat diabaikan jika mencoba mengerjakan job lain.
```
$ yes &
```
untuk menghentikannya tidak dapat menggunakan Ctrl+Z. job harus dipindah ke foreground,baru dihentikan dengan cara tekan fg dan enter, kemudian dilanjutkan dengan Ctrl+Z untuk menghentikkan sementara

![App Screenshot](img/5.4.jpg)

![App Screenshot](img/5.5.jpg)

 Analisa : 
    Job pada *background* dapat digunakan untuk menampilkan teks pada terminal, dimana dapat diabaikan jika mencoba mengerjakan job lain seperti perintah di atas. Untuk menghentikannya tidak dapat menggunakan *Ctrl + C*. Job harus dipindah ke *foreground* baru diberhentikan dengan cara tekan `fg` dan tekan enter, Kemudian lanjutkan dengan *Ctrl + Z* untuk menghentikan sementara

5. Apabila ingin menampilkan banyak job dalam satu waktu,letakkan job pada foreground atau background dengan memberikan job id
```
$ fg %2 atau $ %2
$ bg %2
```
![App Screenshot](img/5.6.jpg)

 Analisa : 
    Perintah di atas digumakan apabila ingin menjalankan banyak job dalam satu waktu, letakkan job pada *foreground* atau *background* dengan memberikan job ID. 

6. tekan fg dan enter kemudian dilanjutkan dengan ctrl+z untuk menghentikan sementara

![App Screenshot](img/5.7.jpg)

![App Screenshot](img/5.8.jpg)

Analisa : 
    tekan `fg` dan tekan *Enter*, kemudian dilanjutkan dengan *Ctrl-Z* untuk menghentikan sementara

7. lihat job dengan perintah ps -fae dan tekan enter kemudian hentikan proses dengan perintah kill.
```
$ ps -fae
$ kill -9 <nomor pid>
```

![App Screenshot](img/5.8.jpg)

![App Screenshot](img/5.10.jpg)

![App Screenshot](img/5.11.jpg)

Analisa : 
    Lihat job dengan perintah `ps -fae` dan tekan Enter. Kemudian hentikan proses dengan perintah kill.


### Percobaan 6

1. Login sebagai root
2. buka 3 terminal,tampilkan pada screen yang sama

![App Screenshot](img/6.1.jpg)

3. Pada setiap terminal, ketik PS1 = "\w;" diikuti enter  \w menampilkan path pada direktori home 

![App Screenshot](img/6.2.jpg)

4. Karena login sebagai root, maka akan ditampilkan ~: pada setiap terminal. Untuk setiap
terminal ketik pwd dan tekan Enter untuk melihat bahwa Anda sedang berada pada
direktori /root.

![App Screenshot](img/6.3.jpg)

5. Buka terminal lagi (keempat), atur posisi sehingga keempat terminal terlihat pada screen.

![App Screenshot](img/6.4.jpg)

6. Pada terminal keempat, ketik top dan tekan Enter. Maka program top akan muncul. Ketik i. Top akan menampilkan proses yang aktif .ketik lmt Top tidak lagi menampilkan informasi pada bagian atas dari screen.pada percobaan ini terminal keempat sebagai jendela

7. Pada terminal 1 bukalah program executable C++ dengan mengetik yes dan enter.

8. Ulangi langkah 7 untuk terminal 2

9. jendela top akan menampilkan dua program yes sebagai proses yang berjalan. nilai %CPU sama pada keduanya. hal ini berarti kedua proses mengkonsumsi waktu proses yang sama dan berjalan sama cepat. PID dari kedua proses akan berbeda ,misalnya 3148 dan 3149.kemudian gunakan terminal 3 dan ketik renice 19 < pid teminal 1 > contoh renice 19 3148 dan tekan enter.hal ini berarti mengganti penjadwalan prioritas dari proses ke 19.

![App Screenshot](img/6.5.jpg)

Analisa : 
Perintah top berfungsi untuk mengetahui semua rincian proses yang berjalan dan beberapa fungsi lainnya. Dengan mengetikkan i pada window top maka akan menghasilkan proses yang sedang aktif sedangkan opsi Imt digunakan untuk menghilangkan atau menampilkan informasi pada bagian atas dari tampilan top. Perintah yes diatas untuk membuat proses baru. PID yang digunakan adalah 2299 dan menjalankan perintah $ renice pada terminal 1 yang berarti bahwa menggati penjadwalan prioritas dari proses ke 19 dan terlihat bahwa NI berubah menjadi 19.


10. Tunggu beberapa saat sampai program top berubah dan terlihat pada jendela Top. pada kolom stat memperlihatkan N untuk proses 3148. Hal ini berarti bahwa penjadwalan prioritas untuk proses 3148 lebih besar/lebih lambat dari 0, proses 3149 lebih cepat.

11. program top juga memiliki fungsi yang sama dengan progran renice. pilih jendela top dan tekan r,program top terdapat prompt pid to renice: tekan 3148 (ingat bahwa anda harus mengganti 3148 dengan pid anda sendiri) dan tekan enter. program top memberikan prompt Renice PID 3148 to value: tekan -19 dan enter.

![App Screenshot](img/6.6.jpg)

![App Screenshot](img/6.7.jpg)

12. Tunggu beberapa saat sampai top berubah dan nilai %CPU pada kedua proses. sekarang proses 2327 lebih cepat dibanding proses 2336. kolom status menunjukan < pada proses 2327 yang menunjukan penjadwalan prioritas lebih rendah / lebih cepat dari nilai 0.

![App Screenshot](img/6.8.jpg)

13. Pilih terminal 3 dan ketik nice -n -10 yes dan tekan enter. tunggu beberapa saat agar program top berubah dan akan terlihat proses primes ketiga .misalnya pid 4107. opsi -10 berada pada kolom NI(penjadwalan prioritas)

![App Screenshot](img/6.9.jpg)

14. Jangan menggunakan mouse dan keyboard selama 10 detik program top menampilkan proses yang aktif selain program yes. maka akan terlihat proses top terdaftar tetapi %CPU kecil (dibawah 1.0) dan konsisten. juga terlihat proses berhubungan dengan dekstop grafis seperti X,panel dll.

![App Screenshot](img/6.10.jpg)

15. Pindahkan mouse sehingga kursor berubah pada screen dan liat apa yang terjadi dengan tampilan top. proses tambahan akan muncul dan nilai %CPU berubah sebagai bagian grafis yang bekerja. satu alasan adalah bahwa proses  berjalan pada penjadwalan prioritas tinggi. pilih jendela top ketik r 4107 dan tekan enter. renice pid tersebut ketik 0 dan tekan enter . sekarang pindahkan mouse ke sekeliling screen,dan lihat perubahan nya.

![App Screenshot](img/6.10.jpg)

### Latihan 

1. Masuk ke tty2 dengan Ctrl+Alt+F2. Ketik ps –au dan tekan Enter. Kemudian
perhatikan keluaran sebagai berikut :
a. Sebutkan nama-nama proses yang bukan root

![App Screenshot](img/lat1.jpg)
semua proses kecuali /bin/login -p-- adalah bukan root

b. Tulis PID dan COMMAND dari proses yang paling banyak menggunakan CPU
time

![App Screenshot](img/lat1.jpg)

PID : 1799,dan 1949 <br> COMMAND : /bin/login -p-- , dan -bash

c. Sebutkan buyut proses dan PID dari proses tersebut

![App Screenshot](img/lat1.jpg)

/usr/liberxec-gdm-wayland-session dengan PID 1162

  d. Sebutkan beberapa proses daemon

pada beberapa proses yang tertampil tidak ada proses daemon


 e. Pada prompt login lakukan hal - hal sebagai berikut :
- $ csh
- $ who
- $ bash
- $ ls
- $ sh
- $ ps

![App Screenshot](img/lat2.jpg)

perintah `$ csh` adalah sebuah shell interaktif yang menawarkan lebih banyak sintaks dibandingkan dengan Bourne Shell. 
perintah `$ bash` digunakan untuk mengkonversi instruksi yang dimasukkan ke dalam bahasa biner yang dapat dimengerti oleh kernel Linux. 
perintah `$ ls` digunakan untuk menunjukkan semua file yang terletak dalam direktori aktif.
perintah `$ sh` adalah singkatan dari Bourne Shell, yang bertindak sebagai interpreter perintah atau shell standar di unix.
perintah `$ ps` digunakan untuk menampilkan daftar proses yang sedang berlangsung dalam sistem. Tampilan dari perintah ps mencakup empat kolom utama: PID, TTY, TIME, dan CMD.
Perintah `$ who`digunakan untuk menampilkan daftar pengguna yang saat ini login ke sistem. Ini menampilkan informasi seperti nama pengguna, terminal yang mereka gunakan, waktu login, dan sebagainya. Perintah ini sering digunakan untuk memeriksa siapa yang sedang menggunakan sistem atau untuk melihat apakah ada pengguna yang login secara tidak sah.

f. Sebutkan PID yang paling besar dan kemudian buat urut - urutan proses sampai ke PPID = 1

![App Screenshot](img/lat3.jpg)

Untuk menampilkan keseluruhan proses yang berjalan kita menggunakan perintah $ps -au yang berfungsi untuk melihat seluruh proses yang berjalan dan didapatkan PID terbesar adalah 2683 dan PPID atau parent PID adalah 1162.

2.  Cobalah format tampilan ps dengan opsi berikut dan perhatikan hasil tampilannya :
    - `-f` daftar penuh

![App Screenshot](img/lat4.jpg)

Analisa : 

 Hasil daftar penuh berupa :
          - UID yang menunjukkan user ID
          - PID  menujukkan proses ID
          - PPID yang merupkan parent dari PID
          - C menunjukkan penggunaan CPU
          - STATIME nenunjukkan start time atau waktu pertama kali program dijalankan
          - TTY terminal yang digunakan untuk menjalankan proses
          - TIME total waktu yang digunakan CPU untuk memproses
          - CMD menunjukkan nama dari proses termasuk argument jika ada.

  - `-j` format job

![App Screenshot](img/lat5.jpg)

Analisa : 
Perintah tersebut menghasilkan tampilan lima kolom, yakni PID, PGID, SID, TTY, dan TIME, dengan SID muncul dua kali. PGID berarti Process Group ID, yang merujuk pada nomor kelompok proses, sementara SID, atau Session ID, mengacu pada sesi yang memuat beberapa kelompok proses di dalamnya, dimana setiap kelompok terdiri dari berbagai proses dan setiap proses dapat memiliki beberapa thread. Thread adalah unit terkecil dalam penggunaan CPU.

  - `j` format job control

![App Screenshot](img/lat6.jpg)

Analisa : 
 Tampilan dari hasil perintah tersebut adalah format control yang dimana terdapat TPGID yang berfungsi untuk menunjukkan control terminal proses group id, STAT untuk menunjukkan status proses, dan UID untuk menunjukkan user ID berupa nilai integer.

  - `l` daftar memanjang

![App Screenshot](img/lat7.jpg)

Analisa : 
Tampilan format ini yang memperlihatkan daftar secara vertikal mencakup 'f' atau flags, yang merupakan hasil dari operasi bitwise OR dari nilai numerik untuk proses yang aktif. Kolom PRI menampilkan prioritas penjadwalan proses, sementara NI menunjuk pada nilai NICE proses tersebut. Ukuran virtual dari proses dalam kilobyte ditunjukkan dalam kolom VSZ. Sedangkan kolom WCHAN mengindikasikan waiting channel, yang merujuk pada alamat memori event yang sedang menunggu proses tersebut.

  - `s` format sinyal

![App Screenshot](img/lat8.jpg)

Format ini menampilkan kolom PENDING, yang menggambarkan sinyal proses yang tertunda dalam bentuk nilai heksadesimal. Kolom BLOCKED menunjukkan nilai heksadesimal dari sinyal proses yang diblokir. Sementara itu, sinyal yang diabaikan memiliki nilai heksadesimalnya tersaji dalam kolom IGNORED. Kolom CAUGHT menyajikan nilai heksadesimal dari sinyal yang berhasil ditangkap. Dari penjelasan ini, jelas bahwa format sinyal ini menggunakan sistem bilangan heksadesimal.

  - `v` format virtual memory

![App Screenshot](img/lat9.jpg)

  Analisa : 
  Perintah ini digunakan untuk menunjukkan informasi proses dalam bentuk virtual memori.

  - `X` format register i386

![App Screenshot](img/lat10.jpg)

Analisa : 
Perintah ini akan menunjukkan informasi proses dalam bentuk format register dalam memory seperti PID,STACKP,ESP,EIP,TIMEOUT,ALARM,STAT,TTY,TIME,dan COMMAND


3. Lakukan urutan pekerjaan berikut :

    - Gunakan perintah `find` ke seluruh direktory pada sistem, belokkan output sehingga daftar direktori dialihkan ke file `directories.txt` dan daftar pesan error dialihkan ke file `errors.txt`

![App Screenshot](img/lat11.jpg)


   Gunakan perintah `sleep 5`. Apa yang terjadi dengan perintah ini ?

![App Screenshot](img/lat12.jpg)

- Jalankan perintah pada background menggunakan `&`

![App Screenshot](img/lat13.jpg)

  - Jalankan `sleep 15` pada foreground, hentikan sementara dengan Ctrl-Z dan kemudian letakkan pada background dengan `bg`. Ketikkan `jobs`. Ketikkan `ps`. Kembalikan job ke foreground dengan perintah `fg`.

      ![App Screenshot](img/lat14.jpg)

    - Jalankan `sleep 15` pada background menggunakan `&` dan kemudian gunakan perintah `kill` untuk menghentikan proses diikuti job number.

      ![App Screenshot](img/lat15.jpg)

    - Jalankan `sleep 15` pada background menggunakan `&` dan kemudian gunakan `kill` untuk menghentikan sementara proses. Gunakan `bg` untuk melanjutkan menjalankan proses.

      ![App Screenshot](img/lat16.jpg)

    - Jalankan `sleep 60` pada background 5 kali dan terminasi semua pada dengan menggunakan perintah `killall`.

      ![App Screenshot](img/lat17.jpg)

    - Gunakan perintah `ps`, `w` dan `top` untuk menunjukkan semua proses yang sedang dieksekusi.

      ![App Screenshot](img/lat18.jpg)

      ![App Screenshot](img/lat19.jpg)

    - Gunakan perintah `ps –aeH` untuk menampilkan hierarki proses. Carilah init proses. Apakah Anda bisa identifikasi sistem daemon yang penting ? Dapatkan Anda identifikasi shell dan subproses ?

      ![App Screenshot](img/lat20.jpg)

      ![App Screenshot](img/lat21.jpg)

      ![App Screenshot](img/lat22.jpg)

    - Kombinasikan `ps –fae` dan grep, apa yang Anda lihat ?

      ![App Screenshot](img/lat23.jpg)

    - Jalankan proses `sleep 300` pada background. Log off komputer dan log in kembali. Lihat daftar semua proses yang berjalan. Apa yang terjadi pada proses sleep ?

      ![App Screenshot](img/lat24.jpg)

      ![App Screenshot](img/lat25.jpg)

    
### Kesimpulan
Praktikum ini dijalankan melalui command line, tempat seluruh prosesnya akan berlangsung. Dalam praktikum ini, dibahas pula metode untuk mengelola proses baik di latar depan (foreground) maupun latar belakang (background). Ada beragam pilihan perintah yang bisa digunakan bersama dengan fungsi ps untuk memantau proses. Lebih lanjut, kita juga bisa mengeksplorasi struktur hierarki proses menggunakan pstree untuk menampilkan proses dalam bentuk pohon. Berbagai perintah seperti ps, yes, jobs, dan kill digunakan selama praktikum ini untuk memahami dan mengelola proses yang ada.


        
























