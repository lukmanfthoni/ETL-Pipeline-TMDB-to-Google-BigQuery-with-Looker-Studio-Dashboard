

# ETL Pipeline: TMDB → Google BigQuery → Looker Studio Dashboard

Repository ini berisi proses **ETL (Extract, Transform, Load)** untuk mengambil data film dari **TMDB (The Movie Database)** menggunakan API, melakukan transformasi data, dan memuatnya ke **Google BigQuery** sebagai data warehouse.  
Hasil akhirnya divisualisasikan dalam bentuk **dashboard interaktif di Looker Studio**.

---

## 📌 Fitur Utama

- 🔗 Extract data film dari TMDB API  
- 🧹 Transformasi data menjadi format tabular  
- ☁️ Load data ke Google BigQuery  
- 🗂️ Struktur tabel rapi (movies, genres, dll.)  
- 📊 Dashboard interaktif di Looker Studio  
- 🤖 Dapat diperluas menjadi pipeline otomatis (cron/Cloud Scheduler)

---

## 🛠️ Teknologi yang Digunakan

| Bagian | Teknologi |
|--------|-----------|
| Data Source | TMDB API |
| Bahasa | Python |
| Libraries | requests, pandas, google-cloud-bigquery |
| Data Warehouse | Google BigQuery |
| Visualisasi | Looker Studio |
| Version Control | GitHub |

---

## 📥 Extract (TMDB API)

Data diambil dari TMDB menggunakan REST API dengan jenis data berikut:

- Popular Movies  
- Top Rated Movies  
- Upcoming / Now Playing  
- Movie Details (title, genres, popularity, release date, ratings)



## 🔧 Transform

Transformasi data meliputi:

- Normalisasi nested JSON → tabel tabular  
- Konversi tipe data (tanggal, numerik)  
- Normalisasi genre  
- Pembersihan kolom kosong  
- Penyesuaian agar kompatibel dengan BigQuery schema

---

## ☁️ Load (Google BigQuery)

Data dimuat ke BigQuery menggunakan:

- Service Account JSON  
- BigQuery Python Client  
- Mode penulisan: WRITE_APPEND atau WRITE_TRUNCATE (sesuai kebutuhan)

Contoh tabel yang digunakan:

- `movies_raw`  
- `movies_clean`  
- `movie_genres`

---

## 📊 Dashboard Looker Studio

Dashboard menggunakan data dari BigQuery untuk menampilkan berbagai visualisasi.

🔗 **Link Dashboard:**  
https://lookerstudio.google.com/reporting/7bfa357b-baf1-49ca-9867-9f3cf7b70de5

Insight yang ditampilkan:

- Top Rated Movies  
- Popularity Trends  
- Distribusi Genre  
- Rating vs Popularity  
- Jumlah Film per Tahun  
- Analisis Popularitas per Genre

---

## 📂 Struktur Repository

├── etl/
│   ├── extract_tmdb.py
│   ├── transform.py
│   ├── load_bigquery.py
│   └── config.py
├── data/
│   └── sample_output.csv
├── docs/
│   └── architecture_diagram.png
├── README.md
└── requirements.txt

📈 Arsitektur Pipeline
TMDB API → Python ETL → Google BigQuery → Looker Studio Dashboard

👨‍💻 Author

Lukman Fathoni
