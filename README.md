<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Терминал Anderson Robotics</title>
    <style>
        body {
            background-color: #1a1a1a;
            color: #00ff00;
            font-family: 'Courier New', Courier, monospace;
            overflow: hidden;
            margin: 0;
            padding: 0;
        }
        h1, h2 {
            text-align: center;
            animation: fadeIn 2s;
        }
        h1 {
            font-size: 3em;
            margin-top: 20px;
        }
        h2 {
            font-size: 2em;
            margin-top: 10px;
        }
        .terminal {
            width: 80%;
            margin: 0 auto;
            background-color: #000;
            border: 2px solid #00ff00;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 0 20px rgba(0, 255, 0, 0.5);
            animation: slideIn 1s;
            white-space: pre; /* Сохраняет пробелы и переносы строк */
            overflow: hidden; /* Скрывает переполнение */
        }
        .footer {
            text-align: center;
            margin-top: 20px;
            font-size: 0.8em;
        }
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }
        @keyframes slideIn {
            from { transform: translateY(-100%); }
            to { transform: translateY(0); }
        }
        .robot-status {
            margin: 20px 0;
            font-size: 1.2em;
            animation: pulse 1.5s infinite;
        }
        @keyframes pulse {
            0%, 100% { opacity: 1; }
            50% { opacity: 0.5; }
        }
        /* Бургерное меню */
        .burger-menu {
            position: absolute;
            top: 20px;
            left: 20px;
            cursor: pointer;
            z-index: 1000;
        }
        .burger-menu img {
            width: 50px; /* Размер логотипа */
            height: auto;
        }
        .nav {
            display: none;
            position: absolute;
            top: 80px;
            left: 20px;
            background-color: #000;
            border: 2px solid #00ff00;
            border-radius: 10px;
            box-shadow: 0 0 20px rgba(0, 255, 0, 0.5);
            padding: 10px;
            z-index: 999; /* Убедитесь, что меню выше других элементов */
        }
        .nav a {
            color: #00ff00;
            text-decoration: none;
            display: block;
            margin: 5px 0;
        }
        .nav a:hover {
            text-decoration: underline;
        }
        .group {
            margin: 20px auto;
            width: 80%;
            background-color: #000;
            border: 2px solid #00ff00;
            border-radius: 10px;
            padding: 10px;
            box-shadow: 0 0 10px rgba(0, 255, 0, 0.5);
            text-align: center;
        }
        .group h3 {
            margin: 10px 0;
        }
        .button {
            background-color: #00ff00;
            color: #000;
            padding: 10px 20px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-size: 16px;
            transition: background-color 0.3s;
            text-decoration: none;
        }
        .button:hover {
            background-color: #00cc00; /* Темнее при наведении */
        }
    </style>
</head>
<body>
    <div class="burger-menu" onclick="toggleMenu()">
        <img src="https://cdn.discordapp.com/attachments/1330253205124419657/1330266177410301992/image-removebg-preview_2.png?ex=678d5a6b&is=678c08eb&hm=b9044de4913ac1126b3e2b510f6ff7c5792c73ea79cea9a30888da7d8fe238e7" alt="Логотип Anderson Robotics">
    </div>
    <div class="nav" id="navMenu">
        <a href="https://scpfoundation.net/anderson-robotics-hub" target="_blank">Главная</a>
    </div>
    <h1>Терминал Anderson Robotics</h1>
    <h2>Версия Протокола Безопасности 43.56</h2>
    <div class="terminal" id="terminal">
        <pre id="output"></pre>
    </div>
    
    <div class="group">
        <h3>Технологии</h3>
        <a href="https://discord.com/channels/1257381863107067966/1271901754249969705" class="button" target="_blank">Перейти в Технологии</a>
    </div>
    
    <div class="group">
        <h3>Новости</h3>
        <a href="https://discord.com/channels/1257381863107067966/1257384163422765076" class="button" target="_blank">Перейти в Новости</a>
    </div>

    <div class="footer">© 2023 Anderson Robotics. Все права защищены.</div>
    <script>
        const textLines = [
            "База данных роботов загружена, все роботы подключены.",
            "Инициализация системы...",
            "Состояние: ОК",
            "Загрузка данных...",
            "Загрузка завершена.",
            "Проверка системных модулей...",
            "Модуль 1: ОК",
            "Модуль 2: ОК",
            "Модуль 3: ОК",
            "Все системы функционируют в норме.",
            "Ожидание команд..."
        ];

        let currentLine = 0;

        function typeLine() {
            if (currentLine < textLines.length) {
                const output = document.getElementById('output');
                output.textContent += textLines[currentLine] + '\n';
                currentLine++;
                setTimeout(typeLine, 2000); // Задержка между строками
            }
        }

        window.onload = function() {
            typeLine();
        };

        function toggleMenu() {
            const navMenu = document.getElementById('navMenu');
            navMenu.style.display = navMenu.style.display === 'block' ? 'none' : 'block';
        }
    </script>
</body>
</html>
