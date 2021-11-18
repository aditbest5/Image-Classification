# Laporan Proyek Machine Learning - Aditya Aprianto

## Domain Proyek

Domain proyek yang dipilih dalam proyek machine learning ini mengenai **Ekonomi dan Bisnis** dengan judul "Prediksi Harga Microsoft Stock".

- **Latar Belakang**

    Belakangan ini harga stock market, baik diluar maupun didalam negeri mengalami nilai yang cukup fluktuatif. Investasi melalui pasar modal atau bursa saham menjanjikan return yang lebih besar dibandingkan dengan instrumen konvensional baik dalam bentuk dividen(keuntungan dari hasil pembagian laba perusahaan) maupun capital gain (keuntungan yang diperoleh dari kelebihan nilai jual terhadap nilai beli saham). Pada dasarnya harga saham bergerak secara fluktuatif setiap harinya, oleh karena itu dibutuhkan sistem yang dapat memprediksi pergerakan harga saham tersebut untuk membantu para investor dalam melakukan analisis dan tindakan yang tepat sehingga resiko dapat diminimalisir dan return dapat dioptimalkan [1](https://repository.telkomuniversity.ac.id/pustaka/65748/prediksi-pergerakan-harga-saham-menggunakan-algoritma-memetikaprediction-of-stock-market-price-movement-using-memetic-algorithm.html). Oleh karena perlu dilakukan pemodelan dan prediksi untuk mengetahui kondisi dan mempersiapkan strategi untuk menghadapi penurunan atau pelonjakan harga saham.
    
    Data yang digunakan adalah data pergerakan saham Microsoft inc dari tahun 2015 sampai 2021 dengan total data sebanyak 1511 data. Untuk menganalisis data sebanyak ini menggunakan bantuan program Jupyter Notebook dengan bahasa pemrograman python. Python telah banyak digunakan oleh para Data Scientist untuk mengolah data. Python juga bahasa pemrograman yang populer dan relatif mudah penggunaannya. Dalam proses analisa menggunakan konsep Machine Learning dimana mesin mempelajari data historik dari pergerakan saham sebelumnya untuk memprediksi harga saham dimasa depan.
    
## Business Understanding

Pada kasus ini seorang trader atau manajement investasi ingin memprediksi harga sebuah saham microsoft akan tetapi mereka menginginkan keuntungan yang cukup signifikan dan bisa menghindari loss. Mereka memiliki data dengan barbagai macam karakteristik pergerakan harga saham microsoft untuk memprediksi harga sahamnya di masa yang akan datang.

### Problem Statements

Berdasarkan latar belakang diatas, berikut rincian masalah yang dapat diselesaikan pada proyek ini :

- Bagaimana cara melakukan pra-pemrosesan data stock saham agar dapat digunakan untuk membuat model yang baik?
- Bagaimana cara membuat model _machine learning_ untuk memprediksi berdasarkan rentang waktu yang ada?

### Goals

Adapun tujuan dibuatnya proyek ini, yaitu:
- Melakukan pemrosesan data stock microsoft dengab baik agar dapat digunakan dalam membuat model.
- Membuat sebuah model _machine learning_ yang dapat memprediksi harga saham microsoft dikemudian hari.

### Solution statements
Solusi yang dapat diterapkan untuk proyek ini antara lain:

-   Pada tahap pra-pemrosesan data dapat dilakukan beberapa teknik, diantaranya :

    -   Mengisi data yang kosong dengan nilai metode ffil
    -   Mengatasi data outlier / pencilan menggunakan interquartil, yaitu membatasi kuartil atas dan kuartil bawah pada data.
    -   Melakukan **pembagian dataset** menjadi dua bagian dengan rasio 80% untuk data latih dan 20% untuk data uji
    -   Melakukan **normalisasi data** pada semua fitur data.

- Pada tahap pemodelan dilakukan teknik model time series dengan Long Term Short Memory (LSTM). Aplikasi time series sangat banyak dan luas, mulai dari prakiraan penjualan hingga prakiraan cuaca. Dalam keputusan yang melibatkan faktor ketidakpastian tentang masa depan, model time series telah ditemukan sebagai salah satu metode peramalan yang paling efektif.

## Data Understanding
Dataset yang saya gunakan pada kasus ini bersumber dari kaggle [Microsoft Stock](https://www.kaggle.com/vijayvvenkitesh/microsoft-stock-time-series-analysis) yang memiliki dimensi 1511 rows × 5 columns dengan variabel-variabelnya antara lain:

- Date : Tanggal transaksi
- Open : Harga Pembukaan
- High : Harga Tertinggi
- Low  : Harga Terendah
- Close : Harga Penutupan
- Volume : Jumlah Transaksi


## Visualization Data


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
