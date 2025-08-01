# Attrition Prediction and Monitoring System for Human Resources Decision Support

## Business Understanding

Jaya Jaya Maju adalah perusahaan multinasional yang telah beroperasi sejak tahun 2000 dan memiliki lebih dari 1.000 karyawan yang tersebar di berbagai wilayah. Meski telah tumbuh menjadi perusahaan besar, Jaya Jaya Maju menghadapi tantangan serius dalam pengelolaan sumber daya manusianya. Salah satu indikator utama dari permasalahan ini adalah meningkatnya attrition rate atau tingkat keluar masuk karyawan, yang telah melampaui angka 10%.

Tingginya attrition rate berdampak pada produktivitas, biaya rekrutmen, pelatihan ulang, serta stabilitas tim dan proyek yang sedang berjalan. Oleh karena itu, dibutuhkan langkah strategis untuk mengidentifikasi faktor-faktor penyebab utama attrition dan membuat sistem monitoring berbasis dashboard yang mampu memberikan gambaran menyeluruh tentang kondisi karyawan di berbagai dimensi.

### Permasalahan Bisnis

1. **Tingginya tingkat attrition karyawan** (>10%) yang dapat mengganggu kinerja dan stabilitas organisasi.

2. **Tidak adanya pemantauan data karyawan yang komprehensif** untuk memahami penyebab utama dari keluarnya karyawan.

3. **Sulitnya mengidentifikasi faktor-faktor penting** seperti:
   - Kepuasan kerja (`JobSatisfaction`, `EnvironmentSatisfaction`, `RelationshipSatisfaction`)
   - Beban kerja dan keseimbangan hidup (`WorkLifeBalance`, `OverTime`)
   - Gaji dan kenaikan upah (`MonthlyIncome`, `PercentSalaryHike`)
   - Status pernikahan, usia, dan pengalaman kerja

4. **Tidak tersedianya visualisasi data dalam bentuk dashboard** untuk mendukung pengambilan keputusan manajerial secara cepat dan berbasis data.

5. **Kurangnya sistem peringatan dini (early warning system)** yang dapat memprediksi potensi karyawan yang akan keluar.

### Cakupan Proyek

Cakupan proyek ini mencakup seluruh proses analisis data hingga evaluasi model prediksi tingkat attrition pada karyawan perusahaan **Jaya Jaya Maju**. Adapun cakupan kegiatan dalam proyek ini meliputi:

### 1. Persiapan
- Menyiapkan library yang dibutuhkan.
- Menyiapkan dan memuat dataset yang akan digunakan.

### 2. Data Understanding
- **Exploratory Data Analysis (EDA)**:
  - *Univariate Analysis*: Analisis distribusi masing-masing fitur.
  - *Bivariate Analysis*: Analisis hubungan antar fitur dan target `Attrition`.

### 3. Data Preparation / Preprocessing
- Menghapus outlier.
- Seleksi fitur yang relevan.
- Encoding variabel kategorikal.
- Pembagian data menjadi *train* dan *test set*.
- Standarisasi fitur numerik.
- Penyeimbangan data menggunakan teknik **SMOTE**.

### 4. Modeling
Pembangunan model klasifikasi untuk memprediksi `Attrition` menggunakan beberapa algoritma:
- **Random Forest**
- **Support Vector Machine (SVM)**
- **Naive Bayes (NB)**
- **XGBoost (XGB)**

### 5. Evaluation
- Evaluasi model dilakukan sebelum dan sesudah tuning **Hyperparameter**.
- Perbandingan performa antar model untuk memilih model terbaik.

---

Proyek ini akan menghasilkan model prediksi yang dapat membantu tim HR dalam mengidentifikasi karyawan berisiko tinggi untuk keluar, serta menyediakan dasar pengambilan keputusan yang lebih tepat.

### Persiapan

Sumber data: [Click Here!](https://github.com/dicodingacademy/dicoding_dataset/tree/main/employee)

# Setup Environment

Lingkungan pengembangan dan analisis proyek ini menggunakan Python serta tool visualisasi Metabase. Berikut langkah-langkah setup yang perlu dilakukan:

---

## **1. Membuat dan Mengaktifkan Virtual Environment (venv)**

Sebelum menginstal dependensi, pastikan Anda membuat dan mengaktifkan virtual environment untuk proyek ini. 

### Langkah-langkah:

1. **Buat Virtual Environment**  
   Masuk ke direktori proyek Anda menggunakan terminal, lalu buat virtual environment dengan perintah berikut:

   python -m venv venv

Anda bisa mengganti nama `venv` dengan nama lain jika diinginkan.

2. **Aktifkan Virtual Environment**

- **Untuk Windows**, jalankan perintah:
  ```
  .\venv\Scripts\activate
  ```

- **Untuk macOS/Linux**, jalankan perintah:
  ```
  source venv/bin/activate
  ```

3. Setelah virtual environment aktif, Anda akan melihat nama `venv` muncul di awal prompt terminal Anda.

---

## **2. Install Library Python**

Untuk memastikan semua dependensi Python terinstal, gunakan file `requirements.txt` yang telah disediakan. Jalankan perintah berikut di terminal:

pip install -r requirements.txt


---

## **3. Menjalankan Business Dashboard dengan Metabase**

Metabase digunakan untuk membuat dashboard interaktif yang menampilkan insight dari data karyawan.

### 🔧 Langkah Setup Metabase:

1. **Tarik Image Metabase menggunakan Docker:**

   docker pull metabase/metabase:v0.46.4


2. **Jalankan Container Metabase:**

   docker run -p 3001:3000 --name submisson metabase/metabase


3. **Akses Metabase melalui Browser:**

   http://localhost:3001


4. **Login ke Metabase:**

   Username: root@mail.com
   Password: root123
---

## **4. Pengujian Model**

Model yang telah dilatih (xgb_model.pkl) diuji menggunakan notebook `test_model.ipynb`.

### 🧪 Langkah Pengujian:

1. **Pastikan file berikut tersedia:**

- `xgb_model.pkl`: Model XGBoost hasil training
- `test_model.ipynb`: Notebook untuk evaluasi dan testing

2. **Jalankan `test_model.ipynb` di Jupyter Notebook atau Google Colab. Pastikan file yang disebutkan sebelumnya berada dalam satu folder yang sama.**  
Sebagai contoh, pada proyek ini menggunakan data dari `X_test` dan `y_test` pada model yang dibuat untuk bahan uji coba. 




## Business Dashboard

Business dashboard yang dibuat berfungsi sebagai alat bantu visualisasi untuk memahami faktor-faktor utama yang mempengaruhi attrition (keluarnya karyawan) di perusahaan Jaya Jaya Maju. Dashboard ini dibuat menggunakan **Metabase**, dan menyajikan berbagai metrik penting seperti:

- Tingkat attrition berdasarkan Job Role, Marital Status, dan Overtime
- Distribusi kepuasan kerja (Environment, Job, dan Relationship)
- Analisis faktor Work-Life Balance, Monthly Rate, dan Percent Salary Hike

Dashboard ini membantu tim HR dalam:
- Memantau kondisi ketenagakerjaan secara real-time
- Mengidentifikasi potensi risiko attrition
- Menyusun strategi retensi yang lebih efektif

> 💡 **Akses Dashboard**: *(Masukkan link jika tersedia, contoh: http://localhost:3001/dashboard)*  
> Login:  
> **Username**: `root@mail.com`  
> **Password**: `root123`

## Conclusion

Berdasarkan hasil analisis data dan visualisasi yang telah dilakukan, ditemukan bahwa beberapa faktor memiliki pengaruh besar terhadap tingkat attrition karyawan, di antaranya:

- **Job Role**: Distribusi attrition tidak merata antar posisi.
- **Marital Status**: Karyawan lajang (single) cenderung memiliki tingkat attrition lebih tinggi.
- **Overtime**: Karyawan yang sering lembur memiliki kecenderungan lebih tinggi untuk keluar.
- **Work-Life Balance**: Ketidakseimbangan antara pekerjaan dan kehidupan pribadi berkontribusi signifikan.
- **Kompensasi** seperti MonthlyRate dan PercentSalaryHike juga ikut mempengaruhi keputusan karyawan.

Selain itu, dilakukan juga **pemodelan prediktif** untuk memproyeksikan kemungkinan attrition menggunakan algoritma XGBoost, yang dapat membantu HR dalam pengambilan keputusan berbasis data.

### Rekomendasi Action Items (Optional)

- 🔍 **Audit Internal** terhadap posisi pekerjaan dengan attrition tinggi untuk memahami penyebabnya lebih lanjut.
- 💬 **Fokus pada retensi karyawan lajang**, misalnya dengan program engagement dan work-life balance yang lebih baik.
- ⏰ **Evaluasi kebijakan lembur** untuk mencegah burnout.
- 📈 **Optimasi sistem kompensasi** dan kenaikan gaji berbasis performa.
- 🧠 **Implementasi sistem peringatan dini** berbasis model prediksi untuk mengidentifikasi karyawan berisiko tinggi keluar.
