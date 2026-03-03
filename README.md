# Saudi-Arabia-Used-Car-Price-Prediction-with-Machine-Learning

Kendaraan telah menjadi kebutuhan sehari-hari bagi banyak orang, baik untuk menunjang aktivitas pekerjaan, mobilitas keluarga, maupun kebutuhan bisnis. Seiring dengan meningkatnya kebutuhan mobilitas, permintaan terhadap kendaraan pribadi pun terus bertumbuh. Namun, tidak semua konsumen memiliki kemampuan finansial untuk membeli mobil baru, sehingga opsi membeli mobil bekas menjadi alternatif yang lebih terjangkau dan rasional secara ekonomi.

Pasar mobil bekas berkembang pesat karena menawarkan variasi harga yang lebih fleksibel, pilihan model yang beragam, serta depresiasi harga yang lebih stabil dibandingkan mobil baru. Meskipun demikian, dinamika pasar mobil bekas cenderung lebih kompleks karena harga kendaraan sangat dipengaruhi oleh berbagai faktor seperti usia kendaraan, kondisi penggunaan, merek, tipe, dan lokasi penjualan. Ketidakteraturan dalam penentuan harga sering kali menyebabkan ketimpangan antara nilai pasar yang wajar dan harga yang ditawarkan oleh penjual.

Syarah merupakan situs jual beli mobil bekas di Arab Saudi yang mempertemukan penjual dan pembeli kendaraan melalui platform digital. Syarah.com memberikan pelayanan maksimal pada situs dan aplikasi yang mereka buat seperti jenis dan merek mobil, variasi harga, dan juga lokasi kendaraan dapat diakses semua melalui situs dan aplikasi resmi. karena dalam operasionalnya, setiap penjual dapat mengunggah spesifikasi kendaraan seperti tipe mobil, merek, jenis transmisi, kelengkapan fitur, tahun produksi, kapasitas mesin, serta jarak tempuh. Informasi tersebut menjadi dasar utama dalam menentukan harga jual kendaraan. Maka dari itu pelanggan atau pembeli pada situs Syarah.com mendapatkan informasi lengkap dari seluruh kendaraan yang tersedia pada situs dan aplikasi.

__________________________________________________________________________________________________________________________________________________________________
## **Business Problem Statement**
Marketplace mobil bekas seperti Syarah pastinya memiliki permasalahan, salah satunya adalah proses penentuan harga kendaraan. Ketidaktepatan dalam menetapkan acuan harga berpotensi menyebabkan kendaraan terlalu mahal sehingga sulit terjual, atau terlalu murah sehingga merugikan penjual. Kondisi ini tidak hanya mempengaruhi efisiensi waktu terhadap pemilihan harga, tetapi juga berdampak pada dan performa bisnis marketplace secara keseluruhan. 

Dengan banyaknya faktor yang memengaruhi harga mobil bekas—seperti usia kendaraan, jarak tempuh, merek, tipe kendaraan, kapasitas mesin, serta wilayah penjualan—diperlukan pendekatan berbasis data yang mampu mengidentifikasi pola harga pasar secara objektif dan konsisten.

__________________________________________________________________________________________________________________________________________________________________
## **Stakeholders**
**Marketplace Team**

Spesifiknya adalah Marketplace Management & Marketplace Developers

__________________________________________________________________________________________________________________________________________________________________
## **Goals**
Membangun model machine learning yang mampu memprediksi harga mobil bekas berdasarkan karakteristik kendaraan, sehingga dapat digunakan sebagai sistem rekomendasi harga yang membantu seller menetapkan harga yang optimal dan kompetitif.

__________________________________________________________________________________________________________________________________________________________________
## **Analytical Approach**
Untuk menjawab permasalahan penentuan harga kendaraan di marketplace seperti Syarah, pendekatan yang digunakan dalam proyek ini adalah supervised machine learning dengan metode regresi, karena variabel target yang diprediksi berupa nilai numerik kontinu (Price).

Tahapan analisis dimulai dari eksplorasi data untuk memahami distribusi harga dan karakteristik kendaraan, kemudian dilanjutkan dengan proses data preprocessing seperti encoding pada variabel kategorikal, scaling pada variabel numerik, serta feature engineering. Pada tahap feature engineering, ditambahkan variabel Car_Age untuk merepresentasikan usia kendaraan dan Mileage_Per_Year untuk menggambarkan intensitas penggunaan kendaraan secara lebih representatif dibandingkan hanya melihat total mileage.

Selanjutnya dilakukan proses pemodelan dengan membandingkan beberapa algoritma regresi untuk menemukan model dengan performa terbaik. Setelah model terbaik diperoleh, dilakukan hyperparameter tuning guna mengoptimalkan performa serta mengurangi risiko overfitting. Evaluasi akhir dilakukan pada data testing untuk memastikan model memiliki kemampuan generalisasi yang baik terhadap data baru.

__________________________________________________________________________________________________________________________________________________________________
## **Evaluation Metrics**
Tujuan utama proyek ini adalah memprediksi harga mobil bekas secara akurat dan stabil, Evaluasi model dilakukan menggunakan beberapa metrik regresi berikut:

1. Root Mean Squared Error (RMSE)
RMSE digunakan untuk mengukur rata-rata besar kesalahan prediksi dalam satuan harga yang sama dengan target. Metrik ini sensitif terhadap error besar, sehingga cocok digunakan dalam konteks pricing, di mana kesalahan prediksi yang terlalu jauh dari harga pasar dapat berdampak signifikan terhadap keputusan bisnis.

2. Mean Absolute Error (MAE)
MAE mengukur rata-rata selisih absolut antara harga aktual dan harga prediksi. Metrik ini memberikan gambaran yang lebih mudah diinterpretasikan karena menunjukkan rata-rata kesalahan harga yang terjadi tanpa memperbesar pengaruh outlier.

3. Mean Absolute Percentage Error (MAPE)
MAPE digunakan untuk memahami besar kesalahan dalam bentuk persentase terhadap harga aktual. Metrik ini membantu stakeholder memahami seberapa besar deviasi harga model dibandingkan nilai sebenarnya dalam konteks persentase, yang lebih intuitif secara bisnis.

Selain itu, dilakukan evaluasi terhadap gap antara performa training dan testing untuk memastikan model tidak mengalami overfitting. Model yang baik diharapkan memiliki error yang rendah sekaligus stabil pada data baru, sehingga dapat diandalkan saat diimplementasikan dalam sistem produksi.

__________________________________________________________________________________________________________________________________________________________________
## **Data Understanding**
- Dataset merupakan data listing mobil bekas yang dijual pada lokasi asal Saudi Arabia.
- Setiap baris data merepresentasikan informasi terkait kendaraan yang dijual.

**Attributes Information**

| **Attribute** | **Data Type** | **Description** |
| --- | --- | --- |
| Type | Object | Type of used car |
| Region | Object | Region of used car |
| Make | Object | The company name |
| Gear_Type | Object | Gear type size of used car |
| Origin| Object | Origin of used car |
| Options| Object | Options of used car |
| Year | Integer | Manufacturing year |
| Engine_Size | Float | The engine size of used car |
| Mileage | Integer | Mileage |
| Negotiable | Object | Negotiable in dollars |
| Price | Integer | Amount of used car |
__________________________________________________________________________________________________________________________________________________________________
## **Conclusion** 
Secara keseluruhan, model machine learning yang dikembangkan menggunakan XGBoost Regressor menunjukkan performa yang cukup baik dalam memprediksi nilai target. Model mampu menangkap pola utama dalam data dengan tingkat error yang relatif rendah, Hal ini ditunjukkan dari nilai evaluasi RMSE (Root Mean Squared Error) yang menampilkan error sebesar 6.32%. karena ada jarak antara data test dan data train yaitu RMSE Train : 21939.838467955957, RMSE Test : 23327.558294858038. Sehingga mengindikasikan bahwa rata-rata kesalahan prediksi model masih dalam batas yang dapat diterima.

Proses benchmarking juga memperlihatkan bahwa XGBoost merupakan algoritma dengan performa terbaik dibandingkan model lain yang diuji. Namun, hasil hyperparameter tuning menunjukkan bahwa peningkatan kompleksitas model tidak selalu menghasilkan performa yang lebih baik. Dalam studi ini, model baseline justru memberikan hasil evaluasi yang lebih optimal dibandingkan model hasil tuning.

Dari sisi diagnostik, ditemukan bahwa model masih memiliki keterbatasan dalam memprediksi nilai pada rentang yang tinggi, yang ditunjukkan oleh heteroskedasticity.Hal ini menunjukkan bahwa model belum sepenuhnya mampu menangkap pola kompleks pada rentang nilai ekstrem.

Dengan demikian, dapat disimpulkan bahwa model sudah cukup robust dan layak digunakan sebagai baseline. Namun, masih terdapat ruang untuk perbaikan, khususnya dalam meningkatkan akurasi prediksi pada nilai tinggi serta mengurangi variasi error.

__________________________________________________________________________________________________________________________________________________________________
## **Recomendation**
Berdasarkan hasil diatas, terdapat beberapa rekomendasi yang dapat dilakukan untuk pengembangan lebih lanjut adalah sebagai berikut:

**1. Model Improvement**
- Menerapkan transformasi pada variabel target, seperti log transformation, untuk mengurangi skewness dan mengatasi heteroskedasticity
- Mengeksplorasi algoritma lain yang lebih adaptif terhadap distribusi data kompleks, seperti LightGBM atau CatBoost
- Melakukan tuning hyperparameter dengan ruang pencarian yang lebih luas dan terarah

**2. Feature Engineering**
- Melakukan feature selection untuk mengurangi noise dan meningkatkan interpretabilitas model

**3. Error & Data Handling**
- Melakukan analisis lebih lanjut terhadap outlier, khususnya pada nilai target tinggi
- Menggunakan pendekatan robust modeling untuk mengurangi sensitivitas terhadap data ekstrem
- Mengevaluasi distribusi residual untuk memastikan asumsi model lebih terpenuhi
__________________________________________________________________________________________________________________________________________________________________
