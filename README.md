
<!DOCTYPE html>
<html lang="ar">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>قهوة سوداء - بورتفوليو</title>
<style>
    * {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
        font-family: 'Arial', sans-serif;
        transition: all 0.3s ease;
    }

    body {
        line-height: 1.6;
        background-color: #ffe6f0;
        color: #333;
    }

    a { text-decoration: none; color: inherit; }

    /* ---------- Navbar ---------- */
    header {
        background-color: #1a1a1a;
        padding: 10px 20px;
        position: sticky;
        top: 0;
        z-index: 1000;
        display: flex;
        justify-content: space-between;
        align-items: center;
    }

    .logo {
        font-size: 1.8rem;
        font-weight: bold;
        color: #fff;
    }

    nav ul {
        display: flex;
        list-style: none;
    }

    nav ul li {
        margin-left: 10px;
    }

    nav ul li a {
        display: block;
        padding: 10px 20px;
        background-color: #ff4081;
        color: white;
        border-radius: 5px;
        font-weight: bold;
        text-align: center;
        width: 120px; /* أزرار مستقيمة */
        transition: background 0.3s;
    }

    nav ul li a:hover {
        background-color: #e03570;
    }

    #darkModeToggle {
        cursor: pointer;
        background-color: #333;
        border: none;
        border-radius: 5px;
        padding: 10px 15px;
        color: white;
        font-size: 1rem;
        margin-left: 15px;
    }

    #darkModeToggle:hover {
        background-color: #ff4081;
    }

    section {
        padding: 80px 20px;
        max-width: 1000px;
        margin: auto;
    }

    h2 {
        text-align: center;
        margin-bottom: 40px;
        color: #1a1a1a;
    }

    #about p {
        text-align: center;
        max-width: 700px;
        margin: auto;
    }

    #portfolio .projects {
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
        gap: 20px;
    }

    #portfolio .project {
        background-color: white;
        border-radius: 10px;
        overflow: hidden;
        box-shadow: 0 2px 8px rgba(0,0,0,0.1);
        transition: transform 0.3s ease;
    }

    #portfolio .project img {
        width: 100%;
        display: block;
        height: 200px;
        object-fit: cover;
        background-color: #ddd;
    }

    #portfolio .project:hover {
        transform: scale(1.05);
    }

    #portfolio .project h3 {
        padding: 15px;
        text-align: center;
        color: #1a1a1a;
    }

    #contact form {
        max-width: 500px;
        margin: auto;
        display: flex;
        flex-direction: column;
    }

    #contact input, #contact textarea {
        padding: 10px;
        margin-bottom: 15px;
        border: 1px solid #ccc;
        border-radius: 5px;
        font-size: 1rem;
        background-color: #fff;
    }

    #contact button {
        padding: 10px;
        background-color: #ff4081;
        color: white;
        border: none;
        border-radius: 5px;
        cursor: pointer;
        font-size: 1rem;
        transition: background 0.3s;
    }

    #contact button:hover {
        background-color: #e03570;
    }

    footer {
        text-align: center;
        padding: 20px;
        background-color: #1a1a1a;
        color: white;
    }

    /* ---------- Dark Mode ---------- */
    body.dark {
        background-color: #121212;
        color: #e0e0e0;
    }

    body.dark header, body.dark footer {
        background-color: #1f1f1f;
    }

    body.dark nav ul li a {
        background-color: #ff4081;
        color: white;
    }

    body.dark nav ul li a:hover {
        background-color: #e03570;
    }

    body.dark #portfolio .project {
        background-color: #1f1f1f;
        color: #e0e0e0;
    }

    body.dark #contact input, body.dark #contact textarea {
        background-color: #333;
        border: 1px solid #555;
        color: #fff;
    }

    body.dark #contact button {
        background-color: #ff4081;
        color: white;
    }

    body.dark #contact button:hover {
        background-color: #e03570;
    }

    @media (max-width: 600px) {
        nav ul { flex-direction: column; margin-top: 10px; }
        nav ul li { margin-left: 0; margin-top: 10px; width: 100%; }
        nav ul li a { width: 100%; }
    }
</style>
</head>
<body>

<header>
    <div class="logo">قهوة سوداء</div>
    <div style="display:flex; align-items:center;">
        <nav>
            <ul>
                <li><a href="#about">عنّي</a></li>
                <li><a href="#portfolio">أعمالي</a></li>
                <li><a href="#contact">اتصل بي</a></li>
            </ul>
        </nav>
        <button id="darkModeToggle">🌙</button>
    </div>
</header>

<section id="about">
    <h2>عنّي</h2>
    <p>مرحباً! أنا Marwane Mellouk، مطور ومصمم مواقع شغوف بابتكار تجارب رقمية مميزة. أحب تعلم التقنيات الجديدة وتحويل الأفكار إلى مشاريع ملموسة.</p>
</section>

<section id="portfolio">
    <h2>أعمالي</h2>
    <div class="projects">
        <!-- صور افتراضية للبرمجة -->
        <div class="project">
            <img src="https://via.placeholder.com/400x200?text=Code+1" alt="مشروع برمجي 1">
            <h3>مشروع برمجي 1</h3>
        </div>
        <div class="project">
            <img src="https://via.placeholder.com/400x200?text=Code+2" alt="مشروع برمجي 2">
            <h3>مشروع برمجي 2</h3>
        </div>
        <div class="project">
            <img src="https://via.placeholder.com/400x200?text=Code+3" alt="مشروع برمجي 3">
            <h3>مشروع برمجي 3</h3>
        </div>
        <div class="project">
            <img src="https://via.placeholder.com/400x200?text=Code+4" alt="مشروع برمجي 4">
            <h3>مشروع برمجي 4</h3>
        </div>
    </div>
</section>

<section id="contact">
    <h2>اتصل بي</h2>
    <form>
        <input type="text" placeholder="الاسم" required>
        <input type="email" placeholder="البريد الإلكتروني" required>
        <textarea rows="5" placeholder="رسالتك" required></textarea>
        <button type="submit">أرسل</button>
    </form>
</section>

<footer>
    &copy; 2025 قهوة سوداء | جميع الحقوق محفوظة
</footer>

<script>
    const toggleBtn = document.getElementById('darkModeToggle');
    toggleBtn.addEventListener('click', () => {
        document.body.classList.toggle('dark');
        toggleBtn.textContent = document.body.classList.contains('dark') ? '☀️' : '🌙';
    });
</script>

</body>
</html>
