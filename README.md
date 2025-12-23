# Container Load Optimization (CLO) - Proof of Concept

Repository utama yang berisi dokumentasi dan gambaran umum protek Container Load Optimization (CLO)

Proyek CLO ini dikembangkan sebagai **proof-of-concept akademik** untuk mengeksplorasi algoritma penataan barang (packing heuristic) ke dalam kontainer tiga dimensi.

## Tujuan Proyek

Tujuan dari proyek ini adalah:

- Mensimulasikan penempatan barang berbentuk balok (3D Box) ke dalam kontainer
- Menghasilkan koordinat penempatan barang (x, y, z)
- Mengukur tingkat pemanfaatan ruang kontainer
- Menyediakan sistem yang mudah diuji dan dipahami secara akademik

## Gambaran Umum Sistem

Sistem CLO terdiri dari beberapa komponen terpisah:

1. **CLO Engine (Golang)**

   - Mengimplementasikan algoritma packing
   - Bersifat stateless dan deterministik
   - Menghasilkan hasil penempatan dan metrik pemanfaatan ruang

2. **CLO API (Laravel)**

   - Bertindak sebagai HTTP wrapper
   - Menerima input JSON dari pengguna
   - Menjalankan CLO Engine
   - Mengembalikan output dalam format JSON

3. **Visualisasi (Python)**

## Repository Terkait

- CLO Engine (Golang)  
   Implementasi algoritma packing dan logika utama
  https://github.com/dhafinrazaqa/clo-engine

- CLO API (Laravel)  
   HTTP API untuk mengakses CLO Engine
  https://github.com/dhafinrazaqa/clo-api

## Algoritma Packing

Algoritma yang digunakan adalah **First Fit Decreasing 3D (FFD-3D)**
dengan pendekatan **Shelf-based Packing**

Secara umum:

- Barang diurutkan berdasarkan volume (descending)
- Barang ditempatkan sepanjang sumbu x (panjang kontainer)
- Stacking vertikal dilakukan menggunakan konsep shelf pada sumbu Z
- Shelf bersifat konseptual, bukan rak fisik

## Sistem Koordinat & Visualisasi

Sistem koordinat yang digunakan:

- X -> Panjang kontainer (arah masuk barang)
- Y -> Lebar kontainer
- Z -> Tinggi kontainer

Visualisasi menggunakan proyeksi ortografis 2D:

- Top view (X-Y): denah lantai kontainer
- Longitudinal section: (X-Z): kedalaman vs tinggi
- Door view (Y-Z): tampilan dari pintu kontainer

## Batasan Proyek

- Proyek ini bersifat proof-of-concept
- Tidak mempertimbangkan stabilitas fisik dan distribusi berat
- Tidak menjamin solusi optimal secara global
- Tidak digunakan dalam proses operasional logistik nyata

## Konteks Akademik

Proyek ini dikembangkan sebagai bagian dari:

- Kegiatan akademik / magang
- Eksplorasi algoritma heuristik
- Pendukung penyusunan laporan PA

## Penutup

Repository ini bertujuan memberikan gambaran menyeluruh mengenai
struktur dan tujuan proyek CLO

Untuk detail teknis dan pengujian bisa dilihat di repo CLO Engine dan CLO API masing-masing
