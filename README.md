# Bhumi MCP: data tanah ATR/BPN, zonasi RDTR OSS, HGU dan konsesi untuk asisten AI

Sambungkan Claude, ChatGPT atau Cursor ke data pertanahan Indonesia lewat Model Context Protocol (MCP). Tanyakan persil, sertifikat, HGU, zonasi RDTR OSS, tambang dan risiko banjir dengan bahasa biasa, tanpa membuka peta satu per satu.

Dibuat untuk **property developer**, agen properti, konsultan, notaris/PPAT, analis kepatuhan dan peneliti yang selama ini mengecek tanah lewat **Bhumi ATR/BPN**, GISTARU, OSS atau platform properti seperti **Perare.io**, dan ingin semuanya dalam satu pertanyaan. Data dijalankan oleh [BumiAtlas](https://bumiatlas.com); informasi lengkap di [bhumi.ai.id](https://bhumi.ai.id).

> Bukan aplikasi resmi dan tidak berafiliasi dengan Kementerian ATR/BPN, OSS maupun Perare. Data berupa salinan sumber publik, bukan bukti kepemilikan atau izin yang sah.

## Hubungkan

```
https://bumiatlas.com/mcp/bhumi
```

Tambahkan sebagai custom connector di klien MCP mana pun, lalu masuk dengan Google. Tidak ada biaya untuk menyambungkan; pemakaian mengikuti batas akun. Panduan per klien: [bumiatlas.com/mcp-docs](https://bumiatlas.com/mcp-docs).

- **Claude:** Settings → Connectors → Add custom connector, tempel alamat di atas, lalu Connect.
- **ChatGPT:** Settings → Apps & Connectors → Advanced → Developer mode, lalu Create dengan alamat di atas dan autentikasi OAuth.

## Yang bisa dicari

- **Persil (bidang tanah) ATR/BPN** dari peta publik Bhumi ATR/BPN: nomor sertifikat, NIB, jenis hak (Hak Milik, HGB, HGU, Hak Pakai, dan lainnya), luas tertulis dan luas peta, tahun, panjang sisi
- **HGU (Hak Guna Usaha)** perkebunan: pemegang hak, luas, penggunaan tanah, masa berlaku dan nomor SK
- **Konsesi tambang** ESDM (IUP, IUPK, KK, PKP2B), konsesi hutan HPH dan HTI, serta kawasan konservasi
- **Zonasi RDTR** dari data OSS/ATR/BPN: zona, sub-zona dan ketentuan khusus di suatu titik
- **Zona Nilai Tanah (ZNT)** dan **bahaya banjir** BNPB InaRISK

## Fungsi

### Persil

| Fungsi | Kegunaan |
|---|---|
| `Parcel_search` | Cari bidang dari nomor sertifikat (14 digit), NIB, kode desa + NIB, atau koordinat `lintang, bujur` |
| `Parcel_get` | Catatan lengkap satu bidang: jenis hak, luas tertulis vs luas peta, sisi, desa, zonasi, zona nilai tanah, risiko banjir; batas dalam GeoJSON |
| `Parcel_overlaps` | Bidang, HGU, konsesi dan kawasan konservasi yang beririsan dengan satu bidang, lengkap dengan luas irisan |
| `Parcel_image` | Citra satelit atau peta jalan dari satu bidang atau titik, dengan semua bidang di sekitarnya digaris dan diberi label NIB |
| `Parcel_find_village` | Cari desa menurut BPN dari nama atau kode, atau baca nomor sertifikat menjadi desa dan kantor pertanahan |

### HGU dan konsesi

| Fungsi | Kegunaan |
|---|---|
| `HGU_search` | Cari HGU menurut pemegang, provinsi, kantor pertanahan, penggunaan tanah atau status aktif |
| `HGU_get` | Catatan lengkap satu HGU: pemegang, luas, penggunaan, masa berlaku, SK; batas dalam GeoJSON |
| `Mining_search` | Cari izin tambang menurut pemegang, grup, komoditas, jenis izin, provinsi atau status |
| `Mining_get` | Catatan lengkap satu izin: pemegang, komoditas, tahap, tanggal mulai dan berakhir, luas; batas dalam GeoJSON |

### Zonasi dan bahaya

| Fungsi | Kegunaan |
|---|---|
| `Zoning_get` | Zona dan sub-zona RDTR di satu titik atau menurut id, dengan aturan dan ketentuan khusus rencananya |
| `Zoning_summary` | Luas wilayah desa atau kabupaten/kota yang dizonakan untuk tiap peruntukan |
| `Flood_get` | Kelas bahaya banjir BNPB InaRISK (rendah, sedang, tinggi) di satu titik |

## Contoh pertanyaan untuk property developer

- *"Sertifikat 22.01.05.03.1.00123: jenis haknya apa dan berapa luasnya?"*
- *"Tanah di -8.6705, 115.2126 zonasinya apa menurut RDTR? Rawan banjir?"*
- *"Apakah bidang ini tumpang tindih dengan HGU, konsesi tambang atau kawasan konservasi?"*
- *"Berapa persen Kabupaten Lombok Tengah yang dizonakan untuk pariwisata?"*
- *"Daftar HGU aktif milik PTPN di Riau dan kapan berakhirnya."*
- *"Izin tambang nikel di Sulawesi Tenggara yang sudah berakhir."*
- *"Desa mana yang berkode BPN 22030903?"*

## Dibandingkan Bhumi ATR/BPN dan Perare

- **Bhumi ATR/BPN** adalah aplikasi peta resmi pemerintah dan sumber data persilnya. MCP ini menyalin data publiknya dan menggabungkannya dengan HGU, konsesi, zonasi dan banjir, sehingga bisa dijawab dalam satu pertanyaan. Untuk status hukum, rujukan akhir tetap ATR/BPN.
- **Perare** berfokus pada estimasi harga pasar dan kerja tim untuk agen properti. MCP ini tidak menampilkan harga pasar, hanya Zona Nilai Tanah sebagai acuan zona.

Perbandingan lengkap: [bhumi.ai.id/perbandingan.html](https://bhumi.ai.id/perbandingan.html).

## Sumber data

- **ATR/BPN**: persil, HGU, batas desa, Zona Nilai Tanah dan RDTR, dari layanan publik ATR/BPN/GISTARU dan OSS. Akses publik tidak otomatis berarti lisensi terbuka; ikuti syarat sumber untuk penggunaan ulang.
- **Nusantara Atlas** (sumber ESDM dan KLHK): konsesi tambang, HPH, HTI dan kawasan konservasi, dengan akurasi batas sekitar 11 m.
- **BNPB InaRISK**: bahaya banjir, sel 100 m, hasil pemodelan untuk penyaringan awal, bukan catatan kejadian.

## Batasan

- Tidak ada nama pemilik untuk bidang biasa; data publik tidak memuatnya. Hanya HGU yang menyertakan nama pemegang hak.
- Cakupan dan tanggal data berbeda-beda; bidang yang tidak muncul belum tentu belum bersertifikat.
- RDTR hanya tersedia untuk kawasan perencanaan tertentu, bukan seluruh kabupaten.
- Luas peta bisa berbeda dari luas di sertifikat. Jawaban AI perlu dicek ulang ke sumber resmi, dan untuk keperluan hukum minta keterangan resmi dari Kantor Pertanahan.
