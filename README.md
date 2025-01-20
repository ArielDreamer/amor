<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Contagem Progressiva</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      text-align: center;
      background-color: #5C2438;
      color: #F4CAB8;
      margin: 0;
      padding: 0;
    }
    .container {
      margin-top: 50px;
    }
    .timer {
      font-size: 2em;
      font-weight: bold;
      margin: 20px 0;
    }
  </style>
</head>
<body>
  <div class="container">
    <h1>Te amo há:</h1>
    <div class="timer" id="timer">Calculando...</div>
  </div>
  <script>
    // Data de início do relacionamento
    const startDate = new Date("2024-06-12T00:00:00");

    function updateTimer() {
      const now = new Date();
      const elapsedTime = now - startDate; // Diferença em milissegundos

      const years = Math.floor(elapsedTime / (1000 * 60 * 60 * 24 * 365.25));
      const days = Math.floor((elapsedTime % (1000 * 60 * 60 * 24 * 365.25)) / (1000 * 60 * 60 * 24));
      const hours = Math.floor((elapsedTime / (1000 * 60 * 60)) % 24);
      const minutes = Math.floor((elapsedTime / (1000 * 60)) % 60);
      const seconds = Math.floor((elapsedTime / 1000) % 60);

      document.getElementById("timer").innerText = 
        `${years} anos, ${days} dias, ${hours} horas, ${minutes} minutos e ${seconds} segundos`;
    }

    // Atualiza o contador a cada segundo
    setInterval(updateTimer, 1000);

    // Atualiza o contador imediatamente ao carregar a página
    updateTimer();
  </script>
</body>
</html>
