# DDCMart — Kanal Pembaruan Resmi

Repository ini khusus **distribusi pembaruan DDCMart untuk UMKM**. Nama dan logo toko tetap dapat diatur oleh pemilik toko masing-masing.

## Status kanal
**MENUNGGU AKTIVASI.** Installer Windows resmi belum dipublikasikan dan `latest.json` bertanda tangan belum tersedia. Pembaruan otomatis **belum aktif**.

- **Alamat tetap:** `https://raw.githubusercontent.com/dansDigitalCenter/ddcmart-updates/main/latest.json`
- **Unduhan installer:** [GitHub Releases](https://github.com/dansDigitalCenter/ddcmart-updates/releases)
- **Kode sumber dan data toko:** **tidak disimpan di repository ini**.

Agar klien tanpa akun GitHub bisa memeriksa pembaruan, repository harus berstatus **Public**.

## Untuk pengembang
Baca [Panduan Pemilik](PANDUAN-PEMILIK.md). Gunakan **DDCMart V0.9.2 Kit GitHub** untuk konfigurasi kunci, pembuatan installer, penandatanganan rilis, dan publikasi.

**Jangan unggah:** `private_key.pem`, kunci lain, database SQLite, backup dan data pelanggan, log perangkat kasir, atau kode sumber aplikasi ke repository publik ini.

## Cara kerja update
Aplikasi hanya menerima manifest yang memiliki tanda tangan Ed25519 valid; unduhan installer harus cocok dengan ukuran dan SHA-256 yang ditandatangani. Pemasangan update dilakukan setelah sesi kasir ditutup. Transaksi tetap dapat berjalan tanpa koneksi internet.

**Setiap rilis wajib diuji pada satu PC pilot sebelum diterbitkan ke seluruh klien.**
