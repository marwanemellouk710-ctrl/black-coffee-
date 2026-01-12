
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Marwane Mellouk - Black Coffee</title>

<style>
    body {
        font-family: Tahoma, sans-serif;
        margin: 0;
        padding: 0;
        transition: background-color 0.5s, color 0.5s;
    }

    /* Light & Dark Mode */
    body.light {
        background-color: #f5f5f5;
        color: #000;
    }

    body.dark {
        background-color: #1e1e1e;
        color: #f5f5f5;
    }

    /* زر تبديل الوضع */
    .toggle-btn {
        position: fixed;
        top: 10px;
        right: 10px;
        padding: 10px 15px;
        cursor: pointer;
        background-color: #007bff;
        color: #fff;
        border: none;
        border-radius: 5px;
        font-weight: bold;
        transition: background-color 0.3s;
    }

    .toggle-btn:hover {
        background-color: #0056b3;
    }

    /* صورة دائرية في الأعلى */
    .profile-img {
        display: block;
        margin: 20px auto;
        width: 150px;
        height: 150px;
        border-radius: 50%;
        object-fit: cover;
        border: 4px solid #fff;
        box-shadow: 0 4px 10px rgba(0,0,0,0.3);
    }

    /* تنسيق البطاقات */
    .card {
        background-color: rgba(255,255,255,0.9);
        color: #000;
        margin: 20px auto;
        padding: 20px;
        max-width: 800px;
        border-radius: 15px;
        box-shadow: 0 5px 15px rgba(0,0,0,0.2);
        transition: transform 0.3s, background-color 0.5s, color 0.5s;
    }

    body.dark .card {
        background-color: rgba(50,50,50,0.9);
        color: #f5f5f5;
    }

    .card:hover {
        transform: translateY(-5px);
        box-shadow: 0 8px 25px rgba(0,0,0,0.4);
    }

    h1, h2, h6 {
        margin: 10px 0;
        text-align: center;
    }

    hr {
        border: 1px solid #ccc;
        margin: 20px 0;
    }

    marquee {
        font-family: tahoma;
        font-size: 18px;
        color: #007bff;
        margin-bottom: 20px;
    }

    /* أزرار احترافية */
    .btn {
        display: inline-block;
        padding: 10px 20px;
        margin: 10px 0;
        background-color: #007bff;
        color: #fff;
        border-radius: 8px;
        text-decoration: none;
        font-weight: bold;
        transition: background-color 0.3s, transform 0.2s;
    }

    .btn:hover {
        background-color: #0056b3;
        transform: scale(1.05);
    }

    /* روابط داخل النص */
    a {
        color: #007bff;
        text-decoration: none;
    }

    a:hover {
        text-decoration: underline;
    }

</style>
</head>
<body class="light">

<!-- زر تبديل الوضع -->
<button class="toggle-btn" onclick="toggleMode()">🌙 / ☀️</button>

<!-- صورة دائرية -->
<img src="profile.jpg" alt="Marwane Mellouk" class="profile-img">

<marquee direction="right">Moroccan Sahara🇲🇦☕</marquee>

<!-- بطاقة التعريف -->
<div class="card">
    <h1 style="color: pink;">☰</h1>
    <h1 style="color: black;">𝕄𝕒𝕣𝕨𝕒𝕟𝕖 𝕄𝕖𝕝𝕝𝕠𝕦𝕜 🅥</h1>
    <h1 style="color: orange;">Black coffee Mr. Marwan Malook☕</h1>
    <hr>
    <h6>Takbisa updated ☁️⬇️</h6>
    <h6>Number of views on the site: 1000</h6>
    <h6>Date modified: 4/1/2026✎</h6>
</div>

<!-- بطاقة عن الكاتب -->
<div class="card">
    <h1 style="color: red;">Information board📋</h1>
    <p>☛ About me: My name is Marwan Malouk from Morocco, residing in the United States of America. My profession is a content creator and influencer on social media. My work is a web programmer. This is my personal website, where I publish everything that concerns me.</p>
    <h6>Takbisa updated ☁️⬇️</h6>
    <h6>Number of views: 31 ♥︎</h6>
    <hr>
    <h6>Writer: Marwan✎</h6>
</div>

<!-- بطاقة الغضب -->
<div class="card">
    <h1>Anger is a disease ☀︎</h1>
    <h2>There is no cure for this neurological disease. If you suffer from it, you will feel something abnormal; you will break everything in front of you and hate yourself.</h2>
    <h6>Post✎</h6>
</div>

<!-- بطاقة بوت التليجرام -->
<div class="card">
    <h2>This is my channel on Telegram. There is a bot in it 🤖</h2>
    <a href="https://t.me/Developers230" class="btn">Go to Telegram Bot</a>
    <h6>A look at this bot and its development story 🤖</h6>
    <p>This bot has a different story. Its code was developed and it took me about 12 hours to develop it. Suddenly, the internet was cut off and without realizing it, my mobile phone was broken. This is the first project for which a mobile phone was broken. It was a miracle. 🤖😂💔</p>
    <h6>Number of views: 67 ♥︎</h6>
    <h6>To get in touch, message us on Telegram ☎︎☛ @blackCoffee987</h6>
</div>

<!-- بطاقة الحقوق -->
<div class="card">
    <h2 style="color: yellow;">All rights reserved to Marwan website 2026</h2>
</div>

<marquee direction="right">Moroccan Sahara🇲🇦☕</marquee>
<img src="ff.jpg" alt="ff" style="display:block; margin:auto; width:200px; border-radius:20px;">

<script>
    // تبديل الوضع بين Light و Dark
    function toggleMode() {
        document.body.classList.toggle('dark');
        document.body.classList.toggle('light');
    }

    // الوضع التلقائي حسب الوقت
    const hour = new Date().getHours();
    if(hour >= 18 || hour < 6) {
        document.body.classList.add('dark');
        document.body.classList.remove('light');
    } else {
        document.body.classList.add('light');
        document.body.classList.remove('dark');
    }
</script>

</body>
</html>
