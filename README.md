# Laporan Proyek Machine Learning - Aditya Aprianto

## Domain Proyek

Domain proyek yang dipilih dalam proyek machine learning ini mengenai **Ekonomi dan Bisnis** dengan judul "Prediksi Harga Microsoft Stock".

- **Latar Belakang**

    Belakangan ini harga stock market, baik diluar maupun didalam negeri mengalami nilai yang cukup fluktuatif. Investasi melalui pasar modal atau bursa saham menjanjikan return yang lebih besar dibandingkan dengan instrumen konvensional baik dalam bentuk dividen(keuntungan dari hasil pembagian laba perusahaan) maupun capital gain (keuntungan yang diperoleh dari kelebihan nilai jual terhadap nilai beli saham). Pada dasarnya harga saham bergerak secara fluktuatif setiap harinya, oleh karena itu dibutuhkan sistem yang dapat memprediksi pergerakan harga saham tersebut untuk membantu para investor dalam melakukan analisis dan tindakan yang tepat sehingga resiko dapat diminimalisir dan return dapat dioptimalkan [[1](https://repository.telkomuniversity.ac.id/pustaka/65748/prediksi-pergerakan-harga-saham-menggunakan-algoritma-memetikaprediction-of-stock-market-price-movement-using-memetic-algorithm.html)]. Oleh karena perlu dilakukan pemodelan dan prediksi untuk mengetahui kondisi dan mempersiapkan strategi untuk menghadapi penurunan atau pelonjakan harga saham.
    
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


### Data Visualization

Dibawah ini merupakan hasil visualisasi grafik harga open vs price :

![alternate text](https://github.com/aditbest5/Image-Classification/blob/main/Open-close%20variable.png)

Dibawah ini merupakan hasil visualisasi grafik harga high vs low:

![alternate text](https://github.com/aditbest5/Image-Classification/blob/main/Screenshot%202021-11-18%20204538.png)

Dan yang terakhir adalah hasil visualisasi chart bar volume dari tahun ke tahun:

![alternate text](https://github.com/aditbest5/Image-Classification/blob/main/Screenshot%202021-11-18%20204611.png)



## Data Preparation
Seperti yang telah disebutkan di bagian solution statement, berikut tahapan-tahapan dalam melakukan pra-pemrosesan data:

- **Mengisi data yang kosong dengan nilai metode ffil**

    ![Data NaN](https://github.com/aditbest5/Image-Classification/blob/main/Missing%20Value.png)
    
     Sebenernya tidak perlu melakukan handling missing value karena data yang kosong tidak ada. Tetapi pada data tetap dilakukan handling missing value menggunakan metode ffil seperti gambar dibawah ini :
     
    ![Data NaN](https://github.com/aditbest5/Image-Classification/blob/main/Missing%20value%202.png)
    
 - **Mengatasi data outlier / pencilan menggunakan interquartil, yaitu membatasi kuartil atas dan kuartil bawah pada data**
 
  Nilai outliers (atau yang biasa disebut dengan nilai pencilan) merupakan suatu nilai yang tidak normal. Dalam kata lain, nilai tersebut bernilai jauh sekali dari pusat data. Nilai pencilan ini dapat menyebabkan distorsi terhadap nilai yang asli. 
Ada beberapa teknik untuk menangani outliers, antara lain:
1. Hypothesis Testing
2. Z-score method
3. IQR Method

Pada kasus ini, outliers akan dideteksi dengan teknik visualisasi data (boxplot). Kemudian, outliers akan ditangani dengan teknik IQR method. IQR adalah singkatan dari Inter Quartile Range. Kuartil dari suatu populasi adalah tiga nilai yang membagi distribusi data menjadi empat sebaran. Seperempat dari data berada di bawah kuartil pertama (Q1), setengah dari data berada di bawah kuartil kedua (Q2), dan tiga perempat dari data berada di kuartil ketiga (Q3). Dengan demikian interquartile range atau IQR = Q3 - Q1.

![alternate text](https://github.com/aditbest5/Image-Classification/blob/main/Outliers.png)

Gambar boxplot diatas tidak menunjukan outlier pada data. Handling outlier tetap dilakukan supaya mendapatkan data yang lebih bersih dan akurat. 

Berikut penggunaan IQR method :

![alternate text](https://github.com/aditbest5/Image-Classification/blob/main/Outliers%202.png)

Setelah melakukan IQR dapat dilihat bahwa data berkurang menjadi 1411 baris. Ini artinya perlakuan membatasi kuartil atas dan kuartil bawah pada data telah berhasil.

- **Melakukanpembagian dataset menjadi dua bagian dengan rasio 80% untuk data latih dan 20% untuk data uji**

Agar dapat menguji performa model pada data sebenarnya, maka perlu dilakukan pembagian dataset kedalam dua atau tiga bagian. Pada proyek ini dilakukan dua bagian saja yakni pada data latih dan data uji dengan rasio 80:20. Data latih dilakukan sepenuhnya untuk melatih model, sedangkan data uji merupakan data yang belum pernah dilihat oleh model dan diharapkan model dapat memiliki performa yang sama baiknya pada data uji seperti pada data latih. Pada bagian ini dipastikan juga pembagian label kategorikal haruslah sama banyak pada data latih dan data uji. Pembagian dataset dilakukan dengan modul [train_test_split](https://scikit-learn.org/0.24/modules/generated/sklearn.model_selection.train_test_split.html#sklearn.model_selection.train_test_split) dari scikit-learn.

- **Melakukan normalisasi data pada semua fitur data**

Tahap terakhir dengan melakukan standarisasi data. Hal ini akan membuat semua fitur numerik berada dalam skala data yang sama juga membuat komputasi dari pembuatan model dapat berjalan lebih cepat karena rentang datanya hanya antara 0-1. Untuk melakukan standarisasi data digunakan fungsi [MinMaxScaler](https://scikit-learn.org/0.24/modules/generated/sklearn.preprocessing.MinMaxScaler.html#sklearn.preprocessing.MinMaxScaler)


## Modeling
Setelah melakukan pra-pemrosesan data yang baik pada tahap modeling akan dilakukan dua hal, yakni tahap pembuatan model _Time Series_ dan pembuatan model yang dikembangkan.

- Model _Time Series_

Pada tahap ini saya menggunakan model _Time Series_ yang menunjukan format waktu dan label data. Time Series adalah rentetan kejadian atau pengamatan diambil secara sekuensial terhadap waktu. jika dilihat secara sekilah data statistik tidak berbeda jauh dengan model time series, namun, ada satu hal yang menjadi pembeda, yaitu dimensi waktu. Dimensi waktu ini berfungsi sebagai sesuatu yang biasa kita sebut feature dalam dunia machine learning. Feature ini dapat memberikan banyak kegunaan dalam pemrosesan dan analisis data, kita dapat mendapat insight, atau kesimpulan terhadap suatu observasi.

fungsi di bawah yang dapat merubah data menjadi format yang dapat diterima oleh model. Fungsi di bawah menerima sebuah series/atribut yang telah di konversi menjadi tipe numpy, lalu mengembalikan label dan atribut dari dataset dalam bentuk batch.

![alternate text](https://github.com/aditbest5/Image-Classification/blob/main/Windowing.png)

- Model _LSTM_
Selanjutnya untuk arsitektur model gunakan 2 buah layer LSTM. Ketika menggunakan 2 buah layer LSTM, perhatikan bahwa salah satu layer harus memiliki parameter return_sequences yang bernilai True.

![alternate text](https://github.com/aditbest5/Image-Classification/blob/main/LSTM.png)




## Evaluation

# Metrik evaluasi
Pada kasus time series ini saya hanya menggunakan 1 metrik yaitu _Mean Squared Error_ (MSE), alasan saya menggunkan  _Mean Squared Error_ adalah karena  _Mean Squared Error_ ini dapat menghitung eror yang dibuat pada model seperti kita mengevaluasi model regresi dan cukup mudah untuk dipahami serta cocok untuk masalah _Time Series_.  Rumus dari  MSE sendiri adalah sebagai berikut:

![alternate text](https://github.com/aditbest5/Image-Classification/blob/main/Rumus%20MSE.png)

 Pada gambar dibawah ini hasil dari pengukuran model yang dikembangkan dengan metriks _Mean Squared Error_ :
 
 ![alternate text](https://github.com/aditbest5/Image-Classification/blob/main/Hasil%20MSE.png)
 
 ![alternate text](https://github.com/aditbest5/Image-Classification/blob/main/Grafik%20train%20test.png)
 
 Dari hasil metriks evaluasi tersebut dapat digambarkan grafik perbandingan nilai hasil prediksi dengan nilai aslinya seperti berikut :
 
 ![alternate text](https://github.com/aditbest5/Image-Classification/blob/main/Predict%20model.png)
 
 Hasil nilai prediksi tersebut masih belum mendekati real valuenya dan cenderung menjauhi nilai real valuenya.
 
 
 ## _Referensi:_

[[1](https://repository.telkomuniversity.ac.id/pustaka/65748/prediksi-pergerakan-harga-saham-menggunakan-algoritma-memetikaprediction-of-stock-market-price-movement-using-memetic-algorithm.html)] Satria Bakti. PREDIKSI PERGERAKAN HARGA SAHAM MENGGUNAKAN ALGORITMA MEMETIKAPrediction of Stock Market Price Movement Using Memetic Algorithm (2014). https://repository.telkomuniversity.ac.id/pustaka/65748/prediksi-pergerakan-harga-saham-menggunakan-algoritma-memetikaprediction-of-stock-market-price-movement-using-memetic-algorithm.html.
