# **Generalized Regression Neural Network**
**(by Abdi Negara Guci S.Mat)**
Halo Teman - Teman, Kali ini saya akan menjelaskan terkait sebuah metode *Neural Network* , metode ini bernama **Generalized Regression Neural Network (GRNN)**. Metode ini merupakan jenis *Neural Network* yang umum digunakan untuk tugas regresi, yang melibatkan suatu prediksi nilai kontinu berdasarkan suatu *Input* data. GRNN ini juga menurut saya sangat unik, karena menggunakan suatu kernel *Radial Basis Function* (RBF) yang biasanya kita temui kalau kita belajar lebih mendalam tentang kernel pada *Support Vector Machine*

## **Karakteristik GRNN**

Berikut adalah beberapa karakteristik kunci dari GRNN:

1. **Fungsi Basis Radial (RBF)**: GRNN menggunakan fungsi basis radial untuk mentransformasi data masukan ke dalam ruang fitur berdimensi lebih tinggi. Fungsi basis radial adalah fungsi matematika yang bergantung hanya pada jarak dari titik pusat, yang dikenal sebagai pusat atau prototipe. Fungsi basis radial yang paling umum digunakan dalam GRNN adalah fungsi Gaussian.

2. **Pembelajaran Sekali Jalan:** GRNN melakukan proses pembelajaran sekali jalan, yang berarti mereka belajar set data latih segera setelah disajikan. Hal ini membuatnya efisien terutama untuk tugas regresi dengan kumpulan data berukuran kecil hingga sedang.

3. **Pelatihan Cepat:** Pelatihan GRNN umumnya lebih cepat dibandingkan dengan jenis jaringan saraf lainnya karena tidak melibatkan proses optimisasi iteratif seperti gradien turun. Sebaliknya, ia menghitung bobot selama pelatihan berdasarkan data pelatihan dan menyimpannya untuk digunakan nanti selama prediksi.

4. **Pendekatan Universal:** Seperti banyak arsitektur jaringan saraf lainnya, GRNN adalah pendekatan fungsi universal, yang berarti mereka memiliki kapasitas untuk memperkirakan fungsi kontinu apa pun dengan akurasi sewenang-wenang dengan jumlah neuron tersembunyi yang cukup.

5. **Tugas Regresi:** Sementara beberapa jaringan saraf dirancang untuk tugas klasifikasi (di mana keluarannya adalah kategori atau label), GRNN secara khusus ditujukan untuk tugas regresi, di mana tujuannya adalah untuk memprediksi variabel keluaran kontinu berdasarkan fitur masukan.

## **Pendekatan Matematika GRNN**

Untuk membahas GRNN secara matematis, maka pada kesempatan kali ini saya berusaha memahami konsepnya dari jurnal aslinya langsung dari bapak *Donald F. Specht* pada papernya berjudul ***A General Regression Neural Network*** Namun sebelum itu, ada beberapa konsep matematis yang menurut saya perlu dipahami lebih lanjut untuk itu, simak beberapa penjelasan berikut ini.
 1. **Fungsi Kepadatan peluang Bersama:** Jika $X$ dan $Y$ adalah dua variabel acak kontinu, maka fungsi kepadatan peluang bersama $f(x,y)$ untuk $X$ dan $Y$ adalah fungsi yang memenuhi sifat berikut:
 *  $f(x,y) \geq 0$ untuk setiap $(x)$ dan $(y)$.
 *  $\int_{-\infty}^{\infty} \int_{-\infty}^{\infty} f(x, y) \, dx \, dy = 1$, yaitu total area di bawah kurva $f(x, y)$ sama dengan $1$.
 *  Untuk setiap daerah $R$ di bidang $xy$, probabilitas $X$ dan $Y$ jatuh dalam $R$ adalah $P((X,Y) \in R) = \iint_R f(x, y) \, dx \, dy$.
 * Misalkan \( X \) adalah variabel acak kontinu dengan fungsi kepadatan peluang:

 >  $f(x) = \frac{1}{\sqrt{2\pi\sigma^2}} e^{-\frac{(x-\mu)^2}{2\sigma^2}} ...\text{(1)}$

 di mana $\mu$ adalah rata-rata (mean) dari distribusi $X$ dan $\sigma^2$ adalah varians (variance) dari distribusi $X$. Persamaan $(1)$ adalah bentuk standar dari fungsi kepadatan peluang untuk distribusi normal (Gaussian), di mana $\mu$ adalah rata-rata (mean) dan $\sigma^2$ adalah varians (variance) dari distribusi $X$.





