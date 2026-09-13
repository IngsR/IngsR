<div align="center">

<img src="https://readme-typing-svg.herokuapp.com?font=Fira+Code&size=28&duration=2000&pause=800&color=0078FF&center=true&vCenter=true&width=800&lines=Junior+Web+Developer;Full+Stack+Web+Developer;Building+Web+Solutions+from+Real+Problems" alt="Typing SVG" />

</div>

### 👋 Halo, saya **Ikhwan Ramadhan (Ings)**

**Junior Web Developer / Full-Stack Web Developer**  
Fresh Graduate S1 Teknik Informatika — **Universitas Putra Indonesia "YPTK" Padang** (2022–2026 · IPK 3.27/4.0)

Saya mengembangkan aplikasi web dengan pemahaman alur menyeluruh: merancang antarmuka frontend, membangun backend REST API, mengelola database relasional, menangani autentikasi dan otorisasi, mengeksekusi logika bisnis, menulis pengujian, hingga deployment ke production. Terbiasa bekerja dengan ekosistem **TypeScript**, **Next.js**, **React**, **Angular**, **NestJS**, **PostgreSQL**, **Prisma**, dan **Drizzle ORM**. Melalui riset skripsi, saya juga memiliki nilai tambah di bidang **Data Science dan AI/ML** untuk analisis data dan eksperimen pemodelan prediktif.

---

## Pengalaman & Project Pilihan

### 1. Website Resmi & Sistem Informasi SMP Negeri 24 Padang — Pengalaman Magang / PKL

**Peran:** Ketua Tim & Full-Stack Web Developer (Magang / PKL, Agustus – September 2025 · 96 Jam)  
**Tautan:** [smpn24padang.sch.id](https://smpn24padang.sch.id) · [Repository](https://github.com/IngsR/Website-SMPN24padang)  
**Stack:** Next.js (App Router), TypeScript, Drizzle ORM, Neon PostgreSQL, Tailwind CSS

Pengalaman kerja praktik nyata memimpin tim pengembang web untuk memenuhi kebutuhan digitalisasi SMP Negeri 24 Padang hingga sistem rilis di domain resmi sekolah.

- **Masalah:** Kebutuhan sekolah bukan sekadar profil statis. Pihak sekolah (kepala sekolah, wakil kurikulum, dan staf tata usaha) membutuhkan sistem terpadu: portal publik informasi sekolah, panel admin (CMS) untuk pembaruan konten mandiri tanpa bantuan teknis, serta modul digital untuk mengelola bank sampah sekolah.
- **Solusi & Keputusan Teknis:**
  - Berkomunikasi langsung dengan kepala sekolah untuk memetakan kebutuhan operasional ke arsitektur aplikasi full-stack menggunakan Next.js App Router.
  - Membangun portal publik yang terhubung langsung dengan CMS terproteksi autentikasi Auth.js dan middleware route untuk pengelolaan berita, pengumuman, data guru, dan galeri.
  - Merancang modul **Sispendik** (Bank Sampah Digital) dengan alur data: `setoran → kategori sampah → berat (kg) → kalkulasi nilai → penyimpanan database → rekapitulasi → laporan`.
  - Mengelola skema dan migrasi database via Drizzle ORM dengan optimasi index pada kolom tanggal dan relasi penyetor untuk efisiensi query agregasi admin.
  - Menerapkan script pengujian otomatis (unit, integration, e2e, dan pemeriksaan dasar keamanan web).
- **Hasil:** Skor **Google Lighthouse Performance 99/100** (FCP ~0,5 detik), CMS aktif digunakan staf sekolah untuk update berkala, modul Sispendik menyediakan dashboard data publik serta rekap admin dengan fitur cetak/export PDF (`window.print`), dan sistem berhasil dideploy ke domain resmi `smpn24padang.sch.id`.

### 2. B2B Auction Marketplace

**Repository:** [github.com/IngsR/Monorepo-B2B](https://github.com/IngsR/Monorepo-B2B)  
**Stack:** Angular, NestJS, TypeScript, Prisma ORM, PostgreSQL, Turborepo

Platform lelang barang B2B yang dibangun dalam arsitektur monorepo, memisahkan client Single Page Application (Angular) dan backend REST API (NestJS) dalam satu workspace pengembangan terpadu.

- **Masalah:** Menjaga integritas dan konsistensi transaksi lelang multi-pengguna agar aturan bisnis tidak bergantung pada validasi client yang rentan dimanipulasi.
- **Solusi & Keputusan Teknis:**
  - Mengatur batasan akses tegas untuk tiga peran: **Admin** (verifikasi vendor & kategori), **Vendor** (katalog barang & sesi lelang), dan **Bidder** (eksplorasi lelang & penawaran) menggunakan autentikasi JWT dan guard role-based (RBAC).
  - Mengunci aturan bisnis di server: lelang memiliki siklus hidup terstruktur (draft, aktif, selesai, batal). Tawaran hanya diterima jika lelang berstatus aktif dan nominal secara valid lebih tinggi dari penawaran tertinggi saat itu, divalidasi melalui DTO sebelum diproses ke PostgreSQL via Prisma ORM.
  - Menormalisasi response dan exception layer agar struktur error dan data yang diterima client selalu konsisten.
- **Hasil:** Logika transaksi lelang terlindungi secara terpusat di backend, dengan verifikasi otomatis alur login, siklus lelang, dan konsistensi bid melalui integration testing (Vitest & Supertest).

### 3. Automotive Commerce & Sales Workflow

**Repository:** [github.com/IngsR/web_store](https://github.com/IngsR/web_store) · **Live Demo:** [cars.ikhwann.my.id](https://cars.ikhwann.my.id)  
**Stack:** Next.js (App Router), TypeScript, Prisma ORM, PostgreSQL, Tailwind CSS

Aplikasi penjualan mobil full-stack yang mengombinasikan etalase kendaraan pelanggan dengan otomasi alur operasional penugasan sales berbasis workflow.

- **Masalah:** Mengatasi penanganan prospek calon pembeli (_leads_) yang lambat atau tidak merata akibat proses penugasan manual oleh staf dealer.
- **Solusi & Keputusan Teknis:**
  - Merancang alur otomasi pemrosesan lead:
    `Customer Submit Pemesanan → Admin Review & Validasi → Otomasi Penugasan Round-Robin → Handoff WhatsApp`.
  - Menerapkan aturan bisnis penugasan round-robin: setelah pesanan diverifikasi admin, sistem menugaskan prospek ke sales consultant aktif secara bergilir berdasarkan kuota penugasan terendah dan waktu penugasan paling lampau.
  - Membangun dashboard manajemen operasional untuk inventaris mobil (kondisi baru/bekas, kilometer, harga), status order, tim sales aktif, dan analitik penjualan via Route Handlers dan Prisma ORM.
- **Hasil:** Distribusi calon pembeli berjalan otomatis dan adil antar-sales, serta sistem menyiapkan pesan terformat yang siap diteruskan langsung ke komunikasi personal WhatsApp sales bersangkutan.

### 4. Prediksi Lintasan Siklon Tropis — Project Skripsi

**Tautan:** [prediksi.ikhwann.my.id](https://prediksi.ikhwann.my.id) · [Repository](https://github.com/IngsR/PrediksiSIklon-LSTM)  
**Periode:** Juni – Agustus 2026  
**Stack:** Python, TensorFlow/Keras, LSTM, ONNX Runtime, Astro, TypeScript, Geospatial UI

Proyek riset skripsi yang memprediksi lintasan siklon tropis menggunakan arsitektur Long Short-Term Memory (LSTM) berbasis data historis IBTrACS (1980–2025). Berfungsi sebagai bukti kemampuan analitis, eksplorasi data mendalam, dan penerapan model AI/ML ke dalam sistem web interaktif.

- **Masalah:** Data historis mencakup dua wilayah laut dengan karakteristik yang sangat heterogen: North Indian Ocean (NI: 17.801 observasi, 458 siklon pada 0°–30° LU) dan South Indian Ocean (SI: 68.668 observasi, 903 siklon pada -60°–0° LS). Pola musimannya berlawanan (puncak NI Oktober vs puncak SI Februari), sehingga penggabungan data secara naif berisiko mengaburkan akurasi model.
- **Solusi & Keputusan Teknis:**
  - Melakukan validasi statistik sebelum pemodelan: Uji Kolmogorov-Smirnov membuktikan perbedaan distribusi secara signifikan ($KS = 0,4802$, $p < 1 \times 10^{-16}$) serta uji Mann-Whitney pada kecepatan perpindahan, turning angle, dan panjang lintasan.
  - Menjadikan temuan heterogenitas data sebagai acuan perancangan **12 skenario eksperimen** arsitektur LSTM untuk menentukan model terbaik secara objektif.
  - Mengonversi model terbaik ke format **ONNX** dan mengeksekusi inferensi langsung di browser pengguna via **ONNX Runtime** (_client-side inference_ tanpa beban server).
  - Mengintegrasikan hasil model ke antarmuka web interaktif berbasis Astro dan TypeScript dengan visualisasi peta geospasial.
- **Hasil:** Model terbaik mencatatkan rata-rata error Haversine **14,2 km** dan **$R^2 = 0,999$**, dapat diuji langsung oleh pengguna melalui simulasi peta interaktif di web browser.

---

## Technology Ecosystem

<div align="center">

  <img src="https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white" alt="TypeScript" />
  <img src="https://img.shields.io/badge/Next.js-000000?style=for-the-badge&logo=nextdotjs&logoColor=white" alt="Next.js" />
  <img src="https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB" alt="React" />
  <img src="https://img.shields.io/badge/Angular-DD0031?style=for-the-badge&logo=angular&logoColor=white" alt="Angular" />

  <img src="https://img.shields.io/badge/NestJS-E0234E?style=for-the-badge&logo=nestjs&logoColor=white" alt="NestJS" />
  <img src="https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white" alt="PostgreSQL" />
  <img src="https://img.shields.io/badge/Prisma-2D3748?style=for-the-badge&logo=prisma&logoColor=white" alt="Prisma" />
  <img src="https://img.shields.io/badge/Drizzle_ORM-C5F74F?style=for-the-badge&logo=drizzle&logoColor=black" alt="Drizzle ORM" />

  <img src="https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white" alt="Tailwind CSS" />
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python" />
  <img src="https://img.shields.io/badge/TensorFlow-FF6F00?style=for-the-badge&logo=tensorflow&logoColor=white" alt="TensorFlow" />
  <img src="https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white" alt="Git" />

</div>

---

## Repositori Lainnya

- **[Aplikasi Pengelolaan Gudang](https://github.com/IngsR/manajemen-iventory)** — Sistem inventaris dan manajemen stok barang dengan kontrol akses berbasis role. **Stack:** Next.js, PostgreSQL. [Live Demo](https://kelola-barang.vercel.app)
- **[DockRank TF-IDF](https://github.com/IngsR/DockRank_TF-IDF)** — Mesin pencari dan perangkingan dokumen teks berbasis algoritma Term Frequency-Inverse Document Frequency (TF-IDF). **Stack:** Python, Next.js. [Live Demo](https://tfidf.vercel.app)

---

<div align="center">

### 📊 GitHub Stats

<p align="center">
  <img 
    src="https://github-readme-stats-eight-theta.vercel.app/api?username=IngsR&show_icons=true&bg_color=0d1117&title_color=58a6ff&text_color=c9d1d9&icon_color=58a6ff&border_color=30363d&include_all_commits=true&count_private=true" 
    alt="Ikhwan's GitHub Stats" 
    height="160" 
  />
  <img 
    src="https://github-readme-stats-eight-theta.vercel.app/api/top-langs/?username=IngsR&layout=compact&hide=Jupyter%20Notebook&bg_color=0d1117&title_color=58a6ff&text_color=c9d1d9&border_color=30363d" 
    alt="Top Languages" 
    height="160" 
  />
</p>

</div>

---

<div align="center">

✨ _“Code. Learn. Build. Repeat.”_ ✨

</div>
