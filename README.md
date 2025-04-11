<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>100 Razones por las que te amo</title>
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Pacifico&display=swap');

    * {
      box-sizing: border-box;
    }

    body {
      margin: 0;
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      background: linear-gradient(to bottom right, #ffdde1, #ee9ca7);
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      min-height: 100vh;
      overflow-x: hidden;
    }

    .heart {
      position: fixed;
      width: 20px;
      height: 20px;
      background: red;
      transform: rotate(45deg);
      animation: float 8s linear infinite;
      opacity: 0.6;
    }

    .heart::before,
    .heart::after {
      content: '';
      position: absolute;
      width: 20px;
      height: 20px;
      background: red;
      border-radius: 50%;
    }

    .heart::before {
      top: -10px;
      left: 0;
    }

    .heart::after {
      left: -10px;
      top: 0;
    }

    @keyframes float {
      0% {
        transform: translateY(100vh) rotate(45deg);
        opacity: 0.6;
      }
      100% {
        transform: translateY(-10vh) rotate(45deg);
        opacity: 0;
      }
    }

    #intro {
      font-family: 'Pacifico', cursive;
      font-size: 2rem;
      color: #d6336c;
      text-align: center;
      margin: 1.5rem;
      padding: 0 1rem;
      animation: fadeOut 2s 5s forwards;
      z-index: 1;
    }

    #subintro {
      font-size: 1.2rem;
      color: #6f1d1b;
      text-align: center;
      margin-bottom: 1.5rem;
      padding: 0 1rem;
      animation: fadeOut 2s 5s forwards;
      z-index: 1;
    }

    @keyframes fadeOut {
      to {
        opacity: 0;
        visibility: hidden;
      }
    }

    @keyframes popIn {
      0% {
        transform: scale(0.5);
        opacity: 0;
      }
      100% {
        transform: scale(1);
        opacity: 1;
      }
    }

    @keyframes sparkle {
      0%, 100% { box-shadow: 0 0 10px pink; }
      50% { box-shadow: 0 0 20px hotpink; }
    }

    #grid {
      display: none;
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(80px, 1fr));
      gap: 10px;
      width: 100%;
      max-width: 600px;
      padding: 20px;
      animation: popIn 1s ease-out;
      z-index: 1;
    }

    .box {
      aspect-ratio: 1 / 1;
      background-color: #ff8fab;
      border-radius: 15px;
      display: flex;
      align-items: center;
      justify-content: center;
      font-weight: bold;
      font-size: 1rem;
      color: white;
      cursor: pointer;
      transition: transform 0.3s, background-color 0.3s;
      text-align: center;
      padding: 8px;
      word-wrap: break-word;
      overflow: hidden;
      animation: sparkle 2s infinite;
    }

    .box:hover {
      transform: scale(1.05);
    }

    .opened {
      background-color: #fff0f5;
      color: #d6336c;
      font-size: 0.9rem;
      border: 2px dashed #d6336c;
      white-space: normal;
      overflow-wrap: break-word;
      animation: popIn 0.5s ease-out;
      animation-fill-mode: both;
    }

    @media (max-width: 600px) {
      #intro {
        font-size: 1.8rem;
      }
      #subintro {
        font-size: 1rem;
      }
      .box {
        font-size: 0.9rem;
        padding: 5px;
      }
    }

    .message {
      display: none;
      font-family: 'Pacifico', cursive;
      font-size: 2.5rem;
      color: #d6336c;
      text-align: center;
      margin-top: 2rem;
      padding: 1rem;
      animation: fadeInMessage 2s ease-in;
      z-index: 2;
    }

    @keyframes fadeInMessage {
      0% {
        opacity: 0;
        transform: scale(0.8);
      }
      100% {
        opacity: 1;
        transform: scale(1);
      }
    }
  </style>
</head>
<body>
  <div id="intro">Con mucho amor para ti, mi Ivannita ❤️</div>
  <div id="subintro">100 razones por las que te amo 🥰</div>
  <div id="grid"></div>
  <div class="message" id="finalMessage">
    <p>Te amo mucho, mi Ivannita. Gracias por todo lo que haces por mí, por todo lo que sigues haciendo. Eres mi todo y siempre estaré aquí, amándote más cada día.</p>
  </div>

  <script>
    const reasons = [
      "Tu sonrisa", "Tu ternura", "Tu paciencia", "Tu voz", "Tus abrazos", "Tu risa", "Tu mirada",
      "Tus mensajes lindos", "Tus detalles", "Tu apoyo", "Tu inteligencia", "Tus ocurrencias",
      "Tu forma de ver la vida", "Cómo me miras", "Tu forma de amar", "Tu dulzura", "Tu energía",
      "Tu compañía", "Tus locuras", "Tus caricias", "Tu olor", "Tu forma de hablar", "Tu lealtad",
      "Tu belleza", "Tus manos", "Tus besos", "Tu corazón", "Tu comprensión", "Tus valores",
      "Cómo me haces reír", "Cómo me entiendes", "Tu espontaneidad", "Tu confianza",
      "Lo bien que me haces sentir", "Tu forma de cuidar", "Tus ganas de crecer conmigo",
      "Tus sueños", "Tus palabras", "Tu forma de sorprenderme", "Lo orgullosa que eres de mí",
      "Tus metas", "Tus ideas", "Tu creatividad", "Tu perseverancia", "Tu fuerza",
      "Tu autenticidad", "Tu ternura infinita", "Tu forma de ser única", "Tus gestos lindos",
      "Cómo me motivas", "Cómo haces especial cada día", "Tu alma hermosa", "Tu alegría",
      "Cómo haces que me sienta amado", "Tus bromas", "Tus miradas cómplices",
      "Tu forma de hacerme sentir seguro", "Tu amor incondicional", "Tus palabras de aliento",
      "Tu forma de decir mi nombre", "Tus ocurrencias tiernas", "Tus silencios a mi lado",
      "Tu risa contagiosa", "Tus ocurrencias locas", "Tu manera de darme paz",
      "Cómo estás en los momentos difíciles", "Cómo celebras mis logros", "Tu cariño",
      "Cómo me haces sentir especial", "Cómo estás ahí siempre", "Cómo compartes conmigo",
      "Cómo confías en mí", "Tus manías lindas", "Tus historias", "Tu forma de dormir",
      "Cómo me abrazas en silencio", "Tu cara de enojo linda", "Tus cejas cuando te sorprendes",
      "Cómo amas a los tuyos", "Tu espíritu fuerte", "Cómo bailas sin vergüenza",
      "Tu forma de luchar por lo que amas", "Cómo me inspiras", "Cómo me completas",
      "Tu forma de ver el amor", "Cómo haces que todo valga la pena", "Cómo sueñas conmigo",
      "Cómo construimos juntos", "Cómo me das paz", "Cómo me haces reír incluso en mis días malos",
      "Cómo me haces mejor persona", "Cómo haces que quiera ser mejor cada día",
      "Porque existes", "Porque me amas", "Porque eres tú", "Porque eres única",
      "Porque no hay nadie como tú", "Porque contigo todo es mejor",
      "Porque me haces feliz", "Porque eres mi todo", "Porque te amo sin razón",
      "Porque TE AMO"
    ];

    const grid = document.getElementById("grid");
    const finalMessage = document.getElementById("finalMessage");

    function createBoxes() {
      for (let i = 0; i < 100; i++) {
        const box = document.createElement("div");
        box.classList.add("box");
        box.textContent = i + 1;
        box.addEventListener("click", () => {
          if (!box.classList.contains("opened")) {
            box.classList.add("opened");
            box.textContent = reasons[i];
            checkCompletion();
          }
        });
        grid.appendChild(box);
      }
    }

    function createHearts() {
      for (let i = 0; i < 20; i++) {
        const heart = document.createElement("div");
        heart.classList.add("heart");
        heart.style.left = Math.random() * 100 + "vw";
        heart.style.animationDuration = (5 + Math.random() * 5) + "s";
        document.body.appendChild(heart);
      }
    }

    function checkCompletion() {
      const openedBoxes = document.querySelectorAll(".box.opened");
      if (openedBoxes.length === 100) {
        setTimeout(() => {
          grid.style.display = "none"; // Ocultar las cajas
          finalMessage.style.display = "block"; // Mostrar el mensaje final
        }, 1000); // Espera antes de cambiar de escena
      }
    }

    setTimeout(() => {
      document.getElementById("intro").style.display = 'none';
      document.getElementById("subintro").style.display = 'none';
      grid.style.display = 'grid';
      createBoxes();
    }, 6000);

    window.onload = createHearts;
  </script>
</body>
</html>
