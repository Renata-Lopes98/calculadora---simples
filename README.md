# calculadora---simples
Calculadora Básica com HTML (estrutura), CSS (Estilo) e JavaScript (lógica)
<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Calculadora</title>
<style>
    body {
        font-family: Arial, sans-serif;
        background: #f0f0f0;
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100vh;
    }
    .calculadora {
        background: #222;
        padding: 20px;
        border-radius: 10px;
        box-shadow: 0px 0px 15px rgba(0,0,0,0.5);
    }
    #display {
        width: 100%;
        height: 50px;
        background: #fff;
        border: none;
        font-size: 24px;
        text-align: right;
        padding: 10px;
        margin-bottom: 10px;
        border-radius: 5px;
    }
    .botoes {
        display: grid;
        grid-template-columns: repeat(4, 60px);
        gap: 10px;
    }
    button {
        height: 60px;
        font-size: 20px;
        background: #444;
        color: white;
        border: none;
        border-radius: 5px;
        cursor: pointer;
    }
    button:hover {
        background: #666;
    }
    .igual {
        background: #ff9500;
    }
    .igual:hover {
        background: #e08900;
    }
</style>
</head>
<body>
    <div class="calculadora">
        <input type="text" id="display" disabled>
        <div class="botoes">
            <button onclick="adicionar('7')">7</button>
            <button onclick="adicionar('8')">8</button>
            <button onclick="adicionar('9')">9</button>
            <button onclick="adicionar('/')">÷</button>

            <button onclick="adicionar('4')">4</button>
            <button onclick="adicionar('5')">5</button>
            <button onclick="adicionar('6')">6</button>
            <button onclick="adicionar('*')">×</button>

            <button onclick="adicionar('1')">1</button>
            <button onclick="adicionar('2')">2</button>
            <button onclick="adicionar('3')">3</button>
            <button onclick="adicionar('-')">−</button>

            <button onclick="adicionar('0')">0</button>
            <button onclick="adicionar('.')">.</button>
            <button onclick="calcular()" class="igual">=</button>
            <button onclick="adicionar('+')">+</button>

            <button onclick="limpar()" style="grid-column: span 4; background:#c0392b;">C</button>
        </div>
    </div>

<script>
    let display = document.getElementById('display');

    function adicionar(valor) {
        display.value += valor;
    }

    function calcular() {
        try {
            display.value = eval(display.value);
        } catch {
            display.value = "Erro";
        }
    }

    function limpar() {
        display.value = "";
    }
</script>
</body>
</html>

