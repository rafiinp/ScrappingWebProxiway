Muhammad Rafi Naufal Pratama
V3922034
TIE

Script ini berguna untuk mengambil judul ulasan dari halaman web 'https://proxyway.com/reviews' menggunakan teknik web scraping. Script ini menggunakan library requests untuk melakukan permintaan HTTP ke halaman web dan library BeautifulSoup (dalam hal ini diimport sebagai bs) untuk melakukan parsing HTML.

Berikut adalah penjelasan langkah-langkah utama dalam script ini:

1. Import library:
   - `csv`: Digunakan untuk menulis data ke dalam file CSV.
   - `requests`: Digunakan untuk membuat permintaan HTTP ke halaman web.
   - `BeautifulSoup` (diimport sebagai `bs`): Digunakan untuk melakukan parsing HTML.

2. Mendefinisikan URL:
   - URL yang dituju adalah 'https://proxyway.com/reviews'.

3. Membuat variabel `data` sebagai list kosong. Variabel ini akan digunakan untuk menyimpan data yang akan ditulis ke dalam file CSV.

4. Loop melalui halaman 1 hingga 3:
   - Setiap halaman diakses dengan mengirimkan permintaan HTTP menggunakan metode `get` dari library `requests`.
   - Respon HTML dari halaman web kemudian di-parse menggunakan BeautifulSoup.
   - Menggunakan BeautifulSoup, mencari semua elemen 'h3' dengan kelas 'archive-list__title' yang merupakan judul ulasan.
   - Loop melalui judul-judul tersebut dan mencetak nomor halaman, nomor judul, dan judul ke layar.
   - Setiap judul ditambahkan ke dalam variabel `data` sebagai sebuah dictionary dengan kunci 'Page Number', 'Title Number', dan 'Title Name'.

5. Menyimpan data ke dalam file CSV:
   - Mendefinisikan nama file CSV sebagai 'proxywayreviews.csv'.
   - Mendefinisikan fieldnames (nama kolom) dalam file CSV.
   - Membuka file CSV menggunakan `open` dengan mode 'w' (menulis) dan 'newline=' agar tidak ada baris kosong di antara setiap baris data.
   - Membuat objek `writer` menggunakan `csv.DictWriter` untuk menulis data ke dalam file CSV.
   - Menulis header (nama kolom) ke dalam file CSV menggunakan `writer.writeheader()`.
   - Menulis setiap baris data dalam `data` ke dalam file CSV menggunakan `writer.writerows(data)`.

6. Mencetak pesan bahwa data telah disimpan ke dalam file CSV.

Script ini akan menghasilkan file CSV yang berisi kolom 'Page Number', 'Title Number', dan 'Title Name' yang berisi judul-judul ulasan yang diambil dari halaman web 'https://proxyway.com/reviews'.
