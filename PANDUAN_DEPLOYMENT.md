# Panduan Lengkap Deploy Geotag Photo Editor

## 🚀 Pilihan Deployment (Urutkan dari Termudah)

---

## OPSI 1: Vercel (Rekomendasi - Gratis, Tercepat)

### Kelebihan:
- ✅ Gratis selamanya (untuk project personal)
- ✅ Domain gratis: nama-anda.vercel.app
- ✅ Deploy super cepat (hanya 1 klik)
- ✅ CDN global (cepat di seluruh dunia)
- ✅ Auto-deploy dari GitHub

### Langkah-langkah:

1. **Buat akun Vercel**
   - Buka https://vercel.com
   - Sign up dengan GitHub / Google / Email
   - Ikuti verifikasi email

2. **Upload project ke GitHub (Opsional tapi recommended)**
   ```bash
   # Jika belum install Git, download di https://git-scm.com
   
   cd /folder/project
   git init
   git add .
   git commit -m "Initial commit"
   git remote add origin https://github.com/USERNAME/photo-editor.git
   git push -u origin main
   ```

3. **Deploy ke Vercel**
   - Login ke Vercel
   - Klik "New Project"
   - Import repository GitHub (atau upload folder)
   - Framework: "Other" (karena ini static HTML)
   - Build command: kosongkan
   - Output directory: . (root)
   - Klik Deploy!

4. **Hasilnya**
   ```
   URL: https://nama-anda.vercel.app
   ```

---

## OPSI 2: Netlify (Gratis, User-Friendly)

### Kelebihan:
- ✅ Gratis
- ✅ Drag-drop upload file (paling mudah!)
- ✅ Domain gratis: nama-anda.netlify.app

### Langkah-langkah:

1. **Buka Netlify**
   - https://app.netlify.com
   - Sign up dengan GitHub / Google / Email

2. **Upload File**
   - Klik "New site from Git" atau "Drag to deploy"
   - Pilih folder project Anda
   - Atau drag-drop file index.html langsung ke area yang ditunjuk
   - Tunggu deploy selesai

3. **Hasilnya**
   ```
   URL: https://nama-acak.netlify.app
   (bisa diganti dengan nama custom)
   ```

4. **Ganti Domain (Opsional)**
   - Settings > Domain
   - Klik "Change site name"
   - Masukkan nama yang diinginkan

---

## OPSI 3: GitHub Pages (Gratis, untuk GitHub Users)

### Kelebihan:
- ✅ Gratis
- ✅ Domain: username.github.io/photo-editor
- ✅ Langsung dari GitHub repo

### Langkah-langkah:

1. **Buat GitHub Repository**
   - Login ke GitHub
   - Klik "New repository"
   - Nama: "photo-editor"
   - Pilih "Public"
   - Klik "Create repository"

2. **Upload File**
   ```bash
   git clone https://github.com/USERNAME/photo-editor.git
   cd photo-editor
   cp photo-geotag-editor.html index.html
   git add .
   git commit -m "Add photo editor"
   git push origin main
   ```

3. **Enable GitHub Pages**
   - Buka repository settings
   - Cari "Pages" di sidebar kiri
   - Source: "Deploy from a branch"
   - Branch: "main" / folder: "/ (root)"
   - Klik Save

4. **Hasilnya**
   ```
   URL: https://USERNAME.github.io/photo-editor
   ```

---

## OPSI 4: Niagahoster (Shared Hosting - Murah)

### Kelebihan:
- ✅ Domain gratis
- ✅ Support Indonesia
- ✅ Murah (Rp 100k/tahun)
- ✅ Shared hosting semua-in-one

### Langkah-langkah:

1. **Beli Hosting + Domain**
   - Buka https://www.niagahoster.co.id
   - Pilih paket hosting (mulai dari Rp 30k/bulan)
   - Atau beli domain Rp 79k/tahun
   - Selesaikan pembayaran

2. **Login ke Control Panel**
   - Buka https://hosting.niagahoster.co.id
   - Login dengan email & password

3. **Upload File via FTP/cPanel**
   - Di cPanel, buka "File Manager"
   - Buka folder "public_html"
   - Upload file index.html (rename ke "index.html")
   - Pastikan nama file tepat!

4. **Akses Website**
   ```
   URL: https://domain-anda.com
   atau https://domain-anda.id
   ```

---

## OPSI 5: InfinityFree (Gratis Selamanya)

### Kelebihan:
- ✅ 100% GRATIS selamanya
- ✅ Subdomain gratis
- ✅ Tidak perlu kartu kredit

### Langkah-langkah:

1. **Buat Akun**
   - https://www.infinityfree.net
   - Sign up (gratis, tidak perlu kartu kredit)

2. **Buat Hosting**
   - Create Account
   - Pilih nama domain gratis (contoh: fotoedit.infinityfreeapp.com)
   - Klik Generate

3. **Upload File**
   - Buka File Manager
   - Upload index.html ke folder "public_html"

4. **Hasilnya**
   ```
   URL: https://fotoedit.infinityfreeapp.com
   ```

---

## OPSI 6: AWS / Google Cloud (Professional)

### Kelebihan:
- ✅ Scalable
- ✅ Performa tinggi
- ✅ Enterprise-grade

### Langkah-langkah:

**AWS S3 + CloudFront:**
```bash
# Install AWS CLI
npm install -g aws-cli

# Configure
aws configure

# Upload
aws s3 sync . s3://nama-bucket-anda

# Enable static hosting di S3 settings
```

**Google Cloud Storage:**
```bash
# Install Google Cloud SDK
# Upload file ke Cloud Storage bucket
# Enable static website hosting

gsutil -m cp index.html gs://bucket-name/
gsutil web set -m index.html -e index.html gs://bucket-name/
```

---

## 🌐 Membeli Domain Custom

Jika ingin domain sendiri (contoh: fotoedit.com), tidak harus warna-warni:

### Provider Domain Indonesia:
- **Niagahoster** - Rp 79k - 500k/tahun
- **IDwebhost** - Rp 75k - 400k/tahun
- **Rumahweb** - Rp 80k - 450k/tahun

### Provider Domain Internasional:
- **Namecheap** - $0.99 - $12/tahun
- **GoDaddy** - $1.17 - $15/tahun
- **Google Domains** - $12/tahun

### Langkah Menghubungkan Domain:

1. **Beli domain**
2. **Login ke provider domain**
3. **Cari "Nameserver" atau "DNS Settings"**
4. **Sesuaikan dengan nameserver hosting Anda:**

**Untuk Vercel:**
```
ns-1.vercel.com
ns-2.vercel.com
```

**Untuk Netlify:**
```
dns1.p01.nsone.net
dns2.p01.nsone.net
dns3.p01.nsone.net
dns4.p01.nsone.net
```

**Untuk Niagahoster:**
(Lihat di control panel Niagahoster)

5. **Tunggu 24-48 jam untuk propagasi**
6. **Selesai!**

---

## 📋 Checklist Deployment

- [ ] Sudah download file `photo-geotag-editor.html`
- [ ] Sudah setup akun hosting (Vercel/Netlify/GitHub Pages)
- [ ] Sudah upload file ke hosting
- [ ] Website bisa diakses dari browser
- [ ] Coba fitur: upload foto, hapus geotag, tambah geotag
- [ ] Coba download foto hasil edit
- [ ] Share URL ke teman

---

## 🔧 Troubleshooting

### Website tidak muncul
- Pastikan file bernama `index.html`
- Cek browser cache (Ctrl+Shift+Delete)
- Tunggu 5 menit untuk DNS propagasi

### File tidak bisa upload
- Pastikan format file JPG/PNG
- Cek size file (max 50MB)
- Reload page dan coba lagi

### Geotag tidak tersimpan
- File harus format JPG (PNG tidak support EXIF fully)
- Download file setelah edit
- Cek EXIF data dengan tools online

### Domain tidak connect
- Tunggu 24-48 jam propagasi
- Cek nameserver sudah benar di provider domain
- Clear browser cache

---

## 💡 Tips Optimal

1. **Untuk Pemula:** Gunakan Netlify (paling mudah, drag-drop)
2. **Untuk GitHub User:** Gunakan GitHub Pages (gratis, terintegrasi)
3. **Untuk Custom Domain:** Pakai Vercel + domain custom
4. **Untuk Jangka Panjang:** Niagahoster (terintegrasi domain + hosting)
5. **Untuk Budget Minimal:** InfinityFree (gratis selamanya)

---

## 📞 Support & Updates

Jika ada error saat deploy:
1. Baca error message dengan teliti
2. Google error message tersebut
3. Cek dokumentasi hosting resmi
4. Tanya di community (GitHub Issues, Stack Overflow)

Untuk update fitur:
1. Edit file `photo-geotag-editor.html`
2. Re-upload ke hosting
3. Refresh browser (Ctrl+F5)

---

## 🎉 Selesai!

Website Anda sudah live! Sekarang:
- ✅ Share ke teman & keluarga
- ✅ Tambah fitur baru sesuai kebutuhan
- ✅ Monitor traffic & feedback pengguna
- ✅ Improve UX berdasarkan feedback

Good luck! 🚀
