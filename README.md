<html lang="de">
<head>
  <meta charset="UTF-8">
  <style>
    body {
      margin: 0;
      height: 100vh;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      background-color: #f5f5f5;
      font-family: serif;
    }

    h1 {
      margin-bottom: 40px;
      font-size: 18px;
      color: #333;
      text-align: center;
    }

    audio {
      width: auto;
      height: 80px;
      background: none;
      outline: none;
    }

    audio::-webkit-media-controls-panel {
      transform: scale(2.5);
      transform-origin: center;
    }
  </style>
</head>
<body>
  <h1>So klingt Julia Rammler</h1>
  <audio controls>
    <source src="JuliaRammler.mp3" type="audio/mpeg">
  </audio>
</body>
</html>
