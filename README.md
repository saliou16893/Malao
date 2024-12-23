# Malao
Wave
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Suivi des Parieurs - Paris Lutte Sénégal</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f4f4f4;
            margin: 0;
            padding: 0;
        }

        header {
            background-color: #3498db;
            color: white;
            padding: 15px;
            text-align: center;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }

        .counter {
            background-color: white;
            padding: 20px;
            text-align: center;
            border-radius: 5px;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
        }

        .counter h2 {
            font-size: 2em;
            margin-bottom: 20px;
        }

        .counter p {
            font-size: 1.5em;
            color: #2c3e50;
        }

        footer {
            background-color: #2c3e50;
            color: white;
            padding: 10px;
            text-align: center;
        }
    </style>
</head>
<body>

<header>
    <h1>Suivi des Parieurs - Paris Lutte Sénégal</h1>
</header>

<div class="container">
    <div class="counter">
        <h2>Nombre total de parieurs</h2>
        <p id="parieurCount">Chargement...</p>
    </div>
</div>

<footer>
    <p>© 2024 Paris Lutte Sénégal - Tous droits réservés</p>
</footer>

<script>
    // Fonction pour récupérer et afficher le nombre de parieurs
    function fetchParieurCount() {
        fetch('https://votre-backend.com/api/parieurs') // Remplacez par l'URL de votre API
            .then(response => response.json())
            .then(data => {
                document.getElementById('parieurCount').innerText = data.count + " parieurs actifs";
            })
            .catch(error => {
                console.error('Erreur de récupération du nombre de parieurs:', error);
                document.getElementById('parieurCount').innerText = "Impossible de récupérer les données.";
            });
    }

    // Appeler la fonction pour afficher le nombre des parieurs au chargement de la page
    window.onload = fetchParieurCount;
</script>

</body>
</html>
