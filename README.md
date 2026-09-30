# Amincraft — Next-Gen Voxel Sandbox

Amincraft adalah game sandbox voxel 3D untuk browser yang memadukan dua tema: **Fantasi Alam** dan **Cyberpunk**.
Seluruh game (HTML, CSS, dan JavaScript) ada dalam satu file, `index.html`. Tampilannya berbahasa Indonesia, dan game bisa dimainkan sendiri atau bersama teman (**multipemain online**), dengan **keyboard & mouse** maupun **joystick**.

## Fitur utama

- **5 tipe dunia**: Standar, Pegunungan, Kepulauan Tropis, Pulau Langit, dan Datar. Pemandangannya meliputi gunung bersalju, air terjun, pantai, sungai, terumbu karang, dan pulau melayang.
- **21 bioma**, antara lain hutan, hutan sakura, hutan birch, hutan hujan, taiga, sabana, gurun, rawa, tundra bersalju, puncak bersalju, pantai, sungai, dan laut hangat.
- **Bangunan alami**: desa (gaya rumah menyesuaikan bioma), piramida gurun, iglo, reruntuhan, dan kapal karam.
- **86 jenis blok** dalam 5 kategori tas: Alam, Kayu, Bangunan, Tanaman, dan Fantasi. Ada bijih, wol berwarna, kaca, rak buku, obor, batu cahaya, kristal, karang, bunga, dan TNT.
- **Hewan**: domba, babi, sapi, dan ayam. Hewan bergerak berkelompok dan kabur saat dipukul.
- **TNT**: pukul untuk menyalakan. Ledakannya menghancurkan blok dan bisa memicu TNT lain di dekatnya.
- **Siang–malam dan cuaca**: satu hari berlangsung 20 menit. Cuaca bisa cerah, berawan, hujan, atau badai.
- **Kamera orang pertama/ketiga** dan **jongkok** (pemain tidak jatuh dari tepi saat jongkok).
- **Multipemain online** hingga 8 pemain lewat kode room, lengkap dengan chat.
- **Dukungan joystick/gamepad**: tombol bisa diatur ulang, stik bisa dikalibrasi, dan joystick bergetar saat memukul.
- **Dua tema yang berganti secara real-time** (tombol **T**).

## Cara bermain

1. Unduh repositori ini (**Code → Download ZIP**, lalu ekstrak) atau clone:

   ```bash
   git clone https://github.com/travis-diaz/gameamincraft.git
   ```

2. Klik dua kali `index.html` untuk membukanya di browser, atau buka versi online (lihat bagian GitHub Pages di bawah).
3. Tunggu dunia selesai dibangun, pilih tema, lalu klik **MAINKAN**.

**Persyaratan**

- Browser desktop terbaru dengan dukungan **WebGL2** (Chrome, Edge, Firefox, atau Safari).
- **Koneksi internet** saat membuka game, karena three.js dimuat dari CDN jsDelivr. Mode multipemain juga membutuhkan internet.
- Keyboard & mouse, atau joystick (USB/Bluetooth).

> Jika browser membatasi file lokal, jalankan server lokal dari folder ini, misalnya `python -m http.server 8000`, lalu buka `http://localhost:8000`.

## Tipe dunia

Pilih tipe dunia di menu **DUNIA BARU**. Kamu juga bisa mengisi seed; seed dan tipe yang sama selalu menghasilkan dunia yang sama.

| Tipe | Pemandangan |
|---|---|
| **Standar** | Semua bioma dalam satu dunia: gunung, pantai, hutan, gurun, sungai, desa, dan pulau melayang |
| **Pegunungan** | Puncak bersalju, lembah dalam, tebing curam, dan air terjun |
| **Kepulauan Tropis** | Laut biru jernih, pulau berpasir, pohon kelapa, dan terumbu karang |
| **Pulau Langit** | Ratusan pulau melayang di atas samudra luas |
| **Datar** | Dunia rata untuk membangun dengan bebas |

Hasil uji otomatis generator dunia dengan tiga seed (`amin-123`, `pantai-7`, `lembah-42`). Setiap seed dihitung pada area 13×13 chunk (208×208 blok) di sekitar titik awal:

| Tipe | Hasil pengukuran |
|---|---|
| Standar | Tinggi tanah 4–94 (seed `amin-123`), banyak bioma dalam satu area |
| Pegunungan | Puncak tanah setinggi 97–113, salju menutupi 6–8% permukaan, 8–15 kolom air terjun |
| Kepulauan Tropis | Laut 48–56% permukaan, 27–139 pohon kelapa, sekitar 4.600–6.200 blok karang |
| Pulau Langit | Pulau melayang di atas 27–57% area |
| Datar | Permukaan rata di ketinggian 35 |

## Kontrol keyboard & mouse

| Tombol | Aksi |
|---|---|
| `W` `A` `S` `D` / tombol panah | Bergerak |
| Mouse | Melihat sekeliling |
| `Spasi` | Lompat; naik saat terbang atau berenang |
| `Shift` | Berlari |
| `C` | Jongkok; turun saat terbang atau berenang |
| `F` | Mode terbang |
| `V` | Ganti kamera (orang pertama / orang ketiga) |
| Klik kiri | Hancurkan blok, pukul hewan, nyalakan TNT |
| Klik kanan | Pasang blok |
| Klik tengah | Ambil jenis blok yang sedang dibidik |
| `1`–`9` / roda mouse | Pilih slot hotbar |
| `E` | Buka / tutup Tas Blok |
| `T` | Ganti tema |
| `M` | Buka / tutup menu |
| `Enter` | Chat (saat multipemain) |
| `P` | Statistik performa |
| `Esc` | Jeda |

> Tips TNT: pukul TNT untuk menyalakannya (sumbu 4 detik), lalu menjauh. Untuk mengambil TNT tanpa meledakkannya, tahan `C` (jongkok) sambil memukul.

## Bermain dengan joystick

1. Hubungkan joystick ke laptop lewat USB atau Bluetooth, lalu buka game.
2. **Tekan salah satu tombol joystick.** Browser baru mengenali joystick setelah ada tombol yang ditekan. Setelah itu muncul notifikasi **"🎮 Joystick terhubung"**.
3. Tekan **Start** untuk membuka menu, lalu **A** untuk bermain. Kamu tidak perlu mouse.
4. Browser baru mengizinkan suara setelah layar diklik, jadi **klik layar sekali** untuk mengaktifkan musik dan efek suara.

Tata letak bawaan (Xbox / tata letak standar; padanan PlayStation ditulis dalam kurung):

| Tombol | Aksi |
|---|---|
| Stik kiri | Bergerak |
| Stik kanan | Melihat sekeliling |
| A (✕) | Lompat / naik |
| B (○) | Jongkok / turun |
| X (□) | Ambil jenis blok |
| Y (△) | Tas Blok |
| LB / RB (L1 / R1) atau D-pad ← / → | Slot hotbar sebelumnya / berikutnya |
| LT (L2) | Pasang blok |
| RT (R2) | Hancurkan / pukul |
| L3 (tekan stik kiri) | Berlari (aktif sampai berhenti bergerak) |
| D-pad ↑ | Ganti kamera |
| D-pad ↓ | Mode terbang |
| Back / Select (Share / Create) | Ganti tema |
| Start (Options) | Menu / jeda |

Di menu dan panel, gunakan D-pad atau stik kiri untuk berpindah pilihan, **A** untuk memilih, dan **B** untuk kembali. Di Tas Blok, **LB/RB** mengganti kategori dan **LT/RT** mengganti slot hotbar.

**Menu → JOYSTICK** berisi pengaturan berikut:

- **Ubah tombol**: pilih sebuah aksi, lalu tekan tombol joystick yang diinginkan. Jika tombol itu sudah dipakai aksi lain, kedua tombol ditukar.
- **KALIBRASI STIK**: ikuti 4 langkah di layar (stik kiri ke kanan, stik kiri ke atas, stik kanan ke kanan, stik kanan ke atas). Gunakan fitur ini jika arah stik terbalik atau tertukar, misalnya pada joystick generik yang tidak memakai tata letak standar.
- **Zona Mati Stik**, **Sensitivitas Kamera**, **Balik Sumbu Vertikal**, dan **Getaran**.
- **SETEL ULANG** mengembalikan semua pengaturan joystick ke bawaan.

Pengaturan joystick tersimpan otomatis di browser.

## Multipemain online

**Membuat room (host)**

1. Buka **Menu → MULTIPEMAIN** dan isi nama pemain.
2. Klik **BUAT ROOM**. Game menampilkan kode room 6 karakter.
3. Klik **SALIN**, lalu kirim kode itu ke teman.

**Bergabung ke room**

1. Buka game (sebaiknya dari link GitHub Pages yang sama), lalu buka **Menu → MULTIPEMAIN**.
2. Ketik kode room, lalu klik **GABUNG**. Dunia host (seed, tipe dunia, dan semua perubahan blok) akan diunduh otomatis.

**Yang disinkronkan**: blok yang dipasang atau dihancurkan, posisi dan avatar pemain beserta namanya, hewan, TNT dan ledakan, waktu dan cuaca (diatur oleh host), serta chat (tekan `Enter`). Daftar pemain tampil di pojok kiri atas layar.

**Ketentuan**

- Satu room menampung maksimal **8 pemain** (host + 7 teman). Semua pemain harus memakai versi game yang sama.
- Dunia room disimpan di browser host. Dunia milik pemain yang bergabung tidak ditimpa. Setelah **KELUAR ROOM**, pemain kembali ke dunianya sendiri.
- Room ditutup jika host keluar. Jika koneksi host ke server room terputus, game mencoba menyambung ulang secara otomatis.
- Koneksi memakai [PeerJS](https://peerjs.com/) 1.5.5 (dimuat dari jsDelivr) dan server publik PeerJS yang gratis untuk mempertemukan pemain. Data permainan dikirim langsung antarpemain lewat WebRTC.
- Beberapa jaringan (Wi-Fi sekolah/kantor, NAT yang ketat, atau sebagian operator seluler) dapat memblokir WebRTC. Jika tidak bisa terhubung, coba jaringan lain, misalnya hotspot ponsel.

## Pengaturan

Di **Menu → PENGATURAN** kamu bisa mengatur:

- Kualitas grafis (Rendah, Sedang, Tinggi, Ultra) dan jarak pandang (3–10 chunk)
- Sensitivitas mouse dan bidang pandang (FOV 60°–100°)
- Volume musik dan efek suara
- **Waktu** (Pagi, Siang, Senja, Malam), **Siklus Siang-Malam**, dan **Cuaca** (Otomatis, Cerah, Berawan, Hujan, Badai). Saat multipemain, hanya host yang dapat mengubah waktu dan cuaca.
- Tampilan penghitung FPS

Jika FPS rendah, turunkan kualitas grafis atau jarak pandang.

## Dua tema

Ganti tema lewat kartu tema di menu utama atau dengan tombol **T** (joystick: **Back**). Warna voxel, cahaya, kabut, langit, partikel, logo, dan musik berubah dengan transisi halus, tanpa memuat ulang dunia.

| Fantasi Alam | Cyberpunk |
|---|---|
| Rumput subur, pohon raksasa, dan sulur | Terrain logam gelap dan blok grid neon |
| Pilar batu kuno dan batu rune | Monolit baja dan rune neon |
| Pulau melayang dengan air terjun | Kristal magenta, sian, dan ungu yang menyala |
| Sinar matahari keemasan (god rays) dan awan | Matahari synthwave bergaris dan bintang |
| Air biru yang dalam | Cairan neon |
| Kabut keemasan dan kunang-kunang | Kabut ungu neon dan debu neon |

## Grafis

- Material berbasis fisika dengan roughness dan metalness berbeda untuk tiap blok, serta cahaya emisif pada blok neon, kristal, obor, dan lentera.
- Bayangan matahari yang mengikuti pemain, peta lingkungan (PMREM) untuk pantulan, dan ambient occlusion per verteks.
- Pasca-proses: bloom, god rays, efek bawah air, tone mapping ACES, color grading, vignette, dan film grain.
- Chunk berukuran 16×16×128 dimuat otomatis di sekitar pemain. Geometri tiap chunk digabung dan memakai face culling supaya draw call tetap sedikit.

## Penyimpanan

Progres tersimpan otomatis di `localStorage` browser: seed, tipe dunia, perubahan blok, posisi pemain, hotbar, dan pengaturan. Membuat **DUNIA BARU** akan mengganti dunia yang sedang dimainkan. Menghapus data situs di browser juga menghapus dunia yang tersimpan.

## GitHub Pages

Jika GitHub Pages aktif, game bisa dibuka di `https://travis-diaz.github.io/gameamincraft/`. Link ini juga cara termudah untuk mengajak teman bermain multipemain.

Cara mengaktifkannya:

1. Buka **Settings → Pages** di repositori ini.
2. Pada **Build and deployment**, pilih **Deploy from a branch**, lalu branch `main` dan folder `/ (root)`.
3. Klik **Save** dan tunggu beberapa menit.

## Pengujian

Game diuji otomatis di lingkungan headless (Node.js + jsdom dengan tiruan WebGL, Gamepad API, dan PeerJS). Uji tersebut mencakup permainan, variasi dunia, joystick, dan alur multipemain host maupun tamu, dan semua shader divalidasi dengan glslang. Tampilan di browser sungguhan, FPS, joystick fisik, dan koneksi multipemain lewat internet belum diuji langsung, jadi silakan laporkan jika menemukan masalah.

## Teknologi

- [three.js](https://threejs.org/) 0.160.0 (lisensi MIT), dimuat lewat import map dari jsDelivr.
- [PeerJS](https://peerjs.com/) 1.5.5 (lisensi MIT) untuk koneksi multipemain WebRTC.
- WebGL2 dengan shader GLSL kustom untuk blok, air, langit, partikel, dan pasca-proses.
- Gamepad API untuk joystick dan Web Audio API untuk musik serta efek suara prosedural.
