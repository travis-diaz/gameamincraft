# Amincraft — Next-Gen Voxel Sandbox

Game sandbox voxel 3D untuk browser yang memadukan dua dunia: **Fantasi Alam** dan **Cyberpunk**.
Seluruh game (HTML, CSS, dan JavaScript) ada dalam satu file: `index.html`.

## Cara Bermain

1. Unduh repositori ini (**Code → Download ZIP**, lalu ekstrak) atau clone:

   ```bash
   git clone https://github.com/travis-diaz/gameamincraft.git
   ```

2. Klik dua kali `index.html` untuk membukanya di browser.
3. Tunggu dunia selesai dibangun, pilih tema, lalu klik **MAINKAN**. Kursor akan terkunci ke layar dan kamu bisa langsung bermain.

**Persyaratan**

- Browser desktop terbaru dengan dukungan **WebGL2** (Chrome, Edge, Firefox, atau Safari).
- **Koneksi internet** saat membuka game, karena pustaka three.js dimuat dari CDN jsDelivr. Font diambil dari Google Fonts; jika gagal dimuat, game memakai font cadangan.
- Keyboard dan mouse.

> Jika browser membatasi file lokal, jalankan server lokal dari folder ini, misalnya `python -m http.server 8000`, lalu buka `http://localhost:8000`.

## Fitur

### Dua tema yang berganti secara real-time

Ganti tema lewat kartu tema di menu utama atau dengan tombol **T**. Warna voxel, cahaya, kabut, langit, partikel, logo, dan musik langsung berubah dengan transisi halus sekitar satu detik, tanpa memuat ulang dunia.

| Fantasi Alam | Cyberpunk |
|---|---|
| Rumput subur, pohon raksasa, dan sulur | Terrain logam gelap dan blok grid neon |
| Pilar batu kuno raksasa dan batu rune | Monolit baja dan rune neon |
| Pulau melayang dengan air terjun | Kristal magenta, sian, dan ungu yang menyala |
| Sinar matahari keemasan (god rays) dan awan | Matahari synthwave bergaris dan bintang |
| Air biru yang dalam | Cairan neon |
| Kabut eksponensial keemasan dan kunang-kunang | Kabut ungu neon pekat dan debu neon |

### Dunia prosedural

- Generator noise buatan sendiri, tanpa pustaka noise tambahan.
- Bukit, jurang, tebing menjorok, danau/laut, dan pulau melayang dua lapis.
- Dunia berbasis seed: seed yang sama selalu menghasilkan dunia yang sama. Kamu bisa membuat dunia baru dari menu **DUNIA BARU**.
- Chunk berukuran 16×16×128 dimuat dan dilepas otomatis di sekitar pemain.
- Geometri tiap chunk digabung (*merged geometry*) dengan face culling dan ambient occlusion per verteks, supaya jumlah draw call tetap rendah.

### Grafis

- `MeshStandardMaterial` dengan roughness dan metalness berbeda untuk tiap blok, plus cahaya emisif pada blok neon, kristal, dan lentera.
- Bayangan dari `DirectionalLight` yang mengikuti pemain.
- Peta lingkungan (PMREM) untuk pantulan logam dan air.
- Pasca-proses: bloom, god rays, efek bawah air, tone mapping ACES, color grading yang cerah, vignette, dan film grain. Tema Cyberpunk menambahkan scanline dan memperkuat aberasi kromatik.
- Empat preset kualitas: **Rendah**, **Sedang**, **Tinggi**, dan **Ultra**.

### Permainan

- Kontrol orang pertama (`PointerLockControls`) dengan tabrakan, lompat, lari, berenang, dan mode terbang.
- Hancurkan dan pasang blok, dengan efek pecahan blok.
- 17 jenis blok yang bisa dipasang. Nama blok menyesuaikan tema aktif.
- Hotbar 9 slot dan **Tas Blok** untuk memilih blok.
- HUD futuristik: crosshair, nama blok terpilih, judul Amincraft, tema aktif, kompas, penghitung FPS, dan statistik performa.
- Musik ambient dan efek suara prosedural (Web Audio), tanpa file audio.
- Simpan otomatis di browser (`localStorage`): seed dan perubahan blok, posisi pemain, hotbar, dan pengaturan.

## Kontrol

| Tombol | Aksi |
|---|---|
| `W` `A` `S` `D` | Bergerak |
| Mouse | Melihat sekeliling |
| `Spasi` | Lompat; naik saat terbang atau berenang |
| `Shift` | Berlari |
| `C` | Turun saat terbang atau berenang |
| `F` | Mengaktifkan / menonaktifkan mode terbang |
| Klik Kiri | Hancurkan blok (tahan untuk mengulang) |
| Klik Kanan | Pasang blok (tahan untuk mengulang) |
| Klik Tengah | Ambil jenis blok yang sedang dibidik |
| `1`–`9` / Roda mouse | Pilih slot hotbar |
| `E` | Buka / tutup Tas Blok |
| `T` | Ganti tema dengan cepat |
| `M` | Buka / tutup menu utama |
| `P` | Statistik performa |
| `Esc` | Jeda (melepas kursor) |

## Pengaturan

Di menu **PENGATURAN** kamu bisa mengatur:

- Kualitas grafis (Rendah, Sedang, Tinggi, Ultra)
- Jarak pandang (3–10 chunk)
- Sensitivitas mouse
- Bidang pandang / FOV (60°–100°)
- Volume musik dan volume efek suara
- Tampilan penghitung FPS

Jika FPS rendah, turunkan kualitas grafis atau jarak pandang.

## Penyimpanan

Progres tersimpan otomatis di `localStorage` browser, jadi game melanjutkan dunia terakhir saat dibuka lagi. Membuat **Dunia Baru** akan mengganti dunia yang sedang dimainkan. Menghapus data situs di browser juga menghapus dunia yang tersimpan.

## Publikasi dengan GitHub Pages (opsional)

1. Buka **Settings → Pages** di repositori ini.
2. Pada **Build and deployment**, pilih **Deploy from a branch**, lalu branch `main` dan folder `/ (root)`.
3. Klik **Save**. Setelah beberapa menit, game bisa dibuka di `https://travis-diaz.github.io/gameamincraft/`.

## Teknologi

- [three.js](https://threejs.org/) 0.160.0 (lisensi MIT), dimuat lewat import map dari jsDelivr: `PointerLockControls`, `EffectComposer`, `RenderPass`, `UnrealBloomPass`, dan `ShaderPass`.
- WebGL2 dengan shader GLSL kustom untuk material blok, air, langit, partikel, dan pass akhir.
- Web Audio API untuk musik dan efek suara prosedural.
