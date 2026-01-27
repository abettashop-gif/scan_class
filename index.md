---
# Front Matter untuk Jekyll. Ini memberitahu Jekyll untuk menggunakan layout tema.
layout: default
---

<!-- 
    KODE DI BAWAH INI ADALAH KONTEN LENGKAP ANDA YANG TELAH DIPERBAIKI DAN DISEMPURNAKAN
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
    .main-content { padding: 1rem; }
    
    /* --- CONTAINER & HEADER KUSTOM ANDA --- */
    .container {
        max-width: 800px;
        margin: 0 auto;
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
    .main-buttons-container { display: flex; flex-direction: column; gap: 2rem; margin: 2rem auto; }
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
        <!-- Grup Tombol Unduh Aplikasi -->
        <div class="button-group">
            <h2 class="group-title">Unduh Aplikasi</h2>
            <p class="group-subtitle">Pilih versi aplikasi yang sesuai.</p>
            
            <a href="https://www.mediafire.com/file/8si4nckothpgzuf/Scan_class_2_4_1.apk/file" class="download-button primary">
                <i class="fas fa-chalkboard-teacher"></i> Aplikasi Guru (V.2.4.1) #TERBARU
            </a>

            <details style="width: 95%; max-width: 450px; margin: 0.5rem auto; border-color: var(--warning-color); background-color: #fff9e6;">
                <summary style="color: #856404; font-weight: bold;">
                    <i class="fas fa-exclamation-triangle"></i> WAJIB BACA: Info Update V.2.6
                </summary>
                 <div style="padding-top: 1rem; border-top: 1px solid #ffeeba; margin-top: 0.5rem;">
                    <h4 style="margin-top: 1rem; margin-bottom: 0.5rem; color: #333;">🚀 Changelog:</h4>
                     <ul>
                        <li>Perbaikan Struktur Data</li>
                        <li>Menu baru: Profile Edit dan tema </li>
                        <li>Perbaikan & peningkatan lainnya</li>
                    </ul>
                    <h4 style="margin-top: 1rem; margin-bottom: 0.5rem; color: #333;">Langkah Instalasi Pengguna Lama:</h4>
                    <ol style="padding-left: 20px; font-size: 0.95rem;">
                        <li><strong>Peringatan!!</strong> dari aplikasi.</li>
                        <li>Untuk Pencegahan Hal yang tidak diinginkan Lakukan Export/sycnron semua data absen yang ada</li>
                        <li>Jika Update tidak berhasil/error silahkan uninstal dan instal versi baru</li>
                        <li>Jika ada masalah atau ide Silahkan laporkan menggunakan menu bantuan yang tersedia.</li>
                    </ol>
            
                </div>
                <summary style="color: #856404; font-weight: bold;">
                    <i class="fas fa-exclamation-triangle"></i> WAJIB BACA: Info Update V.2.4.1
                </summary>
                <div style="padding-top: 1rem; border-top: 1px solid #ffeeba; margin-top: 0.5rem;">
                    <h4 style="margin-top: 1rem; margin-bottom: 0.5rem; color: #333;">🚀 Changelog:</h4>
                     <ul>
                        <li>Update keamanan akun</li>
                        <li>Menu baru: Jurnal Pembelajaran (ekspor langsung ke Excel)</li>
                        <li>Akun & data tersimpan di server</li>
                        <li>Data dapat dipulihkan saat ganti HP / instal ulang</li>
                        <li>Perbaikan & peningkatan lainnya</li>
                    </ul>

                    <h4 style="margin-top: 1rem; margin-bottom: 0.5rem; color: #333;">Langkah Instalasi Pengguna Lama:</h4>
                    <ol style="padding-left: 20px; font-size: 0.95rem;">
                        <li><strong>Uninstall versi lama</strong> dari aplikasi.</li>
                        <li>Install Scan Class v2.4.1.</li>
                        <li><strong>Registrasi ulang</strong> dengan email yang sama (pilih peran Wali Kelas / Guru Mapel sesuai tugas).</li>
                        <li>Isi data siswa & pengaturan seperti biasa.</li>
                    </ol>
                    <p style="margin-top: 1rem; font-size: 0.9rem;"><strong>Catatan Penting:</strong> Mulai versi ini, aplikasi bersifat <strong>semi-online</strong>. Login pertama kali wajib menggunakan koneksi internet. Akun dan data Anda kini terikat pada server, bukan lagi hanya di perangkat.</p>
                </div>
            </details>
            <a href="https://www.mediafire.com/file/gjj5je33s9iwvpq/Izin_Siswa_V1_1.apk/file" class="download-button" style="background-color: var(--success-color);">
                <i class="fas fa-user-graduate"></i> Aplikasi Siswa/Orang Tua V1.1 #LatesUpdate
            </a>            
            <a href="https://www.mediafire.com/file/ohym5l4jgeocvws/fix_izin_siswa_0.2.apk/file" class="download-button" style="background-color: var(--success-color);">
                <i class="fas fa-user-graduate"></i> Aplikasi Siswa/Orang Tua V0.2
            </a>
        </div>
        
        <!-- Grup Tombol Unduh File Pendukung -->
        <div class="button-group">
            <h2 class="group-title">Unduh File Pendukung</h2>
            <p class="group-subtitle">Gunakan file-file ini untuk fitur impor dan sinkronisasi.</p>
            <a href="https://drive.google.com/file/d/1eu-5L-mogqYmrzVdhNc8-aba8KDBXIWx/view?usp=sharing" class="download-button info">
                <i class="fas fa-file-csv"></i> Contoh File Import Siswa
            </a>
            <a href="https://docs.google.com/document/d/1kLX30K9OiZs2bmLGp5dR6zEA8XaBhG30/edit?usp=sharing&ouid=118214817902322932165&rtpof=true&sd=true" class="download-button danger">
                <i class="fab fa-google-drive"></i> Kode AppScript Sinkronisasi
            </a>
            <a href="https://docs.google.com/document/d/1ZQ-EedlKnkjC16PP7q9YUwNuaGH6VgNl/edit?usp=sharing&ouid=118214817902322932165&rtpof=true&sd=true" class="download-button danger">
                <i class="fab fa-google-drive"></i> Kode AppScript Data Izin
            </a>
        </div>
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
                <i class="fas fa-book-open"></i>
                <h4>Jurnal Mengajar Digital</h4>
                <p>Isi jurnal mengajar harian langsung di aplikasi dan ekspor ke dalam format <strong>Excel profesional</strong> yang siap cetak kapan saja.</p>
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
            </div>
             <div class="feature-item">
                <i class="fas fa-cloud-upload-alt"></i>
                <h4>Integrasi Aplikasi Siswa</h4>
                <p>Terima pengajuan izin sakit/izin secara digital dari aplikasi siswa, lengkap dengan bukti foto. Data izin otomatis terintegrasi ke dalam rekap absensi harian.</p>
            </div>
        </div>
    </section>

    <section class="section">
        <h2>🎬 Video Tutorial</h2>
        <p style="text-align:center;">Pelajari cara Membuat Master Data Siswa untuk import di Scan Class (CSV).</p>
        <ul><li><strong>Format CSV:</strong> Gunakan kolom dengan urutan <code>NISN</code>, <code>NAMA</code>, <code>JENISKELAMIN</code>.</li></ul>
        <div class="video-container">
            <iframe src="https://www.youtube.com/embed/-pwUjCfONNY?si=3B4VkHgd6FEBVDhM" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
        </div>
        <p style="text-align:center;">Pelajari cara Menghubungkan Scan Class ke Google Sheet melalui Apps Script Code.</p>
        <ul><li><strong>Info:</strong> Panduan ini berlaku untuk <strong>Sinkronisasi Rekap Absensi</strong> dan <strong>Pengambilan Data Izin</strong>. Gunakan kode Apps Script yang sesuai dari menu unduhan di atas.</li></ul>
        <div class="video-container">
            <iframe src="https://www.youtube.com/embed/ibsJVs8RtoI?si=PcH-vFcsDysDyU7y" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
        </div>
        <p style="text-align:center;">Contoh format header Google Sheet untuk Data Izin.</p>
        <a href="https://ibb.co.com/rG5vVNg"><img src="https://i.ibb.co/SXVJzG2/Whats-App-Image-2025-11-23-at-10-57-59.jpg" alt="Contoh Header Google Sheet untuk Data Izin" border="0" style="max-width:100%; height:auto; border-radius: 8px; margin-top: 1rem;"></a>
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
                    <p><span class="solution-tag">Solusi:</span> Sebelum mengganti perangkat atau melakukan reset, buka menu <code>Rekap Absensi</code>, lalu gunakan fitur <code>Ekspor ke Excel</code>. Simpan file hasil ekspor ke tempat aman.</p>
                </div>
                <div class="warning-item">
                    <strong class="warning-title">2. JANGAN "Hapus Data" (Clear Data) dari Pengaturan Android</strong>
                    <p><span class="reason-tag">Mengapa?</span> Aksi ini memiliki efek yang <strong>SAMA PERSIS</strong> dengan uninstall aplikasi. Semua data lokal akan terhapus.</p>
                    <p><span class="solution-tag">Solusi:</span> Jika aplikasi lambat, coba "Hapus Cache" (Clear Cache) dulu. Jika masih bermasalah, ekspor data Anda sebelum mencoba langkah ini.</p>
                </div>
                 <div class="warning-item">
                    <strong class="warning-title">3. PASTIKAN Login Pertama Kali Menggunakan Internet</strong>
                    <p><span class="reason-tag">Mengapa?</span> Mulai versi 2.4.1, aplikasi memerlukan koneksi internet saat login pertama kali untuk sinkronisasi akun dengan server.</p>
                    <p><span class="solution-tag">Solusi:</span> Setelah registrasi ulang, pastikan perangkat terhubung ke internet yang stabil saat Anda login.</p>
                </div>
            </div>
        </details>

        <details>
            <summary>Kebijakan Privasi (Privacy Policy)</summary>
            <div style="padding-top: 1rem;">
                <p><strong>Terakhir diperbarui:</strong> 12 Januari 2026</p>
                <p>Aplikasi Scan Class berkomitmen melindungi privasi Anda. Berikut informasi yang kami kumpulkan dan bagaimana kami menggunakannya:</p>
                <h4>Informasi yang Kami Kumpulkan</h4>
                <ul>
                    <li><strong>Aplikasi Guru:</strong> Data Akun Guru (email, nama, dll.), data Siswa & Kelas yang Anda masukkan, serta riwayat absensi disimpan di server kami (Firebase) dan juga dicadangkan secara lokal di perangkat Anda. Kami juga mengumpulkan ID Perangkat unik untuk keperluan aktivasi lisensi.</li>
                    <li><strong>Aplikasi Izin Siswa:</strong> Data yang dimasukkan pada formulir izin (NISN, Nama, Kelas, Tanggal, Keterangan, URL bukti) akan dikirim ke server kami (Firebase) untuk diteruskan ke guru yang bersangkutan.</li>
                </ul>
                <h4>Penggunaan Informasi</h4>
                <ul>
                    <li>Semua data digunakan untuk menjalankan fitur inti aplikasi, seperti rekam absensi, rekapitulasi, sinkronisasi antar perangkat, dan proses pengajuan izin.</li>
                    <li>ID Perangkat digunakan secara anonim untuk memvalidasi kunci aktivasi aplikasi.</li>
                </ul>
                <h4>Keamanan Data</h4>
                <p>Kami tidak menjual atau membagikan informasi pribadi Anda kepada pihak ketiga. Data Anda dienkripsi saat transit dan dilindungi oleh aturan keamanan Firebase.</p>
                <p>Jika ada pertanyaan, hubungi kami di: <strong>adisaputra99@guru.sd.belajar.id</strong></p>
            </div>
        </details>

        <details>
            <summary>Syarat & Ketentuan (Terms & Conditions)</summary>
            <div style="padding-top: 1rem;">
                <p><strong>Terakhir diperbarui:</strong> 12 Januari 2026</p>
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
    <p>&copy; 2026 Scan Class - Dibuat oleh Adi Saputra</p>
</footer>

