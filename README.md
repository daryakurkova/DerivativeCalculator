<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Калькулятор производной</title>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/mathjs/11.4.0/math.min.js"></script>
</head>
<body>
    <h1>Калькулятор производной функции</h1>
    <label for="expression">Введите функцию (например, x^2, sin(x), ln(x)): </label>
    <input type="text" id="expression" placeholder="Введите функцию">
    <button onclick="calculateDerivative()">Вычислить производную</button>
    
    <h2>Результат:</h2>
    <p id="result"></p>

    <script>
        function calculateDerivative() {
            // Получаем строку с функцией
            let expr = document.getElementById('expression').value;
            
            // Проверяем, что строка не пустая
            if (!expr) {
                document.getElementById('result').innerText = 'Введите функцию.';
                return;
            }

            try {
                // Используем библиотеку math.js для парсинга и вычисления производной
                let derivative = math.derivative(expr, 'x').toString();

                // Выводим результат
                document.getElementById('result').innerText = `Производная: ${derivative}`;
            } catch (error) {
                document.getElementById('result').innerText = 'Ошибка: Невозможно вычислить производную.';
            }
        }
    </script>
</body>
</html>
