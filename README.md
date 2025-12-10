# Kelompok27-FPDatmin

| Name           | NRP        | Kelas     |
| ---            | ---        | ----------|
| Bunga Melati Putri Luqman | 5025231253 | Data Mining |
| Rosidah Darman | 5025231307 | Data Mining |
| Dzikrina Hidayani Martin | 5025231311 | Data Mining |

# Flowchart
<img width="1933" height="1176" alt="mermaid-diagram-2025-12-04-132533" src="https://github.com/user-attachments/assets/a7fcbff7-9395-4c18-9051-b8551ff9cdc9" />

# Alur Penelitian (Flowchart)
Rancangan penelitian disusun secara sistematis agar seluruh proses analisis, mulai dari akuisisi data hingga evaluasi model, dapat dijalankan secara terstruktur dan direplikasi oleh peneliti lain. Tahapan penelitian dimulai dengan pemuatan dataset asli yang diperoleh dari platform Kaggle, kemudian dilanjutkan dengan proses pemeriksaan struktur data awal untuk memastikan konsistensi format dan kelengkapan variabel.
Pada tahap berikutnya dilakukan parsing dan ekstraksi label penyakit dari kolom Disease. Kolom ini bersifat multi-nilai sehingga perlu dikonversi menjadi format multi-label biner menggunakan MultiLabelBinarizer agar dapat diproses oleh algoritma machine learning. Setelah label terbentuk, proses exploratory data analysis (EDA) dilakukan untuk memahami karakteristik fitur nutrisi, demografi, gaya hidup, serta distribusi penyakit pada dataset. EDA menjadi tahapan penting karena pola-pola awal inilah yang akan menentukan jenis preprocessing, pilihan fitur, dan model yang paling sesuai untuk digunakan dalam penelitian multilabel.
Tahap selanjutnya adalah rekayasa fitur, yaitu penambahan variabel Body Mass Index (BMI) yang dihitung dari tinggi dan berat badan. BMI ditambahkan sebagai fitur penting karena berfungsi sebagai indikator fisiologis yang berkaitan erat dengan faktor risiko penyakit metabolik. Setelah rekayasa fitur dilakukan, dataset dibagi menjadi dua skenario fitur, yakni feature_1 yang hanya mencakup nutrisi, dan feature_2 yang mencakup nutrisi, demografi, serta gaya hidup. Pembentukan dua skenario fitur ini bertujuan untuk mengevaluasi secara empiris pengaruh kontribusi variabel demografi dalam meningkatkan performa prediksi multi-penyakit.
Tahapan berikutnya adalah preprocessing fitur campuran menggunakan ColumnTransformer. Pada tahap ini fitur numerik distandardisasi menggunakan StandardScaler, sedangkan fitur kategorikal di-encode menggunakan OneHotEncoder. Seluruh preprocessing digabungkan ke dalam pipeline agar proses transformasi konsisten antara data latih dan data uji.
Data kemudian dibagi menjadi data latih dan data uji menggunakan proporsi 80:20. Tahap pengujian awal (Tahap 1) dilakukan untuk membandingkan performa dua skenario fitur menggunakan strategi multi-label One-vs-Rest (OvR) dengan Random Forest sebagai model dasar. Hasil Tahap 1 menentukan feature set terbaik yang kemudian digunakan pada Tahap 2.
Pada Tahap 2, penelitian membandingkan lima algoritma machine learning berbeda yang diintegrasikan dengan OvR, yaitu Logistic Regression, Random Forest, Linear SVC, XGBoost, dan Gaussian Naive Bayes. Masing-masing model dievaluasi dengan metrik multilabel yang sama untuk memastikan perbandingan yang adil.
Seluruh alur penelitian diringkas pada flowchart yang ditunjukkan pada Gambar 1. Flowchart tersebut tidak hanya menggambarkan urutan aktivitas penelitian, tetapi juga menunjukkan hubungan antarproses, mulai dari akuisisi data, persiapan data, pembentukan model, hingga pemilihan model terbaik. Oleh karena itu, flowchart berfungsi sebagai representasi visual dari keseluruhan metodologi sehingga membantu pembaca memahami struktur penelitian secara menyeluruh.

