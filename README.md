<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Nossa Música</title>
    <style>
        :root {
            --spotify-green: #1DB954;
            --spotify-black: #191414;
            --spotify-light-black: #212121;
            --text-grey: #b3b3b3;
        }

        body {
            background-color: var(--spotify-black);
            color: white;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            display: flex;
            flex-direction: column;
            align-items: center;
            margin: 0;
            padding: 20px;
        }

        .player-container {
            background: linear-gradient(to bottom, #404040, var(--spotify-black));
            width: 100%;
            max-width: 350px;
            padding: 20px;
            border-radius: 15px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.5);
            text-align: center;
        }

        .album-art {
            width: 100%;
            aspect-ratio: 1/1;
            background-image: url('foto.jpg'); /* Nome do seu arquivo de foto */
            background-size: cover;
            background-position: center;
            border-radius: 8px;
            margin-bottom: 20px;
            box-shadow: 0 4px 15px rgba(0,0,0,0.4);
        }

        .song-info {
            text-align: left;
            margin-bottom: 20px;
        }

        .song-title {
            font-size: 1.4rem;
            font-weight: bold;
            margin: 0;
        }

        .artist-name {
            color: var(--text-grey);
            font-size: 1rem;
            margin: 5px 0 0 0;
        }

        .progress-bar {
            width: 100%;
            height: 4px;
            background-color: #5e5e5e;
            border-radius: 2px;
            margin: 15px 0;
            position: relative;
        }

        .progress-fill {
            width: 70%; /* Simulação de progresso */
            height: 100%;
            background-color: white;
            border-radius: 2px;
        }

        .counter {
            margin-top: 30px;
            padding: 15px;
            border-top: 1px solid #333;
            font-size: 0.9rem;
            color: var(--spotify-green);
            font-weight: bold;
        }

        .letter-section {
            margin-top: 40px;
            max-width: 500px;
            line-height: 1.6;
            text-align: center;
            background: var(--spotify-light-black);
            padding: 25px;
            border-radius: 10px;
        }

        .lyrics {
            font-style: italic;
            color: var(--text-grey);
            margin-bottom: 30px;
            white-space: pre-line;
        }

        h2 { color: var(--spotify-green); }
    </style>
</head>
<body>

    <div class="player-container">
        <div class="album-art"></div>
        <div class="song-info">
            <p class="song-title">Os Anjos Cantam Nosso Amor</p>
            <p class="artist-name">Jorge & Mateus</p>
        </div>
        
        <div class="progress-bar">
            <div class="progress-fill"></div>
        </div>

        <div id="tempo-juntos" class="counter">
            Carregando nosso tempo...
        </div>
    </div>

    <div class="letter-section">
        <h2>Para o amor da minha vida</h2>
        <p>
            <em>"O que na vida ninguém fez, você fez em menos de um mês..."</em>
        </p>
        
        <div class="lyrics">
            [Letra da Música]
            Os anjos cantam nosso amor
            Oh, oh, oh, oh...
            E a gente vai se amar
            Aonde o sol se pôr...
        </div>

        <hr style="border: 0.5px solid #333; margin: 20px 0;">
        
        <p>
            <strong>Minha Carta:</strong><br>
            Escreva aqui tudo o que você está sentindo. Diga o quanto ela é forte, 
            o quanto você a ama e que logo ela estará bem para vocês viverem 
            mais momentos lindos juntos.
        </p>
    </div>

    <script>
        // COLOQUE A DATA QUE VOCÊS SE CONHECERAM AQUI (Ano, Mês - 1, Dia)
        // Exemplo: 15 de Janeiro de 2023 seria (2023, 0, 15)
        const dataInicio = new Date(2023, 0, 15); 

        function atualizarContador() {
            const agora = new Date();
            const diff = agora - dataInicio;

            const dias = Math.floor(diff / (1000 * 60 * 60 * 24));
            const horas = Math.floor((diff / (1000 * 60 * 60)) % 24);
            
            document.getElementById('tempo-juntos').innerText = 
                `Juntos há ${dias} dias e ${horas} horas`;
        }

        setInterval(atualizarContador, 1000);
        atualizarContador();
    </script>

</body>
</html>
