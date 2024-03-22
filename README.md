# Module 6 - Concurrency #

**Memahami Method handle_connection** <br>
Method `handle_connection` adalah method yang berfungis untuk mengatur perilaku server ketika mendapatkan connection request dari browser. 
Method menerima TcpStream, yang merupakan representasi connection antara local host dengan remote host, yang selanjutnya di-*wrap* dengan `BufReader`. Setelah itu, data dari `BufReader` akan dibaca tiap line dan hasilnya disimpan di dalam `Vec<_>`.