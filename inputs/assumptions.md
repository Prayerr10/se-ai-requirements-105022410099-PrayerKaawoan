# Facts, Assumptions, Constraints, and Open Questions

## FACT

- `FACT-01`: Nama studi kasus adalah Student Task Management System.
- `FACT-02`: Sistem digunakan dalam konteks kampus.
- `FACT-03`: Stakeholder yang disebutkan secara langsung adalah Lecturer, Student, dan Administrator.
- `FACT-04`: Sistem berkaitan dengan tugas perkuliahan, pengumpulan tugas, penilaian, deadline, dan pelaporan.
- `FACT-05`: Lecturer dapat membuat tugas, menetapkan deadline, serta memberikan nilai dan umpan balik.
- `FACT-06`: Student dapat melihat tugas, mengumpulkan file, serta memantau status dan deadline.
- `FACT-07`: Administrator dapat mengelola pengguna, mata kuliah, dan konfigurasi sistem.
- `FACT-08`: Sistem harus memperhatikan usability, security, performance, reliability, dan data integrity.
- `FACT-09`: Mahasiswa berperan sebagai Requirements Engineer yang dibantu AI dan bertanggung jawab atas baseline akhir.
- `FACT-10`: Informasi yang tidak berasal dari studi kasus harus ditandai sebagai asumsi.

## ASSUMPTION

- `ASSUMPTION-01`: Lecturer menginginkan proses pengelolaan tugas dan penilaian yang tidak menambah beban administrasi secara tidak perlu.
- `ASSUMPTION-02`: Lecturer memerlukan informasi pengumpulan yang terorganisasi untuk membantu pemeriksaan tugas.
- `ASSUMPTION-03`: Student menginginkan informasi tugas dan deadline yang mudah dipahami.
- `ASSUMPTION-04`: Student menginginkan kepastian bahwa file yang dikumpulkan telah tercatat.
- `ASSUMPTION-05`: Administrator menginginkan pengelolaan data pengguna, mata kuliah, dan konfigurasi yang terkendali.
- `ASSUMPTION-06`: Belum ada kesepakatan mengenai aturan perubahan deadline, keterlambatan, pengumpulan ulang, koreksi nilai, atau publikasi nilai.
- `ASSUMPTION-07`: Belum ada keputusan mengenai platform, teknologi, integrasi, anggaran, atau jadwal proyek.
- `ASSUMPTION-08`: Belum ada target terukur untuk usability, security, performance, reliability, dan data integrity.

Semua asumsi harus dikonfirmasi melalui elicitation sebelum digunakan sebagai dasar spesifikasi.

## CONSTRAINT

- `CONSTRAINT-01`: Analisis awal harus menggunakan studi kasus resmi Student Task Management System dari assignment.
- `CONSTRAINT-02`: Informasi tambahan yang tidak diberikan assignment tidak boleh diperlakukan sebagai fakta.
- `CONSTRAINT-03`: Setiap informasi tambahan harus diberi label `ASSUMPTION` sampai dikonfirmasi.
- `CONSTRAINT-04`: Istilah stakeholder harus konsisten menggunakan Lecturer, Student, dan Administrator.
- `CONSTRAINT-05`: Informasi awal hanya tersedia pada tingkat tinggi; assignment tidak menyediakan kebijakan bisnis, ukuran kualitas, teknologi, jadwal, atau anggaran rinci.
- `CONSTRAINT-06`: AI hanya menghasilkan draft; mahasiswa bertanggung jawab atas pemeriksaan, koreksi, dan baseline akhir.

## OPEN QUESTION

- `OPEN-01`: Apa masalah utama pada proses pengelolaan tugas saat ini?
- `OPEN-02`: Apa aturan pembuatan, perubahan, penerbitan, dan pembatalan tugas?
- `OPEN-03`: Apa aturan deadline, keterlambatan, dan pengumpulan ulang?
- `OPEN-04`: Format dan ukuran file apa yang dapat dikumpulkan?
- `OPEN-05`: Bagaimana nilai dan umpan balik dibuat, dikoreksi, dipublikasikan, dan dilihat?
- `OPEN-06`: Laporan apa yang diperlukan, oleh siapa, dan untuk periode apa?
- `OPEN-07`: Bagaimana hubungan pengguna, mata kuliah, kelas, dan semester dikelola?
- `OPEN-08`: Konfigurasi apa yang dapat dikelola oleh Administrator?
- `OPEN-09`: Apa target terukur untuk usability, security, performance, reliability, dan data integrity?
- `OPEN-10`: Apakah terdapat stakeholder lain yang harus dilibatkan?
- `OPEN-11`: Apakah ada sistem kampus lain yang perlu dipertimbangkan?
- `OPEN-12`: Apa batasan jadwal, anggaran, platform, dan operasional proyek?
