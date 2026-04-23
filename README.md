#  𝐔𝐓𝐒 𝐁𝐔𝐒𝐈𝐍𝐄𝐒𝐒 𝐈𝐍𝐓𝐄𝐋𝐋𝐈𝐆𝐄𝐍𝐂𝐄 - 𝐇𝐨𝐭𝐞𝐥 𝐁𝐨𝐨𝐤𝐢𝐧𝐠 🏢
<p align="justify">
Project ini bertujuan untuk mengintegrasikan data pemesanan hotel ke dalam Data Warehouse guna mendukung proses analisis data. Dataset Hotel Booking Demand digunakan untuk mengidentifikasi pola reservasi, perilaku pelanggan, serta faktor yang mempengaruhi kinerja pemesanan hotel.
</p>


## 📚 𝗜𝗻𝗳𝗼𝗿𝗺𝗮𝘀𝗶 𝗠𝗮𝘁𝗮 𝗞𝘂𝗹𝗶𝗮𝗵

| Keterangan | Detail |
|------------|--------|
| **Mata Kuliah** | Business Intelligence |
| **Dosen Pengampu** | Dr. Akhmad Irsyad S.T.,M.Kom |
| **Universitas** | Universitas Mulawarman |
| **Tahun** | 2026 |


## 👩‍💻 𝗔𝗻𝗴𝗴𝗼𝘁𝗮 𝗞𝗲𝗹𝗼𝗺𝗽𝗼𝗸
  
| Isrina Luthfiah | Nayla Camelia Indraswari | Dilla Maharani| Muhammad Refi Fadhilah |
|---------------|------------|------|--------------------|
| <div align="center"><img src="https://github.com/user-attachments/assets/50351347-5da8-41ec-89b8-4958d80b9d10"   width="200"></div> | <div align="center"><img src="https://github.com/user-attachments/assets/e2e91fb9-5571-4255-9105-149632ebeafb" width="215"></div> | <div align="center"><img src="https://github.com/user-attachments/assets/381b595d-7d93-47dc-9848-9423666a2085" width="210"></div> | <div align="center"><img src="https://github.com/user-attachments/assets/f8693272-f6be-487a-9d99-37ef7f04d229" width="250"></div> |
| <div align="center">2409116003</div> | <div align="center">2409116009</div> | <div align="center">2409116023</div> | <div align="center">2409116034</div> |
| <div align="center">Sistem Informasi A '24</div> | <div align="center">Sistem Informasi A '24</div> | <div align="center">Sistem Informasi A '24</div> | <div align="center">Sistem Informasi A '24</div> |
| <div align="center"><a href="https://github.com/rinaaluthfiah"><img src="https://img.shields.io/badge/GitHub-Isrina-pink?style=for-the-badge&logo=github"></a></div> | <div align="center"><a href="https://github.com/naylacamelia"><img src="https://img.shields.io/badge/GitHub-Nayla-pink?style=for-the-badge&logo=github"></a></div> | <div align="center"><a href="https://github.com/dillamhrn"><img src="https://img.shields.io/badge/GitHub-Dilla-pink?style=for-the-badge&logo=github"></a></div> | <div align="center"><a href="https://github.com/Refficmd"><img src="https://img.shields.io/badge/GitHub-Reffi-pink?style=for-the-badge&logo=github"></a></div> |




## 📊 𝗗𝗮𝘁𝗮𝘀𝗲𝘁:

<img width="344" height="61" alt="image" src="https://github.com/user-attachments/assets/9f7710ec-fdc5-488a-908b-3b8e495c3b2d" />

| Atribut | Detail |
|---|---|
| **Sumber** | [Hotel Booking Demand Dataset](https://www.kaggle.com/datasets/jessemostipak/hotel-booking-demand) |
| **Jumlah Record** | 119,390 baris |
| **Periode** | Juli 2015 – Agustus 2017 |
| **Jumlah Kolom** | 32 kolom |
| **Jenis Hotel** | City Hotel & Resort Hotel |






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
2. **Merancang pipeline ETL** yang bersih dan terdokumentasi (Extract, Transform, Load)
3. **Melakukan analisis OLAP** untuk menjawab pertanyaan bisnis kritis
4. **Menghasilkan laporan eksekutif** berupa KPI Dashboard dan Business Insights
5. **Mendokumentasikan ETL lineage** melalui Metadata Repository

---

## ⛃ Tools 
- **Storage**: SQLite (persistent) + DuckDB (in-memory OLAP)
- **Processing**: Python, pandas, NumPy
- **Visualization**: Matplotlib, Seaborn
- **Model**: Kimball Star Schema (Bottom-Up)


## 🏗️ Arsitektur Sistem

<img width="842" height="289" alt="Screenshot 2026-04-24 013435" src="https://github.com/user-attachments/assets/221979e1-23a3-4899-82eb-f98d8f36db61" />

<p align="justify">
Arsitektur sistem Data Warehouse pada proyek ini terdiri dari beberapa komponen utama, yaitu sumber data, proses ETL, penyimpanan data dalam Data Warehouse berbasis Star Schema, serta modul analisis yang digunakan untuk menghasilkan insight bisnis.
</p>


## ⚙️ Tahapan Proses ETL

<div style="border:1px solid #d0d7de; padding:16px; border-radius:10px; background-color:#e8f2ff;">

<h3>1️⃣ Extract [Pengambilan Data]</h3>

<p>
 Dataset <b>Hotel Booking Demand</b> dibaca dari file CSV menggunakan Python. 
Dataset ini berisi informasi pemesanan hotel seperti data pelanggan, tipe kamar, durasi menginap, hingga pembatalan reservasi.
</p>

<p><b>Karakteristik dataset:</b></p>

<ul>
<li>📊 Jumlah data: <b>119.390 record</b></li>
<li>📅 Periode data: <b>2015 – 2017</b></li>
<li>🧾 Jumlah kolom: <b>32 atribut</b></li>
<li>🏨 Jenis hotel: <b>City Hotel & Resort Hotel</b></li>
</ul>

<p>
Dataset kemudian dimuat ke dalam memori untuk diproses pada tahap berikutnya.
</p>

</div>



 ### 2️⃣ Transform [Pembersihan & Pengolahan Data]

 Tahap transform dilakukan untuk memastikan data berada dalam kondisi **bersih, konsisten, dan siap digunakan** dalam proses analisis.

 #### 🧹 Data Cleaning

 | Aktivitas | Keterangan |
 |-----------|------------|
 | Missing values | Mengisi nilai kosong pada `children`, `country`, `agent`, dan `company` |
 | Data tidak valid | Menghapus nilai `ADR` negatif |
 | Data tidak relevan | Menghapus reservasi tanpa tamu |

 #### ⚙️ Feature Engineering

 | Kolom Baru | Keterangan |
 |------------|------------|
 | `arrival_date` | Tanggal lengkap kedatangan tamu |
 | `total_nights` | Total malam menginap |
 | `total_guests` | Jumlah total tamu |
 | `total_revenue` | Estimasi pendapatan dari booking |
 | `is_family` | Menandai apakah tamu datang bersama keluarga |
 | `room_upgraded` | Menandai apakah terjadi upgrade kamar |

 Setelah proses transformasi selesai, dataset menjadi lebih bersih dan siap dimasukkan ke dalam Data Warehouse.


 ### 3️⃣ Load [Pembuatan Data Warehouse]

 Tahap ini merupakan proses pemuatan data yang telah dibersihkan ke dalam **Data Warehouse** untuk mendukung analisis lebih lanjut.

 Model yang digunakan adalah **Kimball Star Schema**, karena mampu mempermudah proses query dan analisis bisnis.

 #### ⭐ Tabel Fakta
 - `fact_booking`  
   → Menyimpan data utama transaksi pemesanan hotel

 #### 📊 Tabel Dimensi
 - `dim_date`  
 - `dim_hotel`  
 - `dim_customer`  
 - `dim_market`  
 - `dim_room`  

 Tabel dimensi digunakan untuk menyimpan informasi deskriptif yang berfungsi sebagai konteks dalam proses analisis data.



## ✒️ Desain Data Warehouse — Star Schema



<img width="701" height="691" alt="star scema drawio (1)" src="https://github.com/user-attachments/assets/bb0b9581-08e7-4e10-b2cf-e2839c8fbb97" />

<p align="justify">
Struktur Data Warehouse dirancang menggunakan model Star Schema, di mana tabel fakta berada di pusat dan terhubung dengan tabel dimensi. Model ini memudahkan proses analisis data, terutama dalam melakukan query bisnis dan pengolahan OLAP.
</p>



## 💡 Strategic Business Insights

### Insight 1 
  Revenue & Skala
- City Hotel mendominasi **volume booking**, namun Resort Hotel memegang **ADR premium** terutama di musim panas (Juli–Agustus).

### Insight 2  
  Risiko Pembatalan (Kritis)
- Cancellation rate ~37% **jauh di atas** benchmark industri (~20%).
- Deposit jenis *Non Refund* terbukti menekan pembatalan secara drastis.
- **Rekomendasi:** Terapkan kebijakan deposit berlapis — wajibkan non-refundable untuk pemesanan dengan *lead time* > 90 hari.

### Insight 3 
  Nilai Tamu Loyal
- *Returning guests* mencatat **durasi menginap lebih panjang** dan ADR lebih tinggi.
- **Rekomendasi:** Investasikan program loyalitas (early check-in, upgrade otomatis setelah 3 kunjungan, penawaran personal).

### Insight 4 
  Strategi Musim Puncak
- **Top 3 bulan pendapatan:** Agustus, Juli, Oktober.
- Konsentrasi Juli–Agustus menunjukkan ketergantungan tinggi pada tamu leisure.
- **Rekomendasi:** Kembangkan paket korporat untuk Q1 & Q4 guna mengurangi kesenjangan musiman.

### Insight 5 
  Efisiensi Saluran Distribusi
- *Online Travel Agent (OTA)* menghasilkan volume tertinggi namun juga **cancel rate tertinggi** — mencerminkan tamu yang price-sensitive dan low-commitment.
- Direct channel menunjukkan cancel rate 30–40% lebih rendah.
- **Rekomendasi:** Insentif direct booking (best price guarantee, exclusive perks).



---

## 🗃️ Struktur Repositori

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

## 🌐 Teknologi yang Digunakan

| Kategori | Tool / Library | Versi |
|---|---|---|
| **Language** | Python | 3.9+ |
| **Data Processing** | pandas, NumPy | latest |
| **Database** | SQLite3 (built-in) | — |
| **OLAP Engine** | DuckDB | latest |
| **Visualization** | Matplotlib, Seaborn | latest |
| **Notebook** | Jupyter / Google Colab | — |
| **DW Architecture** | Kimball Star Schema | — |






