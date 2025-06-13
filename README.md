
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>Para María Paula ❤️</title>
  <style>
    html, body {
      height: 100%;
      margin: 0;
      background-color: #ffe6f0;
      font-family: 'Comic Sans MS', cursive, sans-serif;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      text-align: center;
      overflow: hidden;
    }

    .heart {
      width: 100px;
      height: 90px;
      background-color: red;
      position: relative;
      transform: rotate(-45deg);
      animation: heartbeat 1s infinite;
      margin-bottom: 40px;
    }

    .heart::before,
    .heart::after {
      content: "";
      width: 100px;
      height: 90px;
      background-color: red;
      border-radius: 50%;
      position: absolute;
    }

    .heart::before {
      top: -50px;
      left: 0;
    }

    .heart::after {
      left: 50px;
      top: 0;
    }

    @keyframes heartbeat {
      0%, 100% {
        transform: scale(1) rotate(-45deg);
      }
      50% {
        transform: scale(1.2) rotate(-45deg);
      }
    }

    h1 {
      font-size: 36px;
      color: #cc0066;
      margin: 20px;
    }

    .btn {
      margin: 10px;
      padding: 15px 30px;
      font-size: 20px;
      background-color: #ff3399;
      color: white;
      border: none;
      border-radius: 12px;
      cursor: pointer;
      transition: background-color 0.3s ease;
    }

    .btn:hover {
      background-color: #e60073;
    }

    #buttons {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
    }

    .hearts {
      position: absolute;
      bottom: 0;
      width: 100%;
      height: 100%;
      pointer-events: none;
      z-index: -1;
    }

    .hearts span {
      position: absolute;
      width: 20px;
      height: 20px;
      background: pink;
      animation: rise 5s linear infinite;
      opacity: 0.7;
      border-radius: 50%;
    }

    @keyframes rise {
      0% {
        transform: translateY(100%);
        opacity: 0.7;
      }
      100% {
        transform: translateY(-120vh);
        opacity: 0;
      }
    }

    #gif {
      margin-top: 30px;
    }

  </style>
</head>
<body>

  <div class="heart"></div>
  <h1>María Paula, princesita hermosa,<br>¿quieres ser mi novia? 💖</h1>

  <div id="buttons">
    <button class="btn" onclick="responderSi()">Sí, quiero 💘</button>
    <button class="btn" id="noBtn" onclick="responderNo()">No 😢</button>
  </div>

  <div class="hearts" id="hearts"></div>
  <div id="gif"></div>

  <script>
    function responderSi() {
      alert('💕 Me haces muy feliz mi amor 🥰');
      for (let i = 0; i < 100; i++) {
        const span = document.createElement("span");
        span.style.left = Math.random() * 100 + "vw";
        span.style.animationDelay = Math.random() * 5 + "s";
        document.getElementById("hearts").appendChild(span);
      }

      document.getElementById("gif").innerHTML = `
        <img src="https://media.giphy.com/media/mCRJDo24UvJMA/giphy.gif" alt="Stitch beso" width="200">
      `;
    }

    function responderNo() {
      const noBtn = document.getElementById('noBtn');
      noBtn.innerText = '¿Segura? Vuelve a intentar 💔';
      noBtn.onclick = () => {
        const buttons = document.getElementById('buttons');
        buttons.innerHTML = `
          <button class="btn" onclick="responderSi()">¡Sí quiero! 💘</button>
          <button class="btn" onclick="responderSi()">¡Sí quiero! 💘</button>
        `;
      };
    }
  </script>

</body>
</html>
