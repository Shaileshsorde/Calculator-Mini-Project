<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Calculator Mini Project</title>

  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: "Poppins", sans-serif;
    }

    body {
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      background: linear-gradient(135deg, #6a11cb, #2575fc);
    }

    .calculator {
      background: #fff;
      border-radius: 20px;
      box-shadow: 0 4px 15px rgba(0, 0, 0, 0.2);
      padding: 20px;
      width: 300px;
    }

    #display {
      width: 100%;
      height: 60px;
      border: none;
      outline: none;
      background: #f3f3f3;
      border-radius: 10px;
      font-size: 2rem;
      text-align: right;
      padding-right: 10px;
      margin-bottom: 15px;
    }

    .buttons {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 10px;
    }

    .btn {
      background: #e0e0e0;
      border: none;
      border-radius: 10px;
      padding: 20px;
      font-size: 1.2rem;
      cursor: pointer;
      transition: 0.3s;
    }

    .btn:hover {
      background: #d4d4d4;
    }

    .operator {
      background: #ff9f43;
      color: white;
    }

    .operator:hover {
      background: #ff7b00;
    }

    .equal {
      grid-column: span 2;
      background: #28a745;
      color: white;
    }

    .equal:hover {
      background: #218838;
    }
  </style>
</head>
<body>

  <div class="calculator">
    <input type="text" id="display" disabled />
    <div class="buttons">
      <button class="btn" onclick="clearDisplay()">C</button>
      <button class="btn" onclick="deleteLast()">DEL</button>
      <button class="btn" onclick="appendValue('%')">%</button>
      <button class="btn operator" onclick="appendValue('/')">÷</button>

      <button class="btn" onclick="appendValue('7')">7</button>
      <button class="btn" onclick="appendValue('8')">8</button>
      <button class="btn" onclick="appendValue('9')">9</button>
      <button class="btn operator" onclick="appendValue('*')">×</button>

      <button class="btn" onclick="appendValue('4')">4</button>
      <button class="btn" onclick="appendValue('5')">5</button>
      <button class="btn" onclick="appendValue('6')">6</button>
      <button class="btn operator" onclick="appendValue('-')">−</button>

      <button class="btn" onclick="appendValue('1')">1</button>
      <button class="btn" onclick="appendValue('2')">2</button>
      <button class="btn" onclick="appendValue('3')">3</button>
      <button class="btn operator" onclick="appendValue('+')">+</button>

      <button class="btn" onclick="appendValue('0')">0</button>
      <button class="btn" onclick="appendValue('.')">.</button>
      <button class="btn equal" onclick="calculate()">=</button>
    </div>
  </div>

  <script>
    const display = document.getElementById("display");

    function appendValue(value) {
      display.value += value;
    }

    function clearDisplay() {
      display.value = "";
    }

    function deleteLast() {
      display.value = display.value.slice(0, -1);
    }

    function calculate() {
      try {
        display.value = eval(display.value);
      } catch {
        display.value = "Error";
      }
    }
  </script>
</body>
</html>
