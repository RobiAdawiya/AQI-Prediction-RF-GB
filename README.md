# Komparasi Algoritma Ensemble untuk Prediksi Air Quality Index (AQI) Jakarta (2010-2023)

## Ringkasan Proyek
Proyek ini bertujuan untuk mengkomparasi kinerja dua algoritma Ensemble Learning terkemuka—Random Forest (RF) dan Gradient Boosting (GB) dalam mengklasifikasikan Indeks Kualitas Udara (AQI) di DKI Jakarta. Mengingat isu polusi udara yang kritis di Jakarta , model prediksi akurat sangat esensial untuk perencanaan dan rekomendasi kebijakan lingkungan.
Hasil Utama: Kedua model mencapai akurasi klasifikasi sangat tinggi (0.96-0.97 atau 96-97%), dengan Random Forest menunjukkan akurasi yang sedikit lebih baik (97.51%) dibandingkan Gradient Boosting (97.41%) pada data uji.

## Metodologi dan Teknik Utama
1. Data Understanding & Preprocessing
   Dataset: Menggunakan data AQI sekunder dari Kaggle di 5 stasiun DKI Jakarta, mencakup periode 2010 hingga 2023 dengan total 4625 record5.
   Variabel independen (5 Polutan): PM10, SO2, CO, O3, NO266, variabel dependen: category_encoded (Kelas 0=Baik hingga 4=Berbahaya).
   Missing Value Imputation: Menangani nilai hilang (misalnya 159 missing values pada PM10) menggunakan Jarak Mahalanobis. Pendekatan ini dipilih untuk mempertahankan struktur korelasi dalam data multivariat.
   Outlier Detection: Menggunakan visualisasi Boxplot dan metode Interquartile Range (IQR) untuk mengidentifikasi outliers pada variabel polutan.
3. Pemodelan dan Tuning.
   Algoritma: Random Forest (RF) dan Gradient Boosting (GB) Classifier.
   Hyperparameter Optimization: Menggunakan Grid Search Cross-Validation (CV=5) pada data latih untuk menemukan kombinasi parameter terbaik bagi kedua model.RF Terbaik: max_depth=20, n_estimators=10013.GB Terbaik: learning_rate=0.3, max_depth=10, n_estimators=5014.3.
   Evaluasi Kinerja (Performance Metrics) Random Forest menunjukkan metrik performa testing yang sedikit lebih unggul. Namun, Mean Cross-Validation Score Gradient Boosting sedikit lebih tinggi, menunjukkan potensi generalisasi yang lebih stabil
4. Key Insight: Feature Important
   Konsentrasi Ozon (O3) adalah variable polutan paling dominan dan krusial dalam memprediksi indeks kualitas udara dengan importance score pada model random forest sangat dominan yaitu melebihi 0.6. Temuan ini memberikan wawasan bagi stakeholder bahwa Ozon harus menjadi fokus utama dalam perencanaan dan pengelolaan kualitas udara di Jakarta
