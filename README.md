<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sistem Informatika Terintegrasi - SMPN 1 Seputih Surabaya</title>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css" rel="stylesheet">
    <script src="https://cdnjs.cloudflare.com/ajax/libs/lz-string/1.4.4/lz-string.min.js"></script>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, sans-serif;
        }

        body {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            color: #333;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }

        .card {
            background: white;
            border-radius: 12px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
            padding: 25px;
            margin-bottom: 25px;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }

        .card:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.15);
        }

        .card-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 20px;
            padding-bottom: 15px;
            border-bottom: 1px solid #eee;
        }

        .card-title {
            font-size: 1.5rem;
            font-weight: 600;
            color: #4f46e5;
        }

        .btn {
            padding: 10px 20px;
            border: none;
            border-radius: 8px;
            cursor: pointer;
            font-weight: 500;
            display: inline-flex;
            align-items: center;
            gap: 8px;
            transition: all 0.3s ease;
        }

        .btn-primary {
            background: #4f46e5;
            color: white;
        }

        .btn-primary:hover {
            background: #4338ca;
            transform: translateY(-2px);
        }

        .btn-success {
            background: #10b981;
            color: white;
        }

        .btn-success:hover {
            background: #059669;
            transform: translateY(-2px);
        }

        .btn-warning {
            background: #f59e0b;
            color: white;
        }

        .btn-warning:hover {
            background: #d97706;
            transform: translateY(-2px);
        }

        .btn-danger {
            background: #ef4444;
            color: white;
        }

        .btn-danger:hover {
            background: #dc2626;
            transform: translateY(-2px);
        }

        .btn-secondary {
            background: #6b7280;
            color: white;
        }

        .btn-secondary:hover {
            background: #4b5563;
            transform: translateY(-2px);
        }

        .form-group {
            margin-bottom: 20px;
        }

        .form-label {
            display: block;
            margin-bottom: 8px;
            font-weight: 500;
            color: #374151;
        }

        .form-control {
            width: 100%;
            padding: 12px 15px;
            border: 1px solid #d1d5db;
            border-radius: 8px;
            font-size: 1rem;
            transition: border-color 0.3s ease, box-shadow 0.3s ease;
        }

        .form-control:focus {
            outline: none;
            border-color: #4f46e5;
            box-shadow: 0 0 0 3px rgba(79, 70, 229, 0.1);
        }

        .badge {
            display: inline-block;
            padding: 5px 10px;
            border-radius: 20px;
            font-size: 0.85rem;
            font-weight: 500;
        }

        .badge.success {
            background: #d1fae5;
            color: #065f46;
        }

        .badge.warning {
            background: #fef3c7;
            color: #92400e;
        }

        .badge.danger {
            background: #fee2e2;
            color: #991b1b;
        }

        .badge.gray {
            background: #f3f4f6;
            color: #6b7280;
        }

        .badge.blue {
            background: #dbeafe;
            color: #1e40af;
        }

        .tab-container {
            display: flex;
            border-bottom: 1px solid #e5e7eb;
            margin-bottom: 20px;
            overflow-x: auto;
        }

        .tab-btn {
            padding: 12px 20px;
            background: none;
            border: none;
            cursor: pointer;
            font-weight: 500;
            color: #6b7280;
            border-bottom: 2px solid transparent;
            transition: all 0.3s ease;
            white-space: nowrap;
        }

        .tab-btn.active {
            color: #4f46e5;
            border-bottom-color: #4f46e5;
        }

        .tab-btn:hover {
            color: #4f46e5;
        }

        .tab-content {
            display: none;
        }

        .tab-content.active {
            display: block;
        }

        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            margin-bottom: 25px;
        }

        .stat-card {
            background: white;
            border-radius: 12px;
            padding: 20px;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.05);
            text-align: center;
            transition: transform 0.3s ease;
        }

        .stat-card:hover {
            transform: translateY(-5px);
        }

        .stat-card.blue {
            border-top: 4px solid #4f46e5;
        }

        .stat-card.green {
            border-top: 4px solid #10b981;
        }

        .stat-card.orange {
            border-top: 4px solid #f59e0b;
        }

        .stat-card.purple {
            border-top: 4px solid #8b5cf6;
        }

        .stat-card .label {
            font-size: 0.9rem;
            color: #6b7280;
            margin-bottom: 8px;
        }

        .stat-card .value {
            font-size: 2rem;
            font-weight: 700;
            color: #1f2937;
        }

        .materi-item {
            background: white;
            border-radius: 10px;
            padding: 20px;
            margin-bottom: 15px;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.05);
            border-left: 4px solid #4f46e5;
            transition: all 0.3s ease;
        }

        .materi-item:hover {
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            transform: translateX(5px);
        }

        .materi-header {
            display: flex;
            justify-content: space-between;
            align-items: flex-start;
            margin-bottom: 10px;
        }

        .materi-actions {
            display: flex;
            gap: 10px;
        }

        .progress-bar {
            height: 8px;
            background: #e5e7eb;
            border-radius: 4px;
            overflow: hidden;
            margin: 10px 0;
        }

        .progress-fill {
            height: 100%;
            background: #10b981;
            border-radius: 4px;
            transition: width 0.5s ease;
        }

        table {
            width: 100%;
            border-collapse: collapse;
        }

        th, td {
            padding: 12px 15px;
            text-align: left;
            border-bottom: 1px solid #e5e7eb;
        }

        th {
            background: #f9fafb;
            font-weight: 600;
            color: #374151;
        }

        tr:hover {
            background: #f9fafb;
        }

        .login-container {
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            padding: 20px;
        }

        .login-card {
            background: white;
            border-radius: 16px;
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.1);
            padding: 40px;
            width: 100%;
            max-width: 450px;
            text-align: center;
        }

        .login-title {
            font-size: 1.8rem;
            font-weight: 700;
            margin-bottom: 10px;
            color: #1f2937;
        }

        .login-subtitle {
            color: #6b7280;
            margin-bottom: 30px;
        }

        .role-selector {
            display: flex;
            margin-bottom: 25px;
            border-radius: 10px;
            overflow: hidden;
            border: 1px solid #d1d5db;
        }

        .role-btn {
            flex: 1;
            padding: 12px;
            background: white;
            border: none;
            cursor: pointer;
            font-weight: 500;
            transition: all 0.3s ease;
        }

        .role-btn.active {
            background: #4f46e5;
            color: white;
        }

        .demo-info {
            background: #f0f9ff;
            border-radius: 8px;
            padding: 15px;
            margin-top: 20px;
            text-align: left;
            font-size: 0.9rem;
            color: #0369a1;
            border-left: 4px solid #0ea5e9;
        }

        .file-preview {
            display: flex;
            align-items: center;
            gap: 12px;
            background: #f9fafb;
            border-radius: 8px;
            padding: 15px;
            margin-top: 15px;
        }

        .file-info {
            flex: 1;
        }

        .file-name {
            font-weight: 500;
            margin-bottom: 5px;
        }

        .file-size {
            font-size: 0.85rem;
            color: #6b7280;
        }

        .share-section {
            background: #f0f9ff;
            border-radius: 10px;
            padding: 20px;
            margin-top: 25px;
        }

        .share-input-group {
            display: flex;
            gap: 10px;
            margin-bottom: 15px;
        }

        .share-input {
            flex: 1;
            padding: 12px 15px;
            border: 1px solid #d1d5db;
            border-radius: 8px;
            font-size: 0.9rem;
        }

        .copy-btn {
            background: #4f46e5;
            color: white;
            border: none;
            border-radius: 8px;
            padding: 0 15px;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .copy-btn:hover {
            background: #4338ca;
        }

        .copy-btn.copied {
            background: #10b981;
        }

        .share-buttons {
            display: flex;
            gap: 10px;
        }

        .share-btn {
            flex: 1;
            padding: 10px;
            border: none;
            border-radius: 8px;
            cursor: pointer;
            font-weight: 500;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 8px;
            transition: all 0.3s ease;
        }

        .whatsapp-btn {
            background: #25d366;
            color: white;
        }

        .whatsapp-btn:hover {
            background: #128c7e;
        }

        .telegram-btn {
            background: #0088cc;
            color: white;
        }

        .telegram-btn:hover {
            background: #006699;
        }

        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.5);
            z-index: 1000;
            justify-content: center;
            align-items: center;
        }

        .modal-content {
            background: white;
            border-radius: 12px;
            width: 90%;
            max-width: 600px;
            max-height: 90vh;
            overflow-y: auto;
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.2);
        }

        .modal-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px;
            border-bottom: 1px solid #e5e7eb;
        }

        .modal-title {
            font-size: 1.3rem;
            font-weight: 600;
            color: #1f2937;
        }

        .modal-close {
            background: none;
            border: none;
            font-size: 1.5rem;
            cursor: pointer;
            color: #6b7280;
            transition: color 0.3s ease;
        }

        .modal-close:hover {
            color: #374151;
        }

        .modal-body {
            padding: 20px;
        }

        .status-buttons {
            display: flex;
            gap: 10px;
            margin-bottom: 20px;
        }

        .status-btn {
            flex: 1;
            padding: 12px;
            border: 1px solid #d1d5db;
            border-radius: 8px;
            background: white;
            cursor: pointer;
            font-weight: 500;
            transition: all 0.3s ease;
        }

        .status-btn.active {
            background: #4f46e5;
            color: white;
            border-color: #4f46e5;
        }

        .nilai-input {
            width: 70px;
            padding: 8px;
            border: 1px solid #d1d5db;
            border-radius: 6px;
            text-align: center;
        }

        @media (max-width: 768px) {
            .materi-header {
                flex-direction: column;
                gap: 15px;
            }
            
            .materi-actions {
                width: 100%;
                justify-content: flex-end;
            }
            
            .share-input-group {
                flex-direction: column;
            }
            
            .share-buttons {
                flex-direction: column;
            }
            
            .stats-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <!-- Halaman Login -->
    <div id="loginPage" class="login-container">
        <div class="login-card">
            <h1 class="login-title">SMPN 1 Seputih Surabaya</h1>
            <p class="login-subtitle">Sistem Informatika Terintegrasi</p>
            
            <div class="role-selector">
                <button class="role-btn active" onclick="selectRole('siswa')">Siswa</button>
                <button class="role-btn" onclick="selectRole('guru')">Guru</button>
            </div>
            
            <form id="loginForm" onsubmit="handleLogin(event)">
                <div class="form-group">
                    <label for="username" class="form-label" id="usernameLabel">NIS</label>
                    <input type="text" id="username" class="form-control" placeholder="Masukkan NIS" required>
                </div>
                
                <div class="form-group">
                    <label for="password" class="form-label">Password</label>
                    <input type="password" id="password" class="form-control" placeholder="Masukkan password" required>
                </div>
                
                <button type="submit" class="btn btn-primary" style="width: 100%;">
                    <i class="fas fa-sign-in-alt"></i> Masuk
                </button>
            </form>
            
            <div class="demo-info" id="demoInfo">
                <strong>Demo Siswa:</strong><br>
                NIS: <strong>8103</strong><br>
                Password: <strong>8103</strong>
            </div>
        </div>
    </div>
    
    <!-- Dashboard Siswa -->
    <div id="dashboardSiswa" class="container" style="display: none;">
        <div class="card">
            <div class="card-header">
                <h1 class="card-title">Dashboard Siswa</h1>
                <div>
                    <span id="siswaInfo"></span>
                    <button class="btn btn-secondary" onclick="logout()" style="margin-left: 15px;">
                        <i class="fas fa-sign-out-alt"></i> Keluar
                    </button>
                </div>
            </div>
            
            <div class="stats-grid">
                <div class="stat-card blue">
                    <div class="label">Kehadiran</div>
                    <div class="value" id="siswaKehadiran">0%</div>
                </div>
                <div class="stat-card green">
                    <div class="label">Tugas Selesai</div>
                    <div class="value" id="siswaTugasSelesai">0/0</div>
                </div>
                <div class="stat-card orange">
                    <div class="label">Nilai Rata-rata</div>
                    <div class="value" id="siswaNilaiRata">0</div>
                </div>
            </div>
            
            <div class="tab-container">
                <button class="tab-btn active" onclick="switchTab('siswa', 'home')">Beranda</button>
                <button class="tab-btn" onclick="switchTab('siswa', 'absensi')">Absensi</button>
                <button class="tab-btn" onclick="switchTab('siswa', 'tugas')">Tugas</button>
                <button class="tab-btn" onclick="switchTab('siswa', 'materi')">Materi</button>
                <button class="tab-btn" onclick="switchTab('siswa', 'nilai')">Nilai</button>
            </div>
            
            <!-- Tab Beranda Siswa -->
            <div id="siswa-home" class="tab-content active">
                <div class="card">
                    <h2 style="margin-bottom: 15px;">Selamat Datang!</h2>
                    <p style="margin-bottom: 20px; color: #6b7280;">
                        Selamat datang di Sistem Informatika Terintegrasi SMPN 1 Seputih Surabaya. 
                        Gunakan menu di atas untuk mengakses berbagai fitur pembelajaran.
                    </p>
                    
                    <div class="share-section">
                        <h3 style="margin-bottom: 15px;">Bagikan Data Pembelajaran</h3>
                        <div class="share-input-group">
                            <input type="text" id="shareUrl" class="share-input" readonly>
                            <button class="copy-btn" onclick="copyShareUrl()">
                                <i class="fas fa-copy"></i>
                            </button>
                        </div>
                        <div class="share-buttons">
                            <button class="share-btn whatsapp-btn" onclick="shareToWhatsApp()">
                                <i class="fab fa-whatsapp"></i> WhatsApp
                            </button>
                            <button class="share-btn telegram-btn" onclick="shareToTelegram()">
                                <i class="fab fa-telegram"></i> Telegram
                            </button>
                        </div>
                    </div>
                </div>
            </div>
            
            <!-- Tab Absensi Siswa -->
            <div id="siswa-absensi" class="tab-content">
                <div class="card">
                    <h2 style="margin-bottom: 20px;">Absensi Harian</h2>
                    
                    <div class="form-group">
                        <label class="form-label">Tanggal</label>
                        <input type="date" id="siswaAbsensiDate" class="form-control">
                    </div>
                    
                    <div class="form-group">
                        <label class="form-label">Status Kehadiran</label>
                        <div class="status-buttons">
                            <button class="status-btn" onclick="selectStatus('present')">
                                <i class="fas fa-check-circle"></i> Hadir
                            </button>
                            <button class="status-btn" onclick="selectStatus('late')">
                                <i class="fas fa-clock"></i> Terlambat
                            </button>
                            <button class="status-btn" onclick="selectStatus('absent')">
                                <i class="fas fa-times-circle"></i> Tidak Hadir
                            </button>
                        </div>
                    </div>
                    
                    <div class="form-group">
                        <label class="form-label">Keterangan (Opsional)</label>
                        <textarea id="siswaAbsensiNote" class="form-control" rows="3" placeholder="Tambahkan keterangan jika diperlukan..."></textarea>
                    </div>
                    
                    <button class="btn btn-primary" onclick="submitAbsensi()">
                        <i class="fas fa-paper-plane"></i> Kirim Absensi
                    </button>
                </div>
            </div>
            
            <!-- Tab Tugas Siswa -->
            <div id="siswa-tugas" class="tab-content">
                <div class="card">
                    <h2 style="margin-bottom: 20px;">Daftar Tugas</h2>
                    <div id="siswaTugasList">
                        <!-- Daftar tugas akan dimuat di sini -->
                    </div>
                </div>
            </div>
            
            <!-- Tab Materi Siswa -->
            <div id="siswa-materi" class="tab-content">
                <div class="card">
                    <h2 style="margin-bottom: 20px;">Materi Pembelajaran</h2>
                    <div id="siswaMateriList">
                        <!-- Daftar materi akan dimuat di sini -->
                    </div>
                </div>
            </div>
            
            <!-- Tab Nilai Siswa -->
            <div id="siswa-nilai" class="tab-content">
                <div class="card">
                    <h2 style="margin-bottom: 20px;">Nilai dan Evaluasi</h2>
                    <div id="siswaNilaiList">
                        <!-- Daftar nilai akan dimuat di sini -->
                    </div>
                </div>
            </div>
        </div>
    </div>
    
    <!-- Dashboard Guru -->
    <div id="dashboardGuru" class="container" style="display: none;">
        <div class="card">
            <div class="card-header">
                <h1 class="card-title">Dashboard Guru</h1>
                <div>
                    <button class="btn btn-secondary" onclick="logout()">
                        <i class="fas fa-sign-out-alt"></i> Keluar
                    </button>
                </div>
            </div>
            
            <div class="stats-grid">
                <div class="stat-card blue">
                    <div class="label">Total Siswa</div>
                    <div class="value" id="totalSiswaCount">0</div>
                </div>
                <div class="stat-card green">
                    <div class="label">Hadir Hari Ini</div>
                    <div class="value" id="guruPresentCount">0</div>
                </div>
                <div class="stat-card orange">
                    <div class="label">Tugas Aktif</div>
                    <div class="value" id="guruActiveTasks">0</div>
                </div>
                <div class="stat-card purple">
                    <div class="label">Materi Tersedia</div>
                    <div class="value" id="guruMateriCount">0</div>
                </div>
            </div>
            
            <div class="tab-container">
                <button class="tab-btn active" onclick="switchTab('guru', 'home')">Beranda</button>
                <button class="tab-btn" onclick="switchTab('guru', 'absensi')">Absensi</button>
                <button class="tab-btn" onclick="switchTab('guru', 'tugas')">Tugas</button>
                <button class="tab-btn" onclick="switchTab('guru', 'materi')">Materi</button>
                <button class="tab-btn" onclick="switchTab('guru', 'siswa')">Data Siswa</button>
                <button class="tab-btn" onclick="switchTab('guru', 'penilaian')">Penilaian</button>
            </div>
            
            <!-- Tab Beranda Guru -->
            <div id="guru-home" class="tab-content active">
                <div class="card">
                    <h2 style="margin-bottom: 15px;">Selamat Datang, Guru!</h2>
                    <p style="margin-bottom: 20px; color: #6b7280;">
                        Selamat datang di Sistem Informatika Terintegrasi SMPN 1 Seputih Surabaya. 
                        Gunakan menu di atas untuk mengelola pembelajaran siswa.
                    </p>
                    
                    <div class="share-section">
                        <h3 style="margin-bottom: 15px;">Bagikan Data Pembelajaran</h3>
                        <div class="share-input-group">
                            <input type="text" id="shareUrlGuru" class="share-input" readonly>
                            <button class="copy-btn" onclick="copyShareUrl()">
                                <i class="fas fa-copy"></i>
                            </button>
                        </div>
                        <div class="share-buttons">
                            <button class="share-btn whatsapp-btn" onclick="shareToWhatsApp()">
                                <i class="fab fa-whatsapp"></i> WhatsApp
                            </button>
                            <button class="share-btn telegram-btn" onclick="shareToTelegram()">
                                <i class="fab fa-telegram"></i> Telegram
                            </button>
                        </div>
                    </div>
                </div>
            </div>
            
            <!-- Tab Absensi Guru -->
            <div id="guru-absensi" class="tab-content">
                <div class="card">
                    <h2 style="margin-bottom: 20px;">Rekap Absensi</h2>
                    
                    <div class="form-group" style="display: flex; gap: 15px;">
                        <div style="flex: 1;">
                            <label class="form-label">Kelas</label>
                            <select id="guruAbsensiKelas" class="form-control" onchange="loadAbsensiGuru()">
                                <option value="8.1">8.1</option>
                                <option value="8.2">8.2</option>
                                <option value="8.3">8.3</option>
                                <option value="8.4">8.4</option>
                                <option value="8.5">8.5</option>
                                <option value="8.6">8.6</option>
                                <option value="8.7">8.7</option>
                                <option value="8.8">8.8</option>
                            </select>
                        </div>
                        <div style="flex: 1;">
                            <label class="form-label">Tanggal</label>
                            <input type="date" id="guruAbsensiDate" class="form-control" onchange="loadAbsensiGuru()">
                        </div>
                    </div>
                    
                    <div style="overflow-x: auto;">
                        <table>
                            <thead>
                                <tr>
                                    <th>No</th>
                                    <th>NIS</th>
                                    <th>Nama</th>
                                    <th>Status</th>
                                </tr>
                            </thead>
                            <tbody id="guruAbsensiBody">
                                <!-- Data absensi akan dimuat di sini -->
                            </tbody>
                        </table>
                    </div>
                </div>
            </div>
            
            <!-- Tab Tugas Guru -->
            <div id="guru-tugas" class="tab-content">
                <div class="card">
                    <div class="card-header">
                        <h2 class="card-title">Manajemen Tugas</h2>
                        <button class="btn btn-primary" onclick="toggleFormTugas()">
                            <i class="fas fa-plus"></i> Tugas Baru
                        </button>
                    </div>
                    
                    <div id="formTugas" style="display: none; margin-bottom: 25px; padding: 20px; border: 1px solid #e5e7eb; border-radius: 8px;">
                        <h3 style="margin-bottom: 15px;">Tambah Tugas Baru</h3>
                        
                        <div class="form-group">
                            <label class="form-label">Judul Tugas</label>
                            <input type="text" id="tugasTitle" class="form-control" placeholder="Masukkan judul tugas">
                        </div>
                        
                        <div class="form-group">
                            <label class="form-label">Kelas</label>
                            <select id="tugasKelas" class="form-control">
                                <option value="8.1">8.1</option>
                                <option value="8.2">8.2</option>
                                <option value="8.3">8.3</option>
                                <option value="8.4">8.4</option>
                                <option value="8.5">8.5</option>
                                <option value="8.6">8.6</option>
                                <option value="8.7">8.7</option>
                                <option value="8.8">8.8</option>
                                <option value="all">Semua Kelas</option>
                            </select>
                        </div>
                        
                        <div class="form-group">
                            <label class="form-label">Deadline</label>
                            <input type="datetime-local" id="tugasDeadline" class="form-control">
                        </div>
                        
                        <div class="form-group">
                            <label class="form-label">Deskripsi</label>
                            <textarea id="tugasDesc" class="form-control" rows="3" placeholder="Masukkan deskripsi tugas"></textarea>
                        </div>
                        
                        <div class="form-group">
                            <label class="form-label">Lampiran (Opsional)</label>
                            <input type="file" id="tugasFile" class="form-control" onchange="handleFileSelect(event)">
                            
                            <div id="filePreview" class="file-preview" style="display: none;">
                                <i id="fileIcon" class="fas fa-file"></i>
                                <div class="file-info">
                                    <div class="file-name" id="fileName"></div>
                                    <div class="file-size" id="fileSize"></div>
                                </div>
                                <button type="button" class="btn btn-danger" onclick="removeFile()">
                                    <i class="fas fa-times"></i>
                                </button>
                            </div>
                        </div>
                        
                        <div style="display: flex; gap: 10px;">
                            <button class="btn btn-primary" onclick="saveTugas()">
                                <i class="fas fa-save"></i> Simpan
                            </button>
                            <button type="button" class="btn btn-secondary" onclick="toggleFormTugas()">
                                <i class="fas fa-times"></i> Batal
                            </button>
                        </div>
                    </div>
                    
                    <div id="guruTugasList">
                        <!-- Daftar tugas akan dimuat di sini -->
                    </div>
                </div>
            </div>
            
            <!-- Tab Materi Guru -->
            <div id="guru-materi" class="tab-content">
                <div class="card">
                    <div class="card-header">
                        <h2 class="card-title">Manajemen Materi</h2>
                        <button class="btn btn-primary" onclick="toggleFormMateri()">
                            <i class="fas fa-plus"></i> Materi Baru
                        </button>
                    </div>
                    
                    <div id="formMateri" style="display: none; margin-bottom: 25px; padding: 20px; border: 1px solid #e5e7eb; border-radius: 8px;">
                        <h3 style="margin-bottom: 15px;">Tambah Materi Baru</h3>
                        
                        <div class="form-group">
                            <label class="form-label">Judul Materi</label>
                            <input type="text" id="materiTitle" class="form-control" placeholder="Masukkan judul materi">
                        </div>
                        
                        <div class="form-group">
                            <label class="form-label">Kelas</label>
                            <select id="materiKelas" class="form-control">
                                <option value="8.1">8.1</option>
                                <option value="8.2">8.2</option>
                                <option value="8.3">8.3</option>
                                <option value="8.4">8.4</option>
                                <option value="8.5">8.5</option>
                                <option value="8.6">8.6</option>
                                <option value="8.7">8.7</option>
                                <option value="8.8">8.8</option>
                                <option value="all">Semua Kelas</option>
                            </select>
                        </div>
                        
                        <div class="form-group">
                            <label class="form-label">Deskripsi</label>
                            <textarea id="materiDesc" class="form-control" rows="3" placeholder="Masukkan deskripsi materi"></textarea>
                        </div>
                        
                        <div class="form-group">
                            <label class="form-label">Lampiran (Opsional)</label>
                            <input type="file" id="materiFile" class="form-control" onchange="handleMateriFileSelect(event)">
                            
                            <div id="materiFilePreview" class="file-preview" style="display: none;">
                                <i id="materiFileIcon" class="fas fa-file"></i>
                                <div class="file-info">
                                    <div class="file-name" id="materiFileName"></div>
                                    <div class="file-size" id="materiFileSize"></div>
                                </div>
                                <button type="button" class="btn btn-danger" onclick="removeMateriFile()">
                                    <i class="fas fa-times"></i>
                                </button>
                            </div>
                        </div>
                        
                        <div style="display: flex; gap: 10px;">
                            <button class="btn btn-primary" onclick="saveMateri()">
                                <i class="fas fa-save"></i> Simpan
                            </button>
                            <button type="button" class="btn btn-secondary" onclick="toggleFormMateri()">
                                <i class="fas fa-times"></i> Batal
                            </button>
                        </div>
                    </div>
                    
                    <div id="guruMateriList">
                        <!-- Daftar materi akan dimuat di sini -->
                    </div>
                </div>
            </div>
            
            <!-- Tab Data Siswa -->
            <div id="guru-siswa" class="tab-content">
                <div class="card">
                    <h2 style="margin-bottom: 20px;">Data Siswa</h2>
                    
                    <div class="form-group">
                        <label class="form-label">Kelas</label>
                        <select id="guruSiswaKelas" class="form-control" onchange="loadDataSiswa()">
                            <option value="8.1">8.1</option>
                            <option value="8.2">8.2</option>
                            <option value="8.3">8.3</option>
                            <option value="8.4">8.4</option>
                            <option value="8.5">8.5</option>
                            <option value="8.6">8.6</option>
                            <option value="8.7">8.7</option>
                            <option value="8.8">8.8</option>
                        </select>
                    </div>
                    
                    <div style="overflow-x: auto;">
                        <table>
                            <thead>
                                <tr>
                                    <th>No</th>
                                    <th>NIS</th>
                                    <th>Nama</th>
                                    <th>Kelas</th>
                                    <th>Kehadiran</th>
                                    <th>Nilai Rata-rata</th>
                                </tr>
                            </thead>
                            <tbody id="guruSiswaBody">
                                <!-- Data siswa akan dimuat di sini -->
                            </tbody>
                        </table>
                    </div>
                </div>
            </div>
            
            <!-- Tab Penilaian -->
            <div id="guru-penilaian" class="tab-content">
                <div class="card">
                    <h2 style="margin-bottom: 20px;">Penilaian Tugas</h2>
                    
                    <div class="form-group" style="display: flex; gap: 15px;">
                        <div style="flex: 1;">
                            <label class="form-label">Kelas</label>
                            <select id="penilaianKelas" class="form-control" onchange="loadPenilaian()">
                                <option value="8.1">8.1</option>
                                <option value="8.2">8.2</option>
                                <option value="8.3">8.3</option>
                                <option value="8.4">8.4</option>
                                <option value="8.5">8.5</option>
                                <option value="8.6">8.6</option>
                                <option value="8.7">8.7</option>
                                <option value="8.8">8.8</option>
                            </select>
                        </div>
                        <div style="flex: 1;">
                            <label class="form-label">Tugas</label>
                            <select id="penilaianTugas" class="form-control" onchange="loadPenilaian()">
                                <option value="">Pilih Tugas</option>
                            </select>
                        </div>
                    </div>
                    
                    <div style="overflow-x: auto;">
                        <table>
                            <thead>
                                <tr>
                                    <th>No</th>
                                    <th>NIS</th>
                                    <th>Nama</th>
                                    <th>Status</th>
                                    <th>Nilai</th>
                                    <th>Komentar</th>
                                    <th>Aksi</th>
                                </tr>
                            </thead>
                            <tbody id="guruPenilaianBody">
                                <!-- Data penilaian akan dimuat di sini -->
                            </tbody>
                        </table>
                    </div>
                </div>
            </div>
        </div>
    </div>
    
    <!-- Modal Tugas -->
    <div id="tugasModal" class="modal">
        <div class="modal-content">
            <div class="modal-header">
                <h3 class="modal-title">Kerjakan Tugas</h3>
                <button class="modal-close" onclick="closeTugasModal()">&times;</button>
            </div>
            <div class="modal-body">
                <div class="form-group">
                    <label class="form-label">Jawaban</label>
                    <textarea id="tugasJawaban" class="form-control" rows="6" placeholder="Tulis jawaban Anda di sini..."></textarea>
                </div>
                
                <div class="form-group">
                    <label class="form-label">Lampiran (Opsional)</label>
                    <input type="file" class="form-control">
                </div>
                
                <div style="display: flex; gap: 10px; justify-content: flex-end;">
                    <button class="btn btn-primary">
                        <i class="fas fa-paper-plane"></i> Kirim
                    </button>
                    <button class="btn btn-secondary" onclick="closeTugasModal()">
                        <i class="fas fa-times"></i> Batal
                    </button>
                </div>
            </div>
        </div>
    </div>
    
    <!-- Modal Nilai -->
    <div id="nilaiModal" class="modal">
        <div class="modal-content">
            <div class="modal-header">
                <h3 class="modal-title">Detail Penilaian</h3>
                <button class="modal-close" onclick="closeNilaiModal()">&times;</button>
            </div>
            <div class="modal-body">
                <div class="form-group">
                    <label class="form-label">Nilai</label>
                    <input type="number" id="modalNilai" class="form-control" min="0" max="100">
                </div>
                
                <div class="form-group">
                    <label class="form-label">Komentar</label>
                    <textarea id="modalKomentar" class="form-control" rows="4" placeholder="Berikan komentar untuk siswa..."></textarea>
                </div>
                
                <div style="display: flex; gap: 10px; justify-content: flex-end;">
                    <button class="btn btn-primary">
                        <i class="fas fa-save"></i> Simpan
                    </button>
                    <button class="btn btn-secondary" onclick="closeNilaiModal()">
                        <i class="fas fa-times"></i> Batal
                    </button>
                </div>
            </div>
        </div>
    </div>

    <script>
        // DATA SISWA LENGKAP DARI FILE ASLI
        const studentsData = {
            "8.1": [
                { nis: "8103", name: "ALFIN MAULANA AKBAR", password: "8103" },
                { nis: "8106", name: "ALIF AFFAN BAYHAQI", password: "8106" },
                { nis: "8112", name: "ANGELICA ANDRA OKTAVIA", password: "8112" },
                { nis: "8115", name: "ANI SAFITRI", password: "8115" },
                { nis: "8131", name: "ASKIA FARDA NAFISA", password: "8131" },
                { nis: "8132", name: "ASSYIFA'UL HAMIDAH", password: "8132" },
                { nis: "8138", name: "AURELIA KANIA WIDA PUTRI", password: "8138" },
                { nis: "8140", name: "AYU RETNO PUTRI", password: "8140" },
                { nis: "8144", name: "AZZAM BAHIR", password: "8144" },
                { nis: "8157", name: "DIKA ALFIAN SAPUTRA", password: "8157" },
                { nis: "8168", name: "FALEN KESTI FIRNAYU", password: "8168" },
                { nis: "8170", name: "FARISKI NIKO EPENDI", password: "8170" },
                { nis: "8175", name: "FREDITA YUSDINA", password: "8175" },
                { nis: "8179", name: "GUSTI AYU NADIA", password: "8179" },
                { nis: "8181", name: "HAIRIL ARMANDA PUTRA", password: "8181" },
                { nis: "8187", name: "HENI YULIASARI", password: "8187" },
                { nis: "8200", name: "IQBAL REYVANDY", password: "8200" },
                { nis: "8202", name: "ISNAENI LARASATI", password: "8202" },
                { nis: "8214", name: "KORIN PUJI LESTARI", password: "8214" },
                { nis: "8226", name: "M. IQBAL PRATAMA", password: "8226" },
                { nis: "8233", name: "MARCHELITHA RIZQI ATHQODARY", password: "8233" },
                { nis: "8234", name: "MARSYA AULIA PUTRI", password: "8234" },
                { nis: "8237", name: "MOHAMMAD REHAN ERLANGGA", password: "8237" },
                { nis: "8245", name: "MUHAMAD WILDAN RAMDHANI", password: "8245" },
                { nis: "8253", name: "MUHAMMAD HAFIZHUL MUZAKKI", password: "8253" },
                { nis: "8283", name: "PUTRI KHAIRUNIA", password: "8283" },
                { nis: "8287", name: "RAFA PRATAMA AFANDI", password: "8287" },
                { nis: "8309", name: "RIZKI TIRTAJAYA", password: "8309" },
                { nis: "8325", name: "STEFANI PAULIN BR MANIK", password: "8325" },
                { nis: "8329", name: "SYIFA AZZAHRA SUTIYONO", password: "8329" },
                { nis: "8342", name: "VIKO RAMADANI", password: "8342" },
                { nis: "8349", name: "YUNITA", password: "8349" }
            ],
            "8.2": [
                { nis: "8359", name: "ANNISA LUTHFIYAH", password: "8359" },
                { nis: "8125", name: "ARETHA ELYSIA MANSYUR", password: "8125" },
                { nis: "8134", name: "AULA MIFTAHUL HASANAH", password: "8134" },
                { nis: "8143", name: "AZZAHRA SINTYA AYU SANTIKA", password: "8143" },
                { nis: "8615", name: "DAMARJAYA PRABU WASESO", password: "8615" },
                { nis: "8153", name: "DESTI APRIANI", password: "8153" },
                { nis: "8160", name: "DINY SEPTIYANI", password: "8160" },
                { nis: "8360", name: "ELLYCIA AYUDIA WINARPUTRI", password: "8360" },
                { nis: "8164", name: "EZRA ADJANTHA BIOGENAKBAR", password: "8164" },
                { nis: "8173", name: "FELIS VIRONIKA AMANDA", password: "8173" },
                { nis: "8174", name: "FIKA AFIFATUNNISA", password: "8174" },
                { nis: "8189", name: "HUMAIDI ILMAN NIAMI", password: "8189" },
                { nis: "8201", name: "IRVAN ABDULLAH AL NURI", password: "8201" },
                { nis: "8203", name: "JAMILATA AINU ROHMAH", password: "8203" },
                { nis: "8216", name: "LASMI OKTAVIA", password: "8216" },
                { nis: "8227", name: "M. KHOIRUL ANWAR", password: "8227" },
                { nis: "8235", name: "MELDA INDAH MUKTI", password: "8235" },
                { nis: "8246", name: "MUHAMAD ZAQARIA SIDIQ", password: "8246" },
                { nis: "8268", name: "NAZWA FATIMATUZ ZAHRA", password: "8268" },
                { nis: "8278", name: "NURMAN JAYA PRATAMA", password: "8278" },
                { nis: "8279", name: "OKSA TERIVA HARSONO", password: "8279" },
                { nis: "8280", name: "OKTINA WIRANTI", password: "8280" },
                { nis: "8289", name: "RAHEL CHELSYANA SIDABUKKE", password: "8289" },
                { nis: "8290", name: "RAHMAD DERMAWAN", password: "8290" },
                { nis: "8295", name: "RARA SEKAR ARUM", password: "8295" },
                { nis: "8301", name: "RIDHO KURNIAWAN", password: "8301" },
                { nis: "8302", name: "RIFALDO SAPUTRA", password: "8302" },
                { nis: "8310", name: "RIZKY RAMADHAN", password: "8310" },
                { nis: "8323", name: "SINTA NUR AINI", password: "8323" },
                { nis: "8328", name: "SYAKIRA FS", password: "8328" },
                { nis: "8343", name: "VINO SAPUTRA", password: "8343" },
                { nis: "8356", name: "ZULFA INEZILA PURRY", password: "8356" }
            ],
            "8.3": [
                { nis: "8109", name: "ALVINO", password: "8109" },
                { nis: "8136", name: "AURA SAPUTRI", password: "8136" },
                { nis: "8142", name: "AZZAHRA", password: "8142" },
                { nis: "8146", name: "BELLA ALENA FARICHTA", password: "8146" },
                { nis: "8148", name: "DANANG GALIH PRAKOSO", password: "8148" },
                { nis: "8169", name: "FARA FAUZANA", password: "8169" },
                { nis: "8172", name: "FEBBY DWI SAPUTRI", password: "8172" },
                { nis: "8190", name: "I KOMANG ARJUNA BATISTA", password: "8190" },
                { nis: "8204", name: "JULIO JAFINO SAPUTRA", password: "8204" },
                { nis: "8209", name: "KEYLA ZHABILA HIDAYAT", password: "8209" },
                { nis: "8211", name: "KHOIRUL ILHAM", password: "8211" },
                { nis: "8212", name: "KHOIRUN NISA", password: "8212" },
                { nis: "8228", name: "M. MUHLISIN", password: "8228" },
                { nis: "8239", name: "MUHAMAD ALVINO SAPUTRA", password: "8239" },
                { nis: "8257", name: "MUHAMMAD ZAKKY MIFTAH HULUM", password: "8257" },
                { nis: "8259", name: "MYTHA TRI ARUMI", password: "8259" },
                { nis: "8269", name: "NAZWA KARIMAH", password: "8269" },
                { nis: "8276", name: "NUR' AZIZAH", password: "8276" },
                { nis: "8291", name: "RAHMAD GERY PRASETYA", password: "8291" },
                { nis: "8297", name: "RENATA YOBEL ZEFANYA N", password: "8297" },
                { nis: "8303", name: "RIFKI ADITYA", password: "8303" },
                { nis: "8308", name: "RIZAL ALFIANSAH", password: "8308" },
                { nis: "8311", name: "ROHMATUL AFIFAH", password: "8311" },
                { nis: "8313", name: "SAFATUL AZIZA", password: "8313" },
                { nis: "8314", name: "SAFIRA WULAN ANGGRAINI", password: "8314" },
                { nis: "8316", name: "SAYVIA NAZEILA WILDAN ZANZABIL", password: "8316" },
                { nis: "8326", name: "STYO BIMO PRAYOGO", password: "8326" },
                { nis: "8335", name: "TERESIA ADVENTY", password: "8335" },
                { nis: "8336", name: "TIARA SELFIA NURFIANI", password: "8336" },
                { nis: "8345", name: "WAHYU PUTRI SENA", password: "8345" },
                { nis: "8348", name: "YOSEF ZEIN HALOMOAN", password: "8348" },
                { nis: "8355", name: "ZAKIY SIFTYANO", password: "8355" }
            ],
            "8.4": [
                { nis: "8089", name: "ABELLIA CAHYA AGUSTIN", password: "8089" },
                { nis: "8096", name: "AHMAD AJI FATHULLOH", password: "8096" },
                { nis: "8097", name: "AHMAD JERRY ZACKY ZAMANY", password: "8097" },
                { nis: "8099", name: "AKHEYLA ARZZALIKA", password: "8099" },
                { nis: "8110", name: "AMAR MA'RUF AL ARIF", password: "8110" },
                { nis: "8116", name: "ANINDYA OCTAVIANI", password: "8116" },
                { nis: "8117", name: "ANISA FADILLA", password: "8117" },
                { nis: "8357", name: "AQILLA ZHAAFIRAH HASAN", password: "8357" },
                { nis: "8133", name: "ATIKA ZAHRA LATIFA", password: "8133" },
                { nis: "8137", name: "AUREL DINA LARASATI", password: "8137" },
                { nis: "8149", name: "DEFA PATO PRATAMA", password: "8149" },
                { nis: "8159", name: "DINI AYU AZZAHRA", password: "8159" },
                { nis: "8161", name: "DWI RISMA ALFIANA", password: "8161" },
                { nis: "8166", name: "FAHMI PRANANDHA PRISTIADI", password: "8166" },
                { nis: "8191", name: "I MADE ARTE DWITYA ERLANGGA", password: "8191" },
                { nis: "8206", name: "KASIH DINDA KRISTIAN ANGGRAINI", password: "8206" },
                { nis: "8220", name: "LUQMAN NUR HAKIM", password: "8220" },
                { nis: "8230", name: "M. WILDAN DIMASYQI", password: "8230" },
                { nis: "8240", name: "MUHAMAD ASIFUDDIN", password: "8240" },
                { nis: "8248", name: "MUHAMMAD ADWA AL AFWU", password: "8248" },
                { nis: "8258", name: "MUKHAMAD KRISNA", password: "8258" },
                { nis: "8260", name: "NADA AZHAR AZIZAH", password: "8260" },
                { nis: "8281", name: "OLIVIA FITRIASARI", password: "8281" },
                { nis: "8351", name: "ZAHWA ALIYA", password: "8351" },
                { nis: "8614", name: "REZA ARDIANSYAH", password: "8614" },
                { nis: "8304", name: "RIFKY SYAPUTRA", password: "8304" },
                { nis: "8318", name: "SHAFIYYAH SALSABILA AL HASNA", password: "8318" },
                { nis: "8327", name: "SULTHAN NUR RASYID", password: "8327" },
                { nis: "8331", name: "TAMARA YULIA ASTIANI", password: "8331" },
                { nis: "8332", name: "TAZKIA QOTRUN NADA", password: "8332" },
                { nis: "8338", name: "TRI NOFITA SARI", password: "8338" },
                { nis: "8350", name: "YUSUF MAJID NUR RASIT", password: "8350" }
            ],
            "8.5": [
                { nis: "8090", name: "ABNI AZAINI", password: "8090" },
                { nis: "8092", name: "ADINDA DWIHAPSARI", password: "8092" },
                { nis: "8094", name: "AFIKA HARA SALSABILA", password: "8094" },
                { nis: "8118", name: "ANISA KARISMA PUTRI", password: "8118" },
                { nis: "8120", name: "ANISSA TRI RAMADANI", password: "8120" },
                { nis: "8124", name: "ARDIKA PRATAMA", password: "8124" },
                { nis: "8130", name: "ARUM DWI SASONO", password: "8130" },
                { nis: "8151", name: "DENIS ARGIANTARA", password: "8151" },
                { nis: "8162", name: "EKA VIRLI AULIA", password: "8162" },
                { nis: "8167", name: "FAIZ FARENDRA TAMA", password: "8167" },
                { nis: "8178", name: "GRACEY FATRYY ZAHRAA", password: "8178" },
                { nis: "8185", name: "HARIL SYARIFUDIN", password: "8185" },
                { nis: "8192", name: "I WAYAN DAVID KEVINDRA WINOLA", password: "8192" },
                { nis: "8196", name: "INNAS HANIFAH", password: "8196" },
                { nis: "8205", name: "KAEYSA AFIANA PUTRI", password: "8205" },
                { nis: "8213", name: "KHOLIFAH DWI UTAMI", password: "8213" },
                { nis: "8217", name: "LATIFATUL AZIZAH", password: "8217" },
                { nis: "8218", name: "LATIFATUZAHRA", password: "8218" },
                { nis: "8223", name: "M. ALIF FEBRIAN", password: "8223" },
                { nis: "8242", name: "MUHAMAD FARHAN BAYU AJI", password: "8242" },
                { nis: "8249", name: "MUHAMMAD AHLAN MAULANA", password: "8249" },
                { nis: "8256", name: "MUHAMMAD RIDHO", password: "8256" },
                { nis: "8262", name: "NADIA SILVIANA", password: "8262" },
                { nis: "8266", name: "NATHANIA ANDITA AZZAHARI", password: "8266" },
                { nis: "8272", name: "NIKIZA SELVANI", password: "8272" },
                { nis: "8298", name: "REVANDI YOHANES SITUMORANG", password: "8298" },
                { nis: "8305", name: "RIGKAN BERNATA DIEN", password: "8305" },
                { nis: "8306", name: "RIKI KHOERUL AZAM", password: "8306" },
                { nis: "8312", name: "SABILA ALYA SYAFIRA", password: "8312" },
                { nis: "8324", name: "SKOLASTIKA YOSEPA AMORA", password: "8324" },
                { nis: "8333", name: "TEGAR CARLO MAHARDIKA", password: "8333" },
                { nis: "8347", name: "WULAN RAHMA DEVI", password: "8347" },
                { nis: "8353", name: "ZAKI ANDRYANSYAH", password: "8353" }
            ],
            "8.6": [
                { nis: "8093", name: "ADZKIA NADHIRA ZULFA", password: "8093" },
                { nis: "8098", name: "AHMAD MURROQIB", password: "8098" },
                { nis: "8101", name: "ALENA RAJWA", password: "8101" },
                { nis: "8111", name: "AMELIA RAMADANI", password: "8111" },
                { nis: "8126", name: "ARGA BRAMASTYA", password: "8126" },
                { nis: "8128", name: "ARINA DINA HANIFA", password: "8128" },
                { nis: "8147", name: "CAHAYA APRILIA", password: "8147" },
                { nis: "8152", name: "DENTA KUSUMA MAULANA SINGGIH", password: "8152" },
                { nis: "8154", name: "DESTY SYAHIRA", password: "8154" },
                { nis: "8158", name: "DINDA KARISMA DEWI", password: "8158" },
                { nis: "8177", name: "GHONIYUN IKHWAN NIRWANA", password: "8177" },
                { nis: "8183", name: "HANINDA AULIA RACHMAN", password: "8183" },
                { nis: "8195", name: "INDRI NURMALITA", password: "8195" },
                { nis: "8197", name: "INTAN KURNIA WIJAYANTI", password: "8197" },
                { nis: "8198", name: "IQBAL ASALMA", password: "8198" },
                { nis: "8215", name: "KRISDAYANTI", password: "8215" },
                { nis: "8221", name: "LUTFINA NUR AZIZAH", password: "8221" },
                { nis: "8231", name: "M. ZILDAN PRATAMA", password: "8231" },
                { nis: "8232", name: "MAICKY DESTA HANDALD KANUGRAHAN", password: "8232" },
                { nis: "8243", name: "MUHAMAD PURWANTORO", password: "8243" },
                { nis: "8250", name: "MUHAMMAD AQSHO ALVARIZO", password: "8250" },
                { nis: "8254", name: "MUHAMMAD KAYSHA ALFARUQ BIMA CAKRA", password: "8254" },
                { nis: "8261", name: "NADHEEV ACHMAD ZAHEEN ARIFIAN", password: "8261" },
                { nis: "8263", name: "NADIRA DWI. JB", password: "8263" },
                { nis: "8270", name: "NEYSA FEBY ERVIANA", password: "8270" },
                { nis: "8274", name: "NUR AENI", password: "8274" },
                { nis: "8299", name: "REYA FITRIYANSYAH", password: "8299" },
                { nis: "8307", name: "RILDAN KURNIAWAN", password: "8307" },
                { nis: "8319", name: "SHYFA CALISTA PUTRI", password: "8319" },
                { nis: "8321", name: "SILLVA CAHYA FORTUNA", password: "8321" },
                { nis: "8322", name: "SILVANA ADELIA SARI", password: "8322" },
                { nis: "8334", name: "TEGUH WAHYUDI", password: "8334" }
            ],
            "8.7": [
                { nis: "8102", name: "ALFIAN LUTFIANSYAH", password: "8102" },
                { nis: "8105", name: "ALFIZ IZAM MAULANA", password: "8105" },
                { nis: "8107", name: "ALISA SEPTIANI", password: "8107" },
                { nis: "8121", name: "ANNISA SINTYA SARI", password: "8121" },
                { nis: "8122", name: "AQILA RAYYA HARVITA PUTRI", password: "8122" },
                { nis: "8127", name: "ARGA WINDRIAN PRATAMA", password: "8127" },
                { nis: "8135", name: "AULIA DWI AQVIANTI", password: "8135" },
                { nis: "8139", name: "AYMAY KEYSYA PUTRI", password: "8139" },
                { nis: "8156", name: "DIAN AHMAD SAPUTRA", password: "8156" },
                { nis: "8163", name: "ELEN TERESIYA", password: "8163" },
                { nis: "8171", name: "FATHIR AFDARANI", password: "8171" },
                { nis: "8182", name: "HAND SEBTIAN", password: "8182" },
                { nis: "8358", name: "HANIYA ZAFIRA PUTRI", password: "8358" },
                { nis: "8199", name: "IQBAL DWI PRANATA", password: "8199" },
                { nis: "8225", name: "M. DWI RAHMAD DANU", password: "8225" },
                { nis: "8236", name: "MIFTHAHUL HUDA", password: "8236" },
                { nis: "8252", name: "MUHAMMAD FAWWAZ RAMADHAN", password: "8252" },
                { nis: "8264", name: "NAILA ELSAFIA", password: "8264" },
                { nis: "8265", name: "NAILATUL KHASANAH", password: "8265" },
                { nis: "8267", name: "NAYA SAPHIRA AZZAHRA", password: "8267" },
                { nis: "8271", name: "NIKI AUREL PAERIN", password: "8271" },
                { nis: "8282", name: "POPI INDAH PERMATA SARI", password: "8282" },
                { nis: "8285", name: "PUTU NAFEEZA VIDVAN PUTRA", password: "8285" },
                { nis: "8296", name: "RENATA", password: "8296" },
                { nis: "8300", name: "REZA ANANDA PUTRA", password: "8300" },
                { nis: "8315", name: "SALMA SYAFIIQAH", password: "8315" },
                { nis: "8320", name: "SIFA AULIA", password: "8320" },
                { nis: "8330", name: "TAMADER SINTAMAHARANI", password: "8330" },
                { nis: "8337", name: "TIYAS EVA NADILA", password: "8337" },
                { nis: "8339", name: "TUMORANG HASELL SIANTURI", password: "8339" },
                { nis: "8341", name: "VANEZHA FEBNIKOVA", password: "8341" },
                { nis: "8346", name: "WINDA OKTAVIANI", password: "8346" },
                { nis: "8352", name: "ZAHWA ALIYA PUTRI", password: "8352" }
            ],
            "8.8": [
                { nis: "8095", name: "AGUSTIN RAMADHINA", password: "8095" },
                { nis: "8100", name: "ALDO ALDI VANTARA", password: "8100" },
                { nis: "8108", name: "ALLAN RAHENDRA ILHAM", password: "8108" },
                { nis: "8113", name: "ANGELITA AMELIA SARI", password: "8113" },
                { nis: "8114", name: "ANGGI ANGGRAINI", password: "8114" },
                { nis: "8119", name: "ANISA PUTRI FAJARINI", password: "8119" },
                { nis: "8123", name: "AQSYANI FITRIA", password: "8123" },
                { nis: "8129", name: "ARINA MANASIKANA", password: "8129" },
                { nis: "8141", name: "AYUNI WULANDARI", password: "8141" },
                { nis: "8155", name: "DHIKA NURAHMAD", password: "8155" },
                { nis: "8176", name: "GEZA NOVA ANGGRAINI", password: "8176" },
                { nis: "8180", name: "HAFFI VALENTINA ENZEL", password: "8180" },
                { nis: "8184", name: "HANIP RAMADANI", password: "8184" },
                { nis: "8193", name: "ICKA FEBI MAULANA", password: "8193" },
                { nis: "8194", name: "ILHAM WIDIANSYAH", password: "8194" },
                { nis: "8207", name: "KEISYA ANDARA PUTRI", password: "8207" },
                { nis: "8210", name: "KHANSA ALYA FADHILLA", password: "8210" },
                { nis: "8222", name: "M. AGUNG TRISTAN PERMANA", password: "8222" },
                { nis: "8229", name: "M. RAFAEL LAPASO", password: "8229" },
                { nis: "8241", name: "MUHAMAD BARKAL ILMI", password: "8241" },
                { nis: "8251", name: "MUHAMMAD BAHARUDDIN HABIBIE", password: "8251" },
                { nis: "8255", name: "MUHAMMAD RAFAEL HANTORO", password: "8255" },
                { nis: "8273", name: "NIZAM YUVI PRASETIA", password: "8273" },
                { nis: "8275", name: "NUR ANISA", password: "8275" },
                { nis: "8277", name: "NUR LIYA QISTIYAH", password: "8277" },
                { nis: "8284", name: "PUTRI LIANA SARI", password: "8284" },
                { nis: "8286", name: "RAFA ARIZA SARI", password: "8286" },
                { nis: "8288", name: "RAFFA RAFKI RAMADHAN", password: "8288" },
                { nis: "8292", name: "RAISHA AZ ZAHRA", password: "8292" },
                { nis: "8293", name: "RAMA ADITYA SEPTIANDIKA", password: "8293" },
                { nis: "8317", name: "SEFFI ENJITA HAPSARI", password: "8317" },
                { nis: "8340", name: "VADILA RAHMAWATI", password: "8340" },
                { nis: "8344", name: "VIRJINIA RAHMA DHANIATI", password: "8344" }
            ]
        };

        // Data aplikasi
        let appData = {
            absensi: [],
            tugas: [],
            materi: [],
            nilai: [],
            currentUser: null,
            currentRole: null
        };

        // Data guru
        const guruData = [
            { username: "guru", password: "guru123", nama: "Bapak/Ibu Guru" }
        ];

        // Inisialisasi aplikasi
        document.addEventListener('DOMContentLoaded', function() {
            // Set tanggal default
            const today = new Date().toISOString().split('T')[0];
            document.getElementById('siswaAbsensiDate').value = today;
            document.getElementById('guruAbsensiDate').value = today;
            
            // Cek apakah ada data di URL
            loadDataFromURL();
            
            // Cek apakah user sudah login sebelumnya
            const savedUser = localStorage.getItem('currentUser');
            const savedRole = localStorage.getItem('currentRole');
            
            if (savedUser && savedRole) {
                appData.currentUser = JSON.parse(savedUser);
                appData.currentRole = savedRole;
                showDashboard(savedRole);
            }
        });

        // ==================== FUNGSI LOGIN & LOGOUT ====================

        function selectRole(role) {
            document.querySelectorAll('.role-btn').forEach(btn => {
                btn.classList.remove('active');
            });
            
            event.target.classList.add('active');
            
            if (role === 'siswa') {
                document.getElementById('usernameLabel').textContent = 'NIS';
                document.getElementById('username').placeholder = 'Masukkan NIS';
                document.getElementById('demoInfo').innerHTML = `
                    <strong>Demo Siswa:</strong><br>
                    NIS: <strong>8103</strong><br>
                    Password: <strong>8103</strong>
                `;
            } else {
                document.getElementById('usernameLabel').textContent = 'Username';
                document.getElementById('username').placeholder = 'Masukkan username';
                document.getElementById('demoInfo').innerHTML = `
                    <strong>Login Guru:</strong><br>
                    Silakan hubungi administrator untuk mendapatkan akses.
                `;
            }
        }

        function handleLogin(event) {
            event.preventDefault();
            
            const username = document.getElementById('username').value;
            const password = document.getElementById('password').value;
            const role = document.querySelector('.role-btn.active').getAttribute('onclick').includes('siswa') ? 'siswa' : 'guru';
            
            if (role === 'siswa') {
                let foundSiswa = null;
                let foundKelas = null;
                
                for (const kelas in studentsData) {
                    const siswa = studentsData[kelas].find(s => s.nis === username && s.password === password);
                    if (siswa) {
                        foundSiswa = siswa;
                        foundKelas = kelas;
                        break;
                    }
                }
                
                if (foundSiswa) {
                    appData.currentUser = { 
                        nis: foundSiswa.nis, 
                        nama: foundSiswa.name, 
                        kelas: foundKelas,
                        password: foundSiswa.password
                    };
                    appData.currentRole = role;
                    localStorage.setItem('currentUser', JSON.stringify(appData.currentUser));
                    localStorage.setItem('currentRole', role);
                    showDashboard(role);
                    updateShareUrl();
                } else {
                    alert('NIS atau password salah!');
                }
            } else {
                const guru = guruData.find(g => g.username === username && g.password === password);
                if (guru) {
                    appData.currentUser = guru;
                    appData.currentRole = role;
                    localStorage.setItem('currentUser', JSON.stringify(guru));
                    localStorage.setItem('currentRole', role);
                    showDashboard(role);
                    updateShareUrl();
                } else {
                    alert('Username atau password salah! Silakan hubungi administrator untuk mendapatkan akses.');
                }
            }
        }

        function showDashboard(role) {
            document.getElementById('loginPage').style.display = 'none';
            
            if (role === 'siswa') {
                document.getElementById('dashboardSiswa').style.display = 'block';
                document.getElementById('siswaInfo').textContent = 
                    `${appData.currentUser.nama} - Kelas ${appData.currentUser.kelas}`;
                
                loadTugasSiswa();
                loadMateriSiswa();
                loadNilaiSiswa();
                updateStatsSiswa();
            } else {
                document.getElementById('dashboardGuru').style.display = 'block';
                
                loadAbsensiGuru();
                loadTugasGuru();
                loadMateriGuru();
                loadDataSiswa();
                loadPenilaian();
                updateTotalSiswaCount();
            }
            
            updateShareUrl();
        }

        function logout() {
            appData.currentUser = null;
            appData.currentRole = null;
            localStorage.removeItem('currentUser');
            localStorage.removeItem('currentRole');
            
            document.getElementById('dashboardSiswa').style.display = 'none';
            document.getElementById('dashboardGuru').style.display = 'none';
            document.getElementById('loginPage').style.display = 'flex';
            
            document.getElementById('username').value = '';
            document.getElementById('password').value = '';
        }

        // ==================== FUNGSI TAB & NAVIGASI ====================

        function switchTab(role, tab) {
            document.querySelectorAll(`#${role}-home, #${role}-absensi, #${role}-tugas, #${role}-materi, #${role}-nilai, #${role}-siswa, #${role}-penilaian`).forEach(el => {
                if (el) el.classList.remove('active');
            });
            
            document.getElementById(`${role}-${tab}`).classList.add('active');
            
            document.querySelectorAll(`.tab-btn`).forEach(btn => {
                btn.classList.remove('active');
            });
            
            event.target.classList.add('active');
            
            if (role === 'siswa' && tab === 'tugas') {
                loadTugasSiswa();
            } else if (role === 'siswa' && tab === 'materi') {
                loadMateriSiswa();
            } else if (role === 'siswa' && tab === 'nilai') {
                loadNilaiSiswa();
            } else if (role === 'guru' && tab === 'absensi') {
                loadAbsensiGuru();
            } else if (role === 'guru' && tab === 'tugas') {
                loadTugasGuru();
            } else if (role === 'guru' && tab === 'materi') {
                loadMateriGuru();
            } else if (role === 'guru' && tab === 'siswa') {
                loadDataSiswa();
            } else if (role === 'guru' && tab === 'penilaian') {
                loadPenilaian();
            }
        }

        // ==================== FUNGSI ABSENSI ====================

        let selectedStatus = '';
        function selectStatus(status) {
            selectedStatus = status;
            
            document.querySelectorAll('.status-btn').forEach(btn => {
                btn.classList.remove('active');
            });
            
            event.target.classList.add('active');
        }

        function submitAbsensi() {
            if (!selectedStatus) {
                alert('Pilih status kehadiran terlebih dahulu!');
                return;
            }
            
            const date = document.getElementById('siswaAbsensiDate').value;
            const note = document.getElementById('siswaAbsensiNote').value;
            
            const existingIndex = appData.absensi.findIndex(a => 
                a.nis === appData.currentUser.nis && a.date === date
            );
            
            if (existingIndex !== -1) {
                appData.absensi[existingIndex].status = selectedStatus;
                appData.absensi[existingIndex].note = note;
            } else {
                appData.absensi.push({
                    nis: appData.currentUser.nis,
                    nama: appData.currentUser.nama,
                    kelas: appData.currentUser.kelas,
                    date: date,
                    status: selectedStatus,
                    note: note
                });
            }
            
            alert('Absensi berhasil disimpan!');
            updateShareUrl();
        }

        function loadAbsensiGuru() {
            const kelas = document.getElementById('guruAbsensiKelas').value;
            const date = document.getElementById('guruAbsensiDate').value;
            
            const siswaKelas = studentsData[kelas] || [];
            const tbody = document.getElementById('guruAbsensiBody');
            tbody.innerHTML = '';
            
            siswaKelas.forEach((siswa, index) => {
                const absensi = appData.absensi.find(a => 
                    a.nis === siswa.nis && a.date === date
                );
                
                const status = absensi ? absensi.status : 'belum';
                
                let statusText = '';
                let badgeClass = '';
                
                switch(status) {
                    case 'present':
                        statusText = 'Hadir';
                        badgeClass = 'badge success';
                        break;
                    case 'late':
                        statusText = 'Terlambat';
                        badgeClass = 'badge warning';
                        break;
                    case 'absent':
                        statusText = 'Tidak Hadir';
                        badgeClass = 'badge danger';
                        break;
                    default:
                        statusText = 'Belum Absen';
                        badgeClass = 'badge gray';
                }
                
                tbody.innerHTML += `
                    <tr>
                        <td>${index + 1}</td>
                        <td>${siswa.nis}</td>
                        <td>${siswa.name}</td>
                        <td><span class="${badgeClass}">${statusText}</span></td>
                    </tr>
                `;
            });
            
            updateGuruStats();
        }

        // ==================== FUNGSI TUGAS ====================

        let editingTugasId = null;

        function toggleFormTugas() {
            const form = document.getElementById('formTugas');
            form.style.display = form.style.display === 'none' ? 'block' : 'none';
            
            // Reset form jika tidak dalam mode edit
            if (!editingTugasId) {
                resetFormTugas();
            }
        }

        function resetFormTugas() {
            document.getElementById('tugasTitle').value = '';
            document.getElementById('tugasKelas').value = '8.1';
            document.getElementById('tugasDeadline').value = '';
            document.getElementById('tugasDesc').value = '';
            removeFile();
            editingTugasId = null;
        }

        function saveTugas() {
            const title = document.getElementById('tugasTitle').value;
            const kelas = document.getElementById('tugasKelas').value;
            const deadline = document.getElementById('tugasDeadline').value;
            const desc = document.getElementById('tugasDesc').value;
            
            if (!title || !deadline) {
                alert('Judul dan deadline harus diisi!');
                return;
            }
            
            if (editingTugasId) {
                // Edit tugas yang sudah ada
                const tugasIndex = appData.tugas.findIndex(t => t.id === editingTugasId);
                if (tugasIndex !== -1) {
                    appData.tugas[tugasIndex].title = title;
                    appData.tugas[tugasIndex].kelas = kelas;
                    appData.tugas[tugasIndex].deadline = deadline;
                    appData.tugas[tugasIndex].desc = desc;
                    appData.tugas[tugasIndex].updatedAt = new Date().toISOString();
                }
            } else {
                // Tambah tugas baru
                const newTugas = {
                    id: Date.now().toString(),
                    title: title,
                    kelas: kelas,
                    deadline: deadline,
                    desc: desc,
                    createdAt: new Date().toISOString()
                };
                
                appData.tugas.push(newTugas);
            }
            
            document.getElementById('formTugas').style.display = 'none';
            resetFormTugas();
            loadTugasGuru();
            alert('Tugas berhasil disimpan!');
            updateShareUrl();
        }

        function editTugas(id) {
            const tugas = appData.tugas.find(t => t.id === id);
            if (!tugas) return;
            
            document.getElementById('tugasTitle').value = tugas.title;
            document.getElementById('tugasKelas').value = tugas.kelas;
            document.getElementById('tugasDeadline').value = tugas.deadline;
            document.getElementById('tugasDesc').value = tugas.desc || '';
            
            editingTugasId = id;
            document.getElementById('formTugas').style.display = 'block';
        }

        function deleteTugas(id) {
            if (confirm('Hapus tugas ini?')) {
                appData.tugas = appData.tugas.filter(t => t.id !== id);
                loadTugasGuru();
                updateShareUrl();
            }
        }

        function loadTugasGuru() {
            const container = document.getElementById('guruTugasList');
            container.innerHTML = '';
            
            if (appData.tugas.length === 0) {
                container.innerHTML = '<p style="text-align: center; padding: 20px; color: #666;">Belum ada tugas yang dibuat.</p>';
                return;
            }
            
            const sortedTugas = [...appData.tugas].sort((a, b) => 
                new Date(b.createdAt) - new Date(a.createdAt)
            );
            
            sortedTugas.forEach(tugas => {
                const deadline = new Date(tugas.deadline);
                const now = new Date();
                const isOverdue = deadline < now;
                
                container.innerHTML += `
                    <div class="materi-item">
                        <div class="materi-header">
                            <div>
                                <h3 style="margin: 0 0 5px 0;">${tugas.title}</h3>
                                <p style="margin: 0; color: #666;">Kelas: ${tugas.kelas === 'all' ? 'Semua Kelas' : tugas.kelas} | Deadline: ${formatDate(deadline)}</p>
                            </div>
                            <div class="materi-actions">
                                <button class="btn-warning" onclick="editTugas('${tugas.id}')">
                                    <i class="fas fa-edit"></i> Edit
                                </button>
                                <button class="btn-danger" onclick="deleteTugas('${tugas.id}')">
                                    <i class="fas fa-trash"></i> Hapus
                                </button>
                            </div>
                        </div>
                        ${tugas.desc ? `<p style="margin: 10px 0;">${tugas.desc}</p>` : ''}
                        ${isOverdue ? `<span class="badge danger">Terlambat</span>` : `<span class="badge success">Aktif</span>`}
                    </div>
                `;
            });
            
            updateGuruStats();
        }

        function loadTugasSiswa() {
            const container = document.getElementById('siswaTugasList');
            container.innerHTML = '';
            
            const tugasSiswa = appData.tugas.filter(t => 
                t.kelas === 'all' || t.kelas === appData.currentUser.kelas
            );
            
            if (tugasSiswa.length === 0) {
                container.innerHTML = '<p style="text-align: center; padding: 20px; color: #666;">Belum ada tugas yang tersedia.</p>';
                return;
            }
            
            const sortedTugas = [...tugasSiswa].sort((a, b) => 
                new Date(a.deadline) - new Date(b.deadline)
            );
            
            sortedTugas.forEach(tugas => {
                const deadline = new Date(tugas.deadline);
                const now = new Date();
                const isOverdue = deadline < now;
                const timeLeft = deadline - now;
                const daysLeft = Math.ceil(timeLeft / (1000 * 60 * 60 * 24));
                
                let statusText = '';
                let statusClass = '';
                
                if (isOverdue) {
                    statusText = 'Terlambat';
                    statusClass = 'badge danger';
                } else if (daysLeft <= 1) {
                    statusText = 'Batas waktu hampir habis';
                    statusClass = 'badge warning';
                } else {
                    statusText = `${daysLeft} hari lagi`;
                    statusClass = 'badge success';
                }
                
                container.innerHTML += `
                    <div class="materi-item">
                        <div class="materi-header">
                            <div>
                                <h3 style="margin: 0 0 5px 0;">${tugas.title}</h3>
                                <p style="margin: 0; color: #666;">Deadline: ${formatDate(deadline)}</p>
                            </div>
                            <div class="materi-actions">
                                <span class="${statusClass}">${statusText}</span>
                                <button class="btn-primary" onclick="openTugasModal('${tugas.id}')">
                                    <i class="fas fa-pencil-alt"></i> Kerjakan
                                </button>
                            </div>
                        </div>
                        ${tugas.desc ? `<p style="margin: 10px 0;">${tugas.desc}</p>` : ''}
                    </div>
                `;
            });
        }

        // ==================== FUNGSI MATERI ====================

        let editingMateriId = null;

        function toggleFormMateri() {
            const form = document.getElementById('formMateri');
            form.style.display = form.style.display === 'none' ? 'block' : 'none';
            
            // Reset form jika tidak dalam mode edit
            if (!editingMateriId) {
                resetFormMateri();
            }
        }

        function resetFormMateri() {
            document.getElementById('materiTitle').value = '';
            document.getElementById('materiKelas').value = '8.1';
            document.getElementById('materiDesc').value = '';
            removeMateriFile();
            editingMateriId = null;
        }

        function saveMateri() {
            const title = document.getElementById('materiTitle').value;
            const kelas = document.getElementById('materiKelas').value;
            const desc = document.getElementById('materiDesc').value;
            
            if (!title) {
                alert('Judul materi harus diisi!');
                return;
            }
            
            if (editingMateriId) {
                // Edit materi yang sudah ada
                const materiIndex = appData.materi.findIndex(m => m.id === editingMateriId);
                if (materiIndex !== -1) {
                    appData.materi[materiIndex].title = title;
                    appData.materi[materiIndex].kelas = kelas;
                    appData.materi[materiIndex].desc = desc;
                    appData.materi[materiIndex].updatedAt = new Date().toISOString();
                }
            } else {
                // Tambah materi baru
                const newMateri = {
                    id: Date.now().toString(),
                    title: title,
                    kelas: kelas,
                    desc: desc,
                    createdAt: new Date().toISOString()
                };
                
                appData.materi.push(newMateri);
            }
            
            document.getElementById('formMateri').style.display = 'none';
            resetFormMateri();
            loadMateriGuru();
            alert('Materi berhasil disimpan!');
            updateShareUrl();
        }

        function editMateri(id) {
            const materi = appData.materi.find(m => m.id === id);
            if (!materi) return;
            
            document.getElementById('materiTitle').value = materi.title;
            document.getElementById('materiKelas').value = materi.kelas;
            document.getElementById('materiDesc').value = materi.desc || '';
            
            editingMateriId = id;
            document.getElementById('formMateri').style.display = 'block';
        }

        function deleteMateri(id) {
            if (confirm('Hapus materi ini?')) {
                appData.materi = appData.materi.filter(m => m.id !== id);
                loadMateriGuru();
                updateShareUrl();
            }
        }

        function loadMateriGuru() {
            const container = document.getElementById('guruMateriList');
            container.innerHTML = '';
            
            if (appData.materi.length === 0) {
                container.innerHTML = '<p style="text-align: center; padding: 20px; color: #666;">Belum ada materi yang dibuat.</p>';
                return;
            }
            
            const sortedMateri = [...appData.materi].sort((a, b) => 
                new Date(b.createdAt) - new Date(a.createdAt)
            );
            
            sortedMateri.forEach(materi => {
                container.innerHTML += `
                    <div class="materi-item">
                        <div class="materi-header">
                            <div>
                                <h3 style="margin: 0 0 5px 0;">${materi.title}</h3>
                                <p style="margin: 0; color: #666;">Kelas: ${materi.kelas === 'all' ? 'Semua Kelas' : materi.kelas} | Dibuat: ${formatDate(new Date(materi.createdAt))}</p>
                            </div>
                            <div class="materi-actions">
                                <button class="btn-warning" onclick="editMateri('${materi.id}')">
                                    <i class="fas fa-edit"></i> Edit
                                </button>
                                <button class="btn-danger" onclick="deleteMateri('${materi.id}')">
                                    <i class="fas fa-trash"></i> Hapus
                                </button>
                            </div>
                        </div>
                        ${materi.desc ? `<p style="margin: 10px 0;">${materi.desc}</p>` : ''}
                    </div>
                `;
            });
            
            updateGuruStats();
        }

        function loadMateriSiswa() {
            const container = document.getElementById('siswaMateriList');
            container.innerHTML = '';
            
            const materiSiswa = appData.materi.filter(m => 
                m.kelas === 'all' || m.kelas === appData.currentUser.kelas
            );
            
            if (materiSiswa.length === 0) {
                container.innerHTML = '<p style="text-align: center; padding: 20px; color: #666;">Belum ada materi yang tersedia.</p>';
                return;
            }
            
            const sortedMateri = [...materiSiswa].sort((a, b) => 
                new Date(b.createdAt) - new Date(a.createdAt)
            );
            
            sortedMateri.forEach(materi => {
                container.innerHTML += `
                    <div class="materi-item">
                        <div class="materi-header">
                            <div>
                                <h3 style="margin: 0 0 5px 0;">${materi.title}</h3>
                                <p style="margin: 0; color: #666;">Dibuat: ${formatDate(new Date(materi.createdAt))}</p>
                            </div>
                        </div>
                        ${materi.desc ? `<p style="margin: 10px 0;">${materi.desc}</p>` : ''}
                        <div class="materi-actions">
                            <button class="btn-primary">
                                <i class="fas fa-download"></i> Unduh
                            </button>
                            <button class="btn-success">
                                <i class="fas fa-eye"></i> Lihat
                            </button>
                        </div>
                    </div>
                `;
            });
        }

        // ==================== FUNGSI DATA SISWA ====================

        function loadDataSiswa() {
            const kelas = document.getElementById('guruSiswaKelas').value;
            const siswaKelas = studentsData[kelas] || [];
            const tbody = document.getElementById('guruSiswaBody');
            tbody.innerHTML = '';
            
            siswaKelas.forEach((siswa, index) => {
                const absensiSiswa = appData.absensi.filter(a => a.nis === siswa.nis);
                const totalAbsensi = absensiSiswa.length;
                const hadirCount = absensiSiswa.filter(a => a.status === 'present').length;
                const kehadiran = totalAbsensi > 0 ? Math.round((hadirCount / totalAbsensi) * 100) : 0;
                
                tbody.innerHTML += `
                    <tr>
                        <td>${index + 1}</td>
                        <td>${siswa.nis}</td>
                        <td>${siswa.name}</td>
                        <td>${kelas}</td>
                        <td>${kehadiran}%</td>
                        <td>85</td>
                    </tr>
                `;
            });
        }

        // ==================== FUNGSI PENILAIAN ====================

        function loadPenilaian() {
            const kelas = document.getElementById('penilaianKelas').value;
            const tugasId = document.getElementById('penilaianTugas').value;
            
            const tugasSelect = document.getElementById('penilaianTugas');
            tugasSelect.innerHTML = '<option value="">Pilih Tugas</option>';
            
            appData.tugas.forEach(tugas => {
                if (tugas.kelas === kelas || tugas.kelas === 'all') {
                    tugasSelect.innerHTML += `<option value="${tugas.id}">${tugas.title}</option>`;
                }
            });
            
            if (!tugasId) {
                document.getElementById('guruPenilaianBody').innerHTML = '<tr><td colspan="7" style="text-align: center; padding: 20px;">Pilih tugas terlebih dahulu</td></tr>';
                return;
            }
            
            const siswaKelas = studentsData[kelas] || [];
            const tbody = document.getElementById('guruPenilaianBody');
            tbody.innerHTML = '';
            
            siswaKelas.forEach((siswa, index) => {
                const nilaiData = appData.nilai.find(n => 
                    n.tugasId === tugasId && n.nis === siswa.nis
                );
                
                const status = nilaiData ? 'Dinilai' : 'Belum Dinilai';
                const nilai = nilaiData ? nilaiData.nilai : '';
                const komentar = nilaiData ? nilaiData.komentar : '';
                
                tbody.innerHTML += `
                    <tr>
                        <td>${index + 1}</td>
                        <td>${siswa.nis}</td>
                        <td>${siswa.name}</td>
                        <td><span class="badge ${nilaiData ? 'success' : 'warning'}">${status}</span></td>
                        <td>
                            <input type="number" class="nilai-input" id="nilai-${siswa.nis}" 
                                   value="${nilai}" min="0" max="100" 
                                   onchange="updateNilai('${tugasId}', '${siswa.nis}')">
                        </td>
                        <td>
                            <input type="text" id="komentar-${siswa.nis}" 
                                   value="${komentar}" placeholder="Komentar..."
                                   onchange="updateNilai('${tugasId}', '${siswa.nis}')">
                        </td>
                        <td>
                            <button class="btn-primary" onclick="openNilaiModal('${tugasId}', '${siswa.nis}')">
                                <i class="fas fa-edit"></i> Detail
                            </button>
                        </td>
                    </tr>
                `;
            });
        }

        function updateNilai(tugasId, nis) {
            const nilai = document.getElementById(`nilai-${nis}`).value;
            const komentar = document.getElementById(`komentar-${nis}`).value;
            
            const existingIndex = appData.nilai.findIndex(n => 
                n.tugasId === tugasId && n.nis === nis
            );
            
            if (existingIndex !== -1) {
                appData.nilai[existingIndex].nilai = nilai;
                appData.nilai[existingIndex].komentar = komentar;
                appData.nilai[existingIndex].updatedAt = new Date().toISOString();
            } else {
                appData.nilai.push({
                    tugasId: tugasId,
                    nis: nis,
                    nilai: nilai,
                    komentar: komentar,
                    createdAt: new Date().toISOString(),
                    updatedAt: new Date().toISOString()
                });
            }
            
            updateShareUrl();
        }

        function loadNilaiSiswa() {
            const container = document.getElementById('siswaNilaiList');
            const nis = appData.currentUser.nis;
            const nilaiSiswa = appData.nilai.filter(n => n.nis === nis);
            
            if (nilaiSiswa.length === 0) {
                container.innerHTML = '<p style="text-align: center; padding: 20px; color: #666;">Belum ada nilai yang tersedia.</p>';
                return;
            }
            
            let html = '<div class="stats-grid" style="margin-bottom: 20px;">';
            
            const totalNilai = nilaiSiswa.reduce((sum, n) => sum + parseInt(n.nilai || 0), 0);
            const rataRata = nilaiSiswa.length > 0 ? Math.round(totalNilai / nilaiSiswa.length) : 0;
            const nilaiTertinggi = Math.max(...nilaiSiswa.map(n => parseInt(n.nilai || 0)));
            const nilaiTerendah = Math.min(...nilaiSiswa.map(n => parseInt(n.nilai || 0)));
            
            html += `
                <div class="stat-card blue">
                    <div class="label">Rata-rata</div>
                    <div class="value">${rataRata}</div>
                </div>
                <div class="stat-card green">
                    <div class="label">Tertinggi</div>
                    <div class="value">${nilaiTertinggi}</div>
                </div>
                <div class="stat-card orange">
                    <div class="label">Terendah</div>
                    <div class="value">${nilaiTerendah}</div>
                </div>
            </div>`;
            
            html += '<h3 style="margin-bottom: 15px;">Detail Nilai</h3>';
            
            nilaiSiswa.forEach(nilai => {
                const tugas = appData.tugas.find(t => t.id === nilai.tugasId);
                if (!tugas) return;
                
                const progress = parseInt(nilai.nilai || 0);
                
                html += `
                    <div class="materi-item">
                        <div class="materi-header">
                            <div>
                                <h3 style="margin: 0 0 5px 0;">${tugas.title}</h3>
                                <p style="margin: 0; color: #666;">Nilai: <strong>${nilai.nilai || 'Belum dinilai'}</strong></p>
                            </div>
                            <div class="materi-actions">
                                <span class="badge ${progress >= 80 ? 'success' : progress >= 60 ? 'warning' : 'danger'}">
                                    ${progress >= 80 ? 'Baik' : progress >= 60 ? 'Cukup' : 'Perlu Perbaikan'}
                                </span>
                            </div>
                        </div>
                        ${nilai.komentar ? `<p style="margin: 10px 0;"><strong>Komentar:</strong> ${nilai.komentar}</p>` : ''}
                        <div class="progress-bar">
                            <div class="progress-fill" style="width: ${progress}%"></div>
                        </div>
                        <p style="text-align: center; margin: 5px 0; font-size: 12px; color: #666;">${progress}%</p>
                    </div>
                `;
            });
            
            container.innerHTML = html;
        }

        // ==================== FUNGSI STATISTIK ====================

        function updateStatsSiswa() {
            const nis = appData.currentUser.nis;
            
            const absensiSiswa = appData.absensi.filter(a => a.nis === nis);
            const totalAbsensi = absensiSiswa.length;
            const hadirCount = absensiSiswa.filter(a => a.status === 'present').length;
            const kehadiran = totalAbsensi > 0 ? Math.round((hadirCount / totalAbsensi) * 100) : 0;
            
            const tugasSiswa = appData.tugas.filter(t => 
                t.kelas === 'all' || t.kelas === appData.currentUser.kelas
            );
            const tugasDikumpulkan = appData.nilai.filter(n => 
                n.nis === nis && tugasSiswa.some(t => t.id === n.tugasId)
            ).length;
            
            const nilaiSiswa = appData.nilai.filter(n => n.nis === nis);
            const totalNilai = nilaiSiswa.reduce((sum, n) => sum + parseInt(n.nilai || 0), 0);
            const rataRata = nilaiSiswa.length > 0 ? Math.round(totalNilai / nilaiSiswa.length) : 0;
            
            document.getElementById('siswaKehadiran').textContent = `${kehadiran}%`;
            document.getElementById('siswaTugasSelesai').textContent = `${tugasDikumpulkan}/${tugasSiswa.length}`;
            document.getElementById('siswaNilaiRata').textContent = rataRata;
        }

        function updateGuruStats() {
            const date = document.getElementById('guruAbsensiDate').value;
            
            const presentCount = appData.absensi.filter(a => 
                a.date === date && a.status === 'present'
            ).length;
            
            document.getElementById('guruPresentCount').textContent = presentCount;
            
            const activeTasks = appData.tugas.filter(t => {
                const deadline = new Date(t.deadline);
                const now = new Date();
                return deadline > now;
            }).length;
            
            document.getElementById('guruActiveTasks').textContent = activeTasks;
            
            document.getElementById('guruMateriCount').textContent = appData.materi.length;
        }

        function updateTotalSiswaCount() {
            let totalSiswa = 0;
            for (const kelas in studentsData) {
                totalSiswa += studentsData[kelas].length;
            }
            document.getElementById('totalSiswaCount').textContent = totalSiswa;
        }

        // ==================== FUNGSI SHARING URL ====================

        function updateShareUrl() {
            const dataToSave = {
                absensi: appData.absensi,
                tugas: appData.tugas,
                materi: appData.materi,
                nilai: appData.nilai
            };
            
            const jsonData = JSON.stringify(dataToSave);
            const compressedData = LZString.compressToEncodedURIComponent(jsonData);
            
            const baseUrl = window.location.href.split('?')[0];
            const shareUrl = `${baseUrl}?data=${compressedData}`;
            
            document.getElementById('shareUrl').value = shareUrl;
            document.getElementById('shareUrlGuru').value = shareUrl;
            
            window.history.replaceState(null, null, `?data=${compressedData}`);
        }

        function loadDataFromURL() {
            const urlParams = new URLSearchParams(window.location.search);
            const dataParam = urlParams.get('data');
            
            if (dataParam) {
                try {
                    const jsonData = LZString.decompressFromEncodedURIComponent(dataParam);
                    
                    if (jsonData) {
                        const parsedData = JSON.parse(jsonData);
                        
                        if (parsedData.absensi) appData.absensi = parsedData.absensi;
                        if (parsedData.tugas) appData.tugas = parsedData.tugas;
                        if (parsedData.materi) appData.materi = parsedData.materi;
                        if (parsedData.nilai) appData.nilai = parsedData.nilai;
                        
                        console.log('Data berhasil dimuat dari URL');
                    }
                } catch (error) {
                    console.error('Error loading data from URL:', error);
                }
            }
        }

        function copyShareUrl() {
            const urlInput = document.getElementById('shareUrl') || document.getElementById('shareUrlGuru');
            urlInput.select();
            document.execCommand('copy');
            
            const copyBtn = event.target.closest('.copy-btn');
            const originalText = copyBtn.innerHTML;
            
            copyBtn.innerHTML = '<i class="fas fa-check"></i> URL Disalin!';
            copyBtn.classList.add('copied');
            
            setTimeout(() => {
                copyBtn.innerHTML = originalText;
                copyBtn.classList.remove('copied');
            }, 2000);
        }

        function shareToWhatsApp() {
            const url = document.getElementById('shareUrl').value;
            const text = `Halo! Saya ingin berbagi data pembelajaran dengan Anda:\n${url}`;
            const whatsappUrl = `https://wa.me/?text=${encodeURIComponent(text)}`;
            window.open(whatsappUrl, '_blank');
        }

        function shareToTelegram() {
            const url = document.getElementById('shareUrl').value;
            const text = `Halo! Saya ingin berbagi data pembelajaran dengan Anda:\n${url}`;
            const telegramUrl = `https://t.me/share/url?url=${encodeURIComponent(url)}&text=${encodeURIComponent(text)}`;
            window.open(telegramUrl, '_blank');
        }

        // ==================== FUNGSI BANTUAN ====================

        function formatDate(date) {
            return date.toLocaleDateString('id-ID', {
                weekday: 'long',
                year: 'numeric',
                month: 'long',
                day: 'numeric',
                hour: '2-digit',
                minute: '2-digit'
            });
        }

        function handleFileSelect(event) {
            const file = event.target.files[0];
            if (file) {
                const fileSize = (file.size / 1024 / 1024).toFixed(2);
                document.getElementById('fileName').textContent = file.name;
                document.getElementById('fileSize').textContent = `${fileSize} MB`;
                document.getElementById('filePreview').style.display = 'block';
                
                const fileIcon = document.getElementById('fileIcon');
                if (file.type.includes('pdf')) {
                    fileIcon.className = 'fas fa-file-pdf';
                    fileIcon.style.color = '#ef4444';
                } else if (file.type.includes('word') || file.type.includes('document')) {
                    fileIcon.className = 'fas fa-file-word';
                    fileIcon.style.color = '#3b82f6';
                } else if (file.type.includes('powerpoint') || file.type.includes('presentation')) {
                    fileIcon.className = 'fas fa-file-powerpoint';
                    fileIcon.style.color = '#f59e0b';
                } else {
                    fileIcon.className = 'fas fa-file';
                    fileIcon.style.color = '#6b7280';
                }
            }
        }

        function handleMateriFileSelect(event) {
            const file = event.target.files[0];
            if (file) {
                const fileSize = (file.size / 1024 / 1024).toFixed(2);
                document.getElementById('materiFileName').textContent = file.name;
                document.getElementById('materiFileSize').textContent = `${fileSize} MB`;
                document.getElementById('materiFilePreview').style.display = 'block';
                
                const fileIcon = document.getElementById('materiFileIcon');
                if (file.type.includes('pdf')) {
                    fileIcon.className = 'fas fa-file-pdf';
                    fileIcon.style.color = '#ef4444';
                } else if (file.type.includes('word') || file.type.includes('document')) {
                    fileIcon.className = 'fas fa-file-word';
                    fileIcon.style.color = '#3b82f6';
                } else if (file.type.includes('powerpoint') || file.type.includes('presentation')) {
                    fileIcon.className = 'fas fa-file-powerpoint';
                    fileIcon.style.color = '#f59e0b';
                } else if (file.type.includes('image')) {
                    fileIcon.className = 'fas fa-file-image';
                    fileIcon.style.color = '#10b981';
                } else {
                    fileIcon.className = 'fas fa-file';
                    fileIcon.style.color = '#6b7280';
                }
            }
        }

        function removeFile() {
            document.getElementById('tugasFile').value = '';
            document.getElementById('filePreview').style.display = 'none';
        }

        function removeMateriFile() {
            document.getElementById('materiFile').value = '';
            document.getElementById('materiFilePreview').style.display = 'none';
        }

        // Fungsi untuk modal tugas
        function openTugasModal(tugasId) {
            document.getElementById('tugasModal').style.display = 'flex';
        }

        function closeTugasModal() {
            document.getElementById('tugasModal').style.display = 'none';
        }

        // Fungsi untuk modal nilai
        function openNilaiModal(tugasId, nis) {
            const nilaiData = appData.nilai.find(n => 
                n.tugasId === tugasId && n.nis === nis
            );
            
            if (nilaiData) {
                document.getElementById('modalNilai').value = nilaiData.nilai;
                document.getElementById('modalKomentar').value = nilaiData.komentar;
            } else {
                document.getElementById('modalNilai').value = '';
                document.getElementById('modalKomentar').value = '';
            }
            
            document.getElementById('nilaiModal').style.display = 'flex';
        }

        function closeNilaiModal() {
            document.getElementById('nilaiModal').style.display = 'none';
        }
    </script>
</body>
</html>
