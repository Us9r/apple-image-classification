# Proyek Klasifikasi Gambar: Deteksi Apel Sehat vs Busuk

Proyek ini mengembangkan model **Convolutional Neural Network (CNN)** untuk mengklasifikasikan gambar apel menjadi dua kategori: **Apel Sehat (Healthy)** dan **Apel Busuk (Rotten)**. Model ini dibangun menggunakan TensorFlow dan Keras di Google Colab, bertujuan untuk deteksi dini apel busuk guna mengurangi kerugian dan menjaga kualitas produk.

-----

## Dataset

Dataset berasal dari [Fruit And Vegetable Diseases Dataset (Healthy vs Rotten) di Kaggle](https://www.kaggle.com/datasets/muhammad0subhan/fruit-and-vegetable-disease-healthy-vs-rotten), dengan fokus hanya pada data **Apel**.

Dataset apel terdiri dari gambar 'Healthy' dan 'Rotten', dibagi menjadi set pelatihan, validasi, dan pengujian dengan proporsi sekitar 60% : 25% : 15%.

-----

## Metode dan Teknologi

  * **Framework:** TensorFlow 2.x, Keras
  * **Bahasa Pemrograman:** Python
  * **Lingkungan:** Google Colab
  * **Teknik:** CNN, Augmentasi Data (`ImageDataGenerator`), Batch Normalization, Dropout, Early Stopping, ReduceLROnPlateau, Model Checkpoint.
  * **Konversi Model:** TensorFlow SavedModel, TensorFlow Lite (TFLite), TensorFlow.js (TFJS).

-----

## Arsitektur Model

Model CNN ini memiliki arsitektur sekuensial dengan beberapa blok konvolusi, *pooling*, dan lapisan *dense* yang dilengkapi *Batch Normalization* dan *Dropout* untuk regularisasi.

-----

## Hasil

Setelah pelatihan, model dievaluasi pada set pengujian:

  * **Akurasi Pelatihan:** [99.06%]%
  * **Akurasi Pengujian:** [99.01%]%
  * **Loss Pelatihan:** [0.0304]
  * **Loss Pengujian:** [0.0322]

Model ini memenuhi kriteria akurasi [95%]. Detail lebih lanjut (confusion matrix, classification report, grafik history pelatihan) tersedia di notebook Google Colab.

-----

## File Hasil Konversi Model

Model yang sudah dilatih dikonversi ke format berikut untuk kemudahan *deployment*:

  * **TensorFlow SavedModel:** `submission/saved_model/`
  * **TensorFlow Lite (.tflite):** `submission/tflite/model.tflite` dan `submission/tflite/label.txt`
  * **TensorFlow.js:** `submission/tfjs_model/`

Semua file ini tersedia untuk diunduh.

-----

## Cara Menjalankan Proyek

1.  **Buka Notebook:** Klik tombol "Open In Colab" di atas.
2.  **Siapkan Dataset:** Jalankan sel kode untuk mengunduh dataset dari Kaggle (memerlukan `kaggle.json` dengan kredensial API Kaggle Anda).
3.  **Jalankan Sel Kode:** Jalankan semua sel secara berurutan untuk pra-pemrosesan data, pelatihan, evaluasi, dan konversi model.
4.  **Unduh Hasil:** Setelah konversi selesai, unduh file model yang dihasilkan.

-----

## Struktur Direktori Proyek (Hasil Konversi)

```
.
├── dataset/
│   └── Fruit And Vegetable Diseases Dataset/
│       ├── Apple__Healthy/
│       └── Apple__Rotten/
├── submission/
│   ├── saved_model/         # TensorFlow SavedModel format
│   │   └── ...
│   ├── tflite/              # TensorFlow Lite format
│   │   ├── model.tflite
│   │   └── label.txt
│   └── tfjs_model/          # TensorFlow.js format
│       └── ...
├── nama_notebook_anda.ipynb # File notebook Google Colab
└── README.md                # File ini
```
