<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Para ti</title>

  <style>
    body {
      margin: 0;
      min-height: 100vh;
      font-family: Arial, sans-serif;
      overflow: hidden;
      color: white;
    }

    /* ---------- PANTALLA INICIAL ---------- */
    .intro {
      position: fixed;
      inset: 0;
      background: #f5f0e6;
      display: flex;
      justify-content: center;
      align-items: center;
      z-index: 10;
    }

    .intro button {
      padding: 18px 40px;
      font-size: 20px;
      border-radius: 35px;
      border: none;
      background: #e8dcc8;
      color: #333;
      cursor: pointer;
      box-shadow: 0 10px 25px rgba(0,0,0,0.15);
      transition: transform 0.2s, box-shadow 0.2s;
    }

    .intro button:hover {
      transform: scale(1.05);
      box-shadow: 0 15px 30px rgba(0,0,0,0.2);
    }

    /* ---------- CONTENIDO PRINCIPAL ---------- */
    .main {
      display: none;
      min-height: 100vh;
      background: linear-gradient(180deg, #1c1c2b, #2f2f4f);
      display: flex;
      justify-content: center;
      align-items: center;
    }

    .container {
      background: rgba(255, 255, 255, 0.14);
      backdrop-filter: blur(8px);
      padding: 28px;
      border-radius: 20px;
      width: 90%;
      max-width: 420px;
      text-align: center;
      box-shadow: 0 0 25px rgba(0,0,0,0.4);
      animation: fadeIn 1.8s ease;
      z-index: 2;
    }

    h1 {
      font-size: 24px;
      margin-bottom: 12px;
    }

    p {
      font-size: 16px;
      line-height: 1.5;
    }

    .tulips {
      font-size: 26px;
      margin: 10px 0;
    }

    @keyframes fadeIn {
      from {
        opacity: 0;
        transform: translateY(15px);
      }
      to {
        opacity: 1;
        transform: translateY(0);
      }
    }

    /* ---------- PARTÍCULAS ---------- */
    .particle {
      position: absolute;
      font-size: 16px;
      opacity: 0.8;
      animation: floatUp linear forwards;
      pointer-events: none;
    }

    @keyframes floatUp {
      from {
        transform: translateY(0);
        opacity: 1;
      }
      to {
        transform: translateY(-120vh);
        opacity: 0;
      }
    }

    @media (max-width: 360px) {
      h1 { font-size: 22px; }
      p { font-size: 15px; }
    }
  </style>
</head>

<body>

  <!-- PANTALLA INICIAL -->
  <div class="intro" id="intro">
    <button onclick="startExperience()">Para ti</button>
  </div>

  <!-- CONTENIDO PRINCIPAL -->
  <div class="main" id="main">
    <div class="container">
      <div class="tulips">🌷 🌷 🌷</div>

      <h1>Holaaas</h1>

      <p>
        Quise hacer esto simple.<br>
        A veces me cuesta decir las cosas bien,
        pero quería que supieras cómo me siento.
      </p>

      <p>
        He pensado en lo que dijiste. Creo que a distancia me costó saber cómo tratarte y cómo comunicarme contigo. No porque no me importaras, sino porque no supe cómo hacerlo bien. <br>
        Pero lo que siento por ti en sincero y verdadero, yo no soy un tipo de una en otra, porque me criaron correctamente y me enseñaron a amar a una sola persona.
     <p>
     Quiero que sepas que esto no va a ser lo único que haré por ti.
     </p> 

      <div class="tulips">🌷 🌷 🌷</div>
    </div>
  </div>

  <!-- MÚSICA -->
  <audio id="music" loop>
    <source src="Harvey.mp3" type="audio/mpeg">
  </audio>

  <script>
    const intro = document.getElementById("intro");
    const main = document.getElementById("main");
    const music = document.getElementById("music");

    function startExperience() {
      intro.style.display = "none";
      main.style.display = "flex";
      music.volume = 0.4;
      music.play();
      startParticles();
    }

    // Partículas
    const symbols = ["💗", "⭐", "💫"];

    function startParticles() {
      setInterval(() => {
        const particle = document.createElement("div");
        particle.className = "particle";
        particle.textContent = symbols[Math.floor(Math.random() * symbols.length)];
        particle.style.left = Math.random() * 100 + "vw";
        particle.style.bottom = "-20px";
        particle.style.animationDuration = (5 + Math.random() * 3) + "s";
        document.body.appendChild(particle);

        setTimeout(() => particle.remove(), 8000);
      }, 600);
    }
  </script>

</body>
</html>
