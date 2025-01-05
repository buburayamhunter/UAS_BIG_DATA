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
### **Langkah Pembersihan Data**
1. **Memuat Data**
   ```python
   data = pd.read_csv('tidy_spotify_songs.csv')

   ## **Data Preprocessing**

2. **Menangani Nilai yang Hilang**
Langkah-langkah untuk menangani nilai hilang:
- **Kolom `track_album_release_date`:**
  - Nilai kosong diubah menjadi format `NaT` menggunakan `pd.to_datetime` dengan parameter `errors='coerce'`.
  - **Tujuan:** Memastikan analisis berbasis waktu tetap akurat.
  - Kode:
    ```python
    data['track_album_release_date'] = pd.to_datetime(data['track_album_release_date'], errors='coerce')
    ```
- **Kolom `track_name` dan `track_artist`:**
  - Baris dengan nilai kosong dihapus karena kolom ini penting untuk identifikasi lagu.
  - Kode:
    ```python
    data.dropna(subset=['track_name', 'track_artist'], inplace=True)
    ```

---

### **3. Menghapus Duplikasi**
- Duplikasi diperiksa berdasarkan ID unik lagu di kolom `track_id`. Baris duplikat dihapus untuk memastikan setiap lagu hanya muncul sekali.
- Kode:
  ```python
  data.drop_duplicates(subset='track_id', inplace=True)









































