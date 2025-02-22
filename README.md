<!DOCTYPE html>
<html lang="ar">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>منصة كراء وبيع الأدوات</title>
    <link rel="stylesheet" href="styles.css">
    <script defer src="script.js"></script>
    <style>
        body {
            font-family: 'Tajawal', sans-serif;
            background-color: #f8f9fa;
            color: #333;
            margin: 0;
            padding: 0;
        }
        header {
            background: linear-gradient(135deg, #007bff, #0056b3);
            color: white;
            padding: 15px;
            text-align: center;
            display: flex;
            align-items: center;
            justify-content: space-between;
        }
        .logo {
            font-size: 1.5em;
            font-weight: bold;
        }
        .content-section {
            background-color: white;
            padding: 20px;
            margin: 15px;
            border-radius: 10px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
        }
        button {
            background: linear-gradient(135deg, #ff7f50, #ff4500);
            color: white;
            border: none;
            padding: 10px 15px;
            margin: 5px;
            border-radius: 5px;
            cursor: pointer;
            font-weight: bold;
            transition: 0.3s ease-in-out;
        }
        button:hover {
            background: linear-gradient(135deg, #ff4500, #c53030);
        }
        nav {
            text-align: center;
            margin: 10px 0;
        }
        .offer-list img, .tool-list img, .item-list img {
            width: 120px;
            height: 120px;
            border-radius: 10px;
            margin: 10px;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.2);
        }
        .bottom-bar {
            position: fixed;
            bottom: 0;
            left: 0;
            width: 100%;
            background: #007bff;
            color: white;
            text-align: center;
            padding: 10px;
            display: flex;
            justify-content: space-around;
        }
    </style>
</head>
<body>
    <header>
        <img src="algeria-flag.png" alt="علم الجزائر" width="50">
        <div class="logo">منصة كراء وبيع الأدوات</div>
        <input type="text" id="search" placeholder="🔍 بحث..." onkeyup="searchItems()">
    </header>
    
    <nav>
        <button class="tab" data-target="rentTools">كراء الأدوات</button>
        <button class="tab" data-target="sellItems">بيع الأشياء المستعملة</button>
    </nav>
    
    <section id="offers" class="content-section">
        <div class="filters">
            <button>الفئة</button>
            <button>السعر</button>
            <button>الموقع</button>
        </div>
        <div class="offer-list" id="itemsList">
            <img src="https://m.media-amazon.com/images/I/61k0ydxg+wL._AC_SL1500_.jpg" alt="حقيبة">
            <img src="https://cdn.salla.sa/rAoqGR/5ecdbbec-2fbc-4f86-b22f-d5520a8e06f1-804.6875x1000-yDm7ZdXLpeuyFUnP263ci036gobkmu3AyoERjQPa.jpg" alt="فستان">
            <img src="https://cdn.salla.sa/BDaqy/pU9xm7lWYsjBBPyIFC0Uo9Odah7svXfkSBaMGoe0.png" alt="كعب لامع ">
        </div>
    </section>
    
    <section id="login" class="hidden content-section">
        <h2>تسجيل الدخول</h2>
        <form>
            <input type="text" placeholder="اسم المستخدم" required>
            <input type="password" placeholder="كلمة المرور" required>
            <button type="submit">تسجيل الدخول</button>
        </form>
        <button onclick="showRegister()">إنشاء حساب</button>
    </section>
    
    <section id="register" class="hidden content-section">
        <h2>إنشاء حساب</h2>
        <form>
            <input type="text" placeholder="الاسم" required>
            <input type="email" placeholder="البريد الإلكتروني" required>
            <input type="password" placeholder="كلمة المرور" required>
            <button type="submit">إنشاء</button>
        </form>
    </section>
    
    <section id="rentTools" class="content-section hidden">
        <h2>كراء الأدوات</h2>
        <input type="text" placeholder="🔍 بحث عن الأدوات..." onkeyup="searchItems()">
        <div class="tool-list">
            <img src="rent1.jpg" alt="أداة للإيجار 1">
            <img src="rent2.jpg" alt="أداة للإيجار 2">
        </div>
    </section>
    
    <section id="sellItems" class="content-section hidden">
        <h2>بيع الأشياء المستعملة</h2>
        <input type="text" placeholder="🔍 بحث عن المنتجات...">
        <button>+ أضف منتج</button>
        <div class="item-list">
            <img src="item1.jpg" alt="منتج 1">
            <img src="item2.jpg" alt="منتج 2">
        </div>
    </section>
    
    <div class="bottom-bar">
        <button onclick="showLogin()">تسجيل الدخول</button>
        <button onclick="showAddAd()">+ أضف إعلان</button>
    </div>
    
    <script>
        function searchItems() {
            let input = document.getElementById('search').value.toLowerCase();
            let items = document.querySelectorAll('.offer-list img');
            items.forEach(item => {
                let altText = item.alt.toLowerCase();
                item.style.display = altText.includes(input) ? "block" : "none";
            });
        }
        
        function showLogin() {
            document.getElementById('login').classList.remove('hidden');
            document.getElementById('register').classList.add('hidden');
        }
        
        function showRegister() {
            document.getElementById('login').classList.add('hidden');
            document.getElementById('register').classList.remove('hidden');
        }
    </script>
</body>
</html>

 