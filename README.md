# RoxShelf: panduan pasang ke GitHub + Netlify

Isi paket:
- `index.html`   : websitenya
- `assets.json`  : daftar aset (diubah lewat panel admin)
- `images/`      : gambar aset
- `admin/`       : panel admin (Decap CMS) di alamat `/admin`

## 1. Upload ke GitHub
1. Ekstrak file zip ini.
2. Di GitHub, buat repositori baru bernama `roxshelf`.
3. Klik "uploading an existing file", lalu seret SEMUA isi folder (index.html, assets.json, README.md, folder images dan admin). Klik Commit.
4. Buka `admin/config.yml` di GitHub (ikon pensil), ganti `USERNAME-GITHUB-KAMU` dengan username GitHub kamu, lalu commit.

## 2. Hubungkan ke Netlify
1. Di Netlify: Add new project, Import an existing project, pilih GitHub, lalu pilih repositori `roxshelf`.
2. Build command: kosongkan. Publish directory: kosongkan atau isi `.`
3. Klik Deploy. Catat alamat situsmu (misalnya https://namamu.netlify.app).

## 3. Buat login panel admin (GitHub OAuth)
1. GitHub: Settings, Developer settings, OAuth Apps, New OAuth App.
2. Homepage URL: alamat Netlify-mu. Authorization callback URL: https://api.netlify.com/auth/done
3. Simpan, lalu salin Client ID dan buat Client Secret.
4. Netlify: Project configuration, Access and security, OAuth, Authentication providers, Install provider (GitHub). Tempel Client ID dan Secret.

Nama menu di GitHub dan Netlify bisa sedikit berbeda dari tulisan ini. Kalau bingung, ikuti panduan resmi Decap CMS bagian "GitHub backend" dan "Netlify".

## 4. Pakai panel admin
1. Buka `alamat-situsmu/admin`, lalu Login with GitHub.
2. Pilih Katalog, Daftar aset. Tambah, edit, atau hapus aset, termasuk upload gambar.
3. Klik Publish. Semua perubahan di satu sesi tersimpan sekaligus, jadi tambahkan beberapa aset dulu baru Publish (hemat kredit Netlify).

## Catatan
- Kategori ada di dua tempat: `admin/config.yml` dan variabel `CATS` di `index.html`. Kalau menambah kategori, ubah keduanya.
- Kompres gambar (sekitar 100 sampai 300 KB) supaya hemat bandwidth.
- Link unduhan aset berbayar sebaiknya mengarah ke platform pembayaran, bukan Google Drive publik.
