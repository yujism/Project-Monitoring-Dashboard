# 📊 Dashboard Monitoring PO

## 📸 Preview

![Dashboard Preview](Dashboard_Preview.jpg)

Dashboard berbasis HTML + Google Apps Script untuk monitoring Purchase Order (PO) secara real-time langsung dari Google Spreadsheet.

---

## 🚀 Features

* 📡 **Live Data** dari Google Sheets (via Apps Script API)
* 📊 **Visualisasi Chart**

  * PO per Sales Channel
  * PO per Stage
  * On Track vs Delay (Pareto)
* 🔍 **Filtering Interaktif**

  * Channel
  * Stage (multi-select)
  * Status (On Track / Delay)
  * Order Status (Done / Progress / Waiting)
  * Range tanggal revisi stuffing
* 🔎 **Search PO / Customer**
* 📋 **Table Detail + Pagination**
* 📦 **Modal Detail PO**

  * Qty PO vs Delivery
  * Fulfillment Rate
  * Aggregated Reason

---

## 🧠 Arsitektur

Frontend:

* HTML, CSS, Vanilla JavaScript
* Chart.js untuk visualisasi

Backend:

* Google Apps Script (Web App)
* Data source dari Google Spreadsheet

```text
Google Sheets → Apps Script (API /exec) → HTML Dashboard
```

---

## 🔗 API Endpoint

```text
https://script.google.com/macros/s/AKfycbyo5y8mS6FJC8UY5UHnW_uD4QnjqceRhjUgbctUz7N4srKb6-L_BkmHe6hhIMWzfKj3eA/exec
```

Pastikan:

* Deployment = Web App
* Access = Anyone

---

## 📂 Struktur Data (Expected)

Field yang digunakan:

| Field                   | Description               |
| ----------------------- | ------------------------- |
| NO PO                   | Nomor PO                  |
| CHANNEL                 | Sales channel             |
| Customer                | Nama customer             |
| Tanggal Stuffing Awal   | Tanggal awal              |
| Revisi tanggal stuffing | Tanggal revisi            |
| Qty PO (Dus)            | Quantity PO               |
| Qty Delv. (Dus)         | Quantity delivery         |
| Stages                  | Status proses             |
| Pareto Problem          | ON TRACK / DELAY          |
| Status Order            | Done / Progress / Waiting |
| Reason                  | Alasan delay / note       |

---

## 🛠 Cara Menjalankan

### 1. Lokal (Testing)

```bash
open dashboard_po_live.html
```

atau double click file HTML.

---

### 2. Deploy jadi Web App

#### Opsi 1 — GitHub Pages

1. Upload ke repository
2. Enable GitHub Pages
3. Akses via:

```text
https://username.github.io/repo-name/
```

#### Opsi 2 — Apps Script HTML Service

* Embed HTML ke Apps Script
* Deploy via `doGet()`

#### Opsi 3 — Vercel / Netlify

* Drag & drop project
* Auto deploy

---

## ⚠️ Troubleshooting

### ❌ Data tidak muncul

* Cek API bisa diakses langsung di browser
* Pastikan return JSON valid

### ❌ Error fetch / CORS

* Pastikan Apps Script deploy sebagai Web App
* Access: Anyone

### ❌ Data kosong

* Cek struktur field di Spreadsheet
* Pastikan nama kolom sesuai

---

## 📈 Future Improvement

* 🔐 Authentication / Login
* 📤 Export Excel / CSV
* 🔔 Alert untuk PO Delay
* 📊 KPI tambahan (Lead Time, SLA)
* 📱 Responsive optimization (mobile)

---

## 👨‍💻 Author
Wahyu Aji L - SCM

Developed for internal SCM / PPIC monitoring.

---

## 📄 License

Internal use only.
