<!-- Cover Makalah dengan Logo -->

<div align="center">


# *PEMROSESAN CITRA DIGITAL*

## *(Detail Halftoning: Patterning & Dithering)*
<!-- Menambahkan Logo -->
<img src="https://ulm.ac.id/id/wp-content/uploads/2023/03/lambangULM2021warna.png" width="200"/>
---

### Disusun Oleh:

**Putu Devia Marsa**  
**NIM: 2310131220003**

### Dosen Pembimbing:
**Dr. Harja Santana Purba, M.KOM**
**Novan Alkaf Bahraini Saputra, S.Kom., M.T**
**Ihdalhubbi Maulida, M.Kom**

**UNIVERSITAS LAMBUNG MANGKURAT** 
**FAKULTAS KEGURUAN DAN ILMU PENDIDIKAN**  
**PROGRAM STUDI PENDIDIKAN KOMPUTER**
**2024**

</div>

---

<!-- Daftar Isi -->
# Daftar Isi
1. Daftar Isi
2. BAB I - Pendahuluan
3. BAB II - Pembahasan
    2.1 Patterning
    2.2 Dithering
4. BAB III - Penutup


---

<!-- BAB I -->
<a name="bab-i---pendahuluan"></a>

# BAB I  Pendahuluan


Halftoning adalah teknik yang digunakan untuk merepresentasikan gambar atau ilustrasi dengan gradasi warna atau bayangan menggunakan pola titik-titik yang berbeda ukuran atau kepadatan. Teknik ini sangat populer dalam dunia percetakan, terutama pada media yang hanya mendukung jumlah warna terbatas, seperti cetakan hitam-putih atau layar komputer yang menggunakan piksel. Patterning merujuk pada pola atau susunan titik-titik yang digunakan dalam halftoning untuk menciptakan variasi visual dari bayangan atau warna. Sementara itu, detailing dalam halftoning mengacu pada tingkat detail yang dihasilkan dari variasi ukuran dan posisi titik, yang berpengaruh pada kejelasan atau kualitas gambar keseluruhan.

Pada prinsipnya, halftoning bekerja dengan mengatur pola titik-titik (patterning) yang lebih besar atau lebih rapat untuk menciptakan ilusi gradasi abu-abu, meskipun sebenarnya hanya terdiri dari dua warna dasar (hitam dan putih, atau warna primer lainnya). Semakin rapat pola titik-titik tersebut, semakin gelap area yang dihasilkan, sementara area dengan titik yang lebih jarang akan tampak lebih terang.

Teknik ini memungkinkan reproduksi gambar berkualitas tinggi pada berbagai media, seperti surat kabar, majalah, atau layar digital dengan resolusi rendah, tanpa memerlukan jumlah warna penuh. Halftoning juga digunakan dalam pencetakan warna melalui teknik CMYK, di mana titik-titik warna Cyan, Magenta, Yellow, dan Black dipadukan untuk menghasilkan gambar penuh warna.



---

<!-- BAB II -->
<a name="bab-ii---Pembahasan"></a>

# BAB II  Pembahasan

### 2.1 Patterning
Patterning adalah proses membentuk pola teratur atau berulang menggunakan elemen visual seperti titik, garis, atau bentuk untuk menciptakan efek visual tertentu. Dalam konteks halftoning, patterning digunakan untuk menciptakan ilusi gradasi warna atau bayangan dengan menyusun titik-titik secara sistematis, meskipun sebenarnya hanya dua warna yang digunakan (misalnya hitam dan putih). Teknik ini memungkinkan tampilan gambar kompleks di media yang memiliki keterbatasan warna atau resolusi.

**Langkah-langkah dalam Proses Patterning**
1. Konversi Gambar Grayscale ke Piksel: Gambar asli yang memiliki gradasi warna (biasanya dalam bentuk grayscale) dipecah menjadi piksel-piksel kecil. Setiap piksel merepresentasikan intensitas kecerahan yang berbeda, dari 0 (hitam) hingga 255 (putih) dalam sistem 8-bit.

2. Tentukan Ukuran dan Pola Grid: Untuk melakukan patterning, tentukan ukuran grid atau matriks (misalnya 3x3, 4x4, atau 5x5) yang akan digunakan untuk mewakili setiap piksel. Ukuran grid ini akan mempengaruhi resolusi dan ketajaman gambar.

3. Assign Nilai Piksel ke Pola Grid: Setiap piksel diubah menjadi pola titik-titik dalam grid. Jumlah titik yang diisi dalam grid ini ditentukan berdasarkan intensitas piksel. Piksel yang lebih gelap akan diwakili oleh lebih banyak titik hitam dalam grid, sementara piksel yang lebih terang akan diwakili oleh lebih sedikit titik hitam.

4. Generasi Pola: Pola titik dibuat dengan mengikuti urutan tertentu. Misalnya, dalam pola 4x4, gradasi untuk nilai piksel 255 (putih) akan diwakili oleh grid kosong (tanpa titik hitam), sedangkan nilai piksel 0 (hitam) akan diwakili oleh semua sel dalam grid diisi dengan titik hitam.

5. Proses Perulangan untuk Seluruh Gambar: Setelah pola grid terbentuk untuk satu piksel, proses ini diulang untuk seluruh piksel dalam gambar sehingga menghasilkan pola besar yang mencerminkan keseluruhan gambar.

**Cara Perhitungan dalam Patterning:**
Perhitungan dalam patterning didasarkan pada pembagian nilai intensitas piksel dengan jumlah sel dalam grid yang tersedia.
Misalkan kita menggunakan grid 4x4 (16 sel) dan gambar yang akan diproses adalah gambar grayscale (nilai 0 hingga 255). Langkah perhitungannya adalah:

1. Tentukan Jumlah Gradasi yang Diinginkan: Dalam grid 4x4, terdapat 16 sel, artinya kita dapat merepresentasikan 17 tingkatan gradasi (mulai dari 0 titik hitam hingga 16 titik hitam).
2. Nilai Piksel: Setiap piksel grayscale (nilai 0-255) dibagi menjadi tingkatan yang sesuai dengan jumlah sel dalam grid.
3. Terapkan Pola Grid: Berdasarkan perhitungan, untuk piksel bernilai 128, kita akan mengisi 8 dari 16 sel dalam grid 4x4 dengan titik hitam. Pola titik-titik ini kemudian disusun dalam urutan yang simetris atau acak tergantung pada jenis patterning yang digunakan.

**Pseudocode patterning**
1. Input: Gambar Grayscale (Matrix)
2. Output: Gambar Biner (Matrix)

3. Definisikan threshold (misalnya 128 untuk gambar grayscale)
4. Buat matriks kosong untuk gambar biner dengan ukuran yang sama

5. Untuk setiap piksel (i, j) dalam Gambar Grayscale:
    a. Ambil nilai piksel saat ini: value = Gambar[i][j]
    
    b. Jika value >= threshold:
       i. Set Gambar Biner[i][j] = 255  // Putih
    c. Jika value < threshold:
        i. Set Gambar Biner[i][j] = 0    // Hitam

6. Selesai

7. Tampilkan atau simpan Gambar Biner

**Penjelasan**
Kode ini adalah algoritma untuk melakukan proses patterning pada gambar grayscale guna menghasilkan gambar biner. Pertama, program menerima input berupa gambar grayscale yang disimpan dalam bentuk matriks, dan menyiapkan matriks kosong untuk output gambar biner. Selanjutnya, kode mendefinisikan threshold, yang dalam hal ini diatur pada nilai 128. Proses utama dilakukan dengan iterasi pada setiap piksel dalam gambar grayscale; untuk setiap piksel, nilai piksel dibandingkan dengan threshold: jika nilai tersebut lebih besar atau sama dengan threshold, piksel biner diatur menjadi putih (255), dan jika kurang, diatur menjadi hitam (0). Setelah semua piksel diproses, hasil akhir adalah gambar biner yang ditampilkan atau disimpan.





### 2.2 Dithering
Dithering adalah teknik grafis yang digunakan untuk mensimulasikan gradasi warna atau bayangan pada gambar yang hanya memiliki jumlah warna terbatas. Dalam proses ini, piksel dengan intensitas warna berbeda ditempatkan berdekatan untuk menciptakan ilusi gradasi yang lebih halus. Meskipun gambar sebenarnya terdiri dari warna-warna tertentu (misalnya hitam-putih atau jumlah warna yang lebih sedikit), dithering memberikan kesan seolah-olah gambar memiliki spektrum warna yang lebih luas.

**Langkah-langkah dalam Dithering:**
1. Konversi Gambar Grayscale: Sebelum melakukan dithering, gambar sering kali diubah menjadi grayscale untuk menyederhanakan proses. Gambar grayscale memiliki nilai intensitas piksel mulai dari 0 (hitam) hingga 255 (putih).
2. Penghitungan Nilai Piksel: Setiap piksel dalam gambar grayscale diperiksa untuk menentukan warna terdekat yang bisa dihasilkan dalam palet warna terbatas (misalnya, hitam atau putih dalam gambar hitam-putih).

**contoh perhitungan dithering:**
Misalkan kita memiliki gambar grayscale 3x3 dengan nilai piksel sebagai berikut:
|  100 |  200 |  150 |
|  50  |  125 |  175 |
|  180 |  90  |  220 |

**Pilih Warna Terdekat**
Kita hanya memiliki dua warna yang tersedia: hitam (0) dan putih (255). Mari kita pilih warna terdekat untuk setiap piksel.

Piksel (0,0): 100 → Hitam (0) (karena 100 < 128)
Piksel (0,1): 200 → Putih (255) (karena 200 ≥ 128)
Piksel (0,2): 150 → Putih (255) (karena 150 ≥ 128)
Piksel (1,0): 50 → Hitam (0) (karena 50 < 128)
Piksel (1,1): 125 → Hitam (0) (karena 125 < 128)
Piksel (1,2): 175 → Putih (255) (karena 175 ≥ 128)
Piksel (2,0): 180 → Putih (255) (karena 180 ≥ 128)
Piksel (2,1): 90 → Hitam (0) (karena 90 < 128)
Piksel (2,2): 220 → Putih (255) (karena 220 ≥ 128)

**Hasil Awal Warna Terdekat**
|  0   |  255 |  255 |
|  0   |  0   |  255 |
|  255 |  0   |  255 |

**Hitung Error**
Hitung error untuk setiap piksel:

Piksel (0,0):
Error = 100 - 0 = 100
Piksel (0,1):
Error = 200 - 255 = -55
Piksel (0,2):
Error = 150 - 255 = -105
Piksel (1,0):
Error = 50 - 0 = 50
Piksel (1,1):
Error = 125 - 0 = 125
Piksel (1,2):
Error = 175 - 255 = -80
Piksel (2,0):
Error = 180 - 255 = -75
Piksel (2,1):
Error = 90 - 0 = 90
Piksel (2,2):
Error = 220 - 255 = -35

**Sebarkan Error ke Piksel lainnya:**
Error dari Piksel (0,0):
Error yang dihitung untuk piksel ini adalah 100.
Sebarkan ke Piksel (0,1):
Sebagian dari error ini, yaitu tujuh per enam belas dari 100, dihitung sebagai berikut: Tujuh per enam belas dikali 100 menghasilkan 43.75. Kita bulatkan hasil ini menjadi 44.
Sebarkan ke Piksel (1,0):
Sebagian dari error ini, yaitu tiga per enam belas dari 100, dihitung sebagai berikut: Tiga per enam belas dikali 100 menghasilkan 18.75. Kita bulatkan hasil ini menjadi 19.
Sebarkan ke Piksel (1,1):
Sebagian dari error ini, yaitu lima per enam belas dari 100, dihitung sebagai berikut: Lima per enam belas dikali 100 menghasilkan 31.25. Kita bulatkan hasil ini menjadi 31.

Nilai Setelah Penyebaran untuk Piksel Tetangga
Setelah menyebarkan error, kita memperbarui nilai piksel tetangga sebagai berikut:
Untuk Piksel (0,1): Nilai awalnya adalah 200, dan setelah menambahkan 44, nilainya menjadi 244.
Untuk Piksel (1,0): Nilai awalnya adalah 50, dan setelah menambahkan 19, nilainya menjadi 69.
Untuk Piksel (1,1): Nilai awalnya adalah 125, dan setelah menambahkan 31, nilainya menjadi 156

**Pseudocode Dithering**
1. Input: Gambar Grayscale (Matrix)
2. Output: Gambar Biner (Matrix)

3. Definisikan threshold (misalnya 128)
4. Buat matriks kosong untuk gambar biner dengan ukuran yang sama
5. Buat matriks untuk menyimpan error dengan nilai awal 0

6. Untuk setiap piksel (i, j) dalam Gambar Grayscale:
    a. Ambil nilai piksel saat ini: value = Gambar[i][j]
    
    b. Tambahkan error yang sudah disimpan: 
       value = value + Error[i][j]
    
    c. Tentukan warna terdekat berdasarkan nilai:
       Jika value >= threshold:
           i. Set Gambar Biner[i][j] = 255  // Putih
           ii. Hitung error = value - 255
       Jika value < threshold:
           i. Set Gambar Biner[i][j] = 0    // Hitam
           ii. Hitung error = value - 0

    d. Sebarkan error ke piksel tetangga:
       - Piksel (i, j+1): Gambar[i][j+1] += (7/16) * error
       - Piksel (i+1, j-1): Gambar[i+1][j-1] += (3/16) * error
       - Piksel (i+1, j): Gambar[i+1][j] += (5/16) * error
       - Piksel (i+1, j+1): Gambar[i+1][j+1] += (1/16) * error

7. Selesai

8. Tampilkan atau simpan Gambar Biner

**Penjelasan**
Kode ini adalah algoritma untuk melakukan dithering pada gambar grayscale menggunakan metode Error Diffusion, khususnya algoritma Floyd-Steinberg. Proses dimulai dengan menerima input berupa gambar grayscale dalam bentuk matriks, kemudian mendefinisikan threshold untuk membedakan antara warna hitam dan putih. Selanjutnya, kode menyiapkan matriks kosong untuk gambar biner dan matriks error yang diinisialisasi dengan nol. Dalam iterasi untuk setiap piksel, nilai piksel ditambahkan dengan error yang ada, kemudian ditentukan warna terdekat berdasarkan threshold: jika nilai lebih besar atau sama dengan threshold, piksel diatur menjadi putih dan error dihitung; jika kurang, piksel diatur menjadi hitam dan error juga dihitung. Setelah itu, error disebarkan ke piksel-piksel tetangga menggunakan bobot tertentu sesuai algoritma. Setelah semua piksel diproses, gambar biner yang dihasilkan ditampilkan atau disimpan.




---

<!-- BAB III -->
<a name="bab-iii---metodologi-penelitian"></a>

# BAB III  Penutup

### Kesimpulan
Halftoning: Patterning & Dithering adalah teknik penting dalam reproduksi gambar yang bertujuan untuk menciptakan ilusi gradasi warna pada media biner. Dengan menggunakan metode patterning, gambar grayscale diubah menjadi gambar biner berdasarkan nilai threshold, menghasilkan tampilan kontras tinggi yang sesuai untuk pencetakan. Sementara itu, dithering mengimplementasikan penyebaran error untuk menghasilkan efek visual yang lebih halus, memungkinkan detail gambar yang lebih baik dengan mempertahankan tampilan natural pada gambar yang terbatas dalam jumlah warna. Kedua teknik ini sangat berguna dalam desain grafis, percetakan, dan aplikasi digital, memfasilitasi representasi gambar yang efisien pada perangkat dengan kapasitas warna terbatas.

---



<!-- Daftar Pustaka -->
<a name="daftar-pustaka"></a>

# Daftar Pustaka
Putri, D. A., & Hidayati, R. (2018). *Implementasi Patterning dalam Proses Halftoning pada Gambar.*. Jurnal Seni dan Desain, 5(2), 78-86.

Santoso, A. B., & Widodo, S. (2019). *Analisis Metode Dithering untuk Meningkatkan Kualitas Gambar Digital*.Jurnal Ilmu Komputer dan Informatika, 7(1), 45-56.

Wibowo, A., & Rahmawati, I. (2021).  *Studi Komparatif Teknik Halftoning dan Dithering pada Gambar Grayscale*. Jurnal Komputer dan Multimedia, 14(2), 102-111.