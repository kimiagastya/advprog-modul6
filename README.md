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