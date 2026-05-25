# ruru-valentine-s-
valentine's for ruru 
<!DOCTYPE html>
<html lang="hi">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Will you be my Valentine, Ruru? 💕</title>
  <style>
    body {
      margin: 0; padding: 0; height: 100vh;
      background: linear-gradient(135deg, #1a0033, #4a0022);
      color: white;
      font-family: 'Segoe UI', sans-serif;
      display: flex; align-items: center; justify-content: center;
      overflow: hidden; position: relative;
    }
    .container { text-align: center; z-index: 10; }
    h1 { font-size: 2.5em; margin-bottom: 20px; text-shadow: 0 0 20px #ff69b4; }
    .gif { margin: 20px auto; border-radius: 20px; box-shadow: 0 0 30px rgba(255,105,180,0.6); }
    button {
      padding: 15px 40px; margin: 10px; font-size: 1.3em;
      border: none; border-radius: 50px; cursor: pointer;
    }
    #yesBtn { background: #ff1493; color: white; font-weight: bold; }
    #noBtn { background: #555; color: white; }
    .message { margin-top: 30px; font-size: 1.4em; opacity: 0; transition: 1s; }
    .hearts { position: absolute; top: 0; left: 0; width: 100%; height: 100%; pointer-events: none; overflow: hidden; }
    .heart { position: absolute; font-size: 25px; color: #ff1493; animation: fall linear infinite; }
    @keyframes fall { to { transform: translateY(100vh); } }
  </style>
</head>
<body>
  <div class="hearts" id="hearts"></div>
  <div class="container">
    <h1>Will you be my Valentine, <span style="color:#ff69b4;">Ruru</span>? 💕</h1>
    <img src="https://media.tenor.com/EBV7OT7ACfwAAAAj/u-u-qua-qua-u-quaa.gif" class="gif" width="220">
    <div>
      <button id="yesBtn">Yes 💖</button>
      <button id="noBtn">No 😢</button>
    </div>
    <div class="message" id="message">Thank you Ruru! I love you so much ❤️</div>
  </div>

  <script>
    const yesBtn = document.getElementById('yesBtn');
    const noBtn = document.getElementById('noBtn');
    const message = document.getElementById('message');
    let size = 1;

    noBtn.addEventListener('mouseover', () => {
      noBtn.style.transform = `translate(${Math.random()*300-150}px, ${Math.random()*200-100}px)`;
    });

    yesBtn.addEventListener('click', () => {
      size += 0.3;
      yesBtn.style.transform = `scale(${size})`;
      if (size > 2.5) message.style.opacity = 1;
    });

    function createHeart() {
      const h = document.createElement('div');
      h.className = 'heart';
      h.textContent = '❤️';
      h.style.left = Math.random() * 100 + 'vw';
      h.style.animationDuration = (Math.random() * 3 + 3) + 's';
      document.getElementById('hearts').appendChild(h);
      setTimeout(() => h.remove(), 6000);
    }
    setInterval(createHeart, 400);
  </script>
</body>
</html>