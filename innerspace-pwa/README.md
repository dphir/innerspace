# InnerSpace (PWA)

Ruang refleksi pribadi. Semua catatan disimpan hanya di perangkat (penyimpanan browser). Tidak ada akun, server, analitik, atau permintaan ke situs lain (font memakai font sistem).

## Isi folder
- `index.html` — aplikasinya
- `manifest.webmanifest` — nama, ikon, dan mode layar penuh
- `service-worker.js` — menyimpan berkas di perangkat agar bisa dipakai tanpa internet
- `icons/` — ikon 192, 512, dan maskable

## Pasang di GitHub Pages
1. Buat repositori baru di GitHub (misalnya `innerspace`), publik atau privat sesuai paket akunmu.
2. Unggah **isi folder ini** (bukan folder pembungkusnya) ke cabang `main`.
3. Buka **Settings → Pages**. Pada *Build and deployment*, pilih **Deploy from a branch**, cabang `main`, folder `/ (root)`, lalu Save.
4. Tunggu 1–2 menit. Alamatnya: `https://NAMA-GITHUB.github.io/innerspace/`.

## Coba di Android
1. Buka alamat itu di Chrome.
2. Menu ⋮ → **Instal aplikasi** (atau *Tambahkan ke layar utama*).
3. Buka dari ikon di layar utama. Isi nama panggilan di tab **Saya**.
4. Uji offline: nyalakan mode pesawat, buka aplikasi, pastikan masih jalan dan catatan masih ada.

## Memperbarui aplikasi
Setiap kali `index.html` diubah, ganti angka versi di `service-worker.js` (sekarang `innerspace-v3`; naikkan ke `v4`, dst.). Tanpa itu, perangkat bisa terus memakai versi lama.

## Data
- Data tiap alamat web terpisah. Catatan di versi lain (misalnya halaman uji di claude.ai) tidak ikut pindah. Pakai **Saya → Ekspor** di versi lama, lalu **Impor** di versi baru.
- Data belum dienkripsi. Jangan memakai perangkat bersama untuk catatan sensitif.
- Menghapus data situs atau meng-uninstall bisa menghapus catatan. Buat cadangan JSON secara berkala.
- Repositori publik berarti kode terlihat publik, bukan catatanmu (catatan tidak pernah ada di repositori).

Alat refleksi, bukan diagnosis atau terapi.

## Hosting dari repositori privat (Cloudflare Pages atau Netlify)
GitHub Pages gratis hanya untuk repositori publik. Untuk menjaga repositori tetap privat, pakai Cloudflare Pages atau Netlify:
- Framework: None. Build command: kosong. Output/publish directory: `.` (root).
- `_headers` sudah disiapkan (CSP ketat, tanpa referrer, noindex) dan didukung keduanya.
- Ganti `[NAMA LENGKAP KAMU]` di `LICENSE` dan di komentar `index.html` dengan namamu.
- Kode di sisi browser tetap bisa dibaca siapa pun yang membuka situsnya; perlindungannya lewat lisensi, bukan kerahasiaan.
