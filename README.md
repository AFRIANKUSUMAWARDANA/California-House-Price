📝 CAPSTONE 3 - CALIFORNIA HOUSING PRICE 🏡

MUHAMMAD AFRIAN KUSUMAWARDANA (JCDS 0708-BATCH BANDUNG)

Sumber data California Housing Prices

1. Business Problem Understanding

Konteks

California adalah salah satu negara bagian terpadat di Amerika Serikat, dengan pasar properti yang sangat kompleks. Harga properti di sini dipengaruhi oleh berbagai faktor, termasuk lokasi geografis, karakteristik properti, dan kondisi ekonomi makro. Kenaikan harga properti yang signifikan telah menciptakan tantangan bagi pembeli dan penjual.

Pernyataan Masalah

Pembeli dan penjual di California kesulitan dalam menilai harga pasar properti secara akurat. Ketidakakuratan ini dapat mengakibatkan pembeli membayar lebih atau kehilangan kesempatan, sementara penjual dapat menetapkan harga terlalu rendah atau terlalu tinggi.

Tujuan

Proyek ini bertujuan untuk mengembangkan model machine learning yang sangat akurat untuk memprediksi harga median rumah berdasarkan data sensus tahun 1990. Tujuannya adalah untuk mencapai akurasi setinggi mungkin dan kesalahan serendah mungkin. Selain itu, proyek ini juga bertujuan untuk mengidentifikasi faktor-faktor kunci yang memengaruhi harga rumah, memberikan wawasan dan rekomendasi praktis kepada pembeli dan penjual, serta memastikan keandalan model melalui validasi dan analisis residual.

Pendekatan Analitik

Pendekatan yang digunakan adalah menganalisis data untuk menemukan pola dan hubungan antara fitur-fitur yang memengaruhi harga rumah. Langkah-langkahnya meliputi eksplorasi dan pembersihan data, kemudian membangun model regresi untuk memprediksi harga median rumah.

Metrik Evaluasi

Metrik evaluasi yang digunakan adalah Root Mean Squared Error (RMSE), Mean Absolute Error (MAE), Mean Absolute Percentage Error (MAPE), dan R-squared (R²). Semakin kecil nilai RMSE, MAE, dan MAPE, semakin akurat modelnya. Nilai R² digunakan untuk mengukur seberapa baik model dapat menjelaskan variansi data, dengan nilai mendekati 1 menunjukkan model yang lebih baik.

2. Data Understanding

Konteks

Dataset California Housing Price ini berisi data sensus California tahun 1990. Dataset ini digunakan sebagai pengenalan dasar machine learning dan memerlukan langkah-langkah preprocessing karena belum dibersihkan. Setiap baris data merepresentasikan informasi tentang satu distrik di California.

Informasi Atribut

Berikut adalah atribut yang terdapat dalam dataset:
Atribut	Tipe Data	Deskripsi
longitude	Float	Koordinat bujur lokasi distrik.
latitude	Float	Koordinat lintang lokasi distrik.
housing_median_age	Integer	Usia median rumah di distrik tersebut.
total_rooms	Integer	Jumlah total ruangan di seluruh distrik.
total_bedrooms	Integer	Jumlah total kamar tidur di seluruh distrik.
population	Integer	Jumlah total penduduk di distrik tersebut.
households	Integer	Jumlah total rumah tangga di distrik tersebut.
median_income	Float	Pendapatan median per rumah tangga di distrik (dalam puluhan ribu dolar AS).
median_house_value	Float	Harga median rumah di distrik (dalam dolar AS) - variabel target.
ocean_proximity	Object	Kedekatan distrik dengan laut (variabel kategorikal).

3. Exploratory Data Analysis (EDA)

EDA dilakukan untuk memahami karakteristik dataset secara mendalam sebelum pemodelan. Analisis ini mencakup:

  . Exploratory Data Analysis (EDA)

EDA dilakukan untuk memahami karakteristik dataset secara mendalam sebelum pemodelan. Analisis ini mencakup:

    Analisis Univariat: Mengeksplorasi distribusi setiap variabel secara individual untuk mengidentifikasi outlier dan skewness.

        Terdapat beberapa outlier, terutama pada fitur housing_median_age dan median_house_value.

        Sebagian besar fitur numerik (seperti total_rooms, total_bedrooms, population, households) memiliki distribusi positif skewed.

        Terdapat 137 nilai yang hilang (missing values) pada fitur total_bedrooms.

    Analisis Bivariat: Memahami hubungan antara dua variabel.

        Korelasi positif yang kuat (0.68) ditemukan antara median_income dan median_house_value, menjadikannya fitur paling signifikan.

        Fitur ocean_proximity juga menunjukkan pengaruh signifikan, di mana distrik yang dekat dengan laut cenderung memiliki harga rumah yang lebih tinggi.

    Analisis Korelasi: Mengukur hubungan linear antar variabel.

        median_income memiliki korelasi positif kuat dengan median_house_value.

        Korelasi negatif kecil pada latitude menunjukkan kemungkinan harga rumah cenderung menurun ke arah utara.

    Analisis Geospasial Multivariat: Visualisasi data menggunakan longitude dan latitude untuk memahami bagaimana faktor geografis memengaruhi harga rumah.
