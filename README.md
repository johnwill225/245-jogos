<!DOCTYPE html><html lang="pt">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>246 Jogos</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 0;
      padding: 0;
      background: #f0f0f0;
      text-align: center;
    }
    header {
      background: #333;
      color: white;
      padding: 20px 0;
    }
    .games {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 20px;
      margin: 30px;
    }
    .game {
      background: white;
      border-radius: 10px;
      overflow: hidden;
      box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
      width: 280px;
      text-decoration: none;
      color: black;
      transition: transform 0.2s ease;
    }
    .game:hover {
      transform: scale(1.05);
    }
    .game img {
      width: 100%;
      height: auto;
      display: block;
    }
    footer {
      margin-top: 40px;
      padding: 20px;
      background: #333;
      color: white;
    }
  </style>
</head>
<body>
  <header>
    <h1>246 Jogos</h1>
    <p>Jogue grátis diretamente do seu navegador!</p>
  </header>  <div class="games">
    <a class="game" href="jogo1/index.html">
      <img src="https://i.imgur.com/xFYbpMD.png" alt="Jogo de Plataforma 1">
      <h3>Jogo de Plataforma 1</h3>
    </a>
    <a class="game" href="#" onclick="alert('Em breve!')">
      <img src="https://i.imgur.com/Fg9vOYZ.jpeg" alt="Jogo 2">
      <h3>Jogo de Corrida</h3>
    </a>
    <a class="game" href="#" onclick="alert('Em breve!')">
      <img src="https://i.imgur.com/95ZyW7W.jpeg" alt="Jogo 3">
      <h3>Labirinto Aventura</h3>
    </a>
  </div>  <footer>
    <p>246 Jogos - Criado por João, Pedro e Olavo</p>
  </footer>
</body>
</html>
