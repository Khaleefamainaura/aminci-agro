<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Aminci Agro Service Enterprise</title>
    <style>
        /* RESET & FONT */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: Arial, Helvetica, sans-serif;
        }

        body {
            scroll-behavior: smooth;
            background: #f4f7f3;
            color: #333;
        }

        /* NAVBAR */
        header {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            background: #14532d;
            color: white;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 15px 40px;
            z-index: 1000;
        }

        header h1 {
            font-size: 22px;
        }

        nav a {
            color: white;
            text-decoration: none;
            margin-left: 20px;
            font-weight: bold;
        }

        nav a:hover {
            color: #bbf7d0;
        }

        /* HERO */
        section {
            padding: 100px 10%;
            min-height: 100vh;
            scroll-margin-top: 80px;
        }

        .hero {
            background: url("https://images.unsplash.com/photo-1500382017468-9049fed747ef") center/cover no-repeat;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            color: white;
            position: relative;
        }

        .hero::after {
            content: "";
            position: absolute;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.5);
            top: 0;
            left: 0;
        }

        .hero h2 {
            position: relative;
            font-size: 40px;
            z-index: 2;
        }

        /* ABOUT */
        #about h2,
        #services h2,
        #blog h2,
        #contact h2 {
            color: #14532d;
            margin-bottom: 30px;
            text-align: center;
        }

        #about p {
            margin-bottom: 15px;
            line-height: 1.6;
        }

        /* SERVICES */
        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 30px;
        }

        .card {
            background: white;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            transition: 0.3s;
        }

        .card:hover {
            transform: translateY(-5px);
        }

        .card img {
            width: 100%;
            height: 180px;
            object-fit: cover;
        }

        .card-content {
            padding: 20px;
        }

        .card-content h3 {
            margin-bottom: 10px;
            color: #14532d;
        }

        .card-content p {
            font-size: 14px;
            margin-bottom: 10px;
        }

        /* BLOG */
        .blog-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 30px;
        }

        .blog-card {
            background: white;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            transition: 0.3s;
            cursor: pointer;
        }

        .blog-card:hover {
            transform: translateY(-5px);
        }

        .blog-card img {
            width: 100%;
            height: 180px;
            object-fit: cover;
        }

        .blog-content {
            padding: 20px;
        }

        .blog-content h3 {
            margin-bottom: 10px;
            color: #14532d;
        }

        .blog-content small {
            color: gray;
        }

        .blog-content p {
            margin: 10px 0 15px;
            font-size: 14px;
        }

        .blog-content a {
            text-decoration: none;
            background: #16a34a;
            color: white;
            padding: 8px 15px;
            border-radius: 5px;
            font-size: 14px;
            transition: 0.3s;
        }

        .blog-content a:hover {
            background: #14532d;
        }

        /* MODAL */
        .modal {
            display: none;
            position: fixed;
            z-index: 2000;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            overflow: auto;
            background-color: rgba(0, 0, 0, 0.7);
        }

        .modal-content {
            background: white;
            margin: 10% auto;
            padding: 20px;
            border-radius: 10px;
            max-width: 600px;
            position: relative;
        }

        .close {
            color: #14532d;
            position: absolute;
            top: 10px;
            right: 20px;
            font-size: 28px;
            font-weight: bold;
            cursor: pointer;
        }

        /* CONTACT */
        form {
            background: white;
            padding: 30px;
            border-radius: 10px;
            max-width: 600px;
            margin: auto;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }

        form label {
            display: block;
            margin-bottom: 8px;
            font-weight: bold;
        }

        form input,
        form textarea {
            width: 100%;
            padding: 10px;
            margin-bottom: 20px;
            border: 1px solid #ccc;
            border-radius: 5px;
        }

        form button {
            background: #16a34a;
            color: white;
            padding: 10px 20px;
            border: none;
            border-radius: 5px;
            font-size: 16px;
            cursor: pointer;
        }

        form button:hover {
            background: #14532d;
        }

        /* FOOTER */
        footer {
            background: #14532d;
            color: white;
            text-align: center;
            padding: 20px;
            margin-top: 50px;
        }

        /* RESPONSIVE */
        @media(max-width:768px) {
            header {
                flex-direction: column;
                align-items: flex-start;
            }

            nav {
                margin-top: 10px;
            }

            nav a {
                margin-left: 0;
                margin-right: 15px;
                display: inline-block;
                margin-bottom: 5px;
            }

            .hero h2 {
                font-size: 28px;
                padding: 0 10px;
            }
        }

        @media(max-width:480px) {

            .card img,
            .blog-card img {
                height: 160px;
            }

            .card-content h3,
            .blog-content h3 {
                font-size: 16px;
            }

            .card-content p,
            .blog-content p {
                font-size: 13px;
            }
        }
    </style>
</head>

<body>

    <header>
        <h1>Aminci Agro Service Enterprise</h1>
        <nav>
            <a href="#home">Home</a>
            <a href="#about">About</a>
            <a href="#services">Services</a>
            <a href="#blog">Blog</a>
            <a href="#contact">Contact</a>
        </nav>
    </header>

    <section id="home" class="hero">
        <h2>Welcome to Aminci Agro Service Enterprise</h2>
    </section>

    <section id="about">
        <h2>About Us</h2>
        <p>Aminci Agro Service Enterprise provides quality agricultural services and products. Our mission is to empower
            agricultural growth through sustainable and innovative solutions.</p>
        <p>Founded in 2020, we offer crop consulting, farm management, and delivery of agro products.</p>
    </section>

    <section id="services">
        <h2>Our Services</h2>
        <div class="services-grid">
            <div class="card">
                <img src="https://images.unsplash.com/photo-1501004318641-b39e6451bec6" alt="Service 1">
                <div class="card-content">
                    <h3>Crop Consulting</h3>
                    <p>Expert advice to maximize crop yield and efficiency.</p>
                </div>
            </div>
            <div class="card">
                <img src="https://images.unsplash.com/photo-1464226184884-fa280b87c399" alt="Service 2">
                <div class="card-content">
                    <h3>Farm Management</h3>
                    <p>Professional farm planning and management solutions.</p>
                </div>
            </div>
            <div class="card">
                <img src="https://images.unsplash.com/photo-1500937386664-56d1dfef3854" alt="Service 3">
                <div class="card-content">
                    <h3>Agro Products</h3>
                    <p>Quality agro products delivered to your farm efficiently.</p>
                </div>
            </div>
        </div>
    </section>

    <section id="blog">
        <h2>Our Latest Blog Updates</h2>
        <div class="blog-grid">
            <div class="blog-card"
                onclick="openModal('Crafting Captivating Headlines','Learn how to create headlines that grab attention and improve engagement.')">
                <img src="https://images.unsplash.com/photo-1492496913980-501348b61469">
                <div class="blog-content">
                    <h3>Crafting Captivating Headlines</h3>
                    <small>February 19, 2026</small>
                    <a href="javascript:void(0)">Read More</a>
                </div>
            </div>

            <div class="blog-card"
                onclick="openModal('The Art of Drawing Readers In','Discover techniques for writing introductions that keep readers engaged.')">
                <img src="https://images.unsplash.com/photo-1464226184884-fa280b87c399">
                <div class="blog-content">
                    <h3>The Art of Drawing Readers In</h3>
                    <small>February 19, 2026</small>
                    <a href="javascript:void(0)">Read More</a>
                </div>
            </div>

            <div class="blog-card"
                onclick="openModal('Mastering the First Impression','Make a powerful first impression with strong opening paragraphs.')">
                <img src="https://images.unsplash.com/photo-1501004318641-b39e6451bec6">
                <div class="blog-content">
                    <h3>Mastering the First Impression</h3>
                    <small>February 19, 2026</small>
                    <a href="javascript:void(0)">Read More</a>
                </div>
            </div>
        </div>
    </section>

    <!-- MODAL -->
    <div id="modal" class="modal">
        <div class="modal-content">
            <span class="close" onclick="closeModal()">&times;</span>
            <h3 id="modal-title"></h3>
            <p id="modal-body"></p>
        </div>
    </div>

    <section id="contact">
        <h2>Contact Us</h2>
        <form action="khaleefamainaura@gmail.com" method="POST">
            <label for="name">Name</label>
            <input type="text" id="name" name="name" placeholder="Your name" required>
            <label for="email">Email</label>
            <input type="email" id="email" name="email" placeholder="Your email" required>
            <label for="message">Message</label>
            <textarea id="message" name="message" rows="6" placeholder="Your message" required></textarea>
            <button type="submit">Send Message</button>
        </form>
    </section>

    <footer>
        © 2026 Aminci Agro Service Enterprise | All Rights Reserved
    </footer>

    <script>
        // Blog Modal
        function openModal(title, body) {
            document.getElementById('modal-title').innerText = title;
            document.getElementById('modal-body').innerText = body;
            document.getElementById('modal').style.display = 'block';
        }
        function closeModal() {
            document.getElementById('modal').style.display = 'none';
        }
        window.onclick = function (event) {
            if (event.target == document.getElementById('modal')) {
                closeModal();
            }
        }
    </script>

</body>

</html>
