<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Alina Store ✅ - Восточные сладости и напитки</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Arial', sans-serif;
        }
        
        body {
            background-color: #f9f5f0;
            color: #333;
        }
        
        header {
            background: linear-gradient(135deg, #d4a762, #b78d4a);
            color: white;
            padding: 25px 0;
            text-align: center;
            box-shadow: 0 4px 12px rgba(0,0,0,0.1);
            position: relative;
            overflow: hidden;
        }
        
        header::before {
            content: "";
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: url('https://example.com/arabic-pattern.png') repeat;
            opacity: 0.1;
            pointer-events: none;
        }
        
        .logo {
            font-size: 2.8rem;
            font-weight: bold;
            margin-bottom: 10px;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.2);
            position: relative;
        }
        
        nav {
            background-color: #b78d4a;
            padding: 15px 0;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
        }
        
        nav ul {
            display: flex;
            justify-content: center;
            list-style: none;
        }
        
        nav ul li {
            margin: 0 25px;
            position: relative;
        }
        
        nav ul li a {
            color: white;
            text-decoration: none;
            font-weight: bold;
            font-size: 1.1rem;
            transition: all 0.3s;
            padding: 5px 10px;
            border-radius: 4px;
        }
        
        nav ul li a:hover {
            color: #f0e6d2;
            background-color: rgba(255,255,255,0.1);
            transform: translateY(-2px);
        }
        
        .container {
            max-width: 1200px;
            margin: 40px auto;
            padding: 0 25px;
        }
        
        h2 {
            font-size: 2rem;
            color: #b78d4a;
            margin-bottom: 25px;
            position: relative;
            padding-bottom: 10px;
        }
        
        h2::after {
            content: "";
            position: absolute;
            bottom: 0;
            left: 0;
            width: 80px;
            height: 3px;
            background: linear-gradient(to right, #d4a762, #f9f5f0);
        }
        
        .products-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 35px;
        }
        
        .product-card {
            background-color: white;
            border-radius: 12px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0,0,0,0.08);
            transition: all 0.3s ease;
            position: relative;
        }
        
        .product-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0,0,0,0.12);
        }
        
        .product-image {
            height: 220px;
            overflow: hidden;
            position: relative;
        }
        
        .product-image img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.5s ease;
        }
        
        .product-card:hover .product-image img {
            transform: scale(1.1);
        }
        
        .product-info {
            padding: 25px;
        }
        
        .product-title {
            font-size: 1.3rem;
            margin-bottom: 12px;
            color: #b78d4a;
            font-weight: 600;
        }
        
        .product-description {
            color: #666;
            margin-bottom: 20px;
            font-size: 0.95rem;
            line-height: 1.5;
        }
        
        .product-price {
            font-size: 1.4rem;
            font-weight: bold;
            color: #d4a762;
            margin-bottom: 20px;
        }
        
        .add-to-cart {
            background: linear-gradient(to right, #d4a762, #c79b53);
            color: white;
            border: none;
            padding: 12px 25px;
            border-radius: 6px;
            cursor: pointer;
            font-weight: bold;
            width: 100%;
            transition: all 0.3s;
            font-size: 1rem;
            box-shadow: 0 3px 6px rgba(0,0,0,0.1);
        }
        
        .add-to-cart:hover {
            background: linear-gradient(to right, #c79b53, #b78d4a);
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(0,0,0,0.15);
        }
        
        .cart-icon {
            position: fixed;
            top: 25px;
            right: 25px;
            background-color: white;
            border-radius: 50%;
            width: 60px;
            height: 60px;
            display: flex;
            align-items: center;
            justify-content: center;
            box-shadow: 0 4px 15px rgba(0,0,0,0.15);
            cursor: pointer;
            z-index: 100;
            transition: all 0.3s;
        }
        
        .cart-icon:hover {
            transform: scale(1.1);
        }
        
        .cart-icon span {
            position: absolute;
            top: -5px;
            right: -5px;
            background-color: #d4a762;
            color: white;
            border-radius: 50%;
            width: 25px;
            height: 25px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 0.9rem;
            font-weight: bold;
            box-shadow: 0 2px 5px rgba(0,0,0,0.2);
        }
        
        /* Стили для модального окна корзины */
        .cart-modal {
            display: none;
            position: fixed;
            top: 0;
            right: 0;
            width: 100%;
            max-width: 450px;
            height: 100%;
            background-color: white;
            box-shadow: -5px 0 25px rgba(0,0,0,0.15);
            z-index: 1000;
            overflow-y: auto;
            padding: 25px;
            transform: translateX(100%);
            transition: transform 0.3s ease-out;
        }
        
        .cart-modal.active {
            transform: translateX(0);
        }
        
        .cart-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 25px;
            padding-bottom: 15px;
            border-bottom: 2px solid #f0f0f0;
        }
        
        .cart-title {
            font-size: 1.6rem;
            color: #b78d4a;
            font-weight: 600;
        }
        
        .close-cart {
            background: none;
            border: none;
            font-size: 1.8rem;
            cursor: pointer;
            color: #666;
            transition: transform 0.3s;
        }
        
        .close-cart:hover {
            transform: rotate(90deg);
            color: #d4a762;
        }
        
        .cart-items {
            margin-bottom: 25px;
        }
        
        .cart-item {
            display: flex;
            margin-bottom: 20px;
            padding-bottom: 20px;
            border-bottom: 1px solid #f0f0f0;
            transition: all 0.3s;
        }
        
        .cart-item:hover {
            background-color: rgba(0,0,0,0.02);
        }
        
        .cart-item-image {
            width: 90px;
            height: 90px;
            object-fit: cover;
            border-radius: 8px;
            margin-right: 20px;
            box-shadow: 0 3px 8px rgba(0,0,0,0.1);
        }
        
        .cart-item-details {
            flex-grow: 1;
        }
        
        .cart-item-title {
            font-weight: bold;
            margin-bottom: 8px;
            font-size: 1.1rem;
            color: #555;
        }
        
        .cart-item-price {
            color: #d4a762;
            font-weight: bold;
            margin-bottom: 8px;
            font-size: 1.1rem;
        }
        
        .cart-item-quantity {
            display: flex;
            align-items: center;
            margin-top: 10px;
        }
        
        .quantity-btn {
            width: 30px;
            height: 30px;
            background-color: #f0f0f0;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-weight: bold;
            font-size: 1rem;
            transition: all 0.2s;
        }
        
        .quantity-btn:hover {
            background-color: #e0e0e0;
        }
        
        .quantity-input {
            width: 45px;
            height: 30px;
            text-align: center;
            margin: 0 8px;
            border: 1px solid #ddd;
            border-radius: 5px;
            font-weight: bold;
        }
        
        .remove-item {
            background: none;
            border: none;
            color: #ff6b6b;
            cursor: pointer;
            margin-top: 10px;
            font-size: 0.9rem;
            transition: color 0.2s;
        }
        
        .remove-item:hover {
            color: #ff5252;
            text-decoration: underline;
        }
        
        .delivery-row {
            display: flex;
            justify-content: space-between;
            padding: 15px 0;
            border-top: 2px solid #f0f0f0;
            font-weight: bold;
            font-size: 1.1rem;
            margin-top: 15px;
        }
        
        .free-delivery {
            color: #4CAF50;
        }
        
        .cart-summary {
            border-top: 2px solid #eee;
            padding-top: 25px;
            margin-top: 20px;
        }
        
        .cart-total {
            display: flex;
            justify-content: space-between;
            font-size: 1.3rem;
            font-weight: bold;
            margin-bottom: 25px;
            color: #333;
        }
        
        .checkout-btn {
            background: linear-gradient(to right, #d4a762, #c79b53);
            color: white;
            border: none;
            padding: 15px 25px;
            border-radius: 8px;
            cursor: pointer;
            font-weight: bold;
            width: 100%;
            font-size: 1.1rem;
            transition: all 0.3s;
            box-shadow: 0 4px 10px rgba(0,0,0,0.1);
            text-transform: uppercase;
            letter-spacing: 1px;
        }
        
        .checkout-btn:hover {
            background: linear-gradient(to right, #c79b53, #b78d4a);
            transform: translateY(-3px);
            box-shadow: 0 8px 20px rgba(0,0,0,0.15);
        }
        
        .empty-cart {
            text-align: center;
            padding: 50px 0;
            color: #666;
            font-size: 1.1rem;
        }
        
        .delivery-info {
            text-align: center;
            margin-top: 15px;
            color: #666;
            font-size: 0.9rem;
            padding: 10px;
            background-color: #f9f9f9;
            border-radius: 6px;
        }
        
        footer {
            background-color: #333;
            color: white;
            text-align: center;
            padding: 40px 0;
            margin-top: 70px;
        }
        
        footer p {
            margin: 10px 0;
            opacity: 0.8;
        }

        /* Стили для промокодов */
        .promo-section {
            display: flex;
            margin: 15px 0;
        }
        
        .promo-input {
            flex-grow: 1;
            padding: 12px;
            border: 1px solid #ddd;
            border-radius: 6px 0 0 6px;
            font-size: 1rem;
        }
        
        .apply-promo {
            background: linear-gradient(to right, #d4a762, #c79b53);
            color: white;
            border: none;
            padding: 0 20px;
            border-radius: 0 6px 6px 0;
            cursor: pointer;
            font-weight: bold;
            transition: all 0.3s;
        }
        
        .apply-promo:hover {
            background: linear-gradient(to right, #c79b53, #b78d4a);
        }
        
        .promo-message {
            margin-top: 10px;
            padding: 8px 12px;
            border-radius: 6px;
            text-align: center;
            font-weight: bold;
        }
        
        .promo-success {
            background-color: #d4edda;
            color: #155724;
        }
        
        .promo-error {
            background-color: #f8d7da;
            color: #721c24;
        }
        
        .discount-row {
            display: flex;
            justify-content: space-between;
            padding: 10px 0;
            font-weight: bold;
            font-size: 1.1rem;
            color: #4CAF50;
        }
        
        @media (max-width: 768px) {
            nav ul {
                flex-direction: column;
                align-items: center;
            }
            
            nav ul li {
                margin: 10px 0;
            }
            
            .products-grid {
                grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
                gap: 25px;
            }
            
            .cart-modal {
                width: 100%;
                max-width: 100%;
            }
            
            .logo {
                font-size: 2.2rem;
            }
        }
    </style>
</head>
<body>
    <header>
        <div class="logo">Alina store ✅</div>
        <p>Настоящие  и очень вкусные восточные сладости и напитки</p>
    </header>
    
    <nav>
        <ul>
            <li><a href="#chocolate">Дубайский шоколад</a></li>
            <li><a href="#milkshakes">Милкшейки</a></li>
            <li><a href="#bubble-tea">Бабл Ти</a></li>
            <li><a href="#other">Другие сладости</a></li>
        </ul>
    </nav>
    
    <div class="cart-icon">
        🛒
        <span>0</span>
    </div>
    
    <div class="container">
        <h2 id="chocolate">Дубайский шоколад</h2>
        <div class="products-grid">
            <div class="product-card" data-id="1" data-name="Dubai Gold" data-price="890" data-image="https://example.com/dubai-chocolate1.jpg">
                <div class="product-image">
                    <img src="https://sun1-24.userapi.com/impg/DC64up7CaG6OjZyi-hlLicmZnLL6QH-tYk6m6A/lwSbn3-MiMw.jpg?size=604x373&quality=96&sign=518be96f7c51e738f3226f302a19a41f&type=album" alt="Шоколад Dubai Gold">
                </div>
                <div class="product-info">
                    <h3 class="product-title">Дубайский шоколад</h3>
                    <p class="product-description">Роскошный молочный шоколад стандартный (фисташковый) (250гр.).</p>
                    <div class="product-price">890 ₽</div>
                    <button class="add-to-cart">В корзину</button>
                </div>
            </div>
            
            <div class="product-card" data-id="2" data-name="Arabian Nights" data-price="950" data-image="https://example.com/dubai-chocolate2.jpg">
                <div class="product-image">
                    <img src="https://i.postimg.cc/CLQzqfQJ/1752708729116.jpg" alt="Шоколад Arabian Nights">
                </div>
                <div class="product-info">
                    <h3 class="product-title">Дубайский Шоколад</h3>
                    <p class="product-description">Роскошный молочный шоколад (Малиновый) (250гр.).</p>
                    <div class="product-price">950 ₽</div>
                    <button class="add-to-cart">В корзину</button>
                </div>
            </div>
            
            <div class="product-card" data-id="3" data-name="Camel Milk Chocolate" data-price="470" data-image="https://i.postimg.cc/wTC8F80N/1752713796570.jpg">
                <div class="product-image">
                    <img src="https://i.postimg.cc/3rqPJQMq/IMG-20250717-035610-973.jpg" alt="Шоколад Camel Milk">
                </div>
                <div class="product-info">
                    <h3 class="product-title">Дубайский шоколад</h3>
                    <p class="product-description">Роскошный молочный шоколад (Черничный) (250гр.)</p>
                    <div class="product-price">470₽</div>
                    <button class="add-to-cart">В корзину</button>
                </div>
            </div>
            
            <div class="product-card" data-id="13" data-name="Golden Dates Chocolate" data-price="1100" data-image="https://example.com/dubai-chocolate4.jpg">
                <div class="product-image">
                    <img src="https://example.com/dubai-chocolate4.jpg" alt="Шоколад Golden Dates">
                </div>
                <div class="product-info">
                    <h3 class="product-title">Golden Dates Chocolate</h3>
                    <p class="product-description">Темный шоколад с кусочками фиников и золотой пылью (250гр.).</p>
                    <div class="product-price">1100 ₽</div>
                    <button class="add-to-cart">В корзину</button>
                </div>
            </div>
        </div>
        
        <h2 id="milkshakes" style="margin-top: 50px;">Милкшейки</h2>
        <div class="products-grid">
            <div class="product-card" data-id="4" data-name="Date Shake" data-price="450" data-image="https://example.com/milkshake1.jpg">
                <div class="product-image">
                    <img src="https://example.com/milkshake1.jpg" alt="Милкшейк Date Shake">
                </div>
                <div class="product-info">
                    <h3 class="product-title">Date Shake</h3>
                    <p class="product-description">Классический дубайский милкшейк с финиками и кардамоном.</p>
                    <div class="product-price">450 ₽</div>
                    <button class="add-to-cart">В корзину</button>
                </div>
            </div>
            
            <div class="product-card" data-id="5" data-name="Saffron Dream" data-price="550" data-image="https://example.com/milkshake2.jpg">
                <div class="product-image">
                    <img src="https://i.pinimg.com/736x/33/51/96/335196499d70a8289db246ba9dcb662f.jpg" alt="Милкшейк Saffron Dream">
                </div>
                <div class="product-info">
                    <h3 class="product-title">Saffron Dream</h3>
                    <p class="product-description">Милкшейк с шафраном - королевское наслаждение.(250мл)</p>
                    <div class="product-price">550 ₽</div>
                    <button class="add-to-cart">В корзину</button>
                </div>
            </div>
            
            <div class="product-card" data-id="6" data-name="Camel Milk Shake" data-price="600" data-image="https://example.com/milkshake3.jpg">
                <div class="product-image">
                    <img src="https://example.com/milkshake3.jpg" alt="Милкшейк Camel Milk Shake">
                </div>
                <div class="product-info">
                    <h3 class="product-title">Camel Milk Shake</h3>
                    <p class="product-description">Нежный милкшейк на основе верблюжьего молока с медом.</p>
                    <div class="product-price">600 ₽</div>
                    <button class="add-to-cart">В корзину</button>
                </div>
            </div>
        </div>
        
        <h2 id="bubble-tea" style="margin-top: 50px;">Бабл Ти</h2>
        <div class="products-grid">
            <div class="product-card" data-id="7" data-name="Dubai Pearl" data-price="400" data-image="https://example.com/bubble-tea1.jpg">
                <div class="product-image">
                    <img src="https://example.com/bubble-tea1.jpg" alt="Бабл Ти Dubai Pearl">
                </div>
                <div class="product-info">
                    <h3 class="product-title">Dubai Pearl</h3>
                    <p class="product-description">Черный чай с жемчужинами тапиоки и нотками розовой воды.</p>
                    <div class="product-price">400 ₽</div>
                    <button class="add-to-cart">В корзину</button>
                </div>
            </div>
            
            <div class="product-card" data-id="8" data-name="Golden Oasis" data-price="500" data-image="https://example.com/bubble-tea2.jpg">
                <div class="product-image">
                    <img src="https://example.com/bubble-tea2.jpg" alt="Бабл Ти Golden Oasis">
                </div>
                <div class="product-info">
                    <h3 class="product-title">Golden Oasis</h3>
                    <p class="product-description">Зеленый чай с шафраном, медом и золотыми жемчужинами.</p>
                    <div class="product-price">500 ₽</div>
                    <button class="add-to-cart">В корзину</button>
                </div>
            </div>
            
            <div class="product-card" data-id="9" data-name="Desert Flower" data-price="450" data-image="https://example.com/bubble-tea3.jpg">
                <div class="product-image">
                    <img src="https://example.com/bubble-tea3.jpg" alt="Бабл Ти Desert Flower">
                </div>
                <div class="product-info">
                    <h3 class="product-title">Desert Flower</h3>
                    <p class="product-description">Молочный бабл ти с цветочными нотами и разноцветными жемчужинами.</p>
                    <div class="product-price">450 ₽</div>
                    <button class="add-to-cart">В корзину</button>
                </div>
            </div>
        </div>
        
        <h2 id="other" style="margin-top: 50px;">Другие сладости</h2>
        <div class="products-grid">
            <div class="product-card" data-id="10" data-name="Лукум Royal" data-price="1200" data-image="https://example.com/sweets1.jpg">
                <div class="product-image">
                    <img src="https://example.com/sweets1.jpg" alt="Лукум Royal">
                </div>
                <div class="product-info">
                    <h3 class="product-title">Лукум Royal</h3>
                    <p class="product-description">Набор восточных сладостей: 8 видов традиционного лукума с орехами.</p>
                    <div class="product-price">1200 ₽</div>
                    <button class="add-to-cart">В корзину</button>
                </div>
            </div>
            
            <div class="product-card" data-id="11" data-name="Финики Medjoul" data-price="1500" data-image="https://example.com/sweets2.jpg">
                <div class="product-image">
                    <img src="https://example.com/sweets2.jpg" alt="Финики Medjoul">
                </div>
                <div class="product-info">
                    <h3 class="product-title">Финики Medjoul</h3>
                    <p class="product-description">Королевские финики сорта Medjoul, отборные, с начинкой на выбор.</p>
                    <div class="product-price">1500 ₽/кг</div>
                    <button class="add-to-cart">В корзину</button>
                </div>
            </div>
            
            <div class="product-card" data-id="12" data-name="Халва Assorted" data-price="850" data-image="https://example.com/sweets3.jpg">
                <div class="product-image">
                    <img src="https://example.com/sweets3.jpg" alt="Халва Assorted">
                </div>
                <div class="product-info">
                    <h3 class="product-title">Халва Assorted</h3>
                    <p class="product-description">Набор халвы: кунжутная, арахисовая, фисташковая с шафраном.</p>
                    <div class="product-price">850 ₽</div>
                    <button class="add-to-cart">В корзину</button>
                </div>
            </div>
        </div>
    </div>
    
    <!-- Модальное окно корзины -->
    <div class="cart-modal">
        <div class="cart-header">
            <h2 class="cart-title">Ваша корзина</h2>
            <button class="close-cart">×</button>
        </div>
        <div class="cart-items">
            <!-- Товары будут добавляться сюда динамически -->
            <div class="empty-cart">Ваша корзина пуста</div>
        </div>
        <div class="cart-summary">
            <!-- Секция для ввода промокода -->
            <div class="promo-section">
                <input type="text" class="promo-input" placeholder="Введите промокод">
                <button class="apply-promo">Применить</button>
            </div>
            <div class="promo-message"></div>
            
            <div class="discount-row" style="display: none;">
                <span>Скидка:</span>
                <span class="discount-amount">0 ₽</span>
            </div>
            
            <div class="delivery-row">
                <span>Доставка:</span>
                <span class="delivery-cost">0 ₽</span>
            </div>
            
            <div class="cart-total">
                <span>Итого:</span>
                <span class="total-price">0 ₽</span>
            </div>
            <button class="checkout-btn">Оформить заказ</button>
        </div>
    </div>
    
    <footer>
        <p>© 2023 Dubai Delights. Все права защищены.</p>
        <p>Телефон: +7 (123) 456-78-90 | Email: info@dubai-delights.ru</p>
        <p>Адрес: г. Москва, ул. Восточная, 15</p>
    </footer>
    
    <script>
        // Данные товаров
        const products = [
            { id: 1, name: "Дубайский Шоколад (фисташковый)", price: 890, image: "https://example.com/dubai-chocolate1.jpg", description: "Роскошный молочный шоколад с золотой пылью" },
            { id: 2, name: "Дубайский Шоколад (Малиновый)", price: 950, image: "https://example.com/dubai-chocolate2.jpg", description: "Темный шоколад с финиками и орехами" },
            { id: 3, name: "Дубайский шоколад (Черничный)", price: 470, image: "https://example.com/dubai-chocolate3.jpg", description: "Шоколад на верблюжьем молоке" },
            { id: 13, name: "Golden Dates Chocolate", price: 1100, image: "https://example.com/dubai-chocolate4.jpg", description: "Темный шоколад с кусочками фиников и золотой пылью" },
            { id: 4, name: "Date Shake", price: 450, image: "https://example.com/milkshake1.jpg", description: "Милкшейк с финиками и кардамоном" },
            { id: 5, name: "Saffron Dream", price: 550, image: "https://example.com/milkshake2.jpg", description: "Милкшейк с шафраном и розовой водой" },
            { id: 6, name: "Camel Milk Shake", price: 600, image: "https://example.com/milkshake3.jpg", description: "Милкшейк на верблюжьем молоке" },
            { id: 7, name: "Dubai Pearl", price: 400, image: "https://example.com/bubble-tea1.jpg", description: "Черный чай с жемчужинами тапиоки" },
            { id: 8, name: "Golden Oasis", price: 500, image: "https://example.com/bubble-tea2.jpg", description: "Зеленый чай с шафраном и медом" },
            { id: 9, name: "Desert Flower", price: 450, image: "https://example.com/bubble-tea3.jpg", description: "Молочный бабл ти с цветочными нотами" },
            { id: 10, name: "Лукум Royal", price: 1200, image: "https://example.com/sweets1.jpg", description: "Набор восточных сладостей" },
            { id: 11, name: "Финики Medjoul", price: 1500, image: "https://example.com/sweets2.jpg", description: "Королевские финики сорта Medjoul" },
            { id: 12, name: "Халва Assorted", price: 850, image: "https://example.com/sweets3.jpg", description: "Набор халвы" }
        ];

        // Корзина
        let cart = [];
        let discount = 0; // Скидка в процентах
        let appliedPromo = ''; // Примененный промокод
        const cartCounter = document.querySelector('.cart-icon span');
        const cartModal = document.querySelector('.cart-modal');
        const cartItemsContainer = document.querySelector('.cart-items');
        const totalPriceElement = document.querySelector('.total-price');
        const discountAmountElement = document.querySelector('.discount-amount');
        const discountRow = document.querySelector('.discount-row');
        const deliveryCostElement = document.querySelector('.delivery-cost');
        const emptyCartMessage = document.querySelector('.empty-cart');
        const promoInput = document.querySelector('.promo-input');
        const applyPromoBtn = document.querySelector('.apply-promo');
        const promoMessage = document.querySelector('.promo-message');

        // Открытие/закрытие корзины
        document.querySelector('.cart-icon').addEventListener('click', () => {
            cartModal.style.display = 'block';
            setTimeout(() => {
                cartModal.classList.add('active');
            }, 10);
            renderCart();
        });

        document.querySelector('.close-cart').addEventListener('click', () => {
            cartModal.classList.remove('active');
            setTimeout(() => {
                cartModal.style.display = 'none';
            }, 300);
        });

        // Добавление товаров в корзину
        document.querySelectorAll('.add-to-cart').forEach(button => {
            button.addEventListener('click', (e) => {
                const productCard = e.target.closest('.product-card');
                const productId = parseInt(productCard.getAttribute('data-id'));
                addToCart(productId);
                
                // Анимация добавления в корзину
                button.textContent = 'Добавлено!';
                button.style.backgroundColor = '#4CAF50';
                
                setTimeout(() => {
                    button.textContent = 'В корзину';
                    button.style.backgroundColor = '';
                    button.style.backgroundImage = 'linear-gradient(to right, #d4a762, #c79b53)';
                }, 1000);
            });
        });

        // Функция добавления в корзину
        function addToCart(productId) {
            const product = products.find(p => p.id === productId);
            if (!product) return;

            const existingItem = cart.find(item => item.id === productId);
            
            if (existingItem) {
                existingItem.quantity += 1;
            } else {
                cart.push({
                    ...product,
                    quantity: 1
                });
            }
            
            updateCartCounter();
            saveCartToLocalStorage();
        }

        // Функция обновления счетчика корзины
        function updateCartCounter() {
            const totalItems = cart.reduce((sum, item) => sum + item.quantity, 0);
            cartCounter.textContent = totalItems;
        }

        // Функция отрисовки корзины
        function renderCart() {
            if (cart.length === 0) {
                emptyCartMessage.style.display = 'block';
                cartItemsContainer.innerHTML = '';
                totalPriceElement.textContent = '0 ₽';
                deliveryCostElement.textContent = '0 ₽';
                discountRow.style.display = 'none';
                promoMessage.textContent = '';
                return;
            }
            
            emptyCartMessage.style.display = 'none';
            
            let cartHTML = '';
            let subtotal = 0;
            
            cart.forEach(item => {
                subtotal += item.price * item.quantity;
                
                cartHTML += `
                    <div class="cart-item" data-id="${item.id}">
                        <img src="${item.image}" alt="${item.name}" class="cart-item-image">
                        <div class="cart-item-details">
                            <div class="cart-item-title">${item.name}</div>
                            <div class="cart-item-price">${item.price} ₽</div>
                            <div class="cart-item-quantity">
                                <button class="quantity-btn minus">-</button>
                                <input type="number" value="${item.quantity}" min="1" class="quantity-input">
                                <button class="quantity-btn plus">+</button>
                            </div>
                            <button class="remove-item">Удалить</button>
                        </div>
                    </div>
                `;
            });
            
            // Расчет стоимости доставки
            const deliveryCost = subtotal >= 2000 ? 0 : 200;
            const deliveryText = subtotal >= 2000 
                ? '<span class="free-delivery">Бесплатная доставка</span>' 
                : 'Доставка: 200 ₽';
            
            // Расчет скидки
            const discountAmount = Math.round(subtotal * discount / 100);
            const discountedSubtotal = subtotal - discountAmount;
            
            // Общая сумма (товары - скидка + доставка)
            const totalPrice = discountedSubtotal + deliveryCost;
            
            // Обновление элементов интерфейса
            deliveryCostElement.textContent = deliveryCost === 0 ? 'Бесплатно' : `${deliveryCost} ₽`;
            
            if (discount > 0) {
                discountRow.style.display = 'flex';
                discountAmountElement.textContent = `-${discountAmount} ₽`;
            } else {
                discountRow.style.display = 'none';
            }
            
            totalPriceElement.textContent = `${totalPrice} ₽`;
            
            // Добавляем информацию о бесплатной доставке
            if (subtotal < 2000) {
                const needed = 2000 - subtotal;
                cartHTML += `
                    <div class="delivery-info">
                        Добавьте ещё ${needed} ₽ для бесплатной доставки
                    </div>
                `;
            }
            
            cartItemsContainer.innerHTML = cartHTML;
            
            // Добавляем обработчики для кнопок в корзине
            document.querySelectorAll('.quantity-btn.minus').forEach(btn => {
                btn.addEventListener('click', decreaseQuantity);
            });
            
            document.querySelectorAll('.quantity-btn.plus').forEach(btn => {
                btn.addEventListener('click', increaseQuantity);
            });
            
            document.querySelectorAll('.quantity-input').forEach(input => {
                input.addEventListener('change', updateQuantity);
            });
            
            document.querySelectorAll('.remove-item').forEach(btn => {
                btn.addEventListener('click', removeItem);
            });
        }

        // Применение промокода
        applyPromoBtn.addEventListener('click', applyPromoCode);
        
        // Обработка нажатия Enter в поле промокода
        promoInput.addEventListener('keypress', (e) => {
            if (e.key === 'Enter') {
                applyPromoCode();
            }
        });
        
        function applyPromoCode() {
            const promoCode = promoInput.value.trim();
            
            if (!promoCode) {
                showPromoMessage('Введите промокод', 'error');
                return;
            }
            
            // Проверяем промокод
            if (promoCode.toLowerCase() === 'каролина') {
                discount = 50; // 50% скидка
                appliedPromo = promoCode;
          showPromoMessage('Скидка применена ✅', 'success');
                saveCartToLocalStorage();
                renderCart();
            } else {
                discount = 0;
                appliedPromo = '';
                showPromoMessage('Промокод неверный ❌', 'error');
                saveCartToLocalStorage();
                renderCart();
            }
        }
        
        function showPromoMessage(message, type) {
            promoMessage.textContent = message;
            promoMessage.className = 'promo-message';
            promoMessage.classList.add(`promo-${type}`);
            
            // Очищаем сообщение через 3 секунды
            setTimeout(() => {
                promoMessage.textContent = '';
                promoMessage.className = 'promo-message';
            }, 3000);
        }

        // Функции для работы с количеством товаров
        function decreaseQuantity(e) {
            const itemId = parseInt(e.target.closest('.cart-item').getAttribute('data-id'));
            const item = cart.find(item => item.id === itemId);
            
            if (item.quantity > 1) {
                item.quantity -= 1;
            } else {
                cart = cart.filter(item => item.id !== itemId);
            }
            
            saveCartToLocalStorage();
            updateCartCounter();
            renderCart();
        }

        function increaseQuantity(e) {
            const itemId = parseInt(e.target.closest('.cart-item').getAttribute('data-id'));
            const item = cart.find(item => item.id === itemId);
            
            item.quantity += 1;
            
            saveCartToLocalStorage();
            updateCartCounter();
            renderCart();
        }

        function updateQuantity(e) {
            const itemId = parseInt(e.target.closest('.cart-item').getAttribute('data-id'));
            const item = cart.find(item => item.id === itemId);
            const newQuantity = parseInt(e.target.value);
            
            if (newQuantity > 0) {
                item.quantity = newQuantity;
            } else {
                cart = cart.filter(item => item.id !== itemId);
            }
            
            saveCartToLocalStorage();
            updateCartCounter();
            renderCart();
        }

        function removeItem(e) {
            const itemId = parseInt(e.target.closest('.cart-item').getAttribute('data-id'));
            cart = cart.filter(item => item.id !== itemId);
            
            saveCartToLocalStorage();
            updateCartCounter();
            renderCart();
        }

        // Оформление заказа
        document.querySelector('.checkout-btn').addEventListener('click', () => {
            if (cart.length === 0) {
                alert('Ваша корзина пуста!');
                return;
            }
            
            // Рассчитываем итоговую сумму
            const subtotal = cart.reduce((sum, item) => sum + (item.price * item.quantity), 0);
            const discountAmount = Math.round(subtotal * discount / 100);
            const discountedSubtotal = subtotal - discountAmount;
            const deliveryCost = subtotal >= 2000 ? 0 : 200;
            const totalPrice = discountedSubtotal + deliveryCost;
            
            // Формируем сообщение
            let message = `Заказ оформлен!\nСумма товаров: ${subtotal} ₽`;
            
            if (discount > 0) {
                message += `\nСкидка ${discount}%: -${discountAmount} ₽`;
            }
            
            if (deliveryCost === 0) {
                message += '\nБесплатная доставка!';
            } else {
                message += `\nСтоимость доставки: ${deliveryCost} ₽`;
            }
            
            message += `\nИтого к оплате: ${totalPrice} ₽\nСпасибо за покупку!`;
            
            alert(message);
            
            // Очищаем корзину
            cart = [];
            discount = 0;
            appliedPromo = '';
            saveCartToLocalStorage();
            updateCartCounter();
            renderCart();
            cartModal.classList.remove('active');
            setTimeout(() => {
                cartModal.style.display = 'none';
            }, 300);
        });

        // Сохранение корзины в localStorage
        function saveCartToLocalStorage() {
            const cartData = {
                items: cart,
                discount: discount,
                appliedPromo: appliedPromo
            };
            localStorage.setItem('dubaiDelightsCart', JSON.stringify(cartData));
        }

        // Загрузка корзины из localStorage
        function loadCartFromLocalStorage() {
            const savedCart = localStorage.getItem('dubaiDelightsCart');
            if (savedCart) {
                const cartData = JSON.parse(savedCart);
                cart = cartData.items || [];
                discount = cartData.discount || 0;
                appliedPromo = cartData.appliedPromo || '';
                
                // Если был применен промокод, показываем его в поле ввода
                if (appliedPromo) {
                    promoInput.value = appliedPromo;
                }
                
                updateCartCounter();
            }
        }

        // Плавная прокрутка для навигации
        document.querySelectorAll('nav a').forEach(anchor => {
            anchor.addEventListener('click', function(e) {
                e.preventDefault();
                
                const targetId = this.getAttribute('href');
                const targetElement = document.querySelector(targetId);
                
                window.scrollTo({
                    top: targetElement.offsetTop - 100,
                    behavior: 'smooth'
                });
            });
        });

        // Инициализация при загрузке страницы
        document.addEventListener('DOMContentLoaded', () => {
            loadCartFromLocalStorage();
        });
    </script>
</body>
</html>
