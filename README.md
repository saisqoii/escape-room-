<!DOCTYPE html>
<html lang="nl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Escape Room - Doodverklaard</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            background-color: #222;
            color: white;
            padding: 20px;
        }
        .container {
            max-width: 600px;
            margin: auto;
            background: #333;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(255, 255, 255, 0.2);
        }
        input, button {
            padding: 10px;
            margin: 10px;
            font-size: 16px;
        }
        .hidden {
            display: none;
        }
    </style>
</head>
<body>
    <div class="container" id="game">
        <h1>Escape Room: Doodverklaard</h1>
        <p>Isa is doodverklaard, maar ze leeft nog. Help haar de waarheid te achterhalen!</p>
        <p>Los het raadsel op: <br><strong>"Ik besta, maar niemand herkent me. Wat ben ik?"</strong></p>
        <input type="text" id="answer" placeholder="Jouw antwoord">
        <button onclick="checkAnswer()">Controleer</button>
        <p id="message"></p>
    </div>
    
    <div class="container hidden" id="endScreen">
        <h1>Gefeliciteerd!</h1>
        <p>Je hebt Isa geholpen haar identiteit terug te krijgen en de waarheid te ontdekken!</p>
        <p>Dank je voor het spelen!</p>
    </div>

    <script>
        function checkAnswer() {
            let answer = document.getElementById("answer").value.toLowerCase();
            if (answer === "geheim" || answer === "schaduw") {
                document.getElementById("game").classList.add("hidden");
                document.getElementById("endScreen").classList.remove("hidden");
            } else {
                document.getElementById("message").innerHTML = "Probeer opnieuw...";
            }
        }
    </script>
</body>
</html>
