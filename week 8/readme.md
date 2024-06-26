<div align="center">
  <h1 style="text-align: center;font-weight: bold">Praktikum 8<br>Praktek Sistem Operasi</h1>
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

## Bash Programming 

### Apa itu bash?

Bash, kependekan dari Bourne Again Shell, adalah open source command line interpreter dan scripting language. Ini menafsirkan perintah yang dimasukkan pengguna, baik secara interaktif atau dari file skrip.

Ini berfungsi sebagai interface untuk memanggil perintah, memungkinkan system function calls.

Ada 2 tipe dari mode bash

- **Interactive Mode**
    Juga disebut sebagai command intepreter, memungkinkan eksekusi perintah di terminal. Ini mengeksekusi perintah secara berurutan jika ada beberapa perintah.

- **Non-interactive Mode**
    Ini merujuk pada scrpts, memungkinkan Anda menulis Bash syntax yang berisi rangkaian beberapa perintah untuk eksekusi skrip.

### Apa Perbedaan dari Bash dan Shell

Shell, an alias for Bourne Shell, adalah command-line interpreter untuk OS Unix dan Linux. Bash, alias Bourne Again Shell, adalah versi yang disempurnakan.

### Untuk apa skrip bash digunakan?

Skrip Bash memiliki banyak kasus penggunaan, termasuk:
- Menulis skrip untuk mengotomatiskan tugas pemrograman
- Menyinkronkan tugas untuk menyalin file
- Menjalankan tugas cron untuk penjadwalan

### Bagaimana cara menulis kode di bash?

Untuk menulis kode dalam skrip Bash, ikuti langkah-langkah berikut:
- Di terminal, buat file menggunakan `vi test.sh`.
- Tambahkan `#!/bin/bash` di bagian atas file.
- Tambahkan beberapa cuplikan kode shell.
- Simpan file shell dengan `.sh` ekstensi.
- Jalankan skrip shell menggunakan `./test.sh` perintah di terminal.

### Apakah bash termasuk bahasa pengkodean?

Bash menjalankan perintah dari terminal atau file. Ini adalah bahasa pemrograman yang beroperasi pada sistem operasi kernel Unix/Linux, berisi semua fitur untuk menulis kode lengkap.

Bash adalah tipe shell khusus yang menerima masukan dari perintah, menjalankan kode, dan memproses masukan, serta mengembalikan hasilnya.

### Jenis Shell

Ada berbagai jenis shell di OS Unix.

<table>
<thead>
<tr>
  <th style="background-color: blue; color: white">Tipe Cangkang</th>
  <th style="background-color: blue; color: white">Alias</th>
  <th style="background-color: blue; color: white">Garis Pertama</th>
<tr>
</thead>
<tbody>
  <tr>
  <td>SH</td>
  <td>Bourne Shell</td>
  <td>#!/bin/sh</td>
  </tr>
   <tr>
  <td>bash</td>
  <td>Bourne Again Shell</td>
  <td>#!/bin/bash</td>
  </tr>
   <tr>
  <td>cshell</td>
  <td>C shel</td>
  <td>#!/bin/csh</td>
  </tr>
</tbody>
</table>

| tcsh | TENEX C shell | #!/bin/tcsh | | | | ksh | Korn shell | #!/bin/ksh |

### Perbedaan dari Command Line dan Script di bash

Mari kita lihat perbedaan antara baris perintah dan skrip

Opsi baris perintah

- Baris perintah memiliki prompt yang menerima masukan dari pengguna
- Perintah tidak disimpan ke file.
- Ini hanya mendukung satu perintah pada satu waktu.

File skrip

- Mendukung banyak perintah dalam satu file
- Prompt masih dapat ditulis dalam file skrip
- Hanya satu baris dalam sebuah file yang dijalankan secara berurutan

## Bash - Variables

**Deklarasi Variable**: Untuk membuat variable, maka harus memberikan nilai padanya

``` 
variableName=VariableValue
```

Keterangan: 

- variableName: dapat berisi kombinasi huruf apa saja, angka, dan garis bawah
- variableValue: adalah nilai yang disimpan dalam variabel, dan dapat berupa angka, string atau boolean. Simbol `=` digunakan untuk memberikan nilai pada suatu variabel.

Misalnya

```
AGE=25
```

### Cara mengakses variabel di bash

![App Screenshot](img/variable1.jpg)

Pertama, deklarasikan variabel *AGE* dan beri nilai 25. Kemudian, gunakan `echo` untuk menampilkan outputnya. Simbol dolar `$` sebelum nama variabel sangat penting untuk mengakses nilainya.

![App Screenshot](img/variable2.jpg)

### Bash Shell readonly variables

![App Screenshot](img/variable3.jpg)

Setelah variabel diberi nilai, kita dapat mengubahnya menjadi nilai baru menggunakan operator penugasan =.

![App Screenshot](img/variable4.jpg)

### Bash Unset Variable

Keyword `unset` membantu menghapus nilai dari variabel yang ditentukan. Variabel tetap dapat diakses tetapi akan mencetak nilai kosong.

![App Screenshot](img/variable5.jpg)

Output:

![App Screenshot](img/variable6.jpg)

### Variables Scope

Setiap variabel yang dideklarasikan harus memiliki cakupan, yang menentukan di mana variabel tersebut dapat digunakan dalam program.

Misalnya, jika suatu variabel dideklarasikan di dalam suatu fungsi, maka variabel tersebut hanya tersedia di dalam fungsi tersebut dan tidak dapat diakses di luar fungsi tersebut.

Dalam Bash, cakupan variabel dapat didefinisikan dengan dua cara:

- Variabel global: Variabel yang dideklarasikan di luar fungsi atau blok kode khusus dan dapat diakses dari seluruh bagian skrip.
- Variabel lokal: Variabel yang dideklarasikan di dalam fungsi atau blok kode khusus dan hanya dapat diakses di dalam fungsi atau blok tersebut.

Terkadang kita ingin membaca konten file menggunakan bash programming. 
Ada berbagai macam cara yang dapat kita lakukan

### Bagaimana cara membaca file demi baris di bash Shell?
- menggunakan perulangan while

![App Screenshot](img/loopfile1.jpg)

Output

![App Screenshot](img/loopfile2.jpg)

Output diatas merupakan isi dari file `loop-file.txt` 

## Bash - Comments

Posting ini menjelaskan cara menulis komentar dalam skrip bash shell, disertai dengan contoh.

Komentar dalam skrip bash shell adalah pernyataan kode yang berisi teks yang bisa dibaca oleh pengguna, namun dilewati oleh shell saat eksekusi. Setiap bahasa pemrograman memiliki fitur komentar, yang memberikan deskripsi pada baris kode atau pernyataan.

Komentar satu baris dalam kode membantu pengembang dalam mengedit dan memahami kode dengan lebih baik.

Bahasa skrip bash memungkinkan penggunaan dua jenis komentar:

- **Komentar satu baris**
- **Komentar multi-baris**

Komentar bermanfaat bagi manusia, karena kode ditulis untuk scripting.

### Komentar satu baris di bash shell 

Komentar satu baris dalam skrip shell dilambangkan dengan simbol `#` di awal setiap baris.

Komentar ini mengandung string yang memberikan informasi tentang baris kode terkait dalam skrip shell.

Penting untuk menempatkan komentar satu baris pada baris terpisah untuk kejelasan.

Untuk menulis komentar satu baris, gunakan simbol `#` di awal komentar. Komentar satu baris selalu dimulai dengan simbol `#`.

**Syntax:**

```
# Single-line comments
```

Spasi kosong setelah `#` simbol tidak diperlukan. Berikut ini adalah contoh komentar satu baris dalam skrip shell.

![App Screenshot](img/comment1.jpg)

Output

![App Screenshot](img/comment2.jpg)

### Komentar multi-baris dalam skrip shell

![App Screenshot](img/comment3.jpg)

Output:

![App Screenshot](img/comment4.jpg)

### Kesimpulan

Singkatnya, kita telah mempelajari cara menambahkan komentar satu baris dan multi-baris dalam pemrograman skrip shell.

## Bash - Arrays

Array dalam shell adalah variabel yang memungkinkan Anda menyimpan lebih dari satu nilai atau data dalam satu variabel. Misalnya, jika Anda memiliki daftar bilangan bulat dari 1 hingga 100, Anda dapat menggunakan array untuk menyimpannya dalam skrip shell, yang akan menghindari kebutuhan untuk mendeklarasikan setiap nilai secara terpisah dengan pernyataan seperti `let number1=1`, dan seterusnya. Dengan menggunakan array, Anda dapat merujuk ke satu variabel dan menyimpan semua nilai tersebut di dalamnya.

### Bagaimana cara mendeklarasikan dan membuat array?

Ada dua jenis array yang dapat kita buat:

- Array yang diindeks: Elemen array disimpan dengan indeks mulai dari nol.
- Array terkait: Array disimpan dengan pasangan nilai kunci.

**Deklarasi sebuah array**

Untuk membuat array, kita perlu mendeklarasikan array.
```
declares -a array; # indexed array
declare -A array; # associative array
```
Sebuah array dideklarasikan dengan kata kunci declaredengan opsi `-a` atau `A`

**Menetapkan nilai tanpa mendeklarasikan Array**

```
arrayvariable[index]=value
```
Artinya, `arrayvariable[indeks]` array dideklarasikan dan diberi nilai.

Array yang diindeks dimulai dari nol dengan panjang array - 1. Indeks 0 mengembalikan elemen pertama, sedangkan indeks -1 mengembalikan elemen terakhir.

Array bisa berisi angka, string, atau campurannya. Mari kita buat contoh array.

### Akses nilai Array

Array berisi indeks untuk mendapatkan elemen. Elemen array dapat diakses menggunakan sintaks di bawah ini.

```
${array_name[index]}
```

### Deklarasi Array angka dan Loop

Array dapat berisi angka Contoh ini berisi array angka dan loop for untuk dicetak

![App Screenshot](img/array1.jpg)

Output:

![App Screenshot](img/array2.jpg)

### Deklarasi Array string dan Loop

Array dapat berisi angka Contoh ini berisi array angka dan loop for untuk dicetak

![App Screenshot](img/array3.jpg)

Output:

![App Screenshot](img/array4.jpg)

### Akses elemen pertama array

Dalam array, indeks elemen pertama adalah nol, sehingga `array[0]` mengembalikan elemen pertama.

![App Screenshot](img/array5.jpg)

Output:

![App Screenshot](img/array6.jpg)

### Dapatkan element terakhir dalam sebuah array

Dalam skrip bash, Anda dapat menggunakan indeks -1 untuk mendapatkan elemen array terakhir.

![App Screenshot](img/array7.jpg)

Output:

![App Screenshot](img/array8.jpg)

### Iterate atau Loop element array

For loop digunakan untuk mengulangi elemen.

Berikut adalah contoh loop array untuk mencetak semua elemen

![App Screenshot](img/array9.jpg)

Output:

![App Screenshot](img/array10.jpg)

### Cetak semua elemen array

Gunakan [@] atau [*] untuk mencetak semua elemen array.

![App Screenshot](img/array11.jpg)

Output:

![App Screenshot](img/array12.jpg)

### Hapus elemen dari array

Anda dapat menghapus elemen dari array menggunakan `unset` indeks tertentu.

![App Screenshot](img/array13.jpg)

Output:

![App Screenshot](img/array14.jpg)

### Menambahkan elemen ke array

Anda dapat menambahkan elemen di posisi indeks mana pun menggunakan sintaksis di bawah ini.

```
array[index]=value
```

![App Screenshot](img/array15.jpg)

Output:

![App Screenshot](img/array16.jpg)

### Array cheat sheet

<table>
<thead>
<tr>
  <th style="background-color: blue; color: white">Example</th>
  <th style="background-color: blue; color: white">Description</th>
<tr>
</thead>
<tbody>
    <tr>
        <td>Sdeclare -a array	</td>
        <td>Declare an Indexed array</td>
    </tr>
    <tr>
        <td>declare -A array	</td>
        <td>Declare an Associative array</td>
    </tr>
    <tr>
        <td>declare -a array=()	</td>
        <td>Declare an indexed array with empty array</td>
    </tr>
    <tr>
        <td>array=()</td>
        <td>create an empty array with declaring is valid</td>
    </tr>
    <tr>
        <td>array=(1 6 3)</td>
        <td>Initialize array with numbers</td>
    </tr>
    <tr>
        <td>array=(one two three)</td>
        <td>Initialize the array with string</td>
    </tr>
    <tr>
        <td>array=(one two 1)</td>
        <td>Initialize the array with mixed data</td>
    </tr>
    <tr>
        <td>${array[0]}</td>
        <td>Get first element</td>
    </tr>
    <tr>
        <td>${array[1]}</td>
        <td>Get second element</td>
    </tr>
    <tr>
        <td>${array[-1]}</td>
        <td>Get last element</td>
    </tr>
    <tr>
        <td>${array[@]}</td>
        <td>Get All element</td>
    </tr>
    <tr>
        <td>${array[*]}</td>
        <td>Get All element</td>
    </tr>
    <tr>
        <td>${!array[!]}</td>
        <td>Get All indexes</td>
    </tr>
    <tr>
        <td>${#array[!]}</td>
        <td>Array length</td>
    </tr>
    <tr>
        <td>array[0]=12</td>
        <td>Add element to array at first position.i.e index=0</td>
    </tr>
    <tr>
        <td>array[-1]=22</td>
        <td>Add element to array at last position.</td>
    </tr>
    <tr>
        <td>array+=(11)</td>
        <td>Append value to an array</td>
    </tr>
    <tr>
        <td>${array[@]:k:i}</td>
        <td>Get index=1 element starting from index=k</td>
    </tr>
</tbody>
</table>

## Bash - Expansion

Tutorial ini menjelaskan cara menulis skrip batch dalam shell script dan menjalankannya.

Perintah dimasukkan ke sistem operasi untuk membuat panggilan sistem dan melakukan tindakan. Perintah masukan pengguna di terminal digunakan untuk melakukan operasi seperti `ls`, `cd`, `mkdir`, dan sebagainya.

Salah satu cara lain adalah dengan menempatkan beberapa perintah dalam satu file, di mana bahasa bash akan membaca dan menjalankannya.

Berikut adalah cara menulis skrip shell di bash:

- Pilih editor atau editor teks.
- Buat file dengan ekstensi `.sh` atau `.bash`.
- Tulis perintah dalam file.
- Simpan file sebagai `hello.sh`.

![App Screenshot](img/expansion1.jpg)

Output:

![App Screenshot](img/expansion2.jpg)

## Bash - Conditional Expression

Ekspresi kondisional dievaluasi saat skrip dieksekusi, dan berdasarkan hasilnya, ia mengeksekusi blok perintah tertentu.

Berikut beberapa jenis ekspresi kondisional di Bash:

- Operator perbandingan string
- Operator perbandingan numerik
- Operator file
- Operator logis

Conditional expressions berisi opsi dan jalur file yang selalu mengembalikan nilai benar atau salah.

Berikut adalah beberapa opsi yang disediakan:

<table>
<thead>
<tr>
  <th style="background-color: blue; color: white">Example</th>
  <th style="background-color: blue; color: white">Description</th>
<tr>
</thead>
<tbody>
    <tr>
        <td>-e file</td>
        <td>Returns true if given file exists, file can be normal file or directory</td>
    </tr>
    <tr>
        <td>-f file</td>
        <td>Returns true if given file exists and a file(not directory)<td>
    </tr>
    <tr>
        <td>-d file</td>
        <td>Returns true if file is an directory</td>
    </tr>
    <tr>
        <td>-r file</td>
        <td>Returns true if file exists and has readable permission</td>
    </tr>
    <tr>
        <td>-w file</td>
        <td>Returns true if given file exists, file can be normal file or directory</td>
    </tr>
    <tr>
        <td>-x file</td>
        <td>Returns true if file exists and has writable permission</td>
    </tr>
    <tr>
        <td>-s file</td>
        <td>Returns true if file exists and size is not empty</td>
    </tr>
    <tr>
        <td>-G file</td>
        <td>Returns true if file exists and isowned by a Group ID that matches</td>
    </tr>
    <tr>
        <td>-O file</td>
        <td>Returns true if file exists and owned by a user ID that matches</td>
    </tr>
    <tr>
        <td>-N file</td>
        <td>Returns true if file exists and modified by last read date</td>
    </tr>
    <tr>
        <td>-L file</td>
        <td>Returns true if file exists and and is an symbolic Link</td>
    </tr>
    <tr>
        <td>file1 -ot file2</td>
        <td>Returns true if file1 is older than file2 or file2 exists, file1 does not exist</td>
    </tr>
    <tr>
        <td>file1 -ne file2</td>
        <td>Returns true if file1 is newer than file2,file1 exists, file2 does not exists</td>
    </tr>
    <tr>
        <td>file1 -ef file2</td>
        <td>Returns true if file1 and file2 pointed to same device and inode</td>
    </tr>
</tbody>
</table>

## Bash - Case Statements

Pernyataan case mirip dengan switch case dalam bahasa pemrograman lain.

Ini digunakan untuk membandingkan masukan yang diberikan dengan beberapa pola, dan menjalankan perintah di dalam pola yang cocok.

Syntax:

```
case expression in

pattern1)
  ## Commands
  ;;
pattern1)
  ## Commands
  ;;
*)
  ## Default case to execute if none of the pattern is matched
  ;;
```

- Expression adalah variabel atau ekspresi yang valid untuk dievaluasi.
- Ini berisi pola yang didefinisikan di dalam case yang dievaluasi dengan membandingkan expression, mencocokkan case yang ditemukan, dan mengeksekusi perintah di dalamnya.
- Case default (`*`) dijalankan jika tidak ada pola yang cocok.
- Setiap blok pola diakhiri dengan `;;`.
`case` adalah kata awal dan `esac` merupakan kata yang mengakhiri pernyataan case.

Contohnya sebagai berikut:

![App Screenshot](img/case1.jpg)

Output:

![App Screenshot](img/case2.jpg)

## Bash - Special Characters

Spesial Characters dalam bahasa Bash dievaluasi dengan makna tertentu dalam pengolahan sebuah perintah. Karakter-karakter ini memiliki instruksi khusus yang memberikan makna yang berbeda tergantung pada konteksnya.

Tanda kutip tunggal ('), misalnya, digunakan untuk mendefinisikan sebuah string tanpa interpretasi khusus. Ini berarti semua variabel dan ekspansi tidak diproses dan string yang sama akan dicetak secara harfiah.

Sebagai contoh, dalam perintah `echo` yang pertama, variabel "nama" akan diperluas dan diinterpretasikan sebagai string sebelum dicetak. Namun, dalam perintah `echo` yang kedua, ketika tanda kutip tunggal digunakan, variabel "nama" tidak akan diperluas dan akan dicetak sebagai string literal.

Jika tanda kutip tunggal mengandung tanda kutip tunggal bertingkat, Anda perlu menghindarinya dengan menggunakan karakter ``` backtick ```.

![App Screenshot](img/sc1.jpg)

Output : 

![App Screenshot](img/sc2.jpg)

Tanda kutip ganda (") digunakan untuk mendefinisikan string literal dengan makna khusus. Ketika string mengandung variabel dan ekspansi sintaks, tanda kutip ganda akan menginterpretasikan dan memperluasnya, dengan nilai yang dievaluasi saat runtime.

Jika Anda ingin menghindari ekspansi variabel dalam string, Anda dapat menggunakan karakter escape (\) sebelum tanda dolar ($).

Sebagai contoh, dalam perintah `echo` yang pertama, variabel "nama" akan diekspansi dan diinterpretasikan sebagai string sebelum dicetak. Namun, dalam perintah `echo` yang kedua, karakter escape (\) digunakan sebelum tanda dolar ($), sehingga variabel "nama" dicetak sebagai string literal.

![App Screenshot](img/sc3.jpg)

Output : 

![App Screenshot](img/sc4.jpg)


Karakter Backslash (\) digunakan untuk melarikan karakter-karakter dalam string. Biasanya, ini digunakan dalam string yang diapit oleh tanda kutip ganda (""). 

Dalam contoh pertama, pada perintah `echo`,  akan menampilkan ID proses. Namun, dalam contoh kedua, perintah `echo` berisi \$, yang menyebabkan $$ ditampilkan sebagai string literal dengan karakter escape.

![App Screenshot](img/sc5.jpg)

Output : 

![App Screenshot](img/sc6.jpg)

## Bash Shell Conditional Statements

Bash Script menyediakan ekspresi kondisional untuk menjalankan kode yang berbeda berdasarkan kondisi yang ditentukan. Pernyataan if digunakan untuk menjalankan blok kode jika suatu kondisi benar, dengan sintaks if then fi. Pernyataan else digunakan untuk menjalankan kode jika kondisi salah, mengikuti sintaks if then else fi. Pernyataan if..elif..else berguna saat Anda perlu menjalankan kode jika tidak ada dari kondisi sebelumnya yang benar. Sintaksnya adalah sebagai berikut: 

- If-Else Conditional Statements

![App Screenshot](img/if1.jpg)

Output : 

![App Screenshot](img/if2.jpg)

- If..Elif..Else Statements

![App Screenshot](img/if3.jpg)

Output : 

![App Screenshot](img/if4.jpg)

## Bash - Loops

Loop digunakan untuk menjalankan blok kode untuk sejumlah kali tertentu. Misalnya, saat Anda ingin menjalankan perintah secara berulang atau mencetak array. Loop for digunakan dalam Bash. Ada beberapa jenis loop yang tersedia dalam Bash:
- Loop for
- Loop for indeks
- Loop while
- Loop until

##### for loop

Loop for digunakan untuk menjalankan kode beberapa kali berdasarkan kondisi yang ditentukan.

![App Screenshot](img/loop1.jpg)

Output : 

![App Screenshot](img/loop2.jpg)

##### for index loop

Loop for indeks mirip dengan loop for dalam bahasa C. Ini menjalankan kode beberapa kali berdasarkan kondisi yang benar. Dimulai dengan nilai awal dan iterasi berisi nilai yang akan ditambahkan dengan 1.

![App Screenshot](img/loop3.jpg)

Output : 

![App Screenshot](img/loop4.jpg)

##### while loop in bash

Loop while dalam Bash memungkinkan untuk menjalankan kode secara berulang selama kondisi tertentu benar. Jika kondisinya menjadi salah, loop keluar.

![App Screenshot](img/loop5.jpg)

Output : 

![App Screenshot](img/loop6.jpg)

##### Until loop in bash

Kata kunci until dalam Bash digunakan untuk menjalankan kode secara berulang hingga suatu kondisi tertentu menjadi benar, pada saat itu loop keluar.

![App Screenshot](img/loop7.jpg)

Output : 

![App Screenshot](img/loop8.jpg)

## Bash - Append String

contoh pemrograman untuk menggabungkan variabel string menggunakan penambahan sederhana dan operator aritmatika singkat. Ekspresi aritmatika digunakan untuk melakukan operasi matematika. "Ekspresi" adalah istilah yang digunakan dalam matematika untuk menunjukkan suatu operasi. Ini berisi operand dan operator untuk melakukan operasi matematika. Misalnya, a < b adalah suatu ekspresi. Ini dapat berisi operator biner atau uner.

Operator perbandingan digunakan untuk memeriksa nilai satu dengan yang lain dengan membandingkan nilai. Operator-operator tersebut adalah (<, <=, >, >=, ==, !=).

##### Bash Athematic expressions

![App Screenshot](img/append1.jpg)

Output : 

![App Screenshot](img/append2.jpg)

##### Bash Athematic Expansion

seperti ekspresi. Ini menghitung nilai dari suatu ekspresi dan menggantikan hasilnya dengan nilai tersebut, selalu dengan awalan tanda dolar. Misalnya, untuk menghitung rata-rata dari dua angka dan mencetak hasilnya, kita menggunakan sintaks ekspansi yang mengevaluasi ekspresi dan menggantikan hasilnya dengan keluaran dari ekspresi tersebut.

![App Screenshot](img/append3.jpg)

Output : 

![App Screenshot](img/append4.jpg)

## Function

Tutorial Bash mengenai fungsi-fungsi dalam pemrograman dengan contoh-contoh penggabungan variabel string menggunakan operasi penambahan sederhana dan operator aritmatika singkat.

Fungsi-fungsi adalah potongan kode yang dapat digunakan kembali yang dikelompokkan di bawah satu nama.

Cara mendeklarasikan fungsi, memanggilnya, serta memahami cakupan variabel di dalamnya:

- Deklarasi fungsi
- Memanggil fungsi
- Fungsi dengan argumen
- Ruang lingkup variabel dalam fungsi

Definisi fungsi berisi beberapa baris kode yang akan dieksekusi. Fungsi memiliki nama yang diapit oleh kurung kurawal {}. Mereka dapat dideklarasikan dengan dua cara.

```

function function_name {
# Commands or valid bash code
# multiple lines
}
```

## Bash - Operators

Operator adalah simbol dalam pemrograman yang melakukan operasi pada operand.

```
operand1 operator operand2
```

Macam macam operator : 

<table border="1">
  <tr>
    <th>Operator</th>
    <th>Title</th>
    <th>Description</th>
    <th>Example</th>
  </tr>
  <tr>
    <td>+</td>
    <td>Addition</td>
    <td>penjumlahan dua atau lebih operand</td>
    <td>p + q = 50</td>
  </tr>
  <tr>
    <td>-</td>
    <td>Subtraction</td>
    <td>pengurangan dua atau lebih operand</td>
    <td>q - p = 10</td>
  </tr>
  <tr>
    <td>*</td>
    <td>Multiplication</td>
    <td>perkalian dua atau lebih operand</td>
    <td>p * q = 600</td>
  </tr>
  <tr>
    <td>/</td>
    <td>Divide</td>
    <td>menghasilkan hasil bagi setelah pembagian nilai</td>
    <td>q / p = 1.5</td>
  </tr>
  <tr>
    <td>%</td>
    <td>Modulus</td>
    <td>Mengembalikan sisa setelah pembagian nilai</td>
    <td>q % p = 10</td>
  </tr>
  <tr>
    <td>-expr</td>
    <td>Unary Minus</td>
    <td>balik dari suatu ekspresi</td>
    <td>-(10-7) adalah -3</td>
  </tr>
  <tr>
    <td>~/</td>
    <td>Division Int</td>
    <td>mengembalikan nilai int dari pembagian</td>
    <td>(10~/7) adalah 1</td>
  </tr>
  <tr>
    <td>++</td>
    <td>Increment</td>
    <td>Menambahkan nilai sebesar 1</td>
    <td>++p = 21</td>
  </tr>
  <tr>
    <td>--</td>
    <td>Decrement</td>
    <td>Mengurangkan nilai sebesar 1</td>
    <td>--q = 29</td>
  </tr>
</table>

##### Assignment Operators

Operator penugasan digunakan untuk menetapkan nilai ke variabel. Berikut adalah beberapa contoh operator penugasan yang umum digunakan dalam pemrograman:

=: Menetapkan nilai dari nilai kanan ke nilai kiri.
+=: Menambahkan nilai nilai kanan ke nilai kiri.
-=: Mengurangkan nilai nilai kanan dari nilai kiri.
*=: Mengalikan nilai nilai kiri dengan nilai kanan.
/=: Membagi nilai nilai kiri dengan nilai kanan.
%=: Menetapkan sisa hasil bagi nilai kiri dengan nilai kanan.

##### Bitwise Operators

Operator bitwise digunakan untuk melakukan operasi pada level bit pada operand. Berikut adalah beberapa operator bitwise yang umum digunakan:

<table border="1">
  <tr>
    <th>Operasi</th>
    <th>Simbol</th>
    <th>Deskripsi</th>
    <th>Hasil</th>
  </tr>
  <tr>
    <td>AND</td>
    <td>&amp;</td>
    <td>Operasi AND bitwise dari dua operand</td>
    <td>$op1 &amp; $op2 adalah 0</td>
  </tr>
  <tr>
    <td>AND Equal</td>
    <td>&amp;=</td>
    <td>Operasi AND Equal bitwise dari dua operand</td>
    <td>$op1 &amp;= $op2 adalah 0</td>
  </tr>
  <tr>
    <td>OR</td>
    <td>|</td>
    <td>Operasi OR bitwise dari dua operand</td>
    <td>$op1 | $op2 adalah 7</td>
  </tr>
  <tr>
    <td>XOR</td>
    <td>^</td>
    <td>Operasi XOR bitwise dari dua operand</td>
    <td>$op1 ^ $op2 adalah 7</td>
  </tr>
  <tr>
    <td>Left Shift</td>
    <td>&lt;&lt;</td>
    <td>Operasi Left Shift bitwise dari dua operand</td>
    <td>$op1 &lt;&lt; $op2 adalah 0</td>
  </tr>
  <tr>
    <td>Left Shift Eql</td>
    <td>&lt;&lt;=</td>
    <td>Operasi Left Shift Equal bitwise dari dua operand</td>
    <td>$op1 &lt;&lt;= $op2 adalah 7</td>
  </tr>
  <tr>
    <td>XOR</td>
    <td>^</td>
    <td>Operasi XOR bitwise dari dua operand</td>
    <td>$op1 ^ $op2 adalah 7</td>
  </tr>
  <tr>
    <td>XOR Equal</td>
    <td>^=</td>
    <td>Operasi XOR Equal bitwise dari dua operand</td>
    <td>$op1 ^= $op2 adalah 7</td>
  </tr>
</table>

##### Logical operators

Operator-operator ini digunakan untuk melakukan operasi logika pada variabel, ekspresi, atau data.

##### Numerical Comparision Operator

``` -eq ``` digunakan untuk logika equal/mencari persamaan nilai

![App Screenshot](img/operator1.jpg)

Output : 

![App Screenshot](img/operator2.jpg)

```-ne``` digunakan untuk logika equal, mencari ketidaksamaan nilai

![App Screenshot](img/operator3.jpg)

Output : 

![App Screenshot](img/operator4.jpg)

## Bash - Numbers Comparison

Berikut adalah operator perbandingan:

- `-eq`: Sama dengan
  - Memeriksa apakah dua variabel sama
- `-ne`: Tidak sama dengan
  - Memeriksa apakah dua variabel tidak sama
- `-lt`: Kurang dari
  - Memeriksa apakah variabel pertama kurang dari variabel kedua
- `-le`: Kurang dari atau sama dengan
  - Memeriksa apakah variabel pertama kurang dari atau sama dengan variabel kedua
- `-gt`: Lebih dari
  - Memeriksa apakah variabel pertama lebih besar dari variabel kedua
- `-ge`: Lebih besar dari atau sama dengan
  - Memeriksa apakah variabel pertama lebih besar dari atau sama dengan variabel kedua

![App Screenshot](img/comp1.jpg)

Output : 

![App Screenshot](img/comp2.jpg)

## Bash - Check Directory


Untuk memeriksa apakah sebuah direktori ada atau tidak dalam skrip Bash, Anda dapat menggunakan perintah test dengan opsi -d. Berikut adalah contoh cara melakukannya dalam skrip Bash:

```
#!/bin/bash

directory="/path/to/directory"

if [ -d "$directory" ]; then
    echo "Directory $directory exists."
else
    echo "Directory $directory does not exist."
fi
```

##### How to mkdir only if a directory does not already exist?

![App Screenshot](img/check1.jpg)

Output : 

![App Screenshot](img/check2.jpg)

Sebagai alternatif, ekspresi kondisional ternary digunakan sebagai pengganti ekspresi kondisional if.

![App Screenshot](img/check3.jpg)

Output : 

![App Screenshot](img/check4.jpg)

## Bash - File Name

Untuk mendapatkan nama file beserta ekstensinya, perintah basename dapat digunakan untuk menghapus direktori dan mengembalikan hanya nama file untuk jalur yang diberikan, baik itu variabel atau string.

Contoh, jika jalurnya adalah /home/john/run.sh, nama file yang dikembalikan adalah run.sh. Proses ini melibatkan pengambilan jalur lengkap dan mengekstrak hanya nama file dengan menghapus jalur. Nama file yang dihasilkan kemudian disimpan dalam sebuah variabel dan dicetak ke konsol.

basename digunakan untuk menghapus direktori dan mengembalikan nama file untuk jalur yang diberikan. Jalur tersebut bisa berupa variabel atau string. Sebagai contoh, jika jalurnya adalah /home/john/run.sh, nama file yang dikembalikan adalah run.sh. Dalam hal ini, jalur lengkap diberikan dan mengembalikan nama file dengan menghapus jalur.

```
file_path="/home/john/run.sh"
filename=$(basename "$file_path")
echo $filename
```

##### Extract extension for a file path

Untuk mengisolasi ekstensi file dari jalur file yang diberikan, ${filename##*.} dapat digunakan. Ekspresi ini mengembalikan hanya ekstensi file.

Sebagai contoh, pertimbangkan jalur /home/john/run.sh, hasil ekstensinya adalah sh.

Awalnya, perintah basename digunakan untuk menghapus jalur direktori dan mengembalikan nama file untuk jalur yang ditentukan, dan nama file ini kemudian digunakan bersama dengan sintaks ekspresi untuk mengembalikan hanya ekstensinya.

![App Screenshot](img/fname1.jpg)

Output : 

![App Screenshot](img/fname2.jpg)

## Bash - Split String


Kadang-kadang, saat bekerja dengan skrip bash, ada kebutuhan untuk memisahkan string berdasarkan delimiter dan mengekstrak beberapa string untuk pengolahan lebih lanjut atau penyimpanan dalam variabel.

##### Split a string using the awk command in a bash shell script

Perintah awk, sebuah utilitas Linux yang kompatibel dengan semua distribusi bash dan shell, digunakan untuk memisahkan sebuah string berdasarkan delimiter yang ditentukan.

Inputnya diberikan menggunakan simbol pipa (|), dan contoh di bawah ini menunjukkan pembagian sebuah string yang berisi titik dua 

![App Screenshot](img/split1.jpg)

Output : 

![App Screenshot](img/split2.jpg)

##### split using IFS variable

Di sini, string input terdiri dari elemen-elemen yang dipisahkan oleh tanda hubung. Variabel shell IFS (Internal Field Separator) diatur menjadi tanda hubung, dan string tersebut diiterasi menggunakan loop for.

![App Screenshot](img/split3.jpg)

Output : 

![App Screenshot](img/split4.jpg)

##### Use Parameter expansion and loop

Ekspansi parameter digunakan untuk mengubah nilai variabel berdasarkan opsi yang ditentukan. Dalam kasus ini, sebuah variabel string dikonversi menjadi sebuah array. Array tersebut kemudian diiterasi menggunakan sintaks loop for, mencetak setiap elemen ke konsol.

![App Screenshot](img/split5.jpg)

Output : 

![App Screenshot](img/split6.jpg)

## Bash - String Length

Panjang sebuah string ditentukan oleh jumlah karakter yang terkandung di dalamnya, dan umumnya mudah untuk mengetahui panjang ini untuk teks normal.

Posting ini akan menjelajahi berbagai metode untuk menghitung jumlah karakter dalam sebuah string dengan encoding UTF.

![App Screenshot](img/length1.jpg)

Output : 

![App Screenshot](img/length2.jpg)

Metode kedua melibatkan penggunaan perintah wc -m, baik langsung dengan sebuah string atau melalui sebuah variabel.


![App Screenshot](img/length3.jpg)

Output : 

![App Screenshot](img/length4.jpg)

echo -n "string" digunakan untuk mencetak string tanpa baris baru (opsi -n). Operator pipa | mengarahkan output dari perintah di sebelah kiri ke perintah di sebelah kanan, dan wc -m menghitung jumlah karakter dalam sebuah string.

Menggunakan Perintah expr
Metode lain melibatkan penggunaan perintah expr untuk menemukan panjang sebuah string.

![App Screenshot](img/length5.jpg)

Output : 

![App Screenshot](img/length6.jpg)

Di sini, ${} digunakan untuk substitusi ekspresi, mengganti nilai ekspresi ke dalam string. Perintah expr mengeksekusi ekspresi, dan length adalah argumen yang diberikan untuk menemukan panjang string.

## Bash - bashrc

File .bashrc adalah skrip bash yang dieksekusi saat:

1. Eksekusi skrip bash.
2. Shell bash dibuka secara interaktif.

File ini tersembunyi secara default karena dimulai dengan titik (.). Terletak di direktori home pengguna.

Anda dapat menggunakan editor Vi atau Nano untuk melihat file .bashrc.

Berikut adalah perintahnya:

```
nano ~/.bashrc
```

Anda juga dapat menggunakan:

```
vi ~/.bashrc
```

Kedua perintah tersebut akan membuka file .bashrc dalam editor Nano atau Vi.

Untuk memuat ulang pengaturan .bashrc tanpa masuk dan keluar lagi, Anda dapat menjalankan perintah berikut di prompt perintah:

```bash
source ~/.bashrc
```

Perintah ini akan memuat ulang pengaturan .bashrc saat ini tanpa perlu masuk dan keluar dari sesi bash.

## Bash - Ternary Operator

Cara lainnya adalah dengan menggunakan perintah `let` untuk menetapkan variabel berdasarkan hasil ekspresi kondisional.

![App Screenshot](img/ternary1.jpg)

Output : 

![App Screenshot](img/ternary2.jpg)

## Bash - Lowercase

Misalnya, jika string inputnya adalah "Hello World Welcome", maka outputnya akan menjadi "hello world welcome".

Ada beberapa cara untuk mencapai ini, tergantung pada jenis dan versi Bash.

Menggunakan perintah tr
Perintah tr, singkatan dari translator, adalah perintah Unix yang digunakan untuk mengonversi karakter dari satu format ke format lainnya.

![App Screenshot](img/lower1.jpg)

Output : 

![App Screenshot](img/lower2.jpg)

Alternatifnya : 

![App Screenshot](img/lower3.jpg)

Output : 

![App Screenshot](img/lower4.jpg)

## Bash - Uppercase


Sebuah string huruf besar merujuk pada sebuah string yang mengandung semua huruf dalam huruf besar.

Misalnya, jika string inputnya adalah "Hello World Welcome", maka outputnya akan menjadi "HELLO WORLD WELCOME."

![App Screenshot](img/upper1.jpg)

Output : 

![App Screenshot](img/upper2.jpg)

Untuk mengkonversi sebuah string menjadi huruf besar menggunakan perintah awk, fungsi toupper digabungkan dengan awk. Hasilnya kemudian diteruskan ke perintah echo menggunakan operator pipa:

![App Screenshot](img/upper3.jpg)

Output : 

![App Screenshot](img/upper4.jpg)

## Bash - Substring

Skrip Bash ini dirancang untuk menentukan apakah sebuah string mengandung sebuah substring tertentu.

Ada beberapa cara untuk melakukan pemeriksaan ini.

##### Using the Comparison Operator to Check for Substring exists or not

Gunakan pernyataan if untuk membandingkan string dengan substring yang diinginkan menggunakan operator kesetaraan (==) dan wildcard (*).
Terakhir, cetak string jika substring ditemukan.

![App Screenshot](img/subs1.jpg)

Output : 

![App Screenshot](img/subs2.jpg)

##### Use Regular Expressions to Find a Substring

Operator =~ memudahkan pencarian substring dalam sebuah string yang diberikan, digunakan dalam sebuah blok if.

```
mainstring='Welcome to w3schools'
if [[ $mainstring =~ "w3schools" ]]; then
  echo "w3schools exists in the main string"
fi
```

##### Use the grep command

Perintah grep digunakan untuk mencari string yang ditentukan, dipipakan ke string utama untuk dibandingkan.

![App Screenshot](img/subs3.jpg)

Output : 
![App Screenshot](img/subs4.jpg)

##### Bash - variable set

Dalam pemrograman skrip shell bash, Anda dapat melakukan pengecekan variabel untuk:

1. Memeriksa apakah variabel sudah diatur atau belum.
2. Memeriksa apakah variabel kosong atau tidak kosong.
3. Memeriksa apakah variabel adalah string kosong atau tidak.

Berikut adalah contoh sintaks untuk setiap kasus:

1. Memeriksa apakah variabel sudah diatur atau belum:
```bash
if [ -v variable ]; then
    echo "Variable is set."
else
    echo "Variable is not set."
fi
```

2. Memeriksa apakah variabel kosong atau tidak kosong:
```bash
if [ -z "$variable" ]; then
    echo "Variable is empty."
else
    echo "Variable is not empty."
fi
```

3. Memeriksa apakah variabel adalah string kosong atau tidak:
```bash
if [ -z "${variable+x}" ]; then
    echo "Variable is an empty string."
else
    echo "Variable is not an empty string."
fi
```

Dalam contoh di atas, ganti `variable` dengan nama variabel yang ingin Anda periksa.

contoh : 


![App Screenshot](img/setvar1.jpg)

Output : 
![App Screenshot](img/setvar2.jpg)


![App Screenshot](img/setvar3.jpg)

Output : 
![App Screenshot](img/setvar4.jpg)

![App Screenshot](img/setvar5.jpg)

Output : 
![App Screenshot](img/setvar6.jpg)

## Bash - Iterate Nos

Kadang-kadang, kita ingin membuat nama file dengan nama yang berisi angka yang dihasilkan dari urutan atau rentang angka.

##### Generate a range of numbers in the bash script

Perintah seq digunakan untuk menghasilkan urutan angka.

![App Screenshot](img/nos1.jpg)

Output : 
![App Screenshot](img/nos2.jpg)

menggunakan perulangan for

![App Screenshot](img/nos3.jpg)

Output : 
![App Screenshot](img/nos4.jpg)

menggunakan perulangan while


![App Screenshot](img/nos5.jpg)

Output : 
![App Screenshot](img/nos6.jpg)


