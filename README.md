# PT Quanta Indonesia — Website Package

## ⚠️ PENTING — Cara Membuka Website

**Jangan pindahkan file HTML secara terpisah dari folder `assets/`.**
Semua gambar (logo, foto kapal) sekarang berupa **file terpisah**, bukan lagi base64 di dalam HTML. Artinya file HTML butuh folder `assets/` persis di sebelahnya agar semua gambar muncul.

**Struktur yang benar:**
```
📁 (folder manapun)
├── quanta_website_english.html   ← Homepage
├── gallery.html                   ← Halaman Galeri
└── assets/                        ← WAJIB ada di folder yang sama
    ├── logo_quanta_full.png
    ├── logo_quanta_icon.png
    ├── logos/                     (13 logo klien)
    └── ships/                     (foto kapal & operasional)
```

**Cara membuka:** Extract seluruh isi ZIP ke satu folder, lalu buka `quanta_website_english.html` langsung dua kali klik. Jangan hanya download HTML-nya saja.

**Catatan soal nama file:** Jika browser Anda otomatis mengganti nama file saat download (misalnya menjadi `quanta_website_english (2).html`), silakan **rename kembali** ke nama aslinya (`quanta_website_english.html`) atau hapus dulu file lama di folder Downloads Anda. Kedua halaman saling me-link menggunakan nama file asli — jika nama berubah, tombol navigasi antar halaman (Gallery ↔ Homepage) tidak akan berfungsi.

---

## 📁 Struktur Folder Assets

```
assets/
├── logo_quanta_full.png     → Logo lengkap PT Quanta Indonesia (dengan wordmark), dipakai di navbar & footer
├── logo_quanta_icon.png     → Icon Q saja, dipakai untuk watermark besar di pojok halaman
│
├── logos/                   → Logo 13 klien (PNG transparan, sudah di-crop rapat)
│   ├── banpu.png
│   ├── cemindo.png
│   ├── sle.png                              (PT Sentosa Laju Energy)
│   ├── sumber_daya_alam_mullia.png
│   ├── manoor_bulatn_lestari.png
│   ├── rencana_mulia_baratama.png
│   ├── pelayaran_brawijaya_maritim.png
│   ├── artha_yuta.png
│   ├── bumi_laut_shipping_service.png
│   ├── global_energi_lestari.png
│   ├── baramulti_sukses_sarana.png
│   ├── global_trans_energi_internasional.png
│   └── bainra_lautan_utama.png
│
└── ships/                   → Foto kapal & operasional (semua foto ASLI dari klien)
    ├── hero_unloading.jpg           → Hero banner (foto "Unloading Process")
    ├── about_taurians.jpg           → Section About, foto utama
    ├── about_mini_max_christo.jpg   → Section About, foto kecil kiri
    ├── about_mini_bulesko.jpg       → Section About, foto kecil kanan
    ├── fleet_gal_big_max_christo.jpg → Fleet gallery, foto besar kiri
    ├── fleet_gal_taurians_sunset.jpg → Fleet gallery
    ├── fleet_gal_indomarina.jpg      → Fleet gallery
    ├── fleet_gal_bulesko_river.jpg   → Fleet gallery
    ├── fleet_gal_bulesko_crane.jpg   → Fleet gallery
    ├── card_max_christo.jpg          → Thumbnail kartu spesifikasi TB Max Christo 07
    ├── card_taurians.jpg             → Thumbnail kartu spesifikasi TB Taurians One
    ├── card_bulesko.jpg              → Thumbnail kartu spesifikasi BG Bulesko II
    ├── card_indomarina.jpg           → Thumbnail kartu spesifikasi BG Indomarina 3002
    ├── full_max_christo.jpg          → Foto ukuran penuh (untuk klik-perbesar/lightbox)
    ├── full_taurians.jpg             → Foto ukuran penuh (untuk klik-perbesar/lightbox)
    ├── full_bulesko.jpg              → Foto ukuran penuh (untuk klik-perbesar/lightbox)
    ├── full_indomarina.jpg           → Foto ukuran penuh (untuk klik-perbesar/lightbox)
    ├── contact_bg.jpg                → Background section Contact
    │
    └── gallery_*.jpg (11 file)       → Semua foto untuk halaman Gallery terpisah:
        ├── gallery_unloading.jpg
        ├── gallery_max_christo.jpg
        ├── gallery_taurians_1.jpg
        ├── gallery_taurians_2.jpg
        ├── gallery_bulesko_1.jpg  s/d  gallery_bulesko_5.jpg
        └── gallery_indomarina_1.jpg, gallery_indomarina_2.jpg
```

---

## 🔄 Cara Mengganti / Menambah Foto

### Mengganti foto kapal yang sudah ada
1. Siapkan foto baru dengan kualitas HD (disarankan minimal 1200px pada sisi terpanjang)
2. Beri nama file **PERSIS SAMA** dengan file yang ingin diganti (contoh: `card_max_christo.jpg`)
3. Replace file lama di folder `assets/ships/` dengan file baru
4. Refresh browser — otomatis berubah, tidak perlu edit HTML

### Menambah foto baru ke halaman Gallery
1. Simpan foto baru ke folder `assets/ships/` dengan nama unik (misal `gallery_new_photo.jpg`)
2. Buka `gallery.html` dengan text editor, cari bagian `GALLERY_ITEMS` di dalam kode Python (jika generate ulang) **atau** cari langsung blok `<div class="gitem"...>` di HTML dan duplikasi salah satu blok, ganti `src`, `title`, dan `cap` sesuai foto baru
3. Simpan file

### Menambah logo klien baru
1. Siapkan logo dalam format PNG transparan (background bening), resolusi minimal 800px
2. Simpan ke folder `assets/logos/` dengan nama singkat (contoh: `nama_klien_baru.png`)
3. Di `quanta_website_english.html`, cari bagian daftar client card (`cli-card`), duplikasi salah satu blok yang menggunakan logo, lalu ganti `src="assets/logos/nama_klien_baru.png"` dan nama perusahaan

### Klien tanpa logo (memakai default icon inisial)
3 klien berikut belum memiliki logo, jadi ditampilkan sebagai lingkaran berisi inisial:
- **PT Batu Berkah Nusantara** → "BB"
- **PT Elmar** → "EL"
- **PT Delta Anugerah Makmur Kotrindo** → "DA"

Begitu logo mereka tersedia, ikuti langkah "Menambah logo klien baru" di atas untuk menggantinya.

---

## 🖼️ Pemetaan Foto per Kapal (Owned Vessels)

| Kapal | Kartu Thumbnail | Foto Full (klik-perbesar) |
|---|---|---|
| TB Max Christo 07 | `card_max_christo.jpg` | `full_max_christo.jpg` |
| TB Taurians One | `card_taurians.jpg` | `full_taurians.jpg` |
| BG Bulesko II | `card_bulesko.jpg` | `full_bulesko.jpg` |
| BG Indomarina 3002 | `card_indomarina.jpg` | `full_indomarina.jpg` |

Klik foto di kartu kapal pada section **Fleet** akan membuka foto ukuran penuh dalam pop-up (lightbox).

---

## ✅ Perbaikan pada Revisi Ini (18 Juli 2026)

- Logo kecil di atas teks "ESTABLISHED 2000" pada hero banner dihapus
- Semua foto pecah/rusak (artefak warna aneh) diganti dengan foto asli berkualitas tinggi yang baru diupload
- **Mekanisme gambar diubah dari base64 menjadi file terpisah** — ukuran halaman jauh lebih ringan, gambar mudah diganti tanpa edit kode
- Fleet gallery dipadatkan — tidak ada lagi slot kosong, semua terisi foto asli
- Section "Owned Vessels" — setiap kapal kini punya foto asli yang sesuai namanya
- Foto kapal di "Owned Vessels" bisa diklik untuk melihat versi lebih besar (pop-up lightbox)
- Hero banner memakai foto "Unloading Process Photo" sesuai permintaan
- Watermark logo diubah jadi 1 logo besar saja (bukan pola berulang kecil-kecil)
- Icon Instagram (tanpa frame) + nama akun `@Indonesiaquanta_` ditambahkan di section Contact
- Icon WhatsApp asli (putih, tanpa frame/border) menggantikan emoji telepon
- Halaman Gallery diisi ulang dengan 11 foto asli baru (Unloading Process, Bulesko II ×5, Indomarina 3002 ×2, Taurians One ×2, Max Christo 07 ×1)
- Link navigasi antar halaman (Home ↔ Gallery) diperbaiki — pastikan kedua file disimpan bersama tanpa rename
- Header dan footer diseragamkan persis sama antara halaman Home dan Gallery

---

## 📧 Kontak yang Digunakan di Website

- **Email:** marketing_vessel@quantaindonesia.com
- **WhatsApp:** +62 878-7529-3374
- **Instagram:** [@Indonesiaquanta_](https://www.instagram.com/Indonesiaquanta_/)
- **Alamat:** Gedung Palma One, Jl. HR. Rasuna Said Kav. X2 No. 4, Lt. 10 No. 102, Kuningan, Jakarta Selatan
