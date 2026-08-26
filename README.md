# Cerita Metro — Realistic Metro-Pop Mystery Workspace

Aplikasi web *single-file* (HTML, CSS Tailwind CDN, & Vanilla JavaScript) untuk menyusun cerita pendek misteri realistis berlatar urban Indonesia dengan bantuan AI *OpenAI-Compatible*.

---

## 🚀 Cara Menjalankan

Aplikasi ini tidak memerlukan backend server, build tools, atau dependensi Node.js.

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

## 🤖 Konfigurasi AI Provider (OpenAI-Compatible Only)

Cerita Metro menggunakan arsitektur AI terpadu yang kompatibel dengan seluruh provider berstandar OpenAI Chat Completions API.

Buka ikon **Pengaturan (⚙)** di sudut kanan atas untuk mengonfigurasi:

### 1. Format Base Endpoint URL
Masukkan base URL endpoint provider Anda (otomatis dinormalisasi tanpa perlu menulis `/chat/completions`):
- **OpenAI**: `https://api.openai.com/v1`
- **OpenRouter**: `https://openrouter.ai/api/v1`
- **Groq**: `https://api.groq.com/openai/v1`
- **DeepSeek**: `https://api.deepseek.com/v1`
- **Ollama (Lokal)**: `http://localhost:11434/v1`
- **LM Studio / LocalAI / vLLM**: `http://localhost:1234/v1`

### 2. API Key
- Masukkan API Key / Bearer Token dari provider pilihan Anda.
- Untuk server lokal tanpa otentikasi (misal Ollama default), API Key dapat dikosongkan.
- **Keamanan**: API Key hanya disimpan secara lokal di `localStorage` peramban Anda dan tidak pernah dikirim ke server pihak ketiga maupun disertakan dalam ekspor data ZIP.

### 3. Model & Pemindaian Otomatis
- Tekan tombol **"TES & SCAN MODEL"** untuk menguji koneksi dan memuat daftar model yang tersedia pada endpoint Anda secara otomatis.
- Anda juga dapat memilih opsi **"Ketik Manual"** jika ingin memasukkan nama model spesifik (contoh: `gpt-4o-mini`, `llama-3.1-8b-instant`, `deepseek-chat`).

### 4. Catatan CORS (Cross-Origin Resource Sharing)
Karena aplikasi berjalan langsung di sisi peramban (*client-side* `fetch`), pastikan endpoint AI Anda mengizinkan permintaan peramban (header `Access-Control-Allow-Origin: *`). Jika menggunakan Ollama lokal, atur environment variable `OLLAMA_ORIGINS="*"`.

---

## 💾 Penyimpanan & Cadangan Data

- **LocalStorage**: Seluruh arsip naskah cerita, riwayat percakapan *Brainstorming Partner*, dan *Writing Brain* (memori preferensi & aturan cerita) disimpan di peramban lokal Anda.
- **Cadangan ZIP**: Buka menu **Pengaturan > Cadangan Data** atau **Arsip Cerita > Export ZIP** untuk mengunduh seluruh data Anda ke dalam satu berkas `.zip`. Berkas cadangan dapat diimpor kembali kapan saja (dengan opsi penggabungan data atau penimpaan).