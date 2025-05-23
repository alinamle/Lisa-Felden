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

    .audio-player {
      background-color: #ff3c00;
      color: white;
      border: none;
      border-radius: 8px;
      padding: 16px 24px;
      display: flex;
      align-items: center;
      gap: 16px;
      box-shadow: 0 4px 8px rgba(0,0,0,0.2);
    }

    .audio-player button {
      background: none;
      border: none;
      cursor: pointer;
      padding: 0;
    }

    .audio-player svg {
      width: 24px;
      height: 24px;
      fill: white;
    }

    .audio-player input[type="range"] {
      accent-color: white;
      height: 4px;
      flex-grow: 1;
    }

    .volume {
      width: 80px;
    }

    input[type=range]::-webkit-slider-thumb {
      background: white;
    }
  </style>
</head>
<body>

  <h1>So klingt Lisa Felden</h1>

  <div class="audio-player">
    <button onclick="toggleAudio()">
      <svg id="play-icon" viewBox="0 0 24 24"><path d="M8 5v14l11-7z"/></svg>
    </button>
    <input type="range" id="seekbar" value="0" step="1">
    <input type="range" id="volume" class="volume" min="0" max="1" step="0.01" value="1">
  </div>

  <audio id="audio">
    <source src="LisaFelden.mp3" type="audio/mpeg">
  </audio>

  <script>
    const audio = document.getElementById('audio');
    const playIcon = document.getElementById('play-icon');
    const seekbar = document.getElementById('seekbar');
    const volume = document.getElementById('volume');

    function toggleAudio() {
      if (audio.paused) {
        audio.play();
        playIcon.innerHTML = '<path d="M6 4h4v16H6zm8 0h4v16h-4z"/>'; // Pause
      } else {
        audio.pause();
        playIcon.innerHTML = '<path d="M8 5v14l11-7z"/>'; // Play
      }
    }

    audio.addEventListener('timeupdate', () => {
      seekbar.max = audio.duration;
      seekbar.value = audio.currentTime;
    });

    seekbar.addEventListener('input', () => {
      audio.currentTime = seekbar.value;
    });

    volume.addEventListener('input', () => {
      audio.volume = volume.value;
    });

    audio.addEventListener('ended', () => {
      playIcon.innerHTML = '<path d="M8 5v14l11-7z"/>';
    });
  </script>

</body>
</html>
