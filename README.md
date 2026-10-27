# Notchy — Unduhan

Notchy adalah notch desktop dengan pengingat minum, agenda, fokus, jadwal sholat, hadis harian dan maskot kucing. Fitur yang tersedia berbeda menurut platform dan tahap rilis.

## Windows

[Rilis 1.4.0-preview.1](https://github.com/tetukon9-cmd/Project-Notchy-Releases/releases/tag/v1.4.0-preview.1) menyediakan [installer Windows](https://github.com/tetukon9-cmd/Project-Notchy-Releases/releases/download/v1.4.0-preview.1/Notchy-Setup.exe) dan [ZIP portable Windows](https://github.com/tetukon9-cmd/Project-Notchy-Releases/releases/download/v1.4.0-preview.1/Notchy-v1.4.0-preview.1-portable.zip) untuk Windows 10/11 x64 dengan .NET Framework 4.8. Keluar dari versi lama melalui ikon tray sebelum membuka versi baru. Profil lokal tidak perlu dihapus. [Versi sebelumnya 1.2.3](https://github.com/tetukon9-cmd/Project-Notchy-Releases/releases/tag/v1.2.3) tetap tersedia.

## Sistem

Buka ikon **Sistem**. Kartu CPU/GPU/Memory/Disk/Network/Power/Fullscreen bisa diklik untuk detail. **Perbesar** membuka dashboard tiga kolom dengan gauge, riwayat, per-core dan delapan proses teratas; klik CPU/RAM untuk mengurutkan. Notch tetap ringkas dengan badan yang dapat digulir. Detail menyediakan pemilihan GPU dan interface jaringan yang terdeteksi.

**Pengaturan** pada Sistem menyediakan saklar monitoring, interval 0,5–5 detik, durasi riwayat, pilihan metrik dan proses. Monitoring berhenti saat Sistem/dashboard tidak terlihat. Riwayat dan hitungan transfer sesi dimulai ulang setelah jeda. Data tidak dikirim ke layanan monitoring. Disk adalah baca/tulis aktual, terpisah dari kapasitas. Angka nol terukur berbeda dari Unavailable; clock merupakan nilai yang dilaporkan OS. Watt baterai diberi label **Battery rate**, bukan watt CPU atau daya dari stopkontak. Fullscreen merupakan deteksi jendela, bukan Game Mode Windows.

Kemampuan sensor mengikuti OS/driver. GPU Windows mendukung beberapa adapter; GPU Linux memakai statistik DRM bila tersedia. GPU utilization macOS belum tersedia, dan memori macOS memakai Free (Mach), dengan cache termasuk dalam Used. Temperatur/watt CPU/GPU tanpa sumber yang didukung tetap Unavailable. Ikon proses memakai monogram fallback.

Versi ini lulus 150 pemeriksaan Sistem Windows dan regresi yang dapat dijalankan. Build native Linux/macOS masing-masing lulus 146 kontrak inti dan 52 pemeriksaan UI; pengujian diulang dari paket yang diekstrak. Collector OS juga dijalankan langsung dari executable Native AOT. UAT visual dan performa laptop pengguna tetap diperlukan.
## Agama & Inspirasi

Windows: **Pengaturan > Agama & inspirasi**. Linux/macOS: **Pengaturan > Agama & konten harian**. Dropdown menyediakan Islam, Kristen Protestan, Katolik, Hindu, Buddha dan Khonghucu. Pada Islam, jadwal/adzan dan hadis dapat dimatikan secara terpisah. Pada agama lain, sholat/adzan/hadis tidak aktif dan bacaan menjadi **Inspirasi**. Inspirasi juga bisa dimatikan. Pilihan tersimpan lokal tanpa mereset hidrasi/agenda.

Inspirasi memuat 35 potongan dari terjemahan sumber public domain, tujuh per agama non-Islam, dan tersedia offline. Reader menyediakan rujukan, teks Inggris, atribusi serta **terjemahan bebas Indonesia oleh Notchy, bukan terjemahan resmi kitab suci**. Penomoran Lun Yu mengikuti edisi Legge. Rujukan dan lisensi disertakan pada paket; rendering Indonesia belum mendapat review ahli agama.

## Linux dan macOS

[Rilis 1.4.0-preview.1](https://github.com/tetukon9-cmd/Project-Notchy-Releases/releases/tag/v1.4.0-preview.1) menyediakan:

| Platform | Unduhan | Kebutuhan |
| --- | --- | --- |
| Linux x64 | [tar.gz](https://github.com/tetukon9-cmd/Project-Notchy-Releases/releases/download/v1.4.0-preview.1/Notchy-v1.4.0-preview.1-linux-x64.tar.gz) | Sistem glibc x64 dengan X11/XWayland, pustaka X11/fontconfig/ICU. Diuji pada Ubuntu 22.04. |
| Mac Apple Silicon (M-series) | [ZIP ARM64](https://github.com/tetukon9-cmd/Project-Notchy-Releases/releases/download/v1.4.0-preview.1/Notchy-v1.4.0-preview.1-osx-arm64.zip) | macOS 14 atau lebih baru; diuji pada macOS 15. |
| Mac Intel | [ZIP x64](https://github.com/tetukon9-cmd/Project-Notchy-Releases/releases/download/v1.4.0-preview.1/Notchy-v1.4.0-preview.1-osx-x64.zip) | macOS 14 atau lebih baru; diuji pada macOS 15. |

Ekstrak arsip ke folder baru. Linux: jalankan `./Notchy` dari folder hasil ekstraksi. macOS: aplikasi berada di `Notchy.app`; pertahankan seluruh isinya. Tidak perlu memasang SDK .NET. Arahkan mouse ke notch untuk membuka toolbar ikon; menu Keluar berada pada tray atau halaman Tentang.

Pratinjau ini menyediakan agenda/pengingat lokal, fokus, catatan/pengingat minum, bacaan sesuai agama dan maskot kucing. Pada pilihan Islam, pilih kota serta zona **WIB/WITA/WIT** sebelum pengingat sholat aktif. Internet diperlukan untuk mengambil data sholat/hadis baru; cache yang tersedia tetap bisa dibaca. Audio adzan opsional memakai afplay di macOS atau ffplay/mpv yang sudah terpasang di Linux.

Media/lirik, clipboard history, file shelf, UI iCal dan notification center belum tersedia pada port ini. Native Wayland belum didukung. Pengingat ditampilkan melalui notch. Pengujian otomatis pada runner belum menggantikan UAT MacBook ber-notch, multi-monitor, seluruh desktop Linux, sleep/resume atau performa laptop pengguna.

Paket macOS ditandatangani **ad-hoc**, belum memakai Developer ID/notarization Apple, sehingga Gatekeeper dapat menolak pembukaan paket unduhan. Ini merupakan pratinjau pengembang; distribusi macOS yang dipercaya Gatekeeper menunggu proses signing/notarization. Tidak perlu mematikan keamanan sistem.

Impor profil hanya menyalin `settings.ini`/`meetings.json` ke profil baru dan menolak penimpaan. Data harian berada di `~/.config/NotchyApp` (atau `$XDG_CONFIG_HOME/NotchyApp`) pada Linux, dan `~/Library/Application Support/NotchyApp` pada macOS. Profil sumber dipertahankan.

## Paket dan lisensi

Repository ini hanya memuat halaman unduhan, pemberitahuan lisensi, dan paket hasil build pada Releases. Source aplikasi, semua branch pengembangan dan riwayatnya dikelola secara privat.

Arsip otomatis GitHub bernama **Source code** hanya berisi halaman unduhan ini dan pemberitahuan lisensi, bukan source aplikasi Notchy. Paket aplikasi tidak menyertakan project, source, skrip build atau simbol debug. Binary tetap dapat dianalisis; distribusi tertutup bukan jaminan anti reverse engineering. Salinan source yang pernah diunduh sebelumnya tidak bisa ditarik kembali.

Lihat `checksums.json` pada setiap rilis untuk SHA256 paket. Pemberitahuan Gili, Sela, audio, dan komponen pihak ketiga tetap disertakan dalam aplikasi/paket. Hak dan lisensi komponen tersebut tetap berlaku.
