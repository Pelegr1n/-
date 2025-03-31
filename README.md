# -
<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Что лучше: Флэт Уайт или Эспрессо?</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            background-image: url('https://images.unsplash.com/photo-1497935586351-b67a49e012bf?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80');
            background-size: cover;
            background-attachment: fixed;
            color: #3E2723;
            margin: 0;
            padding: 0;
            overflow-x: hidden;
        }

        .container {
            max-width: 800px;
            margin: 0 auto;
            padding: 20px;
            background-color: rgba(255, 255, 255, 0.85);
            border-radius: 15px;
            box-shadow: 0 0 20px rgba(0, 0, 0, 0.3);
            margin-top: 30px;
            margin-bottom: 30px;
        }

        h1 {
            text-align: center;
            color: #5D4037;
            font-size: 2.5em;
            margin-bottom: 30px;
            text-shadow: 1px 1px 2px rgba(0,0,0,0.1);
        }

        .coffee-option {
            display: flex;
            align-items: center;
            margin-bottom: 30px;
            padding: 20px;
            border-radius: 10px;
            background-color: rgba(255, 248, 225, 0.7);
            transition: transform 0.3s;
            cursor: pointer;
        }

        .coffee-option:hover {
            transform: scale(1.02);
            background-color: rgba(255, 248, 225, 0.9);
        }

        .coffee-img {
            width: 150px;
            height: 150px;
            object-fit: cover;
            border-radius: 10px;
            margin-right: 20px;
        }

        .coffee-info {
            flex: 1;
        }

        button {
            background-color: #6D4C41;
            color: white;
            border: none;
            padding: 10px 20px;
            border-radius: 5px;
            cursor: pointer;
            font-size: 1em;
            transition: background-color 0.3s;
            display: block;
            margin: 0 auto;
        }

        button:hover {
            background-color: #8D6E63;
        }

        .results {
            margin-top: 30px;
            background-color: rgba(255, 248, 225, 0.7);
            padding: 20px;
            border-radius: 10px;
            display: none;
        }

        .progress-container {
            width: 100%;
            background-color: #D7CCC8;
            border-radius: 5px;
            margin-top: 10px;
        }

        .progress-bar {
            height: 30px;
            border-radius: 5px;
            background-color: #5D4037;
            width: 0%;
            transition: width 1s;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-weight: bold;
        }


        .coffee-bean {
            position: absolute;
            width: 20px;
            height: 10px;
            background-color: #5D4037;
            border-radius: 50%;
            opacity: 0.7;
            animation: float 5s infinite ease-in-out;
            z-index: -1;
        }

        .steam {
            position: absolute;
            width: 40px;
            height: 40px;
            background: radial-gradient(ellipse at center, rgba(255,255,255,0.8) 0%, rgba(255,255,255,0) 70%);
            border-radius: 50%;
            animation: steam 4s infinite ease-in-out;
            z-index: -1;
        }

        @keyframes float {
            0% { transform: translateY(0) rotate(0deg); }
            50% { transform: translateY(-50px) rotate(180deg); }
            100% { transform: translateY(0) rotate(360deg); }
        }

        @keyframes steam {
            0% { transform: scale(0.5); opacity: 0; }
            50% { transform: scale(1.2); opacity: 0.4; }
            100% { transform: scale(0.5); opacity: 0; }
        }

        footer {
            text-align: center;
            margin-top: 30px;
            padding: 10px;
            color: white;
            background-color: rgba(93, 64, 55, 0.7);
            border-radius: 5px;
        }
    </style>
</head>
<body>

    <script>
        document.addEventListener('DOMContentLoaded', function() {

            for (let i = 0; i < 15; i++) {
                createCoffeeBean();
            }
            

            for (let i = 0; i < 8; i++) {
                createSteam();
            }
        });

        function createCoffeeBean() {
            const bean = document.createElement('div');
            bean.className = 'coffee-bean';
            bean.style.left = Math.random() * 100 + 'vw';
            bean.style.top = Math.random() * 100 + 'vh';
            bean.style.transform = 'rotate(' + (Math.random() * 360) + 'deg)';
            bean.style.animationDuration = (3 + Math.random() * 7) + 's';
            document.body.appendChild(bean);
        }

        function createSteam() {
            const steam = document.createElement('div');
            steam.className = 'steam';
            steam.style.left = Math.random() * 100 + 'vw';
            steam.style.top = Math.random() * 100 + 'vh';
            steam.style.animationDelay = Math.random() * 4 + 's';
            document.body.appendChild(steam);
        }
    </script>

    <div class="container">
        <h1>Что лучше: Флэт Уайт или Эспрессо?</h1>
        
        <div class="coffee-option" onclick="vote('flatWhite')">
            <img src="https://images.unsplash.com/photo-1568649929103-28ffbefaca1e?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=80" alt="Флэт Уайт" class="coffee-img">
            <div class="coffee-info">
                <h2>Флэт Уайт</h2>
                <p>Австралийский кофейный напиток, состоящий из эспрессо и микропены. Более мягкий вкус по сравнению с латте, с более выраженным кофейным вкусом.</p>
            </div>
        </div>
        
        <div class="coffee-option" onclick="vote('espresso')">
            <img src="https://images.unsplash.com/photo-1517705008128-361805f42e86?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=80" alt="Эспрессо" class="coffee-img">
            <div class="coffee-info">
                <h2>Эспрессо</h2>
                <p>Крепкий кофейный напиток, приготовленный путём пропускания горячей воды под давлением через спрессованный молотый кофе. Классика кофейного искусства.</p>
            </div>
        </div>
        
        <button onclick="showResults()">Показать результаты</button>
        
        <div class="results" id="results">
            <h2>Результаты голосования</h2>
            <p>Флэт Уайт: <span id="flatWhiteVotes">0</span> голосов</p>
            <div class="progress-container">
                <div class="progress-bar" id="flatWhiteBar">0%</div>
            </div>
            <p>Эспрессо: <span id="espressoVotes">0</span> голосов</p>
            <div class="progress-container">
                <div class="progress-bar" id="espressoBar">0%</div>
            </div>
        </div>
    </div>
    
    <footer>
        © 2025 Coffee Lovers Community | Все права защищены
    </footer>

    <script>

        let flatWhiteVotes = localStorage.getItem('flatWhiteVotes') ? parseInt(localStorage.getItem('flatWhiteVotes')) : 0;
        let espressoVotes = localStorage.getItem('espressoVotes') ? parseInt(localStorage.getItem('espressoVotes')) : 0;
        let voted = localStorage.getItem('voted') === 'true';


        function vote(option) {
            if (voted) {
                alert('Вы уже проголосовали!');
                return;
            }
            
            if (option === 'flatWhite') {
                flatWhiteVotes++;
            } else if (option === 'espresso') {
                espressoVotes++;
            }
            
            // Сохраняем результаты
            localStorage.setItem('flatWhiteVotes', flatWhiteVotes);
            localStorage.setItem('espressoVotes', espressoVotes);
            localStorage.setItem('voted', 'true');
            
            alert('Спасибо за ваш голос!');
            showResults();
        }


        function showResults() {
            const totalVotes = flatWhiteVotes + espressoVotes;
            const resultsDiv = document.getElementById('results');
            
            if (totalVotes === 0) {
                document.getElementById('flatWhiteVotes').textContent = '0';
                document.getElementById('espressoVotes').textContent = '0';
                document.getElementById('flatWhiteBar').style.width = '0%';
                document.getElementById('espressoBar').style.width = '0%';
                document.getElementById('flatWhiteBar').textContent = '0%';
                document.getElementById('espressoBar').textContent = '0%';
            } else {
                const flatWhitePercent = Math.round((flatWhiteVotes / totalVotes) * 100);
                const espressoPercent = 100 - flatWhitePercent;
                
                document.getElementById('flatWhiteVotes').textContent = flatWhiteVotes;
                document.getElementById('espressoVotes').textContent = espressoVotes;
                document.getElementById('flatWhiteBar').style.width = flatWhitePercent + '%';
                document.getElementById('espressoBar').style.width = espressoPercent + '%';
                document.getElementById('flatWhiteBar').textContent = flatWhitePercent + '%';
                document.getElementById('espressoBar').textContent = espressoPercent + '%';
            }
            
            resultsDiv.style.display = 'block';
        }


        if (voted) {
            showResults();
        }
    </script>
</body>
</html>
