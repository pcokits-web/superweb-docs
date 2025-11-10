# 📘 PANDUAN ADMIN — SISTEM EXTERNAL DOCUMENTS PORTAL PCO KITS (Versi Konsolidasi)

**Dokumen Versi:** v3.1 (Konsolidasi)  
**Tanggal Revisi:** 10 November 2025  
**Disusun oleh:** Divisi QA & IT — PCO Kits  
**Disetujui oleh:** Manajer Operasional

---

## DAFTAR ISI (Ringkas)
1. Pendahuluan & Peran Admin
2. Login & Akses Awal
3. Navigasi Antarmuka & Shortcut
4. Struktur Folder & Standar Penamaan
5. Manajemen Folder (buat, rename, move, delete)
6. Upload & Manajemen File (single/multi/folder, tag, metadata, preview, inline edit)
7. Versioning & Proteksi
8. Manage Access (RBAC, inheritance, eksternal)
9. Trash, Restore, Retensi
10. Keamanan, Enkripsi, Backup, Incident Response
11. Fitur Lanjutan (Advanced Search, Integrasi, Template, Review Workflow, Notifikasi, Audit/Reports)
12. Dashboard Analitik & Pelacakan Aktivitas
13. SOP Harian/Mingguan/Bulanan
14. Checklist, Do/Don't, & Naming Examples
15. Troubleshooting & FAQ
16. Lampiran (Template, Contoh Form, Tabel Ikon Aksi)

---

## 🏢 1) Pendahuluan & Peran Admin
Sistem **External Documents** adalah pusat kendali dokumen yang berinteraksi dengan pihak luar (klien, vendor, auditor, partner). Admin bertugas memastikan **keteraturan, keamanan, ketersediaan**, dan **auditability** dokumen.

**Peran utama Admin:**
- Merancang **struktur folder**; menegakkan **standar penamaan**.
- Mengatur **izin (RBAC)** dan **akses eksternal**.
- Menjaga **integritas & keamanan** (enkripsi, 2FA, backup).
- Menangani **versioning, restore, retensi**.
- Menyediakan **laporan audit** dan **mendukung staf** operasional.

---

## 🔐 2) Login & Akses Awal

**Langkah Login:**
1. Buka: **https://pco-kit.co.id**
2. Klik **Employee Portal / Login → Employee**
3. Masukkan **Email Address** & **Password**, klik **Login**
4. Masuk ke **Dashboard Admin**

**Lupa Password:**
- **Forgot Password** → cek email → set password baru  
- Kebijakan: min 8 karakter; huruf besar/kecil; angka; simbol; tidak sama dengan 3 password terakhir

**Hak Admin default:**
- CRUD semua file/folder + **Manage Access** + **Audit Log** + **Settings**
- Bisa **suspend** akses staf yang melanggar

---

## 🧭 3) Navigasi Antarmuka & Shortcut

**Tata letak:**
- **Sidebar Kiri:** Dashboard, Documents (Internal/External), Vendors, Reports, Settings
- **Area Tengah:** Daftar folder/file + detail panel
- **Header:** Global Search, Notifikasi, Profil, Logout

**Shortcut utama (toolbar atas):**
- 🔍 **Search** — cari file/folder/tag/uploader
- ➕ **New Folder**
- 📤 **Add Files** (Upload File / Upload Folder / Upload Multiple)
- 👥 **Manage Access** (kontekstual: folder/file terpilih)
- 🗑️ **Trash**

**Panel Aktivitas:** upload terbaru, edit, delete, perubahan akses, dengan timestamp & lokasi.

---

## 🗂️ 4) Struktur Folder & Standar Penamaan

### 4.1 Folder Operasional (contoh awal)
| Folder | Keterangan |
|-------|------------|
| **Agreement** | Kontrak/Perjanjian/MOU |
| **Certificates and Other Documents** | Sertifikat, izin legal |
| **Company Profile** | Profil & materi publik |
| **Complaint Log** | Keluhan pelanggan & tindakan |
| **Correspondences** | Surat menyurat resmi |
| **Monitoring Layout** | Layout/blueprint/peta |
| **MSDS** | Material Safety Data Sheet |
| **Pest Management Report** | Laporan pengendalian hama |
| **Schedule** | Jadwal kegiatan/inspeksi |
| **Service Report** | Laporan hasil pekerjaan |

> Admin boleh menambah kategori lain (mis. **Vendor Documents**, **Reports**), sesuai kebutuhan.

### 4.2 Standar Penamaan (WAJIB)
**Folder:**  
`[Tahun]_[Kategori]_[NamaKlien/Proyek]`  
Contoh: `2025_Agreement_PTABC`, `2025_Reports_Telkom`

**File:**  
`[YYYY-MM-DD]_[NamaDokumen]_v[Versi].[ext]`  
Contoh: `2025-02-15_AuditReport_v2.pdf`

**Tips:**
- Hindari spasi ganda/karakter terlarang (`# @ % ? !`)
- Maks. kedalaman hierarki: **5 level**
- Wajib **Deskripsi** pada folder tingkat-1

---

## 📁 5) Manajemen Folder

### 5.1 Buat Folder Baru
1. Documents → **External Documents**
2. Klik **New Folder**
3. Isi **Folder Name**, **Parent Folder** (opsional), **Description** (opsional)
4. **Create Folder**

### 5.2 Rename Folder
- Klik kanan → **Rename** → isi nama baru → **Save**

### 5.3 Pindahkan Folder
- Klik kanan → **Move** → pilih lokasi → **Confirm Move**  
  (izin & metadata **tetap** terbawa)

### 5.4 Hapus Folder
- Klik kanan → **Delete** → **Yes**  
  (masuk **Trash** selama 30 hari sebelum hard-delete otomatis)

### 5.5 Tips Tata Kelola
- Kelompokkan **berdasarkan fungsi & tahun**
- Hindari “folder pribadi”
- **Review struktur** tiap **6 bulan**

---

## 📤 6) Upload & Manajemen File

### 6.1 Upload File Tunggal
Folder → **Add Files → Upload File** → pilih berkas → (opsional: **Description**) → **Upload**  
_Notifikasi:_ “Upload successful. File saved with version 1.0.”

### 6.2 Upload Multi-File
**Add Files → Upload Multiple Files** → pilih banyak berkas → **Upload All**

### 6.3 Upload Satu Folder
**Add Files → Upload Folder** → pilih folder → **Upload Folder**  
(struktur subfolder dipertahankan)

### 6.4 Drag & Drop
Buka folder tujuan → seret file ke area bertanda **Drag-and-drop…**

### 6.5 Format & Batas
- Didukung: `.pdf, .docx, .xlsx, .pptx, .jpg, .png, .svg, .zip, .rar, .txt, .csv, .msg`
- Maks file: **200 MB**; batch folder: **2 GB**
- Validasi otomatis: tipe, ukuran, nama, malware  
  (gagal → “unsupported type or size limit exceeded”)

### 6.6 Metadata Otomatis
- Uploader, Tanggal, Folder asal, Ukuran, **Checksum MD5**, **Version ID**

### 6.7 Penamaan & Versi Otomatis
Nama duplikat → sistem buat suffix versi (`_v2`, `_v3`)  
Riwayat di **Version History**

### 6.8 Tag & Properties
File → **Properties** → **Description**, **Tag**, **Category** → **Save**  
Contoh tag: `#Legal`, `#Audit2025`, `#Vendor_XYZ`

### 6.9 Preview & Download
Double-click untuk **preview** (PDF/Gambar/Office); **Download** untuk salin lokal

### 6.10 Edit Online (Inline)
File Office → **Edit Online** → **Save and Close** → otomatis naik **versi**

---

## 🧾 7) Versioning & Proteksi

### 7.1 Version History
Klik kanan → **Version History** → lihat **Nomor Versi / Editor / Tanggal / Catatan** → **Preview/Restore**

### 7.2 Compare Versions
Klik kanan → **Compare Versions** → pilih dua versi → highlight perubahan

### 7.3 Kelola Versi Lama
**Manage Versions** → pilih → **Delete Selected Versions**  
(catatan: hanya Admin; versi terbaru tak bisa dihapus)

### 7.4 Lock Version
Klik kanan → **Lock Version** → alasan → **Confirm**  
(Buka kunci bila perlu revisi)

### 7.5 File Locking (Saat Edit)
File terkunci otomatis; Admin dapat **Force Unlock** jika macet

---

## 👥 8) Manage Access (RBAC & Eksternal)

### 8.1 Peran (RBAC)
| Role | Hak |
|------|-----|
| **Viewer** | Lihat/unduh |
| **Uploader** | Lihat + unggah |
| **Editor** | Lihat + unggah + ubah/rename/move |
| **Manager/Admin** | Semua + atur izin |

### 8.2 Beri Akses ke Staf
Folder/File → **Manage Access** → **Add User** → pilih user → set **Viewer/Editor/Uploader/Manager** → **Save**

### 8.3 Akses Eksternal (Vendor/Klien)
**Manage Access** → masukkan email eksternal → **View Only** → **Send Invitation**  
(Link kadaluarsa default **7 hari**)

### 8.4 Hapus/Suspend Akses
**Manage Access** → ikon **❌** (hapus) atau **Suspend Access** (bekukan sementara)

### 8.5 Inheritance & Subfolder
- Opsi **Inherit parent access** atau **Custom permissions** di tiap subfolder
- Opsi **Apply to all subfolders** untuk penerapan massal

### 8.6 Audit Akses (Wajib Triwulanan)
- Bersihkan user non-aktif
- Validasi kesesuaian peran
- Ekspor laporan untuk QA/ISO

---

## 🗑️ 9) Trash, Restore, Retensi

### 9.1 Hapus (Soft Delete)
File/Folder → **Delete** → konfirmasi → masuk **Trash**

### 9.2 Hapus Massal
Checklist multi → **Delete** → konfirmasi

### 9.3 Trash View
Sidebar → **Trash** → lihat **asal, penghapus, tanggal**

### 9.4 Restore
**Trash** → klik kanan → **Restore**  
(Jika folder asal hilang, dibuat `/Restored_[Tanggal]`)

### 9.5 Hard Delete
**Trash** → item → **Delete Permanently** (irreversible)

### 9.6 Empty Trash
Tombol **Empty Trash** → konfirmasi → log otomatis

### 9.7 Retensi Otomatis
- Trash auto-hard-delete: **30 hari** (biasa), **90 hari** (*Under Review*)
- Reminder H-3: “Files in Trash will be deleted permanently in 3 days.”

---

## 🔒 10) Keamanan, Enkripsi, Backup, Incident Response

### 10.1 Autentikasi & Sesi
- **2FA** aktif; auto-logout idle **30 menit**
- 5x gagal login → **lock** 15 menit
- Log login: IP, lokasi, browser

### 10.2 Enkripsi
- **AES-256** at-rest; **TLS 1.3** in-transit
- Kunci enkripsi unik per file

### 10.3 Backup Jadwal
| Tipe | Frekuensi | Lokasi |
|------|-----------|--------|
| Incremental | 6 jam | Server cadangan 1 |
| Full | Mingguan | Server cadangan 2 (offsite) |
| Snapshot | Harian 00:00 | Cloud archive |

### 10.4 Restore via IT
Laporkan **nama file/folder, lokasi, waktu terakhir** → SLA **≤24 jam**

### 10.5 Audit Keamanan (3 bulanan)
Cek izin folder sensitif, aktivitas anomali, log enkripsi

### 10.6 Notifikasi Keamanan
Login lokasi baru, upload tak wajar, hapus massal → **Security Alert**

### 10.7 Kebijakan Aman (Do/Don’t)
- Jangan bagikan password / unduh rahasia ke perangkat pribadi
- Logout bila meninggalkan perangkat
- Gunakan **VPN** saat akses dari luar kantor

### 10.8 Incident Response
Isolasi → Laporkan ke IT Sec → Investigasi log → Pulihkan dari backup → Dokumentasi insiden (QA)

### 10.9 Client-Side Encryption (Opsional)
**Encrypt before upload** → set password → dekripsi di portal oleh user sah

### 10.10 Kepatuhan
ISO/IEC 27001, ISO 9001, SOC 2 Type II (rujukan standar praktik)

---

## ⚙️ 11) Fitur Lanjutan (Produktivitas & Auditability)

### 11.1 Advanced Search
Filter: **Keyword, Uploader, Date Range, Tags, Folder, File Type, Version, Access Level**

### 11.2 Saved Search
Simpan & bagikan pencarian penting (mis. “Dokumen Audit 2025”)

### 11.3 Auto Filters
**Recently Uploaded / Edited / Most Viewed / Accessed by External**

### 11.4 Activity Log & Export
Reports → **Activity Log** → filter → **Export CSV/XLSX/PDF**

### 11.5 Integrasi
**Google Drive / OneDrive / Dropbox / Gmail/Outlook / Slack/Teams**  
Settings → **Integrations** → **Connect** (API) → Save

### 11.6 Notifikasi
Upload baru, delete, akses eksternal, revisi, kedaluwarsa → set di **Notification Preferences**

### 11.7 Template
Documents → **Templates** → **Use Template** / **Upload Template (.docx/.xlsx)**

### 11.8 Auto Version Comment
“Version 3 uploaded by Admin (John) — revision per client feedback.”

### 11.9 Reminder & Deadline
Klik kanan file → **Set Reminder** (tanggal, penerima) → email otomatis

### 11.10 Review Workflow
**Send for Review** → pilih reviewer → status: **Pending / Approved / Rejected (with comment)**

### 11.11 Analitik Dokumen
Reports → **Dashboard**: total file/kategori, user aktif, tren upload, aktif vs arsip

### 11.12 Offline Sync (Queue)
Ikon ⏳ (antri) → otomatis lanjut saat koneksi pulih → ✅

### 11.13 Full-Text Search (OCR)
Cari di isi PDF hasil scan (mis. `"sertifikat ISO 9001" within:Certificates`)

### 11.14 Backup per Folder
Klik kanan folder → **Backup Now (.zip terenkripsi)** / **Restore Backup**

### 11.15 Export Metadata
Export CSV: nama, lokasi, ukuran, tag, versi, akses

### 11.16 Watermark & Download Tracking
Unduhan ber-watermark:  
`Confidential – PCO Kits [Nama Pengguna] [Tanggal Unduh]`  
Log: **siapa/waktu/IP**

### 11.17 Audit Mode
Semua aksi terekam, **hapus dinonaktifkan**. Cocok periode audit.

### 11.18 Maintenance Mode
Settings → System → aktifkan; hanya Admin IT yang full akses.

---

## 📊 12) Dashboard Analitik & Pelacakan
- Top uploader/editor, puncak aktivitas
- Kepatuhan penamaan (deteksi outlier)
- SLA review & reminder kedaluwarsa
- Trend kategori (Agreement/Reports/Certificates)

---

## 🧩 13) SOP Rutin (Checklist Operasional)

**Harian**
- Tinjau **Panel Aktivitas** & **Notifikasi**
- Cek **Trash** (restore bila perlu)
- Validasi upload masuk (tag/penamaan/izin)

**Mingguan**
- Audit sampling: penamaan, tag, izin folder aktif
- Jalankan **Saved Search** untuk item due/overdue
- Export **Activity Log** ringkas (arsip internal)

**Bulanan**
- Review struktur folder + arsipkan yang pasif
- Validasi akses eksternal yang masih aktif
- Rekap **Dashboard**; laporkan ke QA/Manajer

**Triwulanan**
- Audit izin menyeluruh; uji **restore** dari backup; cek kepatuhan keamanan

---

## ✅ 14) Checklist, Do/Don’t, & Contoh

**Upload Cepat (Do)**
- [ ] Nama file format: `YYYY-MM-DD_DocName_vX.ext`
- [ ] Tag minimal 1 (mis. `#Audit2025`)
- [ ] Set izin sesuai peran
- [ ] Tambahkan **Version Comment** saat revisi

**Jangan (Don’t)**
- [ ] Upload file >200MB (pakai kompresi/arsip)
- [ ] Ubah izin tanpa catatan
- [ ] Pakai nama umum: “scan.pdf”, “new.docx”
- [ ] Edit file terkunci tanpa koordinasi

**Contoh Penamaan**
- `2025-03-10_ServiceReport_SiteA_v1.pdf`
- `2025_Agreement_PTDelta` (folder)

---

## 🛠️ 15) Troubleshooting & FAQ

**Q: Upload gagal, kenapa?**  
A: Cek ukuran/tipe; ubah nama tanpa karakter terlarang; cek koneksi; lihat pesan validasi.

**Q: Tidak bisa hapus file, kenapa?**  
A: Mungkin **Audit Mode** aktif atau file sedang **locked**. Minta Admin IT/Manager.

**Q: Undangan akses eksternal tidak bisa dibuka.**  
A: Link kadaluarsa (7 hari). Kirim ulang; cek domain email & spam.

**Q: File hilang dari folder.**  
A: Cari di **Trash**; pakai **Advanced Search**; cek **Activity Log** siapa memindahkan.

**Q: Versi salah yang aktif.**  
A: **Version History → Restore** versi yang benar; tambahkan komentar klarifikasi.

---

## 📎 16) Lampiran

**A. Tabel Ikon Aksi**
- ✏️ Rename
- ↔️ Move
- 🗑️ Delete
- 👥 Manage Access
- 📤 Upload
- 🔍 Search

**B. Template Internal (disarankan)**
- Naming Guide (PDF)
- SOP Review Workflow (DOCX)
- Form Permintaan Akses Eksternal (DOCX)
- Format Laporan Audit Log Bulanan (XLSX)

**C. Kontak Dukungan**
Helpdesk PCO Kits IT  
Email: **support@pco-kit.co.id**  
Ext: **1404 / 1405**  
Jam: **Senin–Jumat, 08:00–17:00 WIB**
