# Module 6 - Concurrency #

**Commit 1 Reflection Notes**
<br>
Method `handle_connection` adalah method yang berfungis untuk mengatur perilaku server ketika mendapatkan connection request dari browser. Method menerima TcpStream, yang merupakan representasi connection antara local host dengan remote host, yang selanjutnya di-*wrap* dengan `BufReader`. Setelah itu, data dari `BufReader` akan dibaca tiap line dan hasilnya disimpan di dalam `Vec<_>`.
<br>
<br>
**Commit 2 Reflection Notes**
![Commit 2 screen capture](/assets/images/commit2.png)
<br>
Method `handle_connection` yang sudah diperbarui, variabel `status_line` berisi status HTTP success. Variabel `contents` akan membaca konten dari file hello.html yang di-*convert* menjadi string. Terakhir, method akan menghasilkan HTTP response.
<br>
<br>
**Commit 3 Reflection Notes**
![Commit 3 screen capture](/assets/images/commit3.png)
<br>
Untuk menangani dua response yang berbeda, dapat dilakukan pemeriksaan apakah `request_line` sama dengan request line dari GET request dari path yang ingin dituju. Jika sesuai, maka akan muncul konten dari file hello.html. Jika tidak sesuai, maka akan muncul konten dari file 404.html yang menandakan request yang diminta tidak ada. Refactoring perlu dilakukan karena blok if-else sama-sama melakukan pembacaan file HTML dan menulis kontennya ke stream sehingga dilakukan perubahan dengan melakukan conditionals hanya pada `request_line` dan dilanjutkan dengan melakukan prosedur yang sama tanpa repetisi pada penulisan kode.
<br>
<br>
**Commit 4 Reflection Notes**
<br>
Ketika mengakses 127.0.0.1 pada browser, aplikasi memberikan respon tanpa adanya delay yang lama. Ketika mengakses 127.0.0.1/sleep, aplikasi memberikan respon dengan delay 10 detik karena terdapat thread sleep yang menghentikan thread sementara.
<br>