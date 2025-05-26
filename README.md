<html lang="de">
<head>
  <meta charset="UTF-8">
  <title>So klingt Lisa Felden</title>
  <style>
    body {
      margin: 0;
      height: 100vh;
      background: #fff;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      font-family: sans-serif;
      gap: 30px;
    }

    h1 {
      font-size: 20px;
      color: #333;
    }

    .player-container {
      position: relative;
      width: 150px;
      height: 150px;
    }

    .progress-ring {
      transform: rotate(-90deg);
    }

    .progress-ring circle {
      fill: none;
      stroke: #f3eeee;
      stroke-width: 8;
      stroke-linecap: round;
    }

    .play-button {
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      width: 80px;
      height: 80px;
      background-color: #f3eeee;
      border-radius: 50%;
      border: none;
      display: flex;
      align-items: center;
      justify-content: center;
      cursor: pointer;
      box-shadow: 0 4px 10px rgba(0,0,0,0.1);
    }

    .play-button svg {
      width: 24px;
      height: 24px;
      fill: black;
    }
  </style>
</head>
<body>

  <h1>So klingt Lisa Felden</h1>

  <div class="player-container">
    <svg class="progress-ring" width="150" height="150">
      <circle id="progress-ring" cx="75" cy="75" r="65" stroke="#eee" />
    </svg>
    <button class="play-button" onclick="toggleAudio()">
      <svg id="play-icon" viewBox="0 0 24 24"><path d="M8 5v14l11-7z"/></svg>
    </button>
    <audio id="audio">
      <source src="LisaFelden.mp3" type="audio/mpeg">
    </audio>
  </div>

  <script>
    const audio = document.getElementById("audio");
    const playIcon = document.getElementById("play-icon");
    const progressCircle = document.getElementById("progress-ring");
    const radius = progressCircle.r.baseVal.value;
    const circumference = 2 * Math.PI * radius;

    progressCircle.style.strokeDasharray = `${circumference} ${circumference}`;
    progressCircle.style.strokeDashoffset = circumference;

    function setProgress(percent) {
      const offset = circumference - percent * circumference;
      progressCircle.style.strokeDashoffset = offset;
    }

    function toggleAudio() {
      if (audio.paused) {
        audio.play();
        playIcon.innerHTML = '<path d="M6 4h4v16H6zm8 0h4v16h-4z"/>'; // Pause
      } else {
        audio.pause();
        playIcon.innerHTML = '<path d="M8 5v14l11-7z"/>'; // Play
      }
    }

    audio.ontimeupdate = () => {
      const progress = audio.currentTime / audio.duration;
      setProgress(progress);
    };

    audio.onended = () => {
      playIcon.innerHTML = '<path d="M8 5v14l11-7z"/>'; // Reset to play
      setProgress(0);
    };
  </script>

</body>
</html>
    });
  </script>

</body>
</html>
