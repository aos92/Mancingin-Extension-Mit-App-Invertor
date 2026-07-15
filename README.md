# 🎣 Mancingin Extension — MIT App Inventor

Kumpulan 4 extension **MIT App Inventor / Kodular** untuk membangun aplikasi manajemen **lomba mancing (galatama)** — mulai dari database SQLite, tampilan denah lapak, menu kantin, hingga tabel data otomatis.

[![Dokumentasi](https://img.shields.io/badge/docs-GitHub%20Pages-0f7a8c?style=flat-square&logo=github)](https://aos92.github.io/Mancingin-Extension-Mit-App-Invertor/Mancingin.html)
[![Platform](https://img.shields.io/badge/platform-MIT%20App%20Inventor%20%7C%20Kodular-ff7a3d?style=flat-square)](#)
[![License](https://img.shields.io/badge/license-GPLv3-1fb6b0?style=flat-square)](#lisensi)

---

## 📚 Dokumentasi Lengkap

Setiap extension punya halaman dokumentasi sendiri (properties, events, methods, contoh SQL) — live di GitHub Pages:

| Extension | Deskripsi Singkat | Dokumentasi |
|---|---|---|
| 🐟 **MancinginExtension** | Extension database SQLite inti — skema lomba mancing, transaksi, klasemen, timbangan | [Mancingin.html](https://aos92.github.io/Mancingin-Extension-Mit-App-Invertor/Mancingin.html) |
| 🟦 **LapakCanvasExtension** | Menggambar denah lapak 2 kolom dengan kolam di tengah (kosong/terisi) | [LapakCanvas.html](https://aos92.github.io/Mancingin-Extension-Mit-App-Invertor/LapakCanvas.html) |
| 🍗 **MenuGalatama** | Kelola menu kantin bergambar + checkbox & qty + proses order | [MenuGalatama.html](https://aos92.github.io/Mancingin-Extension-Mit-App-Invertor/MenuGalatama.html) |
| 📊 **TableGalatama** | Menampilkan hasil query sebagai tabel otomatis (header, nomor, warna selang-seling) | [TableGalatama.html](https://aos92.github.io/Mancingin-Extension-Mit-App-Invertor/TableGalatama.html) |

> 💡 Keempat halaman saling terhubung lewat nav bar di bagian atas, jadi kamu bisa berpindah antar dokumentasi tanpa kembali ke sini.

---

## 🧩 Ringkasan Tiap Extension

### 1. MancinginExtension
Extension database SQLite yang jadi **fondasi** seluruh aplikasi lomba mancing. Menyediakan kemampuan generik SQLite (Select, SelectSQL, Insert, Update, dst.) sekaligus blok-blok fungsional tingkat tinggi khusus domain lomba mancing (pendaftaran peserta, sesi/babak, input timbangan ikan, transaksi kantin/kas, klasemen live).

- **3** Properties · **15** Events · **35** Methods
- Database default: `mancing.db` — dipakai bersama oleh 3 extension lain di bawah ini

### 2. LapakCanvasExtension
Extension non-visible pendamping `MancinginExtension`. Tugasnya satu: mengambil output "List of Lists" (daftar lapak kosong & `jumlah_lapak`) lalu menggambarkannya sebagai denah 2 kolom dengan kolam di tengah, lengkap indikator warna kosong/terisi.

- **9** Properties · **3** Events · **6** Methods

### 3. MenuGalatama
Menggabungkan upload gambar menu, daftar menu bergambar dengan checkbox & qty, serta proses order — semuanya bekerja langsung di atas `mancing.db` yang sama dengan `MancinginExtension`. Order tersimpan dalam satu transaksi database yang atomik.

- **9** Properties · **7** Events · **14** Methods

### 4. TableGalatama
Menerima hasil query (YailList / List-of-Lists) dari `MancinginExtension` dan langsung menampilkannya sebagai tabel rapi — header, baris bernomor, format Rupiah/kg/tanggal, warna selang-seling — tanpa blok "for each" manual. Termasuk `TampilkanOtomatis()` untuk query apa pun di luar 15 bentuk tabel baku.

- **10** Properties · **3** Events · **16** Methods

---

## 🚀 Cara Pakai (App Inventor / Kodular)

1. Unduh berkas `.aix` masing-masing extension dari [Releases](../../releases) dan import ke project App Inventor/Kodular.
2. Letakkan `MancinginExtension1` di Screen, atur `DatabaseName` (default `mancing.db`).
3. Tambahkan `LapakCanvasExtension`, `MenuGalatama`, dan/atau `TableGalatama` sesuai kebutuhan — pastikan `DatabaseName` sama agar mengacu ke berkas database yang sama.
4. Panggil method `Tampilkan...()` / `SelectSQL()` sesuai contoh SQL yang didokumentasikan di masing-masing halaman dokumentasi di atas.

---

## 🗂️ Struktur Repo

```
├── docs/                    # Halaman dokumentasi (GitHub Pages)
│   ├── Mancingin.html
│   ├── LapakCanvas.html
│   ├── MenuGalatama.html
│   ├── TableGalatama.html
│   └── assets/
│       ├── logo.png
│       └── SevenSegment.ttf
├── assets/                  # Sumber asset (logo & font)
│   ├── logo.png
│   └── SevenSegment.ttf
├── extensions/               # Berkas .aix
│   ├── com.omanasep.mancingin.aix
│   ├── com.omanasep.lapakcanvas.aix
│   ├── com.omanasep.menugalatama.aix
│   └── com.omanasep.tablegalatama.aix
└── README.md
```

### Mengaktifkan GitHub Pages
1. Buka **Settings → Pages** pada repo ini.
2. Pilih **Branch: main** dan folder **`/docs`**.
3. Simpan — situs akan tersedia di `https://aos92.github.io/Mancingin-Extension-Mit-App-Invertor/`.

---

## 🤝 Kontribusi
Pull request & issue sangat diterima — baik untuk perbaikan dokumentasi, penambahan method baru, maupun laporan bug pada extension.

## 📄 Lisensi
[GNU General Public License v3.0 (GPL-3.0)](LICENSE) — bebas digunakan, dipelajari, dimodifikasi, dan didistribusikan ulang, dengan syarat: setiap turunan/redistribusi (termasuk versi modifikasi) tetap dilisensikan GPL-3.0 dan source code-nya tetap terbuka.

---

<p align="center">Dibuat untuk komunitas lomba mancing (galatama) Indonesia 🇮🇩</p>
