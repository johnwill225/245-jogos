<!DOCTYPE html><html lang="pt">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>245 Jogos - Plataforma 2D</title>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/phaser/3.60.0/phaser.min.js"></script>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            background-color: #f4f4f4;
        }
        .game-grid {
            display: flex;
            justify-content: center;
            gap: 20px;
            flex-wrap: wrap;
            margin: 20px;
        }
        .game-card {
            width: 250px;
            background: white;
            padding: 10px;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            cursor: pointer;
            transition: transform 0.2s;
        }
        .game-card:hover {
            transform: scale(1.05);
        }
        .game-card img {
            width: 100%;
            border-radius: 10px;
        }
        #gameContainer {
            width: 800px;
            height: 600px;
            margin: auto;
            border: 1px solid black;
            display: none;
        }
        footer {
            margin-top: 20px;
            padding: 10px;
            background: #ddd;
        }
    </style>
</head>
<body>
    <h1>Bem-vindo ao 245 Jogos!</h1>
    <p>Jogue incríveis jogos de plataforma diretamente no seu navegador!</p><div class="game-grid">
    <div class="game-card" onclick="startGame1()">
        <img src="https://via.placeholder.com/250x150?text=Plataforma+1" alt="Jogo de Plataforma 1">
        <p>Jogo de Plataforma 1</p>
    </div>
    <div class="game-card" onclick="startGame2()">
        <img src="https://via.placeholder.com/250x150?text=Plataforma+2" alt="Jogo de Plataforma 2">
        <p>Jogo de Plataforma 2</p>
    </div>
    <div class="game-card" onclick="startGame3()">
        <img src="https://via.placeholder.com/250x150?text=Corrida" alt="Jogo de Corrida">
        <p>Jogo de Corrida</p>
    </div>
    <div class="game-card" onclick="startGame4()">
        <img src="https://via.placeholder.com/250x150?text=Labirinto" alt="Jogo do Labirinto">
        <p>Jogo do Labirinto</p>
    </div>
</div>

<div id="gameContainer"></div>

<script>
    function startGame1() {
        document.getElementById('gameContainer').style.display = 'block';
        alert('Jogo de Plataforma 1 iniciado!');
    }
    
    function startGame2() {
        document.getElementById('gameContainer').style.display = 'block';
        alert('Jogo de Plataforma 2 em desenvolvimento!');
    }
    
    function startGame3() {
        document.getElementById('gameContainer').style.display = 'block';
        alert('Jogo de Corrida em desenvolvimento!');
    }
    
    function startGame4() {
        document.getElementById('gameContainer').style.display = 'block';
        alert('Jogo do Labirinto em desenvolvimento!');
    }
</script>

<footer>
    <p>245 Jogos - Criado por João, Pedro e Olavo</p>
</footer>

</body>
</html># 245-jogos
