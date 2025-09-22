# LCompany
<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Склад DIP8</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            padding: 50px;
        }
        .container {
            max-width: 600px;
            margin: 0 auto;
        }
        button {
            padding: 15px 30px;
            font-size: 18px;
            margin: 20px;
            cursor: pointer;
        }
        form {
            display: none;
            text-align: left;
            max-width: 400px;
            margin: 0 auto;
        }
        input, select {
            width: 100%;
            padding: 10px;
            margin: 10px 0;
        }
    </style>
</head>
<body>
    <div class="container">
        <!-- Главная страница -->
        <div id="main-page">
            <h1>Добро пожаловать на склад DIP8</h1>
            <button onclick="showForm()">Продолжить</button>
        </div>

        <!-- Форма заказа -->
        <form id="order-form">
            <h2>Заполните данные</h2>
            
            <label>Имя/наименование юр.лица:</label>
            <input type="text" id="companyName" required>
            
            <label>Номер заказа:</label>
            <input type="text" id="orderNumber" required>
            
            <label>Дата визита:</label>
            <input type="date" id="visitDate" required>
            
            <label>Время визита:</label>
            <select id="visitTime" required>
                <option value="">Выберите время</option>
                <option value="9:30 - 12:00">9:30 - 12:00</option>
                <option value="12:30 - 15:30">12:30 - 15:30</option>
                <option value="15:30 - 19:30">15:30 - 19:30</option>
            </select>
            
            <button type="submit">Отправить</button>
        </form>

        <!-- Сообщение об успехе -->
        <div id="success-message" style="display: none;">
            <h2>Данные успешно отправлены!</h2>
        </div>
    </div>

    <!-- Подключаем EmailJS -->
    <script src="https://cdn.jsdelivr.net/npm/@emailjs/browser@3/dist/email.min.js"></script>
    <script>
        // Инициализация EmailJS
        emailjs.init("YOUR_PUBLIC_KEY"); // Замените на ваш публичный ключ

        function showForm() {
            document.getElementById('main-page').style.display = 'none';
            document.getElementById('order-form').style.display = 'block';
        }

        document.getElementById('order-form').addEventListener('submit', function(e) {
            e.preventDefault();
            
            // Собираем данные формы
            const formData = {
                company_name: document.getElementById('companyName').value,
                order_number: document.getElementById('orderNumber').value,
                visit_date: document.getElementById('visitDate').value,
                visit_time: document.getElementById('visitTime').value
            };

            // Отправка письма
            emailjs.send("YOUR_SERVICE_ID", "YOUR_TEMPLATE_ID", formData) // Замените на ваши данные
                .then(function() {
                    document.getElementById('order-form').style.display = 'none';
                    document.getElementById('success-message').style.display = 'block';
                }, function(error) {
                    alert('Ошибка отправки: ' + JSON.stringify(error));
                });
        });
    </script>
</body>
</html>
