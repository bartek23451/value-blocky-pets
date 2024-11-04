<!DOCTYPE html>
<html lang="pl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ceny Petów - Epicka Strona</title>
    <style>
        /* Podstawowy reset */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        /* Tło z gradientem animowanym */
        body {
            font-family: Arial, sans-serif;
            color: #333;
            background: linear-gradient(135deg, #3a6186, #89253e);
            background-size: 200% 200%;
            animation: gradientAnimation 8s ease infinite;
            display: flex;
            flex-direction: column;
            align-items: center;
            min-height: 100vh;
        }

        @keyframes gradientAnimation {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        /* Nagłówek */
        header {
            text-align: center;
            padding: 2rem 0;
            color: #fff;
        }

        header h1 {
            font-size: 2.5rem;
            font-weight: bold;
            letter-spacing: 2px;
        }

        /* Styl pola wyszukiwania */
        #search {
            margin-top: 1rem;
            padding: 0.75rem;
            width: 80%;
            max-width: 400px;
            border: 2px solid #ddd;
            border-radius: 25px;
            outline: none;
            font-size: 1rem;
            text-align: center;
            transition: all 0.3s ease;
        }

        #search:focus {
            border-color: #f39c12;
            box-shadow: 0 0 10px rgba(243, 156, 18, 0.5);
        }

        /* Sekcja główna z kartami */
        main {
            display: flex;
            justify-content: center;
            padding: 2rem;
            width: 100%;
        }

        #pets-list {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 1.5rem;
            width: 80%;
            max-width: 1200px;
        }

        /* Styl karty peta */
        .pet-card {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border: 2px solid #fff;
            border-radius: 15px;
            padding: 1.5rem;
            text-align: center;
            color: #fff;
            transition: transform 0.4s ease, box-shadow 0.4s ease;
            cursor: pointer;
            position: relative;
            overflow: hidden;
        }

        .pet-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(255, 255, 255, 0.3);
            clip-path: circle(0% at 100% 100%);
            transition: clip-path 0.6s ease;
        }

        .pet-card:hover::before {
            clip-path: circle(150% at 0% 0%);
        }

        .pet-card:hover {
            transform: scale(1.05);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.3);
        }

        .pet-card h2 {
            font-size: 1.5rem;
            margin-bottom: 0.5rem;
            font-weight: bold;
            color: #f39c12;
        }

        .pet-card p {
            font-size: 1.1rem;
            color: #ecf0f1;
        }

        /* Efekt pojawiania się kart przy ładowaniu */
        .pet-card {
            opacity: 0;
            transform: translateY(30px);
            animation: fadeInUp 0.5s ease forwards;
        }

        /* Zwiększenie czasu pojawiania się każdej karty */
        .pet-card:nth-child(odd) { animation-delay: 0.2s; }
        .pet-card:nth-child(even) { animation-delay: 0.4s; }

        @keyframes fadeInUp {
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
    </style>
</head>
<body>
    <header>
        <h1>Ceny Petów</h1>
        <input type="text" id="search" placeholder="Szukaj zwierzaka...">
    </header>

    <main>
        <section id="pets-list">
            <!-- 20 kart z petami -->
            <div class="pet-card" data-category="zwykły"><h2>Kotek</h2><p>Cena: 100 monet</p></div>
            <div class="pet-card" data-category="zwykły"><h2>Chomik</h2><p>Cena: 120 monet</p></div>
            <div class="pet-card" data-category="zwykły"><h2>Królik</h2><p>Cena: 150 monet</p></div>
            <div class="pet-card" data-category="rzadki"><h2>Piesek</h2><p>Cena: 500 monet</p></div>
            <div class="pet-card" data-category="rzadki"><h2>Fretka</h2><p>Cena: 600 monet</p></div>
            <div class="pet-card" data-category="rzadki"><h2>Sowa</h2><p>Cena: 700 monet</p></div>
            <div class="pet-card" data-category="epicki"><h2>Jednorożec</h2><p>Cena: 2000 monet</p></div>
            <div class="pet-card" data-category="epicki"><h2>Wilk</h2><p>Cena: 2200 monet</p></div>
            <div class="pet-card" data-category="epicki"><h2>Sokół</h2><p>Cena: 2500 monet</p></div>
            <div class="pet-card" data-category="legendarny"><h2>Feniks</h2><p>Cena: 5000 monet</p></div>
            <div class="pet-card" data-category="legendarny"><h2>Smok</h2><p>Cena: 7500 monet</p></div>
            <div class="pet-card" data-category="legendarny"><h2>Griffin</h2><p>Cena: 8000 monet</p></div>
            <div class="pet-card" data-category="mityczny"><h2>Kraken</h2><p>Cena: 10000 monet</p></div>
            <div class="pet-card" data-category="mityczny"><h2>Cerber</h2><p>Cena: 12000 monet</p></div>
            <div class="pet-card" data-category="mityczny"><h2>Bazyliszek</h2><p>Cena: 15000 monet</p></div>
            <div class="pet-card" data-category="mityczny"><h2>Chimera</h2><p>Cena: 18000 monet</p></div>
            <div class="pet-card" data-category="zwykły"><h2>Żółw</h2><p>Cena: 200 monet</p></div>
            <div class="pet-card" data-category="rzadki"><h2>Lemur</h2><p>Cena: 800 monet</p></div>
            <div class="pet-card" data-category="epicki"><h2>Orzeł</h2><p>Cena: 2700 monet</p></div>
            <div class="pet-card" data-category="legendarny"><h2>Lew</h2><p>Cena: 6000 monet</p></div>
        </section>
    </main>

    <script>
        document.getElementById("search").addEventListener("input", function() {
            const searchTerm = this.value.toLowerCase();
            const pets = document.querySelectorAll(".pet-card");

            pets.forEach(pet => {
                const petName = pet.querySelector("h2").innerText.toLowerCase();
                pet.style.display = petName.includes(searchTerm) ? "block" : "none";
            });
        });
    </script>
</body>
</html>
