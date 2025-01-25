<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Declaração de Amor</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            background-color: #f4f4f4;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            flex-direction: column;
            text-align: center;
        }

        h1 {
            color: #ff69b4;
            font-size: 2.5em;
        }

        button {
            background-color: #ff69b4;
            color: white;
            padding: 10px 20px;
            font-size: 1.2em;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            transition: background-color 0.3s ease;
        }

        button:hover {
            background-color: #ff1493;
        }

        .hearts {
            display: none;
            position: absolute;
            z-index: 10;
            pointer-events: none;
        }

        .heart {
            position: absolute;
            font-size: 2em;
            color: #ff69b4;
            animation: heartAnimation 1s ease-in-out infinite;
        }

        @keyframes heartAnimation {
            0% {
                opacity: 1;
                transform: translateY(0) scale(1);
            }
            50% {
                opacity: 0.6;
                transform: translateY(-20px) scale(1.5);
            }
            100% {
                opacity: 0;
                transform: translateY(-40px) scale(2);
            }
        }
    </style>
</head>
<body>

    <h1>Surpresa para a Leisa!</h1>
    <button onclick="mostrarMensagem()">Clique aqui para ver a surpresa!</button>
    <div class="hearts" id="hearts"></div>
    
    <script>
        function mostrarMensagem() {
            // Exibir a mensagem de amor
            alert("Brunooh te ama, Leisa!");

            // Criar os corações
            const heartsContainer = document.getElementById('hearts');
            heartsContainer.style.display = 'block';
            
            for (let i = 0; i < 20; i++) {
                let heart = document.createElement('div');
                heart.textContent = '❤️';
                heart.classList.add('heart');

                let randomX = Math.random() * window.innerWidth;
                let randomY = Math.random() * window.innerHeight;

                heart.style.left = randomX + 'px';
                heart.style.top = randomY + 'px';
                
                heartsContainer.appendChild(heart);
                
                // Destroi o coração após a animação
                setTimeout(() => {
                    heart.remove();
                }, 1000); // Tempo da animação
            }
        }
    </script>

</body>
</html>
