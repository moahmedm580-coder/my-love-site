# my-love-site
my-love-site
<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>عيد حب سعيد</title>
    <style>
        :root {
            --primary-pink: #ff4d6d;
            --dark-bg: #0f0c29;
            --accent-purple: #302b63;
        }

        body {
            margin: 0;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(to bottom, #0f0c29, #302b63, #24243e);
            color: white;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            overflow: hidden;
            text-align: center;
        }

        /* حاوية الصفحات */
        .container {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            padding: 2rem;
            border-radius: 20px;
            box-shadow: 0 8px 32px 0 rgba(0, 0, 0, 0.37);
            border: 1px solid rgba(255, 255, 255, 0.18);
            width: 90%;
            max-width: 400px;
            z-index: 10;
        }

        .page { display: none; }
        .active { display: block; animation: fadeIn 0.8s ease-in-out; }

        input {
            width: 80%;
            padding: 12px;
            margin: 20px 0;
            border-radius: 10px;
            border: none;
            outline: none;
            background: rgba(255, 255, 255, 0.2);
            color: white;
            font-size: 1.2rem;
            text-align: center;
        }

        button {
            background: var(--primary-pink);
            color: white;
            border: none;
            padding: 10px 25px;
            border-radius: 50px;
            cursor: pointer;
            font-size: 1.1rem;
            transition: 0.3s;
            box-shadow: 0 0 15px var(--primary-pink);
        }

        button:hover { transform: scale(1.1); box-shadow: 0 0 25px var(--primary-pink); }

        /* الأنيميشن والقلوب */
        .heart-bg {
            position: absolute;
            top: 0; left: 0; width: 100%; height: 100%;
            pointer-events: none;
            z-index: 1;
        }

        .heart {
            position: absolute;
            color: var(--primary-pink);
            font-size: 1.5rem;
            animation: moveUp 4s linear infinite;
            opacity: 0.6;
        }

        @keyframes moveUp {
            0% { transform: translateY(100vh) scale(0); opacity: 1; }
            100% { transform: translateY(-10vh) scale(1.5); opacity: 0; }
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        h1 { font-size: 1.8rem; margin-bottom: 1rem; }
        p { font-size: 1.3rem; line-height: 1.6; }

    </style>
</head>
<body>

    <div class="heart-bg" id="heartContainer"></div>

    <div class="container">
        <div id="page1" class="page active">
            <h1>❤️ مرحباً بك ❤️</h1>
            <p>أدخل كلمة السر لفتح الهدية</p>
            <input type="password" id="pass1" placeholder="****">
            <br>
            <button onclick="checkPass1()">دخول</button>
        </div>

        <div id="page2" class="page">
            <h1>كل عيد حب وانتي معايه يقلبي ❤️</h1>
            <p>محضرلك مفاجأة تانية.. أدخلي الكود التاني</p>
            <input type="password" id="pass2" placeholder="****">
            <br>
            <button onclick="checkPass2()">كشف المفاجأة</button>
        </div>

        <div id="page3" class="page">
            <h1 style="color: #00f2fe;">🔥 حمو الجن بيمسي عليك يحبي 🔥</h1>
            <p>أحلى مسا من الجن لعيونك!</p>
            <button onclick="location.reload()">ابدأ من جديد</button>
        </div>
    </div>

    <script>
        // وظيفة التحقق من كلمة السر الأولى
        function checkPass1() {
            const p1 = document.getElementById('pass1').value;
            if(p1 === '1111') {
                document.getElementById('page1').classList.remove('active');
                document.getElementById('page2').classList.add('active');
            } else {
                alert('كلمة السر غلط يا بطل!');
            }
        }

        // وظيفة التحقق من كلمة السر الثانية
        function checkPass2() {
            const p2 = document.getElementById('pass2').value;
            if(p2 === '2222') {
                document.getElementById('page2').classList.remove('active');
                document.getElementById('page3').classList.add('active');
            } else {
                alert('ركز في الكود التاني!');
            }
        }

        // إنشاء قلوب عشوائية في الخلفية
        function createHeart() {
            const container = document.getElementById('heartContainer');
            const heart = document.createElement('div');
            heart.classList.add('heart');
            heart.innerHTML = '❤️';
            heart.style.left = Math.random() * 100 + 'vw';
            heart.style.animationDuration = Math.random() * 2 + 3 + 's';
            container.appendChild(heart);

            setTimeout(() => { heart.remove(); }, 5000);
        }

        setInterval(createHeart, 300);
    </script>
</body>
</html>
