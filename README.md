<!DOCTYPE html>
<html lang="ar">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>قهوة سوداء - بورتفوليو</title>
    <style>
        /* ---------- Reset ---------- */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Arial', sans-serif;
        }

        body {
            line-height: 1.6;
            background-color: #ffe6f0; /* خلفية وردية */
            color: #333;
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
            font-size: 1.8rem;
            font-weight: bold;
            color: #fff;
        }

        nav ul {
            display: flex;
            list-style: none;
        }

        nav ul li {
            margin-left: 20px;
        }

        nav ul li a:hover {
            color: #ff4081; /* لون وردي */
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
            background-color: white;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 2px 8px rgba(0,0,0,0.1);
            transition: transform 0.3s ease;
        }

        #portfolio .project img {
            width: 100%;
            display: block;
        }

        #portfolio .project:hover {
            transform: scale(1.05);
        }

        #portfolio .project h3 {
            padding: 15px;
            text-align: center;
            color: #1a1a1a;
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
            background-color: #ff4081;
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
            <div class="logo">قهوة سوداء</div>
            <ul>
                <li><a href="#about">عنّي</a></li>
                <li><a href="#portfolio">أعمالي</a></li>
                <li><a href="#contact">اتصل بي</a></li>
            </ul>
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
                <img src="https://picsum.photos/400/250?random=1" alt="مشروع 1">
                <h3>مشروع 1</h3>
            </div>
            <div class="project">
                <img src="https://picsum.photos/400/250?random=2" alt="مشروع 2">
                <h3>مشروع 2</h3>
            </div>
            <div class="project">
                <img src="https://picsum.photos/400/250?random=3" alt="مشروع 3">
                <h3>مشروع 3</h3>
            </div>
            <div class="project">
                <img src="https://picsum.photos/400/250?random=4" alt="مشروع 4">
                <h3>مشروع 4</h3>
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
        &copy; 2025 قهوة سوداء | جميع الحقوق محفوظة
    </footer>

</body>
</html>
