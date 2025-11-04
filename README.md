
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
        }

        body {
            line-height: 1.6;
            background-color: #ffe6f0;
            color: #333;
            transition: background 0.5s, color 0.5s;
        }

        a {
            text-decoration: none;
            color: inherit;
        }

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
            color: #ff4081;
        }

        .dark-mode {
            background-color: #121212;
            color: #f5f5f5;
        }

        .dark-mode header {
            background-color: #000;
        }

        .dark-mode footer {
            background-color: #000;
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

        .dark-mode h2 {
            color: #fff;
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

        .dark-mode #portfolio .project {
            background-color: #1e1e1e;
            box-shadow: 0 2px 8px rgba(255,255,255,0.1);
        }

        #portfolio .project img {
            width: 100%;
            display: block;
            height: 250px;
            object-fit: cover;
        }

        #portfolio .project:hover {
            transform: scale(1.05);
        }

        #portfolio .project h3 {
            padding: 15px;
            text-align: center;
            color: #1a1a1a;
        }

        .dark-mode #portfolio .project h3 {
            color: #fff;
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

        footer {
            text-align: center;
            padding: 20px;
            background-color: #1a1a1a;
            color: white;
        }

        #darkToggle {
            background: none;
            border: 1px solid #fff;
            border-radius: 50%;
            width: 40px;
            height: 40px;
            color: #fff;
            cursor: pointer;
            font-size: 1.2rem;
            transition: 0.3s;
        }

        #darkToggle:hover {
            background-color: #ff4081;
            border-color: #ff4081;
        }

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
            <button id="darkToggle">🌙</button>
        </nav>
    </header>

    <!-- About -->
    <section id="about">
        <h2>عنّي</h2>
        <p>مرحباً! أنا Marwane Mellouk، مطور ومصمم مواقع شغوف بابتكار تجارب رقمية مميزة. أحب تعلم التقنيات الجديدة وتحويل الأفكار إلى مشاريع ملموسة.</p>
    </section>

    <!-- Portfolio -->
    <section id="portfolio">
        <h2>أعمالي</h2>
        <div class="projects">
            <div class="project">
                <img src="IMAGE1.jpg" alt="مشروع 1">
                <h3>مشروع 1</h3>
            </div>
            <div class="project">
                <img src="IMAGE2.jpg" alt="مشروع 2">
                <h3>مشروع 2</h3>
            </div>
            <div class="project">
                <img src="IMAGE3.jpg" alt="مشروع 3">
                <h3>مشروع 3</h3>
            </div>
            <div class="project">
                <img src="IMAGE4.jpg" alt="مشروع 4">
                <h3>مشروع 4</h3>
            </div>
            <div class="project">
                <img src="IMAGE5.jpg" alt="مشروع 5">
                <h3>مشروع 5</h3>
            </div>
        </div>
    </section>

    <!-- Contact -->
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

    <script>
        const toggle = document.getElementById('darkToggle');
        toggle.onclick = () => {
            document.body.classList.toggle('dark-mode');
        };
    </script>

</body>
</html>
