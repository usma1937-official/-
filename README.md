[index.html](https://github.com/user-attachments/files/33282691/index.html)
<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>اتحاد العاصمة - USMA 1937</title>
    <style>
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: #0d0d0d;
            color: #ffffff;
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        header {
            width: 100%;
            padding: 20px 50px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            background-color: #1a1a1a;
            border-bottom: 3px solid #e60000;
            position: sticky;
            top: 0;
            z-index: 1000;
        }

        .logo-text {
            font-size: 24px;
            font-weight: bold;
            color: #e60000;
            letter-spacing: 2px;
            cursor: pointer;
        }

        nav a {
            color: #ffffff;
            text-decoration: none;
            margin-right: 20px;
            font-size: 16px;
            transition: 0.3s;
            cursor: pointer;
        }

        nav a:hover, nav a.active {
            color: #e60000;
        }

        .page-section {
            display: none;
            width: 100%;
            max-width: 1000px;
            padding: 40px 20px;
            animation: fadeIn 0.5s ease-in-out;
        }

        .page-section.active {
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .hero-container {
            text-align: center;
            padding: 40px 20px;
        }

        .hero-logo {
            width: 250px;
            max-width: 80%;
            height: auto;
            border-radius: 15px;
            box-shadow: 0 0 25px rgba(230, 0, 0, 0.4);
            margin-bottom: 30px;
            border: 2px solid #e60000;
            background-color: #fff;
            padding: 10px;
        }

        h1 {
            font-size: 36px;
            color: #ffffff;
            margin-bottom: 10px;
        }

        h1 span {
            color: #e60000;
        }

        p.subtitle {
            font-size: 20px;
            color: #cccccc;
            margin-bottom: 30px;
            font-weight: 300;
        }

        .btn-group {
            display: flex;
            gap: 15px;
            justify-content: center;
            flex-wrap: wrap;
        }

        .btn {
            padding: 12px 30px;
            font-size: 16px;
            font-weight: bold;
            border-radius: 25px;
            border: none;
            cursor: pointer;
            transition: all 0.3s ease;
            text-decoration: none;
        }

        .btn-primary {
            background-color: #e60000;
            color: #ffffff;
        }

        .btn-primary:hover {
            background-color: #b30000;
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(230, 0, 0, 0.4);
        }

        .btn-secondary {
            background-color: transparent;
            color: #ffffff;
            border: 2px solid #ffffff;
        }

        .btn-secondary:hover {
            background-color: #ffffff;
            color: #0d0d0d;
            transform: translateY(-3px);
        }

        /* تنسيقات الألقاب والمباريات */
        .section-header {
            text-align: center;
            margin-bottom: 40px;
        }

        .section-header h2 {
            font-size: 32px;
            color: #e60000;
            margin-bottom: 10px;
        }

        .titles-grid, .matches-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 20px;
            width: 100%;
            margin-bottom: 30px;
        }

        .title-card, .match-card {
            background-color: #161616;
            border: 1px solid #333;
            border-right: 4px solid #e60000;
            border-radius: 10px;
            padding: 20px;
            text-align: right;
            transition: transform 0.3s, box-shadow 0.3s;
        }

        .title-card:hover, .match-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 5px 20px rgba(230, 0, 0, 0.2);
            border-color: #e60000;
        }

        .title-card h3, .match-card h3 {
            font-size: 20px;
            color: #ffffff;
            margin-bottom: 8px;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .title-card h3 span, .match-card .badge {
            background-color: #e60000;
            color: #fff;
            font-size: 13px;
            padding: 3px 10px;
            border-radius: 12px;
        }

        .match-teams {
            font-size: 18px;
            font-weight: bold;
            color: #ffffff;
            margin: 10px 0;
            display: flex;
            justify-content: space-between;
            align-items: center;
            border-bottom: 1px solid #2a2a2a;
            padding-bottom: 10px;
        }

        .match-info {
            color: #aaaaaa;
            font-size: 14px;
            line-height: 1.6;
        }

        footer {
            margin-top: auto;
            padding: 20px;
            text-align: center;
            color: #666;
            font-size: 14px;
            width: 100%;
            border-top: 1px solid #222;
        }

        @media(max-width: 768px) {
            header {
                padding: 15px 20px;
                flex-direction: column;
                gap: 10px;
            }
            nav {
                display: flex;
                gap: 15px;
                flex-wrap: wrap;
                justify-content: center;
            }
            nav a {
                margin-right: 0;
            }
        }
    </style>
</head>
<body>

    <header>
        <div class="logo-text" onclick="showPage('home')">USMA 1937</div>
        <nav>
            <a href="#" onclick="showPage('home')" id="nav-home" class="active">الرئيسية</a>
            <a href="#" onclick="showPage('titles')" id="nav-titles">ألقاب النادي</a>
            <a href="#" onclick="showPage('matches')" id="nav-matches">جدول المباريات</a>
            <a href="https://instagram.com/jalil_jalil10.1" target="_blank">تواصل معنا</a>
        </nav>
    </header>

    <!-- الصفحة الرئيسية -->
    <main id="home" class="page-section active">
        <div class="hero-container">
            <img src="usma.jpg" alt="شعار اتحاد العاصمة USMA 1937" class="hero-logo">
            
            <h1>مرحباً بكم في موقع <span>اتحاد العاصمة</span></h1>
            <p class="subtitle">Les Rois d'Alger - ملوك العاصمة منذ 1937</p>

            <div class="btn-group">
                <button class="btn btn-primary" onclick="showPage('titles')">استكشف النادي</button>
                <button class="btn btn-primary" onclick="showPage('matches')">جدول المباريات</button>
                <a href="https://instagram.com/jalil_jalil10.1" target="_blank" class="btn btn-secondary">تواصل معي</a>
            </div>
        </div>
    </main>

    <!-- واجهة ألقاب النادي -->
    <main id="titles" class="page-section">
        <div class="section-header">
            <h2>خزانة ألقاب اتحاد العاصمة</h2>
            <p style="color: #ccc;">سجل حافل بالبطولات والإنجازات التاريخية لملوك العاصمة</p>
        </div>

        <div class="titles-grid">
            <div class="title-card">
                <h3>كأس الجزائر <span>10 ألقاب</span></h3>
                <p class="match-info">أعوام: 1981، 1988، 1997، 1999، 2001، 2003، 2004، 2013، 2025، 2026.</p>
            </div>

            <div class="title-card">
                <h3>الرابطة المحترفة الأولى <span>8 ألقاب</span></h3>
                <p class="match-info">أعوام: 1963، 1996، 2002، 2003، 2005، 2014، 2016، 2019.</p>
            </div>

            <div class="title-card">
                <h3>كأس الكونفيدرالية الإفريقية <span>2 ألقاب</span></h3>
                <p class="match-info">مواسم: 2022–23 و 2025–26.</p>
            </div>

            <div class="title-card">
                <h3>كأس السوبر الإفريقي <span>لقب واحد</span></h3>
                <p class="match-info">عام 2023 (أمام الأهلي المصري).</p>
            </div>

            <div class="title-card">
                <h3>كأس السوبر الجزائري <span>2 ألقاب</span></h3>
                <p class="match-info">أعوام: 2013، 2016.</p>
            </div>

            <div class="title-card">
                <h3>كأس العرب للأندية الأبطال <span>لقب واحد</span></h3>
                <p class="match-info">عام 2013.</p>
            </div>
        </div>

        <button class="btn btn-secondary" onclick="showPage('home')" style="margin-top: 20px;">العودة للرئيسية</button>
    </main>

    <!-- واجهة جدول المباريات القادمة -->
    <main id="matches" class="page-section">
        <div class="section-header">
            <h2>جدول المباريات القادمة</h2>
            <p style="color: #ccc;">مواعيد مواجهات سوسارة ورجال اتحاد العاصمة القادمة</p>
        </div>

        <div class="matches-grid">
            <div class="match-card">
                <h3>المباراة القادمة <span class="badge">الرابطة الأولى</span></h3>
                <div class="match-teams">
                    <span>اتحاد العاصمة 🔴⚫</span>
                    <span>VS</span>
                    <span>شبيبة الساورة 🟡</span>
                </div>
                <p class="match-info">📅 **التاريخ:** الثلاثاء 13 أكتوبر 2026</p>
                <p class="match-info">⏰ **التوقيت:** 20:00 (بتوقيت الجزائر)</p>
                <p class="match-info">Stadium **الملعب:** ملعب عمر حمادي (بولوغين)</p>
            </div>

            <div class="match-card">
                <h3>كأس الكونفيدرالية <span class="badge">الدور التمهيدي</span></h3>
                <div class="match-teams">
                    <span>بانثرز FC ⚽</span>
                    <span>VS</span>
                    <span>اتحاد العاصمة 🔴⚫</span>
                </div>
                <p class="match-info">📅 **التاريخ:** الأحد 18 أكتوبر 2026</p>
                <p class="match-info">⏰ **التوقيت:** 16:00 (بتوقيت الجزائر)</p>
                <p class="match-info">Stadium **المسابقة:** ذهاب الدور الثاني - CAF</p>
            </div>

            <div class="match-card">
                <h3>الرابطة المحترفة <span class="badge">الجولة 9</span></h3>
                <div class="match-teams">
                    <span>اتحاد العاصمة 🔴⚫</span>
                    <span>VS</span>
                    <span>مولودية وهران 🔴⚪</span>
                </div>
                <p class="match-info">📅 **التاريخ:** الخميس 22 أكتوبر 2026</p>
                <p class="match-info">⏰ **التوقيت:** 15:00 (بتوقيت الجزائر)</p>
                <p class="match-info">Stadium **الملعب:** ملعب عمر حمادي</p>
            </div>

            <div class="match-card">
                <h3>إياد CAF <span class="badge">الكونفيدرالية</span></h3>
                <div class="match-teams">
                    <span>اتحاد العاصمة 🔴⚫</span>
                    <span>VS</span>
                    <span>بانثرز FC ⚽</span>
                </div>
                <p class="match-info">📅 **التاريخ:** الأحد 25 أكتوبر 2026</p>
                <p class="match-info">⏰ **التوقيت:** 20:00 (بتوقيت الجزائر)</p>
                <p class="match-info">Stadium **المقابلة:** إياب الدور التمهيدي القاري</p>
            </div>
        </div>

        <button class="btn btn-secondary" onclick="showPage('home')" style="margin-top: 20px;">العودة للرئيسية</button>
    </main>

    <footer>
        تصميم ومطوَّر بواسطة <strong>جليل</strong> | جميع الحقوق محفوظة © 2026
    </footer>

    <script>
        function showPage(pageId) {
            document.querySelectorAll('.page-section').forEach(section => {
                section.classList.remove('active');
            });

            document.querySelectorAll('nav a').forEach(link => {
                link.classList.remove('active');
            });

            document.getElementById(pageId).classList.add('active');

            if (pageId === 'home') {
                document.getElementById('nav-home').classList.add('active');
            } else if (pageId === 'titles') {
                document.getElementById('nav-titles').classList.add('active');
            } else if (pageId === 'matches') {
                document.getElementById('nav-matches').classList.add('active');
            }

            window.scrollTo({ top: 0, behavior: 'smooth' });
        }
    </script>

</body>
</html>
