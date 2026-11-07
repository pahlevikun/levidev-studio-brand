# Kopsurat Levidev Studio

Kopsurat resmi A4 (210 × 297 mm) untuk **Levidev Studio**, nama legal **PT. Levidev Studio Digital**.

## File

| File | Isi |
|---|---|
| `letterhead.svg` | Sumber editable A4, mandiri (lockup vektor di-inline, tanpa prefiks XML rusak) |
| `letterhead-lockup.svg` | Lockup horizontal tanpa background — dipakai header HTML |
| `letterhead-blank.html` | Template kosong print-ready (`@page` A4) — tulis isi surat di dalam `.body` |
| `letterhead-sample.html` | Contoh surat 1 halaman terisi placeholder |
| `letterhead-blank.pdf` / `letterhead-sample.pdf` | PDF A4 siap cetak dari HTML di atas |
| `preview-blank.png` / `preview-sample.png` / `preview-svg.png` | Preview visual (1588 × 2246 px) |

## Aset & fakta yang dipakai

- Lockup header HTML: `letterhead-lockup.svg` (turunan `final/wordmark-light.svg`, tanpa rect latar agar tidak “kotak” di kop).
- Palet terverifikasi dari file tersebut: paper `#f0e7d6`, stone `#B2A994`, rose `#98585C`, ink `#14110d`, sub-teks `#595246`.
- Website: `levidev.studio` (dari `final/schema-id.jsonld` & `PROFILE.md`).
- Lokasi ringkas: “Bogor, Jawa Barat, Indonesia”.

## Sengaja tidak dicantumkan (tidak dikarang)

- Alamat jalan lengkap: `PROFILE.md` menyarankan alamat rumah disembunyikan bila klien tidak datang; footer cukup kota.
- Telepon, email, NIB, NPWP, nomor registrasi: tidak ada data legal/ kontak terverifikasi selain nama PT & website, jadi diomit — bukan diisi karangan.
- Contoh surat hanya memakai placeholder berwarna rose seperti `[Nomor Surat]`, `[Tanggal Surat]`, `[Nama Penandatangan]`.

## Cara pakai

1. Edit `letterhead-sample.html` (ganti semua teks `[...]`), lalu cetak ke PDF dari Chrome: *Print → Save as PDF → A4, margin None, Background graphics ON*. Atau render ulang:

```bash
"/Applications/Google Chrome.app/Contents/MacOS/Google Chrome" --headless --disable-gpu \
  --print-to-pdf=letterhead-sample.pdf --no-pdf-header-footer letterhead-sample.html
```

2. Untuk stempel/tanda tangan digital di atas kop polos, pakai `letterhead-blank.pdf` sebagai latar.

## DOCX

Tidak dibuat: `pandoc`/`libreoffice` tidak terpasang dan `python-docx` tidak tersedia di mesin ini. HTML/SVG/PDF di atas adalah jalur cetak yang terverifikasi; buat DOCX dari `letterhead-blank.html` hanya bila nanti ada converter yang terpasang, lalu cek ulang margin A4-nya.

## Validasi (7 Nov 2026)

- `xmllint --noout letterhead.svg` → valid.
- MediaBox kedua PDF: `0 0 594.96 841.92 pt` = A4.
- Preview PNG diinspeksi visual: alignment, margin, skala logo, dan keterbacaan nama resmi bersih; tidak ada teks bertabrakan/terpotong.
