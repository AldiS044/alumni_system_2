# 🎓 Alumni System — Universitas Muhammadiyah Malang

Sistem informasi pelacakan alumni berbasis web yang dibangun dengan **Python Flask** dan **SQLite**. Dirancang untuk melacak keberadaan alumni di berbagai platform digital serta menyimpan data karier dan kontak mereka.

---

## Link Publish Website
https://alumnisystem-2--aldisaputra044.replit.app

---

## ✨ Fitur Utama

- 🔐 **Sistem Login** — Akses dilindungi autentikasi, manajemen multi-user
- 👥 **Data Alumni** — 142.000+ data alumni dari berbagai fakultas & angkatan
- 🔍 **Pelacak Alumni** — Lacak per alumni atau batch massal
- 📋 **Detail Lengkap** — Sosial media, kontak, data pekerjaan per alumni
- 📊 **Laporan & Grafik** — Visualisasi distribusi fakultas, pekerjaan, lokasi
- ⚙️ **Pengaturan** — Manajemen pengguna dan password

### Data yang Dilacak
| Kategori | Data |
|---|---|
| Media Sosial | LinkedIn, Instagram, Facebook, TikTok |
| Kontak | Email, Nomor HP |
| Pekerjaan | Tempat bekerja, Alamat, Posisi/Jabatan |
| Jenis Kerja | PNS / Swasta / Wirausaha |
| Institusi | Sosial media tempat bekerja |

---

## 🛠️ Teknologi

| Layer | Teknologi |
|---|---|
| Backend | Python 3.x + Flask 3.0 |
| Database | SQLite3 |
| Frontend | HTML5, CSS3, JavaScript |
| Charts | Chart.js 4.4 |
| Fonts | Playfair Display + Plus Jakarta Sans |

---

## 📁 Struktur Proyek

```
alumni_system/
├── app.py                      # Flask backend — routing & logic
├── requirements.txt            # Dependensi Python
├── instance/
│   └── alumni_system.db        # SQLite database (142k+ alumni)
├── templates/
│   ├── base.html               # Layout utama + sidebar
│   ├── login.html              # Halaman login
│   ├── index.html              # Dashboard
│   ├── alumni.html             # Daftar alumni + pagination
│   ├── detail.html             # Detail & edit tracer per alumni
│   ├── add_alumni.html         # Form tambah alumni baru
│   ├── tracer.html             # Halaman pelacakan
│   ├── laporan.html            # Laporan & grafik
│   └── settings.html          # Manajemen pengguna
└── static/
    ├── css/
    │   └── style.css           # Design system — Warm Editorial
    └── js/
        └── main.js             # Toast, delete, chart defaults
```

---

## 🚀 Cara Menjalankan

### 1. Clone repository

```bash
git clone https://github.com/Aldis044/alumni_system.git
cd alumni_system_2
```

### 2. Install dependensi

```bash
pip install flask openpyxl
```

> Atau gunakan virtual environment:
> ```bash
> python -m venv venv
> source venv/bin/activate      # Mac/Linux
> venv\Scripts\activate         # Windows
> pip install flask openpyxl
> ```

### 3. Jalankan aplikasi

```bash
python app.py
```

### 4. Buka di browser

```
http://127.0.0.1:8000
```

> **Catatan untuk macOS:** Port 5000 digunakan oleh AirPlay Receiver. Aplikasi ini berjalan di port **8000** untuk menghindari konflik.

---

## 🔑 Default Login

| Username | Password |
|---|---|
| `admin` | `admin123` |

> ⚠️ Segera ganti password setelah login pertama melalui menu **Pengaturan**.

---

## 📸 Halaman Aplikasi

| Halaman | Deskripsi |
|---|---|
| **Dashboard** | Statistik ringkasan, grafik fakultas & jenis pekerjaan, aktivitas terbaru |
| **Data Alumni** | Tabel 142k+ alumni dengan filter fakultas, status lacak, dan pencarian nama |
| **Detail Alumni** | Profil lengkap + semua data tracer + form edit manual |
| **Pelacak** | Lacak per-alumni (live search) atau batch 50 sekaligus |
| **Laporan** | 5 grafik analitik: fakultas, pekerjaan, posisi, lokasi, prodi |
| **Pengaturan** | Ganti password, tambah/hapus user |

---

## 🗃️ Skema Database

```sql
-- Data master alumni (dari import Excel)
alumni (id, nama, nim, tahun_masuk, tanggal_lulus, fakultas, prodi, universitas)

-- Hasil pelacakan per alumni
tracer  (id, alumni_id, linkedin, instagram, facebook, tiktok,
         email, no_hp, tempat_bekerja, alamat_bekerja,
         posisi, jenis_pekerjaan, sosmed_tempat_bekerja, status)

-- Manajemen akun pengguna sistem
users   (id, username, password_hash, role)
```

---

## 🔒 Keamanan

- Password di-hash menggunakan **SHA-256** sebelum disimpan
- Semua route dilindungi `@login_required` decorator
- Session-based authentication dengan Flask secret key
- Proteksi hapus user sendiri (tidak bisa hapus akun aktif)

---

## ⚠️ Catatan

> Proses pelacakan pada sistem ini bersifat **simulasi** — menggunakan probabilitas acak untuk mensimulasikan pencarian di platform nyata. Untuk implementasi produksi, integrasikan dengan API resmi masing-masing platform (LinkedIn API, dll).

---

## 📄 Lisensi

Proyek ini dibuat untuk keperluan akademik — **Universitas Muhammadiyah Malang**.

---

<div align="center">
  <sub>Built with ❤️ for UMM Alumni Tracking System</sub>
</div>
