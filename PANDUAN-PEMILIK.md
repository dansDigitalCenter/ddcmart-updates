# Panduan Pemilik — Mengaktifkan Update Online

**Repository:** `dansDigitalCenter/ddcmart-updates`  
**Kanal:** `https://raw.githubusercontent.com/dansDigitalCenter/ddcmart-updates/main/latest.json`

## Langkah 1 — Satu kali: buat repository publik
1. Buka repository, klik **Settings**.
2. Di halaman **General**, gulir ke **Danger Zone**.
3. Klik **Change repository visibility** → **Make public**, lalu konfirmasi.
4. Pastikan repository ini hanya memuat panduan, manifest update bertanda tangan, dan installer rilis. **Jangan taruh source aplikasi atau data toko di sini.**

Ini penting karena aplikasi UMKM tidak boleh membutuhkan login GitHub untuk mengecek update.

## Langkah 2 — Satu kali: siapkan komputer pengembang
1. Unduh dan ekstrak **DDCMart V0.9.2 Kit GitHub** dari percakapan pengembang.
2. Jalankan `0-Konfigurasi-Update.bat`. URL kanal GitHub diisi otomatis dan kunci privat dibuat hanya di komputer pengembang: `%USERPROFILE%\DDCMart-RAHASIA-Update\private_key.pem`.
3. Simpan **cadangan terenkripsi** kunci privat itu di media lain. **Jangan mengirimnya di chat atau mengunggahnya ke GitHub.** Jika hilang, update otomatis klien lama tidak bisa menandatangani rilis baru dengan kunci pengganti.
4. Pada komputer pengembang, instal [GitHub CLI](https://cli.github.com/) (misalnya dengan perintah `winget install --id GitHub.cli -e`) lalu jalankan `gh auth login`. Komputer klien tidak memerlukannya.
5. Python dan NSIS tetap diperlukan untuk **membangun installer di PC pengembang**, tidak di PC klien.

## Langkah 3 — Setiap kali merilis update
1. Jalankan `1-Bangun-Installer.bat`.
2. **Uji** EXE Windows: buka/tutup kasir, transaksi, scanner, printer, stok, PIN, backup, dan data lama.
3. Jalankan `2-Buat-Manifest-Rilis-Online.bat` untuk membuat manifest bertanda tangan sesuai EXE yang sudah diuji.
4. Jalankan `4-Publikasikan-Update-GitHub.bat`, lalu ketik `TERBITKAN` ketika yakin. Alat menolak EXE yang tidak cocok dengan tanda tangan, hash, ukuran atau versinya; ia akan mengunggah installer ke GitHub Releases dan manifest ke `latest.json`.
5. Uji unduhan dari satu PC pilot, **baru** sebarkan ke UMKM lain.

## Catatan penting
- **Status saat ini belum aktif** sampai repo publik, kunci telah dibuat pada PC pengembang, installer resmi dibuat dan ditandatangani, serta release + `latest.json` tersedia.
- Aplikasi lama yang dibangun tanpa URL/kunci perlu instal manual satu kali untuk mengaktifkan kanal.
- GitHub hanya menyimpan file pembaruan. **Database klien tetap berada pada PC klien.**
- Jika internet mati, kasir tetap harus berfungsi offline.
- Jangan mempublikasikan EXE sebelum sudah diuji pada Windows asli.
