# voyage-of-soul
A digital voyage for a soul as deep as the ocean. A special birthday tribute.
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Happy Birthday | A Voyage of Soul</title>
    <link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,400;0,600;1,400&family=Playfair+Display:ital,wght@0,400;1,700&family=Montserrat:wght@200;400&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary-blue: #2373a4;
            --deep-sea: #065484;
            --soft-blue: #46799e;
            --dark-base: #2c4b64;
            --silver: #e1e9ef;
        }

        * { margin: 0; padding: 0; box-sizing: border-box; }

        body {
            background: linear-gradient(180deg, var(--dark-base) 0%, var(--deep-sea) 100%);
            color: var(--silver);
            font-family: 'Cormorant Garamond', serif; /* Font Narasi Utama */
            overflow-x: hidden;
        }

        /* Overlay Input */
        #nameOverlay {
            position: fixed;
            inset: 0;
            background: radial-gradient(circle, var(--soft-blue), var(--dark-base));
            z-index: 1000;
            display: flex;
            justify-content: center;
            align-items: center;
            transition: all 1.5s cubic-bezier(0.7, 0, 0.3, 1);
        }

        .input-card {
            text-align: center;
            padding: 50px;
            background: rgba(255, 255, 255, 0.03);
            backdrop-filter: blur(25px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 2px;
        }

        input[type="text"] {
            background: transparent;
            border: none;
            border-bottom: 1px solid var(--primary-blue);
            color: white;
            font-size: 1.8rem;
            text-align: center;
            padding: 10px;
            outline: none;
            font-family: 'Cormorant Garamond', serif;
            margin-bottom: 30px;
            width: 300px;
            letter-spacing: 2px;
        }

        .btn-open {
            padding: 10px 40px;
            background: transparent;
            color: var(--silver);
            border: 1px solid var(--primary-blue);
            cursor: pointer;
            letter-spacing: 5px;
            font-family: 'Montserrat', sans-serif;
            font-size: 0.7rem;
            transition: 0.8s;
        }

        .btn-open:hover {
            background: var(--primary-blue);
            box-shadow: 0 0 30px rgba(35, 115, 164, 0.5);
        }

        /* Waves Animation */
        .waves {
            position: fixed;
            bottom: 0;
            width: 100%;
            height: 12vh;
            z-index: 1;
        }

        .parallax > use {
            animation: move-forever 25s cubic-bezier(.55,.5,.45,.5) infinite;
        }
        .parallax > use:nth-child(1) { animation-delay: -2s; animation-duration: 7s; fill: rgba(35, 115, 164, 0.4); }
        .parallax > use:nth-child(2) { animation-delay: -3s; animation-duration: 10s; fill: rgba(70, 121, 158, 0.2); }
        .parallax > use:nth-child(3) { animation-delay: -4s; animation-duration: 13s; fill: rgba(6, 84, 132, 0.1); }
        .parallax > use:nth-child(4) { animation-delay: -5s; animation-duration: 20s; fill: var(--dark-base); }

        @keyframes move-forever {
            0% { transform: translate3d(-90px,0,0); }
            100% { transform: translate3d(85px,0,0); }
        }

        /* Content Sections */
        section {
            min-height: 110vh;
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 80px 25px;
            position: relative;
            z-index: 5;
            opacity: 0;
            transform: translateY(50px);
            transition: 3s ease;
        }

        section.visible { opacity: 1; transform: translateY(0); }

        .glass-box {
            max-width: 800px;
            text-align: center;
        }

        h1 {
            font-family: 'Playfair Display', serif;
            font-size: 3.5rem;
            color: var(--silver);
            margin-bottom: 30px;
            font-weight: 400;
            font-style: italic;
        }

        .name-target { 
            color: var(--primary-blue); 
            font-style: italic;
            border-bottom: 1px solid rgba(35, 115, 164, 0.3);
        }

        p {
            line-height: 2.4;
            letter-spacing: 0.5px;
            font-size: 1.35rem; /* Ukuran lebih besar agar Garamond terlihat jelas */
            margin-bottom: 30px;
            color: rgba(225, 233, 239, 0.9);
            text-align: center;
        }

        .quote-lang {
            font-family: 'Playfair Display', serif;
            font-style: italic;
            color: var(--primary-blue);
            display: block;
            margin: 40px 0;
            font-size: 1.5rem;
            line-height: 1.6;
        }

        .divider {
            width: 50px;
            height: 1px;
            background: var(--primary-blue);
            margin: 40px auto;
            opacity: 0.6;
        }

        /* Dark Blue Flower Accessories */
        .flower {
            position: fixed;
            pointer-events: none;
            z-index: 2;
            opacity: 0.3;
            animation: fall linear infinite;
        }

        @keyframes fall {
            0% { transform: translateY(-10vh) rotate(0deg); }
            100% { transform: translateY(110vh) rotate(360deg); }
        }
    </style>
</head>
<body>

    <div id="nameOverlay">
        <div class="input-card">
            <h2 style="font-family: 'Playfair Display'; font-style: italic; font-weight: 400; margin-bottom: 30px; letter-spacing: 3px;">The Ocean's Whisper</h2>
            <input type="text" id="nameInput" placeholder="Write the name..." autocomplete="off">
            <br>
            <button class="btn-open" onclick="startVoyage()">E N T E R</button>
        </div>
    </div>

    <svg class="waves" xmlns="http://www.w3.org/2000/svg" viewBox="0 24 150 28" preserveAspectRatio="none">
        <defs>
            <path id="gentle-wave" d="M-160 44c30 0 58-18 88-18s 58 18 88 18 58-18 88-18 58 18 88 18 v44h-352z" />
        </defs>
        <g class="parallax">
            <use href="#gentle-wave" x="48" y="0" />
            <use href="#gentle-wave" x="48" y="3" />
            <use href="#gentle-wave" x="48" y="5" />
            <use href="#gentle-wave" x="48" y="7" />
        </g>
    </svg>

    <div id="mainContent">
        <section class="step">
            <div class="glass-box">
                <h1>Happy Birthday, <br><span class="name-target"></span></h1>
                <div class="divider"></div>
                <p>Selamat ulang tahun, wahai jiwa yang lahir di bawah langit semesta. Seperti samudra, hidupmu adalah misteri yang luas, penuh gelombang pasang surut, namun selalu menawarkan kedalaman yang tak terhingga dan keindahan yang tak terlukiskan.</p>
                <p>Setiap tahun yang berlalu adalah ombak yang menghempas, mengukir kebijaksanaan di pasir pantai hatimu, membawa butiran mutiara pengalaman.</p>
            </div>
        </section>

        <section class="step">
            <div class="glass-box">
                <span class="quote-lang">"Que la vie est un voyage, non une destination."<br>
                <small style="font-size: 0.9rem; font-family: 'Montserrat'; font-style: normal; opacity: 0.6;">(Bahwa hidup adalah sebuah perjalanan, bukan tujuan.)</small></span>
                
                <p>Biarlah bintang-bintang di angkasa menjadi kompasmu, dan irama ombak yang berbisik menjadi melodi yang menenangkan jiwamu di setiap badai. Jangan pernah takut berlayar jauh dari pelabuhan yang aman, karena di sana, di cakrawala tak berbatas, menanti keajaiban yang belum pernah kau jumpai.</p>
            </div>
        </section>

        <section class="step">
            <div class="glass-box">
                <span class="quote-lang">"Mögest du immer Rückenwind haben und Sonnenschein im Gesicht..."<br>
                <small style="font-size: 0.9rem; font-family: 'Montserrat'; font-style: normal; opacity: 0.6;">(Semoga kamu selalu mendapat angin di belakang dan sinar matahari di wajahmu...)</small></span>

                <p>Semoga setiap napas adalah berkah, setiap tawa adalah anugerah, dan setiap hari adalah kesempatan baru untuk menemukan keindahan di setiap sudut samudra kehidupanmu.</p>
                <div class="divider"></div>
                <p style="font-style: italic; font-weight: 600;">Selamat berlayar di tahun yang baru, dengan hati yang penuh harapan dan jiwa yang setegar karang.</p>
            </div>
        </section>
    </div>

    <script>
        function startVoyage() {
            const name = document.getElementById('nameInput').value;
            if(!name) return alert("Please write a name... ✨");

            document.querySelectorAll('.name-target').forEach(el => el.innerText = name);
            
            document.getElementById('nameOverlay').style.opacity = '0';
            document.getElementById('nameOverlay').style.transform = 'translateY(-100%)';
            
            setTimeout(() => {
                document.getElementById('nameOverlay').style.visibility = 'hidden';
                document.querySelector('.step').classList.add('visible');
            }, 1200);

            setInterval(createDarkFlower, 700);
        }

        function createDarkFlower() {
            const flower = document.createElement('div');
            flower.classList.add('flower');
            const types = ['✺', '⚜', '✧', '❉', '❀'];
            flower.innerHTML = types[Math.floor(Math.random() * types.length)];
            flower.style.color = '#1a3c5a'; 
            flower.style.left = Math.random() * 100 + 'vw';
            flower.style.fontSize = Math.random() * 25 + 10 + 'px';
            flower.style.animationDuration = Math.random() * 5 + 10 + 's';
            document.body.appendChild(flower);
            setTimeout(() => flower.remove(), 15000);
        }

        window.addEventListener('scroll', () => {
            const steps = document.querySelectorAll('.step');
            steps.forEach(step => {
                const rect = step.getBoundingClientRect();
                if (rect.top < window.innerHeight * 0.7) {
                    step.classList.add('visible');
                }
            });
        });
    </script>
</body>
</html>
