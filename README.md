# 📈 LSTM Forecasting USD/IDR dengan Hyperparameter Tuning

Proyek ini bertujuan untuk memprediksi nilai tukar USD/IDR menggunakan model Long Short-Term Memory (LSTM). Proses melibatkan preprocessing data, normalisasi, pembentukan sequence dengan sliding window, pelatihan model LSTM, tuning hyperparameter dengan GridSearchCV, dan evaluasi performa model.

---

## 🔧 Teknologi yang Digunakan

- Python 3
- TensorFlow / Keras
- scikit-learn
- scikeras
- Pandas, NumPy, Matplotlib

---

## 📚 Langkah-langkah

### 1. Load Dataset
Dataset dalam format `.csv` yang sudah dipreproses. Hanya kolom `Date` dan `Close` yang digunakan.

### 2. Normalisasi
Data diskalakan ke range [0, 1] menggunakan `MinMaxScaler`.

### 3. Split Data
Data dipisah menjadi:
- **Training set**: Semua kecuali 30 data terakhir.
- **Testing set**: 30 data terakhir.

### 4. Sliding Window
Membuat data berurutan (sequence) untuk input LSTM dengan ukuran window 20 langkah waktu.

### 5. Hyperparameter Tuning
Menggunakan `GridSearchCV` dan `KerasRegressor (via scikeras)` untuk mencari kombinasi parameter terbaik:

- `units`: [32, 64, 128]
- `optimizer`: ['adam', 'rmsprop']
- `batch_size`: [16, 32]
- `epochs`: [30, 50]

### 6. Pelatihan Model
Model dilatih dengan kombinasi parameter terbaik (`units=32`, `optimizer=adam`, `batch_size=16`, `epochs=50`).

## 📌 Catatan
GridSearchCV dapat memakan waktu lama karena banyaknya kombinasi parameter dan proses training neural network.
Perlu dilakukan pelatihan ulang (retraining) dengan parameter terbaik pada data training sebelum prediksi final dilakukan.

## 👨‍💻 Author
Paul Wijaya Verda Kusuma (Sanata Dharma - Konsentrasi Jaringan)
