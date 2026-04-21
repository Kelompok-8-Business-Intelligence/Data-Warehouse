#  𝐔𝐓𝐒 𝐁𝐔𝐒𝐈𝐍𝐄𝐒𝐒 𝐈𝐍𝐓𝐄𝐋𝐋𝐈𝐆𝐄𝐍𝐂𝐄 - 𝐇𝐨𝐭𝐞𝐥 𝐁𝐨𝐨𝐤𝐢𝐧𝐠 🏢

  
## 📚 𝗜𝗻𝗳𝗼𝗿𝗺𝗮𝘀𝗶 𝗠𝗮𝘁𝗮 𝗞𝘂𝗹𝗶𝗮𝗵

| Keterangan | Detail |
|------------|--------|
| **Mata Kuliah** | Business Intelligence |
| **Dosen Pengampu** | Ahmad Irsyad |
| **Universitas** | Universitas Mulawarman |
| **Tahun** | 2026 |


## 👩‍💻 𝗔𝗻𝗴𝗴𝗼𝘁𝗮 𝗞𝗲𝗹𝗼𝗺𝗽𝗼𝗸
  
| Isrina Luthfiah | Nayla Camelia Indraswari | Dilla Maharani| Muhammad Refi Fadhilah |
|---------------|------------|------|--------------------|
| <div align="center"><img src="https://github.com/user-attachments/assets/50351347-5da8-41ec-89b8-4958d80b9d10"   width="200"></div> | <div align="center"><img src="https://github.com/user-attachments/assets/e2e91fb9-5571-4255-9105-149632ebeafb" width="215"></div> | <div align="center"><img src="https://github.com/user-attachments/assets/381b595d-7d93-47dc-9848-9423666a2085" width="210"></div> | <div align="center"><img width="240"></div> |
| <div align="center">2409116003</div> | <div align="center">2409116009</div> | <div align="center">2409116023</div> | <div align="center">2409116034</div> |
| <div align="center">Sistem Informasi A '24</div> | <div align="center">Sistem Informasi A '24</div> | <div align="center">Sistem Informasi A '24</div> | <div align="center">Sistem Informasi A '24</div> |
| <div align="center"><a href="https://github.com/rinaaluthfiah"><img src="https://img.shields.io/badge/GitHub-Isrina-pink?style=for-the-badge&logo=github"></a></div> | <div align="center"><a href="https://github.com/naylacamelia"><img src="https://img.shields.io/badge/GitHub-Nayla-pink?style=for-the-badge&logo=github"></a></div> | <div align="center"><a href="https://github.com/dillamhrn"><img src="https://img.shields.io/badge/GitHub-Dilla-pink?style=for-the-badge&logo=github"></a></div> | <div align="center"><a href="https://github.com/aliyah06667"><img src="https://img.shields.io/badge/GitHub-Reffi-pink?style=for-the-badge&logo=github"></a></div> |




## 📊 𝗗𝗮𝘁𝗮𝘀𝗲𝘁:

<img width="344" height="61" alt="image" src="https://github.com/user-attachments/assets/9f7710ec-fdc5-488a-908b-3b8e495c3b2d" />

| Atribut | Detail |
|---|---|
| **Sumber** | [Hotel Booking Demand Dataset](https://www.kaggle.com/datasets/jessemostipak/hotel-booking-demand) |
| **Jumlah Record** | 119,390 baris |
| **Periode** | Juli 2015 – Agustus 2017 |
| **Jumlah Kolom** | 32 kolom |
| **Jenis Hotel** | City Hotel & Resort Hotel |
| **Ukuran File** | ~23 MB |





## 🗒 Latar Belakang

<p align="justify">
Industri perhotelan menghasilkan data transaksi yang cukup besar setiap harinya, seperti data pemesanan kamar, pembatalan reservasi, segmentasi pelanggan, hingga saluran distribusi pemesanan. Data tersebut sebenarnya dapat dimanfaatkan untuk mendukung pengambilan keputusan bisnis. Namun tanpa sistem pengolahan data yang terstruktur, data yang tersedia sering kali sulit dianalisis secara optimal.
</p>

**Permasalahan yang diidentifikasi:**

| Permasalahan | Dampak Bisnis |
|:------------|:-------------|
| Data pemesanan tersebar dan belum terstruktur | Proses pembuatan laporan menjadi lambat dan rentan kesalahan |
| Tidak adanya analisis tren pendapatan | Menyulitkan perencanaan strategi bisnis |
| Tingkat pembatalan reservasi yang cukup tinggi (~37%) | Berpotensi menyebabkan kehilangan pendapatan |
| Belum adanya segmentasi pelanggan yang jelas | Sulit menentukan strategi pemasaran dan retensi pelanggan |




## ★ ˎˊ˗ Tujuan Proyek

1. **Membangun Data Warehouse** dari data hotel booking menggunakan pendekatan Kimball Bottom-Up dengan model Star Schema
2. **Merancang pipeline ETL** yang bersih dan terdokumentasi (Extract → Transform → Load)
3. **Melakukan analisis OLAP** untuk menjawab pertanyaan bisnis kritis
4. **Menghasilkan laporan eksekutif** berupa KPI Dashboard dan Business Insights
5. **Mendokumentasikan ETL lineage** melalui Metadata Repository

---

## 🏗️ Arsitektur Sistem

<img width="900" height="445" alt="image" src="https://github.com/user-attachments/assets/622a052c-d3b0-49a2-a2e5-ac683ee25c82" />




## ⛃ Tools 
- **Storage**: SQLite (persistent) + DuckDB (in-memory OLAP)
- **Processing**: Python, pandas, NumPy
- **Visualization**: Matplotlib, Seaborn
- **Model**: Kimball Star Schema (Bottom-Up)



## ⚙️ Tahapan Proses ETL

### 1️⃣ Extract — Pengambilan Data

Pada tahap ini, dataset Hotel Booking Demand dibaca dari file CSV menggunakan Python. Dataset ini berisi informasi pemesanan hotel seperti data pelanggan, tipe kamar, durasi menginap, hingga pembatalan reservasi.

Karakteristik dataset:

Jumlah data : 119.390 record
Periode data : 2015 – 2017
Jumlah kolom : 32 atribut
Jenis hotel : City Hotel & Resort Hotel

Dataset kemudian dimuat ke dalam memori untuk diproses pada tahap berikutnya.


---

### 2️⃣ Transform — Pembersihan & Pengolahan Data

Tahap transform bertujuan untuk memastikan data bersih, konsisten, dan siap digunakan dalam analisis.

Beberapa proses transformasi yang dilakukan antara lain:

🔹 Data Cleaning
Mengisi nilai kosong (missing values) pada beberapa kolom seperti:
children
country
agent
company
Menghapus data yang tidak valid seperti nilai ADR negatif
Menghapus data reservasi tanpa tamu

 🔹 Feature Engineering

> Beberapa atribut baru dibuat untuk mempermudah proses analisis data.

| Kolom Baru | Keterangan |
|------------|------------|
| `arrival_date` | tanggal lengkap kedatangan tamu |
| `total_nights` | total malam menginap |
| `total_guests` | jumlah total tamu |
| `total_revenue` | estimasi pendapatan dari booking |
| `is_family` | menandai apakah tamu datang bersama keluarga |
| `room_upgraded` | menandai apakah terjadi upgrade kamar |

Setelah proses transformasi selesai, dataset menjadi lebih bersih dan siap dimasukkan ke dalam Data Warehouse.

---

### 3️⃣ Load — Pembuatan Data Warehouse

Tahap terakhir adalah memuat data yang sudah diproses ke dalam Data Warehouse.

Model yang digunakan adalah Kimball Star Schema, karena struktur ini memudahkan proses analisis dan query bisnis.

Struktur Data Warehouse terdiri dari:

⭐ Tabel Fakta
fact_booking

Berisi data utama transaksi pemesanan hotel.

📊 Tabel Dimensi
dim_date
dim_hotel
dim_customer
dim_market
dim_room

Tabel dimensi digunakan untuk menyimpan informasi deskriptif yang mendukung analisis.



## 🌟 Desain Data Warehouse — Star Schema

```
                     ┌──────────────┐
                     │   dim_date   │
                     │ ─────────── │
                     │ date_key PK  │
                     │ full_date    │
                     │ year         │
                     │ quarter      │
                     │ month_name   │
                     └──────┬───────┘
                            │
   ┌──────────────┐         │         ┌──────────────┐
   │  dim_hotel   │         │         │ dim_customer  │
   │ ──────────── │         │         │ ──────────── │
   │ hotel_key PK │         │         │customer_key  │
   │ hotel_name   │         │         │customer_type │
   └──────┬───────┘         │         │country       │
          │                 │         │is_repeated   │
          │        ┌────────┴──────┐  │is_family     │
          └────────┤ fact_booking  ├──┘
                   │ ──────────── │
   ┌──────────────┐│ booking_id PK│┌──────────────┐
   │  dim_market  ││ date_key FK  ││   dim_room   │
   │ ──────────── ││ hotel_key FK ││ ──────────── │
   │ market_key PK││customer_key  ││ room_key PK  │
   │ market_seg.  ││ market_key   ││ reserved_rt  │
   │ dist_channel ││ room_key FK  ││ assigned_rt  │
   │ deposit_type ││ is_canceled  ││ meal         │
   └──────────────┘│ total_rev    │└──────────────┘
                   │ adr          │
                   └──────────────┘
```





## 💡 Strategic Business Insights

### Insight 1 — Revenue & Skala
- City Hotel mendominasi **volume booking**, namun Resort Hotel memegang **ADR premium** terutama di musim panas (Juli–Agustus).

### Insight 2 — Risiko Pembatalan (Kritis)
- Cancellation rate ~37% **jauh di atas** benchmark industri (~20%).
- Deposit jenis *Non Refund* terbukti menekan pembatalan secara drastis.
- **Rekomendasi:** Terapkan kebijakan deposit berlapis — wajibkan non-refundable untuk pemesanan dengan *lead time* > 90 hari.

### Insight 3 — Nilai Tamu Loyal
- *Returning guests* mencatat **durasi menginap lebih panjang** dan ADR lebih tinggi.
- **Rekomendasi:** Investasikan program loyalitas (early check-in, upgrade otomatis setelah 3 kunjungan, penawaran personal).

### Insight 4 — Strategi Musim Puncak
- **Top 3 bulan pendapatan:** Agustus, Juli, Oktober.
- Konsentrasi Juli–Agustus menunjukkan ketergantungan tinggi pada tamu leisure.
- **Rekomendasi:** Kembangkan paket korporat untuk Q1 & Q4 guna mengurangi kesenjangan musiman.

### Insight 5 — Efisiensi Saluran Distribusi
- *Online Travel Agent (OTA)* menghasilkan volume tertinggi namun juga **cancel rate tertinggi** — mencerminkan tamu yang price-sensitive dan low-commitment.
- Direct channel menunjukkan cancel rate 30–40% lebih rendah.
- **Rekomendasi:** Insentif direct booking (best price guarantee, exclusive perks).



---

## 📁 Struktur Repositori

```
hotel-booking-dw/
│
├── README.md                    ← Dokumentasi utama (file ini)
│
├── notebooks/
│   └── uts_bi.ipynb             ← Notebook utama: ETL + DW + Analytics
│
├── data/
│   └── hotel_bookings.csv       ← Dataset mentah (download dari Kaggle)
│
├── outputs/
│   ├── hotel_dw.db              ← SQLite Data Warehouse (hasil export)
│   ├── kpi_dashboard.png        ← Executive KPI dashboard
│   ├── revenue_trend.png        ← Monthly revenue trend
│   ├── cancellation_analysis.png ← Cancellation heatmap + lead time
│   ├── adr_analysis.png         ← ADR seasonality
│   ├── geo_analysis.png         ← Geographic analysis
│   └── segment_matrix.png       ← Customer segment matrix
│
├── docs/
│   ├── star_schema_diagram.png  ← Diagram Star Schema
│   └── etl_lineage.md           ← Dokumentasi ETL field mapping
│
└── requirements.txt             ← Python dependencies
```

---

## 🚀 Cara Menjalankan

### 1. Clone Repository
```bash
git clone https://github.com/username/hotel-booking-dw.git
cd hotel-booking-dw
```

### 2. Install Dependencies
```bash
pip install -r requirements.txt
```

### 3. Siapkan Dataset
Download `hotel_bookings.csv` dari [Kaggle](https://www.kaggle.com/datasets/jessemostipak/hotel-booking-demand) dan letakkan di folder `data/`.

### 4. Jalankan Notebook
```bash
jupyter notebook notebooks/uts_bi.ipynb
```
Atau buka langsung di **Google Colab** — semua dependensi diinstall otomatis di awal notebook.

### 5. Akses Data Warehouse
```python
import sqlite3
import pandas as pd

conn = sqlite3.connect('outputs/hotel_dw.db')

# Contoh query
df = pd.read_sql('''
    SELECT h.hotel_name, d.year, SUM(f.total_revenue) AS revenue
    FROM fact_booking f
    JOIN dim_hotel h ON f.hotel_key = h.hotel_key
    JOIN dim_date  d ON f.date_key  = d.date_key
    WHERE f.is_canceled = 0
    GROUP BY h.hotel_name, d.year
''', conn)
print(df)
```

---

## 🛠️ Teknologi yang Digunakan

| Kategori | Tool / Library | Versi |
|---|---|---|
| **Language** | Python | 3.9+ |
| **Data Processing** | pandas, NumPy | latest |
| **Database** | SQLite3 (built-in) | — |
| **OLAP Engine** | DuckDB | latest |
| **Visualization** | Matplotlib, Seaborn | latest |
| **Notebook** | Jupyter / Google Colab | — |
| **DW Architecture** | Kimball Star Schema | — |

**`requirements.txt`:**
```
pandas>=1.5.0
numpy>=1.23.0
duckdb>=0.8.0
matplotlib>=3.6.0
seaborn>=0.12.0
jupyter>=1.0.0
```

---

## 📝 ETL Lineage — Metadata Repository

| Source Field | DW Table | DW Field | Transformasi |
|---|---|---|---|
| `hotel` | `dim_hotel` | `hotel_name` | Direct map |
| `arrival_date_year/month/day` | `dim_date` | `date_key` | Concat → YYYYMMDD |
| `customer_type` | `dim_customer` | `customer_type` | Direct map |
| `country` | `dim_customer` | `country` | fillna → `'Unknown'` |
| `children + babies > 0` | `dim_customer` | `is_family` | Derived flag (0/1) |
| `market_segment` | `dim_market` | `market_segment` | Direct map |
| `distribution_channel` | `dim_market` | `distribution_channel` | Direct map |
| `deposit_type` | `dim_market` | `deposit_type` | Direct map |
| `reserved_room_type` | `dim_room` | `reserved_room_type` | Direct map |
| `adr` | `fact_booking` | `adr` | Filter `adr >= 0` |
| `adr × total_nights` | `fact_booking` | `total_revenue` | Derived: perkalian |
| `weekend + weekday nights` | `fact_booking` | `total_nights` | Derived: penjumlahan |
| `adults + children + babies` | `fact_booking` | `total_guests` | Derived: penjumlahan |
| `reserved ≠ assigned` | `fact_booking` | `room_upgraded` | Derived flag (0/1) |

---

## ✅ Hasil & Temuan


| Poin Evaluasi | Status | Keterangan |
|---|---|---|
| **Data Warehouse dari data terpilih** | ✅ Lengkap | Star Schema dengan 5 dimensi + 1 tabel fakta, disimpan ke SQLite |
| **Laporan** | ✅ Lengkap | KPI Dashboard (8 KPI card) + 6 chart analitik + Strategic Insights |
| **Latar Belakang** | ✅ Tercakup | Konteks bisnis hotel, masalah data, & justifikasi DW (lihat Section 0 & intro notebook) |
| **Tahapan Proses** | ✅ Lengkap | Section 1–3: Extract → Transform → Load, dengan kode & penjelasan |
| **ETL** | ✅ Lengkap | Cleaning, feature engineering, surrogate key mapping, metadata repository |
| **Analisis Data** | ✅ Lengkap | 5 OLAP query + 6 visualisasi + 5 strategic insights + 90-day roadmap |

---

