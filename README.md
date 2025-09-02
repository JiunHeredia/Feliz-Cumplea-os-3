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
      background: linear-gradient(to top right, #fceabb, #f8b500);
      font-family: 'Comic Sans MS', cursive, sans-serif;
    }
    /* Búho */
    .owl {
      position: relative;
      width: 220px;
      height: 260px;
      margin: auto;
      background: #8b5e3c; /* marrón */
      border-radius: 50% 50% 45% 45%;
      box-shadow: 0 4px 15px rgba(0,0,0,0.3);
      cursor: pointer;
      transition: transform 0.3s ease;
    }
    .owl:hover { transform: scale(1.05); }

    /* Orejitas */
    .ear {
      position: absolute;
      width: 50px;
      height: 50px;
      background: #8b5e3c;
      top: -25px;
      border-radius: 50%;
    }
    .ear.left { left: 15px; transform: rotate(-20deg); }
    .ear.right { right: 15px; transform: rotate(20deg); }

    /* Barriguita */
    .belly {
      position: absolute;
      bottom: 0;
      left: 50%;
      transform: translateX(-50%);
      width: 140px;
      height: 120px;
      background: #d9b08c; /* color más claro */
      border-radius: 70% 70% 50% 50%;
    }

    /* Ojos */
    .eye {
      width: 65px;
      height: 65px;
      background: white;
      border-radius: 50%;
      position: absolute;
      top: 60px;
      border: 3px solid #5a3a23;
    }
    .eye.left { left: 30px; }
    .eye.right { right: 30px; }
    .pupil {
      width: 28px;
      height: 28px;
      background: black;
      border-radius: 50%;
      position: relative;
      top: 18px;
      left: 18px;
      animation: blink 4s infinite;
    }
    @keyframes blink {
      0%, 92%, 100% { transform: scaleY(1); }
      95% { transform: scaleY(0.1); }
    }

    /* Pico */
    .beak {
      width: 35px;
      height: 45px;
      background: orange;
      clip-path: polygon(50% 0, 0 100%, 100% 100%);
      position: absolute;
      top: 135px;
      left: 92px;
    }

    /* Alas */
    .wing {
      position: absolute;
      width: 85px;
      height: 130px;
      background: #6d4c3d;
      border-radius: 50%;
      top: 80px;
    }
    .wing.left { left: -45px; transform: rotate(-15deg); }
    .wing.right { right: -45px; transform: rotate(15deg); }
  </style>
</head>
<body class="flex flex-col items-center justify-center min-h-screen text-center">

  <!-- Música piano suave -->
  <audio id="bg-music" autoplay loop hidden>
    <source src="https://www.bensound.com/bensound-music/bensound-tenderness.mp3" type="audio/mp3">
    Tu navegador no soporta audio en HTML5.
  </audio>

  <h1 class="text-5xl font-bold mb-6 animate-bounce">🎂 ¡Feliz Cumpleaños, amiga! 🎂</h1>

  <!-- Búho -->
  <div class="owl" id="owl">
    <div class="ear left"></div>
    <div class="ear right"></div>
    <div class="eye left"><div class="pupil"></div></div>
    <div class="eye right"><div class="pupil"></div></div>
    <div class="beak"></div>
    <div class="wing left"></div>
    <div class="wing right"></div>
    <div class="belly"></div>
  </div>

  <p class="mt-6 text-lg">Haz clic en el búho para descubrir tu mensaje secreto 🦉✨</p>

  <div id="mensaje" class="hidden mt-8 p-6 max-w-xl bg-white rounded-2xl shadow-lg text-purple-900 text-xl leading-relaxed">
    🎉 ¡Feliz cumpleaños, brillante universitaria!  
    ✨ Tu inteligencia y dedicación son inspiración para todos.  
    📚 Hoy celebramos no solo tu vida, sino también todo el esfuerzo y pasión que te hacen única.  
    🌟 Que este nuevo ciclo esté lleno de logros, alegrías y aventuras maravillosas.  
    💖 Gracias por ser una amiga tan especial, ¡te mereces lo mejor del mundo!  
  </div>

  <script>
    const owl = document.getElementById("owl");
    const mensaje = document.getElementById("mensaje");

    owl.addEventListener("click", () => {
      mensaje.classList.toggle("hidden");

      if (!mensaje.classList.contains("hidden")) {
        confetti({
          particleCount: 180,
          spread: 120,
          origin: { y: 0.6 }
        });
      }
    });
  </script>
</body>
</html>
