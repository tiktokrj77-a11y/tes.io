<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>PulsaKu PPOB - Google Play Store</title>
<link href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;500;700&display=swap" rel="stylesheet">
<style>
/* Reset dan Font Dasar */
body {
    font-family: 'Roboto', sans-serif;
    margin: 0;
    padding: 0;
    background-color: #f1f3f4;
    color: #202124;
    font-size: 14px;
}

/* Container utama meniru lebar dan padding Play Store */
.container {
    max-width: 600px; /* Lebar umum tampilan seluler/play store */
    margin: 0 auto;
    background-color: #fff;
    padding: 16px;
    box-shadow: 0 1px 2px rgba(0,0,0,0.05); /* Sedikit bayangan */
}

/* Bagian Info Aplikasi (Header) */
.app-header {
    display: flex;
    align-items: flex-start;
    gap: 16px;
    margin-bottom: 16px;
}

.app-icon {
    width: 64px; /* Ukuran ikon di Play Store */
    height: 64px;
    border-radius: 12px;
    object-fit: cover;
    flex-shrink: 0;
    box-shadow: 0 1px 3px rgba(0, 0, 0, 0.1);
}

.app-details {
    display: flex;
    flex-direction: column;
}

.app-name {
    font-size: 22px; /* Ukuran font lebih besar untuk nama aplikasi */
    font-weight: 500;
    margin: 0;
    line-height: 1.2;
}

.app-developer {
    font-size: 14px;
    color: #5f6368;
    margin-top: 2px;
}

.app-category {
    font-size: 12px;
    color: #5f6368;
    margin-top: 0px;
}

/* Bagian Statstik Ringkasan (Rating, Download, Rating Usia) */
.summary-stats {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 20px;
    color: #5f6368;
}

.stat-item {
    display: flex;
    flex-direction: column;
    align-items: center;
    text-align: center;
    padding: 0 8px; /* Padding untuk memisahkan item */
    flex: 1; /* Agar membagi ruang secara merata */
}

.stat-value {
    font-size: 16px;
    font-weight: 500;
    color: #202124;
}

.stat-label {
    font-size: 12px;
    margin-top: 2px;
}

.stat-item:nth-child(2) {
    border-left: 1px solid #dadce0;
    border-right: 1px solid #dadce0;
}

/* Tombol Install */
.install-section {
    margin-bottom: 16px;
}

.install-button {
    display: block;
    width: 100%;
    padding: 12px 0;
    background-color: #00874e; /* Warna hijau khas Play Store */
    color: #fff;
    text-align: center;
    border-radius: 24px;
    font-size: 16px;
    font-weight: 500;
    text-decoration: none;
    cursor: pointer;
    box-shadow: 0 1px 2px rgba(0,0,0,0.1);
    transition: background-color 0.15s;
}

.install-button:hover {
    background-color: #006b3e;
}

/* Tombol Share dan Add to Wishlist */
.secondary-actions {
    display: flex;
    justify-content: space-evenly;
    align-items: center;
    padding: 12px 0;
    margin-bottom: 16px;
    border-top: 1px solid #dadce0;
    border-bottom: 1px solid #dadce0;
}

.action-button {
    display: flex;
    align-items: center;
    gap: 6px;
    color: #00874e;
    font-size: 14px;
    font-weight: 500;
    cursor: pointer;
}

/* Screenshot Section */
.screenshots-section {
    overflow-x: auto;
    white-space: nowrap;
    margin: 16px 0;
    padding-bottom: 8px;
    -webkit-overflow-scrolling: touch;
    scrollbar-width: none; /* Firefox */
}

.screenshots-section::-webkit-scrollbar {
    display: none; /* Chrome, Safari, Opera */
}

.screenshot-image {
    height: 100px; /* Tinggi screenshot seperti di gambar */
    width: auto;
    border-radius: 8px;
    margin-right: 8px;
    display: inline-block;
    object-fit: cover;
    box-shadow: 0 1px 3px rgba(0, 0, 0, 0.1);
}

/* Bagian Konten (Tentang, Keamanan, Ulasan) */
.content-section {
    padding: 16px 0 0;
    border-bottom: 1px solid #dadce0;
    margin-bottom: 0;
}

.section-title {
    display: flex;
    justify-content: space-between;
    align-items: center;
    font-size: 16px;
    font-weight: 500;
    color: #202124;
    cursor: pointer;
    padding-bottom: 16px;
}

.section-title span {
    color: #5f6368; /* Warna ikon panah */
    font-size: 20px;
}

.section-body {
    padding-bottom: 16px;
    color: #5f6368;
    line-height: 1.5;
}

/* Detail Keamanan Data */
.security-detail {
    display: flex;
    align-items: flex-start;
    gap: 12px;
    margin-top: 10px;
}

.security-detail-text {
    flex-grow: 1;
}

.security-detail-text a {
    color: #00874e;
    text-decoration: none;
    font-weight: 500;
}

.security-icon {
    font-size: 18px; /* Ukuran ikon */
    color: #5f6368;
    line-height: 1.5;
}

.security-link-more {
    color: #00874e;
    font-weight: 500;
    text-decoration: none;
    display: block;
    margin-top: 10px;
}

/* Rating dan Ulasan */
.ratings-section {
    padding: 16px 0 0;
    border-bottom: 1px solid #dadce0;
    margin-bottom: 0;
}

.rating-summary {
    display: flex;
    align-items: center;
    gap: 16px;
    margin-bottom: 8px;
}

.main-rating {
    font-size: 40px;
    font-weight: 400;
    line-height: 1;
}

.total-reviews {
    font-size: 12px;
    color: #5f6368;
    margin-top: 2px;
}

.rating-chart {
    flex-grow: 1;
}

.chart-bar-row {
    display: flex;
    align-items: center;
    margin-bottom: 2px;
}

.star-count {
    width: 10px;
    font-size: 12px;
    color: #5f6368;
    margin-right: 4px;
}

.chart-bar-bg {
    flex-grow: 1;
    height: 8px;
    background-color: #e8eaed;
    border-radius: 4px;
    overflow: hidden;
}

.chart-bar-fill {
    height: 100%;
    background-color: #00874e;
    border-radius: 4px;
}

.review-item {
    padding: 16px 0;
    border-top: 1px solid #dadce0;
}

.review-item:first-of-type {
    border-top: none;
}

.review-header {
    display: flex;
    align-items: center;
    gap: 12px;
    margin-bottom: 8px;
    position: relative;
}

.reviewer-icon {
    width: 32px;
    height: 32px;
    border-radius: 50%;
    background-color: #dadce0; /* Placeholder warna abu-abu */
    display: flex;
    justify-content: center;
    align-items: center;
    color: #fff;
    font-size: 16px;
    font-weight: 500;
}

.reviewer-name {
    font-size: 14px;
    font-weight: 500;
}

.review-date {
    font-size: 12px;
    color: #5f6368;
}

.review-menu-icon {
    position: absolute;
    right: 0;
    font-size: 20px;
    color: #5f6368;
    cursor: pointer;
}

.review-rating-stars {
    color: #00874e;
    font-size: 14px;
    margin-bottom: 4px;
}

.review-text {
    font-size: 14px;
    line-height: 1.4;
    color: #202124;
    margin-bottom: 10px;
}

.review-helpfulness {
    display: flex;
    align-items: center;
    gap: 12px;
    color: #5f6368;
    font-size: 12px;
    margin-top: 10px;
}

.helpfulness-actions {
    display: flex;
    gap: 8px;
}

.helpfulness-btn {
    padding: 6px 16px;
    border: 1px solid #dadce0;
    border-radius: 16px;
    color: #202124;
    font-weight: 500;
    cursor: pointer;
}

.helpfulness-btn.active {
    background-color: #f0f0f0;
}

/* Teks Lanjut Ulasan */
.review-all-link {
    display: block;
    color: #00874e;
    font-weight: 500;
    text-align: center;
    padding: 16px 0;
    cursor: pointer;
}

/* Bagian Ulasan Tambahan */
.hidden-reviews {
    display: none; /* Sembunyikan secara default */
}

/* Bagian Paling Bawah (What's New) */
.new-features-section {
    padding: 16px 0;
}

.new-features-section .section-title {
    padding-bottom: 0;
}

.hidden-content {
    display: none;
}

/* Tambahkan Material Icons untuk mendukung ikon */
@font-face {
  font-family: 'Material Icons';
  font-style: normal;
  font-weight: 400;
  src: url(https://fonts.gstatic.com/s/materialicons/v140/flUhRq6tzZclQEJ-Vdg-IuiaDsNcIhQ8tQ.woff2) format('woff2');
}

.material-icons {
  font-family: 'Material Icons';
  font-weight: normal;
  font-style: normal;
  font-size: 24px;  /* Ukuran default */
  line-height: 1;
  letter-spacing: normal;
  text-transform: none;
  display: inline-block;
  white-space: nowrap;
  word-wrap: normal;
  direction: ltr;
  -webkit-font-feature-settings: 'liga';
  -webkit-font-smoothing: antialiased;
}
</style>
</head>
<body>

<div class="container">

    <div class="app-header">
        <img class="app-icon" src="https://iili.io/KEEhrge.jpg" alt="Icon PulsaKu PPOB">
        <div class="app-details">
            <h1 class="app-name">PulsaKu PPOB</h1>
            <p class="app-developer">Teamku Developer</p>
            <p class="app-category">Hiburan & Utilitas</p>
        </div>
    </div>

    <div class="summary-stats">
        <div class="stat-item">
            <div class="stat-value">4.8 ⭐</div>
            <small class="stat-label">1 rb ulasan</small>
        </div>
        <div class="stat-item">
            <div class="stat-value">10 rb+</div>
            <small class="stat-label">Download</small>
        </div>
        <div class="stat-item">
            <div class="stat-value">3+</div>
            <small class="stat-label">Rating Konten</small>
        </div>
    </div>

    <div class="install-section">
        <a href="https://app.bukaolshop.com/toko/pulsaku09" class="install-button" target="_blank">Instal</a>
    </div>

    <div class="secondary-actions">
        <div class="action-button" id="shareButton">
            <span class="material-icons" style="font-size: 20px;">share</span>
            Bagikan
        </div>
        <div class="action-button">
            <span class="material-icons" style="font-size: 20px;">bookmark_border</span>
            Tambahkan ke daftar
        </div>
    </div>

    <div class="screenshots-section">
        <img class="screenshot-image" src="https://weme.code.blog/wp-content/uploads/2024/07/slide2.png" alt="Screenshot 1">
        <img class="screenshot-image" src="https://weme.code.blog/wp-content/uploads/2024/07/utama.png" alt="Screenshot 2">
        <img class="screenshot-image" src="https://iili.io/KE4BUQ4.png" alt="Screenshot 3">
    </div>

    <div class="content-section">
        <div class="section-title" id="about-title">
            Tentang Aplikasi ini
            <span class="material-icons">chevron_right</span>
        </div>
        <div class="section-body hidden-content" id="about-body">
            <p style="margin-top: 0; font-weight: 500; color: #202124;">
                PulsaKu PPOB: Solusi Pembayaran Digital Terlengkap.
            </p>
            <ul style="padding-left: 20px; margin-top: 10px; line-height: 1.6; list-style-type: disc; color: #5f6368;">
                <li>Menyediakan layanan pembelian **pulsa, paket data, dan token listrik** dengan harga yang kompetitif.</li>
                <li>Memfasilitasi pembayaran berbagai tagihan PPOB (Listrik Pasca Bayar, PDAM, BPJS, Telkom, dll.) secara **cepat dan aman**.</li>
                <li>Dirancang dengan **antarmuka sederhana (user-friendly)** untuk pengalaman transaksi yang instan, kapan saja dan di mana saja.</li>
                <li>Sangat ideal sebagai platform **agen pulsa** berkat harga modal yang rendah dan sistem yang stabil.</li>
            </ul>
            <p style="margin-bottom: 0;">
                Kelola semua kebutuhan pembayaran dan transaksi digital Anda dalam satu genggaman.
            </p>
        </div>
    </div>

    <div class="content-section">
        <div class="section-title" id="security-title">
            Keamanan data
            <span class="material-icons">chevron_right</span>
        </div>
        <div class="section-body hidden-content" id="security-body">
            <p style="margin-top: 0;">Keamanan dimulai dengan memahami cara developer mengumpulkan dan membagikan data Anda. Praktik privasi dan keamanan data dapat bervariasi berdasarkan penggunaan, wilayah, dan usia Anda. Developer memberikan informasi ini dan dapat memperbaruinya dari waktu ke waktu.</p>

            <div class="security-detail">
                <span class="material-icons security-icon">share</span>
                <div class="security-detail-text">
                    Tidak ada data yang dibagikan dengan pihak ketiga<br>
                    <a href="#">Pelajari lebih lanjut tentang cara developer menyatakan berbagi data</a>
                </div>
            </div>

            <div class="security-detail">
                <span class="material-icons security-icon">info</span>
                <div class="security-detail-text">
                    Aplikasi ini dapat mengumpulkan jenis data ini<br>
                    <small>Lokasi dan 3 data lainnya</small>
                </div>
            </div>

            <div class="security-detail">
                <span class="material-icons security-icon">lock</span>
                <div class="security-detail-text">Data dienkripsi dalam perjalanan</div>
            </div>

            <div class="security-detail">
                <span class="material-icons security-icon">delete</span>
                <div class="security-detail-text">Anda dapat meminta agar data dihapus</div>
            </div>

            <a href="#" class="security-link-more">Lihat detail</a>
        </div>
    </div>

    <div class="content-section">
        <div class="section-title" id="app-size-title">
            Ukuran aplikasi
            <span class="material-icons">chevron_right</span>
        </div>
        <div class="section-body hidden-content" id="app-size-body">
            <p style="margin: 0;">Ukuran download: 12 MB</p>
            <p style="margin-top: 8px;">Ukuran setelah instal: 35 MB</p>
        </div>
    </div>

    <div class="ratings-section">
        <div class="section-title">
            Rating dan ulasan
            <span class="material-icons">chevron_right</span>
        </div>

        <div class="rating-summary" style="margin-bottom: 20px;">
            <div style="text-align: center;">
                <div class="main-rating">4.9</div>
                <div class="total-reviews">827.6K ulasan</div>
            </div>
            <div class="rating-chart">
                <div class="chart-bar-row">
                    <span class="star-count">5</span>
                    <div class="chart-bar-bg"><div class="chart-bar-fill" style="width: 95%;"></div></div>
                </div>
                <div class="chart-bar-row">
                    <span class="star-count">4</span>
                    <div class="chart-bar-bg"><div class="chart-bar-fill" style="width: 3%;"></div></div>
                </div>
                <div class="chart-bar-row">
                    <span class="star-count">3</span>
                    <div class="chart-bar-bg"><div class="chart-bar-fill" style="width: 1%;"></div></div>
                </div>
                <div class="chart-bar-row">
                    <span class="star-count">2</span>
                    <div class="chart-bar-bg"><div class="chart-bar-fill" style="width: 0.5%;"></div></div>
                </div>
                <div class="chart-bar-row">
                    <span class="star-count">1</span>
                    <div class="chart-bar-bg"><div class="chart-bar-fill" style="width: 0.5%;"></div></div>
                </div>
            </div>
        </div>
        
        <div class="reviews-container">
            <div class="review-item">
                <div class="review-header">
                    <div class="reviewer-icon" style="background-color: #5f6368;">AV</div>
                    <div style="line-height: 1.2;">
                        <div class="reviewer-name">Adri Viljoen</div>
                        <div class="review-date">28 Agustus, 2025</div>
                    </div>
                    <span class="material-icons review-menu-icon">more_vert</span>
                </div>
                <div class="review-rating-stars">★★★★★</div>
                <div class="review-text">Dulu Jualan suka rugi, Semenjak Pakai PulsaKu Cuan banget</div>
                <div class="review-helpfulness">
                    Apakah ulasan ini membantu Anda?
                    <div class="helpfulness-actions">
                        <span class="helpfulness-btn">Ya</span>
                        <span class="helpfulness-btn">Tidak</span>
                    </div>
                </div>
            </div>

            <div class="hidden-reviews" id="moreReviews">
                <div class="review-item">
                    <div class="review-header">
                        <div class="reviewer-icon" style="background-color: #fbbc04;">BS</div>
                        <div style="line-height: 1.2;">
                            <div class="reviewer-name">Budi Santoso</div>
                            <div class="review-date">15 Oktober 2025</div>
                        </div>
                        <span class="material-icons review-menu-icon">more_vert</span>
                    </div>
                    <div class="review-rating-stars">★★★★★</div>
                    <div class="review-text">Aplikasi sangat membantu! Transaksi cepat dan harganya bersaing. Rekomendasi!</div>
                    <div class="review-helpfulness">Apakah ulasan ini membantu Anda?<div class="helpfulness-actions"><span class="helpfulness-btn">Ya</span><span class="helpfulness-btn">Tidak</span></div></div>
                </div>
                <div class="review-item">
                    <div class="review-header">
                        <div class="reviewer-icon" style="background-color: #34a853;">DL</div>
                        <div style="line-height: 1.2;">
                            <div class="reviewer-name">Dewi Lestari</div>
                            <div class="review-date">10 Oktober 2025</div>
                        </div>
                        <span class="material-icons review-menu-icon">more_vert</span>
                    </div>
                    <div class="review-rating-stars">★★★★★</div>
                    <div class="review-text">Sangat mudah digunakan, tidak ribet. Saya sudah pakai berkali-kali dan tidak pernah ada masalah.</div>
                    <div class="review-helpfulness">Apakah ulasan ini membantu Anda?<div class="helpfulness-actions"><span class="helpfulness-btn">Ya</span><span class="helpfulness-btn">Tidak</span></div></div>
                </div>
                <div class="review-item">
                    <div class="review-header">
                        <div class="reviewer-icon" style="background-color: #ea4335;">AZ</div>
                        <div style="line-height: 1.2;">
                            <div class="reviewer-name">Ahmad Zaki</div>
                            <div class="review-date">9 Oktober 2025</div>
                        </div>
                        <span class="material-icons review-menu-icon">more_vert</span>
                    </div>
                    <div class="review-rating-stars">★★★★☆</div>
                    <div class="review-text">Layanan pelanggan responsif, sangat puas dengan fitur yang ada.</div>
                    <div class="review-helpfulness">Apakah ulasan ini membantu Anda?<div class="helpfulness-actions"><span class="helpfulness-btn">Ya</span><span class="helpfulness-btn">Tidak</span></div></div>
                </div>
                <div class="review-item">
                    <div class="review-header">
                        <div class="reviewer-icon" style="background-color: #4285f4;">SA</div>
                        <div style="line-height: 1.2;">
                            <div class="reviewer-name">Siti Aminah</div>
                            <div class="review-date">7 Oktober 2025</div>
                        </div>
                        <span class="material-icons review-menu-icon">more_vert</span>
                    </div>
                    <div class="review-rating-stars">★★★★★</div>
                    <div class="review-text">Aplikasi ringan dan tidak memakan banyak memori. Sangat cocok untuk hp saya.</div>
                    <div class="review-helpfulness">Apakah ulasan ini membantu Anda?<div class="helpfulness-actions"><span class="helpfulness-btn">Ya</span><span class="helpfulness-btn">Tidak</span></div></div>
                </div>
                <div class="review-item">
                    <div class="review-header">
                        <div class="reviewer-icon" style="background-color: #fbbc04;">BW</div>
                        <div style="line-height: 1.2;">
                            <div class="reviewer-name">Bayu Wicaksono</div>
                            <div class="review-date">2 Oktober 2025</div>
                        </div>
                        <span class="material-icons review-menu-icon">more_vert</span>
                    </div>
                    <div class="review-rating-stars">★★★★★</div>
                    <div class="review-text">Harga pulsa dan paket datanya jauh lebih murah dari tempat lain. Top!</div>
                    <div class="review-helpfulness">Apakah ulasan ini membantu Anda?<div class="helpfulness-actions"><span class="helpfulness-btn">Ya</span><span class="helpfulness-btn">Tidak</span></div></div>
                </div>
                <div class="review-item">
                    <div class="review-header">
                        <div class="reviewer-icon" style="background-color: #34a853;">JP</div>
                        <div style="line-height: 1.2;">
                            <div class="reviewer-name">Joko Pratama</div>
                            <div class="review-date">19 September 2025</div>
                        </div>
                        <span class="material-icons review-menu-icon">more_vert</span>
                    </div>
                    <div class="review-rating-stars">★★★★☆</div>
                    <div class="review-text">Transaksi token listrik cepat. Sangat berguna untuk kebutuhan sehari-hari.</div>
                    <div class="review-helpfulness">Apakah ulasan ini membantu Anda?<div class="helpfulness-actions"><span class="helpfulness-btn">Ya</span><span class="helpfulness-btn">Tidak</span></div></div>
                </div>
                <div class="review-item">
                    <div class="review-header">
                        <div class="reviewer-icon" style="background-color: #ea4335;">WF</div>
                        <div style="line-height: 1.2;">
                            <div class="reviewer-name">Wulan Fauziah</div>
                            <div class="review-date">16 September 2025</div>
                        </div>
                        <span class="material-icons review-menu-icon">more_vert</span>
                    </div>
                    <div class="review-rating-stars">★★★★★</div>
                    <div class="review-text">Tampilan antarmuka sederhana dan bersih, tidak membingungkan. Sangat suka!</div>
                    <div class="review-helpfulness">Apakah ulasan ini membantu Anda?<div class="helpfulness-actions"><span class="helpfulness-btn">Ya</span><span class="helpfulness-btn">Tidak</span></div></div>
                </div>
                <div class="review-item">
                    <div class="review-header">
                        <div class="reviewer-icon" style="background-color: #4285f4;">FR</div>
                        <div style="line-height: 1.2;">
                            <div class="reviewer-name">Faisal Rahman</div>
                            <div class="review-date">11 September 2025</div>
                        </div>
                        <span class="material-icons review-menu-icon">more_vert</span>
                    </div>
                    <div class="review-rating-stars">★★★★★</div>
                    <div class="review-text">Kenenkji.</div>
                    <div class="review-helpfulness">Apakah ulasan ini membantu Anda?<div class="helpfulness-actions"><span class="helpfulness-btn">Ya</span><span class="helpfulness-btn">Tidak</span></div></div>
                </div>
                <div class="review-item">
                    <div class="review-header">
                        <div class="reviewer-icon" style="background-color: #fbbc04;">LH</div>
                        <div style="line-height: 1.2;">
                            <div class="reviewer-name">Lina Hermawan</div>
                            <div class="review-date">5 September 2025</div>
                        </div>
                        <span class="material-icons review-menu-icon">more_vert</span>
                    </div>
                    <div class="review-rating-stars">★★★★★</div>
                    <div class="review-text">Proses verifikasi cepat, langsung bisa digunakan. Rekomendasi untuk teman-teman.</div>
                    <div class="review-helpfulness">Apakah ulasan ini membantu Anda?<div class="helpfulness-actions"><span class="helpfulness-btn">Ya</span><span class="helpfulness-btn">Tidak</span></div></div>
                </div>
                <div class="review-item">
                    <div class="review-header">
                        <div class="reviewer-icon" style="background-color: #34a853;">RA</div>
                        <div style="line-height: 1.2;">
                            <div class="reviewer-name">Rizky Adiputra</div>
                            <div class="review-date">28 Agustus 2025</div>
                        </div>
                        <span class="material-icons review-menu-icon">more_vert</span>
                    </div>
                    <div class="review-rating-stars">★★★★☆</div>
                    <div class="review-text">Kadang ada gangguan, tapi tim supportnya cepat tanggap. Overall, bagus.</div>
                    <div class="review-helpfulness">Apakah ulasan ini membantu Anda?<div class="helpfulness-actions"><span class="helpfulness-btn">Ya</span><span class="helpfulness-btn">Tidak</span></div></div>
                </div>
                <div class="review-item">
                    <div class="review-header">
                        <div class="reviewer-icon" style="background-color: #ea4335;">AG</div>
                        <div style="line-height: 1.2;">
                            <div class="reviewer-name">Anita Gunawan</div>
                            <div class="review-date">20 Agustus 2025</div>
                        </div>
                        <span class="material-icons review-menu-icon">more_vert</span>
                    </div>
                    <div class="review-rating-stars">★★★★★</div>
                    <div class="review-text">Pulsa masuk dalam hitungan detik. Benar-benar instan!</div>
                    <div class="review-helpfulness">Apakah ulasan ini membantu Anda?<div class="helpfulness-actions"><span class="helpfulness-btn">Ya</span><span class="helpfulness-btn">Tidak</span></div></div>
                </div>
                <div class="review-item">
                    <div class="review-header">
                        <div class="reviewer-icon" style="background-color: #4285f4;">HP</div>
                        <div style="line-height: 1.2;">
                            <div class="reviewer-name">Hendro Purnomo</div>
                            <div class="review-date">15 Agustus 2025</div>
                        </div>
                        <span class="material-icons review-menu-icon">more_vert</span>
                    </div>
                    <div class="review-rating-stars">★★★★★</div>
                    <div class="review-text">Sangat cocok untuk jualan pulsa, harganya kompetitif dan banyak pilihan produk.</div>
                    <div class="review-helpfulness">Apakah ulasan ini membantu Anda?<div class="helpfulness-actions"><span class="helpfulness-btn">Ya</span><span class="helpfulness-btn">Tidak</span></div></div>
                </div>
                <div class="review-item">
                    <div class="review-header">
                        <div class="reviewer-icon" style="background-color: #fbbc04;">MI</div>
                        <div style="line-height: 1.2;">
                            <div class="reviewer-name">Maya Indah</div>
                            <div class="review-date">10 Agustus 2025</div>
                        </div>
                        <span class="material-icons review-menu-icon">more_vert</span>
                    </div>
                    <div class="review-rating-stars">★★★★★</div>
                    <div class="review-text">Top-up E-Wallet lancar jaya. Pilihan payment method-nya juga banyak.</div>
                    <div class="review-helpfulness">Apakah ulasan ini membantu Anda?<div class="helpfulness-actions"><span class="helpfulness-btn">Ya</span><span class="helpfulness-btn">Tidak</span></div></div>
                </div>
                <div class="review-item">
                    <div class="review-header">
                        <div class="reviewer-icon" style="background-color: #34a853;">SS</div>
                        <div style="line-height: 1.2;">
                            <div class="reviewer-name">Surya Saputra</div>
                            <div class="review-date">1 Agustus 2025</div>
                        </div>
                        <span class="material-icons review-menu-icon">more_vert</span>
                    </div>
                    <div class="review-rating-stars">★★★★☆</div>
                    <div class="review-text">Desain aplikasi perlu sedikit di-update, tapi fungsinya sempurna.</div>
                    <div class="review-helpfulness">Apakah ulasan ini membantu Anda?<div class="helpfulness-actions"><span class="helpfulness-btn">Ya</span><span class="helpfulness-btn">Tidak</span></div></div>
                </div>
                <div class="review-item">
                    <div class="review-header">
                        <div class="reviewer-icon" style="background-color: #ea4335;">EL</div>
                        <div style="line-height: 1.2;">
                            <div class="reviewer-name">Eka Laksana</div>
                            <div class="review-date">25 Juli 2025</div>
                        </div>
                        <span class="material-icons review-menu-icon">more_vert</span>
                    </div>
                    <div class="review-rating-stars">★★★★★</div>
                    <div class="review-text">Sering ada promo cashback. Benar-benar untung pakai aplikasi ini.</div>
                    <div class="review-helpfulness">Apakah ulasan ini membantu Anda?<div class="helpfulness-actions"><span class="helpfulness-btn">Ya</span><span class="helpfulness-btn">Tidak</span></div></div>
                </div>
                <div class="review-item">
                    <div class="review-header">
                        <div class="reviewer-icon" style="background-color: #4285f4;">Pulsaku</div>
                        <div style="line-height: 1.2;">
                            <div class="reviewer-name">Nur Rachman</div>
                            <div class="review-date">18 Juli 2025</div>
                        </div>
                        <span class="material-icons review-menu-icon">more_vert</span>
                    </div>
                    <div class="review-rating-stars">★★★☆☆</div>
                    <div class="review-text">Pernah gagal transaksi sekali, tapi dananya langsung dikembalikan. Semoga diperbaiki.</div>
                    <div class="review-helpfulness">Apakah ulasan ini membantu Anda?<div class="helpfulness-actions"><span class="helpfulness-btn">Ya</span><span class="helpfulness-btn">Tidak</span></div></div>
                </div>
                <div class="review-item">
                    <div class="review-header">
                        <div class="reviewer-icon" style="background-color: #fbbc04;">DS</div>
                        <div style="line-height: 1.2;">
                            <div class="reviewer-name">Dian Sari</div>
                            <div class="review-date">10 Juli 2025</div>
                        </div>
                        <span class="material-icons review-menu-icon">more_vert</span>
                    </div>
                    <div class="review-rating-stars">★★★★★</div>
                    <div class="review-text">Sistemnya stabil, bahkan saat tanggal muda. Good job!</div>
                    <div class="review-helpfulness">Apakah ulasan ini membantu Anda?<div class="helpfulness-actions"><span class="helpfulness-btn">Ya</span><span class="helpfulness-btn">Tidak</span></div></div>
                </div>
                <div class="review-item">
                    <div class="review-header">
                        <div class="reviewer-icon" style="background-color: #34a853;">RW</div>
                        <div style="line-height: 1.2;">
                            <div class="reviewer-name">Rudi Wahyudi</div>
                            <div class="review-date">1 Juli 2025</div>
                        </div>
                        <span class="material-icons review-menu-icon">more_vert</span>
                    </div>
                    <div class="review-rating-stars">★★★★★</div>
                    <div class="review-text">Saya seorang agen pulsa, aplikasi ini adalah partner terbaik saya. Laba maksimal.</div>
                    <div class="review-helpfulness">Apakah ulasan ini membantu Anda?<div class="helpfulness-actions"><span class="helpfulness-btn">Ya</span><span class="helpfulness-btn">Tidak</span></div></div>
                </div>
                <div class="review-item">
                    <div class="review-header">
                        <div class="reviewer-icon" style="background-color: #ea4335;">AY</div>
                        <div style="line-height: 1.2;">
                            <div class="reviewer-name">Ani Yuliana</div>
                            <div class="review-date">25 Juni 2025</div>
                        </div>
                        <span class="material-icons review-menu-icon">more_vert</span>
                    </div>
                    <div class="review-rating-stars">★★★★☆</div>
                    <div class="review-text">Paket data murah, bisa buat langganan bulanan. Mantap.</div>
                    <div class="review-helpfulness">Apakah ulasan ini membantu Anda?<div class="helpfulness-actions"><span class="helpfulness-btn">Ya</span><span class="helpfulness-btn">Tidak</span></div></div>
                </div>
                <div class="review-item">
                    <div class="review-header">
                        <div class="reviewer-icon" style="background-color: #4285f4;">YS</div>
                        <div style="line-height: 1.2;">
                            <div class="reviewer-name">Yusuf Setiawan</div>
                            <div class="review-date">18 Juni 2025</div>
                        </div>
                        <span class="material-icons review-menu-icon">more_vert</span>
                    </div>
                    <div class="review-rating-stars">★★★★★</div>
                    <div class="review-text">Sangat direkomendasikan untuk pebisnis PPOB pemula.</div>
                    <div class="review-helpfulness">Apakah ulasan ini membantu Anda?<div class="helpfulness-actions"><span class="helpfulness-btn">Ya</span><span class="helpfulness-btn">Tidak</span></div></div>
                </div>
                <div class="review-item">
                    <div class="review-header">
                        <div class="reviewer-icon" style="background-color: #fbbc04;">SR</div>
                        <div style="line-height: 1.2;">
                            <div class="reviewer-name">Siska Rini</div>
                            <div class="review-date">10 Juni 2025</div>
                        </div>
                        <span class="material-icons review-menu-icon">more_vert</span>
                    </div>
                    <div class="review-rating-stars">★★★★★</div>
                    <div class="review-text">Saya suka dengan fitur riwayat transaksi yang lengkap. Memudahkan pembukuan.</div>
                    <div class="review-helpfulness">Apakah ulasan ini membantu Anda?<div class="helpfulness-actions"><span class="helpfulness-btn">Ya</span><span class="helpfulness-btn">Tidak</span></div></div>
                </div>
                <div class="review-item">
                    <div class="review-header">
                        <div class="reviewer-icon" style="background-color: #34a853;">AW</div>
                        <div style="line-height: 1.2;">
                            <div class="reviewer-name">Arief Widodo</div>
                            <div class="review-date">1 Juni 2025</div>
                        </div>
                        <span class="material-icons review-menu-icon">more_vert</span>
                    </div>
                    <div class="review-rating-stars">★★★★☆</div>
                    <div class="review-text">Cepat dan praktis, tapi butuh lebih banyak variasi game voucher.</div>
                    <div class="review-helpfulness">Apakah ulasan ini membantu Anda?<div class="helpfulness-actions"><span class="helpfulness-btn">Ya</span><span class="helpfulness-btn">Tidak</span></div></div>
                </div>
                <div class="review-item">
                    <div class="review-header">
                        <div class="reviewer-icon" style="background-color: #ea4335;">IK</div>
                        <div style="line-height: 1.2;">
                            <div class="reviewer-name">Iwan Kurniawan</div>
                            <div class="review-date">25 Mei 2025</div>
                        </div>
                        <span class="material-icons review-menu-icon">more_vert</span>
                    </div>
                    <div class="review-rating-stars">★★★★★</div>
                    <div class="review-text">Tidak pernah mengecewakan. Selalu jadi pilihan pertama untuk bayar tagihan bulanan.</div>
                    <div class="review-helpfulness">Apakah ulasan ini membantu Anda?<div class="helpfulness-actions"><span class="helpfulness-btn">Ya</span><span class="helpfulness-btn">Tidak</span></div></div>
                </div>
                <div class="review-item">
                    <div class="review-header">
                        <div class="reviewer-icon" style="background-color: #4285f4;">VT</div>
                        <div style="line-height: 1.2;">
                            <div class="reviewer-name">Vina Trijayanti</div>
                            <div class="review-date">18 Mei 2025</div>
                        </div>
                        <span class="material-icons review-menu-icon">more_vert</span>
                    </div>
                    <div class="review-rating-stars">★★★★★</div>
                    <div class="review-text">Pelayanan customer service cepat dan ramah, masalah saya selesai dalam 5 menit.</div>
                    <div class="review-helpfulness">Apakah ulasan ini membantu Anda?<div class="helpfulness-actions"><span class="helpfulness-btn">Ya</span><span class="helpfulness-btn">Tidak</span></div></div>
                </div>
                <div class="review-item">
                    <div class="review-header">
                        <div class="reviewer-icon" style="background-color: #fbbc04;">HPK</div>
                        <div style="line-height: 1.2;">
                            <div class="reviewer-name">Hari P K</div>
                            <div class="review-date">10 Mei 2025</div>
                        </div>
                        <span class="material-icons review-menu-icon">more_vert</span>
                    </div>
                    <div class="review-rating-stars">★★★★★</div>
                    <div class="review-text">Murah, cepat, lengkap. Tiga kata yang menggambarkan aplikasi ini.</div>
                    <div class="review-helpfulness">Apakah ulasan ini membantu Anda?<div class="helpfulness-actions"><span class="helpfulness-btn">Ya</span><span class="helpfulness-btn">Tidak</span></div></div>
                </div>
                <div class="review-item">
                    <div class="review-header">
                        <div class="reviewer-icon" style="background-color: #34a853;">MR</div>
                        <div style="line-height: 1.2;">
                            <div class="reviewer-name">Maria Rosali</div>
                            <div class="review-date">1 Mei 2025</div>
                        </div>
                        <span class="material-icons review-menu-icon">more_vert</span>
                    </div>
                    <div class="review-rating-stars">★★★★☆</div>
                    <div class="review-text">Kadang suka lag saat pertama buka, tapi setelah itu lancar.</div>
                    <div class="review-helpfulness">Apakah ulasan ini membantu Anda?<div class="helpfulness-actions"><span class="helpfulness-btn">Ya</span><span class="helpfulness-btn">Tidak</span></div></div>
                </div>
                <div class="review-item">
                    <div class="review-header">
                        <div class="reviewer-icon" style="background-color: #ea4335;">SK</div>
                        <div style="line-height: 1.2;">
                            <div class="reviewer-name">Sudirman Kusumo</div>
                            <div class="review-date">25 April 2025</div>
                        </div>
                        <span class="material-icons review-menu-icon">more_vert</span>
                    </div>
                    <div class="review-rating-stars">★★★★★</div>
                    <div class="review-text">Deposit saldo cepat via bank manapun. Benar-benar memudahkan.</div>
                    <div class="review-helpfulness">Apakah ulasan ini membantu Anda?<div class="helpfulness-actions"><span class="helpfulness-btn">Ya</span><span class="helpfulness-btn">Tidak</span></div></div>
                </div>
                <div class="review-item">
                    <div class="review-header">
                        <div class="reviewer-icon" style="background-color: #4285f4;">DP</div>
                        <div style="line-height: 1.2;">
                            <div class="reviewer-name">Dina Putri</div>
                            <div class="review-date">18 April 2025</div>
                        </div>
                        <span class="material-icons review-menu-icon">more_vert</span>
                    </div>
                    <div class="review-rating-stars">★★★★★</div>
                    <div class="review-text">Aplikasi wajib untuk yang sering beli pulsa atau token listrik. Waktu lebih efisien.</div>
                    <div class="review-helpfulness">Apakah ulasan ini membantu Anda?<div class="helpfulness-actions"><span class="helpfulness-btn">Ya</span><span class="helpfulness-btn">Tidak</span></div></div>
                </div>
                <div class="review-item">
                    <div class="review-header">
                        <div class="reviewer-icon" style="background-color: #fbbc04;">FH</div>
                        <div style="line-height: 1.2;">
                            <div class="reviewer-name">Fajar Hermawan</div>
                            <div class="review-date">10 April 2025</div>
                        </div>
                        <span class="material-icons review-menu-icon">more_vert</span>
                    </div>
                    <div class="review-rating-stars">★★★★☆</div>
                    <div class="review-text">Semoga ke depannya bisa tambah layanan asuransi.</div>
                    <div class="review-helpfulness">Apakah ulasan ini membantu Anda?<div class="helpfulness-actions"><span class="helpfulness-btn">Ya</span><span class="helpfulness-btn">Tidak</span></div></div>
                </div>
                <div class="review-item">
                    <div class="review-header">
                        <div class="reviewer-icon" style="background-color: #34a853;">LN</div>
                        <div style="line-height: 1.2;">
                            <div class="reviewer-name">Lia Nuraini</div>
                            <div class="review-date">1 April 2025</div>
                        </div>
                        <span class="material-icons review-menu-icon">more_vert</span>
                    </div>
                    <div class="review-rating-stars">★★★★★</div>
                    <div class="review-text">Pilihan operator lengkap, jarang ada yang kosong. Puas!</div>
                    <div class="review-helpfulness">Apakah ulasan ini membantu Anda?<div class="helpfulness-actions"><span class="helpfulness-btn">Ya</span><span class="helpfulness-btn">Tidak</span></div></div>
                </div>
                <div class="review-item">
                    <div class="review-header">
                        <div class="reviewer-icon" style="background-color: #ea4335;">AG</div>
                        <div style="line-height: 1.2;">
                            <div class="reviewer-name">Andi Ginting</div>
                            <div class="review-date">25 Maret 2025</div>
                        </div>
                        <span class="material-icons review-menu-icon">more_vert</span>
                    </div>
                    <div class="review-rating-stars">★★★★★</div>
                    <div class="review-text">Benar-benar aplikasi multi-fungsi. Sudah pakai 1 tahun, tidak pindah ke lain hati.</div>
                    <div class="review-helpfulness">Apakah ulasan ini membantu Anda?<div class="helpfulness-actions"><span class="helpfulness-btn">Ya</span><span class="helpfulness-btn">Tidak</span></div></div>
                </div>
                <div class="review-item">
                    <div class="review-header">
                        <div class="reviewer-icon" style="background-color: #4285f4;">TW</div>
                        <div style="line-height: 1.2;">
                            <div class="reviewer-name">Taufik Wijaya</div>
                            <div class="review-date">18 Maret 2025</div>
                        </div>
                        <span class="material-icons review-menu-icon">more_vert</span>
                    </div>
                    <div class="review-rating-stars">★★★★★</div>
                    <div class="review-text">Tampilan user friendly. Gampang banget buat orang tua sekalipun.</div>
                    <div class="review-helpfulness">Apakah ulasan ini membantu Anda?<div class="helpfulness-actions"><span class="helpfulness-btn">Ya</span><span class="helpfulness-btn">Tidak</span></div></div>
                </div>
                <div class="review-item">
                    <div class="review-header">
                        <div class="reviewer-icon" style="background-color: #fbbc04;">AS</div>
                        <div style="line-height: 1.2;">
                            <div class="reviewer-name">Ari Susanto</div>
                            <div class="review-date">10 Maret 2025</div>
                        </div>
                        <span class="material-icons review-menu-icon">more_vert</span>
                    </div>
                    <div class="review-rating-stars">★★★★☆</div>
                    <div class="review-text">Fitur scan barcode pembayaran cukup akurat. Memuaskan.</div>
                    <div class="review-helpfulness">Apakah ulasan ini membantu Anda?<div class="helpfulness-actions"><span class="helpfulness-btn">Ya</span><span class="helpfulness-btn">Tidak</span></div></div>
                </div>
                <div class="review-item">
                    <div class="review-header">
                        <div class="reviewer-icon" style="background-color: #34a853;">NL</div>
                        <div style="line-height: 1.2;">
                            <div class="reviewer-name">Nia Larasati</div>
                            <div class="review-date">1 Maret 2025</div>
                        </div>
                        <span class="material-icons review-menu-icon">more_vert</span>
                    </div>
                    <div class="review-rating-stars">★★★★★</div>
                    <div class="review-text">Pengisian saldo selalu real-time. Tidak perlu khawatir kehabisan pulsa di tengah malam.</div>
                    <div class="review-helpfulness">Apakah ulasan ini membantu Anda?<div class="helpfulness-actions"><span class="helpfulness-btn">Ya</span><span class="helpfulness-btn">Tidak</span></div></div>
                </div>
                <div class="review-item">
                    <div class="review-header">
                        <div class="reviewer-icon" style="background-color: #ea4335;">SRT</div>
                        <div style="line-height: 1.2;">
                            <div class="reviewer-name">Suryadi RT</div>
                            <div class="review-date">25 Februari 2025</div>
                        </div>
                        <span class="material-icons review-menu-icon">more_vert</span>
                    </div>
                    <div class="review-rating-stars">★★★★★</div>
                    <div class="review-text">Sangat terbantu untuk bayar tagihan air dan BPJS. Hemat waktu!</div>
                    <div class="review-helpfulness">Apakah ulasan ini membantu Anda?<div class="helpfulness-actions"><span class="helpfulness-btn">Ya</span><span class="helpfulness-btn">Tidak</span></div></div>
                </div>
                <div class="review-item">
                    <div class="review-header">
                        <div class="reviewer-icon" style="background-color: #4285f4;">JH</div>
                        <div style="line-height: 1.2;">
                            <div class="reviewer-name">Jihan Handayani</div>
                            <div class="review-date">18 Februari 2025</div>
                        </div>
                        <span class="material-icons review-menu-icon">more_vert</span>
                    </div>
                    <div class="review-rating-stars">★★★★☆</div>
                    <div class="review-text">Notifikasi transaksi cepat, tidak perlu menunggu lama untuk konfirmasi.</div>
                    <div class="review-helpfulness">Apakah ulasan ini membantu Anda?<div class="helpfulness-actions"><span class="helpfulness-btn">Ya</span><span class="helpfulness-btn">Tidak</span></div></div>
                </div>
                <div class="review-item">
                    <div class="review-header">
                        <div class="reviewer-icon" style="background-color: #fbbc04;">RR</div>
                        <div style="line-height: 1.2;">
                            <div class="reviewer-name">Rangga Ramadhan</div>
                            <div class="review-date">10 Februari 2025</div>
                        </div>
                        <span class="material-icons review-menu-icon">more_vert</span>
                    </div>
                    <div class="review-rating-stars">★★★★★</div>
                    <div class="review-text">Best PPOB app in town! Admin paling ramah.</div>
                    <div class="review-helpfulness">Apakah ulasan ini membantu Anda?<div class="helpfulness-actions"><span class="helpfulness-btn">Ya</span><span class="helpfulness-btn">Tidak</span></div></div>
                </div>
                <div class="review-item">
                    <div class="review-header">
                        <div class="reviewer-icon" style="background-color: #34a853;">SS</div>
                        <div style="line-height: 1.2;">
                            <div class="reviewer-name">Senja Suci</div>
                            <div class="review-date">1 Februari 2025</div>
                        </div>
                        <span class="material-icons review-menu-icon">more_vert</span>
                    </div>
                    <div class="review-rating-stars">★★★★★</div>
                    <div class="review-text">Selalu update fitur baru, developer sangat perhatian dengan kebutuhan pengguna.</div>
                    <div class="review-helpfulness">Apakah ulasan ini membantu Anda?<div class="helpfulness-actions"><span class="helpfulness-btn">Ya</span><span class="helpfulness-btn">Tidak</span></div></div>
                </div>
                <div class="review-item">
                    <div class="review-header">
                        <div class="reviewer-icon" style="background-color: #ea4335;">AW</div>
                        <div style="line-height: 1.2;">
                            <div class="reviewer-name">Angga Wibowo</div>
                            <div class="review-date">25 Januari 2025</div>
                        </div>
                        <span class="material-icons review-menu-icon">more_vert</span>
                    </div>
                    <div class="review-rating-stars">★★★★☆</div>
                    <div class="review-text">Ada fitur laporan penjualan yang sangat detail, cocok untuk bisnis saya.</div>
                    <div class="review-helpfulness">Apakah ulasan ini membantu Anda?<div class="helpfulness-actions"><span class="helpfulness-btn">Ya</span><span class="helpfulness-btn">Tidak</span></div></div>
                </div>
                <div class="review-item">
                    <div class="review-header">
                        <div class="reviewer-icon" style="background-color: #4285f4;">MS</div>
                        <div style="line-height: 1.2;">
                            <div class="reviewer-name">Murni Silalahi</div>
                            <div class="review-date">18 Januari 2025</div>
                        </div>
                        <span class="material-icons review-menu-icon">more_vert</span>
                    </div>
                    <div class="review-rating-stars">★★★★★</div>
                    <div class="review-text">Tersedia fitur cetak struk via bluetooth. Sangat profesional!</div>
                    <div class="review-helpfulness">Apakah ulasan ini membantu Anda?<div class="helpfulness-actions"><span class="helpfulness-btn">Ya</span><span class="helpfulness-btn">Tidak</span></div></div>
                </div>
            </div>
        </div>

        <a id="showReviewsBtn" class="review-all-link">Lihat semua ulasan</a>
    </div>

    <div class="content-section new-features-section">
        <div class="section-title">
            Apa yang baru
            <span class="material-icons">chevron_right</span>
        </div>
        <div class="section-body">
            <p style="margin-bottom: 0;">Penambahan 3 permainan</p>
        </div>
    </div>

    <div class="content-section" style="border-bottom: none;">
        <div class="section-title" style="padding-bottom: 0;">
            Game serupa
            <span class="material-icons">chevron_right</span>
        </div>
    </div>

</div>

<script>
    // Fungsionalitas untuk menampilkan/menyembunyikan ulasan
    document.getElementById('showReviewsBtn').addEventListener('click', function() {
        var moreReviews = document.getElementById('moreReviews');
        if (moreReviews.style.display === 'none' || moreReviews.style.display === '') {
            moreReviews.style.display = 'block';
            this.textContent = 'Tutup ulasan';
        } else {
            moreReviews.style.display = 'none';
            this.textContent = 'Lihat semua ulasan';
        }
    });

    // Fungsionalitas untuk menampilkan/menyembunyikan bagian "Tentang Aplikasi Ini"
    document.getElementById('about-title').addEventListener('click', function() {
        var aboutBody = document.getElementById('about-body');
        var icon = this.querySelector('.material-icons');
        if (aboutBody.style.display === 'none' || aboutBody.style.display === '') {
            aboutBody.style.display = 'block';
            icon.textContent = 'expand_less';
        } else {
            aboutBody.style.display = 'none';
            icon.textContent = 'chevron_right';
        }
    });

    // Fungsionalitas untuk menampilkan/menyembunyikan bagian "Keamanan Data"
    document.getElementById('security-title').addEventListener('click', function() {
        var securityBody = document.getElementById('security-body');
        var icon = this.querySelector('.material-icons');
        if (securityBody.style.display === 'none' || securityBody.style.display === '') {
            securityBody.style.display = 'block';
            icon.textContent = 'expand_less';
        } else {
            securityBody.style.display = 'none';
            icon.textContent = 'chevron_right';
        }
    });
    
    // Fungsionalitas untuk menampilkan/menyembunyikan bagian "Ukuran Aplikasi"
    document.getElementById('app-size-title').addEventListener('click', function() {
        var appSizeBody = document.getElementById('app-size-body');
        var icon = this.querySelector('.material-icons');
        if (appSizeBody.style.display === 'none' || appSizeBody.style.display === '') {
            appSizeBody.style.display = 'block';
            icon.textContent = 'expand_less';
        } else {
            appSizeBody.style.display = 'none';
            icon.textContent = 'chevron_right';
        }
    });

    // Fungsionalitas tombol "Bagikan"
    document.getElementById('shareButton').addEventListener('click', function() {
        if (navigator.share) {
            navigator.share({
                title: 'PulsaKu PPOB',
                text: 'Dapatkan aplikasi PulsaKu PPOB, solusi pembayaran digital terlengkap.',
                url: 'https://app.bukaolshop.com/toko/pulsaku09',
            })
            .then(() => console.log('Berhasil membagikan!'))
            .catch((error) => console.log('Error saat membagikan', error));
        } else {
            alert('Fitur berbagi tidak didukung di perangkat Anda.');
        }
    });
</script>

</body>
</html>
