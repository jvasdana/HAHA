<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Selamat Ulang Tahun!</title>
    <!-- Import Google Font untuk font lucu -->
    <link href="https://fonts.googleapis.com/css2?family=Fredoka+One&display=swap" rel="stylesheet">
    <style>
        html, body {
            height: 100%;
            margin: 0;
            padding: 0;
        }
        body {
            font-family: Arial, sans-serif;
            background: #ffc0cb url('pinti.png') no-repeat center center / cover; /* Gabungan: solid pink + gambar pinti.png */
            background-attachment: fixed; /* Agar background tetap saat scroll */
            text-align: center;
            overflow: hidden;
        }
        .container {
            padding: 20px; /* Kurangi padding untuk HP */
            background-color: rgba(255, 255, 255, 0.8); /* Overlay semi-transparan agar teks terbaca */
            border-radius: 10px;
            max-width: 90%; /* Lebih responsif, gunakan persentase */
            position: absolute; /* Untuk centering di tengah layar */
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%); /* Centering horizontal dan vertikal */
            z-index: 1; /* Pastikan container di depan */
        }
        h1 {
            color: #ff69b4;
            font-size: 2em; /* Kurangi ukuran font untuk HP */
        }
        .question {
            font-family: 'Fredoka One', cursive; /* Font lucu untuk pertanyaan */
            font-size: 1.5em; /* Kurangi ukuran font */
            margin: 20px 0;
            animation: slideIn 0.5s ease-out; /* Animasi slide in */
        }
        @keyframes slideIn {
            from { transform: translateX(-100%); opacity: 0; }
            to { transform: translateX(0); opacity: 1; }
        }
        input {
            font-size: 1.2em; /* Kurangi ukuran font */
            padding: 10px;
            width: 80px; /* Kurangi lebar */
            text-align: center;
        }
        /* Tombol Imut Berbeda-Beda */
        .btn-start {
            font-size: 1em; /* Kurangi ukuran font */
            padding: 12px 24px; /* Kurangi padding */
            background-color: #ff69b4;
            color: white;
            border: none;
            border-radius: 50px; /* Bulat */
            cursor: pointer;
            box-shadow: 0 4px 8px rgba(255, 105, 180, 0.3);
            transition: all 0.3s ease;
        }
        .btn-start:hover {
            background-color: #ff1493;
            transform: scale(1.1);
        }
        .btn-answer {
            font-size: 1em; /* Kurangi ukuran font */
            padding: 8px 16px; /* Kurangi padding */
            background-color: #32cd32;
            color: white;
            border: none;
            border-radius: 20px; /* Oval */
            cursor: pointer;
            box-shadow: 0 4px 8px rgba(50, 205, 50, 0.3);
            transition: all 0.3s ease;
        }
        .btn-answer:hover {
            background-color: #228b22;
            transform: scale(1.05);
        }
        .btn-oh-yaa {
            font-size: 1em; /* Kurangi ukuran font */
            padding: 10px 20px; /* Kurangi padding */
            background-color: #ffd700;
            color: #333;
            border: none;
            border-radius: 30px; /* Bulat panjang */
            cursor: pointer;
            box-shadow: 0 4px 8px rgba(255, 215, 0, 0.3);
            transition: all 0.3s ease;
        }
        .btn-oh-yaa:hover {
            background-color: #ffed4e;
            transform: scale(1.1);
        }
        .btn-iya {
            font-size: 1em; /* Kurangi ukuran font */
            padding: 10px 30px; /* Padding lebih besar agar terlihat */
            background-color: #ff69b4;
            color: white;
            border: none;
            border-radius: 25px; /* Bulat */
            cursor: pointer;
            box-shadow: 0 4px 8px rgba(255, 105, 180, 0.3);
            transition: all 0.3s ease;
        }
        .btn-iya:hover {
            background-color: #ff1493;
            transform: scale(1.1);
        }
        .hidden {
            display: none;
        }
        .firework {
            position: absolute;
            width: 8px; /* Kurangi ukuran untuk HP */
            height: 8px;
            background-color: red;
            border-radius: 50%;
            animation: explode 2s ease-out forwards;
            z-index: 2; /* Di atas animasi background */
        }
        @keyframes explode {
            0% { transform: scale(1); opacity: 1; }
            100% { transform: scale(8); opacity: 0; } /* Kurangi skala */
        }
        .celebration {
            font-family: 'Fredoka One', cursive; /* Font lucu untuk pesan akhir */
            font-size: 1.5em; /* Kurangi ukuran font */
            color: #ff69b4;
            animation: bounce 1s infinite;
        }
        @keyframes bounce {
            0%, 20%, 50%, 80%, 100% { transform: translateY(0); }
            40% { transform: translateY(-10px); }
            60% { transform: translateY(-5px); }
        }
        .wow-message {
            font-family: 'Fredoka One', cursive; /* Font lucu untuk pesan imut */
            font-size: 2em; /* Kurangi ukuran font */
            color: #ff69b4;
            animation: bounce 1s infinite, sparkle 1s infinite; /* Bounce dan sparkle */
            position: relative;
        }
        @keyframes sparkle {
            0%, 100% { text-shadow: 0 0 5px #ff69b4; }
            50% { text-shadow: 0 0 20px #ff69b4, 0 0 30px #ff69b4; }
        }
        .sparkle::before {
            content: '✨';
            position: absolute;
            top: -10px;
            left: -10px;
            animation: twinkle 1s infinite;
        }
        .sparkle::after {
            content: '✨';
            position: absolute;
            top: -10px;
            right: -10px;
            animation: twinkle 1s infinite 0.5s;
        }
        @keyframes twinkle {
            0%, 100% { opacity: 0; }
            50% { opacity: 1; }
        }
        .from-message {
            font-family: 'Fredoka One', cursive; /* Font lucu untuk bagian Dari */
            font-size: 1.2em; /* Kurangi ukuran font */
            color: #333;
            margin-top: 10px;
        }
        .gift-question {
            font-family: 'Fredoka One', cursive; /* Font imut untuk pertanyaan hadiah */
            font-size: 1.5em; /* Kurangi ukuran font */
            color: #ff69b4;
            margin: 20px 0;
        }
        .gift-message {
            font-family: 'Fredoka One', cursive; /* Font imut untuk pesan hadiah */
            font-size: 1.4em; /* Kurangi ukuran font */
            color: #333;
            margin: 20px 0;
        }
        
        /* Animasi: Garis vertikal */
        .line {
            position: absolute;
            width: 2px;
            height: 100vh;
            background: linear-gradient(
                to bottom,
                rgba(255, 105, 180, 0),
                rgba(255, 105, 180, 0.4),
                rgba(255, 105, 180, 0)
            );
            animation: moveLine linear infinite;
            z-index: 0; /* Di belakang container */
        }
        @keyframes moveLine {
            from { transform: translateY(-100vh); }
            to { transform: translateY(100vh); }
        }
        
        /* Animasi: Bunga jatuh */
        .flower {
            position: absolute;
            color: #ff4d88;
            font-size: 20px; /* Kurangi ukuran */
            animation: fall linear infinite;
            opacity: 0.8;
            z-index: 0; /* Di belakang container */
        }
        @keyframes fall {
            0% {
                transform: translateY(-10vh);
                opacity: 1;
            }
            100% {
                transform: translateY(110vh);
                opacity: 0;
            }
        }
        
        /* Animasi: Love jatuh */
        .love {
            position: absolute;
            font-size: 24px; /* Kurangi ukuran */
            animation: fall linear infinite;
            opacity: 0.9;
            z-index: 0; /* Di belakang container */
        }
        
        /* Media query untuk layar kecil (HP) */
        @media (max-width: 600px) {
            .container {
                padding: 15px;
            }
            h1 {
                font-size: 1.8em;
            }
            .question {
                font-size: 1.3em;
            }
            .wow-message {
                font-size: 1.8em;
            }
            .celebration {
                font-size: 1.3em;
            }
            .gift-question {
                font-size: 1.3em;
            }
            .gift-message {
                font-size: 1.2em;
            }
            .from-message {
                font-size: 1em;
            }
            input {
                width: 60px;
            }
            .btn-start, .btn-answer, .btn-oh-yaa, .btn-iya {
                font-size: 0.9em;
                padding: 10px 20px;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <!-- Bagian Awal: Judul, Gambar, Tombol Ayo Main!! -->
        <div id="intro">
            <h1>Happy Birthday, Shafa Amanah!!!</h1>
            <img src="2.gif" alt="Gambar Ulang Tahun" style="max-width: 100%; height: auto; border-radius: 10px; margin: 20px 0;"> <!-- Responsif -->
            <button class="btn-start" onclick="startQuiz()">Ayo Main!!</button>
        </div>
        
        <!-- Pertanyaan 1 -->
        <div id="q1" class="hidden">
            <p class="question">1 + 1 = ?</p>
            <input type="number" id="ans1">
            <button class="btn-answer" onclick="checkAnswer(1, 2)">Jawab</button>
        </div>
        
        <!-- Pertanyaan 2 -->
        <div id="q2" class="hidden">
            <p class="question">2 x 2 = ?</p>
            <input type="number" id="ans2">
            <button class="btn-answer" onclick="checkAnswer(2, 4)">Jawab</button>
        </div>
        
        <!-- Pertanyaan 3 -->
        <div id="q3" class="hidden">
            <p class="question">4 x 4 = ?</p>
            <input type="number" id="ans3">
            <button class="btn-answer" onclick="checkAnswer(3, 16)">Jawab</button>
        </div>
        
        <!-- Pesan Imut Setelah 16 -->
        <div id="wow" class="hidden">
            <p class="wow-message sparkle">WOW SUDAH 16 TAHUN YAA</p>
        </div>
        
        <!-- Efek Ledakan dan Pesan Akhir -->
        <div id="celebration" class="hidden">
            <p class="celebration">Happy birthday bestie!!!</p>
            <p> Semoga panjang umur, sehat terus, rezeki lo banjir, dan hidup lo makin naik level. Semua yang lagi lo incar tahun ini wajib lo penggal lah, gebuk lah taklukkan lah, pokoknya harus lo capai. INGET!! H A R U S. gagal? NGGAK BOLEH!! HARUS BISA!! Pokoknya tahun ini lo harus hancurin semua target dan buktiin kalau lo emang ratunya. 🔥             Anjaaay</p>
            <p class="from-message">Dari: [Orang Gila]</p>
            <button class="btn-oh-yaa" onclick="showGiftQuestion()">Oh yaa!!</button>
        </div>
        
        <!-- Pertanyaan Hadiah (Hanya Tombol Iya) -->
        <div id="gift-question" class="hidden">
            <p class="gift-question">Mau hadiah gak??</p>
            <button class="btn-iya" onclick="showGiftMessage()">Iya</button>
        </div>
        
        <!-- Pesan Hadiah Akhir -->
        <div id="gift-message" class="hidden">
            <p class="gift-message">Ooii harus mau doongss:) DM gua yaa. bilang aja "NUKI!!!" oke 😁😁. Jangan mokel!!</p>
        </div>
    </div>
    
    <script>
        let currentQuestion = 1;
        
        function startQuiz() {
            document.getElementById('intro').classList.add('hidden');
            document.getElementById('q1').classList.remove('hidden');
        }
        
        function checkAnswer(questionNum, correctAnswer) {
            const input = document.getElementById('ans' + questionNum);
            if (parseInt(input.value) === correctAnswer) {
                document.getElementById('q' + questionNum).classList.add('hidden');
                currentQuestion++;
                if (currentQuestion <= 3) {
                    document.getElementById('q' + currentQuestion).classList.remove('hidden');
                } else {
                    // Tampilkan pesan imut WOW
                    document.getElementById('wow').classList.remove('hidden');
                    // Tunggu 3 detik, lalu lanjut ke ledakan
                    setTimeout(() => {
                        document.getElementById('wow').classList.add('hidden');
                        // Efek ledakan
                        explodeFireworks();
                        // Suara petasan (opsional, pastikan file ada)
                        try {
                            const fireworkSound = new Audio('petasan.mp3');
                            fireworkSound.play();
                        } catch (e) {
                            console.log('Suara petasan tidak ditemukan');
                        }
                        // Tunggu sedikit lalu mainkan lagu (opsional)
                        setTimeout(() => {
                            try {
                                const birthdaySong = new Audio('hbdeee.mp3');
                                birthdaySong.play();
                            } catch (e) {
                                console.log('Lagu ulang tahun tidak ditemukan');
                            }
                        }, 2000); // 2 detik setelah ledakan
                        // Tampilkan pesan akhir
                        document.getElementById('celebration').classList.remove('hidden');
                    }, 3000); // 3 detik untuk pesan WOW
                }
            } else {
                alert('Jawaban salah! Coba lagi.');
            }
        }
        
        function explodeFireworks() {
            for (let i = 0; i < 15; i++) { // Kurangi jumlah untuk performa HP
                const firework = document.createElement('div');
                firework.classList.add('firework');
                firework.style.left = Math.random() * 100 + 'vw';
                firework.style.top = Math.random() * 100 + 'vh';
                firework.style.backgroundColor = ['red', 'blue', 'yellow', 'green'][Math.floor(Math.random() * 4)];
                document.body.appendChild(firework);
                setTimeout(() => firework.remove(), 2000);
            }
        }
        
        function showGiftQuestion() {
            document.getElementById('celebration').classList.add('hidden');
            document.getElementById('gift-question').classList.remove('hidden');
        }
        
        function showGiftMessage() {
            document.getElementById('gift-question').classList.add('hidden');
            document.getElementById('gift-message').classList.remove('hidden');
        }
        
        // Script: Garis vertikal
        function createLine() {
            const line = document.createElement("div");
            line.className = "line";
            line.style.left = Math.random() * 100 + "vw";
            line.style.animationDuration = (4 + Math.random() * 6) + "s";
            document.body.appendChild(line);
            
            setTimeout(() => {
                line.remove();
            }, 10000);
        }
        
        // Script: Bunga jatuh
        function createFlower() {
            const flower = document.createElement("div");
            flower.className = "flower";
            flower.innerHTML = "🌸"; // Emoji bunga
            flower.style.left = Math.random() * 100 + "vw";
            flower.style.animationDuration = (1 + Math.random() * 2) + "s"; // Durasi cepat: 1-3 detik
            flower.style.fontSize = (16 + Math.random() * 30) + "px";
            document.body.appendChild(flower);
            
            setTimeout(() => {
                flower.remove();
            }, 3000); // Hilang cepat: 3 detik
        }
        
        setInterval(createLine, 400);
        setInterval(createFlower, 100); // Bunga jatuh cepat dan sering
    </script>
</body>
</html>
