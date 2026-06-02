<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>BC.Inc - Marwane Mellouk</title>

<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.2/css/all.min.css" integrity="sha512-a7VgX9mXzqZ/w+PoFqD2x7FG9U64nKw6l7v6bZ9+T7pG9B8LxN5bD6kD3B3Y2kRkaRbF+JQkOZL2R3vRKwD8g==" crossorigin="anonymous" referrerpolicy="no-referrer" />

<style>
    :root {
        --primary-color: #00ff66; /* لون التشفير الأخضر الكلاسيكي */
        --bg-dark: #0a0f0d;
        --card-bg-dark: rgba(16, 24, 20, 0.9);
        --text-dark: #e0e0e0;
        
        --bg-light: #f4f7f5;
        --card-bg-light: rgba(255, 255, 255, 0.95);
        --text-light: #1a1a1a;
    }

    body {
        font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        margin: 0;
        padding: 0;
        transition: background-color 0.5s, color 0.5s;
        overflow-x: hidden;
        position: relative;
    }

    /* خلفية التشفير الديناميكية */
    #crypto-canvas {
        position: fixed;
        top: 0;
        left: 0;
        width: 100vw;
        height: 100vh;
        z-index: -1;
        pointer-events: none;
        transition: opacity 0.5s;
    }

    body.light #crypto-canvas {
        opacity: 0.15; /* تخفيف حدة شاشة التشفير في الوضع الفاتح */
    }

    /* الوضع الليلي والنهاري */
    body.light {
        background-color: var(--bg-light);
        color: var(--text-light);
    }

    body.dark {
        background-color: var(--bg-dark);
        color: var(--text-dark);
    }

    /* زر تبديل الوضع */
    .toggle-btn {
        position: fixed;
        top: 20px;
        left: 20px; /* تم النقل لليسار ليتناسب مع التصفح باللغة العربية */
        padding: 12px;
        cursor: pointer;
        background-color: transparent;
        color: var(--primary-color);
        border: 2px solid var(--primary-color);
        border-radius: 50%;
        font-size: 20px;
        transition: all 0.3s ease;
        z-index: 1000;
        display: flex;
        align-items: center;
        justify-content: center;
        width: 45px;
        height: 45px;
    }

    body.light .toggle-btn {
        color: #0056b3;
        border-color: #0056b3;
    }

    .toggle-btn:hover {
        transform: scale(1.1) rotate(15deg);
        background-color: rgba(0, 255, 102, 0.1);
    }

    /* الهيدر والعنوان الرئيسي */
    .header-container {
        text-align: center;
        padding: 40px 20px 10px 20px;
    }

    .company-title {
        font-family: 'Courier New', Courier, monospace;
        font-size: 2.5rem;
        letter-spacing: 2px;
        margin-bottom: 5px;
        color: var(--primary-color);
        text-shadow: 0 0 10px rgba(0, 255, 102, 0.5);
    }

    body.light .company-title {
        color: #0056b3;
        text-shadow: none;
    }

    .subtitle {
        font-size: 1.3rem;
        font-weight: normal;
        opacity: 0.9;
    }

    /* صورة دائرية احترافية */
    .circular-img {
        display: block;
        margin: 20px auto;
        width: 130px;
        height: 130px;
        border-radius: 50%;
        object-fit: cover;
        border: 3px solid var(--primary-color);
        box-shadow: 0 0 15px rgba(0, 255, 102, 0.3);
        transition: transform 0.3s;
    }

    body.light .circular-img {
        border-color: #0056b3;
        box-shadow: 0 4px 10px rgba(0,0,0,0.15);
    }

    .circular-img:hover {
        transform: scale(1.05);
    }

    /* شريط الحركة */
    .ticker-wrap {
        width: 100%;
        background-color: rgba(0, 0, 0, 0.4);
        padding: 8px 0;
        border-top: 1px solid rgba(0, 255, 102, 0.2);
        border-bottom: 1px solid rgba(0, 255, 102, 0.2);
        margin-bottom: 30px;
    }

    body.light .ticker-wrap {
        background-color: rgba(0, 86, 179, 0.05);
        border-color: rgba(0, 86, 179, 0.2);
    }

    marquee {
        font-size: 16px;
        font-weight: bold;
        color: var(--primary-color);
    }

    body.light marquee {
        color: #0056b3;
    }

    /* البطاقات الكلاسيكية الاحترافية */
    .card {
        background-color: var(--card-bg-dark);
        color: var(--text-dark);
        margin: 25px auto;
        padding: 30px;
        max-width: 750px;
        border-radius: 6px; /* زوايا كلاسيكية حادة قليلاً وأكثر رسمية */
        border: 1px solid rgba(0, 255, 102, 0.2);
        box-shadow: 0 10px 30px rgba(0,0,0,0.5);
        transition: transform 0.3s, box-shadow 0.3s, background-color 0.5s;
        position: relative;
    }

    body.light .card {
        background-color: var(--card-bg-light);
        color: var(--text-light);
        border: 1px solid #ddd;
        box-shadow: 0 5px 15px rgba(0,0,0,0.05);
    }

    .card:hover {
        transform: translateY(-3px);
        border-color: var(--primary-color);
        box-shadow: 0 12px 35px rgba(0, 255, 102, 0.15);
    }

    body.light .card:hover {
        border-color: #0056b3;
        box-shadow: 0 8px 25px rgba(0,0,0,0.1);
    }

    /* عناصر البطاقة الداخية */
    .card h2 {
        font-size: 1.5rem;
        margin-top: 0;
        margin-bottom: 20px;
        border-bottom: 1px solid rgba(255,255,255,0.1);
        padding-bottom: 10px;
        color: #fff;
    }

    body.light .card h2 {
        color: #111;
        border-bottom: 1px solid #eee;
    }

    .cipher-details {
        background: rgba(0,0,0,0.3);
        padding: 20px;
        border-radius: 4px;
        border-right: 4px solid var(--primary-color);
        font-family: 'Courier New', Courier, monospace;
        margin: 15px 0;
    }

    body.light .cipher-details {
        background: #fdfdfd;
        border-right-color: #0056b3;
        border: 1px solid #e2e8f0;
        border-right: 4px solid #0056b3;
    }

    .cipher-details p {
        margin: 8px 0;
        line-height: 1.6;
    }

    .cipher-example {
        display: block;
        background: #000;
        color: #ff3366;
        padding: 12px;
        text-align: center;
        font-size: 1.2rem;
        letter-spacing: 2px;
        border-radius: 4px;
        margin-top: 10px;
        direction: ltr;
    }

    body.light .cipher-example {
        background: #2d3748;
        color: #ff6b6b;
    }

    .card-meta {
        display: flex;
        justify-content: space-between;
        font-size: 0.85rem;
        opacity: 0.7;
        margin-top: 20px;
        padding-top: 10px;
        border-top: 1px dashed rgba(255,255,255,0.1);
    }

    body.light .card-meta {
        border-top: 1px dashed #ddd;
    }

    /* دليل تعليمي سريع مدمج */
    .step-list {
        padding-right: 20px;
        line-height: 1.8;
    }
    .step-list li {
        margin-bottom: 10px;
    }

    /* أزرار احترافية */
    .btn {
        display: inline-flex;
        align-items: center;
        gap: 8px;
        padding: 12px 24px;
        margin-top: 15px;
        background-color: transparent;
        color: var(--primary-color);
        border: 2px solid var(--primary-color);
        border-radius: 4px;
        text-decoration: none;
        font-weight: bold;
        transition: all 0.3s;
        cursor: pointer;
    }

    body.light .btn {
        color: #0056b3;
        border-color: #0056b3;
    }

    .btn:hover {
        background-color: var(--primary-color);
        color: #000;
        box-shadow: 0 0 15px rgba(0, 255, 102, 0.4);
    }

    body.light .btn:hover {
        background-color: #0056b3;
        color: #fff;
        box-shadow: none;
    }

    /* تذييل الصفحة */
    .footer {
        text-align: center;
        padding: 40px;
        font-size: 0.9rem;
        opacity: 0.7;
    }
</style>
</head>
<body class="dark">

<canvas id="crypto-canvas"></canvas>

<button class="toggle-btn" id="modeBtn"><i class="fas fa-moon"></i></button>

<div class="header-container">
    <h1 class="company-title">BC.Inc</h1>
    <h2 class="subtitle">مؤسس خوارزمية نظام رسالة مشفرة 🔒</h2>
</div>

<img src="ff.jpg" alt="Marwane Mellouk" class="circular-img">

<div class="ticker-wrap">
    <marquee direction="right">Moroccan Sahara 🇲🇦 ☕ خوارزميات التشفير المتقدمة وحماية البيانات</marquee>
</div>

<div class="card">
    <h2><i class="fas fa-key" style="margin-left: 10px;"></i>نظام التشفير المعتمد</h2>
    <div class="cipher-details">
        <p><strong>اسم التشفير:</strong> Mellouk Dot-Bracket Cipher</p>
        <p><strong>الوصف:</strong> نظام ترميز يعتمد على فصل الحروف بنقاط، استخدام أقواس لتحديد الرسالة، وتوظيف أشكال حروف غير قياسية وعلامات ترقيم كجزء من المعنى الداخلي للمحتوى الموجه.</p>
        <p><strong>المصمم:</strong> Marwane Mellouk</p>
        <p><strong>تاريخ الإنشاء:</strong> 2026/02/05</p>
        <p><strong>مثال أصلي للرسالة المشفرة:</strong></p>
        <span class="cipher-example">[ک.ل.اًر.ك.ش.ح.ي.ح.ص.ك.م.ل.ا.ك.م ع؟ن]</span>
    </div>
    <div class="card-meta">
        <span><i class="fas fa-eye"></i> عدد المشاهدات: 1000</span>
        <span>تاريخ التحديث: 2026/04/01✎</span>
    </div>
</div>

<div class="card">
    <h2><i class="fas fa-graduation-cap" style="margin-left: 10px;"></i>دليل تعليمي: كيف تشفر رسالتك آمنًا؟</h2>
    <p>لحماية خصوصيتك قبل إرسال أي معلومات عبر شبكات التواصل، اتبع الهيكلية الكلاسيكية المتبعة في الأنظمة الأمنية المحسنة:</p>
    <ul class="step-list">
        <li><strong>أولاً:</strong> قم بصياغة نصك الأصلي بوضوح بعيدًا عن أي منصة إرسال.</li>
        <li><strong>ثانيًا:</strong> وظّف خوارزمية الفصل (عبر النقاط وعلامات الترقيم المخصصة) لتشتيت قارئي الحزم اللاسلكية.</li>
        <li><strong>ثالثًا:</strong> أغلق رسالتك بالأقواس المحددة العازلة لمنع التلاعب بطول الرسالة (Data Integrity).</li>
    </ul>
    <div class="card-meta">
        <span><i class="fas fa-shield-alt"></i> المنصة التعليمية الآمنة</span>
        <span>الكاتب: Marwane✎</span>
    </div>
</div>

<div class="card">
    <h2><i class="fas fa-user-shield" style="margin-left: 10px;"></i>لوحة معلومات المؤسس📋</h2>
    <p>مرحباً بك، معكم مروان ملوك من المغرب. أعمل كمبرمج ويب ومتخصص في صياغة المحتوى التقني والتوعوي على شبكات التواصل الاجتماعي. هذا الموقع يمثل منصتي الرسمية لشركة <strong>BC.Inc</strong>، حيث أشارككم أحدث الابتكارات البرمجية، وخوارزميات الأمن الرقمي، والأنظمة المخصصة التي أقوم بتطويرها.</p>
    <div class="card-meta">
        <span><i class="fas fa-heart"></i> التفاعل: 31</span>
        <span>موثق بالكامل بـ 2026</span>
    </div>
</div>

<div class="card">
    <h2><i class="fab fa-telegram" style="margin-left: 10px;"></i>المستودع البرمجي وبوت التواصل 🤖</h2>
    <p><strong>قصة تطوير البوت:</strong></p>
    <p>هذا المشروع يحمل طابعاً خاصاً وكفاحاً حقيقياً؛ استغرق تطوير الكود البرمجي الخاص به حوالي 12 ساعة متواصلة من العمل الدؤوب. وفي لحظة غير متوقعة، انقطع الاتصال بالإنترنت تماماً وتزامن ذلك مع عطل مفاجئ أدى إلى كسر هاتفي المحمول! يُعد هذا أول مشروع تقني ينتهي بكسر هاتف ذكي، لكن خروج البوت للعلن كان بمثابة معجزة تقنية تستحق العناء. 🤖😂💔</p>
    
    <a href="https://t.me/Developers230" class="btn" target="_blank">
        <i class="fab fa-telegram-plane"></i> الانتقال إلى بوت تلغرام
    </a>
    
    <div class="card-meta">
        <span><i class="fas fa-bolt"></i> المشاهدات: 67</span>
        <span>للتواصل المباشر: @blackCoffee987 ☎︎</span>
    </div>
</div>

<div class="card">
    <h2><i class="fas fa-brain" style="margin-left: 10px;"></i>التوعية النفسية: الغضب مركب هدّام ☀︎</h2>
    <p>في عالم البرمجة والأمن، الحفاظ على الهدوء هو السلاح الأول. الغضب يشبه الفيروس العصبي الذي لا يترك خلفه سوى القرارات الخاطئة؛ يجعلك تدمر كل ما بنيته وتفقد السيطرة على أدواتك. حماية ذاتك نفسياً لا تقل أهمية عن حماية برمجياتك.</p>
    <div class="card-meta">
        <span>مقالة توعوية قصيرة</span>
    </div>
</div>

<div class="ticker-wrap">
    <marquee direction="right">BC.Inc © 2026 - جميع الحقوق محفوظة لموقع مروان ملوك المطور</marquee>
</div>

<div class="footer">
    <p>جميع الحقوق محفوظة لشركة BC.Inc وموقع مروان 2026</p>
</div>

<script>
    // نظام تبديل الوضع (Dark/Light Mode)
    const modeBtn = document.getElementById('modeBtn');
    const icon = modeBtn.querySelector('i');

    modeBtn.addEventListener('click', () => {
        document.body.classList.toggle('dark');
        document.body.classList.toggle('light');

        if(document.body.classList.contains('dark')) {
            icon.classList.remove('fa-sun');
            icon.classList.add('fa-moon');
        } else {
            icon.classList.remove('fa-moon');
            icon.classList.add('fa-sun');
        }
    });

    // ضبط الوضع التلقائي بناءً على وقت المستخدم الفعلي
    const hour = new Date().getHours();
    if(hour >= 18 || hour < 6) {
        document.body.classList.add('dark');
        document.body.classList.remove('light');
        icon.classList.className = "fas fa-moon";
    } else {
        document.body.classList.add('light');
        document.body.classList.remove('dark');
        icon.className = "fas fa-sun";
    }

    // تأثير خلفية التشفير الرقمية (Crypto Matrix Background)
    const canvas = document.getElementById('crypto-canvas');
    const ctx = canvas.getContext('2d');

    function resizeCanvas() {
        canvas.width = window.innerWidth;
        canvas.height = window.innerHeight;
    }
    resizeCanvas();
    window.addEventListener('resize', resizeCanvas);

    // الرموز البرمجية والمشفرة المستخدمة في الخلفية
    const cryptoChars = "0101010101ABCDEFGHIJKLMNOPQRSTUVWXYZ[]...---***///===:::";
    const charArray = cryptoChars.split('');
    const fontSize = 14;
    const columns = canvas.width / fontSize;
    const drops = [];

    for (let x = 0; x < columns; x++) {
        drops[x] = 1;
    }

    function drawCryptoBackground() {
        // تأثير الشفافية لترك أثر خلف الحروف المتساقطة
        ctx.fillStyle = document.body.classList.contains('dark') ? 'rgba(10, 15, 13, 0.05)' : 'rgba(244, 247, 245, 0.05)';
        ctx.fillRect(0, 0, canvas.width, canvas.height);

        // لون النص في الخلفية
        ctx.fillStyle = document.body.classList.contains('dark') ? '#00ff66' : '#0056b3';
        ctx.font = fontSize + 'px monospace';

        for (let i = 0; i < drops.length; i++) {
            const text = charArray[Math.floor(Math.random() * charArray.length)];
            ctx.fillText(text, i * fontSize, drops[i] * fontSize);

            if (drops[i] * fontSize > canvas.height && Math.random() > 0.975) {
                drops[i] = 0;
            }
            drops[i]++;
        }
    }

    setInterval(drawCryptoBackground, 33);
</script>

</body>
</html>
