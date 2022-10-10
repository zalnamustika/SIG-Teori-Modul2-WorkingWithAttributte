# Working With Attribute (Bekerja Dengan Atribut)

Tutorial kali ini memberikan informasi tenatang tempet -tempat berpenduduk di masing - masing daerah yang memiliki ppulasi lebih dari 1 juta dan menyimpan subset yang dihasilkan sebagi file GeoJSON.

## Hal - Hal yang Dibutuhkan

- Komputer / Laptop
- APK QGIS3
- Mengunduh salinan data [ne_10m_populated_places_simple.zip] (https://www.qgistutorials.com/downloads/ne_10m_populated_places_simple.zip)

## Prosedur

1. Cari ne_10m_populated_places_simple.zipfile di QGIS Browser dan perluas. Pilih ne_10m_populated_places_simple.shpfile dan seret ke kanvas.

2. Lapisan baru ne_10m_populated_places_simplesekarang akan dimuat di QGIS dan Anda akan melihat banyak titik yang mewakili tempat-tempat berpenduduk di dunia. Tampilan default di kanvas QGIS menunjukkan geometri lapisan GIS. Setiap titik juga memiliki atribut terkait. Mari kita lihat mereka. Temukan Bilah Alat Atribut . Toolbar ini berisi banyak alat yang berguna untuk memeriksa, melihat, memilih, dan memodifikasi atribut dari sebuah lapisan.

--------------

Catatan :

Jika Anda tidak melihat toolbar, Anda dapat mengaktifkannya dari View Toolbars Attributes Toolbar .

--------------

3. Klik tombol Identifikasi pada Bilah Alat Atribut . Setelah alat dipilih, klik titik mana pun di kanvas. Atribut terkait dari titik itu akan ditampilkan di panel Identifikasi Hasil baru. Setelah Anda selesai menjelajahi atribut dari titik yang berbeda, Anda dapat mengklik tombol Tutup.

4. Daripada melihat atribut satu fitur pada satu waktu, kita dapat melihat semuanya bersama-sama sebagai sebuah tabel. Klik tombol Buka Tabel Atribut pada Bilah Alat Atribut . Anda juga dapat mengklik kanan ne_10m_populated_places_simplelayer dan memilih Open Attribute Table .

5. Anda dapat menggulir secara horizontal dan menemukan kolom pop_max . Bidang ini berisi populasi tempat terkait. Anda dapat mengklik dua kali pada tajuk bidang untuk mengurutkan kolom dalam urutan menurun.

6. Sekarang kita siap untuk melakukan query kita pada atribut-atribut ini. QGIS menggunakan ekspresi seperti SQL untuk melakukan query. Klik Pilih fitur menggunakan tombol ekspresi .

7. Di jendela Select By Expression , perluas bagian Fields and Values ​​dan klik dua kali pop_maxlabelnya. Anda akan melihat bahwa itu ditambahkan ke bagian ekspresi di bagian bawah. Jika Anda tidak yakin tentang nilai bidang, Anda dapat mengklik tombol Semua Unik untuk melihat nilai atribut apa yang ada dalam kumpulan data. Untuk latihan ini, kami mencari semua fitur yang memiliki populasi lebih dari 1 juta. Jadi lengkapi ekspresi seperti di bawah ini dan klik Select Features lalu Close.

--------------------------

Catatan :

Dalam mesin Ekspresi QGIS, teks dengan tanda kutip ganda mengacu pada bidang dan teks dengan tanda kutip tunggal mengacu pada nilai string.

--------------------------

8. Anda akan melihat bahwa beberapa baris dalam tabel atribut sekarang dipilih. Jendela label juga berubah dan menunjukkan jumlah fitur yang dipilih.

9. Tutup jendela tabel atribut dan kembali ke jendela utama QGIS. Anda akan melihat bahwa subset poin sekarang dirender dengan warna kuning. Ini adalah hasil dari kueri kami dan titik yang dipilih adalah titik yang memiliki pop_maxnilai atribut lebih besar dari 1000000.

10. Mari kita perbarui kueri kita dengan menyertakan syarat bahwa tempat itu juga harus menjadi ibu kota selain memiliki populasi lebih dari 1 juta. Untuk membuka editor ekspresi dengan cepat, Anda dapat menggunakan tombol Select Features by Expression di Attributes Toolbar.

11. Bidang yang berisi data tentang huruf kapital adalah adm0cap . Nilai tersebut 1menunjukkan bahwa tempat tersebut adalah ibukota. Kita dapat menambahkan kriteria ini ke ekspresi kita sebelumnya menggunakan operator and . Masukkan ekspresi seperti di bawah ini dan klik Select Features lalu Close.

--------------------------

"pop_max" > 1000000 and "adm0cap" = 1

------------------------------

12. Kembali ke jendela utama QGIS. Sekarang Anda akan melihat subset yang lebih kecil dari poin yang dipilih. Ini adalah hasil dari kueri kedua dan menunjukkan semua tempat dari kumpulan data yang merupakan ibu kota negara serta memiliki populasi lebih dari 1 juta.

13. Sekarang kita akan mengekspor fitur yang dipilih sebagai layer baru. Klik kanan ne_10m_populated_places_simplelayer dan pergi ke Export Save Selected Features As...

14. Anda dapat memilih format apa pun yang Anda sukai sebagai Format . Untuk latihan ini, kita akan memilih GeoJSON. GeoJSON adalah format berbasis teks yang digunakan secara luas dalam pemetaan web. Klik tombol ... di sebelah Nama file dan masukkan populated_capitals.geojsonsebagai file output.

15. Data input memiliki banyak kolom. Anda hanya dapat memilih sebagian dari kolom asli untuk diekspor. Perluas bagian Pilih bidang yang akan diekspor dan opsi ekspornya . Klik Deselect All dan centang kolom nameand pop_max. Klik Oke.

16. Sebuah layer baru populated_capitalsakan dimuat di QGIS. Anda dapat menghapus centang pada ne_10m_populated_places_simplelayer untuk menyembunyikannya dan melihat poin dari layer yang baru diekspor.

Lihat Hasil Gambar file.JPEG [disini](https://github.com/zalnamustika11/SIG-Teori-Modul2-WorkingWithAttributte/blob/main/working_with_attribute.JPG)

Lihat Hasil file.QGZ [disini](https://github.com/zalnamustika11/SIG-Teori-Modul2-WorkingWithAttributte/blob/main/working_with_attribute.qgz)

