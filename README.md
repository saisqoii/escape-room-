<!DOCTYPE html>
<html lang="nl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Escape Room - Doodverklaard</title>
    <link href="https://fonts.googleapis.com/css2?family=Creepster&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: 'Creepster', cursive;
            text-align: center;
            background-color: black;
            color: red;
            padding: 20px;
        }
        .container {
            max-width: 600px;
            margin: auto;
            background: #222;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 0 20px rgba(255, 0, 0, 0.8);
            border: 2px solid red;
        }
        input, button {
            padding: 10px;
            margin: 10px;
            font-size: 16px;
            font-family: 'Creepster', cursive;
            background: black;
            color: red;
            border: 2px solid red;
        }
        button:hover {
            background: red;
            color: black;
        }
        .hidden {
            display: none;
        }
    </style>
</head>
<body>
    <div class="container" id="riddle1">
        <h1>Escape Room: Doodverklaard</h1>
        <p>Isa is doodverklaard, maar ze leeft nog. Help haar de waarheid te achterhalen!</p>
        <p>Los het eerste raadsel op: <br><strong>"Ik besta, maar niemand herkent me. Wat ben ik?"</strong></p>
        <input type="text" id="answer1" placeholder="Jouw antwoord">
        <button onclick="checkAnswer(1, 'geheim', 'schaduw')">Controleer</button>
        <p id="message1"></p>
    </div>
    
    <div class="container hidden" id="riddle2">
        <p>Goed gedaan! Hier is het volgende raadsel:</p>
        <p><strong>"Hoe meer je van mij wegneemt, hoe groter ik word. Wat ben ik?"</strong></p>
        <input type="text" id="answer2" placeholder="Jouw antwoord">
        <button onclick="checkAnswer(2, 'gat')">Controleer</button>
        <p id="message2"></p>
    </div>

    <div class="container hidden" id="riddle3">
        <p>Bijna daar! Nog een raadsel:</p>
        <p><strong>"Ik heb sleutels, maar geen sloten. Ik heb ruimte, maar geen kamer. Wat ben ik?"</strong></p>
        <input type="text" id="answer3" placeholder="Jouw antwoord">
        <button onclick="checkAnswer(3, 'toetsenbord')">Controleer</button>
        <p id="message3"></p>
    </div>

    <div class="container hidden" id="riddle4">
        <p>Laatste uitdaging!</p>
        <p><strong>"Hoe noem je iemand die leeft, maar doodverklaard is?"</strong></p>
        <input type="text" id="answer4" placeholder="Jouw antwoord">
        <button onclick="checkAnswer(4, 'isa')">Controleer</button>
        <p id="message4"></p>
    </div>

    <div class="container hidden" id="endScreen">
        <h1>Gefeliciteerd!</h1>
        <p>Je hebt Isa geholpen haar identiteit terug te krijgen en de waarheid te ontdekken!</p>
        <p>Dank je voor het spelen!</p>
    </div>

    <script>
        function checkAnswer(step, ...correctAnswers) {
            let answer = document.getElementById(`answer${step}`).value.toLowerCase().trim();
            if (correctAnswers.includes(answer)) {
                document.getElementById(`riddle${step}`).classList.add("hidden");
                if (document.getElementById(`riddle${step + 1}`)) {
                    document.getElementById(`riddle${step + 1}`).classList.remove("hidden");
                } else {
                    document.getElementById("endScreen").classList.remove("hidden");
                }
            } else {
                document.getElementById(`message${step}`).innerHTML = "Probeer opnieuw...";
            }
        }
    </script>
</body>
</html>
