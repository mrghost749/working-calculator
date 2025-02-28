<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Calculator</title>
    <style>
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: #11111;
        }
        .calculator {
            background: #222;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(255, 300, 255, 0.2);
        }
        .display {
            width: 100%;
            height: 50px;
            text-align: right;
            font-size: 2em;
            margin-bottom: 10px;
            padding: 5px;
            background: #333;
            color: white;
            border: none;
            border-radius: 5px;
        }
        .buttons {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 6px;
        }
        button {
            width: 60px;
            height: 60px;
            font-size: 1.5em;
            border: none;
            border-radius: 5px;
            background: #444;
            color: white;
            cursor: pointer;
        }
        button:hover {
            background: #666;
        }
        .equal {
            grid-column: span 2;
            background: #00cc66;
        }
        .equal:hover {
            background: #00aa55;
        }
        .clear {
            background: #cc0000;
        }
        .clear:hover {
            background: #aa0000;
        }
    </style>
</head>
<body>
    <div class="calculator">
        <input type="text" class="display" id="display" disabled>
        <div class="buttons">
            <button onclick="clearDisplay()" class="clear">C</button>
            <button onclick="appendToDisplay('7')">7</button>
            <button onclick="appendToDisplay('8')">8</button>
            <button onclick="appendToDisplay('9')">9</button>
            <button onclick="appendToDisplay('/')">/</button>
            <button onclick="appendToDisplay('4')">4</button>
            <button onclick="appendToDisplay('5')">5</button>
            <button onclick="appendToDisplay('6')">6</button>
            <button onclick="appendToDisplay('*')">*</button>
            <button onclick="appendToDisplay('1')">1</button>
            <button onclick="appendToDisplay('2')">2</button>
            <button onclick="appendToDisplay('3')">3</button>
            <button onclick="appendToDisplay('-')">-</button>
            <button onclick="appendToDisplay('0')">0</button>
            <button onclick="appendToDisplay('.')">.</button>
            <button onclick="calculate()" class="equal">=</button>
            <button onclick="appendToDisplay('+')">+</button>
        </div>
    </div>
    <script>
        function appendToDisplay(value) {
            document.getElementById('display').value += value;
        }
        function clearDisplay() {
            document.getElementById('display').value = '';
        }
        function calculate() {
            try {
                document.getElementById('display').value = eval(document.getElementById('display').value);
            } catch (e) {
                alert('Invalid Expression');
                clearDisplay();
            }
        }
    </script>
</body>
</html>
