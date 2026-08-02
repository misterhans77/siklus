# Kebijakan Privasi — Aplikasi SIKLUS

**Terakhir diperbarui:** 2 Agustus 2026

## 1. Pendahuluan

Aplikasi SIKLUS ("aplikasi") adalah sistem informasi sekolah dasar yang dikembangkan untuk membantu pengelolaan data kelas, ujian, nilai, dan kelulusan siswa. Aplikasi ini dikembangkan dan dikelola oleh pengelola sekolah/pengguna aplikasi ("Anda", "pengelola") dan digunakan dalam lingkup operasional satuan pendidikan.

Kebijakan Privasi ini menjelaskan bagaimana aplikasi mengumpulkan, menggunakan, menyimpan, dan melindungi data yang diproses melalui aplikasi. Dengan menggunakan aplikasi ini, Anda menyetujui praktik yang dijelaskan dalam kebijakan ini.

## 2. Data yang Diproses

Aplikasi memproses data berikut yang dimasukkan oleh pengelola sekolah:

| Kategori | Data | Sumber |
|---|---|---|
| Data Siswa | Nama, NISN, tempat & tanggal lahir, jenis kelamin, kelas, tahun ajaran, nomor ijazah | Dimasukkan pengelola |
| Data Akademik | Nilai harian/UTS/UAS, prestasi, rekap nilai, status kelulusan, asesmen, absensi, catatan anekdotal, buku penghubung | Dimasukkan pengelola |
| Data Pengguna Admin | Username dan password (dihash dengan SHA-256) | Dibuat pengelola saat login |
| Data Operasional | Pengaturan sekolah, data guru, struktur organisasi, jadwal pelajaran, inventaris | Dimasukkan pengelola |
| Data Unduhan/Dokumen | File upload (mis. file ijazah), dokumen PDF/Excel yang dicetak | Diunggah/dicetak pengelola |

**Aplikasi TIDAK mengumpulkan secara otomatis:** lokasi perangkat, kontak, media penyimpanan, riwayat penelusuran, atau identitas perangkat (IMEI/ID iklan). Aplikasi tidak menampilkan iklan dan tidak menggunakan SDK analitik pihak ketiga untuk pelacakan pengguna.

## 3. Data Anak

Aplikasi memproses data siswa yang merupakan **anak di bawah 13 tahun** dalam konteks pendidikan. Pemrosesan dilakukan **atas dasar kepentingan pendidikan** dan **otorisasi sekolah** selaku pengendali data. Kami tidak menggunakan data anak untuk tujuan pemasaran, periklanan, atau profil iklan.

## 4. Cara Data Digunakan

Data digunakan hanya untuk:
1. Mengelola data siswa, nilai, dan kelulusan dalam lingkup operasional sekolah;
2. Menghitung nilai akhir, merangking, dan menerbitkan dokumen kelulusan (transkrip, SKL, SKHU, rekap nilai);
3. Menampilkan informasi status kelulusan kepada siswa/orang tua melalui fitur **Cek Kelulusan**;
4. Menyediakan fitur AI (Google Gemini) untuk analisis soal dan pembuatan perangkat pembelajaran atas permintaan pengelola.

## 5. Penyimpanan Data

- **Penyimpanan lokal:** Data tersimpan dalam database SQLite di perangkat tempat aplikasi diinstal. Data tidak dikirim ke server cloud yang kami kelola.
- **Backup:** Pengelola dapat membuat backup database secara manual; file backup berada di bawah kendali pengelola.
- **Akses internet via tunnel:** Ketika fitur "Tunnel" diaktifkan, aplikasi membuat URL publik sementara melalui layanan localtunnel.me agar fitur Cek Kelulusan dapat diakses dari luar jaringan lokal. Selama tunnel aktif, data yang diakses (NISN dan status kelulusan) dapat diakses siapa pun yang mengetahui URL tersebut. **Nonaktifkan tunnel atau gunakan Mode Tahan URL jika tidak diperlukan.**

## 6. Layanan Pihak Ketiga

| Layanan | Tujuan | Data yang dikirim |
|---|---|---|
| localtunnel.me | Membuka URL publik untuk fitur Cek Kelulusan | Trafik HTTP ke URL publik (tanpa kredensial admin) |
| Google Gemini API | Analisis soal & pembuatan perangkat pembelajaran (opsional, atas permintaan) | Isi prompt yang dikirim pengelola |
| PostgreSQL E-RaporSD | Sinkronisasi data ke server E-RaporSD sekolah (opsional) | Data siswa & nilai, dikirim ke host yang dikonfigurasi pengelola |

Setiap layanan pihak ketiga memiliki kebijakan privasinya masing-masing.

## 7. Keamanan Data

- Password pengelola disimpan dalam bentuk hash (SHA-256) — tidak pernah plaintext.
- Endpoint login dilindungi pembatasan laju permintaan (rate limiting) untuk mencegah serangan brute-force.
- Endpoint publik (Cek Kelulusan) dibatasi laju permintaan untuk mencegah penarikan data massal.
- Password default wajib diganti sebelum aplikasi digunakan lebih lanjut.
- Komunikasi tunnel menggunakan HTTPS; lalu lintas ke server lokal dalam perangkat menggunakan HTTP localhost.
- File konfigurasi berisi kredensial dienkripsi (AES-256-GCM) di perangkat.

Meskipun kami menerapkan langkah-langkah keamanan di atas, tidak ada metode transmisi atau penyimpanan yang 100% aman.

## 8. Retensi Data

Data disimpan selama diperlukan untuk tujuan operasional sekolah. Penghapusan data dilakukan oleh pengelola melalui fitur manajemen data di aplikasi, atau dengan menghapus database dari perangkat.

## 9. Hak Anda

Sesuai peraturan perlindungan data yang berlaku (termasuk UU PDP No. 27 Tahun 2022 dan, jika berlaku, GDPR untuk pengguna di Uni Eropa), Anda berhak untuk:
- Mengakses dan meminta salinan data;
- Memperbaiki data yang tidak akurat;
- Meminta penghapusan data;
- Membatasi atau menolak pemrosesan tertentu.

Untuk menggunakan hak-hak ini, hubungi pengelola sekolah atau tim pengembangan aplikasi.

## 10. Kontak

Pertanyaan tentang Kebijakan Privasi ini dapat diajukan kepada pengelola sekolah yang menggunakan aplikasi, atau kepada tim pengembangan aplikasi melalui alamat email yang tercantum pada halaman listing aplikasi di Google Play.

## 11. Perubahan Kebijakan

Kebijakan Privasi ini dapat diperbarui sewaktu-waktu. Perubahan akan diumumkan melalui halaman aplikasi di Google Play. Tanggal pembaruan terakhir tercantum di bagian atas dokumen ini.
