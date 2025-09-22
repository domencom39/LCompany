# LCompany
<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Добро пожаловать на склад DIP8</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <div class="container">
        <div class="welcome-card">
            <h1>Добро пожаловать на склад DIP8</h1>
            <p>Система подготовки заказов</p>
            <button onclick="location.href='order.html'" class="btn-continue">
                Продолжить
            </button>
        </div>
    </div>
</body>
</html>
<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Данные по заказу</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <div class="container">
        <div class="form-card">
            <h1>Данные по заказу</h1>
            <form id="orderForm">
                <div class="form-group">
                    <label for="organization">Имя/Наименование организации:</label>
                    <input type="text" id="organization" name="organization" required>
                </div>
                <div class="form-group">
                    <label for="orderNumber">Номер заказа:</label>
                    <input type="text" id="orderNumber" name="orderNumber" required>
                </div>
                <div class="form-group">
                    <label for="deliveryDate">Когда хотите получить заказ:</label>
                    <input type="date" id="deliveryDate" name="deliveryDate" required>
                </div>
                <div class="form-group">
                    <label>Желаемое время вашего визита:</label>
                    <div class="radio-group">
                        <label>
                            <input type="radio" name="visitTime" value="9:30-12:00" required>
                            с 9:30 до 12:00
                        </label>
                        <label>
                            <input type="radio" name="visitTime" value="12:30-15:30">
                            с 12:30 до 15:30
                        </label>
                        <label>
                            <input type="radio" name="visitTime" value="16:00-19:30">
                            с 16:00 до 19:30
                        </label>
                    </div>
                </div>
                <button type="submit" class="btn-submit">Завершить подготовку заказа</button>
            </form>         
            <button onclick="location.href='index.html'" class="btn-back">
                ← Назад
            </button>
        </div>
    </div>
    <script>
