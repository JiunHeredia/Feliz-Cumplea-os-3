<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>🎉 Feliz Cumpleaños 🦉</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <script src="https://cdn.jsdelivr.net/npm/canvas-confetti@1.6.0/dist/confetti.browser.min.js"></script>
  <style>
    body {
      background: linear-gradient(to top right, #ffdde1, #ee9ca7);
      font-family: 'Comic Sans MS', cursive, sans-serif;
    }
    .owl {
      position: relative;
      width: 200px;
      height: 250px;
      margin: auto;
      background: #5d4d7a;
      border-radius: 50% 50% 45% 45%;
      box-shadow: 0 4px 10px rgba(0,0,0,0.3);
      cursor: pointer;
      transition: transform 0.3s ease;
    }
    .owl:hover { transform: scale(1.05); }
    .eye {
      width: 60px;
      height: 60px;
      background: white;
      border-radius: 50%;
      position: absolute;
      top: 50px;
    }
    .eye.left { left: 25px; }
    .eye.right { right: 25px; }
    .pupil {
      width: 25px;
      height: 25px;
      background: black;
      border-radius: 50%;
      position: relative;
      top: 18px;
      left: 18px;
      animation: blink 3s infinite;
    }
    @keyframes blink {
      0%, 90%, 100% { transform: scaleY(1); }
      95% { transform: scaleY(0.1); }
    }
    .beak {
      width: 30px;
      height: 40px;
      background: orange;
      clip-path: polygon(50% 0, 0 100%, 100% 100%);
      position: absolute;
      top: 120px;
      left: 85px;
    }
    .wing {
      position: absolute;
      width: 80px;
      height: 120px;
      background: #4a3c63;
      border-radius: 50%;
      top: 70px;
    }
    .wing.left { left: -40px; transform: rotate(-20deg); }
    .wing.right { right: -40px; transform: rotate(20deg); }
  </style>
</head>
<body class="flex flex-col items-center justify-center min-h-screen text-center">

  <!-- Música relajante de fondo -->
  <audio id="bg-music" autoplay loop hidden>
    <source src="https://www.bensound.com/bensound-music/bensound-sunny.mp3" type="audio/mp3">
    Tu navegador no soporta audio en HTML5.
  </audio>

  <h1 class="text-5xl font-bold mb-6 animate-bounce">🎂 ¡Feliz Cumpleaños, amiga! 🎂</h1>

  <!-- Búho -->
  <div class="owl" id="owl">
    <div class="eye left"><div class="pupil"></div></div>
    <div class="eye right"><div class="pupil"></div></div>
    <div class="beak"></div>
    <div class="wing left"></div>
    <div class="wing right"></div>
  </div>

  <p class="mt-6 text-lg">Haz clic en el búho para descubrir tu mensaje secreto 🦉✨</p>

  <div id="mensaje" class="hidden mt-8 p-6 max-w-xl bg-white rounded-2xl shadow-lg text-purple-900 text-xl leading-relaxed">
    🎉 ¡Feliz cumpleaños, genia universitaria!  
    ✨ Estoy muy orgulloso de lo que has logrado con tu inteligencia y esfuerzo.  
    📚 No cualquiera llega tan lejos, y tú lo haces con una sonrisa.  
    🌟 Que este nuevo año de vida te traiga aún más éxitos, aprendizajes y alegrías.  
    💖 Te mereces lo mejor, porque eres una amiga increíble y una persona brillante.  
  </div>

  <script>
    const owl = document.getElementById("owl");
    const mensaje = document.getElementById("mensaje");

    owl.addEventListener("click", () => {
      mensaje.classList.toggle("hidden");

      if (!mensaje.classList.contains("hidden")) {
        confetti({
          particleCount: 150,
          spread: 100,
          origin: { y: 0.6 }
        });
      }
    });
  </script>
</body>
</html>
