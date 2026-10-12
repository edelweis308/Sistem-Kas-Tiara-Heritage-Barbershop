# Sistem-Kas-Tiara-Heritage-Barbershop

## 📋 Skema Database (ERD)
Berikut adalah rancangan diagram hubungan entitas (Entity Relationship Diagram) untuk sistem pencatatan kas Tiara Heritage Barbershop:

```mermaid
erDiagram
    PEGAWAI {
        int id_pegawai PK
        varchar nama_pegawai
        varchar jabatan
    }
    
    PELANGGAN {
        int id_pelanggan PK
        varchar nama_pelanggan
        varchar no_hp
    }
    
    JENIS_KAS {
        int id_jenis_kas PK
        varchar nama_jenis
        varchar tipe "Masuk atau Keluar"
    }
    
    TRANSAKSI {
        int id_transaksi PK
        date tanggal
        int id_pegawai FK
        int id_pelanggan FK "nullable"
        int id_jenis_kas FK
        varchar keterangan
        numeric jumlah
    }

    PEGAWAI ||--o{ TRANSAKSI : mencatat
    PELANGGAN ||--o{ TRANSAKSI : terkait
    JENIS_KAS ||--o{ TRANSAKSI : mengelompokkan
---

## 📌 Tentang
Aplikasi pencatatan kas masuk dan keluar **Tiara Heritage Barbershop**. Frontend dibangun menggunakan **HTML, CSS, dan JavaScript**, sedangkan backend dan database didukung oleh **Supabase (PostgreSQL & REST API)**.

**Fitur Utama:**
* **Dashboard Saldo:** Menampilkan ringkasan total kas masuk, kas keluar, dan saldo akhir secara *real-time*.
* **Input Transaksi:** Form pencatatan transaksi kas masuk dan kas keluar dengan validasi data.
* **Riwayat Transaksi:** Tabel data transaksi lengkap dengan fitur pencarian (*search*), filter berdasarkan periode, serta tombol edit dan hapus data.
* **Laporan Periode:** Rekapitulasi laporan keuangan berdasarkan rentang waktu tertentu.
* **Cetak PDF & Ekspor Excel:** Memudahkan pengguna dalam mengunduh atau mencetak laporan keuangan.

---

## 🚀 Teknologi yang Digunakan
* **Frontend:** HTML5, CSS3, JavaScript (Vanilla)
* **Backend / Database:** Supabase (PostgreSQL, REST API)
* **Deployment:** GitHub Pages / Web Hosting Platform

---

## 💻 Panduan Penggunaan
1. Akses tautan website aplikasi melalui link deployment GitHub Pages repository ini.
2. Lakukan login atau navigasikan ke halaman Dashboard untuk melihat ringkasan saldo.
3. Gunakan menu **Input Transaksi** untuk mencatat kas masuk atau kas keluar yang baru.
4. Periksa menu **Riwayat** untuk memfilter, mengubah, atau menghapus data transaksi jika diperlukan.
5. Unduh laporan melalui fitur **Cetak PDF** atau **Ekspor Excel** pada halaman laporan.
