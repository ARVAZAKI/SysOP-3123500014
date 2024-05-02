<div align="center">
  <h1 style="text-align: center;font-weight: bold">Sistem Operasi</h1>
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

### Soal 

1. Fork : Parent - Child Process
Buat tulisan tentang konsep fork dan implementasinya dengan menggunakan bahasa pemrograman C! (minimal 2 paragraf disertai dengan gambar)
Akses dan clonning repo : https://github.com/ferryastika/operatingsystem.git
Deskripsikan dan visualisasikan pohon proses hasil eksekusi dari kode program fork01.c, fork02.c, fork03.c, fork04.c, fork05.cdan fork06.c.
<br>
2. Tugas
Buatlah program perkalian 2 matriks [4 x 4] dalam bahasa C yang memanfaatkan fork().

### Jawaban nomor 1
1.
Konsep fork adalah salah satu konsep penting dalam sistem operasi Unix dan turunannya. Fork membuat proses baru dengan menduplikasi proses pemanggilan (The calling process). Proses baru ini disebut sebagai proses child (child process) dan proses pemanggilan disebut dengan proses parent (parent process). Meskipun proses CHILD identik dengan proses PARENT-nya, namun keduanya memiliki PID yang berbeda.
Proses child dan proses parent berjalan di ruang memori terpisah. Pada saat fork(), kedua ruang memori memiliki konten yang sama. Penulisan memori, pemetaan file (mmap(2) ), dan penghapusan pemetaan (munmap(2) ) yang dilakukan oleh salah satu proses tidak mempengaruhi proses lainnya. Setelah proses baru (CHILD) berhasil dibuat, eksekusi dilanjutkan secara normal di masing-masing proses pada baris setelah panggilan sistem fork(). Proses pemanggil (PARENT) dapat melakukan forking proses lebih dari satu kali, sehingga memungkinkan terdapat banyak proses CHILD yang dieksekusi. 
<br>
<br>
Selain itu, proses CHILD juga dapat melakukan forking proses seperti halnya PARENT, sehingga terbentuk struktur pohon proses yang kompleks.
Penting untuk diingat bahwa setelah fork, kedua proses (parent dan child) berjalan secara independen. Seiring berjalannya waktu, kedua proses dapat berinteraksi satu sama lain melalui mekanisme komunikasi seperti pipe, shared memory, atau socket.
proses child merupakan duplikat persis dari proses parent kecuali untuk beberapa poin berikut:
- child punya process ID uniknya sendiri, dan PID ini tidak cocok dengan ID grup proses mana pun yang ada (setpgid(2)) atau sesi.
- Child’s parent process ID sama dengan parent’s process ID
- Child tidak mewarisi parent memory key (mlock(2), mlockall(2))
- dsb

![App Screenshot](img/fork1.png)

![App Screenshot](img/fork2.png)

Contoh Implementasi menggunakan bahasa C : 
<br>
```
#include <stdio.h> 
#include <unistd.h> 

int main() { 
	int i; 

	for (i = 0; i < 3; i++) { 
		pid_t child_pid = fork(); 

		if (child_pid == 0) { 
			printf("Child process %d: PID=%d\n", i + 1, getpid()); 
			break; // Each child process should exit the loop 
		} else if (child_pid < 0) { 
			perror("Fork failed"); 
		} 
	} 

	if (getpid() != 1) { 
		// This code is executed only by the parent process 
		printf("Parent process: PID=%d\n", getpid()); 
	} 

	return 0; 
} 

```


![App Screenshot](img/fork3.jpeg)

- hasil eksekusi dari kode program fork01.c, fork02.c, fork03.c, fork04.c, fork05.cdan fork06.c.

1. fork01

```
using namespace std;

#include <iostream>
#include <sys/types.h>
#include <unistd.h>


/* getpid() adalah system call yg dideklarasikan pada unistd.h.
Menghasilkan suatu nilai dengan type pid_t.
pid_t adalah type khusus untuk process id yg ekuivalen dg int
*/
int main(void) {
	pid_t mypid;
	uid_t myuid;
	for (int i = 0; i < 3; i++) {
		mypid = getpid();
		cout << "I am process " << mypid << endl;
		cout << "My parent process ID is " << getppid() << endl;
		cout << "The owner of this process has uid " << getuid()
	<< endl;
/* sleep adalah system call atau fungsi library
yang menghentikan proses ini dalam detik
*/
	sleep(3);
	}
return 0;
}

```

![App Screenshot](img/fork01.jpeg)

deskripsi : 
 Program ini mencetak ID proses (PID), ID proses parent (PPID), dan ID pengguna (UID) dari proses tersebut. Setelah mencetak informasi tersebut, program akan berhenti selama tiga detik sebelum mencetak informasi lagi. Program ini berulang tiga kali.

Visualisasi :


```
int main() { 
    for(int i = 0; i < 3; i++) {

                    pid: 11093, ppid: 11079, uid: 1000
                            [Main Process]
                                    |
                                 sleep(3)
                                    |
                    pid: 11093, ppid: 11079, uid: 1000
                            [Main Process]
                                    |
                                 sleep(3)
                                    |
                    pid: 11093, ppid: 11079, uid: 1000
                            [Main Process]
                                    |
                                 sleep(3)

    }
  return 0;
}
```

2. fork02

```
#include <iostream>
#include <sys/types.h>
#include <unistd.h>
using namespace std;


/* getpid() dan fork() adalah system call yg dideklarasikan
pada unistd.h.
Menghasilkan suatu nilai dengan type pid_t.
pid_t adalah type khusus untuk process id yg ekuivalen dg int
*/
int main(void) {
	pid_t childpid;
	int x = 5;
	childpid = fork();

	while (1) {
		cout << "This is process ID" << getpid() << endl;
		cout << "In this process the value of x becomes " << x << endl;	
		sleep(2);
		x++;
	}
	return 0;
}

```

![App Screenshot](img/fork02.jpeg)


Deskripsi :
Program mencetak ID proses (PID) dan nilai variabel x dalam loop tak terbatas.
Program menggunakan systemCall fork() untuk membuat salinan proses saat ini,dan menciptakan child proses.
Kedua proses (parent dan child) akan mencetak informasi PID mereka sendiri dan nilai variabel x.
Program akan terus berjalan dalam loop tak terbatas, dan nilai variabel x akan terus diperbarui dengan penambahan satu setiap dua detik.

Visualisasi :

```
int main() { 
  fork();              > Child process created <
                                 +
                               /   \
    while(1) {                /     \
               pid: 11512, ppid: -    pid: 11513, ppid: 11512
            [Parent Process] x = 5    [Child Process] x = 5
                              \     /
                               \   /
                                 |
                              sleep(2)
                                 |
                                x++
    }
  return 0;
}
```


3. fork03

```
#include <iostream>
using namespace std;
#include <sys/types.h>
#include <unistd.h>


/* getpid() dan fork() adalah system call yg dideklarasikan
pada unistd.h.
Menghasilkan suatu nilai dengan type pid_t.
pid_t adalah type khusus untuk process id yg ekuivalen dg int
*/
int main(void) {
	pid_t childpid;
	childpid = fork();
	for (int i = 0; i < 5; i++) {
		cout << "This is process " << getpid() << endl;
		sleep(2);
	}
	return 0;
}

```

![App Screenshot](img/fork03.jpeg)

Deskripsi :

Panggilan sistem fork() digunakan untuk membuat proses baru yang merupakan replika dari proses pemanggilan. Nilai kembalian dari fork() berbeda untuk proses parent dan proses child:

Dalam proses parent, fork() mengembalikan ID proses child.
Dalam proses child, fork() mengembalikan 0.
Ada loop yang diulang 5 kali. Di dalam loop, program memanggil getpid() untuk mendapatkan ID proses dan mencetak "this is process" diikuti dengan ID proses menggunakan cout. Panggilan sistem sleep(2) menjeda proses selama 2 detik.

Ketika program dijalankan, ia menciptakan proses child menggunakan fork(). Proses parent dan child terus mengeksekusi kode setelah fork(). Karena kedua proses memiliki kode yang sama, keduanya mencetak pesan "this is process" diikuti dengan ID prosesnya.

ID proses parent adalah 11541 dan ID proses child adalah 11542. Outputnya adalah:

this is process 11541
this is process 11542

this is process 11542 // Proses child terus mengeksekusi perulangan
this is process 11541 // Proses parent terus mengeksekusi perulangan

Visualisasi :

```
int main() { 
  fork();              > Child process created <
                                 +
                               /   \
    loop 0 to 5 {             /     \
               pid: 11541, ppid: -    pid: 11542, ppid: 11541
               [Parent Process]     [Child Process]
                              \     /
                               \   /
                                 |
                              sleep(2)
                                 |
                                x++
    }
  return 0;
}
```

4. fork04

```
#include <iostream>
using namespace std;
#include <sys/types.h>
#include <unistd.h>
#include <sys/wait.h>
/* pid_t fork() dideklarasikan pada unistd.h.
pid_t adalah type khusus untuk process id yg ekuivalen dg int
*/

int main(void) {
	pid_t child_pid;
	int status;
	pid_t wait_result;
	child_pid = fork();
	if (child_pid == 0) {
		/* kode ini hanya dieksekusi proses child */
		cout << "I am a child and my pid = " << getpid() << endl;
		cout << "My parent is " << getppid() << endl;
		/* keluar if akan menghentikan hanya proses child */
	}
	else if (child_pid > 0) {
		/* kode ini hanya mengeksekusi proses parent */
		cout << "I am the parent and my pid = " << getpid() << endl;
		cout << "My child has pid = " << child_pid << endl;
	}
	else {
		cout << "The fork system call failed to create a new process" << endl;
		exit(1);
	}
		/* kode ini dieksekusi baik oleh proses parent dan child */
		cout << "I am a happy, healthy process and my pid = " << getpid() << endl;
		if (child_pid == 0) {
		/* kode ini hanya dieksekusi oleh proses child */
		cout << "I am a child and I am quitting work now!"<< endl;
	}
	else {
		/* kode ini hanya dieksekusi oleh proses parent */
		cout << "I am a parent and I am going to wait for my child" << endl;
	do {
		/* parent menunggu sinyal SIGCHLD mengirim tanda bahwa proses child diterminasi */
		wait_result = wait(&status);
	} while (wait_result != child_pid);
		cout << "I am a parent and I am quitting." << endl;
	}
	return 0;
}

```

![App Screenshot](img/fork04.jpeg)

Deskripsi : 
Program diatas adalah program implementasi dari fork() didalam bahasa C++ dimana ada 2 proses yang memiliki hubungan parent dan child. proses pertama memiliki PID: 11570 dan PPID yang tidak diketahui yang merupakan proses utama (main program atau parent). Setelah program menjalankan fungsi fork() maka akan tercipta proses baru yaitu child dengan PID: 11571 dan PPID: 11570 (PID dari proses utama (parent)). Setelah parent program memberikan output yang menyebutkan nomor PID nya dan nomor PID dari child, parent program akan melakukan tahap menunggu (wait) untuk menunggu child program berjalan. Child program berjalan dan memberikan output nomor PID nya dan nomor PPID nya, lalu akan langsung exit the process. Setelah child program exit the process maka parent program akan mengikuti untuk exit the process juga. Dan ini adalah end of program.

Visualisasi : 

```
int main() { 
  fork();              > Child process created <
                                 +
                               /   \
                              /     \
               pid: 11570, ppid: -    \
                [Parent Process]      \  
                        |              \
                        |               \
                       wait          pid: 11571, ppid: 11570
                           \             [Child Process]
                            \         /
                             \       /
                              \     /
                               \   /
                                 |
                                exit
    
  return 0;
}
```
5. fork05

```
#include <iostream>
using namespace std;
#include <sys/types.h>
#include <unistd.h>
#include <sys/wait.h>
/* pid_t fork() dideklarasikan pada unistd.h.
pid_t adalah type khusus untuk process id yg ekuivalen dg int
*/

int main(void) {
  pid_t child_pid;
  int status; 
  pid_t wait_result;
  child_pid = fork();
  if (child_pid == 0) {
    /* kode ini hanya dieksekusi proses child */
    cout << "I am a child and my pid = " << getpid() << endl;
    execl("/bin/ls", "ls", "-l", "/home", NULL);
    /* jika execl berhasil kode ini tidak pernah digunakan */
    cout << "Could not execl file /bin/ls" << endl;
    exit(1);
    /* exit menghentikan hanya proses child */
   }
  else if (child_pid > 0) {
    /* kode ini hanya mengeksekusi proses parent */
   cout << "I am the parent and my pid = " << getpid() << endl;
   cout << "My child has pid = " << child_pid << endl;
  }
  else {
   cout << "The fork system call failed to create a new process" << endl;
   exit(1);
  }
  /* kode ini hanya dieksekusi oleh proses parent karena
  child mengeksekusi dari “/bin/ls” atau keluar */
   cout << "I am a happy, healthy process and my pid = " << getpid() << endl;
   if (child_pid == 0) {
  /* kode ini tidak pernah dieksekusi */
   printf("This code will never be executed!\n");
  }
  else {
   /* kode ini hanya dieksekusi oleh proses parent */
    cout << "I am a parent and I am going to wait for my child" << endl;
    do {
      /* parent menunggu sinyal SIGCHLD mengirim tanda bila proses child diterminasi */
      wait_result = wait(&status);
    } while (wait_result != child_pid);
    cout << "I am a parent and I am quitting." << endl;
  }
  return 0;
}

```

![App Screenshot](img/fork05.jpeg)

Deskripsi : 
Program diatas adalah program implementasi dari fork() didalam bahasa C++ dimana ada 2 proses yang memiliki hubungan parent dan child. proses pertama memiliki PID: 11604 dan PPID yang tidak diketahui yang merupakan proses utama (main program atau parent). Setelah program menjalankan fungsi fork() maka akan tercipta proses baru yaitu child dengan PID: 11605 dan PPID: 11604 (PID dari proses utama (parent)). Setelah parent program memberikan output yang menyebutkan nomor PID nya dan nomor PID dari child, parent program akan melakukan tahap menunggu (wait) untuk menunggu child program berjalan. Child program akan berjalan dan memberikan output nomor PID nya dan nomor PPID nya dan menjalankan program execl("/bin/ls", "ls", "-l", "/home", NULL), total 20 disini adalah jika proses child berhasil menjalankan sistem panggilan execl(), maka hasil dari perintah ls -l /home akan dicetak, serta setiap proses mencetak pesan sebelum mengakhiri eksekusi. Jadi, total output yang dihasilkan adalah 20. Setelah output dari program child diberikan, program child akan langsung exit the process. Setelah child program exit the process maka parent program akan mengikuti untuk exit the process juga. Dan ini adalah end of program.

Visualisasi : 


```
int main() { 
  fork();              > Child process created <
                                 +
                               /   \
                              /     \
               pid: 11604, ppid: -    \
                [Parent Process]      \  
                        |              \
                        |               \
                        |          pid: 11605, ppid: 11604
                       wait           total 20
                          \           execl(/bin/ls) 
                           \         [Child Process]
                            \         /
                             \       /
                              \     /
                               \   /
                                 |
                                exit
    
  return 0;
}
```

6. Fork06

```
#include <iostream>
using namespace std;
#include <sys/types.h>
#include <unistd.h>
#include <sys/wait.h>
/* pid_t fork() dideklarasikan pada unistd.h.
pid_t adalah type khusus untuk process id yg ekuivalen dg int
*/

int main(void) {
	pid_t child_pid;
	int status;
	pid_t wait_result;
	child_pid = fork();


	if (child_pid == 0) {
		/* kode ini hanya dieksekusi proses child */
		cout << "I am a child and my pid = " << getpid() << endl;
		execl("fork03", "goose", NULL);
		/* jika execl berhasil kode ini tidak pernah digunakan */
		cout << "Could not execl file fork3" << endl;
		exit(1);
		/* exit menghentikan hanya proses child */
	}
	else if (child_pid > 0) {
		/* kode ini hanya mengeksekusi proses parent */
		cout << "I am the parent and my pid = " << getpid()<< endl;
		cout << "My child has pid = " << child_pid << endl;
	}
	else {
		cout << "The fork system call failed to create a new process" << endl;
		exit(1);
	}
	/* kode ini hanya dieksekusi oleh proses parent karena
	child mengeksekusi dari “fork3” atau keluar */
		cout << "I am a happy, healthy process and my pid = " << getpid() << endl;
		if (child_pid == 0) {
	/* kode ini tidak pernah dieksekusi */
		printf("This code will never be executed!\n");
	}
	else {
	/* kode ini hanya dieksekusi oleh proses parent */
		cout << "I am a parent and I am going to wait for my child" << endl;
		do {
		/* parent menunggu sinyal SIGCHLD mengirim tanda
		bila proses child diterminasi */
			wait_result = wait(&status);
		} while (wait_result != child_pid);
		cout << "I am a parent and I am quitting." << endl;
	}
	return 0;
}

```

![App Screenshot](img/fork06.jpeg)

Deskripsi : 
Program diatas adalah program implementasi dari fork() didalam bahasa C++ dimana ada 2 proses yang memiliki hubungan parent dan child. proses pertama memiliki PID: 3076 dan PPID yang tidak diketahui yang merupakan proses utama (main program atau parent). Setelah program menjalankan fungsi fork() maka akan tercipta proses baru yaitu child dengan PID: 3077 dan PPID: 3076 (PID dari proses utama (parent)). Setelah parent program memberikan output yang menyebutkan nomor PID nya dan nomor PID dari child, parent program akan melakukan tahap menunggu (wait) untuk menunggu child program berjalan. Child program akan berjalan dan memberikan output nomor PID nya dan nomor PPID nya dan menjalankan program execl(fork3), panggilan sistem execl() digunakan untuk menjalankan sebuah program di dalam proses yang sudah ada, pada program yang ini sistem execl() menjalankan program fork3 pada file fork3.cpp. Setelah output dari program child diberikan, program child akan langsung exit the process. Setelah child program exit the process maka parent program akan mengikuti untuk exit the process juga. Dan ini adalah end of program.

Visualisasi : 


```
int main() { 
  fork();              > Child process created <
                                 +
                               /   \
                              /     \
               pid: 6598, ppid: -    \
                [Parent Process]      \  
                        |              \
                        |               \
                        |          pid: 6599, ppid: 6598
                       wait           execl(fork3) 
                          \           [Child Process]
                           \           /
                            \         /
                             \       /
                              \     /
                               \   /
                                 |
                                exit
    
  return 0;
}
```

### Jawaban nomor 2

```
#include <stdio.h>
#include <unistd.h>
#include <sys/wait.h>

#define SIZE 4

void multiplyMatrices(int mat1[SIZE][SIZE], int mat2[SIZE][SIZE], int result[SIZE][SIZE]) {
    for (int i = 0; i < SIZE; i++) {
        for (int j = 0; j < SIZE; j++) {
            result[i][j] = 0;
            for (int k = 0; k < SIZE; k++) {
                result[i][j] += mat1[i][k] * mat2[k][j];
            }
        }
    }
}

void printMatrix(int mat[SIZE][SIZE]) {
    for (int i = 0; i < SIZE; i++) {
        for (int j = 0; j < SIZE; j++) {
            printf("%d ", mat[i][j]);
        }
        printf("\n");
    }
}

int main() {
    int mat1[SIZE][SIZE] = {{1, 2, 3, 4},
                            {5, 6, 7, 8},
                            {9, 10, 11, 12},
                            {13, 14, 15, 16}};
    int mat2[SIZE][SIZE] = {{2, 0, 0, 2},
                            {0, 3, 0, 0},
                            {0, 0, 4, 0},
                            {2, 0, 0, 5}};
    int result[SIZE][SIZE];

    pid_t pid;
    pid = fork();

    if (pid == 0) { // Child process
        multiplyMatrices(mat1, mat2, result);
        printf("Child Process Result:\n");
        printMatrix(result);
    } else if (pid > 0) { // Parent process
        wait(NULL);
        printf("Parent Process Result:\n");
        multiplyMatrices(mat1, mat2, result);
        printMatrix(result);
    } else { // Fork failed
        printf("Fork failed!\n");
        return 1;
    }

    return 0;
}
```

Output : 

![App Screenshot](img/matriks.jpg)

Analisis: Kode di atas adalah program perkalian dua matriks [4 x 4] dalam bahasa C yang menggunakan fork().

Proses Fork: Setelah matriks diinisialisasi, program melakukan fork untuk menciptakan proses child. Proses child akan mengalikan setiap elemen matriks dengan skalar, sementara proses parent menunggu proses child selesai.

Pemrosesan Serial: Meskipun perkalian skalar dilakukan secara paralel oleh proses child, program menunggu proses child selesai sebelum melanjutkan eksekusi. Ini dilakukan dengan menggunakan fungsi wait(), sehingga proses parent akan menunggu sampai proses child selesai sebelum mencetak pesan bahwa proses parent telah selesai.

Kesimpulannya, program ini memberikan contoh yang baik tentang penggunaan fork dalam bahasa pemrograman C untuk melakukan operasi secara paralel. Dengan memahami konsep fork dan multitasking, programmer dapat membuat aplikasi yang lebih efisien dan responsif.
