# Analisis Dataset Spotify Songs

## **Latar Belakang Masalah**
Musik adalah bagian integral dari kehidupan manusia, dan platform seperti Spotify telah merevolusi cara kita mengakses musik. Dalam dataset ini, kami mencoba memahami berbagai karakteristik lagu berdasarkan fitur audio seperti danceability, energy, dan valence, serta popularitas lagu.

### **Masalah yang Dibahas**
- Bagaimana karakteristik audio memengaruhi popularitas lagu?
- Apakah ada pola atau klaster tertentu dalam data berdasarkan genre atau fitur audio?
- Bagaimana kita dapat memanfaatkan data ini untuk memberikan rekomendasi musik yang lebih baik?

**Manfaat Penelitian:**
- Membantu artis dan produser memahami elemen musik yang lebih populer.
- Meningkatkan algoritma rekomendasi musik Spotify.
- Memberikan pengalaman musik yang lebih sesuai kepada pendengar.

---

## **Paket Python yang Digunakan**
Berikut adalah daftar library Python yang digunakan dalam analisis:

| **Package**           | **Deskripsi**                                                                                  |
|-----------------------|----------------------------------------------------------------------------------------------|
| `pandas`             | Library utama untuk manipulasi data berbasis tabel.                                           |
| `numpy`              | Library untuk komputasi numerik.                                                              |
| `matplotlib.pyplot`  | Library untuk membuat visualisasi data 2D.                                                    |
| `seaborn`            | Library visualisasi tingkat tinggi berbasis Matplotlib.                                       |
| `sklearn.cluster`    | Menggunakan algoritma KMeans untuk klasterisasi data.                                         |
| `sklearn.ensemble`   | Menggunakan RandomForestRegressor untuk model pembelajaran mesin berbasis pohon keputusan.     |
| `sklearn.model_selection` | Fungsi untuk membagi dataset menjadi data latih dan uji.                                  |
| `sklearn.metrics`    | Fungsi untuk mengevaluasi performa model regresi menggunakan MSE dan R-squared.               |

---

## **Data Preprocessing**

### **Sumber Data**
- **Asal Dataset:** Dataset diambil dari proyek [TidyTuesday](https://github.com/rfordatascience/tidytuesday/blob/main/data/2020/2020-01-21/spotify_songs.csv).
- **Deskripsi Data:**
  - Dataset berasal dari Spotify melalui paket `spotifyr`.
  - Tujuan awal data adalah menganalisis lagu populer di Spotify.
  - Jumlah variabel: 24 variabel mencakup atribut audio seperti popularitas, danceability, energy, dan lainnya.
  - **Kekhasan Data:**
    - Terdapat atribut audio unik seperti `danceability` dan `valence`, yang dihitung algoritme Spotify.
    - Beberapa nilai hilang ditemukan, terutama dalam kolom tanggal rilis album.

---
