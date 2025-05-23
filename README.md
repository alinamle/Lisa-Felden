<html lang="de">
<head>
  <meta charset="UTF-8">
  <style>
 @font-face {
  font-family: 'MinionPro';
  src: url('MinionPro-Regular.woff2') format('woff2');
  font-weight: normal;
  font-style: normal;
}

    body {
      margin: 0;
      height: 100vh;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      font-family: 'MinionPro', serif;
      background-color: #f5f5f5;
    }

    h1 {
      margin-bottom: 30px;
      font-size: 20px;
      color: #333;
      text-align: center;
    }

    audio::-webkit-media-controls-panel {
      transform: scale(2.5); /* Vergrößert den Button */
      transform-origin: center;
    }

    audio {
      width: auto;
      height: 50px;
      background: none;
      outline: none;
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
