# 📚 Blog Viewer - Nuxt 4

Project sederhana ini dibuat untuk menampilkan daftar blog dari API menggunakan **Nuxt 4** dan **Tailwind CSS**. Cocok sebagai bahan ajar untuk belajar:

- Struktur dasar Nuxt 4
- Routing dinamis (`pages/[id].vue`)
- Fetching data dengan `useFetch`
- Desain responsif dengan Tailwind CSS

---

## 🚀 Fitur

- Menampilkan daftar blog dari JSONPlaceholder
- Routing dinamis ke halaman detail tiap post
- Tampilan yang sudah didesain ulang agar lebih menarik
- Loading state & error handling

---

## 🛠️ Teknologi yang Digunakan

- [Nuxt 4](https://nuxt.com)
- [Tailwind CSS](https://tailwindcss.com)
- [JSONPlaceholder API](https://jsonplaceholder.typicode.com)

---

## 🧱 Struktur Folder

```bash
.
├── app.vue
├── components/
│   └── PostCard.vue         # Komponen kartu blog
├── pages/
│   ├── index.vue            # Halaman daftar blog
│   └── posts/
│       └── [id].vue         # Halaman detail blog (routing dinamis)
├── public/
│   └── favicon.ico, robots.txt
├── assets/
│   └── css/main.css         # (Opsional) Gaya global
├── nuxt.config.ts           # Konfigurasi Nuxt
├── tailwind.config.js       # Konfigurasi Tailwind
├── package.json
└── README.md
```

---

## 📦 Instalasi & Menjalankan

1. **Clone repo**
```bash
git clone git@github.com:PrayudhaIbnu/blog-viewer.git
cd blog-viewer
```

2. **Install dependency**
```bash
npm install
```

3. **Jalankan development server**
```bash
npm run dev
```

4. Akses di browser:
```
http://localhost:3000
```

---

## 💡 Catatan Pembelajaran

- Menggunakan `useFetch()` secara `async/await` untuk SSR/CSR otomatis
- Pemanfaatan `<NuxtLink>` untuk navigasi antar halaman
- Styling interaktif menggunakan Tailwind (hover, transition, responsive grid)
- Penggunaan `defineProps()` untuk komponen

---

## 📚 API Referensi

Semua data diambil dari:
[https://jsonplaceholder.typicode.com/posts](https://jsonplaceholder.typicode.com/posts)

---

## 📝 Lisensi

MIT License © 2025 - [Prayudha Ibnu](https://github.com/PrayudhaIbnu)
