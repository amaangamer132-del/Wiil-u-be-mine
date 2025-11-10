<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Will You Be Mine, Harshika?</title>
  <style>
    body {
      margin: 0;
      height: 100vh;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      background: linear-gradient(135deg, #ffb6c1, #ff69b4);
      overflow: hidden;
      font-family: 'Poppins', sans-serif;
    }

    h1 {
      font-size: 2.5em;
      color: white;
      text-shadow: 2px 2px 10px #ff4081;
      margin-bottom: 30px;
      text-align: center;
    }

    .btn-container {
      display: flex;
      gap: 20px;
      position: relative;
    }

    button {
      padding: 15px 30px;
      font-size: 1.2em;
      border: none;
      border-radius: 10px;
      cursor: pointer;
      transition: 0.3s;
    }

    #yesBtn {
      background-color: #ff1493;
      color: white;
    }

    #yesBtn:hover {
      background-color: #ff69b4;
      transform: scale(1.1);
    }

    #noBtn {
      background-color: white;
      color: #ff1493;
      position: absolute;
    }

    /* Floating hearts & flowers */
    .heart, .flower {
      position: absolute;
      top: -50px;
      font-size: 24px;
      animation: fall 6s linear infinite;
      opacity: 0.8;
    }

    @keyframes fall {
      0% { transform: translateY(0) rotate(0deg); opacity: 1; }
      100% { transform: translateY(110vh) rotate(360deg); opacity: 0; }
    }

    /* Hidden love message */
    #loveMessage {
      display: none;
      font-size: 2em;
      color: white;
      margin-top: 30px;
      text-shadow: 2px 2px 8px #ff4081;
    }
  </style>
</head>
<body>
  <audio id="bgMusic" autoplay loop>
    <source src="YOUR_SONG_LINK_HERE.mp3" type="audio/mp3">
  </audio>

  <h1>Hey Harshika 💕<br>Will you be mine?</h1>

  <div class="btn-container">
    <button id="yesBtn">Yes 💖</button>
    <button id="noBtn">No 😜</button>
  </div>

  <div id="loveMessage">I love you, Harshika ❤️</div>

  <script>
    const noBtn = document.getElementById('noBtn');
    const yesBtn = document.getElementById('yesBtn');
    const loveMessage = document.getElementById('loveMessage');

    // Make the No button run away
    noBtn.addEventListener('mouseover', () => {
      const x = Math.random() * (window.innerWidth - noBtn.clientWidth);
      const y = Math.random() * (window.innerHeight - noBtn.clientHeight);
      noBtn.style.left = `${x}px`;
      noBtn.style.top = `${y}px`;
    });

    // When Yes is clicked
    yesBtn.addEventListener('click', () => {
      loveMessage.style.display = 'block';
      createHearts();
    });

    // Floating hearts & flowers
    function createHearts() {
      const symbols = ['💖', '🌸', '💐', '💞', '🌹', '❤️'];
      for (let i = 0; i < 30; i++) {
        const el = document.createElement('div');
        el.className = Math.random() > 0.5 ? 'heart' : 'flower';
        el.innerText = symbols[Math.floor(Math.random() * symbols.length)];
        el.style.left = Math.random() * 100 + 'vw';
        el.style.animationDuration = (3 + Math.random() * 5) + 's';
        document.body.appendChild(el);
        setTimeout(() => el.remove(), 6000);
      }
    }

    // Create random floating hearts continuously
    setInterval(createHearts, 2000);
  </script>
</body>
</html>
