# UTS_AnalitikTeks

Analisis Sentimen Program Makan Bergizi Gratis (MBG) di Indonesia
Proyek ini bertujuan untuk menganalisis opini masyarakat di media sosial Twitter mengenai Program Makan Bergizi Gratis (MBG), sebuah inisiatif prioritas pemerintah Indonesia untuk meningkatkan gizi anak-anak.
Proyek ini mencakup alur kerja Data Science lengkap mulai dari pengumpulan data hingga klasifikasi teks menggunakan Machine Learning.

#📋 Ringkasan Proyek
Program MBG memicu perdebatan luas antara kelompok yang mendukung (61%) dan menolak (34,1%). Isu utama yang diangkat meliputi manfaat meringankan beban orang tua hingga kekhawatiran serius terhadap keamanan pangan akibat tercatatnya 13.168 kasus keracunan hingga Oktober 2025.

#🛠️ Alur Kerja (Bagian 0 - 5)
##Bagian 1: Pengumpulan Data
Sumber Data: Dataset diambil dari Kaggle yang berisi opini publik Twitter terkait program MBG.
Ukuran Data: Terdiri dari sekitar 3.335 data unik.
Fitur Utama: full_text (opini), location, created_at, favorite_count, dan quote_count.

##Bagian 2: Pra-Pemrosesan Teks
Langkah-langkah untuk mengurangi noise pada data mentah:
Lowercasing dan pembersihan karakter khusus (URL, Mention, Hashtag).
Tokenisasi teks.
Penghapusan Stopwords dan proses Stemming menggunakan pustaka Sastrawi untuk mengubah kata ke bentuk dasar dalam Bahasa Indonesia.

##Bagian 3: Rekayasa Fitur
Mengonversi teks menjadi representasi numerik yang dipahami mesin:
TF-IDF Vectorizer: Menghitung bobot kepentingan kata dalam dokumen.
Word2Vec: Menciptakan word embeddings untuk menangkap kesamaan semantik antar kata.

##Bagian 4: Analisis Data Eksploratif (EDA)
Visualisasi dilakukan untuk memahami karakteristik data:
Word Cloud: Menampilkan kata-kata dominan seperti "makan", "gizi", dan "keracunan".
Histogram: Distribusi panjang kata per opini.
Bar Plot: 15 kata yang paling sering muncul untuk mengidentifikasi tren isu terkini.

##Bagian 5: Klasifikasi Teks
Labeling Otomatis: Karena dataset awal tidak memiliki label, dilakukan pelabelan berbasis kata kunci dari artikel sumber. Label Kontra (0) dipicu oleh kata kunci seperti "keracunan" dan "anggaran", sedangkan Pro (1) dipicu oleh kata "meringankan" dan "gizi".
Model: Menggunakan Logistic Regression.
Hasil Evaluasi: Model mencapai Akurasi 0.96.
Precision (Pro): 0.96
Recall (Pro): 1.00
F1-Score (Pro): 0.98

#📊 Hasil Evaluasi
Berdasarkan Confusion Matrix, model berhasil memprediksi 628 data Pro secara akurat, namun masih memiliki tantangan dalam mendeteksi kelas Kontra secara penuh karena distribusi data yang tidak seimbang (mayoritas masyarakat mendukung program sesuai data survei 61%).

#🚀 Teknologi yang Digunakan
Bahasa: Python
Libraries: Pandas, Scikit-Learn, NLTK, Sastrawi, Matplotlib, Seaborn, WordCloud.

--------------------------------------------------------------------------------
Catatan: Proyek ini dikembangkan sebagai bagian dari tugas akademik Analitik Teks (UTS) menggunakan pendekatan Supervised Learning pada data media sosial.
