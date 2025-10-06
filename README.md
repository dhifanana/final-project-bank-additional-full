# LINK TABLEAU
https://public.tableau.com/views/Bank-additional/Dashboard1?:language=en-US&publish=yes&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link

![Visualisasi Dataset](/image.jpeg)


# 📊 Bank Marketing Term Deposit Prediction

## 📌 Deskripsi Proyek
Proyek ini bertujuan untuk **memprediksi apakah nasabah akan setuju untuk membuka deposito berjangka** berdasarkan data kampanye pemasaran bank. Dataset yang digunakan berasal dari **Bank Marketing Dataset (UCI/Kaggle)** yang berisi informasi demografis nasabah, riwayat pinjaman, serta hasil kontak pemasaran.

Target variabel:  
- `y = yes` → nasabah setuju membuka deposito  
- `y = no` → nasabah tidak setuju  

---

## 📂 Struktur Notebook
Notebook ini berisi tahapan berikut:
1. **Import Library & Load Dataset**  
   Membaca dataset dan melakukan pembersihan data.  

2. **Exploratory Data Analysis (EDA)**  
   - Distribusi fitur numerik & kategorikal  
   - Analisis imbalance data (kelas `no` jauh lebih dominan dibanding `yes`)  

3. **Preprocessing**  
   - Encoding variabel kategorikal (OneHotEncoder / LabelEncoder)  
   - Scaling variabel numerik  

4. **Modeling**  
   Algoritma machine learning yang digunakan:
   - Logistic Regression  
   - K-Nearest Neighbors (KNN)  
   - Decision Tree  
   - Random Forest  

5. **Evaluasi Model**  
   Metrik yang digunakan:  
   - Accuracy  
   - Precision, Recall, F1-score (dengan fokus pada kelas `yes`)  
   - ROC AUC Score  

---

## 📈 Hasil Model
| Model               | Recall (yes) | Precision (yes) | F1-score (yes) | ROC AUC |
|---------------------|--------------|-----------------|----------------|---------|
| Logistic Regression | 0.39         | 0.61            | 0.48           | 0.91    |
| KNN                 | 0.40         | 0.52            | 0.45           | 0.83    |
| Decision Tree       | 0.47         | 0.46            | 0.46           | 0.69    |
| Random Forest       | **0.46**     | 0.59            | **0.52**       | **0.91** |

📌 **Kesimpulan**:  
- Random Forest memberikan hasil terbaik dengan recall `0.46` dan ROC AUC `0.91`.  
- Namun recall masih di bawah 0.5 karena masalah **class imbalance**.  

---

## 🚀 Rencana Pengembangan
Untuk meningkatkan performa (khususnya recall kelas `yes`), beberapa langkah yang dapat dilakukan:
- Tuning Threshold (menurunkan threshold prediksi < 0.5)  
- Oversampling (SMOTE) / Undersampling  
- Model Gradient Boosting (XGBoost, LightGBM, CatBoost) dengan parameter `scale_pos_weight`  
- Voting Classifier (kombinasi Logistic Regression + Random Forest)  
- Stacking untuk menggabungkan beberapa model  

---

## 📦 Cara Menjalankan
1. Clone repository / unduh notebook.  
2. Install dependensi:  
   ```bash
   pip install -r requirements.txt
