<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Be My Valentine?</title>
    <style>
        body {
            margin: 0;
            padding: 0;
            height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            /* Romantic Background */
            background-image: url('https://images.unsplash.com/photo-1518199266791-5375a83190b7?q=80&w=2070&auto=format&fit=crop');
            background-size: cover;
            background-position: center;
            font-family: 'Segoe UI', Tahoma, sans-serif;
            overflow: hidden;
        }

        #container {
            background: rgba(255, 255, 255, 0.9);
            backdrop-filter: blur(5px);
            padding: 2rem;
            border-radius: 25px;
            box-shadow: 0 15px 35px rgba(0,0,0,0.2);
            text-align: center;
            max-width: 85%;
            z-index: 10;
        }

        .profile-img {
            width: 140px;
            height: 140px;
            object-fit: cover;
            border-radius: 50%;
            border: 4px solid #ff4d6d;
            margin-bottom: 1rem;
        }

        h1 { color: #d63384; font-size: 1.6rem; margin-bottom: 1.5rem; }

        .buttons {
            display: flex;
            gap: 15px;
            justify-content: center;
            align-items: center;
            height: 60px;
        }

        button {
            padding: 12px 28px;
            font-size: 1.1rem;
            border: none;
            border-radius: 12px;
            cursor: pointer;
            font-weight: bold;
            transition: 0.3s;
        }

        #yesBtn { background-color: #ff4d6d; color: white; }
        #noBtn { background-color: #adb5bd; color: white; position: relative; }

        .heart {
            position: absolute;
            color: #ff4d6d;
            font-size: 20px;
            pointer-events: none;
            animation: fall linear forwards;
            z-index: 1;
        }

        @keyframes fall {
            to { transform: translateY(110vh) rotate(360deg); }
        }

        #celebration { display: none; }
    </style>
</head>
<body>

    <audio id="romanticMusic" loop>
        <source src="https://www.bensound.com/bensound-music/bensound-love.mp3" type="audio/mp3">
    </audio>

    <div id="container">
        <div id="question-side">
            <img src=<img width="480" height="480" alt="image" src="https://github.com/user-attachments/assets/58b924a8-1132-4506-860c-8ca2a7614b60" /👩‍❤️‍👨
            <h1>Will you be my Valentine? 💖</h1>
            <div class="buttons">
                <button id="yesBtn">Yes!</button>
                <button id="noBtn">No</button>
            </div>
        </div>

        <div id="celebration">
            <img src="happy-us.jpg" alt="Yay" class="profile-img">
            <h1 style="color: #d63384;">Yay! I love you! 🥰</h1>
            <p>Can't wait for our date!</p>
        </div>
    </div>

    <script>
        const yesBtn = document.getElementById('yesBtn');
        const noBtn = document.getElementById('noBtn');
        const questionSide = document.getElementById('question-side');
        const celebration = document.getElementById('celebration');
        const music = document.getElementById('romanticMusic');

        // Play music on any interaction (required by browsers)
        function startMusic() {
            music.play().catch(e => console.log("Audio waiting for interaction"));
        }

        // Runaway Button Logic
        function moveButton() {
            startMusic();
            const x = Math.random() * (window.innerWidth - noBtn.offsetWidth);
            const y = Math.random() * (window.innerHeight - noBtn.offsetHeight);
            noBtn.style.position = 'fixed';
            noBtn.style.left = x + 'px';
            noBtn.style.top = y + 'px';
        }

        noBtn.addEventListener('mouseover', moveButton);
        noBtn.addEventListener('touchstart', (e) => {
            e.preventDefault();
            moveButton();
        });

        // Celebration Logic
        yesBtn.addEventListener('click', () => {
            startMusic();
            questionSide.style.display = 'none';
            celebration.style.display = 'block';
            setInterval(createHeart, 150);
        });

        function createHeart() {
            const heart = document.createElement('div');
            heart.classList.add('heart');
            heart.innerHTML = '❤️';
            heart.style.left = Math.random() * 100 + 'vw';
            heart.style.top = '-20px';
            heart.style.animationDuration = Math.random() * 2 + 3 + 's';
            document.body.appendChild(heart);
            setTimeout(() => { heart.remove(); }, 5000);
        }
    </script>
</body>
</html>
