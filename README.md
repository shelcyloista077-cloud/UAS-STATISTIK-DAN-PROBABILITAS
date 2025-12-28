# Tugas Analisis Statistik: Deskriptif, Korelasi, dan Regresi

## 1. Informasi Penyusun

- **Nama:** `[SHELCY LOISTA BR TARIGAN]`
- **NIM:** `[2515091109]`
- **Program Studi:** `[SISTEM INFORMASI]`
- **Mata Kuliah:** Statistika dan Probabilitas

---

## 2. Deskripsi Proyek

Pada bagian ini, jelaskan secara singkat dataset yang Anda gunakan. Apa saja variabel di dalamnya? Apa tujuan dari analisis yang Anda lakukan?

*Contoh:*
> Dataset yang digunakan adalah data `...` yang berisi informasi tentang `...`. Variabel kunci dalam dataset ini meliputi `variabel_A`, `variabel_B`, dan `variabel_C`. Tujuan dari proyek ini adalah untuk memahami karakteristik data melalui statistik deskriptif, menguji hubungan antara `variabel_A` dan `variabel_B` melalui analisis korelasi, serta memprediksi `variabel_C` menggunakan `variabel_A` sebagai prediktor melalui analisis regresi.
> jawaban:
>  Dataset yang digunakan adalah data `data_startup_saas.cvc`yang berisi informasi tentang performa dan karakteristik startup Software-as-a-Service (SaaS).Data ini mencakup berbagai metrik keuangan dan operasional yang relevan yntuk annalisis bisnis teknologi.Variabel kunci dalam dataset ini meliputi
> Pendapatan_Tahunan_Miliar_IDR:Pendapatan tahunan perusahaan dalam miliar Rupiah(variabel numerik kontinu)
> Biaya_Akuisisi_Pelanggan_Juta_IDR:Biaya yang dikeluarkan untuk mendapatkan setiap pelanggan baru dalam juta Rupiah(variabel numerik kontinu)
> Selain ini juga masih ada Nilai_Pelanggan_Juta_IDR,Tingkat_Churn_Persen.Tujuan dari proyek ini adalah:1.(analisis deskriptif) untuk memahami ditribusi dan karakteristik variabel Pendapatan_Tahunan_Miliar_IDR melalui statistik deskriptif dan visualisasi.2.(Uji Asumsi Normalitas) menguji distribusi data untuk menentukan kelayakan metode statistik parametik.3.(Analisis Kolerasi) Untuk menyelidiki hubungan linear anatara Pendapatan_Tahunan_Miliar_IDR dan Biaya_Akuisisi_Pelanggan_Juta_IDR.4.(Pemodelan Regresi) membangun model prediksi untuk memperkirakan pendapatan tahunan berdasarkan biaya akuisisi pelanggan.

## 3. Struktur Proyek

Proyek ini diorganisir ke dalam beberapa folder:
- `/data`: Berisi dataset mentah yang digunakan untuk analisis.
- `/scripts`: Berisi semua skrip R yang digunakan dalam analisis, diurutkan berdasarkan alur kerja.
- `/results`: Berisi output dari analisis, seperti plot, gambar, atau tabel ringkasan.

---

## 4. Cara Menjalankan Analisis

Untuk mereproduksi hasil analisis ini, ikuti langkah-langkah berikut:
1. Pastikan Anda memiliki R dan RStudio terinstal.
2. Buka proyek R ini di RStudio.
3. Instal paket yang diperlukan dengan menjalankan perintah berikut di konsol R:
   ```R
   # install.packages(c("tidyverse", "corrplot", "knitr"))
   ```
4. Jalankan skrip di dalam folder `/scripts` secara berurutan, mulai dari `01_data_preparation.R` hingga `05_analisis_regresi.R`.

---

## 5. Hasil dan Interpretasi

Di bagian ini, mahasiswa diharapkan untuk menyajikan dan menginterpretasikan hasil dari setiap tahap analisis.

### 5.1. Statistik Deskriptif
- **Ukuran Pemusatan (Mean, Median, Modus):**
  - *Tabel atau ringkasan...*
  - *Interpretasi:* Jelaskan apa arti dari nilai-nilai tersebut terkait dengan data
     Anda.
    Jawaban:
    Mean:31.883(Yang dimana rata rata pendapatan adalah sebanyak 31.883 IDR)
    Median:31.305(Nilai tengah data 50% startup berpendapatan ≤ 31.30 miliar IDR dan 50% ≥ 31.30 miliar IDR)
    Modus:1.87(Pendapatan 1.87 Miliar IDR merupakan nilai yang paling sering muncul)
    
- **Ukuran Sebaran (Standar Deviasi, Range, Kuartil):**
  - *Tabel atau ringkasan...*
  - *Interpretasi:* Jelaskan seberapa menyebar data Anda berdasarkan nilai-nilai ini.
  - Jawaban:
  - Standar Deviasi:19.79(Variasi pendapatan antar startup cukup tinggi,kurang lebih sekitar 19.79 Miliar IDR dari rata-rata)
  - Range:1.00-66.89(Yang dimana rangenya yang sangat lebar.Selisih terendah tertinggi:65.89 Miliar IDR,menunjukkan kesenjangan pendapatan yang besar
  - Kuartil pertama (14.31 miliar IDR) dan kaurtil ketiga (49.04 miliar IDR)
    Dimana dari data ini memberikan gambaran bahwa 50% startup sedang berpendapatan dalam rentang yang cukup luas sebesar 34.47 miliar IDR,sementara 25% startup berpendapatan dibawah 14.31 miliar IDR dan 25% sisanya berpendapatan diatas 49.04 miliar IDR.
- **Visualisasi (Histogram/Boxplot):**
  - *Sematkan gambar plot dari folder /results...*
  - *Interpretasi:* Jelaskan wawasan apa yang Anda dapatkan dari bentuk distribusi data.
Jawaban:
-Histogram menunjukkan distribusi pendapatan tahunan startup yang mendekati distribusi normal dengan sedikit kemiringan ke kanan
### 5.2. Uji Normalitas
- **Hasil Uji Shapiro-Wilk:**
  - *Nilai p-value...*
  - *Interpretasi:* Apakah data Anda terdistribusi normal berdasarkan hasil uji? Apa implikasinya?
 Jawaban:
 Nilai p-value adalah
Untuk analisis korelasinya,meski data tidak normal,korelasi pearsson 


- **Plot Q-Q:**
  - *Sematkan gambar plot dari folder /results...*
  - *Interpretasi:* Apakah titik-titik data mengikuti garis lurus? Apa artinya?
  - Jawaban:
  - Titik titik data tidak mengikuti garis lurus diagonal dengan sempurna,teruttama di kedua ekor distribusi.Deviasi dari garis normal teoritis di ekor kanan dan kiri mengindikasi distribusi data tidak normal,yang konsisten dengan hasil uji shapiro-wilk (p-value ≈ 0).Pola lengkungan di kedua ujung menunjukkan data memiliki ekor yang lebih berat dibanding distribusi normal teoritis.

### 5.3. Analisis Korelasi
- **Nilai Koefisien Korelasi:**
  - *Nilai r...*
  - *Interpretasi:* Seberapa kuat dan apa arah hubungan antara dua variabel yang Anda uji? (misalnya, korelasi positif kuat, negatif lemah, atau tidak ada korelasi).
  - Jawaban:
  - Nilai r = 0.9955247 dibulatkan menjadi 0.996
  - Hubungan antara Pendapatan_Tahunan_Miliar_IDR dan Biaya_Akuisisi_Pelanggan_Juta_IDR menunjukkan korelasi positif yang sangat kuat.Nilai r mendekati +1 yang dimana hubungan linearnya hampir sempurna,dan kita juga tahu peningkatan biaya akuisisi pelanggan berkaitan lansung dengan peningkatan pendapatan tahunan.
- **Visualisasi (Scatter Plot):**
  - *Sematkan gambar plot dari folder /results...*
  - *Interpretasi:* Apakah pola pada scatter plot mendukung hasil koefisien korelasi?
  - Jawaban:
  - Scatter plot menunjukkan pola titik titik yang membentuk diagonal yang hampir lurus,dengan titik yang sangat rapat mengikuti garis tren linear merah.Pola tersebut sangat mendukung hasil koefisien korelasi r= 0.996,dimana hubungan linear positif yang hampir sempurna antara kedua variabel.

### 5.4. Analisis Regresi
- **Model Regresi:**
  - *Persamaan regresi: Y = b0 + b1*X*
  - *Interpretasi:* Jelaskan arti dari koefisien intercept (b0) dan slope (b1) dalam konteks data Anda.
  - Jawaban:
  - Persamaan:Pendapatan = -1.06 + 0.98 x Biaya akuisisi
  - Intercept (b0)=-1.06 menujukkan prediksi pendapatan negatif ketika biaya akuisisi nol(tidak realistis secara bisnis),sementara slope (b1) 0.98 yang berarti setiap kenaikan 1 juta IDR biaya akuisisi meningkatkan pendapatan 0.98 miliar IDR.Model ini memiliki R² 99.1%.Yang dimana menunjukkan dan menjelaskan bahwa variasi pendapatan nya yang sangat tinggi dan hubungan nya signifikan secara statistik (p < 0.001).
- **Evaluasi Model (R-squared):**
  - *Nilai R-squared...*
  - *Interpretasi:* Berapa persen variasi dari variabel dependen yang dapat dijelaskan oleh model regresi Anda?
  - jawaban:
  - Nilai R-squared adalah 0.991 atau 99.1%
  - Model regresi mampu menjelaskan 99.1% variasi dalam dependen  Pendapatan_Tahunan_Miliar_IDR.Hanya 0.9% variasi yang tidak dapat dijelaskan oleh variabel independen Biaya_Akuisisi_Pelanggan_Juta_IDR.Nilai R² yang mendekati 1 ini menunjukkan kecocokan model yang hampir sempurna dan diperkirakan sangant tinggi.
- **Visualisasi (Garis Regresi pada Scatter Plot):**
  - *Sematkan gambar plot dari folder /results...*
  - *Interpretasi:* Jelaskan bagaimana garis regresi merepresentasikan hubungan antara variabel.
Jawaban:
Dari gambar tersebut bisa kita simpulkan garis merah pada scatter plot menunjukkan hubungan linear yang hampir sempurna anara biaya akuisisi pelanggan dan pendapatan tahunan.Garis ini melewati pusat sebaran data dengan hampir semua titik berada sangat dekat dengan garis,merepresentasikan slope 0.98 dari persamaan regresi.Dimana data sangat sesuai dengan model dengan sangat baik  R-squared adalah 0.991 atau 99.1%
---

## 6. Kesimpulan

Rangkum temuan utama dari analisis Anda dalam beberapa kalimat. Apa wawasan paling penting yang Anda peroleh?
Jawaban:
