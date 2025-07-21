# Proyek Klasifikasi Ekspresi Wajah Sederhana (Happy vs Sad)

## Ringkasan Proyek

Proyek ini bertujuan untuk mengembangkan dan melatih model *Deep Learning* untuk tugas klasifikasi ekspresi wajah biner: "Happy" (Bahagia) dan "Sad" (Sedih). Kami menggunakan teknik *Transfer Learning* dengan *base model* MobileNetV2 untuk efisiensi pelatihan. Antarmuka pengguna interaktif (UI) menggunakan Gradio untuk demo dan pengumpulan data berkelanjutan juga diimplementasikan.

## Fitur Utama

  * **Pemuatan dan Pra-pemrosesan Data:** Menggunakan `ImageDataGenerator` untuk memuat gambar, mengubah ukuran, menormalisasi piksel, dan menerapkan augmentasi data.
  * **Pemilihan Kelas Spesifik:** Hanya mengimpor dan menggunakan gambar dari folder "Happy" dan "Sad" dari dataset multi-ekspresi.
  * **Arsitektur Model (Transfer Learning):** Memanfaatkan MobileNetV2 yang sudah dilatih, dengan lapisan *base* dibekukan dan lapisan kustom baru ditambahkan di atasnya.
  * **Kompilasi Model:** Menggunakan *optimizer* 'adam' dan `binary_crossentropy` sebagai *loss function*.
  * **Pelatihan Model:** Melatih model menggunakan data pelatihan dan validasi, dengan *callbacks* `EarlyStopping` dan `ReduceLROnPlateau`.
  * **Visualisasi Hasil Pelatihan:** Menampilkan grafik akurasi dan *loss* pelatihan serta validasi.
  * **Antarmuka Pengguna Interaktif (UI):** Menggunakan Gradio untuk membuat UI berbasis web interaktif.
  * **Penyimpanan Data Input:** Gambar yang diunggah melalui UI akan disimpan secara otomatis untuk tujuan pengumpulan data dan potensi pelatihan ulang.

## Struktur Kode

Kode ini disusun dalam format Jupyter Notebook (`.ipynb`) dan mencakup bagian-bagian berikut:

  * **Impor Pustaka dan Memuat Data:** Mengimpor semua pustaka yang diperlukan dan memuat dataset ekspresi wajah.
  * **Membangun Arsitektur Model:** Mendefinisikan arsitektur model dengan *transfer learning* dan menampilkan ringkasan model.
  * **Kompilasi dan Pelatihan Model:** Mengkompilasi model dan melatihnya menggunakan data yang disiapkan serta menerapkan *callbacks*.
  * **Evaluasi Model:** Mengevaluasi model yang telah dilatih dan memvisualisasikan hasilnya dengan grafik akurasi dan *loss*.
  * **Penyimpanan Data Baru dan Implementasi UI:** Mengatur direktori penyimpanan untuk data baru yang diinput melalui UI, dan mengimplementasikan UI Gradio untuk interaksi pengguna.

## Cara Menjalankan Proyek

1.  **Klon Repositori**

    ```bash
    git clone [https://github.com/blackcatin/Mini-Project-Happy-Sad-Expression] 
    cd Mini-Project-Happy-Sad-Expression
    ```

2.  **Instal Dependensi**

    Pastikan Anda memiliki Python terinstal. Kemudian instal pustaka yang diperlukan:

    ```bash
    pip install tensorflow numpy matplotlib pillow gradio
    ```

3.  **Siapkan Dataset**

      * Unduh dataset `face-expression-recognition-dataset` dari Kaggle atau siapkan dataset Anda sendiri dengan struktur folder `train/happy`, `train/sad`, `validation/happy`, dan `validation/sad`.
      * Jika Anda menggunakan dataset Kaggle, tambahkan dataset tersebut ke *notebook* Anda. Pastikan `dataset_path` dalam kode Anda menunjuk ke lokasi yang benar di Kaggle (misalnya: `/kaggle/input/face-expression-recognition-dataset`).

4.  **Jalankan Jupyter Notebook**

    ```bash
    jupyter notebook happy-and-sad-expression.ipynb 
    ```

    Ini akan membuka Jupyter Notebook di *browser* web Anda.

5.  **Eksekusi Sel**

    Di antarmuka Jupyter Notebook, Anda dapat menjalankan setiap sel secara berurutan dari atas ke bawah untuk memuat data, melatih model, dan melihat hasilnya.

## Hasil dan Analisis

Setelah pelatihan, model akan menghasilkan akurasi validasi sekitar **78.95%** dan *loss* validasi sekitar **0.5898** pada dataset yang diberikan (18 gambar pelatihan, 19 gambar validasi). Grafik *loss* akan menunjukkan penurunan *loss* pelatihan, dan *loss* validasi yang relatif stabil, meskipun fluktuatif karena ukuran dataset yang sangat kecil. Model menunjukkan kemampuan belajar dasar dalam membedakan ekspresi "Happy" dan "Sad" melalui *transfer learning*.

## Kontributor

| Nama Kontributor | Jobdesk |
| :--------------- | :----------------------------- |
| Firlana Umi Azzakiy   | Merancang Arsitektur Model     |
| Shafiyyah Al-Khansa      | Pra-pemrosesan Data            |
| Mutiara Afny | Kompilasi dan Pelatihan Model  |
| Andini Putri Rosyidi     | Visualisasi Hasil dan Analisis Loss |
| Rana Rohadatul 'Aisy  | Dokumentasi Kode dan README    |

## Teknologi yang Digunakan

  * Python 3.x
  * TensorFlow/Keras - Framework *deep learning*
  * NumPy - Komputasi numerik
  * Matplotlib - Visualisasi data
  * Pillow (PIL) - Pemrosesan gambar
  * Gradio - *Framework* pengembangan UI
  * Jupyter Notebook - *Environment* pengembangan

## Struktur File

```
mini-project-happy-sad/
├── happy-and-sad-expression.ipynb    # Notebook utama
├── README.md                         # Dokumentasi proyek 
└── face-expression-happy-sad         # Directory Dataset      
    └── Face Expression/
        ├── train/
        │   ├── happy/
        │   └── sad/
        └── validation/
            ├── happy/
            └── sad/
└── new_predictions_data              # direktori penyimpanan data baru
    ├── happy_predicted/
    └── sad_predicted/
```

-----
