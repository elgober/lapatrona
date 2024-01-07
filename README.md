<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Nos vamos a volver a ver?</title>
    <style>
        body {
            text-align: center;
            padding: 50px;
        }

        #button-container {
            position: relative;
            display: inline-block;
        }

        #si-btn, #no-btn {
            cursor: pointer;
            margin: 0 10px;
        }

        #no-btn {
            position: absolute;
        }

        #response-text {
            display: none;
            margin-top: 20px;
        }
    </style>
</head>
<body>
    <h1>Nos vamos a volver a ver?</h1>
    
    <div id="button-container">
        <button id="si-btn" onclick="showResponse('Cuando quieras mi chula')">Sí</button>
        <button id="no-btn" onmouseover="moveNoButton()" onmouseout="stopMoveNoButton()">No</button>
    </div>

    <p id="response-text"></p>

    <script>
        var noButtonInterval;

        function moveNoButton() {
            noButtonInterval = setInterval(function () {
                var noButton = document.getElementById('no-btn');
                noButton.style.transform = 'translate(' + getRandomValue(10) + 'px, ' + getRandomValue(10) + 'px)';
            }, 100);
        }

        function stopMoveNoButton() {
            clearInterval(noButtonInterval);
        }

        function getRandomValue(max) {
            return Math.floor(Math.random() * (max * 2 + 1)) - max;
        }

        function showResponse(response) {
            document.getElementById('response-text').innerText = response;
            document.getElementById('response-text').style.display = 'block';
            document.getElementById('si-btn').disabled = true;
            document.getElementById('no-btn').disabled = true;
        }
    </script>
</body>
</html>
