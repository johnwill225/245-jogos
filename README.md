<!DOCTYPE html><html lang="pt">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>246 Jogos - Plataforma 2D</title>
    <link rel="stylesheet" href="styles/style.css">
    <script src="https://cdnjs.cloudflare.com/ajax/libs/phaser/3.60.0/phaser.min.js"></script>
</head>
<body>
    <h1>Bem-vindo ao 246 Jogos!</h1>
    <p>Jogue incríveis jogos de plataforma diretamente no seu navegador!</p><div class="game-grid">
    <div class="game-card" onclick="startGame1()">
        <img src="assets/imagens/plataforma1.jpg" alt="Jogo de Plataforma 1">
        <p>Jogo de Plataforma 1</p>
    </div>
    <div class="game-card" onclick="startGame2()">
        <img src="assets/imagens/plataforma2.jpg" alt="Jogo de Plataforma 2">
        <p>Jogo de Plataforma 2</p>
    </div>
    <div class="game-card" onclick="startGame3()">
        <img src="assets/imagens/corrida.jpg" alt="Jogo de Corrida">
        <p>Jogo de Corrida</p>
    </div>
    <div class="game-card" onclick="startGame4()">
        <img src="assets/imagens/labirinto.jpg" alt="Jogo do Labirinto">
        <p>Jogo do Labirinto</p>
    </div>
</div>

<div id="gameContainer"></div>

<script>
    function clearGame() {
        const container = document.getElementById('gameContainer');
        container.innerHTML = "";
        container.style.display = 'block';
    }

    function startGame1() {
        clearGame();
        const container = document.getElementById('gameContainer');
        container.innerHTML = '<p>Jogo de Plataforma 1 iniciado! (Phaser pode ser adicionado aqui)</p>';
    }

    function startGame2() {
        clearGame();
        const container = document.getElementById('gameContainer');
        container.innerHTML = '<p>Jogo de Plataforma 2 em desenvolvimento.</p>';
    }

    function startGame3() {
        clearGame();
        const container = document.getElementById('gameContainer');
        container.innerHTML = '<p>Jogo de Corrida em desenvolvimento.</p>';
    }

    function startGame4() {
        clearGame();
        const container = document.getElementById('gameContainer');
        container.innerHTML = '<p>Jogo do Labirinto em desenvolvimento.</p>';
    }
</script>

<footer>
    <p>246 Jogos - Criado por João, Pedro e Olavo</p>
</footer>

</body>
</html>
