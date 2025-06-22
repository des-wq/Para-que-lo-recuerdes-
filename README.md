# Para-que-lo-recuerdes-
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>Para que lo recuerdes</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <div class="container">
    <div class="heart" onclick="transformar()"></div>
    <div class="mensaje" id="mensaje">
      <p>Contigo descubrí que el verdadero hogar está en el corazón de quien amas.</p>
    </div>
    <div class="contador" id="contador">
      Mi amor por ti comenzó hace…<br>
      <span id="tiempo">000 días 00 horas 00 minutos 00 segundos</span>
    </div>
  </div>

  <script>
    const inicio = new Date("2024-06-21T00:00:00"); // Cambialo si querés

    function actualizarTiempo() {
      const ahora = new Date();
      const diff = ahora - inicio;

      const dias = Math.floor(diff / (1000 * 60 * 60 * 24));
      const horas = Math.floor((diff / (1000 * 60 * 60)) % 24);
      const minutos = Math.floor((diff / (1000 * 60)) % 60);
      const segundos = Math.floor((diff / 1000) % 60);

      document.getElementById("tiempo").innerText = 
        `${dias} días ${horas} horas ${minutos} minutos ${segundos} segundos`;
    }

    function transformar() {
      const contenedor = document.querySelector('.container');
      contenedor.classList.add('transformado');
      const mensaje = document.getElementById("mensaje");
      mensaje.style.display = "block";
      for (let i = 0; i < 50; i++) {
        let corazon = document.createElement("div");
        corazon.className = "falling-heart";
        corazon.style.left = Math.random() * 100 + "vw";
        corazon.style.animationDuration = (2 + Math.random() * 3) + "s";
        contenedor.appendChild(corazon);
      }
    }

    setInterval(actualizarTiempo, 1000);
    actualizarTiempo();
  </script>
</body>
</html>
