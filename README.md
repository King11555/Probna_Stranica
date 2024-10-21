<!DOCTYPE html>
<html lang="hr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Jednostavna Stranica s Gumbima</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            margin-top: 50px;
            background-color: #f0f0f0;
        }
        button {
            padding: 10px 20px;
            font-size: 16px;
            margin: 10px;
            cursor: pointer;
        }
        #indicator {
            margin-top: 20px;
            font-size: 24px;
            color: #333;
        }
    </style>
</head>
<body>
    <h1>Gumbi i Indikator</h1>
    <button id="button1">Gumb 1</button>
    <button id="button2">Gumb 2</button>

    <div id="indicator">Pritisnite gumb!</div>

    <script>
        const button1 = document.getElementById('button1');
        const button2 = document.getElementById('button2');
        const indicator = document.getElementById('indicator');

        button1.addEventListener('click', () => {
            indicator.textContent = 'Pritisnut je Gumb 1';
        });

        button2.addEventListener('click', () => {
            indicator.textContent = 'Pritisnut je Gumb 2';
        });
    </script>
</body>
</html>
