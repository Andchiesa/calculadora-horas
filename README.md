# Calculadora-Horas

<html>
<head>
  <title>Calculadora de Horas de Operação</title>
  <style>
    body {
      font-family: sans-serif;
    }
    label {
      display: block;
      margin-bottom: 5px;
    }
    input[type="number"] {
      width: 100%;
      padding: 8px;
      margin-bottom: 10px;
      box-sizing: border-box;
    }
    button {
      padding: 10px 20px;
      background-color: #4CAF50;
      color: white;
      border: none;
      cursor: pointer;
    }
    #resultado {
      margin-top: 10px;
      font-weight: bold;
    }
  </style>
</head>
<body>

  <h1>Calculadora de Horas de Operação</h1>

  <label for="consumo">Consumo Horário Médio de Combustível (l/h):</label>
  <input type="number" id="consumo" value="" placeholder="Ex: 10" required>

  <label for="combustivel">Quantidade de Combustível Consumido (litros):</label>
  <input type="number" id="combustivel" value="" placeholder="Ex: 50" required>

  <button onclick="calcularHoras()">Calcular</button>

  <div id="resultado"></div>

  <script>
    function calcularHoras() {
      const consumo = parseFloat(document.getElementById("consumo").value);
      const combustivel = parseFloat(document.getElementById("combustivel").value);

      if (isNaN(consumo) || isNaN(combustivel) || consumo <= 0) {
        document.getElementById("resultado").innerHTML = "Por favor, insira valores válidos.";
        return;
      }

      const horas = combustivel / consumo;
      document.getElementById("resultado").innerHTML = `Horas de operação estimadas: ${horas.toFixed(2)} horas`;
    }
  </script>

</body>
</html>
