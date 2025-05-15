❤️
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Love Login</title>
  <style>
    body {
      margin: 0;
      font-family: 'Arial', sans-serif;
      background: linear-gradient(to right, #ffafbd, #ffc3a0);
      height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      flex-direction: column;
    }

    .login-box, .heart-container {
      background-color: white;
      padding: 40px;
      border-radius: 15px;
      text-align: center;
      box-shadow: 0px 0px 15px rgba(255, 105, 180, 0.5);
      display: none;
    }

    .login-box {
      display: block;
    }

    h2, h1 {
      color: #ff69b4;
    }

    input, button {
      width: 100%;
      margin: 10px 0;
      padding: 12px;
      border: none;
      border-radius: 10px;
      font-size: 16px;
    }

    button {
      background-color: #ff69b4;
      color: white;
      cursor: pointer;
    }

    .heart {
      position: relative;
      width: 100px;
      height: 90px;
      background: #ff6b81;
      transform: rotate(-45deg);
      margin: 20px auto;
      animation: pulse 1s infinite;
      cursor: pointer;
    }

    .heart::before,
    .heart::after {
      content: "";
      position: absolute;
      width: 100px;
      height: 90px;
      background: #ff6b81;
      border-radius: 50%;
    }

    .heart::before {
      top: -50px;
      left: 0;
    }

    .heart::after {
      left: 50px;
      top: 0;
    }

    @keyframes pulse {
      0% { transform: scale(1) rotate(-45deg); }
      50% { transform: scale(1.1) rotate(-45deg); }
      100% { transform: scale(1) rotate(-45deg); }
    }

    #message {
      margin-top: 20px;
      font-size: 18px;
      font-weight: bold;
      color: #b22222;
    }

    .error {
      color: red;
      margin-top: 10px;
    }
  </style>
</head>
<body>

  <!-- Login Box -->
  <div class="login-box" id="loginBox">
    <h2>Login to My Heart</h2>
    <form onsubmit="login(event)">
      <input type="text" id="username" placeholder="Your Name" required>
      <input type="password" id="password" placeholder="Secret Key" required>
      <button type="submit">Enter</button>
      <div class="error" id="errorMsg"></div>
    </form>
  </div>

  <!-- Heart Page -->
  <div class="heart-container" id="heartContainer">
    <h1>Welcome to My Heart</h1>
    <div class="heart" onclick="connectHeart()"></div>
    <p id="message"></p>
    <audio id="loveSong" src="https://www.jiosaavn.com/song/die-with-a-smile/JgklWSZ6f0E"></audio>
  </div>

  <script>
    function login(event) {
      event.preventDefault();
      const password = document.getElementById("password").value;
      const errorMsg = document.getElementById("errorMsg");

      if (password === "iloveyourashu") {
        document.getElementById("loginBox").style.display = "none";
        document.getElementById("heartContainer").style.display = "block";
      } else {
        errorMsg.textContent = "Incorrect password. Try again!";
      }
    }

    function connectHeart() {
      document.getElementById("message").textContent = "Heart Connected Successfully!";
      document.getElementById("loveSong").play();
    }
  </script>

</body>
</html>
