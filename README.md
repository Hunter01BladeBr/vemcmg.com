<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Pergunta</title>
    <style>
        /* Estilo básico para centralizar o conteúdo */
        body {
            text-align: center;
            font-family: Arial, sans-serif;
            background-color: #f4f4f4;
            margin: 0;
            padding: 0;
        }

        h1 {
            margin-top: 50px;
            color: #333;
        }

        .form-container {
            margin-top: 20px;
        }

        label {
            font-size: 20px;
            margin: 10px;
            cursor: pointer;
        }

        input[type="radio"] {
            margin-right: 10px;
        }

        /* O container dos fogos de artifício será 100% da tela */
        #fireworks-container {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none; /* Para não interferir nos cliques */
            display: none; /* Inicialmente invisível */
        }
    </style>
    <script src="https://cdn.jsdelivr.net/npm/fireworks-js@2.0.0/dist/index.min.js"></script>
</head>
<body>

    <h1>Vamos fazer amor hoje?</h1>

    <div class="form-container">
        <label>
            <input type="radio" name="resposta" value="sim" id="sim"> Sim
        </label>
        <label>
            <input type="radio" name="resposta" value="nao" id="nao"> Não
        </label>
    </div>

    <!-- Container para os fogos de artifício -->
    <div id="fireworks-container"></div>

    <script>
        // Função para iniciar os fogos de artifício
        function startFireworks() {
            const container = document.getElementById('fireworks-container');
            container.style.display = 'block';  // Mostrar o container dos fogos

            // Inicia a animação dos fogos de artifício
            const fireworks = new Fireworks({
                target: container,
                particles: 50, // Número de partículas dos fogos
                size: 3, // Tamanho das partículas
                speed: 3, // Velocidade da animação
                sound: true, // Ativa o som dos fogos
            });
            fireworks.start();
        }

        // Lógica para verificar a escolha do usuário
        const simButton = document.getElementById('sim');
        const naoButton = document.getElementById('nao');

        simButton.addEventListener('click', function() {
            startFireworks();  // Inicia os fogos se "Sim" for clicado
        });

        naoButton.addEventListener('click', function() {
            const container = document.getElementById('fireworks-container');
            container.style.display = 'none';  // Esconde os fogos se "Não" for clicado
        });
    </script>

</body>
</html>
