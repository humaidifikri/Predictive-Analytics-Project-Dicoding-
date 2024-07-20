# Laporan Proyek Machine Learning - Humaidi Fikri

## Domain Proyek

Game online adalah permainan video yang dimainkan melalui jaringan internet atau jaringan komputer lainnya, yang dapat diakses melalui berbagai perangkat seperti komputer, konsol game, dan perangkat mobile. Banyak perusahaan game online di dunia berlomba-lomba untuk membuat game yang unik dan menarik untuk mendapatkan perhatian pemain di seluruh dunia. Salah satu faktor yang mempengaruhi daya tarik game adalah tingkat kesulitan level yang dapat membuat pemain merasa tertantang atau frustrasi. Jika level experience pemain sulit meningkat, banyak pemain yang mungkin berhenti bermain. Oleh karena itu, pentingnya retensi pemain menjadi sangat jelas. Tanpa retensi yang baik, bahkan game yang paling menarik pun bisa kehilangan pemainnya dengan cepat, yang tidak hanya mengurangi basis pengguna aktif tetapi juga dapat merusak reputasi game.

Mengembangkan strategi untuk menjaga keterlibatan pemain, seperti penyeimbangan tingkat kesulitan, pemberian hadiah insentif, dan pembaruan konten secara berkala, adalah kunci untuk memastikan bahwa pemain tetap terlibat dan puas. Dengan fokus pada retensi pemain, pengembang dapat meningkatkan keberhasilan jangka panjang dan daya saing di industri game yang sangat kompetitif. Beberapa masalah yang dihadapi perusahaan game dalam menjaga retensi pemain termasuk kesulitan level yang tidak seimbang, kurangnya konten baru, dan kurangnya peluang untuk interaksi sosial dan membangun komunitas.

Dalam proyek ini, perusahaan akan menggunakan model Machine Learning untuk meningkatkan retensi pemain dalam game online. Model prediksi Machine Learning akan dianalisis dan dioptimalkan untuk memprediksi level engagement dan pengalaman pemain. Data pemain yang mencakup aktivitas dalam game, tingkat kesulitan yang dihadapi, dan interaksi sosial akan digunakan untuk melatih model. Model ini akan dievaluasi menggunakan Confusion Matrix dan Accuracy Metric untuk membandingkan performa prediksi. Tujuan utamanya adalah untuk mengidentifikasi pola yang menunjukkan kapan pemain cenderung berhenti bermain dan menyediakan solusi yang dapat menjaga mereka tetap terlibat.

Dengan pendekatan ini, diharapkan perusahaan dapat memberikan pengalaman bermain yang lebih baik dan lebih personal bagi setiap pemain, sehingga meningkatkan retensi pemain, pendapatan, dan loyalitas pemain. Model prediksi Machine Learning ini akan memungkinkan perusahaan untuk membuat keputusan yang lebih tepat tentang bagaimana menyesuaikan tingkat kesulitan, menyediakan konten baru yang relevan, dan mendorong interaksi sosial dalam game.

## Business Understanding

### Problem Statements
- Algoritma apa yang cocok untuk memprediksi engagement level pemain?
- Bagaimana cara menentukan hasil prediksi suatu algoritma Machine Learning dapat dikatakan bagus/akurat?

### Goals
- Meningkatkan retensi pemain dengan memprediksi engagement level pemain secara akurat, sehingga pengembang game dapat mengambil tindakan proaktif untuk mempertahankan pemain.
- Melakukan evaluasi dengan confusion matrix dari masing-masing algoritma untuk melihat akurasinya.

### Solution Statements
Solusi yang dapat dilakukan untuk memenuhi goals proyek ini adalah sebagai berikut:
 - Membuat 2 model Machine Learning yaitu dengan algoritma Extreme Gradient Boosting (XGBoost) dan RandomForest.
- Menggunakan metric accuracy score untuk menghitung akurasi dari kedua model tersebut.

## Data Understanding

Dataset yang digunakan pada proyek kali ini dibuat oleh [Rabie El Kharoua](https://www.kaggle.com/rabieelkharoua) yang di upload ke [Kaggle](https://www.kaggle.com/) pada Juni 2024. Sumber dataset: [Predict Online Gaming Behavior Dataset](https://www.kaggle.com/datasets/rabieelkharoua/predict-online-gaming-behavior-dataset/data).

Berdasarkan dataset tersebut terdapat informasi tipe data, jumlah kolom, dll. Berikut informasinya:
- **Features**:
	-   **PlayerID**: ID setiap pemain.
	-   **Age**: Umur pemain.
	-   **Gender**: Jenis kelamin pemain.
	-   **Location**: lokasi geografis pemain.
	-   **GameGenre**: Genre permainan yang telah di engage pemain.
	-   **PlayTimeHours**: Rata-rata berapa lama jam bermain.
	-   **InGamePurchases**: Indikasi apakah pemain melakukan pembayaran (0 = No, 1 = Yes).
	-   **GameDifficulty**: Kesulitan level dalam game.
	-   **SessionsPerWeek**: Angka berapa banyak sesi bermain perminggu.
	-   **AvgSessionDurationMinutes**: Rata-rata durasi bermain game dalam hitungan menit.
	-   **PlayerLevel**: Level terakhir pemain saat berada di game.
	-   **AchievementsUnlocked**: Angka berapa banyak pencapaian yang diraih pemain.
	-   **EngagementLevel**: Kategori level pemain yang meningkat ('High', 'Medium', 'Low').

- **Target Variable**:

	-   **EngagementLevel**: Indikasi level pemain dikategorikan sebagai: 'High', 'Medium', or 'Low'.
	
Teknik visualisasi yang digunakan kali ini adalah Boxplot, Histogram, dan Heatmap.
![info](https://github.com/humaidifikri/gambar_subs_dicoding/blob/main/info.PNG?raw=true)

Visualisasi fitur numerik untuk menemukan outliers/pencilan
![age](https://github.com/humaidifikri/gambar_subs_dicoding/blob/main/age.PNG?raw=true)

![ach](https://github.com/humaidifikri/gambar_subs_dicoding/blob/main/ach.PNG?raw=true)
![play](https://github.com/humaidifikri/gambar_subs_dicoding/blob/main/playtime.PNG?raw=true)

![sess](https://github.com/humaidifikri/gambar_subs_dicoding/blob/main/sess.PNG?raw=true)
![avg](https://github.com/humaidifikri/gambar_subs_dicoding/blob/main/dur.PNG?raw=true)
![lvl](https://github.com/humaidifikri/gambar_subs_dicoding/blob/main/lvl.PNG?raw=true)
Dari data numerik diatas kita tahu bahwa data numerk kita bersih dari outlier/pencilan.

Visualisasi fitur kategorik untuk mengetahui persebaran data.
![gnder](https://github.com/humaidifikri/gambar_subs_dicoding/blob/main/gender.PNG?raw=true)
![loc](https://github.com/humaidifikri/gambar_subs_dicoding/blob/main/country.PNG?raw=true)
![genre](https://github.com/humaidifikri/gambar_subs_dicoding/blob/main/genre.PNG?raw=true)
![diff](https://github.com/humaidifikri/gambar_subs_dicoding/blob/main/diffculty.PNG?raw=true)
Setelah mengetahui persebaran data kategorik mari kita lihat persebaran fitur numerik.
![uni_numerik](https://github.com/humaidifikri/gambar_subs_dicoding/blob/main/uni_numerik.PNG?raw=true)
![uni_numerik2](https://github.com/humaidifikri/gambar_subs_dicoding/blob/main/uni_numerik2.PNG?raw=true)
Terlihat fitur numerik juga tersebar merata. Mari lihat korelasi antar fitur numerik dengan target.
![hm](https://github.com/humaidifikri/gambar_subs_dicoding/blob/main/heatmap.PNG?raw=true)
Ada beberapa kolom yang mempunyai korelasi dengan target, bisa kita lihat dari fitur SessionPerWeek dan AvgSessionDurationMinutes yang terindikasi mempunyai korelasi kuat.

## Data Preparation
Tahapan-tahapan dalam Data Preparation:

- Mengonversi tipe data target menjadi menjadi tipe data numerik yang sebelumnya tipe data kategorik, karena mesin lebih cepat dalam bekerja daripada harus men-encode terlebih dahulu.
- Memisahkan Fitur (X) dan Target (y), langkah ini bertujuan untuk memisahkan fitur (predictor variables) yang akan digunakan untuk memprediksi target. Dalam kasus ini, kita menghapus kolom `PlayerID` dan `EngagementLevel` dari dataframe `df` untuk membentuk dataframe `X` yang hanya berisi fitur-fitur yang relevan untuk prediksi. `PlayerID` dihapus karena ID pemain biasanya adalah identifier unik yang tidak berpengaruh terhadap prediksi.`EngagementLevel` dihapus karena ini adalah target (label) yang ingin kita prediksi, sehingga tidak boleh termasuk dalam fitur. Dalam kasus ini, `y` diisi dengan kolom `EngagementLevel` dari dataframe `df`, yang menunjukkan tingkat keterlibatan pemain.
- Melakukan encoding untuk data bertipe kategorik. Encoding tidak hanya bertujuan untuk memudahkan proses memodelkan machine learning, tapi dengan adanya encoding dapat mempercepat waktu pemrosesan dan penyimpanan data[2].
-   Melakukan Split Data, dataset yang ada dibagi menjadi 2 bagian yaitu data latih dan data uji dengan rasio 80:20. Proses ini dilakukan dengan menggunakan modul  [train_test_split](https://scikit-learn.org/stable/modules/generated/sklearn.model_selection.train_test_split.html)  dari library scikit-learn.


## Modeling
Setelah melakukan data preparation, data yang sudah siap akan digunakan untuk membuat model, kali ini akan dibuat 2 model sebagai perbandingan.

1.   Membuat model dengan menggunakan algoritma  [RandomForest](https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.RandomForestRegressor.html). Cara kerja algoritma **RandomForest** dengan menggabungkan banyak pohon keputusan untuk menghasilkan prediksi yang lebih akurat dan stabil. Kelebihan dari menggunakan algoritma ini yaitu dapat mengatasi noise dan missing value serta dapat mengatasi data dalam jumlah yang besar, adapun kekurangan pada algoritma Random Forest yaitu interpretasi yang sulit dan membutuhkan tuning model yang tepat untuk data.

		    rf_clf = RandomForestClassifier(random_state=42) 
		    rf_clf.fit(X_train, y_train)

		Pada langkah ini, sebuah model **Random Forest** dibuat dan dilatih menggunakan data pelatihan (`X_train` dan `y_train`). Parameter `random_state=42` digunakan untuk memastikan hasil yang konsisten setiap kali kode dijalankan.


		    y_pred_rf = rf_clf.predict(X_test)
		    print(f'Akurasi: {accuracy_score(y_test, y_pred_rf)}')
	
		Setelah model dilatih, prediksi dilakukan pada data uji (`X_test`). Hasil prediksi kemudian dibandingkan dengan label asli (`y_test`) untuk menghitung akurasi menggunakan fungsi `accuracy_score`.
		

2.  Membuat model dengan menggunakan algoritma [XGBoost](https://xgboost.readthedocs.io/en/stable/index.html). Cara kerja algoritma **XGBoost** dengan cara menggabungkan beberapa model machine learning yang lemah menjadi satu model yang kuat. Proses ini dilakukan dengan cara mengurangi error dari setiap model yang dibangun, dengan cara menambahkan model baru yang dapat meminimalkan error yang ada[3]. XGBoost dirancang untuk efisiensi waktu dan sumber daya, sering kali lebih cepat dibandingkan dengan implementasi lain dari algoritma boosting, adapun kekurangan yaitu memiliki banyak hyperparameter yang perlu diatur dengan benar, yang bisa menjadi proses yang memakan waktu dan memerlukan keahlian. 

	     xgb_clf = XGBClassifier(objective='multi:softmax', seed=42)
         xgb_clf.fit(X_train,
                    y_train,
                    verbose=True,
                    early_stopping_rounds=20,
                    eval_metric='mlogloss',
                    eval_set=[(X_test, y_test)])
                
	Pada langkah ini, sebuah model **XGBoost** dibuat dan dilatih menggunakan data pelatihan (`X_train` dan `y_train`). Parameter `objective='multi:softmax'` menunjukkan bahwa model ini digunakan untuk klasifikasi multi-kelas. Parameter `seed=42` digunakan untuk memastikan hasil yang konsisten. Beberapa parameter tambahan yang digunakan:
		-   `verbose=True`: Menampilkan proses pelatihan.
		-   `early_stopping_rounds=20`: Menghentikan pelatihan lebih awal jika tidak ada peningkatan pada metrik evaluasi setelah 20 iterasi.
		-   `eval_metric='mlogloss'`: Menggunakan log loss sebagai metrik evaluasi.
		-   `eval_set=[(X_test, y_test)]`: Menggunakan data uji sebagai set evaluasi untuk memantau kinerja model selama pelatihan.
		
	     y_pred_xgb = xgb_clf.predict(X_test)
        print(f'Akurasi: {accuracy_score(y_test, y_pred_xgb)}')

	Setelah model XGBoost dilatih, prediksi dilakukan pada data uji (`X_test`). Hasil prediksi kemudian dibandingkan dengan label asli (`y_test`) untuk menghitung akurasi menggunakan fungsi `accuracy_score`.
	
	
## Evaluation
Proses evaluasi model pada proyek ini menggunakan metrik Confusion matrix dan Accuracy. Confusion matrix berbentuk tabel matriks yang menggambarkan kinerja model klasifikasi pada serangkaian data uji yang nilai sebenarnya diketahui. Confusion matrix akan memberi tahu seberapa baik model yang kita buat. Secara khusus confusion matrix juga memberikan informasi tentang TP, FP, TN, dan FN. Hal ini sangat berguna karena hasil dari klasifikasi umumnya tidak dapat diekspresikan dengan baik dalam satu angka saja[1].
![cm](https://miro.medium.com/v2/resize:fit:712/1*Z54JgbS4DUwWSknhDCvNTQ.png)  
Terdapat 4 istilah sebagai representasi hasil proses klasifikasi pada _confusion matrix_. Keempat istilah tersebut adalah _True Positive_ (TP), _True Negative_ (TN), _False Positive_ (FP) dan _False Negative_ (FN). Cara paling mudah untuk membacanya dengan cara melihat kolom TP dan TN saja. Jika keduanya mempunyai angka yang besar di bandingkan kolom disebelahnya maka hasil akurasi model kita sudah bagus. Accuracy menggambarkan seberapa akurat model dapat mengklasifikasikan dengan benar. Maka, accuracy merupakan rasio prediksi benar (positif dan negatif) dengan keseluruhan data.
![acc](https://miro.medium.com/v2/resize:fit:640/format:webp/1*Y1WWhTFtl3cHLjTHmvnvWA.png)
Dikarenakan pada kasus kali ini saya mempunyai 3 class, dan seperti ini hasil dari dua model tersebut:

1. **Random Forest**
![gambar akurasi rf](https://github.com/humaidifikri/gambar_subs_dicoding/blob/main/rf.PNG?raw=true)
![cm_rf](https://github.com/humaidifikri/gambar_subs_dicoding/blob/main/cm_rf.PNG?raw=true)

2. **XGBoost**
![acc_xgb](https://github.com/humaidifikri/gambar_subs_dicoding/blob/main/xgb.PNG?raw=true)
![hasil](https://github.com/humaidifikri/gambar_subs_dicoding/blob/main/hasil.PNG?raw=true)

Bisa kita lihat model **XGBoost** mempunyai akurasi lebih bagus dibandingkan model **RandomForest** dengan akurasi 0.92 atau 92%. Jika dilihat dari visualisasi confusion matrix model **XGBoost** lebih banyak memprediksi/menebak dibandingkan model **RandomForest**. Evaluasi ini menunjukkan bahwa model XGBoost berhasil mengidentifikasi pemain yang cenderung berhenti bermain dengan tingkat akurasi yang tinggi, membantu dalam memprediksi perilaku churn dengan lebih baik. Dengan memprediksi kapan pemain cenderung berhenti, perusahaan dapat mengambil tindakan preventif untuk meningkatkan retensi pemain. Model ini membantu dalam menjaga retensi pemain dengan memberikan wawasan tentang pola perilaku pemain, memungkinkan tim pengembangan game untuk menyesuaikan tingkat kesulitan, memberikan insentif yang tepat, dan melakukan pembaruan konten secara lebih efektif. Akurasi yang tinggi dari model ini memberikan kepercayaan bahwa keputusan yang diambil berdasarkan prediksi model akan lebih tepat dan efektif.

Selain itu, data dari model XGBoost dapat diintegrasikan ke dalam sistem game untuk memberikan notifikasi kepada pengembang ketika seorang pemain menunjukkan tanda-tanda akan berhenti bermain. Tim pengembangan dapat menggunakan hasil prediksi untuk melakukan intervensi yang lebih personal, seperti menawarkan insentif atau menyesuaikan konten game, sehingga meningkatkan pengalaman bermain dan loyalitas pemain. Implementasi model ini diharapkan dapat mengurangi churn dan meningkatkan pendapatan serta loyalitas pemain dalam jangka panjang. Dengan demikian, model prediksi Machine Learning yang dihasilkan tidak hanya memberikan hasil yang baik secara teknis, tetapi juga memiliki dampak nyata dan positif terhadap pemahaman bisnis dan strategi pengembangan game online. Oleh karena itu, model XGBoost dipilih karena lebih akurat dan tujuan kita telah tercapai berdasarkan goals yang ditetapkan.

### Referensi
[1] Confusion Matrix untuk Evaluasi Model pada Supervised Learning, https://ksnugroho.medium.com/confusion-matrix-untuk-evaluasi-model-pada-unsupervised-machine-learning-bc4b1ae9ae3f
[2] ENCODING in Machine Learning, https://medium.com/@nicholasgabrielkr/encoding-in-machine-learning-493b57fbb1c8
[3] # Algoritme XGBoost dengan Contohnya, https://dindaadi.medium.com/algoritme-xgboost-dengan-contohnya-28e958a3e2f6
