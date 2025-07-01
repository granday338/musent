<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Musent - Kirim Lagu untuk Seseorang</title>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;600&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="styles.css">
    <script src="https://unpkg.com/@supabase/supabase-js@2"></script>
</head>
<body>
    <div class="container">
        <div class="logo">Musent</div>
        
        <!-- Form Kirim Pesan -->
        <div class="card" id="formPesan">
            <h2>Kirim Lagu untuk Seseorang</h2>
            <input type="text" id="namaPengirim" placeholder="Namamu (opsional)">
            <input type="text" id="namaPenerima" placeholder="Nama penerima" required>
            
            <div class="upload-area" id="uploadArea">
                <p>Klik untuk mengunggah lagu (MP3, max 5MB)</p>
                <input type="file" id="fileLagu" accept="audio/mp3" style="display: none;">
                <audio id="audioPreview" controls style="display: none;"></audio>
            </div>
            
            <textarea id="pesan" placeholder="Tulis pesanmu..." rows="4" required></textarea>
            <button id="btnKirim">Kirim Pesan Musik</button>
        </div>
        
        <!-- Hasil Link -->
        <div class="card" id="hasilLink" style="display: none;">
            <h2>🎵 Pesan Musik Siap Dikirim!</h2>
            <p>Berikan link ini ke <strong id="namaPenerimaTampil"></strong>:</p>
            <div class="share-link" id="linkPesan"></div>
            <button id="btnSalin">Salin Link</button>
        </div>
        
        <!-- Tampilan Penerima -->
        <div class="card" id="tampilanPenerima" style="display: none;">
            <h2>Untuk: <span id="penerimaNama"></span></h2>
            <p>Dari: <span id="pengirimNama"></span></p>
            
            <div class="song-player">
                <h3 id="judulLagu"></h3>
                <audio id="pemutarLagu" controls></audio>
            </div>
            
            <div class="message-box">
                <p id="isiPesan"></p>
            </div>
            
            <button onclick="window.location.href = window.location.pathname">Buat Pesan Baru</button>
        </div>
    </div>

    <script src="script.js"></script>
</body>
</html>
