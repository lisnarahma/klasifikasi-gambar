# Klasifikasi Gambar dengan MobileNetV2

## Ringkasan Proyek
Proyek ini adalah sistem klasifikasi gambar berbasis deep learning menggunakan TensorFlow dan Keras. Model menggunakan **MobileNetV2** sebagai dasar transfer learning dan diterapkan pada dataset gambar kustom. Setelah dilatih dan dievaluasi, model diekspor ke format TensorFlow.js untuk deployment ke aplikasi web.

## Dataset
- Dataset berisi gambar-gambar yang dikelompokkan ke dalam folder berdasarkan kelas.
- Setiap folder merepresentasikan satu label kelas.
- Dataset digunakan untuk membedakan berbagai kategori objek berdasarkan ciri visualnya.
- Data dimuat menggunakan `ImageDataGenerator` dari TensorFlow, dengan augmentasi data diterapkan pada data training untuk meningkatkan performa generalisasi model.

## Arsitektur Model
- **Model Dasar**: MobileNetV2 (pre-trained pada ImageNet, tanpa top layer).
- **Layer Tambahan**:
  - Global Average Pooling
  - Dense layer dengan fungsi aktivasi
  - Dropout untuk regularisasi
  - Output layer dengan aktivasi softmax untuk klasifikasi multi-kelas

## Proses Pelatihan
- **Pemisahan Data**: Data dibagi menjadi data training dan validasi.
- **Loss Function**: Categorical Crossentropy
- **Optimizer**: Adam
- **Callbacks**:
  - EarlyStopping (monitoring validation loss)
  - ModelCheckpoint (menyimpan model terbaik)

## Evaluasi Model
- Kinerja model dievaluasi menggunakan data validasi.
- Plot akurasi dan loss ditampilkan untuk memantau performa selama pelatihan.

## Ekspor ke TensorFlow.js
- Setelah pelatihan selesai, model dikonversi ke format TensorFlow.js menggunakan `tensorflowjs_converter` untuk deployment di web.

## Cara Menjalankan
1. Clone repositori ini.
2. Install semua library yang dibutuhkan:

```bash
pip install -r requirements.txt
```

3. Jalankan notebook:

```bash
jupyter notebook Notebook.ipynb
```

Atau upload notebook ke Google Colab dan jalankan semua cell.

## Library yang Dibutuhkan
- tensorflow
- tensorflowjs
- scikit-learn
- matplotlib
- numpy

(Lengkapnya ada di file `requirements.txt`)
