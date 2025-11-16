# Klepon Assistant Bot  
**WhatsApp Bot Modern dengan Baileys v7+ (LID Support)**

> Bot WhatsApp canggih dengan fitur mention bot via LID, download media, auto-detect LID, simpan LID permanen, dan siap produksi.

[![Node.js](https://img.shields.io/badge/Node.js-v20%2B-green)](https://nodejs.org/)
[![Baileys](https://img.shields.io/badge/Baileys-v7.0.0-blue)](https://github.com/WhiskeySockets/Baileys)
[![License](https://img.shields.io/badge/License-MIT-yellow)](LICENSE)

## Fitur Utama

| Fitur | Status |
|------|--------|
| Pairing Code & QR Login | Done |
| Auto Detect Bot LID dari Mention | Done |
| Simpan LID ke botLid.json | Done |
| @mention Bot → Auto Reply | Done |
| Download Media | Done |
| React, Forward, Delete | Done |
| Support Ephemeral & View Once | Done |
| Anti-Ban | Done |
---

## Prasyarat

```bash
Node.js v20 atau lebih baru
NPM atau Yarn
WhatsApp (untuk pairing)
```

---

## Instalasi

```bash
# 1. Clone repo
git clone https://github.com/username/klepon-assistant.git
cd klepon-assistant

# 2. Install dependensi
npm install

# 3. (Opsional) Aktifkan corepack untuk Yarn v4
corepack enable
```

---

## Cara Menjalankan

### Mode Pairing Code (Rekomendasi)

```bash
npm start
```

> Bot akan meminta nomor HP (contoh: `6283151087954`)  
> Masukkan → dapatkan **4-digit code** → tautkan di WhatsApp

### Mode QR Code

Ubah di `index.js`:

```js
const USE_PAIRING = false; // ubah jadi false
```

Lalu jalankan:

```bash
npm start
```

> Scan QR di layar dengan WhatsApp

---

## Fitur Bot (Contoh)

| Perintah | Fungsi |
|--------|-------|
| `ping` | Bot balas "Pong!" |
| `!download` (reply media) | Download & kirim ulang media |
| `@196572801421410` | Bot balas "Ya, ada yang bisa dibantu?" |
| `@6283151087954` | Bot balas "Ya?!" |

---

## Struktur File

```
klepon-assistant/
├── index.js              → Main bot
├── serialize.js          → Message parser + helper
├── botLid.json           → (otomatis) Simpan LID bot
├── auth_session/         → (otomatis) Session login
├── package.json
└── README.md
```

---

## LID Bot? Apa Itu?

> **LID = Local Identifier** — ID baru WhatsApp (contoh: `196572801421410@lid`)  
> Gantikan nomor HP di grup besar untuk privasi.

Bot ini **otomatis detect LID kamu** saat di-mention:  
```
@196572801421410 → bot simpan sebagai LID → reply otomatis
```

LID disimpan di `botLid.json` → **tidak hilang saat restart**.

---

## Troubleshooting

| Masalah | Solusi |
|-------|--------|
| Bot tidak connect | Hapus folder `auth_session`, ulangi pairing |
| Mention tidak terdeteksi | Pastikan orang lain/kamu tag bot dulu, agar `@<LID>` terdeteksi |
| LID tidak tersimpan | Cek izin tulis folder (pastikan `botLid.json` bisa dibuat) |
| Error `signalRepository` | Normal, bot pakai fallback dari mention |

---

## Update & Kontribusi

```bash
git pull origin main
npm install
```

> Ingin tambah fitur? Fork → PR → kami review!

---

## Lisensi

[MIT License](LICENSE) — Bebas digunakan, modifikasi, dan distribusi.

---

## Support

- Issues: [GitHub Issues](https://github.com/huai-baituo/klepon-assistant/issues)
- Developer: `@HuaiBaituo` (WhatsApp)

---

**Bot ini dibuat dengan ❤️ menggunakan [Baileys](https://github.com/WhiskeySockets/Baileys)**
```

---

### File Tambahan: `package.json` (contoh)

```json
{
  "name": "klepon-assistant",
  "version": "1.0.0",
  "description": "WhatsApp Bot with LID Support",
  "main": "index.js",
  "type": "module",
  "scripts": {
    "start": "node index.js"
  },
  "dependencies": {
    "baileys": "^7.0.0",
    "@hapi/boom": "^10.0.1",
    "chalk": "^5.3.0",
    "pino": "^9.0.0",
    "pino-pretty": "^11.0.0",
    "qrcode-terminal": "^0.12.0"
  },
  "keywords": ["whatsapp", "bot", "baileys", "lid", "automation"],
  "author": "KleponDev",
  "license": "MIT"
}
```

---

### File `LICENSE` (MIT)

```txt
MIT License

Copyright (c) 2025 - 2026 Shanhaichu co. Ltd

Permission is hereby granted, free of charge, to any person obtaining a copy...
```

---

## LANGKAH AKHIR

1. **Buat repo GitHub baru**  
2. **Upload semua file:**  
   - `index.js`  
   - `serialize.js`  
   - `package.json`  
   - `README.md`  
   - `LICENSE`  
3. **Commit & push**

```bash
git init
git add .
git commit -m "Initial commit: Klepon Assistant Bot"
git branch -M main
git remote add origin https://github.com/huai-baituo/klepon-assistant.git
git push -u origin main
```
