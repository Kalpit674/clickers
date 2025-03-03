<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Tap Tap Clicker Game</title>
    <style>
        body {
            text-align: center;
            font-family: Arial, sans-serif;
            background-color: #f5f5f5;
        }
        h1 {
            color: #333;
        }
        #score {
            font-size: 24px;
            margin: 20px;
        }
        #clickButton {
            font-size: 20px;
            padding: 15px 30px;
            background-color: #28a745;
            color: white;
            border: none;
            border-radius: 10px;
            cursor: pointer;
            transition: 0.2s;
        }
        #clickButton:hover {
            background-color: #218838;
        }
        #clickButton:active {
            transform: scale(0.95);
        }
    </style>
</head>
<body>

    <h1>Tap Tap Clicker Game</h1>
    <p id="score">Score: 0</p>
    <button id="clickButton">Tap to Earn Points</button>

    <script>
        let score = 0;
        const scoreDisplay = document.getElementById("score");
        const button = document.getElementById("clickButton");

        button.addEventListener("click", function() {
            score++;
            scoreDisplay.innerText = "Score: " + score;
        });
    </script>

</body>
</html># clickers
game to pass the time long journeys
