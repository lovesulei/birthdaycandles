<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <title>Birthday Cake 🎂</title>
    <link rel="stylesheet" href="style.css" />
    <link rel="preconnect" href="https://fonts.googleapis.com" />
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
    <link
      href="https://fonts.googleapis.com/css2?family=Pixelify+Sans:wght@400..700&display=swap"
      rel="stylesheet"
    />
    <style>
      #mainTitle {
        font-size: 32px;
        font-family: 'Pixelify Sans', sans-serif;
        margin-bottom: 8px;
      }

      #subTitle {
        font-size: 18px;
        font-family: 'Pixelify Sans', sans-serif;
        color: #555;
      }
    </style>
  </head>
  <body>
    <div class="container">
      <div id="birthdayText"></div>
      <div class="cake-container">
        <div class="cake" id="cake"></div>
      </div>
    </div>

    <script>
      // Read URL params
      const params = new URLSearchParams(window.location.search);
      const name = params.get("name") || "Friend";
      let candleCount = parseInt(params.get("candles")) || 4;
      candleCount = Math.min(Math.max(candleCount, 1), 30);

      const birthdayText = document.getElementById("birthdayText");
      birthdayText.innerHTML = `
        <div id="mainTitle">Happy Birthday, ${name}!</div>
        <div id="subTitle">Make a wish and blow candles.</div>
      `;

      const cake = document.getElementById("cake");

      const colors = [
        "green-candle",
        "purple-candle",
        "blue-candle",
        "yellow-candle",
      ];
      const CAKE_VISUAL_WIDTH = 35;

      function createCandles(count) {
        cake.innerHTML = "";
        const CANDLE_VISUAL_WIDTH = 2;
        const availableWidth = CAKE_VISUAL_WIDTH;
        const candlesPerRow = 6;
        const rowCount = Math.ceil(count / candlesPerRow);
        const shiftAmount = 4;

        for (let i = 0; i < count; i++) {
          const candle = document.createElement("div");
          candle.classList.add("candle");
          const colorClass = colors[Math.floor(Math.random() * colors.length)];
          candle.classList.add(colorClass);

          const row = Math.floor(i / candlesPerRow);
          const col = i % candlesPerRow;
          const totalCandlesInRow = Math.min(
            candlesPerRow,
            count - row * candlesPerRow
          );
          const rowSpacing = availableWidth / (totalCandlesInRow + 1);

          const leftBase = rowSpacing * (col + 1) - CANDLE_VISUAL_WIDTH / 2 + 5;
          const rowShift = row % 2 === 0 ? 0 : shiftAmount;

          candle.style.position = "absolute";
          candle.style.top = `${10 + row * 3}px`;
          candle.style.left = `${leftBase - rowShift + 4}px`;

          cake.appendChild(candle);
        }
      }

      createCandles(candleCount);

      // === Microphone / Blow Detection ===
      async function startMicDetection() {
        try {
          const stream = await navigator.mediaDevices.getUserMedia({
            audio: true,
          });
          const audioContext = new (window.AudioContext ||
            window.webkitAudioContext)();
          const source = audioContext.createMediaStreamSource(stream);
          const analyser = audioContext.createAnalyser();
          analyser.fftSize = 512;

          source.connect(analyser);

          const dataArray = new Uint8Array(analyser.frequencyBinCount);

          let blown = false;

          function detectBlow() {
            analyser.getByteFrequencyData(dataArray);

            let highFreqSum = 0;
            let lowFreqSum = 0;

            const midpoint = dataArray.length / 2;

            for (let i = 0; i < dataArray.length; i++) {
              if (i < midpoint) {
                lowFreqSum += dataArray[i];
              } else {
                highFreqSum += dataArray[i];
              }
            }

            const highAvg = highFreqSum / (dataArray.length / 2);
            const lowAvg = lowFreqSum / (dataArray.length / 2);

            const ratio = highAvg / (lowAvg + 1);

            const BLOW_RATIO_THRESHOLD = 0.5;

            if (ratio > BLOW_RATIO_THRESHOLD && !blown) {
              blown = true;
              blowOutCandles();
            }

            requestAnimationFrame(detectBlow);
          }

          detectBlow();
        } catch (err) {
          console.error("Mic access error:", err);
        }
      }

      function blowOutCandles() {
        const candles = document.querySelectorAll(".candle");
        candles.forEach((candle) => {
          const delay = Math.random() * 1000;
          setTimeout(() => {
            colors.forEach((color) => {
              if (candle.classList.contains(color)) {
                candle.classList.add("blown");
              }
            });
          }, delay);
        });

        // Update subTitle after short delay
        setTimeout(() => {
          const subTitle = document.getElementById("subTitle");
          subTitle.textContent = `Yayy! Wishing you the happiest birthday ever!! 🎉`;
        }, 1200);
      }

      startMicDetection();
    </script>
  </body>
</html>
