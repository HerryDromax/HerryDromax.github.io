<!doctype html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <title>For Rie ❤️</title>
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />

    <style>
      body {
        margin: 0;
        height: 100vh;
        background: linear-gradient(135deg, #ff758c, #ff7eb3);
        display: flex;
        align-items: center;
        justify-content: center;
        font-family: Arial, sans-serif;
        overflow: hidden;
      }

      .container {
        text-align: center;
        color: white;
      }

      h1 {
        font-size: 2.4rem;
        margin-bottom: 30px;
        text-shadow: 0 4px 15px rgba(0, 0, 0, 0.3);
      }

      button {
        padding: 15px 32px;
        font-size: 1.2rem;
        border: none;
        border-radius: 40px;
        cursor: pointer;
      }

      #yesBtn {
        background: #ff2e63;
        color: white;
        display: none;
        animation: popIn 0.6s ease forwards;
      }

      #noBtn {
        background: white;
        color: #ff2e63;
        position: absolute;
        animation: shake 0.15s infinite;
      }

      @keyframes shake {
        0% {
          transform: translate(0, 0);
        }
        25% {
          transform: translate(-6px, 6px);
        }
        50% {
          transform: translate(6px, -6px);
        }
        75% {
          transform: translate(-6px, -6px);
        }
        100% {
          transform: translate(0, 0);
        }
      }

      @keyframes popIn {
        0% {
          transform: scale(0);
          opacity: 0;
        }
        100% {
          transform: scale(1);
          opacity: 1;
        }
      }

      #result {
        display: none;
        flex-direction: column;
        align-items: center;
      }

      #result img {
        width: 260px;
        max-width: 85%;
        border-radius: 20px;
        margin-bottom: 20px;
      }

      #result h2 {
        font-size: 2rem;
        margin-bottom: 10px;
      }

      #result p {
        font-size: 1.1rem;
        opacity: 0.9;
      }
    </style>
  </head>

  <body>
    <div class="container" id="question">
      <h1>Rie, will you be my Valentine? 💖</h1>
      <button id="yesBtn">Yes ❤️</button>
      <button id="noBtn">No 😒</button>
    </div>

    <div class="container" id="result">
      <img
        src="https://media.giphy.com/media/l0MYt5jPR6QX5pnqM/giphy.gif"
        alt="Happy Love GIF"
      />
      <h2>You made the best decision of your life 💕</h2>
      <p>I love you ❤️ <br />Now screenshot this and send it to me 😌</p>
    </div>

    <audio id="music" loop>
      <source
        src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3"
        type="audio/mpeg"
      />
    </audio>

    <script>
      const noBtn = document.getElementById("noBtn");
      const yesBtn = document.getElementById("yesBtn");
      const question = document.getElementById("question");
      const result = document.getElementById("result");
      const music = document.getElementById("music");

      // Position NO initially
      noBtn.style.left = "50%";
      noBtn.style.top = "60%";

      // NO button escapes
      function moveNo() {
        const x = Math.random() * (window.innerWidth - noBtn.offsetWidth);
        const y = Math.random() * (window.innerHeight - noBtn.offsetHeight);
        noBtn.style.left = x + "px";
        noBtn.style.top = y + "px";
      }

      noBtn.addEventListener("mouseover", moveNo);
      noBtn.addEventListener("click", moveNo);

      // YES appears after delay
      setTimeout(() => {
        yesBtn.style.display = "inline-block";
      }, 3000);

      // YES clicked
      yesBtn.addEventListener("click", () => {
        question.style.display = "none";
        result.style.display = "flex";
        music.play();
      });
    </script>
  </body>
</html>
