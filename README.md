<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>GANTI PASSWORD ABANGKUHHH!</title>
  <style>
    :root {
      --bg: #f7f7f7;
      --text: #000;
      --box: #fff;
      --btn: #4caf50;
      --btn-hover: #45a049;
    }

    body.dark-mode {
      --bg: #121212;
      --text: #eee;
      --box: #1e1e1e;
      --btn: #6dd47e;
      --btn-hover: #57c773;
    }

    body {
      font-family: Arial, sans-serif;
      text-align: center;
      margin-top: 50px;
      background-color: var(--bg);
      color: var(--text);
      transition: background 0.3s, color 0.3s;
    }

    .login-form {
      background-color: var(--box);
      padding: 30px;
      border-radius: 10px;
      box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
      display: inline-block;
      width: 300px;
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

    .copy-btn, .theme-btn {
      background-color: var(--btn);
      color: white;
      padding: 10px 20px;
      border: none;
      cursor: pointer;
      font-size: 16px;
      margin-top: 20px;
      border-radius: 5px;
      transition: transform 0.2s ease;
    }

    .copy-btn:hover, .theme-btn:hover {
      background-color: var(--btn-hover);
      transform: scale(1.05);
    }

    .copy-btn:active, .theme-btn:active {
      transform: scale(0.95);
    }

    .notification {
      display: none;
      position: absolute;
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
    }

    h1 {
      font-size: 24px;
    }
  </style>
</head>
<body>
  <h1>GANTI PASSWORD ABANGKUHHH!</h1>
  <button class="theme-btn" onclick="toggleTheme()">🌗 Ganti Tema</button>

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

  <div class="notification" id="notification">Teks berhasil disalin!</div>

  <script>
    const passwords = ["bunga123", "kucing456", "apel789", "matahari22"];

    const prefixList = ["gacor", "jitu", "bola", "maxwin"];
    for (const prefix of prefixList) {
      for (let i = 1; i <= 999; i++) {
        const num = i.toString().padStart(3, "0");
        passwords.push(`${prefix}${num}`);
      }
    }

    const filteredPasswords = passwords.filter((pw) => pw.length >= 6);

    function copyAndChangePassword() {
      const password =
        filteredPasswords[Math.floor(Math.random() * filteredPasswords.length)];

      const newText = `Silahkan di Login Ya bosku Dengan

ID : 
password: ${password}

Dan ubah password bosku sesuai dengan keinginan bosku
Jangan beritahu password bosku kepada orang lain untuk keamanan akun bosku 🙂

Link login : https://toto12bulan.org`;

      const copyText = document.getElementById("full-text");
      copyText.value = newText;
      copyText.select();
      copyText.setSelectionRange(0, 99999);
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
  </script>
</body>
</html>
