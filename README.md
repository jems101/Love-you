# Love-you
For my love ❤️
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>3D I Love You Animation</title>
  <style>
    body {
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      background: #111;
      margin: 0;
      font-family: 'Arial', sans-serif;
    }

    .container {
      text-align: center;
      perspective: 1000px;
    }

    .heart-button {
      background: none;
      border: none;
      cursor: pointer;
      outline: none;
      margin-bottom: 20px;
    }

    .heart {
      width: 100px;
      height: 90px;
      position: relative;
      background: red;
      transform: rotate(-45deg);
      animation: pulse 1s infinite;
    }

    .heart::before,
    .heart::after {
      content: "";
      width: 100px;
      height: 90px;
      position: absolute;
      background: red;
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

    .message {
      color: white;
      font-size: 2em;
      transform: rotateY(90deg);
      transition: transform 1s, opacity 1s;
      opacity: 0;
    }

    .message.show {
      transform: rotateY(0deg);
      opacity: 1;
    }

    @keyframes pulse {
      0% {
        transform: scale(1) rotate(-45deg);
      }
      50% {
        transform: scale(1.1) rotate(-45deg);
      }
      100% {
        transform: scale(1) rotate(-45deg);
      }
    }
  </style>
</head>
<body>
  <div class="container">
    <button class="heart-button" onclick="showMessage()">
      <div class="heart"></div>
    </button>
    <div class="message" id="loveMessage">I Love You</div>
  </div>

  <script>
    function showMessage() {
      const message = document.getElementById("loveMessage");
      message.classList.toggle("show");
    }
  </script>
</body>
</html>