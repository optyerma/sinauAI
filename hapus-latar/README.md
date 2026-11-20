# Hapus Latar

Web app (PWA) untuk menghapus latar belakang foto dan memangkas orangnya saja. Semua proses berjalan di browser dengan AI (MediaPipe Image Segmenter). Foto tidak diunggah ke server mana pun.

## Fitur
- **Deteksi orang otomatis**, dalam dua tahap. Tahap pertama mendeteksi di seluruh foto, lalu tahap kedua mengulanginya di sekitar orang supaya tepi orang yang kecil di dalam bingkai tetap detail.
- **Rapikan tepi**: tepi topeng (mask) dirapatkan ke kontur rambut dan baju dengan *guided filter* berwarna.
- **Pangkas ke orang**: area kosong di sekitar orang dibuang. Rasio bisa Bebas, 1:1, 3:4 (pas foto), 4:5, 2:3, atau 9:16, dan jarak tepinya bisa diatur. Pada rasio tetap, bingkai dipusatkan ke kepala.
- **Latar**: transparan, putih, merah atau biru (pas foto), abu-abu, hitam, warna pilihan sendiri, atau foto asli yang diburamkan.
- **Kuas koreksi**: *Hapus* untuk membuang sisa latar dan *Kembalikan* untuk memulihkan bagian yang ikut terhapus. Tersedia juga *Urungkan* dan tombol *Tahan: asli* untuk membandingkan dengan foto asli.
- **Hanya orang utama**: membuang orang lain yang ikut terdeteksi.
- Hasil bisa diunduh sebagai PNG atau dibagikan langsung lewat menu Bagikan di ponsel.
- Mendukung mode gelap. Setelah pemakaian pertama, aplikasi bisa dibuka offline.

## Menjalankan
Tidak perlu build. Sajikan folder ini lewat HTTPS, misalnya dengan **GitHub Pages**: buka `https://<username>.github.io/sinauAI/hapus-latar/`, lalu di iPhone ketuk **Bagikan → Tambah ke Layar Utama**.

Untuk mencoba di komputer, jalankan `python3 -m http.server` di folder ini lalu buka `http://localhost:8000`.

Saat pertama kali dipakai, aplikasi mengunduh library MediaPipe dari jsDelivr dan model `selfie_multiclass_256x256` (±16 MB) dari Google. Setelah itu keduanya disimpan oleh service worker.

## Tips
- Pakai foto yang orangnya terlihat jelas dan kontras dengan latar.
- Jika ada sisa latar, geser **Ambang** ke kanan atau pakai kuas **Hapus**. Jika bagian tubuh ikut hilang, geser ke kiri atau pakai **Kembalikan**.
- Hasil maksimal 2048 px di sisi terpanjang.

## Berkas
| Berkas | Isi |
|---|---|
| `index.html` | Seluruh tampilan dan logika (segmentasi, perapian tepi, pangkas, kuas) |
| `manifest.webmanifest` | Nama, ikon, dan mode tampilan saat dipasang |
| `sw.js` | Service worker: cache aplikasi, library, dan model untuk akses offline |
| `icons/` | Ikon aplikasi |
