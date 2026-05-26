<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Will you be my Valentine? 💕</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Nunito:wght@400;700;900&display=swap');

        * { margin: 0; padding: 0; box-sizing: border-box; }
        body {
            font-family: 'Nunito', sans-serif;
            background: linear-gradient(135deg, #ff9a9e, #fad0c4, #fad0c4);
            min-height: 100vh;
            overflow: hidden;
            position: relative;
        }

        .hearts {
            position: absolute;
            top: 0; left: 0; width: 100%; height: 100%;
            pointer-events: none;
        }

        .heart {
            position: absolute;
            font-size: 30px;
            animation: float 8s infinite linear;
            opacity: 0.7;
        }

        @keyframes float {
            0% { transform: translateY(100vh) rotate(0deg); }
            100% { transform: translateY(-100px) rotate(360deg); }
        }

        .container {
            position: relative;
            z-index: 10;
            text-align: center;
            padding: 20px;
            max-width: 500px;
            margin: 0 auto;
        }

        h1 {
            font-size: 2.8rem;
            color: #ff4d94;
            margin: 30px 0 20px;
            text-shadow: 0 4px 10px rgba(255, 77, 148, 0.3);
        }

        .gif-container {
            margin: 20px 0;
            padding: 15px;
            background: white;
            border-radius: 30px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
        }

        img {
            width: 220px;
            border-radius: 20px;
        }

        .buttons {
            margin: 40px 0 30px;
            display: flex;
            justify-content: center;
            gap: 20px;
            flex-wrap: wrap;
        }

        button {
            padding: 18px 40px;
            font-size: 1.4rem;
            border: none;
            border-radius: 50px;
            cursor: pointer;
            transition: all 0.3s;
            font-weight: 700;
        }

        #yes-btn {
            background: #ff4d94;
            color: white;
            box-shadow: 0 8px 20px rgba(255, 77, 148, 0.4);
        }

        #yes-btn:hover {
            transform: scale(1.1);
        }

        #no-btn {
            background: #fff;
            color: #ff4d94;
            border: 3px solid #ff4d94;
        }

        .sticker {
            position: absolute;
            font-size: 45px;
            animation: stickerPop 4s infinite;
            z-index: 5;
        }

        @keyframes stickerPop {
            0%, 100% { transform: scale(0.8) rotate(-15deg); }
            50% { transform: scale(1.2) rotate(15deg); }
        }
    </style>
</head>
<body>

    <div class="hearts" id="hearts"></div>

    <div class="container">
        <h1>Will you be my Valentine? 💕</h1>

        <div class="gif-container">
            <img id="cat-gif" src="https://media.tenor.com/EBV7OT7ACfwAAAAj/u-u-qua-qua-u-quaa.gif" alt="cute cat">
        </div>

        <div class="buttons">
            <button id="yes-btn" onclick="handleYes()">Yes 💖</button>
            <button id="no-btn" onclick="handleNo()">No</button>
        </div>
    </div>

    <!-- Only Cat Stickers -->
    <div class="sticker" style="top: 12%; left: 8%;">🐱</div>
    <div class="sticker" style="top: 22%; right: 10%; animation-delay: 0.8s;">😺</div>
    <div class="sticker" style="bottom: 18%; left: 15%; animation-delay: 1.5s;">🐈</div>
    <div class="sticker" style="bottom: 28%; right: 12%; animation-delay: 2.2s;">😸</div>
    <div class="sticker" style="top: 45%; left: 18%; animation-delay: 0.5s;">🐾</div>

    <script>
        // Floating hearts
        function createHeart() {
            const heart = document.createElement('div');
            heart.classList.add('heart');
            heart.textContent = ['💕','❤️','💗','💖'][Math.floor(Math.random()*4)];
            heart.style.left = Math.random() * 100 + 'vw';
            heart.style.animationDuration = (Math.random() * 6 + 7) + 's';
            document.getElementById('hearts').appendChild(heart);
            
            setTimeout(() => heart.remove(), 15000);
        }

        setInterval(createHeart, 400);

        // No button logic
        let noClick = 0;
        const noBtn = document.getElementById('no-btn');
        const yesBtn = document.getElementById('yes-btn');

        const noTexts = [
            "No", 
            "Are you sure? 🥺", 
            "Pookie please... 🐱", 
            "Mujhe mat reject karo 💔",
            "Last chance... 😭"
        ];

        function handleNo() {
            noClick++;
            if (noClick < noTexts.length) {
                noBtn.textContent = noTexts[noClick];
            }
            const scale = 1 + (noClick * 0.2);
            yesBtn.style.transform = `scale(${scale})`;
        }

        function handleYes() {
            window.location.href = `data:text/html,<h1 style="text-align:center;margin-top:100px;font-size:3rem;color:#ff4d94;">Yayyy! I knew it 💕<br><br>I love you so much! 🐱❤️</h1>`;
        }

        // Auto hearts
        for(let i = 0; i < 8; i++) createHeart();
    </script>
</body>
</html>
