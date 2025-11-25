---
# Front Matter untuk Jekyll. Ini memberitahu Jekyll untuk menggunakan layout tema.
layout: default
---

<!-- 
    KODE DI BAWAH INI ADALAH KONTEN LENGKAP ANDA YANG TELAH DISESUAIKAN
    UNTUK BEKERJA DI DALAM TEMA JEKYLL.
-->

<!-- 1. Impor Font Awesome & CSS Kustom Anda -->
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.2/css/all.min.css">
<style>
    /* --- STYLING GLOBAL & PALET WARNA --- */
    :root {
        --primary-color: #007bff;
        --primary-dark: #0056b3;
        --secondary-color: #6c757d;
        --secondary-dark: #5a6268;
        --success-color: #28a745;
        --danger-color: #dc3545;
        --warning-color: #ffc107;
        --info-color: #17a2b8;
        
        --background-color: #f8f9fa;
        --surface-color: #ffffff;
        --text-color: #343a40;
        --muted-text-color: #6c757d;
        --border-color: #dee2e6;
        
        --box-shadow: 0 8px 30px rgba(0,0,0,0.08);
        --border-radius: 12px;
        --border-radius-sm: 8px;
    }

    /* Override beberapa gaya tema 'minimal' agar tidak bentrok */
    .main-content {
        padding: 1rem; /* Atur padding agar container custom kita pas */
    }
    
    /* --- CONTAINER & HEADER KUSTOM ANDA --- */
    .container {
        max-width: 800px;
        margin: 0 auto; /* Margin atas bawah 0, karena tema sudah memberi ruang */
        padding: 1rem 2rem 2rem 2rem;
        background: var(--surface-color);
        border-radius: var(--border-radius);
        box-shadow: var(--box-shadow);
    }
    .header {
        text-align: center;
        padding-bottom: 2rem;
        border-bottom: 1px solid var(--border-color);
    }
    .app-logo {
        width: 50%;
        max-width: 100px;
        height: auto;
        margin-bottom: 1rem;
        border-radius: 15%;
    }
    /* Menggunakan !important untuk memastikan gaya Anda yang menang atas tema */
    .container h1 { 
        font-size: 2.8rem !important;
        color: #212529 !important;
        margin: 0 !important;
        font-weight: 700 !important;
        border: none !important;
        padding: 0 !important;
    }
    .tagline {
        font-size: 1.25rem;
        color: var(--muted-text-color);
        margin-top: 0.5rem;
    }

    /* --- STYLING TOMBOL UNDUH --- */
    .main-buttons-container { display: flex; flex-direction: column; gap: 1rem; margin: 2rem auto; }
    .button-group { display: flex; flex-direction: column; gap: 0.75rem; align-items: center; }
    .download-button { display: flex; align-items: center; justify-content: center; gap: 12px; width: 95%; max-width: 450px; padding: 1rem; color: #fff; text-align: center; text-decoration: none; font-size: 1.15rem; font-weight: bold; border-radius: 10px; transition: background-color 0.3s, transform 0.2s; box-shadow: 0 4px 15px rgba(0,0,0,0.1); }
    .download-button:hover { transform: translateY(-3px); }
    .download-button.primary { background-color: var(--primary-color); }
    .download-button.primary:hover { background-color: var(--primary-dark); }
    .download-button.secondary { background-color: var(--secondary-color); }
    .download-button.secondary:hover { background-color: var(--secondary-dark); }
    .download-button.danger { background-color: var(--danger-color); }
    .download-button.danger:hover { background-color: #c82333; }
    .download-button.info { background-color: var(--info-color); }
    .download-button.info:hover { background-color: #138496; }
    .download-button .fas { font-size: 1.3rem; }
    .group-title { text-align: center; font-size: 1.5rem; font-weight: 600; color: var(--text-color); margin: 1rem 0 0.5rem 0; }
    .group-subtitle { text-align: center; margin-top: 0; margin-bottom: 1rem; color: var(--muted-text-color); }

    /* --- STYLING KONTEN & SECTION --- */
    .section { margin-top: 3rem; padding-top: 2rem; border-top: 1px solid var(--border-color); }
    .container h2 { text-align: center; color: var(--text-color); margin-bottom: 2rem; font-size: 2rem; font-weight: 600; }
    .container h3 { color: #495057; margin-top: 2.5rem; margin-bottom: 1rem; border-bottom: 2px solid var(--primary-color); padding-bottom: 0.5rem; display: inline-block; }
    .container h3 > .fas { margin-right: 0.75rem; }
    .info-box { background: #e9f5ff; border-left: 5px solid var(--primary-color); padding: 1rem 1.5rem; margin: 1.5rem 0; border-radius: var(--border-radius-sm); }
    .info-box h4 { margin-top: 0; }
    .video-container { position: relative; overflow: hidden; width: 100%; padding-top: 56.25%; margin: 1.5rem 0; border-radius: var(--border-radius); box-shadow: 0 6px 20px rgba(0,0,0,0.1); }
    .video-container iframe { position: absolute; top: 0; left: 0; width: 100%; height: 100%; }
    details { background-color: var(--surface-color); border: 1px solid var(--border-color); border-radius: var(--border-radius); padding: 1.25rem; margin-top: 1rem; transition: box-shadow 0.3s; }
    details[open] { box-shadow: 0 4px 15px rgba(0,0,0,0.05); }
    summary { font-weight: bold; cursor: pointer; color: var(--primary-color); font-size: 1.1rem; list-style: none; position: relative; padding-right: 25px; }
    summary::-webkit-details-marker { display: none; }
    summary::after { content: '\f078'; font-family: 'Font Awesome 6 Free'; font-weight: 900; position: absolute; right: 0; top: 2px; transition: transform 0.2s; }
    details[open] summary::after { transform: rotate(180deg); }
    .footer { text-align: center; margin-top: 4rem; padding: 2rem 0 0 0; color: var(--muted-text-color); font-size: 0.9rem; }

    /* --- Gaya untuk Bagian Peringatan --- */
    .warning-item { background-color: #fff; border: 1px solid #ddd; border-left: 5px solid var(--danger-color); border-radius: var(--border-radius-sm); padding: 15px 20px; margin-top: 1.5rem; box-shadow: 0 2px 4px rgba(0,0,0,0.05); }
    .warning-title { font-weight: bold; color: #bf360c; display: block; margin-bottom: 8px; font-size: 1.1em; }
    .reason-tag { font-weight: 600; color: #555; }
    .solution-tag { font-weight: 600; color: var(--success-color); }
    .warning-item code { background-color: #fce4ec; color: #c2185b; padding: 2px 6px; border-radius: 4px; font-family: "Courier New", Courier, monospace; }
    
    /* --- Gaya untuk Fitur Grid --- */
    .feature-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: 1.5rem; }
    .feature-item { background: var(--background-color); padding: 1.5rem; border-radius: var(--border-radius-sm); border: 1px solid var(--border-color); }
    .feature-item .fas { font-size: 2rem; color: var(--primary-color); margin-bottom: 1rem; display: block; }
    .feature-item h4 { margin-top: 0; font-size: 1.2rem; }
    
    /* --- Utility & Lainnya --- */
    ol, ul { padding-left: 20px; }
    code { background-color: #e9ecef; padding: 2px 5px; border-radius: 4px; font-family: monospace; }
</style>

<!-- 2. Konten Utama Anda (sebelumnya di dalam <body>) -->
<div class="container">
    <header class="header">
        <img src="https://raw.githubusercontent.com/abettashop-gif/scan_class/main/logo-web.png" alt="Logo Scan Class" class="app-logo">
        <h1>Scan Class</h1>
        <p class="tagline">Solusi Absensi Digital Cerdas untuk Guru</p>
    </header>

    <section class="main-buttons-container">
        <div class="button-group">
            <h2 class="group-title">Unduh Aplikasi</h2>
            <p class="group-subtitle">Pilih versi aplikasi yang sesuai untuk Anda.</p>
            <a href="https://www.mediafire.com/file/1j7r19ufegurjh7/Scan_Class_V2_3.apk/file" class="download-button primary">
                <i class="fas fa-chalkboard-teacher"></i> Unduh Aplikasi Guru (V.2_3) #UpdateKeamanan
            </a>
            <details style="width: 95%; max-width: 450px; margin: 0.5rem auto; border-color: var(--warning-color); background-color: #fff9e6;">
                <summary style="color: #856404; font-weight: bold;">
                    <i class="fas fa-exclamation-triangle"></i> WAJIB BACA: Panduan Update Pengguna Lama
                </summary>
                <div style="padding-top: 1rem; border-top: 1px solid #ffeeba; margin-top: 0.5rem;">
                    <p style="font-size: 0.9rem; text-align: center; background-color: #e9f5ff; padding: 8px; border-radius: 6px;">
                        <strong>Info:</strong> Jika Anda pengguna baru, Anda bisa mengabaikan bagian ini.
                    </p>
                    <h4 style="margin-top: 1rem; margin-bottom: 0.5rem; color: #333;">Pembaruan Penting Telah Tiba!</h4>
                    <p>Untuk meningkatkan keamanan akun, versi baru ini menggunakan sistem login yang sepenuhnya berbeda. Akun lama Anda tidak bisa langsung digunakan.</p>
                    <h4 style="margin-top: 1.5rem; margin-bottom: 0.5rem; color: #333;">Langkah yang HARUS Dilakukan:</h4>
                    <ol style="padding-left: 20px; font-size: 0.95rem;">
                        <li>
                            <strong>(Opsional) Cadangkan Data Penting:</strong> Sebelum update, buka aplikasi lama, masuk ke menu "Rekap Absensi", lalu <strong>Ekspor ke PDF/Excel</strong> sebagai cadangan.
                        </li>
                        <li>
                            <strong>Lakukan Update:</strong> Instal aplikasi versi baru ini. Jangan uninstall versi lama.
                        </li>
                        <li style="font-weight: bold; color: var(--danger-color);">
                            <strong>Lakukan REGISTRASI ULANG (Wajib):</strong> Setelah update, buka aplikasi dan pilih menu <strong>"Daftar"</strong>. Anda BISA menggunakan kembali Email dan Password yang sama persis seperti sebelumnya.
                        </li>
                        <li>
                            <strong>Login dengan Akun Baru:</strong> Setelah registrasi ulang berhasil, silakan login.
                        </li>
                    </ol>
                    <p style="margin-top: 1rem;">Langkah ini hanya perlu dilakukan <strong>satu kali</strong>. Terima kasih atas pengertian Anda!</p>
                </div>
            </details>
            <a href="https://www.mediafire.com/file/e52a1c144rwpuup/app-release.apk/file" class="download-button primary">
                <i class="fas fa-chalkboard-teacher"></i> Unduh Aplikasi Guru (V.2_2) #update
            </a>
            <a href="https://drive.google.com/file/d/1p_ONtqnWb0HyW1B0jMk5K5A-lVgcaKNt/view?usp=sharing" class="download-button secondary">
                <i class="fas fa-history"></i> Unduh Aplikasi Guru (V.1 Lama)
            </a>
             <a href="https://www.mediafire.com/file/ohym5l4jgeocvws/fix_izin_siswa_0.2.apk/file" class="download-button" style="background-color: var(--success-color);">
                <i class="fas fa-user-graduate"></i> Aplikasi Siswa/Orang Tua
            </a>
        </div>
        
        <div class="button-group">
            <h2 class="group-title">Unduh File Pendukung</h2>
            <p class="group-subtitle">Gunakan file-file ini untuk fitur impor dan sinkronisasi.</p>
            <a href="https://drive.google.com/file/d/1eu-5L-mogqYmrzVdhNc8-aba8KDBXIWx/view?usp=sharing" class="download-button info">
                <i class="fas fa-file-csv"></i> Unduh Contoh File Import Siswa
            </a>
            <a href="https://docs.google.com/document/d/1kLX30K9OiZs2bmLGp5dR6zEA8XaBhG30/edit?usp=sharing&ouid=118214817902322932165&rtpof=true&sd=true" class="download-button danger">
                <i class="fab fa-google-drive"></i> Unduh Kode AppScript Sinkronisasi
            </a>
            <a href="https://docs.google.com/document/d/1ZQ-EedlKnkjC16PP7q9YUwNuaGH6VgNl/edit?usp=sharing&ouid=118214817902322932165&rtpof=true&sd=true" class="download-button danger">
                <i class="fab fa-google-drive"></i> Unduh Kode AppScript Data Izin
            </a>
        </div>
    </section>

    <section class="section">
        <h2>🚀 Panduan Lengkap untuk Pengguna Baru</h2>
        <div class="info-box">
            <h4>Selamat Datang di Scan Class!</h4>
            <p>Ikuti panduan ini dari awal hingga akhir untuk menyiapkan dan mengaktifkan aplikasi Anda.</p>
        </div>

        <h3 style="margin-top: 2rem;"><i class="fas fa-user-plus"></i> Tahap 1: Pendaftaran & Penyiapan Dasar</h3>
        <ol>
            <li>
                <strong>Daftar Akun & Pilih Peran</strong><br>
                Buka aplikasi Guru, pilih "Daftar Akun Baru". Anda akan diminta memilih peran:
                <ul>
                    <li><strong>Wali Kelas:</strong> Jika Anda mengelola satu kelas secara penuh.</li>
                    <li><strong>Guru Mapel:</strong> Jika Anda mengajar di beberapa kelas.</li>
                </ul>
                Lengkapi semua data, lalu selesaikan pendaftaran.
            </li>
            <li>
                <strong>Login & Buat Kelas Pertama Anda</strong><br>
                Setelah berhasil mendaftar, <strong>Login</strong>. Masuk ke menu "Manajemen Kelas", lalu tekan tombol <code>+</code> untuk membuat kelas baru (contoh: "10-A").
            </li>
            <li>
                <strong>Input Data Siswa</strong><br>
                Masuk ke kelas yang baru Anda buat, lalu pilih "Manajemen Siswa". Di sini Anda bisa menambah data siswa secara manual atau menggunakan fitur <strong>"Impor CSV"</strong>. <em>(Template CSV bisa diunduh di bagian atas halaman ini).</em>
            </li>
            <li>
                <strong>Siap untuk Absensi Offline</strong><br>
                Pada titik ini, Anda sudah bisa mulai melakukan absensi harian dan melihat rekapitulasi data secara offline di dalam aplikasi.
            </li>
        </ol>

        <h3 style="margin-top: 3rem;"><i class="fas fa-cloud"></i> Tahap 2: Menyiapkan Fitur Online </h3>
        <div class="info-box" style="border-color: var(--info-color); background-color: #e2f8fb;">
            <h4><i class="fas fa-info-circle"></i> Info: Langkah ini opsional.</h4>
            <p>Lakukan langkah ini hanya jika Anda adalah <strong>Wali Kelas</strong> dan ingin menggunakan fitur <strong>Sinkronisasi ke Google Sheets</strong> dan <strong>Integrasi Izin Online</strong> dari Aplikasi Siswa.</p>
        </div>
        <ol start="5">
            <li>
                <strong>Buka Menu Managemen Kelas</strong><br>
                Anda akan melihat kolom untuk memasukkan URL. Di sini, Anda perlu mengatur dua hal:
                <ul>
                    <li><strong>Untuk Sinkronisasi Google Sheets:</strong> Jika Anda ingin sinkronisasi, tempel (paste) URL Google Sheet Anda di sini.</li>
                    <li><strong>Untuk Integrasi Izin Online:</strong> Masukkan <strong>nama kelas Anda persis sama</strong> (contoh: <code>10-A</code>). Ini akan menjadi "kunci" bagi aplikasi untuk mengambil data izin dari server dan menghubungkan Aplikasi guru ke Aplikasi siswa.(Guru Mapel tidak perlu memasukan / membuat URL data izin)</li>
                </ul>
                Pastikan Anda memasukkan data yang benar, lalu tekan "Simpan".
            </li>
            <li>
                <strong>✅ Selesai! Fitur Online Siap Digunakan</strong><br>
                Sekarang, aplikasi Anda telah terhubung dengan layanan online. Data izin akan otomatis masuk dan Anda bisa mulai melakukan sinkronisasi rekap ke Google Sheet.
            </li>
            <li>
                <strong>Panduan Lengkap Membuat Google Sheet ada pada Video Tutorial</strong><br>
            </li>
        </ol>

        <h3 style="margin-top: 3rem;"><i class="fas fa-key"></i> Tahap 3: Masa Percobaan & Aktivasi</h3>
        <div class="info-box" style="border-color: var(--warning-color); background-color: #fff3cd;">
            <h4>Masa Percobaan (Trial) 14 Hari</h4>
            <p>Saat pertama kali mendaftar, akun Anda otomatis mendapatkan <strong>akses penuh ke semua fitur premium selama 14 hari</strong>, termasuk Ekspor ke Excel dan fitur-fitur online.</p>
        </div>
        <ol start="8">
            <li>
                <strong>Saat Masa Percobaan Berakhir</strong><br>
                Setelah 14 hari, fitur-fitur premium akan terkunci. Anda akan melihat notifikasi bahwa aplikasi memerlukan aktivasi.
            </li>
            <li>
                <strong>Proses Aktivasi</strong><br>
                Di dalam aplikasi, pilih <strong>"Minta Kunci Aktivasi"</strong>. Lengkapi formulir permintaan, kirim ke developer, lalu masukkan Kunci Aktivasi yang Anda terima untuk membuka kembali semua fitur premium.
            </li>
        </ol>
    </section>

    <section class="section">
        <h2>👋 Panduan untuk Pengguna Lama (Update ke V.2)</h2>
        <div class="info-box">
            <h4>Terima Kasih Telah Setia Menggunakan Scan Class!</h4>
            <p>Versi 2 membawa banyak pembaruan signifikan. Mohon ikuti panduan ini dengan saksama untuk memastikan semua fitur baru berjalan lancar.</p>
        </div>

        <h3 style="margin-top: 2rem;"><i class="fas fa-sync-alt"></i> Langkah 1: Cara Memperbarui Aplikasi</h3>
        <ol>
            <li><strong>Unduh Versi Terbaru:</strong> Gunakan tombol <strong>"Unduh Aplikasi Guru (V.2)"</strong> di bagian atas halaman ini untuk mendapatkan file APK terbaru.</li>
            <li><strong>Instal Pembaruan:</strong> Buka file APK yang sudah diunduh. Android akan secara otomatis mendeteksi bahwa ini adalah pembaruan. Lanjutkan instalasi. <strong>Jangan uninstall aplikasi lama Anda.</strong></li>
            <li><strong>✅ Selesai!</strong> Data lama Anda (kelas, siswa, absensi, dan status aktivasi) akan tetap aman setelah pembaruan.</li>
        </ol>

        <h3 style="margin-top: 3rem;"><i class="fas fa-cogs"></i> Langkah 2: Setup Wajib untuk Fitur Online (Wali Kelas)</h3>
        <div class="info-box" style="border-color: var(--warning-color); background-color: #fff3cd;">
            <h4><i class="fas fa-exclamation-triangle"></i> AKTIFKAN SINKRONISASI REKAP & IZIN ONLINE!</h4>
            <p>Versi 2 menyatukan fitur <strong>Sinkronisasi Rekap Online</strong> dan <strong>Integrasi Izin Online</strong>. Untuk mengaktifkan kedua fitur ini, Anda **wajib** membuat Google Sheet baru dan mendaftarkan URL-nya.</p>
            <ol style="padding-left: 20px; margin-top: 1rem;">
                <li>
                    <strong>Fungsi Sinkronisasi masih sama seperti versi sebelumnya </strong><br>
                    Panduan dapat dilihat di video tutorial.
                </li>
                <li>
                    <strong>New Fitur Izin Siswa:</strong><br>
                    Fungsi ini memungkinkan untuk menghubungkan antara Guru dan Orang tua siswa. Kode Sekolah/ Guru yang diberikan ke Orang tua adalah Username dengan format huru kecil.
                </li>
                <li>
                    <strong>Masukkan URL di Aplikasi:</strong><br>
                    Buka aplikasi Scan Class, masuk ke menu <strong>Manajemen Kelas dan Sinkronisasi</strong>, masukan URL Script Google Sheet<strong>.</strong>
                </li>
                <li>
                    <strong>Tempel & Simpan:</strong><br>
                    Tempel (paste) URL Google Sheet yang sudah Anda salin ke dalam kolom yang tersedia, lalu tekan "Simpan". Panduan Lengkap lihat pada video tutorial.
                </li>
            </ol>
            <p style="margin-top: 1rem;">
                Langkah ini memberitahu aplikasi ke mana harus <strong>mengirim data rekap</strong> dan dari mana harus <strong>mengambil data izin siswa</strong>. Tanpa URL ini, kedua fitur online tersebut tidak akan berfungsi.
            </p>
            <p><strong>PENTING:</strong> Pengguna dengan peran <strong>Guru Mapel tidak perlu melakukan langkap fitur Izin Siswa </strong> karena sistem izin hanya akan diterima wali kelas.</p>
        </div>

        <h3 style="margin-top: 3rem;"><i class="fas fa-info-circle"></i> Langkah 3: Memahami Perubahan Lainnya</h3>
         <div class="info-box" style="border-color: var(--success-color); background-color: #eaf6ec;">
            <h4>Fitur Baru: Dukungan Peran Ganda (Wali Kelas & Guru Mapel)</h4>
            <p>Secara default, akun lama Anda akan terdeteksi sebagai <strong>Wali Kelas</strong>. Kini ada peran baru <strong>Guru Mapel</strong> yang dapat mengelola beberapa kelas dan memilihnya dari menu dropdown di layar Rekap dan Sinkronisasi.</p>
        </div>

        <h3 style="margin-top: 3rem;"><i class="fas fa-question-circle"></i> Pertanyaan Umum (FAQ)</h3>
        <details>
            <summary>Apakah saya perlu daftar ulang setelah update?</summary>
            <div style="padding-top: 1rem;">
                <p><strong>Tidak perlu.</strong> Anda bisa langsung login menggunakan akun lama Anda. Semua data Anda akan tetap tersedia.</p>
            </div>
        </details>
        <details>
            <summary>Apakah Kunci Aktivasi lama saya masih berlaku?</summary>
            <div style="padding-top: 1rem;">
                <p><strong>Ya, tentu saja.</strong> Kunci aktivasi Anda terikat dengan perangkat (HP) Anda. Selama Anda tidak mengganti perangkat, kunci aktivasi lama akan tetap valid setelah Anda memperbarui aplikasi.</p>
            </div>
        </details>
    </section>

    <section class="section">
        <h2>🌟 Ekosistem Absensi Digital Lengkap</h2>
        <p>Scan Class dirancang dengan fitur-fitur canggih yang saling terintegrasi, memberikan solusi absensi yang fleksibel dan efisien untuk setiap kebutuhan guru.</p>

        <div class="feature-grid">
            <div class="feature-item">
                <i class="fas fa-user-friends"></i>
                <h4>Dukungan Peran Ganda</h4>
                <p>Mendaftar sebagai <strong>Wali Kelas</strong> untuk manajemen terpusat, atau sebagai <strong>Guru Mapel</strong> untuk fleksibilitas mengajar di banyak kelas dalam satu akun.</p>
            </div>
            <div class="feature-item">
                <i class="fas fa-file-import"></i>
                <h4>Manajemen Siswa Cepat</h4>
                <p>Tambah data siswa secara manual, atau percepat proses dengan fitur <strong>Impor & Ekspor</strong> data siswa menggunakan file template CSV.</p>
            </div>
            <div class="feature-item">
                <i class="fas fa-bell"></i>
                <h4>Notifikasi Absensi</h4>
                <p>Dengan mengaktifkan fitur online dan menghimbau orang tua siswa untuk menginstal Aplikasi Izin Siswa <strong>memberikan layanan pemantauan kehadiran (Notifikasi absensi real time)pada HP Orang tua siswa</strong>.</p>
            </div>
            <div class="feature-item">
                <i class="fas fa-chart-line"></i>
                <h4>Analisis Rekap Detail</h4>
                <p>Tinjau data kehadiran siswa dalam tiga mode berbeda: <strong>Harian</strong> untuk edit status, <strong>Mingguan</strong>, dan <strong>Bulanan</strong> untuk melihat statistik lengkap.</p>
            </div>
            <div class="feature-item">
                <i class="fas fa-file-excel"></i>
                <h4>Ekspor Profesional</h4>
                <p>Buat laporan matriks absensi dalam format Excel (<code>.xlsx</code>) yang siap cetak untuk periode Harian, Mingguan, Bulanan, hingga satu Semester penuh.</p>
                <p>Buat laporan rekap data izin dapat diambil di google sheet (<code>.xlsx</code>).</p>
            </div>
        </div>

        <div class="info-box" style="margin-top: 3rem; border-color: var(--success-color); background-color: #eaf6ec;">
            <h3 style="margin-top: 0; color: #155724;"><i class="fas fa-cloud-upload-alt"></i> Integrasi Penuh dengan Aplikasi Siswa</h3>
            <p>Kami menyediakan <strong>Aplikasi Izin Siswa</strong> terpisah yang dirancang untuk siswa/orang tua dan terhubung langsung dengan Aplikasi Guru.</p>
            <ul style="margin-top: 1rem;">
                <li><strong>Pengajuan Izin Digital:</strong> Siswa dapat mengajukan izin (Sakit/Izin) lengkap dengan tanggal dan keterangan melalui form online.</li>
                <li><strong>Unggah Bukti:</strong> Memungkinkan siswa untuk melampirkan foto bukti, seperti surat keterangan dokter, langsung dari ponsel.</li>
                <li><strong>Data Izin Otomatis Masuk:</strong> Setiap pengajuan izin yang disetujui akan secara <strong>otomatis muncul</strong> di rekap absensi harian dan statistik di Aplikasi Guru.</li>
                <li><strong>Rekapitulasi Izin Online:</strong> Guru dapat melihat daftar lengkap semua pengajuan izin yang masuk dari siswa dalam satu layar khusus untuk verifikasi dan rekapitulasi.</li>
            </ul>
            <p>Integrasi ini menciptakan alur administrasi yang transparan, efisien, dan mengurangi beban kerja guru secara signifikan.</p>
        </div>

        <div class="info-box" style="margin-top: 2rem; border-color: var(--info-color); background-color: #e2f8fb;">
            <h3 style="margin-top: 0; color: #0c5460;"><i class="fas fa-sync-alt"></i> Sinkronisasi Online dan Rekap izin ke Google Sheets</h3>
            <p>Hubungkan aplikasi dengan Google Sheet untuk membuat laporan online yang dapat diakses dari mana saja. Fitur ini dirancang untuk akun <strong>Wali Kelas</strong>.</p>
        </div>

        <h2 style="margin-top: 3rem;">🎬 Video Tutorial</h2>
        <p style="text-align:center;">Pelajari cara Membuat Master Data Siswa untuk import di Scan Class (CSV).</p>
        <ul><li><strong>Format Csv  </strong> menggunakan NISN,NAMA,JENISKELAMIN.</li></ul>
        <div class="video-container">
            <iframe src="https://www.youtube.com/embed/-pwUjCfONNY?si=3B4VkHgd6FEBVDhM" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
        </div>
        <p style="text-align:center;">Pelajari cara Menghubungkan Scan Class ke google sheet melalui Apps Scrip Code.</p>
        <ul><li><strong>ini juga berlaku untuk Data izin. Code Apps Scrip tersedia menu Download </strong></ul>
        <div class="video-container">
            <iframe src="https://www.youtube.com/embed/ibsJVs8RtoI?si=PcH-vFcsDysDyU7y" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
        </div>
        <p style="text-align:center;">Format hearder googlespreadsheets Data Izin untuk.</p>
        <a href="https://ibb.co.com/rG5vVNg"><img src="https://i.ibb.co/SXVJzG2/Whats-App-Image-2025-11-23-at-10-57-59.jpg" alt="Contoh Header Google Sheet untuk Data Izin" border="0" style="max-width:100%; height:auto; border-radius: 8px; margin-top: 1rem;"></a>
        <a href="https://ibb.co.com/TBb1X71"><img src="https://i.ibb.co/PZ9MpPM/Whats-App-Image-2025-11-23-at-10-57-36.jpg" alt="Contoh Header Google Sheet Lainnya" border="0" style="max-width:100%; height:auto; border-radius: 8px; margin-top: 1rem;"></a>
    </section>

    <section class="section">
        <h2>Informasi Penting</h2>
        <details open>
            <summary>⚠️ Peringatan & Praktik Terbaik (Wajib Baca)</summary>
            <div style="padding-top: 1rem;">
                <p>Untuk memastikan data Anda aman dan aplikasi berjalan lancar, mohon perhatikan poin-poin berikut. Mengabaikan peringatan ini dapat menyebabkan <strong>kehilangan data permanen.</strong></p>
                <div class="warning-item">
                    <strong class="warning-title">1. JANGAN Uninstall Aplikasi Sebelum Mengekspor Rekap</strong>
                    <p><span class="reason-tag">Mengapa?</span> Sebagian besar data absensi dan siswa disimpan secara <strong>lokal</strong> di perangkat. Jika Anda menghapus aplikasi, semua data tersebut akan <strong>HILANG SELAMANYA</strong>.</p>
                    <p><span class="solution-tag">Solusi:</span> Sebelum mengganti perangkat, buka menu <code>Rekap Absensi</code>, pilih rentang waktu, lalu gunakan fitur <code>Ekspor ke PDF/Excel</code>. Simpan file hasil ekspor ke tempat aman.</p>
                </div>
                <div class="warning-item">
                    <strong class="warning-title">2. JANGAN "Hapus Data" (Clear Data) dari Pengaturan Android</strong>
                    <p><span class="reason-tag">Mengapa?</span> Aksi ini memiliki efek yang <strong>SAMA PERSIS</strong> dengan uninstall aplikasi. Semua data lokal akan terhapus.</p>
                    <p><span class="solution-tag">Solusi:</span> Jika aplikasi lambat, coba "Hapus Cache" (Clear Cache) dulu. Jika masih bermasalah, ekspor data Anda sebelum mencoba langkah ini.</p>
                </div>
                <div class="warning-item">
                    <strong class="warning-title">3. PASTIKAN Sinkronisasi Berhasil Setelah Membuat Perubahan Offline</strong>
                    <p><span class="reason-tag">Mengapa?</span> Data baru seperti kelas atau siswa yang ditambahkan saat offline hanya ada di perangkat Anda. Jika Anda berganti perangkat sebelum sinkronisasi, data tersebut tidak ikut pindah.</p>
                    <p><span class="solution-tag">Solusi:</span> Setelah membuat perubahan penting, pastikan terhubung ke internet yang stabil dan biarkan aplikasi berjalan sejenak untuk sinkronisasi.</p>
                </div>
                <div class="warning-item">
                    <strong class="warning-title">4. UNTUK Wali Kelas: Pastikan Peran Akun Anda Benar</strong>
                    <p><span class="reason-tag">Mengapa?</span> Hanya peran <code>Wali Kelas</code> yang dapat menambah/mengedit siswa, mengelola kelas, dan memproses surat izin. Jika Anda mendaftar sebagai "Guru Mapel", Anda tidak akan bisa mengakses fitur-fitur tersebut.</p>
                    <p><span class="solution-tag">Solusi:</span> Saat mendaftar, pastikan Anda memilih peran yang benar. Jika terlanjur salah, hubungi admin atau buat akun baru.</p>
                </div>
            </div>
        </details>

        <details>
            <summary>Kebijakan Privasi (Privacy Policy)</summary>
            <div style="padding-top: 1rem;">
                <p><strong>Terakhir diperbarui:</strong> 22 November 2025</p>
                <p>Aplikasi Scan Class berkomitmen melindungi privasi Anda. Berikut informasi yang kami kumpulkan dan bagaimana kami menggunakannya:</p>
                <h4>Informasi yang Kami Kumpulkan</h4>
                <ul>
                    <li><strong>Aplikasi Guru:</strong> Data Akun Guru, data Siswa & Kelas yang Anda masukkan, serta riwayat absensi disimpan secara lokal di perangkat Anda. Kami juga mengumpulkan ID Perangkat unik untuk keperluan aktivasi lisensi.</li>
                    <li><strong>Aplikasi Izin Siswa:</strong> Data yang dimasukkan pada formulir izin (NISN, Nama, Kelas, Tanggal, Keterangan) akan dikirim ke server kami (Firebase) untuk diteruskan ke guru.</li>
                </ul>
                <h4>Penggunaan Informasi</h4>
                <ul>
                    <li>Semua data digunakan untuk menjalankan fitur inti aplikasi, seperti rekam absensi, rekapitulasi, dan proses pengajuan izin.</li>
                    <li>ID Perangkat digunakan secara anonim untuk memvalidasi kunci aktivasi aplikasi.</li>
                </ul>
                <h4>Keamanan Data</h4>
                <p>Kami tidak menjual atau membagikan informasi pribadi Anda kepada pihak ketiga. Data sensitif seperti daftar siswa dan riwayat absensi tersimpan aman di perangkat Anda.</p>
                <p>Jika ada pertanyaan, hubungi kami di: <strong>adisaputra99@guru.sd.belajar.id</strong></p>
            </div>
        </details>

        <details>
            <summary>Syarat & Ketentuan (Terms & Conditions)</summary>
            <div style="padding-top: 1rem;">
                <p><strong>Terakhir diperbarui:</strong> 22 November 2025</p>
                <p>Dengan menggunakan aplikasi kami, Anda setuju pada syarat berikut:</p>
                <h4>Lisensi dan Aktivasi (Khusus Aplikasi Guru)</h4>
                <ul>
                    <li><strong>Masa Percobaan:</strong> Aplikasi Guru menyediakan masa percobaan gratis selama 14 hari dengan akses penuh ke semua fitur.</li>
                    <li><strong>Pembatasan Fitur:</strong> Setelah masa percobaan berakhir, fitur premium seperti Ekspor ke Excel dan Sinkronisasi akan dinonaktifkan.</li>
                    <li><strong>Aktivasi:</strong> Untuk terus menggunakan fitur premium, Anda harus melakukan aktivasi melalui menu yang tersedia di dalam aplikasi. Satu kunci aktivasi berlaku untuk satu perangkat.</li>
                </ul>
                <h4>Batasan Tanggung Jawab</h4>
                <p>Kami tidak bertanggung jawab atas kehilangan data akibat kerusakan perangkat, penghapusan aplikasi, atau faktor eksternal lainnya. Sangat disarankan untuk melakukan ekspor atau sinkronisasi data secara berkala sebagai cadangan mandiri.</p>
            </div>
        </details>
    </section>
</div>

<footer class="footer">
    <p>&copy; 2025 Scan Class - Dibuat oleh Adi Saputra</p>
</footer>
