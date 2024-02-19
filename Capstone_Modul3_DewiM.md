# **E-Commerce Customer Churn**
### oleh: Dewi Maharani DP

## **Business Problem Understanding**

### Context Permasalahan
Dalam era digital saat ini, bisnis e-commerce menghadapi tantangan churn pelanggan, di mana pelanggan memilih untuk berhenti menggunakan layanan atau membeli produk. Mengatasi churn memerlukan strategi yang berorientasi data untuk mengidentifikasi dan mengintervensi pelanggan yang berisiko.

Dataset churn pelanggan menawarkan wawasan mendalam tentang faktor-faktor yang mempengaruhi keputusan pelanggan, seperti kepuasan, keluhan, dan preferensi pembelian. Memahami dan menganalisis data ini penting bagi perusahaan e-commerce untuk mengidentifikasi strategi yang efektif dalam mempertahankan pelanggan dan mengoptimalkan layanan, sehingga meningkatkan kepuasan dan loyalitas pelanggan.


### Problem Statement
Bagaimana cara mengidentifikasi pelanggan yang berpotensi churn sehingga strategi retensi yang tepat dapat diterapkan untuk meningkatkan retensi pelanggan dan mengurangi tingkat churn?

### Goals
1. Memprediksi pelanggan yang berisiko tinggi untuk churn.
2. Mengidentifikasi faktor-faktor utama yang berkontribusi terhadap churn pelanggan.
3. Mengembangkan strategi retensi pelanggan berdasarkan insight dari model prediksi.

### Analytic Approach
Menggunakan analisa data untuk menemukan pola yang membedakan pelanggan akan churn atau tidak. Kemudian melakukan prediksi menggunakan supervised machine learning yang akan mengevaluasi beberapa model klasifikasi yang memberikan prediksi paling akurat pada seorang pelanggan yang akan churn.

### Metric Evaluation
![image.png](attachment:image.png)

Fokus utama yaitu pelanggan yang akan berhenti berlangganan, maka target yang kita tetapkan adalah sebagai berikut:

Target :

0 : Tidak berhenti berlangganan  
1 : Berhenti berlangganan (churn)

Confusion Metrix Term:

*   True Positive: customernya aktualnya churn dan diprediksi churn
*   True Negative: customernya aktualnya tidak churn dan diprediksi tidak churn
*   False Negative: customernya aktualnya churn dan diprediksi tidak churn
*   False Positive: customernya aktualnya tidak churn dan diprediksi churn

Type 1 error : False Negatif  
* Konsekuensi: Pelanggan benar-benar churn
* Efek samping: Adanya cost customer acquistion untuk menggantikan customer yang telah churn.

Type 2 error : False Positif  
* Konsekuensi: Salah target treatment pada pelanggan yang tidak churn tapi diprediksi churn
* Efek samping: perusahaan kehilangan waktu dan sumber daya untuk promosi

sebisa mungkin membuat model yang dapat mengurangi pelanggan churn dari perusahaan tanpa membuat kesalahan dalam pemberian treatment atau program yang direncanakan perusahaan. Kita ingin sebanyak mungkin prediksi kelas positif yang benar, dengan sesedikit mungkin prediksi false positive.

### Data Understanding
Data berisi informasi tentang interaksi pelanggan dengan e-commerce. Data ini berisi atribut yang dapat digunakan untuk memprediksi pelanggan yang akan churn.

**Attributes Information**  

- **Tenure**: Lama waktu pelanggan bersama perusahaan.
- **WarehouseToHome**: Jarak dari gudang ke rumah pelanggan.
- **NumberOfDeviceRegistered**: Jumlah perangkat yang terdaftar untuk pelanggan tertentu.
- **PreferedOrderCat**: Kategori pesanan yang dipilih pelanggan dalam satu bulan terakhir.
- **SatisfactionScore**: Skor kepuasan pelanggan terhadap layanan.
- **MaritalStatus**: Status pernikahan pelanggan.
- **NumberOfAddress**: Jumlah alamat yang didaftarkan untuk pengguna atau pelanggan.
- **Complain**: Apakah ada keluhan yang diajukan dalam satu bulan terakhir.
- **DaySinceLastOrder**: Hari terakhir pemesanan oleh pelanggan.
- **CashbackAmount**: Jumlah cashback rata-rata dalam satu bulan terakhir.
- **Churn**: Identifikasi churn, menunjukkan apakah pelanggan tersebut churn atau tidak.





## **Analysis**

Analisis yang Anda berikan telah memberikan wawasan yang sangat berguna tentang dataset dan potensi faktor-faktor yang mempengaruhi churn pelanggan dalam bisnis e-commerce. Berikut adalah beberapa poin kunci yang dapat disimpulkan dari analisis Anda:

1. **Analisis Variabel Numerik**:
   - Variabel seperti Tenure, Complain, dan CashbackAmount memiliki korelasi yang signifikan dengan Churn, menunjukkan pentingnya faktor-faktor ini dalam memprediksi perilaku churn pelanggan.
   - Distribusi variabel-numerik menunjukkan variasi yang signifikan, yang menunjukkan pentingnya dalam memahami karakteristik pelanggan.

2. **Analisis Variabel Kategorikal**:
   - Uji chi-square menunjukkan bahwa semua variabel kategorikal memiliki korelasi yang signifikan dengan Churn, menegaskan pentingnya variabel-variabel ini dalam pemodelan.
   - Beberapa kategori, seperti Complain dan PreferedOrderCat_Mobile Phone, menunjukkan korelasi positif yang kuat dengan Churn.

3. **Benchmarking Model**:
   - Model XGBoost dan Random Forest menunjukkan performa yang sangat baik dalam memprediksi churn, dengan skor ROC-AUC yang sangat tinggi.
   - Tuning hyperparameter meningkatkan performa model Random Forest, menjadikannya pilihan terbaik dalam konteks ini.

4. **Interpretasi Fitur Penting**:
   - Fitur seperti Tenure, CashbackAmount, dan Complain muncul sebagai fitur-fitur paling penting dalam memprediksi churn, menunjukkan faktor-faktor yang mungkin mempengaruhi keputusan pelanggan.

5. **Rekomendasi untuk Tindakan Lanjut**:
   - Berdasarkan analisis, perusahaan dapat memfokuskan upaya mereka pada peningkatan layanan dan insentif, serta manajemen keluhan pelanggan.
   - Model prediktif, terutama Random Forest yang telah dioptimalkan, dapat digunakan untuk mengidentifikasi pelanggan yang berisiko churn dan mengambil tindakan pencegahan atau retensi yang sesuai.


## Kesimpulan
- Analisis menunjukkan bahwa faktor seperti Tenure, Complain, CashbackAmount, dan PreferedOrderCat_Mobile Phone memiliki pengaruh signifikan terhadap kecenderungan pelanggan untuk churn. Ini menunjukkan pentingnya memahami perilaku pelanggan dan faktor-faktor yang mempengaruhi kepuasan mereka.
- Model Random Forest dan XGBoost berhasil mengidentifikasi pelanggan berisiko tinggi churn dengan performa yang sangat baik, ditunjukkan oleh skor ROC-AUC Random Forest setelah tuning hyperparameter mencapai skor ROC-AUC sekitar 0.9572, dan XGBoost mencapai skor ROC-AUC sekitar 0.9448, meskipun sedikit lebih rendah dibandingkan Random Forest.

## Rekomendasi
- **Implementasi Model**: Gunakan model Random Forest dan XGBoost untuk mengidentifikasi pelanggan berisiko churn secara real-time, memungkinkan intervensi tepat waktu.
- **Waktu Penggunaan Model**: Model paling dipercaya ketika digunakan pada pelanggan dengan profil serupa dengan data pelatihan. Sebelum diterapkan pada segmen pelanggan yang berbeda, validasi model diperlukan.
- **Dampak Implementasi**: Implementasi model ini diharapkan dapat meningkatkan retensi pelanggan dengan mengurangi churn. Strategi retensi yang ditargetkan berdasarkan insight dari model dapat meningkatkan kepuasan dan loyalitas pelanggan.
- **Batasan dan Perbaikan**: Salah satu batasan proyek adalah potensi bias pada data pelatihan yang mungkin tidak mencakup semua segmen pelanggan. Untuk memperbaiki dan meningkatkan proyek, pertimbangkan penambahan data dari segmen pelanggan yang lebih beragam dan update model secara berkala untuk menjaga relevansinya.

### Langkah Lanjut
- **Analisis Lebih Lanjut**: Lakukan analisis segmentasi pelanggan untuk memahami kebutuhan dan perilaku pelanggan secara lebih detail.
- **Pengujian Model Secara Berkala**: Secara berkala uji model dengan data baru untuk memastikan keakuratannya tetap terjaga.
- **Eksplorasi Teknik Advanced**: Pertimbangkan penggunaan teknik machine learning yang lebih advanced atau deep learning untuk meningkatkan akurasi model.
