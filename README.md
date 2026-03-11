# Gate-Of-THR
Slot game gacha berbasis web untuk bagi-bagi THR Lebaran, terinspirasi dari Gates of THR). Dibangun dengan HTML, CSS, dan Vanilla JavaScript murni — tanpa framework, tanpa dependency.

# ⚡ Gates of THR — Lebaran Edition

---

## 🎮 Demo

Buka langsung file `index.html` di browser — tidak perlu server, tidak perlu install apapun.

---

## ✨ Fitur Utama

### 🎰 Gameplay
- **Grid 6×5** — 30 simbol yang tersusun rapi di arena permainan
- **Cluster Pays** — menang bukan dari payline, tapi dari 4+ simbol yang sama saling terhubung (adjacent)
- **Tumble / Cascade** — simbol yang menang meledak, simbol baru jatuh dari atas mengisi ruang kosong, chain bisa terus berlanjut
- **Multiplier Stack** — setiap cascade sukses meningkatkan multiplier (×2 → ×3 → ×5 → ×8 → ×10...)
- **5 Spins** per sesi dengan pip tracker koin

### 🎁 Sistem Hadiah (Fully Predetermined)
Inilah yang membuat proyek ini jujur dan aman dipakai untuk bagi-bagi THR:

- Saat sesi dimulai, engine **memilih tepat satu** dari tiga tier hadiah:
  - 🟢 **Rp 10.000**
  - 🟡 **Rp 20.000**
  - 🔴 **Rp 30.000**
- Total hadiah **tidak bisa lebih dan tidak bisa kurang** dari tier yang dipilih
- Visual (cluster muncul, simbol berputar, multiplier naik) adalah **gimik dramatis** semata
- Spin ke-1 & ke-3 selalu zonk untuk efek drama, spin ke-2 & ke-4 menghasilkan hadiah terbesar
- Rekonsiliasi otomatis di spin terakhir memastikan total akhir **persis** sesuai target

### 🎬 Animasi
- Simbol **jatuh dari atas** dengan physics bounce (bukan kedip biasa)
- Stagger per kolom kiri → kanan, dalam kolom atas → bawah
- Cluster menang berdenyut & meledak dengan partikel
- Burst text `+5K`, `+12K` muncul di tengah cluster
- Confetti hijau saat menang besar
- Modal **BIG WIN / MEGA WIN** dengan animasi pop

---

## 📊 Tabel Simbol & Hadiah

| Simbol | Nama | Cluster 4 | Cluster 6 | Cluster 8 | Cluster 12 |
|--------|------|-----------|-----------|-----------|------------|
| 🎁 | Amplop | Rp 500 | Rp 1.500 | Rp 3.000 | Rp 8.000 |
| 🌙 | Bulan | Rp 300 | Rp 1.000 | Rp 2.500 | Rp 7.000 |
| ⭐ | Bintang | Rp 150 | Rp 500 | Rp 1.500 | Rp 4.000 |
| 🏮 | Lentera | Rp 80 | Rp 250 | Rp 800 | Rp 1.600 |
| 🌛 | Sabit | Rp 40 | Rp 130 | Rp 400 | Rp 800 |

> Nilai di atas dikali multiplier aktif saat cascade berlangsung.

---

## 🚀 Cara Pakai

### 1. Clone repo
```bash
git clone https://github.com/username/gates-of-thr.git
cd gates-of-thr
```

### 2. Buka di browser
```bash
# Cukup klik dua kali index.html, atau:
open index.html          # macOS
start index.html         # Windows
xdg-open index.html      # Linux
```

Tidak perlu `npm install`, tidak perlu server lokal. Pure HTML.

---

## ⚙️ Konfigurasi

Semua konfigurasi ada di blok `CONFIG` di dalam `<script>` pada `index.html`:

```js
// Tier hadiah yang bisa keluar — ubah sesuai kebutuhan
const PRIZE_TIERS = [10000, 20000, 30000];

// Jumlah spin per sesi
const MAX_SPINS = 5;

// Distribusi hadiah per spin (index 0-4)
// 0 = zonk, angka lain = bobot relatif
const weights = [0, 4, 0, 5, 1];
```

### Contoh kustomisasi:

**Ubah tier hadiah jadi 5K / 15K / 25K:**
```js
const PRIZE_TIERS = [5000, 15000, 25000];
```

**Tambah spin jadi 7x:**
```js
const MAX_SPINS = 7;
```

**Semua spin bisa menang (tanpa zonk):**
```js
const weights = [1, 3, 1, 4, 2]; // semua > 0
```

---

## 📁 Struktur File

```
gates-of-thr/
└── index.html      ← Semua kode dalam satu file (HTML + CSS + JS)
└── README.md       ← Dokumentasi ini
```

Sengaja dibuat single-file agar mudah di-share dan di-deploy ke mana saja (GitHub Pages, langsung kirim via WA, dsb).

---

## 🌐 Deploy ke GitHub Pages

1. Push repo ke GitHub
2. Masuk ke **Settings → Pages**
3. Source: pilih branch `main`, folder `/ (root)`
4. Klik **Save**
5. Akses via `https://username.github.io/gates-of-thr`

---

## 🛠️ Tech Stack

| Teknologi | Penggunaan |
|-----------|------------|
| HTML5 | Struktur & layout |
| CSS3 | Animasi, tema hijau, grid layout |
| Vanilla JS | Game engine, BFS cluster finder, prize system |
| Canvas API | Background nebula & bintang animasi |
| Google Fonts | Cinzel Decorative, Baloo 2 |

Tidak ada framework. Tidak ada library. Tidak ada build step.

---

## 🎨 Desain

- **Tema warna:** Deep forest green (`#010f04`) dengan aksen neon green (`#4dff88`)
- **Font display:** Cinzel Decorative (serif klasik bergaya game)
- **Inspirasi visual:** Gates of Olympus — Pragmatic Play
- **Background:** Procedural nebula hijau dirender via Canvas 2D

---

## ⚠️ Disclaimer

Proyek ini dibuat **hanya untuk hiburan** dalam konteks bagi-bagi THR Lebaran di lingkungan keluarga/kantor. Hadiah bersifat **predetermined** (sudah ditentukan sebelum permainan) — bukan perjudian sungguhan. Tidak ada uang sungguhan yang diproses oleh aplikasi ini.

---

## 📄 Lisensi

MIT License — bebas digunakan, dimodifikasi, dan didistribusikan.

---

<div align="center">
  <b>Selamat Hari Raya Idul Fitri 🌙</b><br>
  <i>Minal Aidin Wal Faizin — Mohon Maaf Lahir & Batin</i>
</div>
