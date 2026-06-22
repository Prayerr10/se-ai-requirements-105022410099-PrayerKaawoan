# Student Task Management System Case

## Case Description

Student Task Management System adalah aplikasi kampus yang digunakan oleh Lecturer, Student, dan Administrator untuk mengelola tugas perkuliahan, pengumpulan tugas, penilaian, tenggat waktu, dan pelaporan.

Dalam assignment ini, mahasiswa bertindak sebagai Requirements Engineer yang dibantu AI. AI digunakan untuk menghasilkan draft, sedangkan mahasiswa tetap bertanggung jawab atas pemeriksaan, koreksi, dan requirement baseline akhir. Informasi yang tidak berasal dari studi kasus resmi harus ditandai secara eksplisit sebagai `ASSUMPTION`.

## Initial Project Objectives

Tujuan awal yang dapat diturunkan langsung dari deskripsi resmi adalah:

- Mendukung pengelolaan tugas perkuliahan dalam konteks kampus.
- Mendukung Lecturer dalam membuat tugas, menetapkan deadline, serta memberikan nilai dan umpan balik.
- Mendukung Student dalam melihat tugas, mengumpulkan file, serta memantau status dan deadline.
- Mendukung Administrator dalam mengelola pengguna, mata kuliah, dan konfigurasi sistem.
- Memperhatikan usability, security, performance, reliability, dan data integrity selama proses Requirements Engineering.

Tujuan di atas masih bersifat awal. Dokumen ini belum menetapkan functional requirements, non-functional requirements, user stories, acceptance criteria, prioritas, atau rancangan solusi.

## Known Facts from the Assignment

- `FACT`: Nama studi kasus adalah Student Task Management System.
- `FACT`: Sistem digunakan dalam lingkungan kampus.
- `FACT`: Stakeholder yang disebutkan secara langsung adalah Lecturer, Student, dan Administrator.
- `FACT`: Ruang masalah mencakup tugas perkuliahan, pengumpulan tugas, penilaian, deadline, dan pelaporan.
- `FACT`: Lecturer dapat membuat tugas, menetapkan deadline, serta memberikan nilai dan umpan balik.
- `FACT`: Student dapat melihat tugas, mengumpulkan file, serta memantau status dan deadline.
- `FACT`: Administrator dapat mengelola pengguna, mata kuliah, dan konfigurasi sistem.
- `FACT`: Sistem harus memperhatikan usability, security, performance, reliability, dan data integrity.
- `FACT`: Semua informasi yang tidak berasal dari studi kasus harus ditandai sebagai asumsi.

## Available Information Boundaries

Assignment hanya memberikan gambaran tingkat tinggi mengenai konteks, stakeholder, aktivitas utama, dan quality concerns. Informasi berikut belum tersedia:

- Kebijakan akademik atau proses bisnis rinci untuk pembuatan, pengumpulan, dan penilaian tugas.
- Jenis, ukuran, format, dan mekanisme penyimpanan file tugas.
- Aturan keterlambatan, perubahan deadline, percobaan pengumpulan ulang, dan pembatalan tugas.
- Detail alur pemberian nilai, umpan balik, koreksi nilai, dan publikasi nilai.
- Isi, audiens, format, dan periode pelaporan.
- Struktur mata kuliah, kelas, semester, dan hubungan pengguna dengan mata kuliah.
- Target terukur untuk usability, security, performance, reliability, dan data integrity.
- Platform, arsitektur, integrasi, teknologi, anggaran, jadwal proyek, dan batasan operasional.
- Kebutuhan stakeholder sekunder selain Lecturer, Student, dan Administrator.

Daftar tersebut merupakan batas pengetahuan awal, bukan keputusan produk.

## Open Questions

- `OPEN QUESTION`: Proses bisnis saat ini berlangsung seperti apa, dan masalah utama apa yang perlu diselesaikan?
- `OPEN QUESTION`: Siapa yang berwenang membuat, mengubah, menerbitkan, atau membatalkan tugas?
- `OPEN QUESTION`: Aturan apa yang berlaku untuk deadline, keterlambatan, dan pengumpulan ulang?
- `OPEN QUESTION`: File apa yang dapat dikumpulkan, dan batas ukuran atau format apa yang berlaku?
- `OPEN QUESTION`: Bagaimana nilai dan umpan balik dibuat, diubah, dan ditampilkan kepada Student?
- `OPEN QUESTION`: Laporan apa yang dibutuhkan, oleh siapa, dan untuk periode apa?
- `OPEN QUESTION`: Bagaimana Administrator mengelola hubungan antara pengguna, mata kuliah, dan kelas?
- `OPEN QUESTION`: Target terukur apa yang berlaku untuk usability, security, performance, reliability, dan data integrity?
- `OPEN QUESTION`: Apakah terdapat stakeholder lain yang harus dilibatkan atau hanya tiga stakeholder yang disebutkan?
- `OPEN QUESTION`: Apakah terdapat sistem kampus lain yang perlu dipertimbangkan dalam ruang lingkup proyek?
