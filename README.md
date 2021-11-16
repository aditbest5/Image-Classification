# Laporan Proyek Machine Learning - Nama Anda

## Domain Proyek

Domain proyek yang dipilih dalam proyek machine learning ini mengenai **Ekonomi dan Bisnis** dengan judul "Prediksi Harga Microsoft Stock".
- **Latar Belakang**
<p align="center">
  <img width="460" height="300" src="https://media.istockphoto.com/vectors/display-of-stock-market-quotes-stock-exchange-board-led-digital-vector-id1220909109" alt="https://www.istockphoto.com/id/vektor/tampilan-penawaran-pasar-saham-papan-bursa-saham-efek-tampilan-digital-yang-gm1220909109-357678133">
</p>
    Belakangan ini harga stock market, baik diluar maupun didalam negeri mengalami nilai yang cukup fluktuatif. Investasi melalui pasar modal atau bursa saham menjanjikan return yang lebih besar dibandingkan dengan instrumen konvensional baik dalam bentuk dividen(keuntungan dari hasil pembagian laba perusahaan) maupun capital gain (keuntungan yang diperoleh dari kelebihan nilai jual terhadap nilai beli saham). Pada dasarnya harga saham bergerak secara fluktuatif setiap harinya, oleh karena itu dibutuhkan sistem yang dapat memprediksi pergerakan harga saham tersebut untuk membantu para investor dalam melakukan analisis dan tindakan yang tepat sehingga resiko dapat diminimalisir dan return dapat dioptimalkan [[1](https://repository.telkomuniversity.ac.id/pustaka/65748/prediksi-pergerakan-harga-saham-menggunakan-algoritma-memetikaprediction-of-stock-market-price-movement-using-memetic-algorithm.html)]. Oleh karena perlu dilakukan pemodelan dan prediksi untuk mengetahui kondisi dan mempersiapkan strategi untuk menghadapi penurunan atau pelonjakan harga saham.
    
    Data yang digunakan adalah data pergerakan saham Microsoft inc dari tahun 2015 sampai 2021 dengan total data sebanyak 1511 data. Untuk menganalisis data sebanyak ini menggunakan bantuan program Jupyter Notebook dengan bahasa pemrograman python. Python telah banyak digunakan oleh para Data Scientist untuk mengolah data. Python juga bahasa pemrograman yang populer dan relatif mudah penggunaannya. Dalam proses analisa menggunakan konsep Machine Learning dimana mesin mempelajari data historik dari pergerakan saham sebelumnya untuk memprediksi harga saham dimasa depan.
  
  Format Referensi: [Judul Referensi](https://scholar.google.com/) 

## Business Understanding

Pada bagian ini, kamu perlu menjelaskan proses klarifikasi masalah.

Bagian laporan ini mencakup:

### Problem Statements

Menjelaskan pernyataan masalah latar belakang:
- Pernyataan Masalah 1
- Pernyataan Masalah 2
- Pernyataan Masalah n

### Goals

Menjelaskan tujuan dari pernyataan masalah:
- Jawaban pernyataan masalah 1
- Jawaban pernyataan masalah 2
- Jawaban pernyataan masalah n

Semua poin di atas harus diuraikan dengan jelas. Anda bebas menuliskan berapa pernyataan masalah dan juga goals yang diinginkan.

**Rubrik/Kriteria Tambahan (Opsional)**:
- Menambahkan bagian “Solution Statement” yang menguraikan cara untuk meraih goals. Bagian ini dibuat dengan ketentuan sebagai berikut: 

    ### Solution statements
    - Mengajukan 2 atau lebih solution statement. Misalnya, menggunakan dua atau lebih algoritma untuk mencapai solusi yang diinginkan atau melakukan improvement pada baseline model dengan hyperparameter tuning.
    - Solusi yang diberikan harus dapat terukur dengan metrik evaluasi.

## Data Understanding
Paragraf awal bagian ini menjelaskan informasi mengenai data yang Anda gunakan dalam proyek. Sertakan juga sumber atau tautan untuk mengunduh dataset. Contoh: [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/Restaurant+%26+consumer+data).

Selanjutnya uraikanlah seluruh variabel atau fitur pada data. Sebagai contoh:  

### Variabel-variabel pada Restaurant UCI dataset adalah sebagai berikut:
- accepts : merupakan jenis pembayaran yang diterima pada restoran tertentu.
- cuisine : merupakan jenis masakan yang disajikan pada restoran.
- dst

**Rubrik/Kriteria Tambahan (Opsional)**:
- Melakukan beberapa tahapan yang diperlukan untuk memahami data, contohnya teknik visualisasi data atau exploratory data analysis.

## Data Preparation
Pada bagian ini Anda menerapkan dan menyebutkan teknik data preparation yang dilakukan. Teknik yang digunakan pada notebook dan laporan harus berurutan.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menjelaskan proses data preparation yang dilakukan
- Menjelaskan alasan mengapa diperlukan tahapan data preparation tersebut.

## Modeling
Tahapan ini membahas mengenai model machine learning yang digunakan untuk menyelesaikan permasalahan. Anda perlu menjelaskan tahapan dan parameter yang digunakan pada proses pemodelan.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menjelaskan kelebihan dan kekurangan dari setiap algoritma yang digunakan.
- Jika menggunakan satu algoritma pada solution statement, lakukan proses improvement terhadap model dengan hyperparameter tuning. **Jelaskan proses improvement yang dilakukan**.
- Jika menggunakan dua atau lebih algoritma pada solution statement, maka pilih model terbaik sebagai solusi. **Jelaskan mengapa memilih model tersebut sebagai model terbaik**.

## Evaluation
Pada bagian ini anda perlu menyebutkan metrik evaluasi yang digunakan. Lalu anda perlu menjelaskan hasil proyek berdasarkan metrik evaluasi yang digunakan.

Sebagai contoh, Anda memiih kasus klasifikasi dan menggunakan metrik **akurasi, precision, recall, dan F1 score**. Jelaskan mengenai beberapa hal berikut:
- Penjelasan mengenai metrik yang digunakan
- Menjelaskan hasil proyek berdasarkan metrik evaluasi

Ingatlah, metrik evaluasi yang digunakan harus sesuai dengan konteks data, problem statement, dan solusi yang diinginkan.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menjelaskan formula metrik dan bagaimana metrik tersebut bekerja.

**---Ini adalah bagian akhir laporan---**
