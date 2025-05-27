# Laporan Proyek Machine Learning - Muhammad Daniel Ilyasa

##  Project Overview

Dalam dunia gim digital yang semakin masif, jumlah pilihan yang tersedia bagi para pemain bisa sangat membingungkan. Steam, sebagai salah satu platform distribusi gim terbesar di dunia, menampung lebih dari 50.000 gim yang terus bertambah setiap tahunnya [1]. Banyak pengguna yang kewalahan saat harus menemukan gim baru yang sesuai dengan preferensi mereka. Masalah ini disebut sebagai *information overload*, di mana jumlah informasi melebihi kapasitas kognitif pengguna untuk mengolahnya [2].

Maka dari itu, sistem rekomendasi hadir sebagai solusi. Sistem ini membantu menyaring informasi berdasarkan minat pengguna dan menyarankan konten yang relevan. Berdasarkan laporan dari McKinsey, sistem rekomendasi telah meningkatkan engagement pengguna sebesar 30% di beberapa platform digital [3].

Proyek ini bertujuan untuk membangun sistem rekomendasi gim berbasis konten (content-based filtering) dari data Steam, dengan memanfaatkan metadata seperti genre, kategori, dan tag SteamSpy. Proyek ini juga menggabungkan teknik NLP seperti TF-IDF dan cosine similarity untuk menghasilkan rekomendasi gim yang personal dan relevan.

---

##  Pentingnya Proyek

Proyek sistem rekomendasi gim berbasis konten ini bukan sekadar eksperimen teknis—ini adalah respons langsung terhadap tantangan nyata yang dihadapi oleh jutaan pengguna platform distribusi gim digital seperti Steam. Di tengah arus deras rilis gim baru setiap harinya, pengguna semakin kewalahan untuk menemukan judul yang sesuai dengan preferensi mereka. Tanpa panduan yang tepat, pengalaman bermain bisa terasa datar atau bahkan mengecewakan.

Sistem rekomendasi hadir untuk mengisi celah tersebut. Dengan menyarankan gim yang sesuai berdasarkan data deskriptif seperti genre, kategori, dan tag, sistem ini mampu mempercepat proses pengambilan keputusan, meminimalisasi risiko ketidakpuasan pengguna, dan secara tidak langsung meningkatkan loyalitas terhadap platform.

Secara bisnis, manfaatnya juga sangat nyata:

- **Peningkatan Retensi Pengguna**  
  Pengguna yang menemukan konten relevan cenderung kembali ke platform secara berulang.

- **Meningkatkan Engagement dan Waktu Bermain**  
  Rekomendasi yang akurat membuat pengguna menjelajahi lebih banyak gim, yang berarti lebih banyak waktu dan uang yang mereka habiskan di platform tersebut.

- **Meningkatkan Penjualan Produk Tertentu**  
  Sistem rekomendasi dapat mendorong penjualan judul-judul tertentu dengan mengenalkannya kepada target pengguna yang tepat.

---
**Referensi**  
[1] McKinsey & Company. (2013). *Big data: The next frontier for innovation, competition, and productivity*.  
[2] Bawden, D., & Robinson, L. (2009). *The dark side of information: overload, anxiety and other paradoxes*. Journal of Information Science, 35(2), 180–191.  
[3] Steam & Game Stats – Steam. https://store.steampowered.com/stats/

---
##  Business Understanding

###  Problem Statements

1. **Bagaimana memberikan rekomendasi game yang relevan berdasarkan metadata game?**  
   Metadata seperti genre, kategori, dan tag sering kali menjadi sumber informasi yang belum dimaksimalkan dalam sistem rekomendasi berbasis konten. Padahal, atribut-atribut ini menyimpan banyak potensi dalam memahami kesamaan antar game.

2. **Bagaimana menjaga keseimbangan antara precision dan recall pada sistem rekomendasi?**  
   Precision yang tinggi saja bisa menyebabkan sistem hanya merekomendasikan game serupa dalam lingkup yang sempit. Sebaliknya, recall yang tinggi tanpa mempertimbangkan precision bisa menghasilkan rekomendasi yang tidak relevan.

3. **Bagaimana meningkatkan pengalaman pengguna dalam menemukan game yang sesuai dengan preferensi mereka?**  
   Pengalaman pengguna sangat dipengaruhi oleh seberapa akurat sistem mengenali selera mereka. Rekomendasi yang kurang tepat akan membuat pengguna enggan mencoba game baru dan meninggalkan platform.

---

###  Goals

- **Membangun sistem rekomendasi berbasis Content-Based Filtering untuk game.**  
  Sistem ini memanfaatkan metadata seperti *genres*, *categories*, dan *steamspy tags* untuk menghitung kemiripan antar game, dengan pendekatan TF-IDF dan Cosine Similarity.

- **Mengoptimalkan metrik evaluasi seperti Precision, Recall, dan F1-Score.**  
  Target utama adalah menjaga precision minimal 75% dengan recall yang seimbang, untuk memastikan relevansi dan cakupan rekomendasi yang optimal.

- **Meningkatkan engagement pengguna dengan rekomendasi yang relevan.**  
  Dengan memberikan rekomendasi yang sesuai dengan preferensi pengguna, sistem diharapkan dapat meningkatkan waktu bermain dan eksplorasi game baru di platform.

---

###  Solution Approach

1. **Content-Based Filtering**  
   Sistem mengandalkan informasi dari metadata game untuk membangun representasi vektor setiap game. Menggunakan TF-IDF untuk mengubah teks menjadi representasi numerik, kemudian menghitung tingkat kemiripan antar game menggunakan Cosine Similarity.

2. **Eksperimen Threshold Kemiripan**  
   Sistem akan dioptimasi dengan pengujian beberapa nilai ambang batas kemiripan untuk mencari titik terbaik dalam menyeimbangkan precision dan recall. Threshold ini menentukan seberapa mirip game yang bisa masuk dalam daftar rekomendasi.

3. **Evaluasi Rekomendasi**  
   Menggunakan metrik precision, recall, dan F1-score untuk mengevaluasi hasil rekomendasi terhadap *ground truth* yang sudah ditentukan. Evaluasi ini akan digunakan untuk menyempurnakan sistem lebih lanjut.

---

## Keuntungan bagi Bisnis

### 1. Peningkatan Keterlibatan Pengguna  
Sistem rekomendasi yang relevan dapat mendorong pengguna untuk lebih aktif dalam menjelajahi konten yang tersedia. Hal ini berkontribusi pada peningkatan durasi interaksi pengguna dengan platform serta meningkatkan tingkat retensi pengguna secara keseluruhan.

### 2. Pengalaman Pengguna yang Lebih Baik  
Dengan menyediakan rekomendasi yang sesuai dengan preferensi pengguna, sistem dapat menciptakan pengalaman pengguna yang lebih personal dan menyenangkan. Pengalaman positif ini akan memperkuat kepuasan pengguna dan meningkatkan loyalitas mereka terhadap platform.

### 3. Potensi Monetisasi yang Lebih Tinggi  
Platform dengan sistem rekomendasi yang efektif memiliki peluang lebih besar dalam meningkatkan pendapatan, baik melalui model langganan, pembelian dalam aplikasi, maupun melalui iklan. Rekomendasi yang tepat sasaran akan mendorong pengguna untuk melakukan lebih banyak transaksi, yang secara langsung berdampak pada pertumbuhan pendapatan bisnis.

---
## Data Understanding

Dataset yang digunakan dalam proyek ini diperoleh dari **Kaggle**: [Steam Store Games Dataset](https://www.kaggle.com/datasets/nikdavis/steam-store-games). Dataset ini menyajikan informasi lengkap mengenai berbagai game yang tersedia di platform Steam, mulai dari data dasar seperti nama dan tanggal rilis, hingga data deskriptif seperti genre, kategori, tag komunitas, dan data statistik pengguna seperti waktu bermain dan rating.

Dataset ini sangat cocok untuk membangun sistem rekomendasi berbasis konten karena memuat metadata yang kaya dan beragam, yang dapat diolah untuk menilai kemiripan antar game.

### Informasi Dataset
Dataset terdiri dari **27.075 entri** (baris) dan **18 fitur** (kolom), dengan rincian sebagai berikut:

- **appid** : merupakan ID unik yang diberikan oleh Steam untuk setiap game.
- **name** : nama atau judul dari game.
- **release_date** : tanggal rilis game dalam format string.
- **english** : indikator biner (1 atau 0) yang menunjukkan apakah game mendukung bahasa Inggris.
- **developer** : nama pengembang atau developer dari game tersebut.
- **publisher** : nama penerbit game.
- **platforms** : platform yang didukung oleh game seperti Windows, macOS, dan Linux.
- **required_age** : batas usia minimum yang diperlukan untuk memainkan game.
- **categories** : kategori fitur yang dimiliki game, misalnya Single-player, Multi-player, dan sebagainya.
- **genres** : genre utama game, seperti Action, Indie, dll.
- **steamspy_tags** : tag yang diberikan komunitas SteamSpy untuk menggambarkan karakteristik game.
- **achievements** : jumlah pencapaian (achievement) yang tersedia dalam game.
- **positive_ratings** : jumlah ulasan positif dari pengguna.
- **negative_ratings** : jumlah ulasan negatif dari pengguna.
- **average_playtime** : rata-rata durasi waktu bermain pengguna dalam menit.
- **median_playtime** : durasi median waktu bermain pengguna, yang biasanya lebih stabil dibanding rata-rata.
- **owners** : estimasi jumlah pengguna yang memiliki game, disajikan dalam rentang angka.
- **price** : harga game dalam satuan USD.

---
### Insight Awal dari Data

1. Jumlah Data:
- Dataset Steam Store Games terdiri dari **27.075** entri dengan informasi terkait game.
- Untuk model rekomendasi, digunakan 8 fitur utama yaitu `appid`, `name`, `developer`, `publisher`, `platforms`, `categories`, `genres`, dan `steamspy_tags`.

2. Kondisi Data:
- Beberapa kolom seperti `developer` dan `publisher` terdapat nilai kosong (null) yang perlu diatasi pada tahap pra-pemrosesan data.
- Fitur `platforms`, `categories`, `genres`, dan `steamspy_tags` berbentuk teks atau kategori, sangat cocok untuk analisis berbasis konten (content-based filtering).
- Kolom `appid` dan `name` berfungsi sebagai identifikasi unik dan nama game, yang penting untuk referensi hasil rekomendasi.

3. Kesesuaian untuk Sistem Rekomendasi:
- `genres`, `categories`, dan `steamspy_tags` menyediakan deskripsi karakteristik game yang relevan untuk mengukur kemiripan antar game.
- Data `developer` dan `publisher` dapat menjadi informasi tambahan untuk mengelompokkan game berdasarkan pihak pembuat atau penerbit.
- `platforms` membantu memastikan rekomendasi game yang sesuai dengan perangkat pengguna.
  
---
### **Tahapan Eksplorasi Data**
Pada tahap eksplorasi data, dilakukan beberapa analisis untuk memahami pola dan informasi yang dapat mendukung pengembangan sistem rekomendasi. Berikut adalah hasil eksplorasi yang telah dilakukan:

---
**1. Menampilkan 5 developer dengan game terbanyak**

   Visualisasi terhadap kolom `developer` menggunakan fungsi `value_counts()` dan menampilkan **5 besar** dengan jumlah game terbanyak.
   
   ![developer](https://github.com/user-attachments/assets/566985ef-576c-4931-9d9c-c88141afd723)

---

**2. 5 Genre terpopuler**

 Melihat tren genre game di Steam, maka akan dilakukan visualisasi kolom `genres` dan mengambil 5 genre gabungan yang paling sering muncul.

![download](https://github.com/user-attachments/assets/25af6372-4ca9-494d-ad60-c3782feac017)

---

**3. Hubungan playtime dan rating positif**

Untuk menunjukkan hubungan antara rata-rata waktu bermain (dalam menit) dan jumlah rating positif. Titik-titik yang tersebar mencerminkan game-game yang ada di Steam.

![download (1)](https://github.com/user-attachments/assets/f7cbae67-3a39-477a-a803-52891c588290)

- Rata-rata positive rating: 1000,56
- Rata-rata negative rating: 211,03
  
Terlihat jelas, jumlah ulasan positif jauh lebih dominan dibandingkan ulasan negatif.Secara visual, tidak ada korelasi yang jelas dan linear — artinya: banyak dimainkan belum tentu disukai, dan sebaliknya, game singkat bisa saja sangat disukai.

---

## **Data Preparation**

Pada tahap ini, dilakukan serangkaian proses untuk mempersiapkan dataset sehingga siap digunakan untuk model Content-Based Filtering. Berikut adalah langkah-langkah yang dilakukan:

---

### 1. Menangani Nilai Hilang
Sebelum memulai pemodelan, dilakukan penanganan nilai hilang (missing values) terutama pada kolom yang akan digunakan. Nilai kosong di kolom seperti `developer` dan `publisher` diisi dengan  (`'Unknown'`) agar tidak mengganggu proses ekstraksi fitur teks.

### 2. Memilih Kolom
Dari dataset lengkap, dipilih kolom-kolom yang relevan untuk sistem rekomendasi, yaitu:
- `appid`
- `name`
- `developer`
- `publisher`
- `platforms`
- `categories`
- `genres`
- `steamspy_tags`

Kolom-kolom ini dianggap mengandung informasi penting untuk mendeskripsikan karakteristik game.

### 3. TF-IDF Vectorizer Feature Extraction (Ekstraksi Fitur Teks)
Untuk mengubah data teks pada fitur `genres`, `categories`, dan `steamspy_tags` menjadi representasi numerik yang dapat diproses oleh algoritma machine learning, digunakan TF-IDF Vectorizer.

---

## Modeling

Tahapan ini membahas mengenai model sistem rekomendasi yang dikembangkan untuk menyelesaikan permasalahan pencarian game serupa berdasarkan metadata yang tersedia. Sistem rekomendasi yang dibuat bertujuan menghasilkan daftar rekomendasi game teratas (top-N recommendation) sebagai output.

### Cosine Similarity

Pada tahap ini, dilakukan pembangunan sistem rekomendasi berbasis **Content-Based Filtering** dengan menggunakan metode **Cosine Similarity**. Cosine Similarity mengukur sudut antara dua vektor dalam ruang multidimensi, dengan nilai hasil yang berkisar antara 0 hingga 1. Nilai yang semakin mendekati 1 menunjukkan tingkat kemiripan yang semakin tinggi antara dua game.

Karena dataset berukuran cukup besar, yaitu 27.075 entri, perhitungan matriks kemiripan secara penuh akan sangat memakan memori dan waktu proses. Oleh karena itu, pada tahap ini perhitungan similarity matrix dibatasi hanya pada 2.000 data pertama untuk efisiensi komputasi.

Dengan matriks kemiripan ini, kita dapat:

- Menentukan game yang paling mirip dengan game tertentu.
- Membuat sistem rekomendasi sederhana dengan memilih game yang memiliki skor kemiripan tertinggi terhadap input pengguna.

### Sistem Rekomendasi

Fungsi `recommend_game` dirancang untuk memberikan rekomendasi game yang relevan berdasarkan judul game yang dimasukkan oleh pengguna. Proses rekomendasi dilakukan dengan cara berikut:

1. Mencari indeks game yang sesuai dengan judul input pengguna pada DataFrame `df_selected`.
2. Mengambil skor kemiripan dari matriks cosine similarity untuk game tersebut terhadap seluruh game lain.
3. Mengurutkan skor kemiripan secara menurun untuk mendapatkan game dengan skor tertinggi.
4. Mengembalikan daftar game rekomendasi sebanyak *top-N* yang telah ditentukan (default 5).

**Parameter fungsi `recommend_game`:**

- `title`: Nama game yang dimasukkan pengguna sebagai acuan pencarian rekomendasi.
- `df_selected`: DataFrame yang berisi informasi game termasuk kolom `name` sebagai referensi pencarian.
- `cosine_sim`: Matriks Cosine Similarity yang sudah dihitung sebelumnya berdasarkan gabungan fitur *genres*, *categories*, dan *steamspy_tags*.
- `top_n` (opsional): Jumlah rekomendasi game teratas yang ingin ditampilkan.

---

### Hasil Rekomendasi

Berikut adalah hasil rekomendasi berdasarkan game input Half-Life. Setiap game direkomendasikan berdasarkan skor kemiripan (Similarity Score) dengan game input yang diberikan oleh pengguna.

| Rekomendasi                  | Similarity Score |
|-----------------------------|------------------|
| Ricochet                    | 0.836000         |
| Counter-Strike              | 0.824973         |
| Team Fortress Classic       | 0.824973         |
| Deathmatch Classic          | 0.824973         |
| Counter-Strike: Condition Zero | 0.823756     |

Nilai Similarity Score menunjukkan tingkat kemiripan antara game yang direkomendasikan dengan game input. Semakin mendekati angka 1, semakin tinggi kemiripannya.

---

## Evaluation

Pada tahap ini, kita akan mengevaluasi performa sistem rekomendasi berbasis Content-Based Filtering yang telah dibangun menggunakan model TF-IDF dan Cosine Similarity. Evaluasi dilakukan untuk mengukur seberapa efektif sistem dalam memberikan rekomendasi game yang relevan berdasarkan judul game yang dimasukkan oleh pengguna.

### Metrik Evaluasi yang Digunakan

Untuk mengevaluasi hasil dari sistem rekomendasi, beberapa metrik yang umum digunakan dalam sistem berbasis konten adalah sebagai berikut:

1. **Precision@k:**  
   Metrik ini mengukur seberapa banyak item yang relevan (game yang relevan) ada di dalam *k* rekomendasi teratas yang diberikan oleh sistem.

   **Penjelasan:**  
   Precision@k menunjukkan seberapa banyak rekomendasi yang diberikan oleh sistem benar-benar relevan dengan input pengguna.

2. **Recall@k:**  
   Metrik ini mengukur sejauh mana sistem dapat menemukan seluruh item relevan di antara hasil rekomendasi.

   **Penjelasan:**  
   Recall@k membantu mengukur seberapa efektif sistem dalam menemukan semua game yang relevan untuk input pengguna.

3. **F1-Score:**  
   F1-Score adalah gabungan dari precision dan recall, memberikan gambaran yang lebih menyeluruh mengenai kemampuan sistem.

   **Penjelasan:**  
   F1-Score memberikan nilai tunggal untuk menilai keseimbangan antara precision dan recall, yang sangat berguna untuk memastikan bahwa sistem tidak hanya memberikan rekomendasi yang relevan, tetapi juga menemukan semua item relevan.

---

### Analisis Hasil Evaluasi

Pada tahap ini, kita menggunakan hasil rekomendasi untuk menghitung precision dan recall berdasarkan data *ground truth* yang sudah tersedia (misalnya, daftar game relevan dari domain expert).

Berikut adalah hasil evaluasi sistem rekomendasi berdasarkan judul game **"Half-Life"**:

| Metrik      | Nilai  |
|-------------|---------|
| Precision@5 | 80%     |
| Recall@5    | 100%    |
| F1-Score    | 89%     |

---

### Kesimpulan

Berdasarkan evaluasi yang dilakukan, sistem rekomendasi memberikan performa yang cukup baik untuk kata kunci "Half-Life", dengan hasil sebagai berikut:

- **Precision (80%)**:  
  Dari semua rekomendasi yang diberikan oleh sistem, 80% di antaranya relevan. Menunjukkan sistem cukup akurat dalam memilih game yang sesuai.

- **Recall (100%)**:  
  Sistem berhasil menemukan seluruh game relevan yang ada dalam daftar *ground truth*, menandakan cakupan rekomendasi yang baik.

- **F1-Score (89%)**:  
  Kombinasi precision dan recall menghasilkan nilai F1 yang tinggi, menandakan keseimbangan yang baik antara relevansi dan cakupan rekomendasi.

---

### Pengaruh Threshold (Ambang Batas Kesamaan)

- **Menaikkan Threshold:**  
  Precision akan meningkat karena hanya rekomendasi dengan skor similarity tinggi yang dianggap relevan. Namun, recall cenderung menurun karena beberapa game relevan dengan skor similarity rendah terlewat.

- **Menurunkan Threshold:**  
  Recall akan meningkat karena lebih banyak game relevan terdeteksi, termasuk yang memiliki skor similarity rendah. Namun, precision cenderung menurun karena rekomendasi kurang relevan ikut masuk.

---

### Rekomendasi untuk "Half-Life":

- Ricochet (score: 0.836)  
- Counter-Strike (score: 0.825)  
- Team Fortress Classic (score: 0.825)  
- Deathmatch Classic (score: 0.825)  
- Counter-Strike: Condition Zero (score: 0.824)  

---

### Evaluasi di berbagai threshold:

| Threshold | Precision | Recall | F1    |
|-----------|-----------|--------|-------|
| 0.1       | 0.8       | 1.0    | 0.89  |
| 0.3       | 0.8       | 1.0    | 0.89  |
| 0.5       | 0.8       | 1.0    | 0.89  |
| 0.7       | 0.8       | 1.0    | 0.89  |

---

### **Rekomendasi Perbaikan**

1. **Feature Engineering:**  
   Tambahkan atribut lain seperti tahun rilis, popularitas, atau rating game untuk memperkaya konteks rekomendasi.  
   Fitur tambahan ini bisa membantu sistem memahami relevansi lebih mendalam.

2. **Eksperimen Threshold:**  
   Meskipun hasil saat ini stabil, pengujian dengan berbagai threshold secara berkala disarankan untuk mengantisipasi dataset yang berkembang.  
   Threshold bisa disesuaikan bila ada perubahan karakteristik data.

3. **Penggunaan Model Hybrid:**  
   Kombinasikan pendekatan berbasis konten (content-based filtering) dengan collaborative filtering (berdasarkan interaksi pengguna).  
   Model hybrid berpotensi meningkatkan personalisasi dan akurasi rekomendasi.

4. **Optimasi Dataset:**  
   Tambahkan data game yang lebih bervariasi, termasuk judul populer maupun niche, untuk memperbaiki representasi data.  
   Data yang lebih lengkap memungkinkan sistem lebih adaptif dan andal.

---

Dengan perbaikan ini, diharapkan sistem rekomendasi dapat mempertahankan precision minimal 80% sambil menjaga recall di angka maksimal, menghasilkan rekomendasi yang lebih akurat dan berguna bagi pengguna.
