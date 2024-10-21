<!DOCTYPE html>
<html lang="hr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>STM32 Upravljačka Aplikacija</title>
</head>
<body>
    <h1>Upravljanje STM32 Pločicom</h1>
    <button id="setValue">Postavi Vrijednost</button>
    <input type="number" id="valueInput" placeholder="Unesite vrijednost">

    <h2>Podaci sa senzora</h2>
    <div id="sensorData">Čekam podatke...</div>

    <script>
        document.getElementById('setValue').addEventListener('click', () => {
            const value = document.getElementById('valueInput').value;
            fetch('/set-value', {
                method: 'POST',
                headers: {
                    'Content-Type': 'application/json',
                },
                body: JSON.stringify({ value: value }),
            })
            .then(response => response.json())
            .then(data => {
                console.log(data);
            })
            .catch(error => console.error('Greška:', error));
        });

        setInterval(() => {
            fetch('/sensor-data')
                .then(response => response.json())
                .then(data => {
                    document.getElementById('sensorData').textContent = `Vrijednost senzora: ${data.value}`;
                })
                .catch(error => console.error('Greška:', error));
        }, 1000); // Ažuriranje svakih 1 sekundu
    </script>
</body>
</html>
