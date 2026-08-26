# Cerita Metro Pop — Realistic Metro-Pop Mystery Workspace

Aplikasi web *single-file static desk* (HTML, CSS Tailwind CDN, & Vanilla JavaScript) untuk menyusun cerita pendek misteri realistis berlatar perkotaan Indonesia dengan AI *OpenAI-Compatible*.

---

## 🚀 Cara Menjalankan

Aplikasi ini berjalan 100% *client-side* tanpa perlu backend server, build tools, atau database cloud.

1. Buka berkas `index.html` langsung di peramban web modern (Google Chrome, Firefox, Safari, Edge), atau
2. Jalankan melalui static local server (opsional):
   ```bash
   # Menggunakan Python:
   python3 -m http.server 8000

   # Atau menggunakan npx serve:
   npx serve .
   ```
3. Buka `http://localhost:8000` di peramban.

---

## 🖥️ Navigasi & Tata Letak Desktop Workspace

Aplikasi didesain menggunakan model *App Shell* dengan sidebar navigasi tetap dan *single scroll container*:

- **CREATE**:
  - `Buat Cerita`: Meja kerja penyusunan naskah (Wizard 8-tahap atau 5 pilihan alur alur).
  - `Brainstorm`: Partner diskusi interaktif jangka panjang untuk membedah motif, alibi, dan plot twist rasional.
- **BRAIN**:
  - `Writing Brain`: Pusat penyimpanan gaya menulis penulis, pola alur, dan prinsip misteri fair-play.
  - `Research`: Catatan fakta realistis (audit korporat, protokol apartemen, prosedur kepolisian).
- **LIBRARY**:
  - `Story History`: Arsip seluruh naskah cerpen yang telah dibuat.
- **SETTINGS**:
  - Konfigurasi AI Provider, Memori & Otonomi, serta Cadangan Data.

*Catatan Tampilan*: Pada layar desktop (≥900px), sidebar dapat diciutkan menjadi ikon ringkas (68px). Pada layar ponsel (<900px), sidebar bertransformasi menjadi laci (drawer) yang dapat dibuka melalui tombol menu atas.

---

## 🤖 Konfigurasi AI Provider (OpenAI-Compatible Only)

Buka menu **Pengaturan (⚙) > AI Provider** untuk mengatur:

1. **Base Endpoint URL**: Masukkan base URL endpoint (misal `https://api.openai.com/v1`, `https://openrouter.ai/api/v1`, `https://api.groq.com/openai/v1`, `https://api.deepseek.com/v1`, atau endpoint lokal seperti Ollama `http://localhost:11434/v1` dan LM Studio `http://localhost:1234/v1`).
2. **API Key**: API key hanya tersimpan di `localStorage` peramban Anda dan tidak pernah dikirim ke pihak ketiga maupun disertakan dalam file backup ZIP.
3. **Tes & Scan Model**: Tekan tombol scan untuk memeriksa model yang tersedia secara otomatis.
4. **CORS**: Pastikan endpoint Anda mengizinkan permintaan dari browser (`Access-Control-Allow-Origin: *`).

---

## 💾 Cadangan Data Manual & Keamanan (Password Protected ZIP)

Aplikasi mengadopsi prinsip **Local-First** murni tanpa database cloud:

1. **Unduh Cadangan**:
   - Buka **Pengaturan > Data & Backup**.
   - Klik **"DOWNLOAD BACKUP"**.
   - Berkas cadangan akan diunduh dalam format ZIP terenkripsi dengan penamaan bertanggal aktual: `CeritaMetro_Backup_YYYY-MM-DD_HH-mm-ss.zip`.
   - *Catatan Keamanan*: Berkas ZIP dilindungi password aplikasi (`tc123456`).
2. **Simpan ke GitHub Releases (Manual)**:
   - Anda dapat menyimpan berkas ZIP tersebut di perangkat atau mengunggahnya secara manual sebagai asset pada GitHub Releases repository Anda.
3. **Impor & Safe Merge**:
   - Klik **"IMPORT BACKUP"** dan pilih berkas `.zip`.
   - Aplikasi memvalidasi integritas data dan menampilkan pratinjau data.
   - Pilih mode **Gabungkan (Merge)** untuk menggabungkan data tanpa menghapus data lokal, atau mode **Timpa (Replace)** jika ingin menyetel ulang.
   - Jika terdapat perbedaan revisi pada cerita atau catatan yang sama, aplikasi akan menampilkan antarmuka resolusi konflik (*Conflict Resolution*) agar tidak ada tulisan Anda yang terhapus secara sepihak.