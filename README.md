<html lang="de">
<head>
  <meta charset="UTF-8">
  <title>So klingt Lisa Felden</title>
  <style>
    body {
      margin: 0;
      height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      background-color: #fff;
      font-family: system-ui, sans-serif;
    }

    .play-button {
      background-color: #ff3c00;
      color: white;
      border: none;
      border-radius: 8px;
      padding: 16px 24px;
      font-size: 20px;
      font-weight: bold;
      display: flex;
      align-items: center;
      gap: 12px;
      cursor: pointer;
      box-shadow: 0 4px 8px rgba(0,0,0,0.2);
      transition: background-color 0.2s;
    }

    .play-button:hover {
      background-color: #e03200;
    }

    .play-button svg {
      width: 20px;
      height: 20px;
      fill: white;
    }

    audio {
      display: none;
    }
  </style>
</head>
<body>

  <button class="play-button" onclick="document.getElementById('audio').play()">
    <svg viewBox="0 0 24 24"><path d="M8 5v14l11-7z"/></svg>
    So klingt Lisa Felden
  </button>

  <audio id="audio">
    <source src="LisaFelden.mp3" type="audio/mpeg">
  </audio>

</body>
</html>
