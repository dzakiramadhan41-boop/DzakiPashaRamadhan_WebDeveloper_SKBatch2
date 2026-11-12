# Recruitment Landing Section

Mini assignment Web Developer, Sekolah Karir Batch 2.
Satu section landing page rekrutmen yang responsif: headline, role cards dengan filter tim, dan CTA.

**Stack:** HTML, CSS, TypeScript, Vite (tanpa framework UI).

## Cara menjalankan

Butuh Node.js 18 atau lebih baru.

```bash
npm install
npm run dev       # development, buka alamat yang tampil di terminal
npm run build     # type-check lalu build ke folder dist/
npm run preview   # lihat hasil build
```

Live demo: _isi link GitHub Pages / Netlify / Vercel di sini_

## Struktur

```
index.html      markup semantik satu section
src/roles.ts    tipe Role dan data mock
src/main.ts     render role cards dan filter
src/style.css   desain dan responsivitas
```

## Keputusan utama

- **TypeScript tanpa framework UI.** Scope hanya satu section, jadi komponen React tidak diperlukan. TypeScript dipakai untuk menjaga data role tetap konsisten (`interface Role`) dan menangkap salah ketik sejak compile.
- **Data dipisah dari tampilan.** Menambah atau mengubah posisi cukup lewat `src/roles.ts`. Filter tim dibuat otomatis dari daftar `teams`.
- **Mobile-first.** CSS dasar ditulis untuk layar sempit, lalu diperluas dengan satu breakpoint di 760px. Grid kartu memakai `auto-fill` + `minmax`, jadi jumlah kolom menyesuaikan lebar layar tanpa banyak media query.
- **Satu CTA utama per konteks.** Di hero: "Lihat posisi terbuka". Di setiap kartu: "Lamar posisi ini". Di bagian akhir: "Kirim lamaran umum" untuk orang yang belum menemukan posisi cocok.
- **Lamaran lewat `mailto:`.** Sengaja sederhana, tanpa backend atau layanan berbayar. Subjek email terisi otomatis dengan nama posisi.
- **Aksesibilitas dasar.** Heading berurutan, skip link, fokus keyboard terlihat, tombol filter memakai `aria-pressed`, jumlah hasil diumumkan lewat `aria-live`, target sentuh minimal 44px, dan `prefers-reduced-motion` dihormati.
- **Tanpa gambar.** Halaman tetap ringan dan tidak bergantung pada aset eksternal selain Google Fonts (dengan font fallback).

## Mock data

Semua posisi, deskripsi, dan alamat email (`karir@example.com`) adalah data contoh. Tidak ada data pribadi atau data rahasia asli.

## Penggunaan AI

Saya memakai Claude (Anthropic) untuk membantu menyusun kerangka project, menulis draf kode, dan README. Saya meninjau kode, menjalankan project, dan menyesuaikan isinya sebelum submit.

## Ide pengembangan

- Form lamaran dengan validasi dan penyimpanan ke layanan form gratis.
- Pencarian teks dan filter tipe kerja (magang atau penuh waktu).
- Halaman detail per posisi.
