# 🏨 Hotel Booking — Data Warehouse & Business Intelligence

> **End-to-End BI Pipeline**: ETL → Dimensional Modeling → OLAP Analytics → Executive Dashboard  
> Dataset: Hotel Bookings (119,390 records, 2015–2017) | Model: Kimball Star Schema | Engine: SQLite + DuckDB

---

## 📋 Daftar Isi

- [Latar Belakang](#-latar-belakang)
- [Tujuan Proyek](#-tujuan-proyek)
- [Arsitektur Sistem](#-arsitektur-sistem)
- [Dataset](#-dataset)
- [Tahapan Proses (ETL)](#-tahapan-proses-etl)
  - [Extract](#1-extract--load-raw-data)
  - [Transform](#2-transform--data-cleaning--feature-engineering)
  - [Load](#3-load--build-star-schema-data-warehouse)
- [Desain Data Warehouse](#-desain-data-warehouse--star-schema)
- [Analisis Data & OLAP](#-analisis-data--olap-queries)
- [Executive KPI Dashboard](#-executive-kpi-dashboard)
- [Business Insights](#-strategic-business-insights)
- [Struktur Repositori](#-struktur-repositori)
- [Cara Menjalankan](#-cara-menjalankan)
- [Teknologi yang Digunakan](#-teknologi-yang-digunakan)
- [Hasil & Temuan](#-hasil--temuan)

---




##   𝐀𝐧𝐠𝐠𝐨𝐭𝐚 𝐊𝐞𝐥𝐨𝐦𝐩𝐨𝐤
  
| Isrina Luthfiah | Nayla Camelia Indraswari | Dilla Maharani| Muhammad Refi Fadhilah |
|---------------|------------|------|--------------------|
| <div align="center"><img  src="https://github.com/user-attachments/assets/1b251582-257f-4409-a469-d821a7d941a4"  width="180"></div> | <div align="center"><img src="https://github.com/user-attachments/assets/ac6bdaaa-f435-456c-93ae-ffd7d438b35f" width="195"></div> | <div align="center"><img  width="195"></div> | <div align="center"><img width="240"></div> |
| <div align="center">2409116003</div> | <div align="center">2409116009</div> | <div align="center">2409116023</div> | <div align="center">2409116034</div> |
| <div align="center">Sistem Informasi A '24</div> | <div align="center">Sistem Informasi A '24</div> | <div align="center">Sistem Informasi A '24</div> | <div align="center">Sistem Informasi A '24</div> |
| <div align="center"><a href="https://github.com/rinaaluthfiah"><img src="https://img.shields.io/badge/GitHub-Isrina-grey?style=for-the-badge&logo=github"></a></div> | <div align="center"><a href="https://github.com/angiee24"><img src="https://img.shields.io/badge/GitHub-Angela-grey?style=for-the-badge&logo=github"></a></div> | <div align="center"><a href="https://github.com/Zahraramadhani014"><img src="https://img.shields.io/badge/GitHub-Zahra-grey?style=for-the-badge&logo=github"></a></div> | <div align="center"><a href="https://github.com/aliyah06667"><img src="https://img.shields.io/badge/GitHub-Aliyah-grey?style=for-the-badge&logo=github"></a></div> |





## 📌 Latar Belakang

Industri perhotelan menghasilkan volume data transaksi yang sangat besar setiap harinya — mulai dari data pemesanan, pembatalan, segmentasi tamu, hingga performa saluran distribusi. Tanpa infrastruktur analitik yang tepat, data ini hanya menjadi tumpukan angka yang sulit dieksplorasi.

**Masalah yang diidentifikasi:**

| Masalah | Dampak Bisnis |
|---|---|
| Data pemesanan tersebar, belum terstruktur | Laporan manual lambat dan rawan kesalahan |
| Tidak ada visibilitas tren pendapatan | Kesulitan perencanaan kapasitas dan pricing |
| Tingkat pembatalan tinggi (~37%) | Potensi kehilangan pendapatan signifikan |
| Tidak ada segmentasi pelanggan yang sistematis | Kesulitan memprioritaskan strategi retensi |

**Solusi:** Membangun **Data Warehouse** berbasis arsitektur Kimball (*Star Schema*) yang mengintegrasikan seluruh data pemesanan ke dalam satu model analitik terpusat, sehingga pertanyaan bisnis yang sebelumnya membutuhkan jam pengerjaan bisa dijawab dalam hitungan detik.

---

## 🎯 Tujuan Proyek

1. **Membangun Data Warehouse** dari data hotel booking menggunakan pendekatan Kimball Bottom-Up dengan model Star Schema
2. **Merancang pipeline ETL** yang bersih dan terdokumentasi (Extract → Transform → Load)
3. **Melakukan analisis OLAP** untuk menjawab pertanyaan bisnis kritis
4. **Menghasilkan laporan eksekutif** berupa KPI Dashboard dan Business Insights
5. **Mendokumentasikan ETL lineage** melalui Metadata Repository

---

## 🏗️ Arsitektur Sistem

```
┌─────────────┐     ┌──────────────────────┐     ┌─────────────────────────┐     ┌──────────────────┐
│   [SOURCE]  │     │     [ETL LAYER]       │     │   [DATA WAREHOUSE]      │     │   [ANALYTICS]    │
│             │     │                      │     │                         │     │                  │
│  hotel_     │────▶│  1. Extract          │────▶│  dim_date               │────▶│  OLAP Queries    │
│  bookings   │     │     (pandas read)    │     │  dim_hotel              │     │  KPI Dashboard   │
│  .csv       │     │                      │     │  dim_customer           │     │  Business Insight│
│             │     │  2. Transform        │     │  dim_market             │     │  Visualisasi     │
│  119,390    │     │     (clean + enrich) │     │  dim_room               │     │  Matplotlib +    │
│  records    │     │                      │     │  ──────────────────     │     │  Seaborn         │
│  2015–2017  │     │  3. Load             │     │  fact_booking ⭐        │     │                  │
└─────────────┘     │     (SQLite DW)      │     │                         │     └──────────────────┘
                    └──────────────────────┘     └─────────────────────────┘
```

**Technology Stack:**
- **Storage**: SQLite (persistent) + DuckDB (in-memory OLAP)
- **Processing**: Python, pandas, NumPy
- **Visualization**: Matplotlib, Seaborn
- **Model**: Kimball Star Schema (Bottom-Up)

---

## 📊 Dataset

| Atribut | Detail |
|---|---|
| **Sumber** | [Hotel Booking Demand Dataset](https://www.kaggle.com/datasets/jessemostipak/hotel-booking-demand) |
| **Jumlah Record** | 119,390 baris |
| **Periode** | Juli 2015 – Agustus 2017 |
| **Jumlah Kolom** | 32 kolom |
| **Jenis Hotel** | City Hotel & Resort Hotel |
| **Ukuran File** | ~23 MB |

**Kolom Utama:**

| Kolom | Deskripsi |
|---|---|
| `hotel` | Jenis hotel (City Hotel / Resort Hotel) |
| `is_canceled` | Status pembatalan (0 = tidak, 1 = ya) |
| `arrival_date_*` | Komponen tanggal kedatangan |
| `adr` | Average Daily Rate (€) |
| `market_segment` | Segmen pasar pemesanan |
| `distribution_channel` | Saluran distribusi |
| `customer_type` | Tipe pelanggan |
| `country` | Negara asal tamu |
| `deposit_type` | Jenis deposit |

---

## ⚙️ Tahapan Proses ETL

### 1. Extract — Load Raw Data

Tahap pertama adalah membaca data mentah dari file CSV ke dalam memori menggunakan pandas.

```python
df_raw = pd.read_csv('hotel_bookings.csv')

print(f'Shape     : {df_raw.shape[0]:,} rows × {df_raw.shape[1]} columns')
print(f'Memory    : {df_raw.memory_usage(deep=True).sum() / 1e6:.1f} MB')
print(f'Date range: {df_raw.arrival_date_year.min()} – {df_raw.arrival_date_year.max()}')
```

**Temuan pada tahap Extract:**

| Kolom | Missing Values | Penanganan |
|---|---|---|
| `children` | 4 | Fill dengan 0 |
| `country` | 488 | Fill dengan `'Unknown'` |
| `agent` | 16,340 | Fill dengan 0 |
| `company` | 112,593 | Fill dengan 0 |

---

### 2. Transform — Data Cleaning & Feature Engineering

Tahap ini terdiri dari tiga sub-proses:

#### 2.1 Handle Missing Values
```python
df['children'] = df['children'].fillna(0).astype(int)
df['country']  = df['country'].fillna('Unknown')
df['agent']    = df['agent'].fillna(0)
df['company']  = df['company'].fillna(0)
```

#### 2.2 Remove Invalid Records
```python
# Hapus ADR negatif (tidak valid secara bisnis)
df = df[df['adr'] >= 0]

# Hapus record tanpa tamu (adults + children + babies = 0)
df = df[(df['adults'] + df['children'] + df['babies']) > 0]
```

#### 2.3 Feature Engineering — Kolom Derivasi

| Kolom Baru | Formula / Logika | Tujuan |
|---|---|---|
| `arrival_date` | Gabung tahun + bulan + hari | Kolom tanggal tunggal untuk join ke dim_date |
| `total_nights` | `stays_in_weekend_nights + stays_in_week_nights` | Durasi menginap |
| `total_guests` | `adults + children + babies` | Jumlah tamu total |
| `total_revenue` | `adr × total_nights` | Proxy pendapatan per booking |
| `quarter` | Dari `arrival_date.dt.quarter` | Analisis kuartalan |
| `is_family` | `children > 0 OR babies > 0` | Flag segmen keluarga |
| `room_upgraded` | `reserved_room_type ≠ assigned_room_type` | Flag upgrade kamar |
| `booking_id` | Auto-increment surrogate key | Primary key unik |

**Hasil Transform:**

```
Removed 180 invalid rows → 119,210 clean rows
✅ Transform complete: 119,210 rows ready for loading
```

---

### 3. Load — Build Star Schema Data Warehouse

Data yang sudah bersih dimuat ke dalam model dimensi berbasis **Kimball Star Schema**.

#### Inisialisasi Database
```python
conn = sqlite3.connect(':memory:')  # atau ganti path untuk persistent
```

#### Pembuatan Tabel Dimensi

**`dim_date`** — Dimensi Waktu
```sql
CREATE TABLE dim_date (
    date_key      INTEGER PRIMARY KEY,   -- format YYYYMMDD
    full_date     TEXT,
    year          INTEGER,
    quarter       TEXT,
    month_num     INTEGER,
    month_name    TEXT,
    week_number   INTEGER,
    day_of_month  INTEGER
)
```

**`dim_hotel`** — Dimensi Hotel
```sql
CREATE TABLE dim_hotel (
    hotel_key  INTEGER PRIMARY KEY AUTOINCREMENT,
    hotel_name TEXT UNIQUE
)
```

**`dim_customer`** — Dimensi Pelanggan
```sql
CREATE TABLE dim_customer (
    customer_key      INTEGER PRIMARY KEY AUTOINCREMENT,
    customer_type     TEXT,
    country           TEXT,
    is_repeated_guest INTEGER,
    is_family         INTEGER
)
```

**`dim_market`** — Dimensi Segmen Pasar
```sql
CREATE TABLE dim_market (
    market_key           INTEGER PRIMARY KEY AUTOINCREMENT,
    market_segment       TEXT,
    distribution_channel TEXT,
    deposit_type         TEXT
)
```

**`dim_room`** — Dimensi Kamar
```sql
CREATE TABLE dim_room (
    room_key           INTEGER PRIMARY KEY AUTOINCREMENT,
    reserved_room_type TEXT,
    assigned_room_type TEXT,
    meal               TEXT
)
```

**`fact_booking`** — Tabel Fakta Utama
```sql
-- Foreign keys ke semua dimensi + measure columns
booking_id, date_key, hotel_key, customer_key, market_key, room_key,
is_canceled, lead_time, total_nights, total_guests,
adr, total_revenue, booking_changes, days_in_waiting_list,
required_car_parking_spaces, total_of_special_requests, room_upgraded,
reservation_status
```

**DW Summary setelah Load:**

```
── Data Warehouse Summary ──────────────────────────
  dim_date               1,023 rows
  dim_hotel                  2 rows
  dim_customer           3,148 rows
  dim_market                34 rows
  dim_room                  45 rows
  fact_booking         119,210 rows
```

---

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

---

## 🔍 Analisis Data & OLAP Queries

### Q1 — Revenue per Hotel per Tahun (Roll-Up)
```sql
SELECT h.hotel_name, d.year, d.quarter, d.month_name,
       SUM(f.total_revenue)                                          AS total_revenue,
       SUM(CASE WHEN f.is_canceled=0 THEN f.total_revenue ELSE 0 END) AS confirmed_revenue,
       AVG(f.adr)                                                    AS avg_daily_rate,
       AVG(f.total_nights)                                           AS avg_length_of_stay
FROM fact_booking f
JOIN dim_hotel h ON f.hotel_key = h.hotel_key
JOIN dim_date  d ON f.date_key  = d.date_key
WHERE f.total_revenue > 0
GROUP BY h.hotel_name, d.year, d.quarter, d.month_name, d.month_num
ORDER BY h.hotel_name, d.year, d.month_num
```

### Q2 — Cancellation Analysis by Market Segment & Lead Time
```sql
SELECT h.hotel_name, m.market_segment, m.deposit_type,
       CASE
           WHEN f.lead_time <=   7 THEN '0-7 days'
           WHEN f.lead_time <=  30 THEN '8-30 days'
           WHEN f.lead_time <=  90 THEN '31-90 days'
           WHEN f.lead_time <= 180 THEN '91-180 days'
           ELSE '180+ days'
       END AS lead_time_bucket,
       COUNT(*)                                          AS total_bookings,
       ROUND(100.0 * SUM(f.is_canceled) / COUNT(*), 2)  AS cancel_rate_pct
FROM fact_booking f
JOIN dim_hotel  h ON f.hotel_key  = h.hotel_key
JOIN dim_market m ON f.market_key = m.market_key
GROUP BY h.hotel_name, m.market_segment, m.deposit_type, lead_time_bucket
ORDER BY cancel_rate_pct DESC
```

### Q3 — Customer Segmentation (Value, Loyalty, Upgrade Rate)
```sql
SELECT c.customer_type, c.is_repeated_guest, c.is_family, h.hotel_name,
       COUNT(f.booking_id)                                    AS bookings,
       ROUND(AVG(f.total_revenue), 2)                        AS avg_revenue,
       ROUND(100.0 * SUM(f.room_upgraded) / COUNT(*), 1)     AS upgrade_rate_pct,
       ROUND(100.0 * SUM(f.is_canceled)  / COUNT(*), 1)      AS cancel_rate_pct
FROM fact_booking f
JOIN dim_customer c ON f.customer_key = c.customer_key
JOIN dim_hotel    h ON f.hotel_key    = h.hotel_key
GROUP BY c.customer_type, c.is_repeated_guest, c.is_family, h.hotel_name
ORDER BY avg_revenue DESC
```

### Q4 — Top 15 Countries by Confirmed Revenue
```sql
SELECT c.country,
       COUNT(f.booking_id)                                         AS bookings,
       SUM(CASE WHEN f.is_canceled=0 THEN f.total_revenue ELSE 0 END) AS confirmed_revenue,
       ROUND(100.0 * SUM(f.is_canceled) / COUNT(*), 1)            AS cancel_rate_pct
FROM fact_booking f
JOIN dim_customer c ON f.customer_key = c.customer_key
WHERE c.country != 'Unknown'
GROUP BY c.country
ORDER BY confirmed_revenue DESC
LIMIT 15
```

### Q5 — YoY Revenue Growth per Hotel
```sql
SELECT h.hotel_name, d.year,
       SUM(f.total_revenue) AS revenue,
       ROUND(100.0 * (SUM(f.total_revenue) - LAG(SUM(f.total_revenue))
             OVER (PARTITION BY h.hotel_name ORDER BY d.year)) /
             LAG(SUM(f.total_revenue)) OVER (PARTITION BY h.hotel_name ORDER BY d.year), 1)
             AS yoy_growth_pct
FROM fact_booking f
JOIN dim_hotel h ON f.hotel_key = h.hotel_key
JOIN dim_date  d ON f.date_key  = d.date_key
WHERE f.is_canceled = 0
GROUP BY h.hotel_name, d.year
```

---

## 📈 Executive KPI Dashboard

KPI utama portofolio hotel 2015–2017:

| KPI | Nilai |
|---|---|
| **Total Bookings** | 119,210 |
| **Confirmed Bookings** | ~75,166 |
| **Overall Cancellation Rate** | ~37.0% |
| **Total Confirmed Revenue** | ~€29.5M |
| **Average Daily Rate (ADR)** | ~€101.83 |
| **Avg Length of Stay** | ~3.4 nights |
| **Avg Guests per Booking** | ~1.89 |
| **Room Upgrade Rate** | ~2.9% |

**Visualisasi yang dihasilkan:**

| File | Konten |
|---|---|
| `kpi_dashboard.png` | 8-card executive KPI summary |
| `revenue_trend.png` | Monthly revenue trend per hotel (2015–2017) |
| `cancellation_analysis.png` | Heatmap cancel rate × deposit type + lead time bar chart |
| `adr_analysis.png` | Median ADR per bulan + distribusi per customer type |
| `geo_analysis.png` | Top 15 negara: revenue + bubble chart volume vs ADR |
| `segment_matrix.png` | Heatmap: avg revenue, cancel rate, engagement per segmen |

---

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

### 🗓️ Quick Wins — 90-Day Roadmap

| Prioritas | Aksi |
|---|---|
| 🔴 HIGH | Wajibkan non-refundable deposit untuk lead time > 90 hari |
| 🔴 HIGH | Diskon direct booking 5–10% vs OTA rate |
| 🟡 MED | Program returning guest: auto upgrade setelah 3 kunjungan |
| 🟡 MED | Paket korporat untuk shoulder season Q1/Q4 |
| 🟢 LOW | Real-time cancellation monitoring dashboard |

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

### Apakah Notebook Menjawab Semua Poin?

| Poin Evaluasi | Status | Keterangan |
|---|---|---|
| **Data Warehouse dari data terpilih** | ✅ Lengkap | Star Schema dengan 5 dimensi + 1 tabel fakta, disimpan ke SQLite |
| **Laporan** | ✅ Lengkap | KPI Dashboard (8 KPI card) + 6 chart analitik + Strategic Insights |
| **Latar Belakang** | ✅ Tercakup | Konteks bisnis hotel, masalah data, & justifikasi DW (lihat Section 0 & intro notebook) |
| **Tahapan Proses** | ✅ Lengkap | Section 1–3: Extract → Transform → Load, dengan kode & penjelasan |
| **ETL** | ✅ Lengkap | Cleaning, feature engineering, surrogate key mapping, metadata repository |
| **Analisis Data** | ✅ Lengkap | 5 OLAP query + 6 visualisasi + 5 strategic insights + 90-day roadmap |

---

## 👤 Author

**Proyek UTS Business Intelligence**  
Dibuat dengan Python · pandas · SQLite · Matplotlib · Seaborn  
Arsitektur: **Kimball Star Schema** — Bottom-Up Approach

---

*"Data is the new oil — but only when refined."*
