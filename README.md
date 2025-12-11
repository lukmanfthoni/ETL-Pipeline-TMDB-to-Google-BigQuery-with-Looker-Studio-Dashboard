# ETL-Pipeline-TMDB-to-Google-BigQuery-with-Looker-Studio-Dashboard
ETL Pipeline TMDB to Google BigQuery with Looker Studio Dashboard

Repository ini berisi proses ETL (Extract, Transform, Load) untuk mengambil data film dari TMDB (The Movie Database) API, melakukan transformasi, lalu memuatnya ke Google BigQuery sebagai data lake/data warehouse.
Hasil akhirnya divisualisasikan dalam bentuk dashboard interaktif Looker Studio.
ETL Pipeline: TMDB → Google BigQuery → Looker Studio Dashboard

Repository ini berisi proses ETL (Extract, Transform, Load) untuk mengambil data film dari TMDB (The Movie Database) API, melakukan transformasi, lalu memuatnya ke Google BigQuery sebagai data lake/data warehouse.

Hasil akhirnya divisualisasikan dalam bentuk dashboard interaktif Looker Studio.
| Bagian          | Teknologi                                              |
| --------------- | ------------------------------------------------------ |
| Data Source     | TMDB API                                               |
| ETL Script      | Python (`requests`, `pandas`, `google-cloud-bigquery`) |
| Data Warehouse  | Google BigQuery                                        |
| Visualization   | Looker Studio                                          |
| Version Control | GitHub                                                 |


📥 Extract (TMDB API)

Proses mengambil data seperti:

Popular Movies

Top Rated Movies

Upcoming / Now Playing

Movie Details (genre, rating, popularity, release date)

Data diekstraksi dalam format JSON dan diubah menjadi DataFrame.

🔧 Transform

Transformasi yang dilakukan:

Normalisasi JSON → tabel tabular

Konversi tipe data (tanggal, angka)

Pembersihan kolom kosong

Penyesuaian format sebelum load ke BQ

☁️ Load (Google BigQuery)

Data dimuat ke BigQuery menggunakan:

Service Account

BigQuery Python Client

Mode WRITE_TRUNCATE / WRITE_APPEND (sesuai kebutuhan)

Struktur tabel mencakup:

movies_raw

movies_clean

movie_genres

📊 Dashboard Looker Studio

Data yang sudah berada di BigQuery divisualisasikan dalam dashboard interaktif:

🔗 Dashboard Link:
https://lookerstudio.google.com/reporting/7bfa357b-baf1-49ca-9867-9f3cf7b70de5

Dashboard menampilkan:

Top Rated Movies

Popularity Trends

Distribusi Genre

Rating vs Popularity

Yearly Release Chart

/
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
