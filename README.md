# REDMI.md — Linux X11 Installer

Panduan lengkap instalasi, penggunaan, dan penjelasan seluruh sistem `linux-x11-installer.sh`.

## 1. Download Installer

Download installer dari MediaFire:

**Link:** https://www.mediafire.com/file/c79u7zs2igf0dk0/linux-x11-installer.sh/file

Setelah file selesai di-download, pastikan namanya:

```text
linux-x11-installer.sh
```

## 2. Instalasi

Buka **Termux**, lalu jalankan:

```bash
termux-setup-storage
cd ~/storage/downloads
chmod +x linux-x11-installer.sh
bash linux-x11-installer.sh install
```

Saat Android meminta izin penyimpanan, pilih **Izinkan**.

Setelah itu installer akan menjalankan proses setup dan meminta pilihan distro serta komponen yang diperlukan.

---

# 3. Sistem Utama

| Sistem | Isi/Fungsi | Cara penggunaan |
|---|---|---|
| **Termux** | Lingkungan Linux utama di Android | Buka Termux |
| **Termux:X11** | Menampilkan desktop Linux secara grafis | Buka Termux:X11 |
| **PRoot-Distro** | Menjalankan distro Linux tanpa root Android | Dikelola installer |
| **Linux Container** | Lingkungan distro Linux terpisah dari Termux | Dikelola installer |
| **X11 Display** | Sistem display grafis Linux | `DISPLAY=:0` |
| **Shared `/tmp`** | Berbagi temporary directory untuk X11/PRoot | Otomatis |
| **PulseAudio** | Sistem audio Linux melalui Termux | Otomatis |
| **DBus** | Session bus untuk aplikasi desktop | Otomatis |
| **Software Rendering** | Fallback rendering untuk kompatibilitas Android | Otomatis |
| **No Root** | Tidak membutuhkan root Android | Otomatis |
| **ARM64/aarch64** | Target perangkat Android ARM64 | Target utama |

---

# 4. Distro Linux

Installer menyediakan enam pilihan distro.

| No. | Distro | Package Manager | Integrasi Desktop | Metode |
|---:|---|---|---|---|
| 1 | **Debian** | APT | XFCE/LXDE/Cinnamon/GNOME/KDE sesuai pilihan | PRoot-Distro |
| 2 | **Ubuntu** | APT | XFCE/LXDE/Cinnamon/GNOME/KDE sesuai pilihan | PRoot-Distro |
| 3 | **Fedora** | DNF | XFCE untuk Termux:X11 | PRoot-Distro |
| 4 | **Arch Linux** | Pacman | XFCE untuk Termux:X11 | PRoot-Distro |
| 5 | **BlackArch Linux** | Pacman | XFCE berbasis Arch | Arch + repository BlackArch |
| 6 | **Parrot OS** | APT | XFCE untuk kompatibilitas X11 | Setup Parrot OS PRoot |

> Ketersediaan paket individual dapat berbeda menurut repository, versi distro, dan arsitektur perangkat.

---

# 5. Desktop Environment

| Desktop | Keterangan | Dukungan |
|---|---|---|
| **XFCE4** | Desktop ringan dan cocok untuk Termux:X11 | Utama |
| **LXDE** | Desktop ringan | Debian/Ubuntu |
| **Cinnamon** | Desktop berbasis GTK | Debian/Ubuntu |
| **GNOME** | Desktop lengkap | Debian/Ubuntu |
| **KDE Plasma** | Desktop KDE lengkap | Debian/Ubuntu |
| **XFCE fallback** | Fallback untuk kompatibilitas X11 | Otomatis sesuai kebutuhan |

Untuk penggunaan di HP Android, desktop ringan umumnya lebih hemat resource.

---

# 6. Menjalankan Desktop

Setelah instalasi berhasil:

```bash
desktop
```

Kemudian buka aplikasi **Termux:X11**.

Sistem desktop menggunakan environment X11 yang disiapkan installer.

Jika ingin memulai sesi desktop kembali:

```bash
desktop
```

---

# 7. Lima Command Utama

| Command | Fungsi | Penggunaan |
|---|---|---|
| `desktop` | Menjalankan Desktop Linux + Termux:X11 | Termux |
| `listapp` | Membuka App Store terminal | Termux + terminal Linux |
| `linux-log` | Melihat log | Termux |
| `linux-update` | Update distro | Termux |
| `linux-repair` | Perbaikan sistem | Termux |

Perintah tersebut dibuat sebagai launcher agar dapat dipanggil langsung dari shell.

---

# 8. `listapp`

`listapp` adalah App Store berbasis terminal.

Jalankan:

```bash
listapp
```

Pada installer v3.8, `listapp` juga dibuat di dalam distro Linux sehingga dapat dijalankan dari terminal XFCE:

```bash
listapp
```

Lokasi native:

```text
/usr/local/bin/listapp
```

dan salinan user:

```text
~/bin/listapp
```

Installer juga menambahkan `~/bin` ke environment user bila diperlukan.

## Katalog `listapp`

| No. | Kategori | Jumlah |
|---:|---|---:|
| 1 | Browser | 3 |
| 2 | Monitor | 5 |
| 3 | Sistem | 5 |
| 4 | Editor | 5 |
| 5 | Dev | 23 |
| 6 | FileManager | 5 |
| 7 | Media | 5 |
| 8 | Office | 6 |
| 9 | Utilitas | 6 |
| 10 | CyberSecurity | 35 |
| 11 | Coding | 10 |
| 12 | Themes | 10 |
| 13 | Icons | 10 |
| 14 | DockPanel | 10 |
| 15 | Cursors | 10 |
| 16 | TopBar | 10 |
| | **Total** | **158** |

---

# 9. Browser

| Aplikasi | Fungsi |
|---|---|
| Firefox | Web browser |
| Chromium | Browser berbasis Chromium |
| Lynx | Browser terminal |

---

# 10. Monitor

| Aplikasi | Fungsi |
|---|---|
| htop | Process monitor |
| btop | Resource monitor |
| glances | System monitor |
| ncdu | Disk usage analyzer |
| iotop | I/O monitor |

---

# 11. Sistem

| Aplikasi | Fungsi |
|---|---|
| neofetch | Informasi sistem |
| fastfetch | Informasi sistem |
| tmux | Terminal multiplexer |
| screen | Terminal multiplexer |
| cron | Penjadwal pekerjaan |

---

# 12. Editor

| Aplikasi | Fungsi |
|---|---|
| nano | Text editor |
| vim | Vi Improved |
| neovim | Modern terminal editor |
| emacs | Extensible editor |
| micro | Modern terminal editor |

---

# 13. Development

| Aplikasi | Fungsi |
|---|---|
| git | Version control |
| Python 3 | Python |
| pip | Python package manager |
| Node.js | JavaScript runtime |
| npm | Node package manager |
| Go | Go language |
| Rust | Rust language |
| Ruby | Ruby language |
| PHP | PHP |
| GCC | C compiler |
| G++ | C++ compiler |
| Make | Build automation |
| CMake | Build system |
| Meson | Build system |
| curl | Data transfer |
| wget | Downloader |
| jq | JSON processor |
| OpenSSH Client | SSH client |
| OpenSSH Server | SSH server |
| build-essential | Development tools |
| SQLite3 | Database |
| MariaDB Client | Database client |
| PostgreSQL Client | Database client |

---

# 14. File Manager

| Aplikasi | Fungsi |
|---|---|
| Thunar | XFCE file manager |
| Nautilus | GNOME file manager |
| PCManFM | Lightweight file manager |
| Midnight Commander | Terminal file manager |
| Ranger | Terminal file manager |

---

# 15. Media

| Aplikasi | Fungsi |
|---|---|
| MPV | Media player |
| VLC | Media player |
| FFmpeg | Multimedia framework |
| Audacity | Audio editor |
| GIMP | Image editor |

---

# 16. Office

| Aplikasi | Fungsi |
|---|---|
| LibreOffice | Office suite |
| LibreOffice Writer | Dokumen |
| LibreOffice Calc | Spreadsheet |
| LibreOffice Impress | Presentasi |
| Evince | PDF viewer |
| Okular | Document/PDF viewer |

---

# 17. Utilitas

| Aplikasi | Fungsi |
|---|---|
| tree | Struktur folder |
| bat | Pengganti `cat` dengan highlighting |
| fzf | Fuzzy finder |
| ripgrep | Pencarian teks |
| fd-find | Pencarian file |
| tldr | Manual command ringkas |

---

# 18. CyberSecurity — 35 Tools

| No. | Tool | Fungsi |
|---:|---|---|
| 1 | Nmap | Network discovery dan port scanning |
| 2 | Masscan | High-speed port scanner |
| 3 | RustScan | Fast port scanner |
| 4 | Hydra | Login auditing |
| 5 | Medusa | Parallel login auditing |
| 6 | John the Ripper | Password hash auditing |
| 7 | Hashcat | Password recovery/auditing |
| 8 | HashID | Identifikasi format hash |
| 9 | Metasploit Exploit Framework | Penetration-testing framework |
| 10 | SQLMap | SQL injection testing |
| 11 | Nikto | Web server security scanner |
| 12 | Gobuster | Directory/DNS/vhost enumeration |
| 13 | FFUF | Web fuzzing |
| 14 | Wfuzz | Web application fuzzing |
| 15 | Dirb | Web content scanner |
| 16 | Dirsearch | Web path discovery |
| 17 | DNSRecon | DNS enumeration |
| 18 | DNSenum | DNS enumeration |
| 19 | Amass | Attack-surface discovery |
| 20 | Subfinder | Passive subdomain discovery |
| 21 | WhatWeb | Web technology fingerprinting |
| 22 | Wapiti | Web vulnerability scanner |
| 23 | Netcat | Network debugging |
| 24 | Socat | Bidirectional relay |
| 25 | Hping3 | Packet/network testing |
| 26 | Tcpdump | Packet capture |
| 27 | TShark | CLI packet analyzer |
| 28 | Wireshark | Graphical packet analyzer |
| 29 | ARPScan | Local network discovery |
| 30 | Bettercap | Network reconnaissance |
| 31 | Ettercap | Network protocol analysis |
| 32 | Enum4linux | SMB/Windows enumeration |
| 33 | Impacket | Network protocol toolkit |
| 34 | Responder | LLMNR/NBT-NS/mDNS analysis |
| 35 | NetExec | Network service enumeration |

Gunakan tools keamanan hanya pada sistem/jaringan yang Anda miliki atau yang memang Anda berwenang untuk menguji.

---

# 19. Coding — 10 Aplikasi

| No. | Aplikasi | Keterangan |
|---:|---|---|
| 1 | Code OSS | Open-source VS Code build |
| 2 | VSCodium | VS Code tanpa telemetry Microsoft |
| 3 | Geany | Lightweight IDE |
| 4 | Kate | Advanced editor |
| 5 | Lite XL | Lightweight code editor |
| 6 | Mousepad | XFCE editor |
| 7 | Gedit | GNOME editor |
| 8 | Pluma | MATE editor |
| 9 | Sublime Text | Code/text editor |
| 10 | Zed | Modern code editor |

---

# 20. Themes — 10

| No. | Theme |
|---:|---|
| 1 | WhiteSur |
| 2 | Qogir |
| 3 | Orchis |
| 4 | Colloid |
| 5 | Graphite |
| 6 | Nordic |
| 7 | Catppuccin GTK |
| 8 | Nephrite |
| 9 | Arc |
| 10 | Materia |

Folder:

```bash
~/Themes
```

Untuk mengatur theme XFCE:

```bash
xfce4-appearance-settings
```

---

# 21. Icons — 10

| No. | Icon |
|---:|---|
| 1 | Papirus Icons |
| 2 | Numix Icons |
| 3 | Breeze Icons |
| 4 | Adwaita Icons |
| 5 | Elementary XFCE Icons |
| 6 | Moka Icons |
| 7 | Faenza Icons |
| 8 | Humanity Icons |
| 9 | Hicolor Icons |
| 10 | Oxygen Icons |

---

# 22. Dock / Panel — 10

| No. | Dock/Panel |
|---:|---|
| 1 | Plank |
| 2 | Cairo-Dock |
| 3 | Docky |
| 4 | Tint2 |
| 5 | XFCE Panel |
| 6 | XFCE Docklike |
| 7 | Rofi |
| 8 | Ulauncher |
| 9 | Albert |
| 10 | Kupfer |

## Pengaturan Plank

Setelah Plank dipasang:

```bash
plank --preferences
```

---

# 23. Cursors — 10

| No. | Cursor |
|---:|---|
| 1 | Bibata Modern Ice |
| 2 | Bibata Modern Amber |
| 3 | Bibata Modern Classic |
| 4 | Breeze Cursor |
| 5 | DMZ White Cursor |
| 6 | DMZ Black Cursor |
| 7 | XCursor Themes |
| 8 | Capitaine Cursor |
| 9 | Oreo Cursor |
| 10 | Volantes Cursor |

---

# 24. TopBar — 10

TopBar menggunakan preset Tint2.

| No. | TopBar |
|---:|---|
| 1 | TopBar Aurora |
| 2 | TopBar Midnight |
| 3 | TopBar Nord |
| 4 | TopBar Ocean |
| 5 | TopBar Forest |
| 6 | TopBar Rose |
| 7 | TopBar Mono |
| 8 | TopBar Solar |
| 9 | TopBar Cyber |
| 10 | TopBar Minimal |

Lokasi:

```bash
~/Themes/TopBar
```

Melihat semua preset:

```bash
ls -1 ~/Themes/TopBar
```

Contoh menjalankan:

```bash
tint2 -c ~/Themes/TopBar/Aurora.tint2rc
```

---

# 25. `linux-log`

Gunakan:

```bash
linux-log
```

Fungsi:

| Log | Fungsi |
|---|---|
| Installation log | Riwayat proses instalasi |
| Error log | Informasi error |
| Repair log | Riwayat repair |
| Diagnosis | Membantu mencari masalah |

Lokasi log:

```text
~/.linux-x11-installer/logs/
```

---

# 26. `linux-update`

Gunakan:

```bash
linux-update
```

Sistem update disesuaikan dengan distro:

| Distro | Package Manager |
|---|---|
| Debian | APT |
| Ubuntu | APT |
| Parrot OS | APT |
| Fedora | DNF |
| Arch Linux | Pacman |
| BlackArch | Pacman |

---

# 27. `linux-repair`

Gunakan:

```bash
linux-repair
```

Sistem repair memeriksa/perbaiki komponen dasar seperti:

| Komponen |
|---|
| Distro |
| Container |
| Package manager |
| User Linux |
| Sudo |
| Desktop |
| Termux:X11 |
| Launcher |
| `listapp` |
| Native `listapp` |
| Konfigurasi dasar |

Setelah repair, lihat log:

```bash
linux-log
```

Kemudian coba:

```bash
desktop
```

---

# 28. Sistem Launcher

| Command | Fungsi |
|---|---|
| `desktop` | Launcher Desktop |
| `listapp` | Launcher App Store |
| `linux-log` | Launcher log |
| `linux-update` | Launcher update |
| `linux-repair` | Launcher repair |

Launcher host berada pada:

```text
$PREFIX/bin/
```

Dengan demikian command dapat dipanggil langsung dari Termux.

---

# 29. Native `listapp` di Linux

Agar `listapp` tidak hanya bekerja di Termux, installer v3.8 membuat:

```text
/usr/local/bin/listapp
```

dan:

```text
~/bin/listapp
```

Kemudian `~/bin` dimasukkan ke PATH user bila diperlukan.

Dengan demikian dari terminal distro:

```bash
debian@localhost:~$ listapp
```

atau user distro lain:

```bash
user@localhost:~$ listapp
```

dapat langsung membuka App Store.

Mekanisme ini berlaku untuk:

- Debian
- Ubuntu
- Fedora
- Arch Linux
- BlackArch Linux
- Parrot OS

---

# 30. Self-Test

Installer memiliki pemeriksaan terhadap komponen utama.

| Pemeriksaan | Tujuan |
|---|---|
| Termux | Memastikan environment host |
| PRoot-Distro | Memastikan runtime |
| Distro | Memastikan container benar-benar bisa dijalankan |
| User | Memastikan user Linux |
| Sudo | Memastikan administrasi |
| Desktop | Memastikan desktop terpasang |
| Termux:X11 | Memastikan GUI tersedia |
| Shared `/tmp` | Integrasi X11/PRoot |
| Audio | Integrasi audio |
| `listapp` | App Store host |
| Native `listapp` | App Store dalam distro |
| Launcher | Memastikan command utama tersedia |

---

# 31. Jika Command Tidak Ditemukan

Periksa:

```bash
command -v desktop
command -v listapp
command -v linux-log
command -v linux-update
command -v linux-repair
```

Jika command utama hilang, jalankan:

```bash
linux-repair
```

Jika `linux-repair` juga tidak ditemukan, jalankan kembali installer:

```bash
cd ~/storage/downloads
bash linux-x11-installer.sh install
```

---

# 32. Jika Desktop Tidak Tampil

Urutan pemeriksaan:

```bash
linux-log
linux-repair
desktop
```

Pastikan **Termux:X11** sudah terpasang.

Setelah:

```bash
desktop
```

buka aplikasi **Termux:X11**.

---

# 33. Alur Penggunaan Lengkap

```text
Android
   │
   ▼
Termux
   │
   ├── Termux:X11
   │
   ▼
PRoot-Distro
   │
   ▼
Pilih Distro
   │
   ├── Debian
   ├── Ubuntu
   ├── Fedora
   ├── Arch Linux
   ├── BlackArch
   └── Parrot OS
   │
   ▼
Pilih/Install Desktop
   │
   ▼
Konfigurasi X11
   │
   ▼
Konfigurasi Audio + DBus
   │
   ▼
Self-Test
   │
   ▼
desktop
   │
   ▼
Termux:X11
   │
   ▼
listapp
   │
   ├── Browser
   ├── Development
   ├── CyberSecurity
   ├── Coding
   ├── Themes
   ├── Icons
   ├── Dock/Panel
   ├── Cursors
   └── TopBar
```

---

# 34. Perintah Harian

| Kebutuhan | Command |
|---|---|
| Mulai desktop | `desktop` |
| Buka App Store | `listapp` |
| Lihat log | `linux-log` |
| Update Linux | `linux-update` |
| Repair Linux | `linux-repair` |
| Pengaturan Plank | `plank --preferences` |
| Pengaturan XFCE theme | `xfce4-appearance-settings` |
| Lihat TopBar | `ls -1 ~/Themes/TopBar` |

---

# 35. Ringkasan Keseluruhan

| Sistem | Jumlah/Status |
|---|---:|
| Distro Linux | **6** |
| Desktop Environment utama | **5** |
| Kategori App Store | **16** |
| Total item App Store | **158** |
| CyberSecurity | **35** |
| Coding | **10** |
| Themes | **10** |
| Icons | **10** |
| Dock/Panel | **10** |
| Cursors | **10** |
| TopBar | **10** |
| Command utama | **5** |
| X11 | **Terintegrasi** |
| Audio | **Terintegrasi** |
| DBus | **Terintegrasi** |
| Self-Test | **Terintegrasi** |
| Update | **Terintegrasi** |
| Repair | **Terintegrasi** |
| Log | **Terintegrasi** |
| Native `listapp` dalam distro | **Terintegrasi** |
| Root Android | **Tidak diperlukan** |

---

# 36. Instalasi Paling Singkat

```bash
termux-setup-storage
cd ~/storage/downloads
chmod +x linux-x11-installer.sh
bash linux-x11-installer.sh install
```

Setelah instalasi:

```bash
desktop
```

Buka **Termux:X11**, kemudian:

```bash
listapp
```

Untuk pemeliharaan:

```bash
linux-update
linux-repair
linux-log
```

---

## Catatan

Dokumen ini menjelaskan sistem dan katalog berdasarkan installer yang sedang digunakan. Ketersediaan paket tertentu tetap dapat berbeda menurut repository distro dan arsitektur perangkat. Instalasi penuh pada perangkat Android fisik harus dianggap sebagai tahap runtime testing tersendiri.

