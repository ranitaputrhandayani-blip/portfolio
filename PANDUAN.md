# Panduan Lengkap: Dari File Portofolio sampai Website Live (GitHub Pages)

Hasil akhir: website portofolio Anda online di alamat `https://USERNAME.github.io/portfolio/` dan gratis.

## Isi paket

```
portfolio/
├── index.html                      # halaman website utama
├── assets/                         # foto dan gambar proyek
├── Portofolio_Preview_Colab.ipynb  # notebook preview di Google Colab
└── PANDUAN.md                      # panduan ini
```

---

## Bagian 0 — Cek dan sesuaikan isi dulu

Buka `index.html` dengan Notepad/VS Code, lalu periksa:

1. **LinkedIn**: cari `USERNAME-ANDA` dan ganti dengan link LinkedIn Anda. Jika tidak punya, hapus baris tombol LinkedIn.
2. **Data pribadi**: demi privasi, website ini hanya menampilkan email dan area (Jakarta Selatan). Nomor telepon dan tanggal lahir sengaja tidak dicantumkan karena website publik bisa dibaca siapa saja. Tambahkan sendiri jika perlu.
3. **Tanggal pada CV**: di CV tertulis "Diandara Family Club, Agustus 2026 – Sekarang". Pastikan itu benar.
4. **Typo CV**: ada beberapa salah ketik di CV (misalnya "Desemberr", "admnistrasi", "terstuktur"). Perbaiki juga di file CV Anda.
5. **Proyek ilustrasi**: bagian "Proyek Design Ilustasi" di dokumen portofolio hanya berisi teks placeholder ("manmbduahje"). Di website saya ganti dengan deskripsi dari gambar poster Anda. Ubah jika kurang sesuai.
6. **Prototype Kepul Pintar**: saya hanya punya link Figma-nya tanpa penjelasan. Tambahkan deskripsi singkat (masalah, solusi, peran Anda) agar lebih kuat.

Saran konten: untuk dashboard Power BI dan Tableau, tambahkan screenshot ke folder `assets/` lalu tampilkan di `index.html`. Portofolio dengan visual jauh lebih meyakinkan.

---

## Bagian 1 — Preview di Google Colab

Colab dipakai untuk melihat hasil website sebelum diunggah.

### Cara A: upload ZIP (paling mudah, belum perlu GitHub)
1. Buka https://colab.research.google.com lalu login akun Google.
2. Klik **File → Upload notebook**, pilih `Portofolio_Preview_Colab.ipynb`.
3. Jalankan **Sel 1B** (tombol ▶), klik **Choose Files**, pilih `portfolio.zip`.
4. Jalankan **Sel 2**. Website tampil di dalam notebook.
5. Opsional: jalankan **Sel 3** untuk mengunduh `preview.html` (sudah berisi semua gambar).

### Cara B: ambil dari GitHub (setelah Bagian 3 selesai)
1. Ubah `GITHUB_USER = "USERNAME"` di Sel 1A dengan username GitHub Anda.
2. Jalankan Sel 1A lalu Sel 2.

Catatan: Colab hanya untuk preview. Website yang bisa diakses publik dibuat lewat GitHub Pages (Bagian 3 sampai 5).

---

## Bagian 2 — Siapkan akun dan tools

1. **Akun GitHub**: daftar di https://github.com/signup. Pilih username yang profesional, misalnya `ranitaputri`, karena akan muncul di URL.
2. Verifikasi email Anda.
3. Pilih salah satu cara upload:
   - **Jalur Mudah (tanpa instalasi)**: lewat browser. Lihat Bagian 3A.
   - **Jalur Git (disarankan untuk belajar)**: instal Git dari https://git-scm.com/downloads. Lihat Bagian 3B.

---

## Bagian 3 — Upload ke GitHub

### 3A. Jalur Mudah (lewat browser)

1. Login GitHub, klik tanda **+** di kanan atas, pilih **New repository**.
2. Isi:
   - **Repository name**: `portfolio`
   - **Public**
   - Centang **Add a README file**
3. Klik **Create repository**.
4. Di halaman repo, klik **Add file → Upload files**.
5. Ekstrak `portfolio.zip` di komputer. **Drag semua isinya**: `index.html` dan folder `assets` (folder ikut ter-upload jika Anda drag langsung dari file explorer).
6. Tulis pesan commit, misalnya `Tambah website portofolio`, lalu klik **Commit changes**.
7. Pastikan `index.html` ada di halaman utama repo, bukan di dalam subfolder.

### 3B. Jalur Git (command line)

Buka **Terminal** (Mac/Linux) atau **Git Bash** (Windows), lalu jalankan satu per satu:

```bash
# 1. Sekali saja: kenalkan diri ke Git
git config --global user.name "Ranita Putri Handayani"
git config --global user.email "email-akun-github@anda.com"

# 2. Masuk ke folder portofolio (sesuaikan lokasi)
cd path/ke/portfolio

# 3. Inisialisasi repo
git init
git branch -M main

# 4. Tambah dan simpan perubahan
git add .
git commit -m "Tambah website portofolio"

# 5. Hubungkan ke GitHub (repo kosong dibuat dulu di github.com/new, tanpa README)
git remote add origin https://github.com/USERNAME/portfolio.git

# 6. Kirim ke GitHub
git push -u origin main
```

Saat `git push`, GitHub meminta login. Karena password biasa tidak diterima, gunakan **Personal Access Token**:
1. GitHub → foto profil → **Settings → Developer settings → Personal access tokens → Tokens (classic) → Generate new token**.
2. Centang scope **repo**, lalu buat token dan salin.
3. Saat diminta password di terminal, tempel token tersebut.

---

## Bagian 4 — Aktifkan GitHub Pages

1. Buka repo `portfolio` di GitHub.
2. Klik tab **Settings** (ikon roda gigi).
3. Menu kiri: **Pages**.
4. Di bagian **Build and deployment**:
   - **Source**: `Deploy from a branch`
   - **Branch**: `main`, folder `/ (root)`
   - Klik **Save**.
5. Tunggu 1–3 menit lalu refresh halaman Pages. Akan muncul tulisan *"Your site is live at https://USERNAME.github.io/portfolio/"*.
6. Buka link itu. Selesai, website Anda sudah online.

---

## Bagian 5 — Mengecek hasil

Checklist:
- [ ] Foto dan semua gambar proyek muncul
- [ ] Semua tombol link (Figma, Maze, PDF, email) bisa dibuka
- [ ] Tampilan rapi di HP (buka dari ponsel)
- [ ] Tidak ada typo
- [ ] Link LinkedIn sudah diganti

**Jika halaman 404:** pastikan `index.html` berada di root repo dan namanya huruf kecil semua. Tunggu beberapa menit lalu coba lagi.
**Jika gambar tidak muncul:** nama folder harus `assets` (huruf kecil) dan nama file harus sama persis, karena GitHub membedakan huruf besar dan kecil.

---

## Bagian 6 — Update di kemudian hari

**Lewat browser:** buka file di repo → klik ikon pensil ✏️ → edit → **Commit changes**. Website ikut berubah dalam 1–2 menit.

**Lewat Git:**
```bash
git add .
git commit -m "Update proyek baru"
git push
```

---

## Bagian 7 — Opsional

### URL yang lebih pendek
Jika nama repo diubah menjadi `USERNAME.github.io` (persis, sesuai username), alamatnya menjadi `https://USERNAME.github.io/` tanpa `/portfolio/`.

### Domain sendiri (misalnya ranitaputri.com)
1. Beli domain di penyedia seperti Niagahoster, Namecheap, atau Cloudflare.
2. Di GitHub: **Settings → Pages → Custom domain**, isi domain Anda lalu **Save**.
3. Di pengaturan DNS domain, tambahkan record `A` ke `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`, dan `CNAME` untuk `www` ke `USERNAME.github.io`. Cek alamat IP terbaru di dokumentasi resmi GitHub Pages sebelum mengisi.
4. Centang **Enforce HTTPS** setelah domain terverifikasi.

### Tips agar dilirik rekruter
- Taruh link website di CV, LinkedIn, dan bio email.
- Tambahkan screenshot dashboard Power BI dan Tableau.
- Di tiap proyek, tulis jelas **masalah, peran Anda, proses, dan hasil**. Bagian Smart Booking Flow sudah memakai pola ini, tinggal ikuti untuk proyek lain.
