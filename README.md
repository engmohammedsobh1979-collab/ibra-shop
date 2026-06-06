<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>IBRA SUPER STORE | 100 منتج حقيقي</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link href="https://fonts.googleapis.com/css2?family=Cairo:wght=400;600;700;900&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * { box-sizing: border-box; margin: 0; padding: 0; }
        body { font-family: 'Cairo', sans-serif; background: #f5f5f5; color: #1a1a1a; }

        /* Splash */
        #splash { position: fixed; inset: 0; background: #0f0f0f; z-index: 999; display: flex; flex-direction: column; align-items: center; justify-content: center; gap: 16px; transition: opacity 0.6s ease; }
        #splash h1 { font-size: 2.5rem; font-weight: 900; color: #fff; }
        #splash h1 span { color: #2563eb; }
        #splash p { color: #888; font-size: 0.9rem; }
        .splash-bar { width: 220px; height: 4px; background: #222; border-radius: 99px; overflow: hidden; }
        .splash-fill { height: 100%; background: #2563eb; border-radius: 99px; animation: fill 2s ease forwards; }
        @keyframes fill { from { width: 0% } to { width: 100% } }

        /* Header */
        header { background: #fff; border-bottom: 1px solid #e5e7eb; position: sticky; top: 0; z-index: 100; }
        .header-inner { max-width: 1300px; margin: auto; padding: 14px 24px; display: flex; align-items: center; gap: 20px; }
        .logo { font-size: 1.5rem; font-weight: 900; color: #0f0f0f; text-decoration: none; white-space: nowrap; }
        .logo span { color: #2563eb; }
        .search-wrap { flex: 1; position: relative; }
        .search-wrap input { width: 100%; border: 1.5px solid #e5e7eb; border-radius: 12px; padding: 10px 16px 10px 44px; font-family: 'Cairo', sans-serif; font-size: 0.85rem; background: #f9fafb; outline: none; transition: all 0.2s; }
        .search-wrap input:focus { border-color: #2563eb; background: #fff; box-shadow: 0 0 0 3px #2563eb20; }
        .search-wrap i { position: absolute; left: 14px; top: 50%; transform: translateY(-50%); color: #9ca3af; }
        .cart-btn { position: relative; background: none; border: none; cursor: pointer; font-size: 1.3rem; color: #374151; padding: 5px; }
        .cart-badge { position: absolute; top: -6px; left: -6px; background: #2563eb; color: #fff; font-size: 10px; font-weight: 700; width: 18px; height: 18px; border-radius: 50%; display: flex; align-items: center; justify-content: center; }
        
        /* زر تسجيل الدخول الجديد */
        .user-tag { background: #0f0f0f; color: #fff; font-size: 0.8rem; font-weight: 700; padding: 8px 18px; border-radius: 10px; white-space: nowrap; cursor: pointer; border: none; display: flex; align-items: center; gap: 8px; transition: background 0.2s; }
        .user-tag:hover { background: #2563eb; }

        /* Categories */
        .cats-bar { background: #fff; border-bottom: 1px solid #e5e7eb; position: sticky; top: 65px; z-index: 90; overflow-x: auto; scrollbar-width: none; }
        .cats-bar::-webkit-scrollbar { display: none; }
        .cats-inner { max-width: 1300px; margin: auto; padding: 10px 24px; display: flex; gap: 8px; }
        .cat-btn { white-space: nowrap; border: none; cursor: pointer; font-family: 'Cairo', sans-serif; font-size: 0.78rem; font-weight: 600; padding: 7px 16px; border-radius: 10px; transition: all 0.2s; background: #f3f4f6; color: #374151; }
        .cat-btn:hover { background: #e5e7eb; }
        .cat-btn.active { background: #2563eb; color: #fff; }

        /* Main */
        main { max-width: 1300px; margin: auto; padding: 28px 24px; }
        .section-header { display: flex; justify-content: space-between; align-items: center; margin-bottom: 20px; }
        .section-header h2 { font-size: 1.2rem; font-weight: 900; }
        .count-badge { background: #eff6ff; color: #2563eb; font-size: 0.75rem; font-weight: 700; padding: 4px 12px; border-radius: 99px; }

        /* Grid */
        .grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(260px, 1fr)); gap: 20px; }

        /* Card */
        .card { background: #fff; border-radius: 16px; overflow: hidden; border: 1px solid #e5e7eb; transition: all 0.25s; position: relative; display: flex; flex-direction: column; }
        .card:hover { transform: translateY(-4px); box-shadow: 0 12px 30px rgba(0,0,0,0.08); }
        .card-img { height: 200px; overflow: hidden; background: #f9fafb; display: flex; align-items: center; justify-content: center; }
        .card-img img { width: 100%; height: 100%; object-fit: cover; transition: transform 0.3s; }
        .card:hover .card-img img { transform: scale(1.04); }
        .discount-badge { position: absolute; top: 10px; right: 10px; background: #ef4444; color: #fff; font-size: 11px; font-weight: 700; padding: 3px 8px; border-radius: 6px; z-index: 5; }
        .card-body { padding: 14px; flex: 1; display: flex; flex-direction: column; gap: 6px; }
        .card-cat { font-size: 0.7rem; color: #9ca3af; font-weight: 600; text-transform: uppercase; }
        .card-name { font-size: 0.9rem; font-weight: 700; color: #111; line-height: 1.4; min-height: 40px; display: -webkit-box; -webkit-line-clamp: 2; -webkit-box-orient: vertical; overflow: hidden; }
        .card-desc { font-size: 0.75rem; color: #6b7280; line-height: 1.5; display: -webkit-box; -webkit-line-clamp: 2; -webkit-box-orient: vertical; overflow: hidden; }
        .card-footer { display: flex; align-items: center; justify-content: space-between; margin-top: auto; padding-top: 10px; }
        .prices { display: flex; flex-direction: column; }
        .old-price { font-size: 0.75rem; color: #9ca3af; text-decoration: line-through; }
        .cur-price { font-size: 1.1rem; font-weight: 900; color: #0f0f0f; }
        .cur-price small { font-size: 0.7rem; font-weight: 600; color: #6b7280; }
        .add-btn { background: #fff; border: 1.5px solid #e5e7eb; color: #374151; font-family: 'Cairo', sans-serif; font-size: 0.75rem; font-weight: 700; padding: 8px 14px; border-radius: 10px; cursor: pointer; display: flex; align-items: center; gap: 6px; transition: all 0.2s; }
        .add-btn:hover { background: #2563eb; border-color: #2563eb; color: #fff; }
        .add-btn.added { background: #16a34a; border-color: #16a34a; color: #fff; }

        /* Rating */
        .rating { display: flex; align-items: center; gap: 4px; font-size: 0.72rem; color: #f59e0b; }
        .rating span { color: #6b7280; }

        /* Empty Search State */
        .empty { grid-column: 1/-1; text-align: center; padding: 60px 20px; color: #9ca3af; }
        .empty i { font-size: 3rem; margin-bottom: 12px; }

        /* Load more */
        #load-more { text-align: center; padding: 32px; color: #9ca3af; font-size: 0.85rem; display: flex; align-items: center; justify-content: center; gap: 8px; }

        /* Cart Dropdown */
        .cart-dropdown { position: absolute; top: 70px; left: 20px; width: 340px; background: #fff; border: 1px solid #e5e7eb; border-radius: 16px; box-shadow: 0 10px 25px rgba(0,0,0,0.1); display: none; flex-direction: column; max-height: 450px; z-index: 200; overflow: hidden; }
        .cart-dropdown.open { display: flex; }
        .cart-drop-header { padding: 15px; border-bottom: 1px solid #e5e7eb; display: flex; justify-content: space-between; align-items: center; font-weight: 700; }
        .cart-drop-items { padding: 10px; overflow-y: auto; flex: 1; }
        .cart-drop-item { display: flex; justify-content: space-between; align-items: center; padding: 8px 5px; border-bottom: 1px dashed #f3f4f6; font-size: 0.85rem; }
        .cart-drop-item span { max-width: 180px; overflow: hidden; text-overflow: ellipsis; white-space: nowrap; }
        .remove-item-btn { background: none; border: none; color: #ef4444; cursor: pointer; font-size: 0.8rem; }
        .cart-drop-footer { padding: 15px; background: #fafafa; border-top: 1px solid #e5e7eb; }
        .cart-drop-total { display: flex; justify-content: space-between; font-weight: 700; margin-bottom: 12px; font-size: 1rem; }
        .checkout-btn { width: 100%; padding: 10px; background: #2563eb; color: #fff; border: none; border-radius: 10px; font-family: 'Cairo', sans-serif; font-weight: 700; cursor: pointer; transition: background 0.2s; }
        .checkout-btn:hover { background: #1d4ed8; }

        /* ==================== واجهة تسجيل الدخول الجديدة ==================== */
        .login-overlay {
            position: fixed;
            inset: 0;
            background: rgba(0, 0, 0, 0.6);
            backdrop-filter: blur(5px);
            z-index: 1000;
            display: none; /* مخفية افتراضياً */
            align-items: center;
            justify-content: center;
            padding: 20px;
        }
        .login-overlay.show { display: flex; }
        
        .login-modal {
            width: 100%;
            max-width: 420px;
            background: #ffffff url('https://img.pngtree.com/background/20210711/original/pngtree-geometric-polygon-blue-gradient-login-interface-background-material-picture-image_1090333.jpg') no-repeat center center;
            background-size: cover;
            border-radius: 24px;
            box-shadow: 0 20px 40px rgba(0,0,0,0.3);
            overflow: hidden;
            position: relative;
            animation: modalFade 0.3s ease-out;
        }
        @keyframes modalFade { from { transform: translateY(20px); opacity: 0; } to { transform: translateY(0); opacity: 1; } }

        .login-blur-box {
            background: rgba(255, 255, 255, 0.88);
            backdrop-filter: blur(3px);
            padding: 40px 30px;
            width: 100%;
            height: 100%;
        }
        .login-header { text-align: center; margin-bottom: 30px; }
        .login-header h3 { font-size: 1.6rem; font-weight: 900; color: #0f0f0f; }
        .login-header h3 span { color: #2563eb; }
        .login-header p { font-size: 0.85rem; color: #6b7280; margin-top: 5px; }
        
        .close-login { position: absolute; top: 15px; left: 20px; font-size: 1.3rem; color: #374151; cursor: pointer; transition: color 0.2s; border: none; background: none; }
        .close-login:hover { color: #ef4444; }

        .form-group { margin-bottom: 20px; position: relative; }
        .form-group i { position: absolute; right: 14px; top: 50%; transform: translateY(-50%); color: #9ca3af; }
        .form-group input { width: 100%; padding: 12px 44px 12px 16px; border: 1.5px solid #e5e7eb; border-radius: 12px; font-family: 'Cairo', sans-serif; font-size: 0.85rem; outline: none; transition: all 0.2s; background: #fff; }
        .form-group input:focus { border-color: #2563eb; box-shadow: 0 0 0 3px #2563eb20; }
        
        .login-submit { width: 100%; padding: 12px; background: #2563eb; color: #fff; border: none; border-radius: 12px; font-family: 'Cairo', sans-serif; font-weight: 700; font-size: 0.95rem; cursor: pointer; transition: background 0.2s; margin-top: 10px; }
        .login-submit:hover { background: #1d4ed8; }
        
        .login-footer { text-align: center; margin-top: 20px; font-size: 0.8rem; color: #4b5563; }
        .login-footer a { color: #2563eb; text-decoration: none; font-weight: 700; }

        @media (max-width: 640px) {
            .header-inner { flex-wrap: wrap; }
            .search-wrap { order: 3; flex-basis: 100%; }
            .grid { grid-template-columns: repeat(2, 1fr); gap: 12px; }
            .card-img { height: 150px; }
            .cart-dropdown { left: 10px; right: 10px; width: auto; top: 120px; }
        }
    </style>
</head>
<body>

<div id="splash">
    <h1>IBRA<span>.</span>STORE</h1>
    <p>جاري تحميل 100 منتج حقيقي...</p>
    <div class="splash-bar"><div class="splash-fill"></div></div>
</div>

<header>
    <div class="header-inner">
        <a href="#" class="logo">IBRA<span>.</span>STORE</a>
        <div class="search-wrap">
            <input type="text" id="search" oninput="filterProducts()" placeholder="ابحث عن أي منتج... (ايفون، نايكي، نيفيا...)">
            <i class="fas fa-search"></i>
        </div>
        <button class="cart-btn" id="cart-btn" onclick="toggleCartDropdown()"><i class="fas fa-shopping-basket"></i><span class="cart-badge" id="cart-count">0</span></button>
        
        <!-- تعديل الزر هنا ليقوم بفتح نافذة تسجيل الدخول عند الضغط عليه -->
        <button class="user-tag" onclick="openLoginModal()"><i class="fas fa-user-circle"></i> تسجيل الدخول</button>
    </div>
    
    <!-- نافذة السلة المنسدلة -->
    <div class="cart-dropdown" id="cartDropdown">
        <div class="cart-drop-header">
            <span>سلة المشتريات 🛒</span>
            <span style="color: #2563eb; cursor:pointer;" onclick="toggleCartDropdown()">✕</span>
        </div>
        <div class="cart-drop-items" id="cartDropItems">
            <p style="text-align:center; color:#9ca3af; padding: 20px; font-size:0.85rem;">السلة فارغة حالياً</p>
        </div>
        <div class="cart-drop-footer">
            <div class="cart-drop-total">
                <span>الإجمالي:</span>
                <span id="cartDropTotal">0 ج.م</span>
            </div>
            <button class="checkout-btn" onclick="checkoutAction()">إتمام الشراء والطلب الفوري</button>
        </div>
    </div>
</header>

<!-- ==================== الواجهة المنبثقة لتسجيل الدخول ==================== -->
<div class="login-overlay" id="loginOverlay" onclick="closeLoginModalOutside(event)">
    <div class="login-modal">
        <button class="close-login" onclick="closeLoginModal()">✕</button>
        <div class="login-blur-box">
            <div class="login-header">
                <h3>IBRA<span>.</span>STORE</h3>
                <p>مرحباً بك مجدداً، سجل دخولك الآن</p>
            </div>
            <form onsubmit="handleLoginSubmit(event)">
                <div class="form-group">
                    <input type="email" placeholder="البريد الإلكتروني أو اسم المستخدم" required>
                    <i class="fas fa-envelope"></i>
                </div>
                <div class="form-group">
                    <input type="password" placeholder="كلمة المرور" required>
                    <i class="fas fa-lock"></i>
                </div>
                <button type="submit" class="login-submit">تسجيل الدخول</button>
            </form>
            <div class="login-footer">
                ليس لديك حساب؟ <a href="#">أنشئ حساب جديد</a>
            </div>
        </div>
    </div>
</div>

<div class="cats-bar">
    <div class="cats-inner" id="cats-inner">
        <button class="cat-btn active" onclick="setCategory('all', this)">🏠 الكل</button>
        <button class="cat-btn" onclick="setCategory('care', this)">🧴 عناية وجمال</button>
        <button class="cat-btn" onclick="setCategory('fashion', this)">👕 أزياء وملابس</button>
        <button class="cat-btn" onclick="setCategory('electronics', this)">💻 إلكترونيات</button>
        <button class="cat-btn" onclick="setCategory('home', this)">🍳 منزل ومطبخ</button>
        <button class="cat-btn" onclick="setCategory('sports', this)">⚽ رياضة ولياقة</button>
        <button class="cat-btn" onclick="setCategory('books', this)">📚 كتب وتعليم</button>
        <button class="cat-btn" onclick="setCategory('toys', this)">🧸 ألعاب وأطفال</button>
        <button class="cat-btn" onclick="setCategory('food', this)">🍫 أغذية ومشروبات</button>
        <button class="cat-btn" onclick="setCategory('auto', this)">🚗 سيارات وإكسسوار</button>
        <button class="cat-btn" onclick="setCategory('office', this)">🖊️ مكتب وقرطاسية</button>
    </div>
</div>

<main>
    <div class="section-header">
        <h2>المنتجات المتاحة</h2>
        <span class="count-badge" id="count-badge">100 منتج</span>
    </div>
    <div class="grid" id="grid"></div>
    <div id="load-more" style="display:none"><i class="fas fa-spinner fa-spin" style="color:#2563eb"></i> جاري تحميل المزيد...</div>
</main>

<footer style="text-align:center;padding:24px;font-size:0.8rem;color:#9ca3af;border-top:1px solid #e5e7eb;background:#fff;margin-top:40px;">
    © 2026 متجر إبراهيم — 100 منتج حقيقي بأسعار واقعية
</footer>

<script>
// مصفوفة الـ 100 منتج الحقيقي مقسمة بالكامل على الـ 10 تصنيفات
const products = [
    // ===== عناية وجمال (care) =====
    { id:1, cat:'care', catLabel:'عناية وجمال', name:'كريم نيفيا الأزرق المرطب للجسم 400مل', desc:'تركيبة الكريم الشهيرة بالمكادميا ترطب البشرة لـ 48 ساعة متواصلة.', img:'https://images.unsplash.com/photo-1608248597481-496100c8c836?w=500&q=80', price:85, oldPrice:110, discount:23, rating:4.7, reviews:2341 },
    { id:2, cat:'care', catLabel:'عناية وجمال', name:'شامبو هيد آند شولدرز لتنظيف الشعر وإزالة القشرة 400مل', desc:'فورمولا طبية تزيل القشرة من أول استخدام وتترك الشعر منعشاً.', img:'https://images.unsplash.com/photo-1535585209827-a15fcdbc4c2d?w=500&q=80', price:65, oldPrice:80, discount:19, rating:4.5, reviews:1892 },
    { id:3, cat:'care', catLabel:'عناية وجمال', name:'سيروم فيتامين سي غارنييه لتفتيح البشرة 30مل', desc:'يقلل البقع الداكنة ويعطي بشرة مضيئة خلال أسبوعين فقط.', img:'https://images.unsplash.com/photo-1620916566398-39f1143ab7be?w=500&q=80', price:180, oldPrice:250, discount:28, rating:4.6, reviews:987 },
    { id:4, cat:'care', catLabel:'عناية وجمال', name:'غسول بشرة سيرافي بالسيراميد للبشرة الجافة 236مل', desc:'يحافظ على حاجز البشرة الطبيعي بدون صابون أو رغوة مضرة.', img:'https://images.unsplash.com/photo-1556228578-0d85b1a4a571?w=500&q=80', price:320, oldPrice:420, discount:24, rating:4.8, reviews:3201 },
    { id:5, cat:'care', catLabel:'عناية وجمال', name:'عطر رجالي شانيل بلو دو شانيل أو دي بارفان 100مل', desc:'مزيج خشبي معطر بنوتات الليمون والزنجبيل ثباته يتجاوز 12 ساعة.', img:'https://images.unsplash.com/photo-1541643600914-78b084683601?w=500&q=80', price:3200, oldPrice:3800, discount:16, rating:4.9, reviews:5671 },
    { id:6, cat:'care', catLabel:'عناية وجمال', name:'واقي شمس لاروش بوزيه أنتيهيليوس SPF50 50مل', desc:'حماية كاملة للبشرة الحساسة ضد UVA وUVB بدون زيوت.', img:'https://images.unsplash.com/photo-1598440947619-2c35fc9aa908?w=500&q=80', price:480, oldPrice:620, discount:23, rating:4.7, reviews:1543 },
    { id:7, cat:'care', catLabel:'عناية وجمال', name:'كريم مرطب نيفيا للوجه Q10 ضد التجاعيد 50مل', desc:'يقلل التجاعيد الدقيقة بنسبة 40% مع ترطيب يدوم 24 ساعة.', img:'https://images.unsplash.com/photo-1608248597481-496100c8c836?w=500&q=80', price:145, oldPrice:185, discount:22, rating:4.5, reviews:876 },
    { id:8, cat:'care', catLabel:'عناية وجمال', name:'مزيل عرق رجالي دوف 48 ساعة 150مل', desc:'يحمي من العرق والرائحة 48 ساعة ولطيف على البشرة الحساسة.', img:'https://images.unsplash.com/photo-1601049541289-9b1b7bbbfe19?w=500&q=80', price:55, oldPrice:70, discount:21, rating:4.4, reviews:2109 },
    { id:9, cat:'care', catLabel:'عناية وجمال', name:'قناع وجه الفحم الأسود بيور تشارككول 100مل', desc:'يشفط الدهون والشوائب من المسام العميقة ويقلصها بشكل واضح.', img:'https://images.unsplash.com/photo-1596755389378-c31d21fd1273?w=500&q=80', price:95, oldPrice:130, discount:27, rating:4.3, reviews:654 },
    { id:10, cat:'care', catLabel:'عناية وجمال', name:'بلسم شعر لوريال إكستراوردينيري أويل للشعر الجاف 200مل', desc:'يغذي ويصلح الشعر التالف بزيوت 6 نادرة من حول العالم.', img:'https://images.unsplash.com/photo-1535585209827-a15fcdbc4c2d?w=500&q=80', price:120, oldPrice:160, discount:25, rating:4.6, reviews:1230 },

    // ===== أزياء وملابس (fashion) =====
    { id:11, cat:'fashion', catLabel:'أزياء وملابس', name:'تيشيرت أديداس أورجينال كلاسيك قطن 100%', desc:'تصميم ثلاثي الشرائط الأيقوني مصنوع من القطن المصري الفاخر.', img:'https://images.unsplash.com/photo-1521572267360-ee0c2909d518?w=500&q=80', price:650, oldPrice:890, discount:27, rating:4.6, reviews:3421 },
    { id:12, cat:'fashion', catLabel:'أزياء وملابس', name:'بنطال جينز ليفايز 501 أصلي ضيق مريح', desc:'الجينز الكلاسيكي الأشهر في العالم بخياطة قوية تتحمل السنين.', img:'https://images.unsplash.com/photo-1542272604-787c3835535d?w=500&q=80', price:1450, oldPrice:1950, discount:26, rating:4.7, reviews:5432 },
    { id:13, cat:'fashion', catLabel:'أزياء وملابس', name:'حذاء نايكي إير فورس 1 جلد أبيض', desc:'الأيقونة الخالدة من نايكي — راحة فائقة وتصميم يناسب كل إطلالة.', img:'https://images.unsplash.com/photo-1542291026-7eec264c27ff?w=500&q=80', price:2800, oldPrice:3500, discount:20, rating:4.8, reviews:8901 },
    { id:14, cat:'fashion', catLabel:'أزياء وملابس', name:'نظارة شمسية ريبان أفياتور كلاسيك UV400', desc:'عدسات مستقطبة ذهبية مع إطار معدني خفيف — الكلاسيكي الأصيل.', img:'https://images.unsplash.com/photo-1511499767150-a48a237f0083?w=500&q=80', price:3500, oldPrice:4500, discount:22, rating:4.9, reviews:6231 },
    { id:15, cat:'fashion', catLabel:'أزياء وملابس', name:'ساعة كاسيو جي-شوك سوداء مقاومة للصدمات', desc:'الساعة الأقوى في العالم — مقاومة للصدمات والماء حتى 200 متر.', img:'https://images.unsplash.com/photo-1524592094714-0f0654e20314?w=500&q=80', price:1800, oldPrice:2400, discount:25, rating:4.7, reviews:4321 },
    { id:16, cat:'fashion', catLabel:'أزياء وملابس', name:'حقيبة ظهر سامسونايت جلد بني 30 لتر', desc:'مصنوعة من جلد البوليستر المقاوم للماء مع حجرة محمول مبطنة.', img:'https://images.unsplash.com/photo-1553062407-98eeb64c6a62?w=500&q=80', price:2200, oldPrice:3000, discount:27, rating:4.5, reviews:1876 },
    { id:17, cat:'fashion', catLabel:'أزياء وملابس', name:'جاكيت جلدي أسود رجالي كلاسيك', desc:'جلد صناعي عالي الجودة بطانة دافئة مناسب لكل المناسبات.', img:'https://images.unsplash.com/photo-1576995853123-5a10305d93c0?w=500&q=80', price:1900, oldPrice:2600, discount:27, rating:4.4, reviews:987 },
    { id:18, cat:'fashion', catLabel:'أزياء وملابس', name:'قميص رجالي أكسفورد قطن أزرق فاتح', desc:'نسيج أكسفورد مريح مناسب للعمل والمناسبات الرسمية وشبه الرسمية.', img:'https://images.unsplash.com/photo-1521572267360-ee0c2909d518?w=500&q=80', price:580, oldPrice:780, discount:26, rating:4.5, reviews:1432 },
    { id:19, cat:'fashion', catLabel:'أزياء وملابس', name:'حذاء رياضي نيو بالانس 574 رمادي', desc:'نعل EVA مريح وتصميم عصري كلاسيكي يناسب المشي اليومي.', img:'https://images.unsplash.com/photo-1542291026-7eec264c27ff?w=500&q=80', price:2100, oldPrice:2800, discount:25, rating:4.6, reviews:3211 },
    { id:20, cat:'fashion', catLabel:'أزياء وملابس', name:'تيشيرت بولو لاكوست قطن قصة مريحة', desc:'قطن بيكيه فاخر مع تطريز التمساح الأيقوني — أناقة بلمسة رياضية.', img:'https://images.unsplash.com/photo-1521572267360-ee0c2909d518?w=500&q=80', price:1200, oldPrice:1600, discount:25, rating:4.7, reviews:2543 },

    // ===== إلكترونيات (electronics) =====
    { id:21, cat:'electronics', catLabel:'إلكترونيات', name:'هاتف سامسونج جالاكسي S24 Ultra 256GB', desc:'شاشة Dynamic AMOLED 6.8 بوصة وكاميرا 200MP وقلم S Pen مدمج.', img:'https://images.unsplash.com/photo-1510557880182-3d4d3cba35a5?w=500&q=80', price:38000, oldPrice:45000, discount:16, rating:4.8, reviews:7654 },
    { id:22, cat:'electronics', catLabel:'إلكترونيات', name:'سماعات سوني WH-1000XM5 لاسلكية إلغاء ضوضاء', desc:'أفضل إلغاء ضوضاء في فئتها مع بطارية 30 ساعة وجودة صوت استثنائية.', img:'https://images.unsplash.com/photo-1505740420928-5e560c06d30e?w=500&q=80', price:13500, oldPrice:17000, discount:21, rating:4.9, reviews:12431 },
    { id:23, cat:'electronics', catLabel:'إلكترونيات', name:'لابتوب ديل XPS 15 معالج Intel i7 الجيل 13', desc:'شاشة OLED 4K 15.6 بوصة وكارت RTX 4060 مناسب للمصممين.', img:'https://images.unsplash.com/photo-1517336714731-489689fd1ca8?w=500&q=80', price:42000, oldPrice:52000, discount:19, rating:4.7, reviews:3214 },
    { id:24, cat:'electronics', catLabel:'إلكترونيات', name:'ماوس لوجيتك MX Master 3S لاسلكي صامت', desc:'دقة 8000 DPI وعجلة تمرير مغناطيسية — الأفضل للإنتاجية والتصميم.', img:'https://images.unsplash.com/photo-1615663245857-ac93bb7c39e7?w=500&q=80', price:380, oldPrice:480, discount:21, rating:4.8, reviews:5432 },
    { id:25, cat:'electronics', catLabel:'إلكترونيات', name:'باور بانك أنكر 737 140W شحن فائق 24000mAh', desc:'يشحن 3 أجهزة في وقت واحد بسرعة خرافية وسعة تكفي أسبوع.', img:'https://images.unsplash.com/photo-1609592424083-0975cb450c38?w=500&q=80', price:2100, oldPrice:2800, discount:25, rating:4.7, reviews:6521 },
    { id:26, cat:'electronics', catLabel:'إلكترونيات', name:'تابلت أبل آيباد برو M2 11 بوصة WiFi 256GB', desc:'معالج M2 قوي بشاشة Liquid Retina ProMotion 120Hz رائعة.', img:'https://images.unsplash.com/photo-1510557880182-3d4d3cba35a5?w=500&q=80', price:35000, oldPrice:42000, discount:17, rating:4.9, reviews:8901 },
    { id:27, cat:'electronics', catLabel:'إلكترونيات', name:'كيبورد ميكانيكي كيتشرون K8 Pro لاسلكي RGB', desc:'مفاتيح هوت-سووب قابلة للتغيير وبطارية 4000mAh ومتوافق مع Mac وWindows.', img:'https://images.unsplash.com/photo-1587829741301-dc798b83add3?w=500&q=80', price:4200, oldPrice:5500, discount:24, rating:4.6, reviews:2341 },
    { id:28, cat:'electronics', catLabel:'إلكترونيات', name:'شاشة LG UltraGear 27 بوصة 4K 144Hz IPS', desc:'دقة 4K مع IPS Nano لأفضل ألوان وزاوية مشاهدة — مثالية للألعاب والتصميم.', img:'https://images.unsplash.com/photo-1527443224154-c4a3942d3acf?w=500&q=80', price:16500, oldPrice:21000, discount:21, rating:4.7, reviews:1987 },
    { id:29, cat:'electronics', catLabel:'إلكترونيات', name:'سماعات أبل إيربودز برو الجيل الثاني', desc:'إلغاء ضوضاء نشط و Transparency Mode وجودة H2 الصوتية الخارقة.', img:'https://images.unsplash.com/photo-1505740420928-5e560c06d30e?w=500&q=80', price:10500, oldPrice:13000, discount:19, rating:4.8, reviews:21543 },
    { id:30, cat:'electronics', catLabel:'إلكترونيات', name:'روتر واي-فاي 6 ASUS RT-AX88U Pro ثنائي النطاق', desc:'سرعة تصل إلى 6000Mbps ويغطي مساحة 2500 قدم مربع بدون انقطاع.', img:'https://images.unsplash.com/photo-1527443224154-c4a3942d3acf?w=500&q=80', price:5800, oldPrice:7500, discount:23, rating:4.6, reviews:3210 },

    // ===== منزل ومطبخ (home) =====
    { id:31, cat:'home', catLabel:'منزل ومطبخ', name:'ماكينة قهوة ديلونجي ديديكا EC685 ستيل', desc:'تضخ 15 بار وتحضر إسبريسو احترافي في 40 ثانية فقط.', img:'https://images.unsplash.com/photo-1517256064527-09c53b2d0c6b?w=500&q=80', price:7900, oldPrice:10500, discount:25, rating:4.7, reviews:4321 },
    { id:32, cat:'home', catLabel:'منزل ومطبخ', name:'قلاية هوائية فيليبس Air Fryer XXL 7.3 لتر', desc:'تقلي بدون زيت وتوفر 90% من الدهون — سعة عائلية ضخمة.', img:'https://images.unsplash.com/photo-1621972750749-0fbb1abb7736?w=500&q=80', price:4500, oldPrice:6200, discount:27, rating:4.8, reviews:7654 },
    { id:33, cat:'home', catLabel:'منزل ومطبخ', name:'طقم مقالي تيفال إنجينيو نيو 10 قطع', desc:'طلاء تيتانيوم غير لاصق يتحمل 5 أضعاف معدل التآكل العادي.', img:'https://images.unsplash.com/photo-1584269600464-37b1b58a9fe7?w=500&q=80', price:3200, oldPrice:4500, discount:29, rating:4.6, reviews:2109 },
    { id:34, cat:'home', catLabel:'منزل ومطبخ', name:'خلاط مولينكس بليندفورس برو 1200 واط', desc:'يسحق الثلج والخضار الصلبة في ثوانٍ بشفرات ستانلس ستيل.', img:'https://images.unsplash.com/photo-1578643463396-0997cb5328c1?w=500&q=80', price:1850, oldPrice:2500, discount:26, rating:4.5, reviews:1654 },
    { id:35, cat:'home', catLabel:'منزل ومطبخ', name:'مكنسة دايسون V15 ديتكت كورد-فري', desc:'تكشف الغبار بليزر وتمتص حتى ذرات PM0.3 بمحرك ديجيتال قوي.', img:'https://images.unsplash.com/photo-1584622781564-1d987f7333c1?w=500&q=80', price:12000, oldPrice:16000, discount:25, rating:4.8, reviews:5432 },
    { id:36, cat:'home', catLabel:'منزل ومطبخ', name:'غلاية مياه زجاجية روسل هوبز 1.7 لتر LED', desc:'إضاءة LED زرقاء ساحرة وغليان في 3 دقائق وفصل تلقائي آمن.', img:'https://images.unsplash.com/photo-1594212699903-ec8a3eca50f5?w=500&q=80', price:680, oldPrice:950, discount:29, rating:4.5, reviews:3210 },
    { id:37, cat:'home', catLabel:'منزل ومطبخ', name:'طقم سكاكين وستنهوف كلاسيك ألماني 7 قطع', desc:'فولاذ ألماني مطروق يدوياً بحدة لا تتلاشى وتوازن مثالي في اليد.', img:'https://images.unsplash.com/photo-1593614242191-23e944567142?w=500&q=80', price:2800, oldPrice:3800, discount:26, rating:4.9, reviews:1987 },
    { id:38, cat:'home', catLabel:'منزل ومطبخ', name:'فرن كهربائي أريستون FT 9 وظائف 71 لتر', desc:'تحكم دقيق بالحرارة مع شواء علوي وسفلي وتسوية مثالية.', img:'https://images.unsplash.com/photo-1556909114-f6e7ad7d3136?w=500&q=80', price:6500, oldPrice:9000, discount:28, rating:4.6, reviews:876 },
    { id:39, cat:'home', catLabel:'منزل ومطبخ', name:'إبريق شاي كاسل تريكس ستانلس ستيل 1.5 لتر', desc:'جسم فولاذي لامع وغطاء يمنع التسرب مع مقبض مريح للحمل.', img:'https://images.unsplash.com/photo-1594212699903-ec8a3eca50f5?w=500&q=80', price:380, oldPrice:520, discount:27, rating:4.3, reviews:1230 },
    { id:40, cat:'home', catLabel:'منزل ومطبخ', name:'مكواة بخار فيليبس باورستيم 3000W', desc:'بخار 210 جرام/دقيقة تزيل أصعب تجاعيد الملابس بضغطة واحدة.', img:'https://images.unsplash.com/photo-1556909114-f6e7ad7d3136?w=500&q=80', price:1200, oldPrice:1650, discount:27, rating:4.6, reviews:2341 },

    // ===== رياضة ولياقة (sports) =====
    { id:41, cat:'sports', catLabel:'رياضة ولياقة', name:'دراجة رياضية داخلية بروفورم Tour de France CBC', desc:'مقاومة ماجنيتيك مع شاشة رقمية وتوافق مع iFit للتدريب التفاعلي.', img:'https://images.unsplash.com/photo-1571019613454-1cb2f99b2d8b?w=500&q=80', price:14500, oldPrice:19000, discount:24, rating:4.6, reviews:876 },
    { id:42, cat:'sports', catLabel:'رياضة ولياقة', name:'حذاء جري أسيكس جيل-نيمبوس 25 رجالي', desc:'نعل FlyteFoam خفيف ومرن يمتص الصدمات ويحمي المفاصل في المسافات الطويلة.', img:'https://images.unsplash.com/photo-1542291026-7eec264c27ff?w=500&q=80', price:3200, oldPrice:4200, discount:24, rating:4.8, reviews:3421 },
    { id:43, cat:'sports', catLabel:'رياضة ولياقة', name:'حزام أوزان قابل للتعديل 20 كجم بوميا', desc:'بدّل الأوزان في 15 ثانية — يستبدل 15 دمبل مختلفة بأداة واحدة.', img:'https://images.unsplash.com/photo-1571019613454-1cb2f99b2d8b?w=500&q=80', price:3800, oldPrice:5200, discount:27, rating:4.7, reviews:5432 },
    { id:44, cat:'sports', catLabel:'رياضة ولياقة', name:'بروتين مصل حليب أون جولد ستاندرد 2.27 كجم', desc:'24 جرام بروتين لكل وجبة مع 5.5 جرام BCAA طبيعي لبناء العضلات.', img:'https://images.unsplash.com/photo-1593095948071-474c5cc2989d?w=500&q=80', price:2800, oldPrice:3600, discount:22, rating:4.8, reviews:21543 },
    { id:45, cat:'sports', catLabel:'رياضة ولياقة', name:'ساعة رياضية جارمن فوريرانر 255 GPS', desc:'تتبع GPS دقيق وقياس HRV ونبض القلب وخطة تدريب ذكية.', img:'https://images.unsplash.com/photo-1523275335684-37898b6baf30?w=500&q=80', price:8500, oldPrice:11000, discount:23, rating:4.7, reviews:4321 },
    { id:46, cat:'sports', catLabel:'رياضة ولياقة', name:'كرة قدم أديداس كونكست الرسمية الحجم 5', desc:'جلد ميكروتكستشر وبلادر لاتكس يضمن ارتداداً متساوياً في الملاعب.', img:'https://images.unsplash.com/photo-1571019613454-1cb2f99b2d8b?w=500&q=80', price:480, oldPrice:650, discount:26, rating:4.5, reviews:1987 },
    { id:47, cat:'sports', catLabel:'رياضة ولياقة', name:'بساط يوجا بيليتيس غير قابل للانزلاق 6مم', desc:'مطاط طبيعي 100% بسطح ميكروفايبر يمتص العرق — مثالي لليوجا والبيلاتس.', img:'https://images.unsplash.com/photo-1571019613454-1cb2f99b2d8b?w=500&q=80', price:850, oldPrice:1200, discount:29, rating:4.6, reviews:3210 },
    { id:48, cat:'sports', catLabel:'رياضة ولياقة', name:'حبل تخطي تانيتا الرقمي بعداد دقيق', desc:'يحسب السرعة والسعرات والقفزات ويعرضها على شاشة LCD واضحة.', img:'https://images.unsplash.com/photo-1593095948071-474c5cc2989d?w=500&q=80', price:320, oldPrice:450, discount:29, rating:4.3, reviews:987 },
    { id:49, cat:'sports', catLabel:'رياضة ولياقة', name:'خوذة دراجة هوائية جيانت بدون تهوية انسيابية', desc:'هيكل بولي كربونات خفيف مع 28 فتحة تهوية ونظام تعديل سريع.', img:'https://images.unsplash.com/photo-1571019613454-1cb2f99b2d8b?w=500&q=80', price:120, oldPrice:170, discount:29, rating:4.5, reviews:654 },
    { id:50, cat:'sports', catLabel:'رياضة ولياقة', name:'قفازات ملاكمة إيفرلاست برو ستايل جلد 12oz', desc:'جلد شامواه ناعم وحشو إيفرفريش ضد الروائح — الخيار الأول للمحترفين.', img:'https://images.unsplash.com/photo-1593095948071-474c5cc2989d?w=500&q=80', price:680, oldPrice:950, discount:28, rating:4.6, reviews:1230 },

    // ===== كتب وتعليم (books) =====
    { id:51, cat:'books', catLabel:'كتب وتعليم', name:'كتاب "فن اللامبالاة" مارك مانسون عربي', desc:'الكتاب الأكثر مبيعاً حول قيم الحياة الحقيقية والسعادة الحقيقية.', img:'https://images.unsplash.com/photo-1512820790803-83ca734da794?w=500&q=80', price:95, oldPrice:130, discount:27, rating:4.6, reviews:12431 },
    { id:52, cat:'books', catLabel:'كتب وتعليم', name:'كتاب "العادات الذرية" جيمس كلير عربي', desc:'الكتاب الأشهر عالمياً عن بناء العادات الجيدة وكسر السيئة.', img:'https://images.unsplash.com/photo-1512820790803-83ca734da794?w=500&q=80', price:110, oldPrice:150, discount:27, rating:4.8, reviews:21654 },
    { id:53, cat:'books', catLabel:'كتب وتعليم', name:'قلم رصاص فابر-كاستل الفني الاحترافي طقم 12', desc:'درجات صلابة B1-B12 للرسم الاحترافي والرسوم التوضيحية.', img:'https://images.unsplash.com/photo-1481627834876-b7833e8f5570?w=500&q=80', price:145, oldPrice:200, discount:28, rating:4.7, reviews:3210 },
    { id:54, cat:'books', catLabel:'كتب وتعليم', name:'كورس أونلاين تصميم جرافيك Adobe CC كامل', desc:'200 ساعة فيديو تعليمي من الصفر للاحتراف مع شهادة معتمدة.', img:'https://images.unsplash.com/photo-1512820790803-83ca734da794?w=500&q=80', price:850, oldPrice:2500, discount:66, rating:4.7, reviews:7654 },
    { id:55, cat:'books', catLabel:'كتب وتعليم', name:'دفتر ملاحظات لوكوتف A5 100 ورقة جلد', desc:'ورق 90 جرام خالٍ من الحموضة لا تسرّب منه الأقلام — مثالي للرسم.', img:'https://images.unsplash.com/photo-1481627834876-b7833e8f5570?w=500&q=80', price:180, oldPrice:250, discount:28, rating:4.5, reviews:1987 },
    { id:56, cat:'books', catLabel:'كتب وتعليم', name:'كتاب "تفكير بطيء وسريع" دانيال كانيمان', desc:'أحد أهم الكتب في علم النفس المعرفي وكيف يتخذ البشر قراراتهم.', img:'https://images.unsplash.com/photo-1512820790803-83ca734da794?w=500&q=80', price:135, oldPrice:180, discount:25, rating:4.7, reviews:9876 },
    { id:57, cat:'books', catLabel:'كتب وتعليم', name:'لوحة رسم رقمية واكوم إنتوس برو M', desc:'8192 مستوى ضغط وإمالة 60 درجة — المعيار الاحترافي للمصممين الرقميين.', img:'https://images.unsplash.com/photo-1481627834876-b7833e8f5570?w=500&q=80', price:8500, oldPrice:12000, discount:29, rating:4.8, reviews:4321 },
    { id:58, cat:'books', catLabel:'كتب وتعليم', name:'كتاب "الأب الغني والأب الفقير" كيوساكي عربي', desc:'الكتاب الأكثر مبيعاً في الثروة المالية والاستثمار منذ 25 عاماً.', img:'https://images.unsplash.com/photo-1512820790803-83ca734da794?w=500&q=80', price:90, oldPrice:120, discount:25, rating:4.5, reviews:34521 },
    { id:59, cat:'books', catLabel:'كتب وتعليم', name:'علبة أقلام تلوين بريستاكولور المهنية 72 لون', desc:'ألوان ناعمة غنية قابلة للمزج — الخيار الأول لفناني الكوميكس.', img:'https://images.unsplash.com/photo-1481627834876-b7833e8f5570?w=500&q=80', price:1850, oldPrice:2600, discount:29, rating:4.8, reviews:5432 },
    { id:60, cat:'books', catLabel:'كتب وتعليم', name:'كتاب "القوة الآن" إيكهارت تول — الوعي الكامل', desc:'دليل روحي للعيش في اللحظة الحالية وإيجاد السلام الداخلي الحقيقي.', img:'https://images.unsplash.com/photo-1512820790803-83ca734da794?w=500&q=80', price:100, oldPrice:140, discount:29, rating:4.6, reviews:8765 },

    // ===== ألعاب وأطفال (toys) =====
    { id:61, cat:'toys', catLabel:'ألعاب وأطفال', name:'مجموعة ليجو تيكنيك سيارة بوغاتي شيرون 3599 قطعة', desc:'نموذج 1:8 بمحرك يشتغل ومقصورة حقيقية — للأطفال من 16 سنة فأكبر.', img:'https://images.unsplash.com/photo-1558618666-fcd25c85cd64?w=500&q=80', price:8500, oldPrice:11000, discount:23, rating:4.9, reviews:3421 },
    { id:62, cat:'toys', catLabel:'ألعاب وأطفال', name:'طائرة درون DJI Mini 4 Pro 4K مع ريموت', desc:'كاميرا 4K/60fps وبث HD على مسافة 20 كم مع تجنب العوائق الذكي.', img:'https://images.unsplash.com/photo-1558618666-fcd25c85cd64?w=500&q=80', price:18000, oldPrice:23000, discount:22, rating:4.8, reviews:5432 },
    { id:63, cat:'toys', catLabel:'ألعاب وأطفال', name:'لعبة مونوبولي ديلوكس عربي أسرة كاملة', desc:'نسخة فاخرة بقطع معدنية وبنك إلكتروني تناسب 2-8 لاعبين.', img:'https://images.unsplash.com/photo-1558618666-fcd25c85cd64?w=500&q=80', price:380, oldPrice:520, discount:27, rating:4.5, reviews:2109 },
    { id:64, cat:'toys', catLabel:'ألعاب وأطفال', name:'سكوتر كهربائي أطفال سيجواي نينيبوت E10 Pro', desc:'سرعة 16 كم/ساعة وبطارية 10 كم وتصميم أمان للأطفال من 6-12 سنة.', img:'https://images.unsplash.com/photo-1558618666-fcd25c85cd64?w=500&q=80', price:4500, oldPrice:6200, discount:27, rating:4.7, reviews:1654 },
    { id:65, cat:'toys', catLabel:'ألعاب وأطفال', name:'مجسم نظام شمسي تعليمي ثلاثي الأبعاد LED', desc:'9 كواكب بأحجام حقيقية نسبياً مع محرك يدور فعلاً — هدية تعليمية رائعة.', img:'https://images.unsplash.com/photo-1558618666-fcd25c85cd64?w=500&q=80', price:680, oldPrice:950, discount:28, rating:4.6, reviews:987 },
    { id:66, cat:'toys', catLabel:'ألعاب وأطفال', name:'طقم علوم تجارب كيمياء أطفال 50 تجربة', desc:'آمن 100% للأطفال من 8 سنوات مع مواد كافية لـ 50 تجربة علمية.', img:'https://images.unsplash.com/photo-1558618666-fcd25c85cd64?w=500&q=80', price:520, oldPrice:720, discount:28, rating:4.5, reviews:1432 },
    { id:67, cat:'toys', catLabel:'ألعاب وأطفال', name:'دمية باربي ستيلا فاشنيستا إضافة جديدة 2024', desc:'ملابس قابلة للخلع مع إكسسوارات واقعية تعكس التنوع والشمول.', img:'https://images.unsplash.com/photo-1558618666-fcd25c85cd64?w=500&q=80', price:280, oldPrice:380, discount:26, rating:4.4, reviews:3210 },
    { id:68, cat:'toys', catLabel:'ألعاب وأطفال', name:'بيانو أطفال كاسيو SA-76 44 مفتاح', desc:'100 لحن ونبضات مدمجة وحجم مناسب للأطفال من 3 سنوات فأكبر.', img:'https://images.unsplash.com/photo-1558618666-fcd25c85cd64?w=500&q=80', price:1200, oldPrice:1650, discount:27, rating:4.5, reviews:876 },
    { id:69, cat:'toys', catLabel:'ألعاب وأطفال', name:'روبو المساعد الذكي لوبو LOONA الذكي الاصطناعي', desc:'يتعرف على الوجوه ويستجيب للأصوات ويتحرك باستقلالية مع شاشة LCD.', img:'https://images.unsplash.com/photo-1558618666-fcd25c85cd64?w=500&q=80', price:5800, oldPrice:8000, discount:28, rating:4.3, reviews:432 },
    { id:70, cat:'toys', catLabel:'ألعاب وأطفال', name:'مجموعة فن وحرفيات دوه كريمية 25 لون', desc:'عجينة ناعمة آمنة لا تجف ولا تلوث الأيدي — للأطفال من 3 سنوات.', img:'https://images.unsplash.com/photo-1558618666-fcd25c85cd64?w=500&q=80', price:180, oldPrice:250, discount:28, rating:4.5, reviews:5432 },

    // ===== أغذية ومشروبات (food) =====
    { id:71, cat:'food', catLabel:'أغذية ومشروبات', name:'شوكولاتة ليندت ليندور كرات حليب 200 جرام', desc:'كرات شوكولاتة سويسرية بقلب كريمي يذوب في الفم — هدية مثالية.', img:'https://images.unsplash.com/photo-1548907040-4baa42d10919?w=500&q=80', price:185, oldPrice:250, discount:26, rating:4.8, reviews:8765 },
    { id:72, cat:'food', catLabel:'أغذية ومشروبات', name:'قهوة نيسكافيه جولد سريعة التحضير 200 جرام', desc:'مصنوعة من حبوب أرابيكا الفاخرة المحمصة بعناية لطعم غني ومميز.', img:'https://images.unsplash.com/photo-1514432324607-a09d9b4aefdd?w=500&q=80', price:210, oldPrice:270, discount:22, rating:4.7, reviews:5432 },
    { id:73, cat:'food', catLabel:'أغذية ومشروبات', name:'زيت زيتون بكر ممتاز وادي فود 1 لتر', desc:'معصور على البارد من أجود حبات الزيتون الطبيعي بنسبة حموضة أقل من 1%.', img:'https://images.unsplash.com/photo-1474979266404-7eaacbcd87c5?w=500&q=80', price:340, oldPrice:420, discount:19, rating:4.6, reviews:3210 },
    { id:74, cat:'food', catLabel:'أغذية ومشروبات', name:'عسل نحل طبيعي امتنان 1 كجم زهور برية', desc:'عسل نحل طبيعي نقي 100% غير مبستر غني بمضادات الأكسدة.', img:'https://images.unsplash.com/photo-1587049352846-4a222e784d38?w=500&q=80', price:240, oldPrice:310, discount:22, rating:4.8, reviews:1876 },
    { id:75, cat:'food', catLabel:'أغذية ومشروبات', name:'مكرونة باريلا إيطالي سباغيتي طقم 3 أكياس', desc:'مكرونة إيطالية أصلية مصنوعة من سميد القمح القاسي عالي الجودة.', img:'https://images.unsplash.com/photo-1551462147-ff29053bfc14?w=500&q=80', price:90, oldPrice:120, discount:25, rating:4.5, reviews:987 },
    { id:76, cat:'food', catLabel:'أغذية ومشروبات', name:'شاي أحمد تي لندن صندوق 100 فتلة ثقيل', desc:'مزيج كلاسيكي من شاي سيلان وأسام الفاخر لنكهة بريطانية قوية.', img:'https://images.unsplash.com/photo-1576092768241-dec231879fc3?w=500&q=80', price:80, oldPrice:110, discount:27, rating:4.6, reviews:2109 },
    { id:77, cat:'food', catLabel:'أغذية ومشروبات', name:'مكسرات مشكلة أبو عوف فاخرة 400 جرام', desc:'كاجو ولوز وفستق وبندق محمص طازج بدون زيوت مهدرجة.', img:'https://images.unsplash.com/photo-1536592233765-f52d59426280?w=500&q=80', price:295, oldPrice:380, discount:22, rating:4.7, reviews:1432 },
    { id:78, cat:'food', catLabel:'أغذية ومشروبات', name:'رقائق شوفان كاملة كويكر صندوق 500 جرام', desc:'مصدر غني بالألياف الطبيعية والطاقة المثالية لوجبة إفطار صحية مشبعة.', img:'https://images.unsplash.com/photo-1586444248902-2f64eddc13df?w=500&q=80', price:65, oldPrice:85, discount:23, rating:4.4, reviews:3211 },
    { id:79, cat:'food', catLabel:'أغذية ومشروبات', name:'تونة ريو ماري قطعة واحدة بزيت الزيتون', desc:'أجود أنواع تونة الزعنفة الصفراء الإيطالية المحفوظة في زيت زيتون بكر.', img:'https://images.unsplash.com/photo-1548907040-4baa42d10919?w=500&q=80', price:75, oldPrice:95, discount:21, rating:4.7, reviews:876 },
    { id:80, cat:'food', catLabel:'أغذية ومشروبات', name:'حليب جهينة كامل الدسم طويل الأجل 1 لتر', desc:'حليب بقري طبيعي 100% معالج بالحرارة العالية ومعبأ في عبوة معقمة.', img:'https://images.unsplash.com/photo-1563636619-e9143da7973b?w=500&q=80', price:38, oldPrice:45, discount:15, rating:4.5, reviews:4321 },

    // ===== سيارات وإكسسوار (auto) =====
    { id:81, cat:'auto', catLabel:'سيارات وإكسسوار', name:'شاحن سيارة أنكر ذكي بتقنية PowerIQ 3.0', desc:'منفذ مزدوج بقوة 52.5 واط يشحن الهاتف واللابتوب داخل السيارة بسرعة خرافية.', img:'https://images.unsplash.com/photo-1563720223185-11003d516935?w=500&q=80', price:450, oldPrice:600, discount:25, rating:4.7, reviews:1230 },
    { id:82, cat:'auto', catLabel:'سيارات وإكسسوار', name:'كاميرا سيارة داش كام شاومي 70mai Pro Plus', desc:'تسجيل بدقة 2.7K مع نظام تحديد المواقع GPS ومراقبة على مدار 24 ساعة.', img:'https://images.unsplash.com/photo-1552519507-da3b142c6e3d?w=500&q=80', price:2800, oldPrice:3500, discount:20, rating:4.8, reviews:1987 },
    { id:83, cat:'auto', catLabel:'سيارات وإكسسوار', name:'منفاخ إطارات رقمي محمول شاومي يشتغل بالبطارية', desc:'مضخة هواء ذكية تتوقف تلقائياً عند الوصول للضغط المطلوب، مناسب للطوارئ.', img:'https://images.unsplash.com/photo-1486006920555-c77dce18193b?w=500&q=80', price:1650, oldPrice:2200, discount:25, rating:4.6, reviews:3210 },
    { id:84, cat:'auto', catLabel:'سيارات وإكسسوار', name:'حامل هاتف للسيارة مغناطيسي يثبت بفتحة التكييف', desc:'مغناطيس نيوديميوم قوي جداً يثبت الهاتف بقوة في أشد الطرق وعورة.', img:'https://images.unsplash.com/photo-1549399542-7e3f8b79c341?w=500&q=80', price:120, oldPrice:180, discount:33, rating:4.3, reviews:4321 },
    { id:85, cat:'auto', catLabel:'سيارات وإكسسوار', name:'مكنسة سيارة محمولة Baseus لاسلكية قوة 6000Pa', desc:'تصميم مدمج وخفيف الوزن ببطارية قوية لتنظيف الفتات والغبار في الزوايا.', img:'https://images.unsplash.com/photo-1507136566006-cfc505b114fc?w=500&q=80', price:890, oldPrice:1200, discount:25, rating:4.4, reviews:876 },
    { id:86, cat:'auto', catLabel:'سيارات وإكسسوار', name:'معطر جو للسيارة كليفتون رائحة السيارة الجديدة', desc:'يدوم حتى 60 يوماً يقضي على الروائح الكريهة ويمنحك انتعاشاً دائماً.', img:'https://images.unsplash.com/photo-1511919884226-fd3cad34687c?w=500&q=80', price:60, oldPrice:85, discount:29, rating:4.2, reviews:5432 },
    { id:87, cat:'auto', catLabel:'سيارات وإكسسوار', name:'طقم مناشف مايكروفايبر لتنظيف السيارة 4 قطع', desc:'فائقة الامتصاص وناعمة جداً لا تترك أي خدوش على طلاء السيارة أو الزجاج.', img:'https://images.unsplash.com/photo-1486006920555-c77dce18193b?w=500&q=80', price:110, oldPrice:150, discount:26, rating:4.5, reviews:987 },
    { id:88, cat:'auto', catLabel:'سيارات وإكسسوار', name:'وسادة مقعد السيارة الطبية ميموري فوم المريحة', desc:'تصميم مريح يقلل الضغط على الظهر والعمود القبلي أثناء القيادة الطويلة.', img:'https://images.unsplash.com/photo-1563720223185-11003d516935?w=500&q=80', price:350, oldPrice:480, discount:27, rating:4.6, reviews:1654 },
    { id:89, cat:'auto', catLabel:'سيارات وإكسسوار', name:'مظلة زجاج أمامي للسيارة قابلة للطي عاكسة', desc:'تحمي مقصورة السيارة والتابلوه من حرارة الشمس الحارقة والأشعة فوق البنفسجية.', img:'https://images.unsplash.com/photo-1552519507-da3b142c6e3d?w=500&q=80', price:180, oldPrice:250, discount:28, rating:4.1, reviews:2341 },
    { id:90, cat:'auto', catLabel:'سيارات وإكسسوار', name:'جهاز فحص أعطال السيارة OBD2 بلوتوث ذكي', desc:'يتصل بالهاتف عبر تطبيق مخصص لقراءة وتصفير أعطال محرك السيارة فوراً.', img:'https://images.unsplash.com/photo-1507136566006-cfc505b114fc?w=500&q=80', price:400, oldPrice:550, discount:27, rating:4.5, reviews:654 },

    // ===== مكتب وقرطاسية (office) =====
    { id:91, cat:'office', catLabel:'مكتب وقرطاسية', name:'طقم أقلام حبر سائل يوني-بال جيت ستريم 3 قطع', desc:'حبر سريع الجفاف يمنع التلطيخ مثالي للكتابة السريعة والمستخدمين الأعسر.', img:'https://images.unsplash.com/photo-1583485088034-697b5bc54ccd?w=500&q=80', price:120, oldPrice:160, discount:25, rating:4.8, reviews:3210 },
    { id:92, cat:'office', catLabel:'مكتب وقرطاسية', name:'دباسة مكتبية ثقيلة كانغارو لـ 50 ورقة كاملة', desc:'هيكل معدني قوي مع مقبض مريح مضاد للانزلاق لأعمال الأرشفة الكبيرة.', img:'https://images.unsplash.com/photo-1513151233558-d860c5398176?w=500&q=80', price:190, oldPrice:250, discount:24, rating:4.6, reviews:1432 },
    { id:93, cat:'office', catLabel:'مكتب وقرطاسية', name:'منظم مكتب خشبي فاخر متعدد الأقسام للأقلام', desc:'يحتوي على درج صغير وحوامل للكتب والأوراق ليحافظ على ترتيب مكتبك.', img:'https://images.unsplash.com/photo-1583485088034-697b5bc54ccd?w=500&q=80', price:280, oldPrice:390, discount:28, rating:4.5, reviews:876 },
    { id:94, cat:'office', catLabel:'مكتب وقرطاسية', name:'صندوق ورق تصوير دبل إيه A4 طقم 5 رزم ناصع', desc:'وزن 80 جرام، ورق ناصع البياض ممتاز للطابعات الليزرية والإنك جيت.', img:'https://images.unsplash.com/photo-1513151233558-d860c5398176?w=500&q=80', price:750, oldPrice:900, discount:16, rating:4.7, reviews:5432 },
    { id:95, cat:'office', catLabel:'مكتب وقرطاسية', name:'أقلام تحديد هايلايتر ستابيلو بوس 4 ألوان زاهية', desc:'تكنولوجيا منع جفاف الحبر حتى 4 ساعات بدون غطاء، ألوان واضحة جداً.', img:'https://images.unsplash.com/photo-1583485088034-697b5bc54ccd?w=500&q=80', price:140, oldPrice:190, discount:26, rating:4.9, reviews:6521 },
    { id:96, cat:'office', catLabel:'مكتب وقرطاسية', name:'لوحة مذكرات مغناطيسية بيضاء إطار ألومنيوم', desc:'مقاس 60×90 سم تأتي مع حامل أقلام وممحاة، مثالية للشرح والتخطيط.', img:'https://images.unsplash.com/photo-1513151233558-d860c5398176?w=500&q=80', price:390, oldPrice:520, discount:25, rating:4.4, reviews:987 },
    { id:97, cat:'office', catLabel:'مكتب وقرطاسية', name:'آلة حاسبة علمية كاسيو FX-991ARX الإصدار العربي', desc:'أقوى حاسبة للمهندسين والطلاب تدعم حل المعادلات والمصفوفات المعقدة.', img:'https://images.unsplash.com/photo-1583485088034-697b5bc54ccd?w=500&q=80', price:1200, oldPrice:1500, discount:20, rating:4.9, reviews:8901 },
    { id:98, cat:'office', catLabel:'مكتب وقرطاسية', name:'خزانة ملفات كيبسيك كرتون مقوى طقم 5 قطع', desc:'مثالية لتنظيم الأوراق وحفظ المستندات والملفات بشكل رأسي أنيق.', img:'https://images.unsplash.com/photo-1513151233558-d860c5398176?w=500&q=80', price:160, oldPrice:220, discount:27, rating:4.2, reviews:1230 },
    { id:99, cat:'office', catLabel:'مكتب وقرطاسية', name:'حقيبة مستندات مقاومة للحريق والماء مقاس A4', desc:'مصنوعة من ألياف زجاجية مطلية بالسيليكون لحماية الأوراق والشهادات الهامة.', img:'https://images.unsplash.com/photo-1583485088034-697b5bc54ccd?w=500&q=80', price:450, oldPrice:600, discount:25, rating:4.6, reviews:654 },
    { id:100, cat:'office', catLabel:'مكتب وقرطاسية', name:'خرامة ورق معدنية تايواني ثقيلة بثقبين مريحين', desc:'تثقب حتى 30 ورقة في وقت واحد بدقة تامة وبها خزان سفلي لتجميع القصاصات.', img:'https://images.unsplash.com/photo-1513151233558-d860c5398176?w=500&q=80', price:130, oldPrice:180, discount:27, rating:4.5, reviews:1876 }
];

let currentCategory = 'all';
let cart = [];

window.addEventListener('DOMContentLoaded', () => {
    setTimeout(() => {
        const splash = document.getElementById('splash');
        splash.style.opacity = '0';
        setTimeout(() => splash.style.display = 'none', 600);
    }, 1500);
    
    renderProducts();
});

function renderProducts() {
    const grid = document.getElementById('grid');
    const searchVal = document.getElementById('search').value.toLowerCase().trim();
    grid.innerHTML = '';

    const filtered = products.filter(p => {
        const matchesCat = (currentCategory === 'all' || p.cat === currentCategory);
        const matchesSearch = p.name.toLowerCase().includes(searchVal) || p.desc.toLowerCase().includes(searchVal);
        return matchesCat && matchesSearch;
    });

    document.getElementById('count-badge').innerText = `${filtered.length} منتج`;

    if (filtered.length === 0) {
        grid.innerHTML = `
            <div class="empty">
                <i class="fas fa-box-open"></i>
                <p>عذراً، لم نجد أي منتجات تطابق بحثك حالياً.</p>
            </div>`;
        return;
    }

    filtered.forEach(p => {
        const isAdded = cart.some(item => item.id === p.id);
        const card = document.createElement('div');
        card.className = 'card';
        card.innerHTML = `
            <span class="discount-badge">${p.discount}% خصم</span>
            <div class="card-img">
                <img src="${p.img}" alt="${p.name}">
            </div>
            <div class="card-body">
                <span class="card-cat">${p.catLabel}</span>
                <div class="card-name">${p.name}</div>
                <div class="card-desc">${p.desc}</div>
                <div class="rating">
                    <i class="fas fa-star"></i> <span>${p.rating} (${p.reviews})</span>
                </div>
                <div class="card-footer">
                    <div class="prices">
                        <span class="old-price">${p.oldPrice} ج.م</span>
                        <span class="cur-price">${p.price} <small>ج.م</small></span>
                    </div>
                    <button class="add-btn ${isAdded ? 'added' : ''}" onclick="toggleCartAction(${p.id}, this)">
                        <i class="fas ${isAdded ? 'fa-check' : 'fa-shopping-cart'}"></i>
                        <span>${isAdded ? 'في السلة' : 'شراء'}</span>
                    </button>
                </div>
            </div>
        `;
        grid.appendChild(card);
    });
}

function setCategory(cat, btn) {
    currentCategory = cat;
    document.querySelectorAll('.cat-btn').forEach(b => b.classList.remove('active'));
    btn.classList.add('active');
    renderProducts();
}

function filterProducts() {
    renderProducts();
}

function toggleCartDropdown() {
    document.getElementById('cartDropdown').classList.toggle('open');
}

function toggleCartAction(productId, btn) {
    const product = products.find(p => p.id === productId);
    const index = cart.findIndex(item => item.id === productId);

    if (index === -1) {
        cart.push(product);
        btn.classList.add('added');
        btn.innerHTML = `<i class="fas fa-check"></i> <span>في السلة</span>`;
    } else {
        cart.splice(index, 1);
        btn.classList.remove('added');
        btn.innerHTML = `<i class="fas fa-shopping-cart"></i> <span>شراء</span>`;
    }

    updateCartUI();
}

function updateCartUI() {
    document.getElementById('cart-count').innerText = cart.length;
    const dropItemsContainer = document.getElementById('cartDropItems');
    const totalDisplay = document.getElementById('cartDropTotal');
    
    if (cart.length === 0) {
        dropItemsContainer.innerHTML = `<p style="text-align:center; color:#9ca3af; padding: 20px; font-size:0.85rem;">السلة فارغة حالياً</p>`;
        totalDisplay.innerText = `0 ج.م`;
        return;
    }

    dropItemsContainer.innerHTML = '';
    let total = 0;

    cart.forEach(item => {
        total += item.price;
        dropItemsContainer.innerHTML += `
            <div class="cart-drop-item">
                <span>${item.name}</span>
                <div>
                    <span style="font-weight:700; color:#16a34a; margin-left:10px;">${item.price} ج.م</span>
                    <button class="remove-item-btn" onclick="removeFromCart(${item.id})">✕</button>
                </div>
            </div>
        `;
    });

    totalDisplay.innerText = `${total} ج.م`;
}

function removeFromCart(productId) {
    const index = cart.findIndex(item => item.id === productId);
    if (index !== -1) {
        cart.splice(index, 1);
        updateCartUI();
        renderProducts();
    }
}

function checkoutAction() {
    if (cart.length === 0) {
        alert("سلتك فارغة تماماً يا إبراهيم! أضف بعض المنتجات أولاً للبدء.");
        return;
    }
    let total = cart.reduce((sum, item) => sum + item.price, 0);
    alert(`🎉 تم إرسال طلب الشراء بنجاح عبر IBRA STORE!\nإجمالي عدد المنتجات: ${cart.length}\nالمبلغ المطلوب: ${total} ج.م\nسيتم تجهيز شحنتك فوراً.`);
    cart = [];
    updateCartUI();
    renderProducts();
    toggleCartDropdown();
}

// ==================== دوال التحكم في واجهة تسجيل الدخول الجديدة ====================

// فتح النافذة
function openLoginModal() {
    document.getElementById('loginOverlay').classList.add('show');
}

// إغلاق النافذة يدوياً
function closeLoginModal() {
    document.getElementById('loginOverlay').classList.remove('show');
}

// إغلاق النافذة عند الضغط في أي مكان خارج المربع الأبيض
function closeLoginModalOutside(event) {
    if (event.target.id === 'loginOverlay') {
        closeLoginModal();
    }
}

// التعامل مع إرسال بيانات النموذج (التجريبي)
function handleLoginSubmit(event) {
    event.preventDefault();
    alert("🎉 تم تسجيل الدخول بنجاح إلى متجرك!");
    closeLoginModal();
}
</script>

</body>
</html>
