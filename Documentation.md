# 📄 Dokumentasi Proyek: Sistem Peminjaman Ruangan 2026

Dokumentasi ini disusun untuk memenuhi standar pengerjaan proyek **PdBL 2026** di Politeknik Elektronika Negeri Surabaya (PENS).

---

## 🏛️ 1. Studi Kasus
**Latar Belakang:** Proses peminjaman ruangan yang bersifat konvensional seringkali menghadapi kendala koordinasi, seperti jadwal yang bertabrakan (*double booking*) dan sulitnya memantau status ketersediaan ruangan secara cepat.

**Solusi yang Ditawarkan:** Membangun ekosistem aplikasi terintegrasi yang terdiri dari aplikasi Web (Admin) dan Mobile (User). Sistem ini memungkinkan sentralisasi data ruangan dan peminjaman sehingga seluruh proses menjadi lebih transparan, cepat, dan terorganisir.

---

## 🏗️ 2. Arsitektur Sistem
Sistem ini dibangun dengan pendekatan **Decoupled Architecture** (Pemisahan Backend dan Frontend):

* **Backend (Server-Side):**
    * Framework: ASP.NET Core 10.0 (Web API).
    * Database: PostgreSQL (Relational Database).
    * Fitur Utama: RESTful API, CORS Policy, dan Swagger OpenAPI.
* **Frontend (Client-Side):**
    * **Web App:** React + Vite + TypeScript (Fokus pada manajemen data).
    * **Mobile App:** Flutter (Fokus pada portabilitas dan reservasi user).
* **Workflow:** Client (Web/Mobile) melakukan request via protokol HTTP -> API Server (ASP.NET) memproses logika bisnis -> Database (PostgreSQL) menyimpan/mengambil data.

---

## 🔌 3. API Specification (Ringkasan)
Dokumentasi teknis API secara interaktif tersedia melalui **Swagger UI** saat aplikasi backend dijalankan.

### **Endpoint Ruangan (`/api/rooms`)**
| Method | Endpoint | Fungsi |
| :--- | :--- | :--- |
| `GET` | `/api/rooms` | Mendapatkan semua daftar ruangan tersedia. |
| `POST` | `/api/rooms` | Menambahkan data ruangan baru. |

### **Endpoint Peminjaman (`/api/peminjaman`)**
| Method | Endpoint | Fungsi |
| :--- | :--- | :--- |
| `GET` | `/api/peminjaman` | Mengambil seluruh riwayat peminjaman. |
| `POST` | `/api/peminjaman` | Mengirimkan formulir booking ruangan baru. |
| `PUT` | `/api/peminjaman/{id}` | Mengedit data peminjaman yang sudah ada. |
| `DELETE` | `/api/peminjaman/{id}` | Membatalkan/menghapus data peminjaman. |

---

## 💡 4. Refleksi Pengembangan
Proses pengerjaan proyek ini memberikan banyak wawasan teknis baru, di antaranya:

1.  **Stabilitas Asynchronous (Mobile):** Menangani *Async Gaps* di Flutter dengan pengecekan `mounted` sangat penting untuk mencegah crash aplikasi saat navigasi cepat.
2.  **Integrasi Cross-Origin:** Mempelajari konfigurasi CORS di ASP.NET Core adalah kunci agar aplikasi Web dan Mobile dapat berkomunikasi dengan lancar dengan Backend di port yang berbeda.
3.  **Modernisasi Kode:** Menyesuaikan dengan API Flutter terbaru (seperti `.withValues`) menunjukkan pentingnya mengikuti pembaruan framework untuk menjaga performa aplikasi.
4.  **Kedisiplinan Version Control:** Penggunaan GitHub Issues dan Pull Request membantu saya dalam mengelola progres fitur demi fitur secara lebih terukur dan profesional.

---
**Dibuat oleh:** Gusthi Pangestu  
**Versi:** 1.0.0 (Stable Release)  
**Tanggal:** 17 Februari 2026