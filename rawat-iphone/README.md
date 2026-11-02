# Rawat iPhone

Web app (PWA) pengingat perawatan iPhone. Bisa dipasang di layar utama iPhone seperti aplikasi biasa, tanpa App Store dan tanpa Mac.

## Fitur
- **Rutin**: tugas mingguan & bulanan (restart, update app, bersihkan Safari, WhatsApp, foto duplikat, dll.). Setelah dicentang, tugas muncul lagi saat jadwalnya tiba.
- **Sekali Atur**: pengaturan iOS yang cukup diatur sekali (Kurangi Gerakan, Refresh App di Latar Belakang, Layanan Lokasi, dll.), lengkap dengan jalur menunya.
- **Baterai**: catat Kapasitas Maksimum tiap bulan dan lihat grafiknya terhadap batas 80%.
- **Memori**: hitung persentase ruang kosong dan dapatkan saran.
- Skor perawatan di bagian atas, mode gelap otomatis, bisa dibuka offline.

Semua data tersimpan di perangkat (localStorage), tidak dikirim ke mana pun.

## Menjalankan
Tidak perlu build. Cukup sajikan folder ini lewat HTTPS, misalnya dengan **GitHub Pages**:

1. GitHub → repositori ini → **Settings → Pages**.
2. *Source*: **Deploy from a branch**, pilih branch ini dan folder `/ (root)`, lalu **Save**.
3. Buka `https://<username>.github.io/sinauAI/rawat-iphone/` di **Safari** iPhone.
4. Ketuk **Bagikan → Tambah ke Layar Utama**.

Untuk mencoba di komputer: `python3 -m http.server` di folder ini, lalu buka `http://localhost:8000`.

## Berkas
| Berkas | Isi |
|---|---|
| `index.html` | Seluruh tampilan & logika aplikasi |
| `manifest.webmanifest` | Nama, ikon, dan mode tampilan saat dipasang |
| `sw.js` | Service worker untuk akses offline |
| `icons/` | Ikon aplikasi (termasuk `apple-touch-icon.png` untuk iPhone) |
