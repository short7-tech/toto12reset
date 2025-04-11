<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>GANTI PASSWORD ABANGKUHHH!</title>

  <!-- 🧠 FAVICON -->
  <link rel="icon" href="https://photosaya.io/images/2024/07/09/LOGO.png" type="image/png"/>

  <style>
    :root {
      --bg: rgba(255, 255, 255, 0.95);
      --text: #000;
      --box: #fff;
      --btn: #4caf50;
      --btn-hover: #45a049;
    }

    body.dark-mode {
      --bg: rgba(0, 0, 0, 0.8);
      --text: #eee;
      --box: #1e1e1e;
      --btn: #6dd47e;
      --btn-hover: #57c773;
    }

    body {
      font-family: Arial, sans-serif;
      margin: 0;
      padding: 0;
      background-image: url('https://imagme.com/images/2025/02/21/photo_2025-02-21_01-31-20.jpeg');
      background-size: cover;
      background-position: center;
      background-attachment: fixed;
      background-repeat: no-repeat;
      color: var(--text);
      transition: 0.3s ease-in-out;
      text-align: center;
      cursor: url('https://photoku.io/images/2025/02/12/cursor.png'), auto;
      overflow-x: hidden;
    }

    canvas#snow {
      position: fixed;
      top: 0;
      left: 0;
      pointer-events: none;
      z-index: 1;
    }

    .judul-gif {
      margin-top: 30px;
      margin-bottom: 10px;
      position: relative;
      z-index: 2;
    }

    .judul-gif img {
      max-width: 300px;
      height: auto;
      filter: drop-shadow(2px 4px 6px rgba(0, 0, 0, 0.5));
    }

    .login-form {
      background-color: var(--box);
      padding: 30px;
      border-radius: 10px;
      box-shadow: 0 8px 20px rgba(0, 0, 0, 0.3);
      display: inline-block;
      width: 300px;
      margin-top: 20px;
      position: relative;
      z-index: 2;
    }

    .input-field {
      margin: 10px 0;
      padding: 10px;
      width: 100%;
      font-size: 16px;
      border: 1px solid #ccc;
      border-radius: 5px;
      background-color: var(--bg);
      color: var(--text);
    }

    .copy-btn, .theme-btn, .mute-btn {
      background-color: var(--btn);
      color: white;
      padding: 10px 20px;
      border: none;
      cursor: pointer;
      font-size: 16px;
      margin: 10px 5px 0 5px;
      border-radius: 5px;
      transition: transform 0.2s ease;
    }

    .copy-btn:hover, .theme-btn:hover, .mute-btn:hover {
      background-color: var(--btn-hover);
      transform: scale(1.05);
    }

    .copy-btn:active, .theme-btn:active, .mute-btn:active {
      transform: scale(0.95);
    }

    .notification {
      display: none;
      position: fixed;
      bottom: 20px;
      left: 50%;
      transform: translateX(-50%);
      background-color: var(--btn);
      color: white;
      padding: 10px;
      border-radius: 5px;
      font-size: 16px;
      opacity: 0;
      transition: opacity 0.5s;
      z-index: 3;
    }

    label {
      display: block;
      font-weight: bold;
      margin-bottom: 5px;
    }

    audio {
      display: none;
    }
  </style>
</head>
<body>

  <!-- ❄️ CANVAS SALJU -->
  <canvas id="snow"></canvas>

  <!-- 🎵 BACKSOUND -->
  <audio id="backsound" autoplay loop>
    <source src="https://cdn.pixabay.com/download/audio/2022/12/07/audio_dcef74f48d.mp3" type="audio/mpeg">
    Your browser does not support the audio element.
  </audio>

  <!-- 🎬 JUDUL GIF -->
  <div class="judul-gif">
    <img src="https://imagme.com/images/2024/11/11/gif-toto12.gif" alt="Judul GIF">
  </div>

  <!-- 🌗 DARK MODE & MUTE -->
  <button class="theme-btn" onclick="toggleTheme()">🌗 Ganti Tema</button>
  <button class="mute-btn" onclick="toggleMute()">🔊 Mute</button>

  <!-- 📋 FORM -->
  <div class="login-form">
    <label for="full-text">Silahkan di Login Ya bosku Dengan</label>
    <textarea id="full-text" class="input-field" rows="8" readonly>
Silahkan di Login Ya bosku Dengan

ID : 
password:

Dan ubah password bosku sesuai dengan keinginan bosku
Jangan beritahu password bosku kepada orang lain untuk keamanan akun bosku 🙂

Link login : https://toto12bulan.org
    </textarea><br />
    <button class="copy-btn" onclick="copyAndChangePassword()">Copy Cok!</button>
  </div>

  <!-- 🔔 NOTIFIKASI -->
  <div class="notification" id="notification">Teks berhasil disalin!</div>

  <!-- ✨ SCRIPT: SALJU -->
  <script>
    const canvas = document.getElementById("snow");
    const ctx = canvas.getContext("2d");
    let w = window.innerWidth;
    let h = window.innerHeight;
    canvas.width = w;
    canvas.height = h;

    const maxFlakes = 100;
    const flakes = [];

    function Flake() {
      this.x = Math.random() * w;
      this.y = Math.random() * h;
      this.radius = Math.random() * 3 + 1;
      this.speed = Math.random() * 1 + 0.5;
      this.wind = Math.random() * 1 - 0.5;

      this.update = function () {
        this.y += this.speed;
        this.x += this.wind;

        if (this.y > h) {
          this.y = 0;
          this.x = Math.random() * w;
        }
        if (this.x > w || this.x < 0) {
          this.x = Math.random() * w;
        }
      };

      this.draw = function () {
        ctx.beginPath();
        ctx.arc(this.x, this.y, this.radius, 0, Math.PI * 2);
        ctx.fillStyle = "rgba(255, 255, 255, 0.8)";
        ctx.fill();
      };
    }

    function createFlakes() {
      for (let i = 0; i < maxFlakes; i++) {
        flakes.push(new Flake());
      }
    }

    function animateFlakes() {
      ctx.clearRect(0, 0, w, h);
      for (let flake of flakes) {
        flake.update();
        flake.draw();
      }
      requestAnimationFrame(animateFlakes);
    }

    window.addEventListener("resize", () => {
      w = window.innerWidth;
      h = window.innerHeight;
      canvas.width = w;
      canvas.height = h;
    });

    createFlakes();
    animateFlakes();
  </script>

  <!-- 📋 SCRIPT: PASSWORD + SALIN -->
  <script>
    const passwords = ["bunga123", "kucing456", "apel789", "matahari22"];
    const prefixList = ["gacor", "jitu", "bola", "maxwin"];
    for (let prefix of prefixList) {
      for (let i = 1; i <= 999; i++) {
        passwords.push(`${prefix}${i.toString().padStart(3, '0')}`);
      }
    }

    const filteredPasswords = passwords.filter((pw) => pw.length >= 6);

    function copyAndChangePassword() {
      const password = filteredPasswords[Math.floor(Math.random() * filteredPasswords.length)];
      const newText = `Silahkan di Login Ya bosku Dengan

ID : 
password: ${password}

Dan ubah password bosku sesuai dengan keinginan bosku
Jangan beritahu password bosku kepada orang lain untuk keamanan akun bosku 🙂

Link login : https://toto12bulan.org`;

      const copyText = document.getElementById("full-text");
      copyText.value = newText;
      copyText.select();
      document.execCommand("copy");

      const notification = document.getElementById("notification");
      notification.style.display = "block";
      notification.style.opacity = 1;
      setTimeout(() => {
        notification.style.opacity = 0;
      }, 2000);
    }

    function toggleTheme() {
      document.body.classList.toggle("dark-mode");
    }

    function toggleMute() {
      const audio = document.getElementById("backsound");
      const muteBtn = document.querySelector(".mute-btn");
      if (audio.muted) {
        audio.muted = false;
        muteBtn.textContent = "🔊 Mute";
      } else {
        audio.muted = true;
        muteBtn.textContent = "🔇 Unmute";
      }
    }

    document.addEventListener("DOMContentLoaded", function () {
      const backsound = document.getElementById("backsound");
      backsound.volume = 0.5;
      document.body.addEventListener("click", () => {
        if (backsound.paused) backsound.play();
      }, { once: true });
    });
  </script>
</body>
</html>
