<!DOCTYPE html><html lang="pt">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>246 Jogos - Plataforma 2D</title>
    <link rel="stylesheet" href="styles/style.css">
    <script src="https://cdn.jsdelivr.net/npm/phaser@3.60.0/dist/phaser.min.js"></script>
    <style>
        body {
            margin: 0;
            font-family: sans-serif;
            text-align: center;
        }
        .game-grid {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 20px;
            margin: 20px;
        }
        .game-card {
            width: 150px;
            cursor: pointer;
        }
        .game-card img {
            width: 100%;
            border-radius: 10px;
        }
        #gameContainer canvas {
            display: block;
            margin: 0 auto;
            max-width: 100%;
            height: auto !important;
        }
        #mobile-controls {
            display: none;
            margin-top: 10px;
        }
        #mobile-controls button {
            padding: 10px 20px;
            margin: 0 10px;
            font-size: 18px;
        }
        @media (max-width: 768px) {
            #mobile-controls {
                display: flex;
                justify-content: center;
            }
        }
    </style>
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
<div id="mobile-controls">
    <button id="leftBtn">◀</button>
    <button id="jumpBtn">⤒</button>
    <button id="rightBtn">▶</button>
</div>

<script>
    let currentGame;

    function clearGame() {
        if (currentGame) {
            currentGame.destroy(true);
            currentGame = null;
        }
        const container = document.getElementById('gameContainer');
        container.innerHTML = "";
        document.getElementById('mobile-controls').style.display = 'none';
    }

    function startGame1() {
        clearGame();
        document.getElementById('mobile-controls').style.display = 'flex';
        const config = {
            type: Phaser.AUTO,
            width: window.innerWidth > 800 ? 800 : window.innerWidth,
            height: window.innerHeight > 600 ? 600 : window.innerHeight * 0.8,
            parent: 'gameContainer',
            physics: {
                default: 'arcade',
                arcade: {
                    gravity: { y: 300 },
                    debug: false
                }
            },
            scene: {
                preload: preload,
                create: create,
                update: update
            }
        };

        let player;
        let cursors;
        let moveLeft = false;
        let moveRight = false;
        let jump = false;

        function preload() {
            this.load.image('sky', 'https://labs.phaser.io/assets/skies/sky4.png');
            this.load.image('ground', 'https://labs.phaser.io/assets/sprites/platform.png');
            this.load.spritesheet('dude', 'https://labs.phaser.io/assets/sprites/dude.png', {
                frameWidth: 32,
                frameHeight: 48
            });
        }

        function create() {
            this.add.image(config.width / 2, config.height / 2, 'sky').setScrollFactor(0);

            const platforms = this.physics.add.staticGroup();
            platforms.create(config.width / 2, config.height - 32, 'ground').setScale(2).refreshBody();

            player = this.physics.add.sprite(100, config.height - 150, 'dude');
            player.setBounce(0.2);
            player.setCollideWorldBounds(true);

            this.physics.add.collider(player, platforms);
            cursors = this.input.keyboard.createCursorKeys();

            this.anims.create({
                key: 'left',
                frames: this.anims.generateFrameNumbers('dude', { start: 0, end: 3 }),
                frameRate: 10,
                repeat: -1
            });

            this.anims.create({
                key: 'turn',
                frames: [ { key: 'dude', frame: 4 } ],
                frameRate: 20
            });

            this.anims.create({
                key: 'right',
                frames: this.anims.generateFrameNumbers('dude', { start: 5, end: 8 }),
                frameRate: 10,
                repeat: -1
            });

            // Botões mobile
            document.getElementById('leftBtn').ontouchstart = () => moveLeft = true;
            document.getElementById('leftBtn').ontouchend = () => moveLeft = false;
            document.getElementById('rightBtn').ontouchstart = () => moveRight = true;
            document.getElementById('rightBtn').ontouchend = () => moveRight = false;
            document.getElementById('jumpBtn').ontouchstart = () => jump = true;
            document.getElementById('jumpBtn').ontouchend = () => jump = false;
        }

        function update() {
            if (cursors.left.isDown || moveLeft) {
                player.setVelocityX(-160);
                player.anims.play('left', true);
            } else if (cursors.right.isDown || moveRight) {
                player.setVelocityX(160);
                player.anims.play('right', true);
            } else {
                player.setVelocityX(0);
                player.anims.play('turn');
            }

            if ((cursors.up.isDown || jump) && player.body.touching.down) {
                player.setVelocityY(-330);
            }
        }

        currentGame = new Phaser.Game(config);
    }

    function startGame2() {
        clearGame();
        document.getElementById('gameContainer').innerHTML = '<h2>Jogo de Plataforma 2</h2><p>Em breve!</p>';
    }

    function startGame3() {
        clearGame();
        document.getElementById('gameContainer').innerHTML = '<h2>Jogo de Corrida</h2><p>Em breve!</p>';
    }

    function startGame4() {
        clearGame();
        document.getElementById('gameContainer').innerHTML = '<h2>Jogo do Labirinto</h2><p>Em breve!</p>';
    }
</script>

<footer>
    <p>246 Jogos - Criado por João, Pedro e Olavo</p>
</footer>

</body>
</html>
