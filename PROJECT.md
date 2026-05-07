# Personal Website — Project Brief

Personal website Ali Hasbullah. Tempat memperkenalkan diri, memamerkan project, dan rutin menulis artikel teknis.

## Status Saat Ini

Website live di `https://personal-website-eat.pages.dev`. Halaman About sudah berisi konten asli; halaman lain masih placeholder.

## Stack & Architecture

- **Hugo extended** sebagai static site generator
- **PaperMod** sebagai theme (Git submodule, branch master)
- **GitHub** sebagai source control (`alihasbullah/personal-website`)
- **Cloudflare Pages** untuk hosting + auto-deploy
- **Markdown** untuk semua konten
- **YAML frontmatter** untuk metadata file

Lihat `README.md` untuk instruksi setup teknis.

## Bahasa Konten

Multilingual: Bahasa Indonesia (default) dan English.

- Bahasa Indonesia: file Markdown tanpa suffix (contoh: `about.md`)
- English: file dengan suffix `.en` (contoh: `about.en.md`)
- URL pattern: `/halaman/` untuk Indonesia, `/en/halaman/` untuk English
- Setiap halaman utama idealnya tersedia di kedua bahasa, tapi boleh ada konten yang hanya di salah satu

## Vibe Visual

- **Minimalis**: banyak whitespace, hierarki tipografi jelas, palet warna terbatas
- **Font**: clean sans-serif untuk body, monospace untuk code
- **Dark mode**: default `auto` (ikut preferensi sistem), toggle tersedia
- **Responsive**: mobile-friendly tanpa effort khusus berkat PaperMod

## Struktur Konten

- **Home** (`content/_index.md`): profile mode dengan tombol cepat ke Posts dan Projects
- **About** (`content/about.md`): bio, background, kontak
- **Posts** (`content/posts/`): tulisan teknis dan reflektif, sorted by date
- **Projects** (`content/projects/`): project showcase
- **Search** (`content/search.md`): client-side fuzzy search via Fuse.js (built-in PaperMod)

## Prinsip Pengembangan

1. **Shipping > perfection** — lebih baik publish konten okay daripada drafting selamanya
2. **Pragmatis, hindari over-engineering** — no database, no JS framework tambahan, no custom build pipeline
3. **Iteratif** — tambah fitur seiring kebutuhan nyata, bukan karena "keren"
4. **Reproducible** — siapapun yang clone repo bisa build dengan `hugo` tanpa konfigurasi tambahan
5. **Konvensi over konfigurasi** — ikuti default Hugo dan PaperMod kecuali ada alasan kuat untuk override

## Yang Harus Dihindari

- ❌ Database atau backend (tetap pure static)
- ❌ JavaScript framework (React, Vue, Svelte) untuk fitur tambahan
- ❌ Build tool tambahan di luar Hugo (webpack, vite, rollup)
- ❌ Komentar section yang butuh server (Disqus dll)
- ❌ Analytics berat (Google Analytics)—gunakan privacy-friendly seperti Plausible atau Umami
- ❌ Inline CSS berlebihan—pakai CSS file terstruktur
- ❌ Modifikasi langsung di folder `themes/PaperMod/`—override via `layouts/` di root project

## Rencana Konten Awal

- [ ] Bio singkat untuk hero homepage (2-3 kalimat)
- [ ] Bio panjang di About (background, minat, kontak)
- [ ] 2-3 project asli dengan deskripsi, tech stack, link repo
- [x] 1 artikel pertama (esai reflektif tentang ekonomi Indonesia)
- [ ] Foto profil (opsional)
- [ ] Update social links di `hugo.toml` (saat ini placeholder)

## Roadmap (loose)

- **Now**: isi konten asli, polish copywriting
- **Soon**: tambah favicon dan OG image, set up Plausible analytics
- **Later**: custom domain, RSS link di footer, eksperimen dengan custom layouts

## Konvensi Penulisan

- **Komit**: pesan dalam Bahasa Inggris, format imperatif (`Add ...`, `Fix ...`, `Update ...`)
- **Branch**: kerja langsung di `main` untuk perubahan kecil; gunakan feature branch untuk eksperimen besar
- **Frontmatter**: YAML dengan field `title`, `date`, `draft`, `tags`, `categories`, `summary`
- **Tanggal**: format ISO `YYYY-MM-DD`
- **File naming**: kebab-case untuk Markdown files (`hello-world.md`, bukan `Hello_World.md`)