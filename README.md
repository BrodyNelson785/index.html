
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Tony's Corner Pizzeria - Authentic Italian Pizza</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Arial', sans-serif;
            line-height: 1.6;
            color: #333;
            overflow-x: hidden;
        }

        .hero {
            height: 100vh;
            background: linear-gradient(45deg, #ff6b35, #f7931e, #ff6b35);
            background-size: 400% 400%;
            animation: gradientShift 8s ease infinite;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            color: white;
            position: relative;
        }

        @keyframes gradientShift {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: rgba(0,0,0,0.3);
        }

        .hero-content {
            position: relative;
            z-index: 2;
            transform: translateY(0);
            animation: float 6s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-20px); }
        }

        .hero h1 {
            font-size: 4rem;
            margin-bottom: 1rem;
            text-shadow: 3px 3px 6px rgba(0,0,0,0.5);
            font-weight: bold;
        }

        .hero p {
            font-size: 1.5rem;
            margin-bottom: 2rem;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.5);
        }

        .cta-button {
            display: inline-block;
            padding: 15px 40px;
            background: #fff;
            color: #ff6b35;
            text-decoration: none;
            border-radius: 50px;
            font-weight: bold;
            font-size: 1.2rem;
            transition: all 0.3s ease;
            box-shadow: 0 8px 25px rgba(0,0,0,0.2);
        }

        .cta-button:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 35px rgba(0,0,0,0.3);
            background: #f8f8f8;
        }

        nav {
            position: fixed;
            top: 0;
            width: 100%;
            background: rgba(255,255,255,0.95);
            backdrop-filter: blur(10px);
            padding: 1rem 0;
            z-index: 1000;
            transition: all 0.3s ease;
        }

        nav.scrolled {
            background: rgba(255,255,255,0.98);
            box-shadow: 0 2px 20px rgba(0,0,0,0.1);
        }

        .nav-container {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 0 2rem;
        }

        .logo {
            font-size: 1.8rem;
            font-weight: bold;
            color: #ff6b35;
        }

        .nav-links {
            display: flex;
            list-style: none;
            gap: 2rem;
        }

        .nav-links a {
            text-decoration: none;
            color: #333;
            font-weight: 500;
            transition: color 0.3s ease;
            position: relative;
        }

        .nav-links a:hover {
            color: #ff6b35;
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background: #ff6b35;
            transition: width 0.3s ease;
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        .section {
            padding: 6rem 2rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        .section h2 {
            text-align: center;
            font-size: 3rem;
            margin-bottom: 3rem;
            color: #333;
            position: relative;
        }

        .section h2::after {
            content: '';
            display: block;
            width: 80px;
            height: 4px;
            background: linear-gradient(45deg, #ff6b35, #f7931e);
            margin: 1rem auto;
            border-radius: 2px;
        }

        .menu-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 2rem;
        }

        .menu-item {
            background: white;
            border-radius: 20px;
            padding: 2rem;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .menu-item::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(45deg, rgba(255,107,53,0.1), rgba(247,147,30,0.1));
            transition: left 0.5s ease;
        }

        .menu-item:hover::before {
            left: 0;
        }

        .menu-item:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(0,0,0,0.15);
        }

        .menu-item h3 {
            color: #ff6b35;
            font-size: 1.5rem;
            margin-bottom: 1rem;
            position: relative;
        }

        .menu-item p {
            color: #666;
            margin-bottom: 1rem;
            position: relative;
        }

        .price {
            font-size: 1.3rem;
            font-weight: bold;
            color: #333;
            position: relative;
        }

        .about {
            background: linear-gradient(135deg, #f8f9fa, #e9ecef);
            border-radius: 30px;
            padding: 4rem;
            margin: 4rem 0;
        }

        .about-content {
            text-align: center;
            max-width: 800px;
            margin: 0 auto;
        }

        .about p {
            font-size: 1.2rem;
            color: #555;
            margin-bottom: 2rem;
        }

        .contact {
            background: #333;
            color: white;
            border-radius: 30px;
            padding: 4rem;
            text-align: center;
        }

        .contact h2 {
            color: white;
        }

        .contact-info {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            margin-top: 2rem;
        }

        .contact-item {
            padding: 1.5rem;
            background: rgba(255,255,255,0.1);
            border-radius: 15px;
            transition: all 0.3s ease;
        }

        .contact-item:hover {
            background: rgba(255,255,255,0.2);
            transform: translateY(-5px);
        }

        .contact-item h3 {
            color: #ff6b35;
            margin-bottom: 1rem;
        }

        .hours {
            background: linear-gradient(45deg, #ff6b35, #f7931e);
            color: white;
            border-radius: 30px;
            padding: 4rem;
            margin: 4rem 0;
            text-align: center;
        }

        .hours h2 {
            color: white;
        }

        .hours-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 1rem;
            margin-top: 2rem;
        }

        .hours-item {
            padding: 1rem;
            background: rgba(255,255,255,0.2);
            border-radius: 10px;
            backdrop-filter: blur(5px);
        }

        footer {
            background: #222;
            color: white;
            text-align: center;
            padding: 2rem;
        }

        .pizza-emoji {
            font-size: 2rem;
            display: inline-block;
            animation: spin 3s linear infinite;
        }

        @keyframes spin {
            from { transform: rotate(0deg); }
            to { transform: rotate(360deg); }
        }

        @media (max-width: 768px) {
            .hero h1 {
                font-size: 2.5rem;
            }
            
            .hero p {
                font-size: 1.2rem;
            }
            
            .nav-links {
                display: none;
            }
            
            .section {
                padding: 4rem 1rem;
            }
            
            .menu-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <nav id="navbar">
        <div class="nav-container">
            <div class="logo">🍕 Tony's Corner</div>
            <ul class="nav-links">
                <li><a href="#home">Home</a></li>
                <li><a href="#menu">Menu</a></li>
                <li><a href="#about">About</a></li>
                <li><a href="#hours">Hours</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </div>
    </nav>

    <section id="home" class="hero">
        <div class="hero-content">
            <h1>Tony's Corner Pizzeria</h1>
            <p>Authentic Italian Pizza Since 1952</p>
            <a href="#menu" class="cta-button">View Our Menu</a>
        </div>
    </section>

    <section id="menu" class="section">
        <h2>Our Delicious Menu <span class="pizza-emoji">🍕</span></h2>
        <div class="menu-grid">
            <div class="menu-item">
                <h3>Margherita Classic</h3>
                <p>Fresh mozzarella, San Marzano tomatoes, basil, extra virgin olive oil</p>
                <div class="price">$16.99</div>
            </div>
            <div class="menu-item">
                <h3>Tony's Supreme</h3>
                <p>Pepperoni, Italian sausage, mushrooms, bell peppers, onions, black olives</p>
                <div class="price">$22.99</div>
            </div>
            <div class="menu-item">
                <h3>Meat Lovers Deluxe</h3>
                <p>Pepperoni, sausage, bacon, ham, ground beef, mozzarella</p>
                <div class="price">$24.99</div>
            </div>
            <div class="menu-item">
                <h3>Mediterranean Veggie</h3>
                <p>Roasted eggplant, zucchini, red peppers, feta cheese, olives, herbs</p>
                <div class="price">$19.99</div>
            </div>
            <div class="menu-item">
                <h3>BBQ Chicken Ranch</h3>
                <p>Grilled chicken, BBQ sauce, red onions, cilantro, ranch drizzle</p>
                <div class="price">$21.99</div>
            </div>
            <div class="menu-item">
                <h3>Four Cheese Special</h3>
                <p>Mozzarella, parmesan, gorgonzola, ricotta, garlic, herbs</p>
                <div class="price">$20.99</div>
            </div>
        </div>
    </section>

    <section id="about" class="section">
        <div class="about">
            <div class="about-content">
                <h2>Our Story</h2>
                <p>Founded in 1952 by Antonio "Tony" Marcelli, Tony's Corner Pizzeria has been serving authentic Italian pizza to our community for over 70 years. What started as a small family business has grown into a beloved local institution.</p>
                <p>We use only the finest ingredients: San Marzano tomatoes imported from Italy, fresh mozzarella made daily, and our secret family recipe dough that's been passed down through three generations.</p>
                <p>Every pizza is hand-tossed and baked in our original brick oven, ensuring that perfect crispy crust and melted cheese combination that keeps our customers coming back.</p>
            </div>
        </div>
    </section>

    <section id="hours" class="hours">
        <h2>Hours & Location</h2>
        <div class="hours-grid">
            <div class="hours-item">
                <strong>Monday - Thursday</strong><br>
                11:00 AM - 10:00 PM
            </div>
            <div class="hours-item">
                <strong>Friday - Saturday</strong><br>
                11:00 AM - 11:00 PM
            </div>
            <div class="hours-item">
                <strong>Sunday</strong><br>
                12:00 PM - 9:00 PM
            </div>
        </div>
    </section>

    <section id="contact" class="section">
        <div class="contact">
            <h2>Visit Us Today!</h2>
            <div class="contact-info">
                <div class="contact-item">
                    <h3>📍 Address</h3>
                    <p>1247 Main Street<br>Little Italy District<br>Your City, ST 12345</p>
                </div>
                <div class="contact-item">
                    <h3>📞 Phone</h3>
                    <p>(555) 123-PIZZA<br>(555) 123-7499</p>
                </div>
                <div class="contact-item">
                    <h3>🚚 Delivery</h3>
                    <p>Free delivery within 5 miles<br>Order online or call ahead</p>
                </div>
                <div class="contact-item">
                    <h3>🅿️ Parking</h3>
                    <p>Free parking available<br>Street and lot parking</p>
                </div>
            </div>
        </div>
    </section>

    <footer>
        <p>&copy; 2025 Tony's Corner Pizzeria. All rights reserved. | Family owned and operated since 1952</p>
    </footer>

    <script>
        // Smooth scrolling for navigation links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({
                        behavior: 'smooth',
                        block: 'start'
                    });
                }
            });
        });

        // Navbar scroll effect
        window.addEventListener('scroll', function() {
            const navbar = document.getElementById('navbar');
            if (window.scrollY > 100) {
                navbar.classList.add('scrolled');
            } else {
                navbar.classList.remove('scrolled');
            }
        });

        // Menu item animation on scroll
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver(function(entries) {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = '0';
                    entry.target.style.transform = 'translateY(30px)';
                    entry.target.style.transition = 'all 0.6s ease';
                    
                    setTimeout(() => {
                        entry.target.style.opacity = '1';
                        entry.target.style.transform = 'translateY(0)';
                    }, 100);
                }
            });
        }, observerOptions);

        document.querySelectorAll('.menu-item').forEach(item => {
            observer.observe(item);
        });
    </script>
</body>
</html>
