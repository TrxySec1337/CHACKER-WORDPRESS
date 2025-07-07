
# 🛠️ AUTO LOGS WORDPRESS CHECKER - TRXYSEC1337

**Versi:** `v1.0-stable`  
**Rilis:** 07 Juli 2025  
**Author:** TrxySec1337

---

## 📌 DESKRIPSI

Auto Logs WordPress Checker adalah tools untuk memvalidasi login dari list combo WordPress.  
Mendukung berbagai format login (`url|user|pass`, `url#user@pass`, `url:user:pass`) serta mendeteksi plugin populer seperti WooCommerce, WP File Manager, dan Plugin Installer setelah login.

---

## 🚀 FITUR UNGGULAN

- Validasi login WordPress secara massal
- Deteksi plugin WooCommerce, WP File Manager, Plugin Installer
- Dukungan multi-format login (1, 2, atau 3)
- Simpan otomatis hasil login ke folder `result/`
- Multi-threading (cepat dan efisien)
- Random User-Agent setiap request
- Penanganan error lengkap (timeout, SSL, DNS, format invalid)
- Tidak perlu modul eksternal tambahan

---

## 🧠 LOGIKA DASAR

- Membaca setiap baris combo dari file
- Parsing sesuai format yang dipilih user
- Menentukan apakah target bisa diakses
- Melakukan POST login ke `wp-login.php`
- Jika login berhasil:
  - Simpan ke `loginSuccess.txt`
  - Cek apakah plugin WooCommerce / FileManager / Installer aktif dari isi halaman
- Hasil ditampilkan di terminal dan disimpan otomatis

---

## 📁 STRUKTUR OUTPUT OTOMATIS

| File Output                 | Keterangan                                      |
|----------------------------|-------------------------------------------------|
| `result/loginSuccess.txt`  | Semua login WordPress yang valid                |
| `result/WooCommerce.txt`   | Jika halaman admin mendeteksi WooCommerce       |
| `result/wpfilemanager.txt` | Jika plugin WP File Manager ditemukan           |
| `result/plugin-install.txt`| Jika menu plugin installer aktif                |

---

## 🧾 FORMAT YANG DIDUKUNG

```
MODE 1 → url|user|pass      contoh: https://site.com|admin|123456
MODE 2 → url#user@pass      contoh: https://site.com#admin@123456
MODE 3 → url:user:pass      contoh: https://site.com:admin:123456
```

---

## 🛠️ CARA INSTALL DAN JALANKAN TOOLS

### 1. ✅ PERSYARATAN

- Python 3.x
- Modul `requests` harus tersedia

### 2. 📥 INSTALL MODUL YANG DIPERLUKAN

Jika kamu belum install `requests`, jalankan:

```bash
pip install requests
```

Atau untuk Termux:

```bash
pkg install python
pip install requests
```

### 3. 🧪 MENJALANKAN SCRIPT

```bash
python AUTOCHACKER.py
```

Lalu:

1. Pilih mode format login sesuai file kamu (1/2/3)
2. Masukkan nama file logs (misal: `list.txt`)
3. Masukkan jumlah thread (misal: `10`)
4. Tunggu proses berjalan, hasil disimpan di folder `result`

---

## ⏳ MASA AKTIF TOOLS

Script ini memiliki pembatasan waktu penggunaan:

- Mulai digunakan: **1 Desember 2024**
- Expired: **30 Januari 2026**

Jika lewat dari tanggal tersebut:
```bash
[ERROR] Masa penggunaan program telah habis.
```

---

## 💬 CONTOH OUTPUT

```text
 [+] https://example.com|admin|123456 → Login Berhasil!
 [+] Plugin Detected: WooCommerce, WP File Manager
 [-] http://target.com|admin|wrongpass → Login Gagal
```

---

## 📌 CATATAN TAMBAHAN

- File logs **harus bersih** dan sesuai format
- Script akan **skip otomatis** jika format salah, target error, atau bukan WordPress
- Tidak cocok untuk brute force, hanya untuk validasi combo

---

## 📛 DISCLAIMER

**Tools ini dibuat hanya untuk tujuan edukasi dan pengujian keamanan pribadi.**

> ⚠️ Segala bentuk penyalahgunaan tools ini **di luar tanggung jawab pembuat.**  
> ⚠️ Gunakan hanya pada sistem milik sendiri atau sistem yang kamu memiliki izin eksplisit untuk menguji.

Kami tidak bertanggung jawab atas:
- Akses tidak sah ke server orang lain
- Perusakan data
- Pelanggaran hukum

**Gunakan dengan bijak dan bertanggung jawab.**

---

## 👤 AUTHOR

```
TrxySec1337 | Nocturnal Bytes
```
