# for-yiyi
VAINAS LINDAS
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Para ti, Yiyi 💚</title>
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;600&display=swap" rel="stylesheet">
  <style>
    * {
      box-sizing: border-box;
      transition: all 0.3s ease;
    }

    body {
      margin: 0;
      padding: 0;
      font-family: 'Poppins', sans-serif;
      background: linear-gradient(160deg, #fff0f5, #ffffe0);
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      height: 100vh;
      overflow: hidden;
      text-align: center;
      cursor: pointer;
    }

    #mensaje {
      font-size: 2rem;
      color: #5a189a;
      padding: 20px;
      border-radius: 20px;
      background: rgba(255, 255, 255, 0.9);
      box-shadow: 0 6px 12px rgba(0, 0, 0, 0.15);
      max-width: 90%;
      margin-bottom: 20px;
    }

    #mensaje:hover {
      transform: scale(1.03);
    }

    .contador {
      font-size: 1.1rem;
      margin-bottom: 20px;
      color: #7b2cbf;
    }

    .boton {
      background: #ff66a5;
      color: #fff;
      padding: 12px 24px;
      border: none;
      border-radius: 20px;
      font-size: 1rem;
      cursor: pointer;
      display: flex;
      align-items: center;
      gap: 10px;
      box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
    }

    .boton:hover {
      background: #e05595;
    }

    .decoracion {
      position: absolute;
      pointer-events: none;
      z-index: -1;
      opacity: 0.6;
    }

    .osito { top: 10%; left: 10%; width: 100px; }
    .abeja { top: 20%; right: 10%; width: 60px; }
    .flor { bottom: 10%; left: 20%; width: 80px; }
    .flor2 { bottom: 5%; right: 20%; width: 70px; }

    .corazon {
      position: fixed;
      color: #ff6b81;
      font-size: 24px;
      animation: flotar 4s ease-in-out infinite;
      user-select: none;
      pointer-events: none;
    }

    @keyframes flotar {
      0% { transform: translateY(0) scale(1); opacity: 1; }
      100% { transform: translateY(-100vh) scale(0.5); opacity: 0; }
    }

    @media (max-width: 600px) {
      #mensaje { font-size: 1.5rem; padding: 15px; }
      .boton { padding: 10px 18px; font-size: 0.9rem; }
    }
  </style>
</head>
<body onclick="mostrarFrase()">
  <div id="mensaje">Toca la pantalla para ver algo bonito 💚</div>
  <div class="contador" id="contadorDias"></div>
  <button class="boton" onclick="enviarMensaje(event)">💌 Déjame un mensajito</button>

  <!-- Decoraciones -->
  <img src="https://i.ibb.co/2WqjDpn/bear.png" class="decoracion osito" />
  <img src="https://i.ibb.co/2KpRhR6/bee.png" class="decoracion abeja" />
  <img src="https://i.ibb.co/JrH0dm2/flower.png" class="decoracion flor" />
  <img src="https://i.ibb.co/pJphJY3/flower2.png" class="decoracion flor2" />

  <!-- Música -->
  <audio id="musica" autoplay loop>
    <source src="https://www.bensound.com/bensound-music/bensound-romantic.mp3" type="audio/mp3">
    Tu navegador no soporta audio.
  </audio>

  <script>
    const frases = [
      "Eres lo mejor del mundo, Anyelis 💚",
      "Tus ojos verdes me hacen soñar despierto 💫",
      "Eres más hermosa que un campo lleno de flores 🌸",
      "Tu sonrisa es mi lugar feliz 🐻",
      "Si tuviera que elegir de nuevo, te volvería a escoger 💌",
      "Eres mi princesa de cuento y yo tu osito 🧸",
      "Tu voz es mi canción favorita 🎶",
      "No hay un día en que no piense en ti 💭",
      "Tu dulzura es más fuerte que mil chocolates 🍫",
      "Yiyi, tú haces que todo valga la pena 💘"
    ];

    function mostrarFrase() {
      const mensaje = document.getElementById('mensaje');
      mensaje.textContent = frases[Math.floor(Math.random() * frases.length)];
      lanzarCorazon();
    }

    function enviarMensaje(event) {
      event.stopPropagation();
      window.open('https://wa.me/18291234567?text=Hola+mi+amor+💌', '_blank');
    }

    function actualizarContador() {
      const inicio = new Date("2024-09-27");
      const hoy = new Date();
      const dias = Math.floor((hoy - inicio) / (1000 * 60 * 60 * 24));
      document.getElementById('contadorDias').textContent = `Han pasado ${dias} días desde que te conocí 💞`;
    }

    function lanzarCorazon() {
      const corazon = document.createElement('div');
      corazon.className = 'corazon';
      corazon.style.left = Math.random() * 100 + 'vw';
      corazon.style.top = '100vh';
      corazon.textContent = '💖';
      document.body.appendChild(corazon);
      setTimeout(() => corazon.remove(), 4000);
    }

    actualizarContador();
  </script>
</body>
</html>
