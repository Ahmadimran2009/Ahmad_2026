---
layout: page
title: calculator
permalink: /calculator/
---
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Simple Calculator</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: #f4f4f4;
        }
        .calculator {
            background: white;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }
        input[type="text"] {
            width: 100%;
            height: 50px;
            text-align: right;
            font-size: 24px;
            border: 1px solid #ccc;
            border-radius: 5px;
            margin-bottom: 10px;
            padding: 5px;
        }
        button {
            width: 23%;
            height: 50px;
            font-size: 18px;
            margin: 1%;
            border: none;
            border-radius: 5px;
            background-color: #007bff;
            color: white;
            cursor: pointer;
        }
        button:hover {
            background-color: #0056b3;
        }
    </style>
</head>
<body>

<div class="calculator">
    <input type="text" id="result" disabled>
    <div>
        <button onclick="clearResult()">C</button>
        <button onclick="appendToResult('7')">7</button>
        <button onclick="appendToResult('8')">8</button>
        <button onclick="appendToResult('9')">9</button>
        <button onclick="appendToResult('/')">/</button>
    </div>
    <div>
        <button onclick="appendToResult('4')">4</button>
        <button onclick="appendToResult('5')">5</button>
        <button onclick="appendToResult('6')">6</button>
        <button onclick="appendToResult('*')">*</button>
    </div>
    <div>
        <button onclick="appendToResult('1')">1</button>
        <button onclick="appendToResult('2')">2</button>
        <button onclick="appendToResult('3')">3</button>
        <button onclick="appendToResult('-')">-</button>
    </div>
    <div>
        <button onclick="appendToResult('0')">0</button>
        <button onclick="calculateResult()">=</button>
        <button onclick="appendToResult('+')">+</button>
    </div>
</div>

<script>
    function appendToResult(value) {
        document.getElementById('result').value += value;
    }

    function clearResult() {
        document.getElementById('result').value = '';
    }

    function calculateResult() {
        const input = document.getElementById('result').value;
        try {
            document.getElementById('result').value = eval(input);
        } catch {
            document.getElementById('result').value = 'Error';
        }
    }
</script>

</body>
</html>