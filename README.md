<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>¡Tienes un regalo especial!</title>
    <style>
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            background-color: #ffe6f0;
            font-family: 'Arial', sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            overflow: hidden;
            text-align: center;
            position: relative;
        }

        /* Corazones flotantes de fondo */
        .heart-bg {
            position: absolute;
            color: #ff6b81;
            font-size: 20px;
            animation: float 6s infinite linear;
            opacity: 0.6;
            z-index: 1;
        }

        @keyframes float {
            0% { transform: translateY(100vh) rotate(0deg); opacity: 1; }
            100% { transform: translateY(-10vh) rotate(360deg); opacity: 0; }
        }

        .container {
            background: rgba(255, 255, 255, 0.9);
            padding: 30px;
            border-radius: 20px;
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.1);
            z-index: 10;
            max-width: 90%;
            width: 400px;
            transition: all 0.5s ease;
        }

        h1 {
            color: #d63384;
            font-size: 1.8rem;
            margin-bottom: 10px;
        }

        p {
            color: #666;
            font-size: 1.1rem;
            margin-bottom: 20px;
        }

        .gift-box {
            font-size: 90px;
            margin: 20px 0;
            cursor: pointer;
            transition: transform 0.3s ease;
            user-select: none;
        }

        .gift-box:hover {
            transform: scale(1.1) rotate(-5deg);
        }

        .btn-open {
            background-color: #ff4757;
            color: white;
            border: none;
            padding: 12px 30px;
            font-size: 1.2rem;
            font-weight: bold;
            border-radius: 25px;
            cursor: pointer;
            box-shadow: 0 5px 15px rgba(255, 71, 87, 0.4);
            transition: background 0.3s, transform 0.2s;
        }

        .btn-open:hover {
            background-color: #ff6b81;
            transform: translateY(-2px);
        }

        /* Estado del regalo abierto */
        .hidden {
            display: none;
        }

        .flower-container {
            font-size: 80px;
            animation: popIn 0.8s ease-out;
            margin: 20px 0;
        }

        @keyframes popIn {
            0% { transform: scale(0); opacity: 0; }
            80% { transform: scale(1.2); }
            100% { transform: scale(1); opacity: 1; }
        }

        .message {
            color: #e67e22;
            font-size: 2rem;
            font-weight: bold;
            margin-top: 15px;
            animation: fadeIn 1.5s ease-in;
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }
    </style>
</head>
<body>

    <!-- Corazones de fondo generados con JS -->
    <script>
        for (let i = 0; i < 20; i++) {
            let heart = document.createElement('div');
            heart.className = 'heart-bg';
            heart.innerHTML = '❤️';
            heart.style.left = Math.random() * 100 + 'vw';
            heart.style.animationDuration = (Math.random() * 3 + 3) + 's';
            heart.style.fontSize = (Math.random() * 20 + 10) + 'px';
            document.body.appendChild(heart);
        }
    </script>

    <div class="container">
        <!-- Pantalla Inicial -->
        <div id="gift-screen">
            <h1>🎁 ¡Tienes un regalo!</h1>
            <p><strong>Rickso</strong> te envió un regalo especial</p>
            <div class="gift-box" onclick="abrirRegalo()">🎁</div>
            <button class="btn-open" onclick="abrirRegalo()">Abrir</button>
        </div>

        <!-- Pantalla con Flores Amarillas -->
        <div id="flower-screen" class="hidden">
            <div class="flower-container">
                🌻 🌼 🌻 🌼 🌻
            </div>
            <div class="message">
                ¡Feliz día de las flores amarillas! 💛✨
            </div>
        </div>
    </div>

    <script>
        function abrirRegalo() {
            document.getElementById('gift-screen').classList.add('hidden');
            document.getElementById('flower-screen').classList.remove('hidden');
        }
    </script>
</body>
</html>
