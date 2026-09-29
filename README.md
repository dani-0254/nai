<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Una cartita </title>

  <style>
    * {
      box-sizing: border-box;
    }

    body {
      margin: 0;
      min-height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      background: linear-gradient(135deg, #ffd6e7, #fff0f5);
      font-family: Arial, sans-serif;
      overflow: hidden;
    }

    .contenedor {
      text-align: center;
    }

    .sobre {
      position: relative;
      width: 320px;
      height: 210px;
      background: #ff8fab;
      border-radius: 8px;
      cursor: pointer;
      box-shadow: 0 15px 35px rgba(0, 0, 0, 0.2);
      transition: transform 0.3s;
    }

    .sobre:hover {
      transform: scale(1.03);
    }

    /* Triángulo de la parte delantera */
    .sobre::before {
      content: "";
      position: absolute;
      bottom: 0;
      left: 0;
      width: 0;
      height: 0;
      border-left: 160px solid transparent;
      border-right: 160px solid transparent;
      border-bottom: 120px solid #ff7096;
      z-index: 3;
    }

    /* Solapa */
    .solapa {
      position: absolute;
      top: 0;
      left: 0;
      width: 0;
      height: 0;
      border-left: 160px solid transparent;
      border-right: 160px solid transparent;
      border-top: 115px solid #ff5c8a;
      transform-origin: top;
      transition: transform 0.8s ease;
      z-index: 4;
    }

    /* Carta */
    .carta {
      position: absolute;
      left: 20px;
      bottom: 10px;
      width: 280px;
      height: 180px;
      background: white;
      border-radius: 5px;
      display: flex;
      justify-content: center;
      align-items: center;
      padding: 20px;
      z-index: 2;
      transition: transform 0.8s ease;
      box-shadow: 0 5px 15px rgba(0, 0, 0, 0.15);
    }

    .mensaje {
      color: #e6396f;
      font-size: 24px;
      font-weight: bold;
    }

    .texto {
      margin-top: 25px;
      color: #a8325c;
      font-size: 18px;
    }

    /* Cuando se abre */
    .sobre.abierto .solapa {
      transform: rotateX(180deg);
      z-index: 1;
    }

    .sobre.abierto .carta {
      transform: translateY(-150px);
      z-index: 5;
    }

    .sobre.abierto {
      margin-top: 150px;
    }
  </style>
</head>

<body>

  <div class="contenedor">

    <div class="sobre" id="sobre" onclick="abrirCarta()">

      <div class="solapa"></div>

      <div class="carta">
        <div class="mensaje">
          hola mundo! JSJSJJS 
        </div>
      </div>

    </div>

    <div class="texto" id="texto">
      Haz clic en el sobre para abrir la carta
    </div>

  </div>

  <script>
    function abrirCarta() {
      const sobre = document.getElementById("sobre");
      const texto = document.getElementById("texto");

      sobre.classList.toggle("abierto");

      if (sobre.classList.contains("abierto")) {
        texto.textContent = " ¡Carta abierta!";
      } else {
        texto.textContent = " Haz clic en el sobre para abrir la carta";
      }
    }
  </script>

</body>
</html>
