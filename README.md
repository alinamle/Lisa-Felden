<html lang="de">
<head>
  <meta charset="UTF-8">
  <title>So klingt Lisa Felden</title>
  <style>
    body {
      margin: 0;
      height: 100vh;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      background-color: #fff;
      font-family: system-ui, sans-serif;
      gap: 20px;
    }

    h1 {
      font-size: 20px;
      color: #333;
    }

    .play-button {
      background-color: #f3eeee;
      color: black;
      border: none;
      border-radius: 8px;
      padding: 16px 24px;
      font-size: 16px;
      font-weight: bold;
      display: flex;
      align-items: center;
      gap: 12px;
      cursor: pointer;
      box-shadow: 0 4px 8px rgba(0,0,0,0.1);
    }

    .play-button svg {
      width: 20px;
      height: 20px;
      fill: black;
    }
  </style>
</head>
<body>

  <h1>So klingt Lisa Felden</h1>

  <button class="play-button" onclick="toggleAudio()">
    <svg id="play-icon" viewBox="0 0 24 24"><path d="M8 5v14l11-7z"/></svg>
    Play
  </button>

  <audio id="audio">
    <source src="LisaFelden.mp3" type="audio/mpeg">
  </audio>

  <script>
    const audio = document.getElementById('audio');
    const playIcon = document.getElementById('play-icon');

    function toggleAudio() {
      if (audio.paused) {
        audio.play();
        playIcon.innerHTML = '<path d="M6 4h4v16H6zm8 0h4v16h-4z"/>'; // Pause
      } else {
        audio.pause();
        playIcon.innerHTML = '<path d="M8 5v14l11-7z"/>'; // Play
      }
    }

    audio.addEventListener('ended', () => {
      playIcon.innerHTML = '<path d="M8 5v14l11-7z"/>';
    });
  </script>

</body>
</html>
