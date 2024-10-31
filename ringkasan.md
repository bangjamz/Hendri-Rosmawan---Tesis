Berikut adalah ringkasan dari hasil tesis dengan topik **Analisis Model SVM-PSO dengan Representasi Fitur TF-IDF dan IndoBERT dalam Prediksi Sentimen dan Aspek pada Review**. Penelitian ini bertujuan untuk mengevaluasi keakuratan model prediksi sentimen dan aspek menggunakan dua teknik representasi fitur yang berbeda, yaitu **TF-IDF** dan **IndoBERT**, yang dioptimalkan menggunakan **Particle Swarm Optimization (PSO)** untuk pemilihan parameter terbaik pada model **Support Vector Machine (SVM)**.

### Latar Belakang
Penggunaan machine learning dalam analisis sentimen dan aspek telah menjadi salah satu pendekatan yang umum dalam berbagai bidang, khususnya dalam mengevaluasi umpan balik pengguna. Pemilihan representasi fitur yang tepat sangat penting dalam menentukan performa model, terutama dalam kasus data teks berbahasa Indonesia yang sering membutuhkan teknik representasi khusus seperti IndoBERT. Penelitian ini membandingkan dua pendekatan, TF-IDF dan IndoBERT, untuk memahami kelebihan dan kekurangan masing-masing dalam konteks analisis sentimen dan aspek.

### Metodologi
Data review diolah menggunakan dua metode representasi fitur: TF-IDF untuk frekuensi kata term-weighted dan IndoBERT sebagai representasi berbasis embedding. Data dibagi dalam tiga skenario pembagian data latih-uji, yaitu 70:30, 80:20, dan 90:10, untuk mengamati konsistensi performa model di berbagai ukuran data. Setelah proses representasi fitur, model SVM dioptimalkan dengan PSO untuk menemukan parameter `C` dan `gamma` terbaik pada setiap kombinasi pembagian data.

### Hasil dan Analisis
Hasil menunjukkan bahwa TF-IDF memberikan akurasi dan f1-score yang lebih tinggi dibandingkan dengan IndoBERT pada ketiga skenario pembagian data, terutama dalam prediksi sentimen dan aspek. Model dengan TF-IDF mencapai akurasi tertinggi sebesar 78% pada rasio 80:20 untuk sentimen, sedangkan IndoBERT hanya mencapai 68.29% pada rasio yang sama. Selain itu, kategori aspek umum memiliki f1-score tertinggi pada TF-IDF dibandingkan IndoBERT, menunjukkan bahwa TF-IDF lebih stabil dan konsisten di berbagai skenario.

| Pembagian Data | Model           | Parameter Terbaik (C) | Parameter Terbaik (Gamma) | Akurasi Sentimen | Akurasi Aspek | F1-Score Sentimen Positif | F1-Score Aspek Umum |
|----------------|-----------------|------------------------|----------------------------|-------------------|---------------|---------------------------|----------------------|
| 70:30          | SVM-PSO TF-IDF  | 20.0                  | 1.0                        | 77.00%            | 61.00%        | 0.76                      | 0.86                 |
| 70:30          | SVM-PSO IndoBERT| 20.57                 | 1.09                       | 72.13%            | 57.38%        | 0.83                      | 0.70                 |
| 80:20          | SVM-PSO TF-IDF  | 17.0                  | 0.1                        | 78.00%            | 54.00%        | 0.85                      | 0.72                 |
| 80:20          | SVM-PSO IndoBERT| 0.29                  | 0.298                      | 68.29%            | 43.90%        | 0.81                      | 0.61                 |
| 90:10          | SVM-PSO TF-IDF  | 15.0                  | 0.05                       | 71.00%            | 62.00%        | 1.00                      | 0.73                 |
| 90:10          | SVM-PSO IndoBERT| 15.86                 | 0.0776                     | 61.90%            | 57.14%        | 0.75                      | 0.70                 |

### Kesimpulan
Penelitian ini menyimpulkan bahwa TF-IDF memiliki performa yang lebih baik dibandingkan dengan IndoBERT dalam skenario data review terstruktur, dengan akurasi yang lebih tinggi pada prediksi sentimen dan aspek. Meski IndoBERT memberikan representasi yang lebih kaya secara semantik, hasilnya menunjukkan bahwa pendekatan ini mungkin lebih efektif pada data dengan variasi bahasa yang kompleks. Adapun TF-IDF lebih direkomendasikan untuk data teks berbahasa Indonesia dengan struktur yang seragam.
