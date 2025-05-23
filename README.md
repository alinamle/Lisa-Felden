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
      flex-direction: column;
      gap: 20px;
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
      width: 300px;
    }
  </style>
</head>
<body>

  <button class="play-button" onclick="toggleAudio()">
    <svg id="play-icon" viewBox="0 0 24 24"><path d="M8 5v14l11-7z"/></svg>
    <span id="button-text">So klingt Lisa Felden</span>
  </button>

  <audio id="audio" controls>
    <source src="LisaFelden.mp3" type="audio/mpeg">
    Dein Browser unterstützt das Audio-Element nicht.
  </audio>

  <script>
    const audio = document.getElementById('audio');
    const playIcon = document.getElementById('play-icon');
    const buttonText = document.getElementById('button-text');

    function toggleAudio() {
      if (audio.paused) {
        audio.play();
        playIcon.innerHTML = '<path d="M6 4h4v16H6zm8 0h4v16h-4z"/>'; // Pause-Symbol
      } else {
        audio.pause();
        playIcon.innerHTML = '<path d="M8 5v14l11-7z"/>'; // Play-Symbol
      }
    }

    // Reset Button Icon when audio ends
    audio.addEventListener('ended', () => {
      playIcon.innerHTML = '<path d="M8 5v14l11-7z"/>';
    });
  </script>

</body>
</html>
