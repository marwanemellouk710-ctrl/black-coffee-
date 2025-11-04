<!DOCTYPE html>
<html lang="ar">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>بورتفوليو Marwane Mellouk</title>
    <style>
        /* ---------- Reset ---------- */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: Arial, sans-serif;
        }

        body {
            line-height: 1.6;
            background-color: #f5f5f5;
            color: #333;
            transition: background 0.4s, color 0.4s;
        }

        a {
            text-decoration: none;
            color: inherit;
        }

        /* ---------- Navbar ---------- */
        header {
            background-color: #1a1a1a;
            color: white;
            padding: 15px 20px;
            position: sticky;
            top: 0;
            z-index: 1000;
        }

        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        nav .logo {
            font-size: 1.5rem;
            font-weight: bold;
        }

        nav ul {
            display: flex;
            list-style: none;
        }

        nav ul li {
            margin-left: 20px;
        }

        nav ul li a:hover {
            color: #ff6600;
        }

        .toggle-btn {
            background: none;
            border: 1px solid #ff6600;
            color: #ff6600;
            padding: 5px 10px;
            border-radius: 5px;
            cursor: pointer;
            transition: background 0.3s;
        }

        .toggle-btn:hover {
            background: #ff6600;
            color: #fff;
        }

        /* ---------- Sections ---------- */
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

        /* ---------- About ---------- */
        #about p {
            text-align: center;
            max-width: 700px;
            margin: auto;
        }

        /* ---------- Portfolio ---------- */
        #portfolio .projects {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
        }

        #portfolio .project {
            border-radius: 12px;
            overflow: hidden;
            box-shadow: 0 2px 8px rgba(0,0,0,0.1);
            transition: transform 0.3s ease;
            position: relative;
            color: white;
        }

        #portfolio .project:hover {
            transform: scale(1.05);
        }

        #portfolio .project img {
            width: 100%;
            display: block;
            border-bottom: 3px solid rgba(255,255,255,0.2);
        }

        #portfolio .project h3 {
            padding: 15px;
            text-align: center;
        }

        /* ---------- كل بطاقة بلون مختلف ---------- */
        #portfolio .project:nth-child(1) {
            background: linear-gradient(135deg, #ff7e5f, #feb47b);
        }

        #portfolio .project:nth-child(2) {
            background: linear-gradient(135deg, #6a11cb, #2575fc);
        }

        #portfolio .project:nth-child(3) {
            background: linear-gradient(135deg, #00b09b, #96c93d);
        }

        #portfolio .project:nth-child(4) {
            background: linear-gradient(135deg, #ff512f, #dd2476);
        }

        #portfolio .project:nth-child(5) {
            background: linear-gradient(135deg, #36d1dc, #5b86e5);
        }

        /* ---------- Download Icon ---------- */
        .download-icon {
            position: absolute;
            bottom: 10px;
            right: 10px;
            background: rgba(0,0,0,0.4);
            color: white;
            padding: 6px 10px;
            border-radius: 50%;
            font-size: 18px;
            cursor: pointer;
            transition: background 0.3s;
        }

        .download-icon:hover {
            background: #ff6600;
        }

        /* ---------- Contact ---------- */
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
        }

        #contact button {
            padding: 10px;
            background-color: #1a1a1a;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-size: 1rem;
        }

        #contact button:hover {
            background-color: #ff6600;
        }

        /* ---------- Footer ---------- */
        footer {
            text-align: center;
            padding: 20px;
            background-color: #1a1a1a;
            color: white;
        }

        /* ---------- Responsive ---------- */
        @media (max-width: 600px) {
            nav ul {
                flex-direction: column;
            }

            nav ul li {
                margin-left: 0;
                margin-top: 10px;
            }
        }
    </style>
</head>
<body>

    <!-- Navbar -->
    <header>
        <nav>
            <div class="logo">Marwane Mellouk</div>
            <ul>
                <li><a href="#about">عنّي</a></li>
                <li><a href="#portfolio">أعمالي</a></li>
                <li><a href="#contact">اتصل بي</a></li>
            </ul>
            <button class="toggle-btn" onclick="toggleDarkMode()">🌙</button>
        </nav>
    </header>

    <!-- About Section -->
    <section id="about">
        <h2>عنّي</h2>
        <p>مرحباً! أنا Marwane Mellouk، مطور ومصمم مواقع شغوف بابتكار تجارب رقمية مميزة. أحب تعلم التقنيات الجديدة وتحويل الأفكار إلى مشاريع ملموسة.</p>
    </section>

    <!-- Portfolio Section -->
    <section id="portfolio">
        <h2>أعمالي</h2>
        <div class="projects">
            <div class="project">
                <img src="IMAGE1.jpg" alt="مشروع 1">
                <h3>مشروع 1</h3>
                <a href="IMAGE1.jpg" download class="download-icon">⬇️</a>
            </div>
            <div class="project">
                <img src="IMAGE2.jpg" alt="مشروع 2">
                <h3>مشروع 2</h3>
                <a href="IMAGE2.jpg" download class="download-icon">⬇️</a>
            </div>
            <div class="project">
                <img src="IMAGE3.jpg" alt="مشروع 3">
                <h3>مشروع 3</h3>
                <a href="IMAGE3.jpg" download class="download-icon">⬇️</a>
            </div>
            <div class="project">
                <img src="IMAGE4.jpg" alt="مشروع 4">
                <h3>مشروع 4</h3>
                <a href="IMAGE4.jpg" download class="download-icon">⬇️</a>
            </div>
            <div class="project">
                <img src="IMAGE5.jpg" alt="مشروع 5">
                <h3>مشروع 5</h3>
                <a href="IMAGE5.jpg" download class="download-icon">⬇️</a>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact">
        <h2>اتصل بي</h2>
        <form>
            <input type="text" placeholder="الاسم" required>
            <input type="email" placeholder="البريد الإلكتروني" required>
            <textarea rows="5" placeholder="رسالتك" required></textarea>
            <button type="submit">أرسل</button>
        </form>
    </section>

    <!-- Footer -->
    <footer>
        &copy; 2025 Marwane Mellouk | جميع الحقوق محفوظة
    </footer>

    <script>
        function toggleDarkMode() {
            document.body.classList.toggle("dark-mode");
            const btn = document.querySelector(".toggle-btn");
            btn.textContent = document.body.classList.contains("dark-mode") ? "☀️" : "🌙";
        }
    </script>
</body>
</html>
