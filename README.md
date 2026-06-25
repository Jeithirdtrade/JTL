<html lang="sw">
<head>
    <meta charset="UTF-8">
    <title>Jumma Kareem · Ijumaa Tukufu · Fataki</title>
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">

    <style>
        /* RESET na msingi */
        html,
        body {
            margin: 0;
            padding: 0;
            height: 100%;
            overflow: hidden;
            background: #0b2a1f;
            font-family: 'Segoe UI', Tahoma, sans-serif;
        }

        /* CANVAS ya fataki */
        #fireworksCanvas {
            position: fixed;
            inset: 0;
            width: 100%;
            height: 100%;
            display: block;
            z-index: 1000;
            pointer-events: none;
        }

        /* KARATASI KUU – SIKU YA IJUMAA */
        .box {
            position: relative;
            z-index: 500;
            background: rgba(0, 0, 0, 0.75);
            color: #ffe9a8;
            max-width: 480px;
            width: 92%;
            margin: 3vh auto 0;
            padding: 22px 18px 28px;
            border-radius: 30px;
            text-align: center;
            border: 2px solid #d4af37;
            box-shadow: 0 15px 50px rgba(0, 0, 0, 0.9);
            backdrop-filter: blur(4px);
        }

        /* AYA ZA QUR-ANI */
        .quran-ayah {
            font-size: 1.2rem;
            color: #f0d080;
            line-height: 1.7;
            margin: 6px 0 4px;
            word-break: break-word;
            font-family: 'Traditional Arabic', 'Amiri', 'Segoe UI', serif;
        }
        .quran-ayah small {
            font-size: 0.75rem;
            color: #c9b27c;
            display: block;
            margin-top: 2px;
            font-family: 'Segoe UI', Tahoma, sans-serif;
            letter-spacing: 0.5px;
        }
        .swahili-trans {
            font-size: 0.9rem;
            color: #eedbaa;
            background: rgba(255, 215, 120, 0.10);
            padding: 8px 12px;
            border-radius: 20px;
            margin: 6px 0 10px;
            line-height: 1.5;
            border-left: 3px solid #d4af37;
            border-right: 3px solid #d4af37;
        }

        .divider {
            border: none;
            height: 2px;
            background: linear-gradient(to right, transparent, #d4af37, transparent);
            margin: 10px 0;
        }

        .box h2 {
            font-size: 1.4rem;
            margin: 6px 0 4px;
            color: #ffd966;
            letter-spacing: 1px;
        }
        .box .sub {
            font-size: 0.85rem;
            color: #c9b27c;
            margin-top: -2px;
            margin-bottom: 10px;
        }

        .box p {
            background: rgba(255, 215, 120, 0.08);
            padding: 10px 14px;
            border-radius: 25px;
            font-size: 0.95rem;
            margin: 8px 0 12px;
            line-height: 1.5;
        }

        /* KITUO CHA KUFUNGUA */
        button {
            margin-top: 8px;
            padding: 14px 28px;
            font-size: 1.2rem;
            border-radius: 40px;
            border: none;
            background: #d4af37;
            color: #1f3a1f;
            font-weight: bold;
            cursor: pointer;
            box-shadow: 0 8px 0 #7a5f1a;
            transition: 0.05s linear;
            width: auto;
            min-width: 200px;
        }
        button:active {
            transform: translateY(6px);
            box-shadow: 0 2px 0 #7a5f1a;
        }

        /* OVERLAY – SURPRISE */
        .surprise-overlay {
            position: fixed;
            inset: 0;
            background: rgba(0, 0, 0, 0.7);
            display: flex;
            align-items: center;
            justify-content: center;
            visibility: hidden;
            opacity: 0;
            z-index: 10000;
            transition: 0.3s ease;
            pointer-events: auto;
            backdrop-filter: blur(3px);
        }
        .surprise-overlay.show {
            visibility: visible;
            opacity: 1;
        }

        .surprise-card {
            background: #1d3b1d;
            border: 4px solid #d4af37;
            border-radius: 40px;
            padding: 28px 22px 32px;
            max-width: 400px;
            width: 88%;
            text-align: center;
            color: #fff3c4;
            box-shadow: 0 0 60px rgba(212, 175, 55, 0.5);
        }

        .surprise-card h2 {
            font-size: 1.3rem;
            line-height: 1.5;
            margin: 8px 0;
            word-break: break-word;
        }
        .surprise-card .quran-ayah-sm {
            font-size: 1.0rem;
            color: #f0d080;
            line-height: 1.6;
            margin: 8px 0;
            font-family: 'Traditional Arabic', 'Amiri', serif;
        }
        .surprise-card p {
            font-size: 1.1rem;
            margin: 12px 0;
        }

        .fomu-link {
            display: inline-block;
            margin-top: 10px;
            padding: 14px 24px;
            font-size: 1.2rem;
            border-radius: 40px;
            border: none;
            background: #e4a010;
            color: #1f3a1f;
            font-weight: bold;
            text-decoration: none;
            box-shadow: 0 6px 0 #7a4f0e;
            transition: 0.05s linear;
            width: auto;
            min-width: 180px;
            cursor: pointer;
        }
        .fomu-link:active {
            transform: translateY(5px);
            box-shadow: 0 1px 0 #7a4f0e;
        }

        .close-surprise {
            padding: 8px 28px;
            font-size: 1.0rem;
            background: #b8860b;
            box-shadow: 0 4px 0 #6b4b0e;
            min-width: auto;
            margin-top: 6px;
        }
        .close-surprise:active {
            transform: translateY(4px);
            box-shadow: 0 1px 0 #6b4b0e;
        }

        .surprise-card .footnote {
            font-size: 0.8rem;
            margin-top: 14px;
            background: transparent;
            opacity: 0.8;
        }

        @media (max-width: 480px) {
            .box {
                padding: 18px 14px 22px;
                margin-top: 2vh;
            }
            .quran-ayah {
                font-size: 1.0rem;
            }
            .box h2 {
                font-size: 1.2rem;
            }
            button {
                font-size: 1.0rem;
                padding: 12px 18px;
                min-width: 160px;
            }
            .surprise-card {
                padding: 20px 16px 24px;
            }
            .surprise-card h2 {
                font-size: 1.1rem;
            }
            .fomu-link {
                font-size: 1.0rem;
                padding: 12px 18px;
                min-width: 150px;
            }
        }
    </style>
</head>
<body>

    <!-- CANVAS ya fataki -->
    <canvas id="fireworksCanvas"></canvas>

    <!-- KARATASI KUU – IJUMAA KAREEM -->
    <div class="box">

        <!-- Surah Al-Jumu'ah 62:9 -->
        <div class="quran-ayah">
            ﴿ يَا أَيُّهَا الَّذِينَ آمَنُوا إِذَا نُودِيَ لِلصَّلَاةِ مِن يَوْمِ الْجُمُعَةِ فَاسْعَوْا إِلَىٰ ذِكْرِ اللَّهِ وَذَرُوا الْبَيْعَ ﴾
            <small>— Surah Al-Jumu'ah (62:9) —</small>
        </div>
        <div class="swahili-trans">
            <i class="fas fa-quote-left" style="opacity:0.6;"></i>
            Enyi mlio amini! Mnapoitwa kwa swala siku ya Ijumaa, nendeni kwa haraka kwenye dhikri ya Mwenyezi Mungu, na acheni biashara.
            <i class="fas fa-quote-right" style="opacity:0.6;"></i>
        </div>

        <hr class="divider">

        <!-- Surah Al-Jumu'ah 62:10 -->
        <div class="quran-ayah">
            ﴿ فَإِذَا قُضِيَتِ الصَّلَاةُ فَانتَشِرُوا فِي الْأَرْضِ وَابْتَغُوا مِن فَضْلِ اللَّهِ وَاذْكُرُوا اللَّهَ كَثِيرًا لَّعَلَّكُمْ تُفْلِحُونَ ﴾
            <small>— Surah Al-Jumu'ah (62:10) —</small>
        </div>
        <div class="swahili-trans">
            <i class="fas fa-quote-left" style="opacity:0.6;"></i>
            Na swala ikisha kamilika, enendeni katika ardhi, na kutafuta fadhili za Mwenyezi Mungu, na mtajeni Mwenyezi Mungu sana ili mpate kufanikiwa.
            <i class="fas fa-quote-right" style="opacity:0.6;"></i>
        </div>

        <hr class="divider">

        <h2><i class="fas fa-mosque"></i> JUMAA KAREEM <i class="fas fa-mosque"></i></h2>
        <div class="sub">✨ Ijumaa Tukufu · Baraka tele ✨</div>

        <p>
            <b>HAJI JECHA KHAMIS</b> akishirikiana na <b>JTL Zanzibar</b><br>
            anakutakia Ijumaa Kareem iliyojaa baraka, neema na mafanikio.
        </p>

        <button onclick="openSurprise()">✨ FUNGUA BARAKA ✨</button>
    </div>

    <!-- OVERLAY ya baraka + kiungo cha fomu -->
    <div id="overlay" class="surprise-overlay">
        <div class="surprise-card">
            <h2>
                <i class="fas fa-star" style="color:gold;"></i>
                ────⊹⊱✫⊰⊹────
                <br>
                جُمُعَةٌ مُبَارَكَةٌ
                <br>
                ────⊹⊱✫⊰⊹────
                <i class="fas fa-star" style="color:gold;"></i>
            </h2>

            <!-- Ayah fupi katika kadi -->
            <div class="quran-ayah-sm">
                ﴿ وَاذْكُرُوا اللَّهَ كَثِيرًا لَّعَلَّكُمْ تُفْلِحُونَ ﴾
                <br>
                <small style="color:#c9b27c; font-family:'Segoe UI',sans-serif;">— Surah Al-Jumu'ah (62:10) —</small>
            </div>

            <p>🤍 Ijumaa Kareem · Heri na baraka kwako na familia yako 🤍</p>

            <a href="https://drive.google.com/drive/folders/1sEbZHMdj91dEGRR6rqK-W6d9s57s-H_a" target="_blank" class="fomu-link" onclick="event.stopPropagation();">
                📋 BONYEZA HAPA · FOMU
            </a>

            <div style="margin-top: 16px;">
                <button class="close-surprise" onclick="closeSurprise()">✖ Funga</button>
            </div>

            <p class="footnote">Bonyeza fomu ili kujaza, au funga kuendelea kutazama fataki.</p>
        </div>
    </div>

    <script>
        /* ============================================================
           FIREWORKS – inayoendelea
           ============================================================ */
        const canvas = document.getElementById("fireworksCanvas");
        const ctx = canvas.getContext("2d");
        let w, h, fireworks = [],
            particles = [],
            running = false;

        function resize() {
            w = canvas.width = window.innerWidth;
            h = canvas.height = window.innerHeight;
        }
        window.addEventListener("resize", resize);
        resize();

        function random(min, max) { return Math.random() * (max - min) + min; }

        // ---------- Firework ----------
        class Firework {
            constructor() {
                this.x = random(0, w);
                this.y = h;
                this.targetY = random(h * 0.15, h * 0.50);
                this.color = `hsl(${random(0, 360)}, 100%, 65%)`;
                this.speed = random(10, 16);
                this.radius = 4;
            }
            update() {
                this.y -= this.speed;
                if (this.y <= this.targetY) {
                    explode(this.x, this.y, this.color);
                    return true;
                }
                drawCircle(this.x, this.y, this.radius, this.color);
                return false;
            }
        }

        // ---------- Particle ----------
        class Particle {
            constructor(x, y, color) {
                this.x = x;
                this.y = y;
                this.color = color;
                this.radius = random(2.5, 6);
                this.speedX = random(-9, 9);
                this.speedY = random(-9, 9);
                this.life = 70;
                this.decay = 0.93;
            }
            update() {
                this.life--;
                this.x += this.speedX;
                this.y += this.speedY;
                this.speedX *= this.decay;
                this.speedY *= this.decay;
                this.radius *= 0.97;
                drawCircle(this.x, this.y, this.radius, this.color);
                return this.life <= 0 || this.radius < 0.3;
            }
        }

        // ---------- Explosion ----------
        function explode(x, y, color) {
            let count = 60 + Math.floor(random(20, 50));
            for (let i = 0; i < count; i++) {
                particles.push(new Particle(x, y, color));
            }
            for (let i = 0; i < 18; i++) {
                let extra = `hsl(${random(0, 360)}, 90%, 72%)`;
                particles.push(new Particle(x, y, extra));
            }
        }

        function drawCircle(x, y, r, c) {
            ctx.beginPath();
            ctx.arc(x, y, r, 0, Math.PI * 2);
            ctx.fillStyle = c;
            ctx.shadowColor = c;
            ctx.shadowBlur = 14;
            ctx.fill();
            ctx.shadowBlur = 0;
        }

        // ---------- Animation loop ----------
        function animate() {
            if (!running) return;
            ctx.clearRect(0, 0, w, h);

            if (Math.random() < 0.10) fireworks.push(new Firework());

            fireworks = fireworks.filter(f => !f.update());
            particles = particles.filter(p => !p.update());

            requestAnimationFrame(animate);
        }

        // ============================================================
        //   OPEN / CLOSE
        // ============================================================
        function openSurprise() {
            document.getElementById("overlay").classList.add("show");
            running = true;
            animate();
        }

        function closeSurprise() {
            document.getElementById("overlay").classList.remove("show");
            running = false;
            ctx.clearRect(0, 0, w, h);
            fireworks = [];
            particles = [];
        }

        // hakikisha kiungo hakijafungwa na overlay
        document.querySelector('.fomu-link').addEventListener('click', function(e) {
            e.stopPropagation();
        });
    </script>

</body>
</html>
