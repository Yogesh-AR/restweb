# Ex.07 Restaurant Website
## Date:06.10.2025

## AIM:
To develop a static Restaurant website to display the food items and services provided by them.

## DESIGN STEPS:

### Step 1:
Requirement collection.

### Step 2:
Creating the layout using HTML and CSS.

### Step 3:
Updating the sample content.

### Step 4:
Choose the appropriate style and color scheme.

### Step 5:
Validate the layout in various browsers.

### Step 6:
Validate the HTML code.

### Step 7:
Publish the website in the given URL.

## PROGRAM:

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sakura Garden | Authentic Japanese Cuisine</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            line-height: 1.6;
            color: #333;
            background-color: #fefefe;
        }
        
        .container {
            width: 90%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px 0;
        }
        
        /* Header */
        header {
            background: #fff;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
        }
        
        .header-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 15px 0;
        }
        
        .logo {
            font-size: 1.8rem;
            font-weight: 700;
            color: #c62e2a;
        }
        
        .logo span {
            color: #f8b500;
        }
        
        nav ul {
            display: flex;
            list-style: none;
        }
        
        nav ul li {
            margin-left: 25px;
        }
        
        nav ul li a {
            text-decoration: none;
            color: #333;
            font-weight: 500;
            transition: color 0.3s;
        }
        
        nav ul li a:hover {
            color: #c62e2a;
        }
        
        .mobile-menu {
            display: none;
            font-size: 1.5rem;
            cursor: pointer;
        }
        
        /* Hero Section */
        .hero {
            background: linear-gradient(rgba(0,0,0,0.6), rgba(0,0,0,0.6)), 
                        url('https://images.unsplash.com/photo-1547592166-23ac45744acd?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1471&q=80') no-repeat center center/cover;
            height: 100vh;
            display: flex;
            align-items: center;
            text-align: center;
            color: white;
            margin-top: 70px;
        }
        
        .hero-content {
            max-width: 800px;
            margin: 0 auto;
            padding: 0 20px;
        }
        
        .hero h1 {
            font-size: 3rem;
            margin-bottom: 20px;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.5);
        }
        
        .hero p {
            font-size: 1.2rem;
            margin-bottom: 30px;
            text-shadow: 1px 1px 2px rgba(0,0,0,0.5);
        }
        
        .btn {
            display: inline-block;
            padding: 12px 30px;
            background: #c62e2a;
            color: white;
            text-decoration: none;
            border-radius: 4px;
            font-weight: 600;
            transition: all 0.3s;
            border: none;
            cursor: pointer;
        }
        
        .btn:hover {
            background: #a02522;
            transform: translateY(-2px);
        }
        
        /* About Section */
        .about {
            padding: 80px 0;
            background: #f9f9f9;
        }
        
        .section-title {
            text-align: center;
            margin-bottom: 50px;
        }
        
        .section-title h2 {
            font-size: 2.5rem;
            margin-bottom: 15px;
            color: #333;
        }
        
        .section-title p {
            color: #777;
            max-width: 600px;
            margin: 0 auto;
        }
        
        .about-content {
            display: flex;
            align-items: center;
            gap: 50px;
        }
        
        .about-img {
            flex: 1;
            border-radius: 8px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }
        
        .about-img img {
            width: 100%;
            height: auto;
            display: block;
        }
        
        .about-text {
            flex: 1;
        }
        
        .about-text h3 {
            font-size: 2rem;
            margin-bottom: 20px;
            color: #333;
        }
        
        .about-text p {
            margin-bottom: 20px;
            color: #555;
        }
        
        /* Menu Section */
        .menu {
            padding: 80px 0;
        }
        
        .menu-categories {
            display: flex;
            justify-content: center;
            margin-bottom: 40px;
            flex-wrap: wrap;
            gap: 10px;
        }
        
        .category-btn {
            padding: 10px 20px;
            background: white;
            border: 1px solid #ddd;
            border-radius: 30px;
            cursor: pointer;
            transition: all 0.3s;
        }
        
        .category-btn.active, .category-btn:hover {
            background: #c62e2a;
            color: white;
            border-color: #c62e2a;
        }
        
        .menu-items {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 30px;
        }
        
        .menu-item {
            background: white;
            border-radius: 8px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0,0,0,0.05);
            transition: transform 0.3s;
        }
        
        .menu-item:hover {
            transform: translateY(-10px);
        }
        
        .menu-item-img {
            height: 200px;
            overflow: hidden;
        }
        
        .menu-item-img img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.5s;
        }
        
        .menu-item:hover .menu-item-img img {
            transform: scale(1.1);
        }
        
        .menu-item-content {
            padding: 20px;
        }
        
        .menu-item-header {
            display: flex;
            justify-content: space-between;
            margin-bottom: 10px;
        }
        
        .menu-item-title {
            font-size: 1.2rem;
            font-weight: 600;
        }
        
        .menu-item-price {
            color: #c62e2a;
            font-weight: 700;
        }
        
        .menu-item-desc {
            color: #777;
            font-size: 0.9rem;
        }
        
        /* Contact Section */
        .contact {
            padding: 80px 0;
            background: #f9f9f9;
        }
        
        .contact-content {
            display: flex;
            gap: 50px;
        }
        
        .contact-info {
            flex: 1;
        }
        
        .contact-info-item {
            display: flex;
            margin-bottom: 30px;
        }
        
        .contact-icon {
            font-size: 1.5rem;
            color: #c62e2a;
            margin-right: 15px;
        }
        
        .contact-details h3 {
            margin-bottom: 5px;
        }
        
        .contact-details p {
            color: #555;
        }
        
        .contact-form {
            flex: 1;
        }
        
        .form-group {
            margin-bottom: 20px;
        }
        
        .form-control {
            width: 100%;
            padding: 12px 15px;
            border: 1px solid #ddd;
            border-radius: 4px;
            font-family: inherit;
        }
        
        textarea.form-control {
            min-height: 150px;
            resize: vertical;
        }
        
        /* Footer */
        footer {
            background: #2c2c2c;
            color: white;
            padding: 60px 0 20px;
        }
        
        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 40px;
            margin-bottom: 40px;
        }
        
        .footer-col h3 {
            font-size: 1.2rem;
            margin-bottom: 20px;
            position: relative;
            padding-bottom: 10px;
        }
        
        .footer-col h3::after {
            content: '';
            position: absolute;
            left: 0;
            bottom: 0;
            width: 50px;
            height: 2px;
            background: #c62e2a;
        }
        
        .footer-col p {
            color: #bbb;
            margin-bottom: 15px;
        }
        
        .social-links {
            display: flex;
            gap: 15px;
        }
        
        .social-links a {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 40px;
            height: 40px;
            background: rgba(255,255,255,0.1);
            border-radius: 50%;
            transition: background 0.3s;
        }
        
        .social-links a:hover {
            background: #c62e2a;
        }
        
        .footer-links li {
            margin-bottom: 10px;
        }
        
        .footer-links a {
            color: #bbb;
            text-decoration: none;
            transition: color 0.3s;
        }
        
        .footer-links a:hover {
            color: #c62e2a;
        }
        
        .copyright {
            text-align: center;
            padding-top: 20px;
            border-top: 1px solid rgba(255,255,255,0.1);
            color: #bbb;
            font-size: 0.9rem;
        }
        
        /* Responsive */
        @media (max-width: 768px) {
            .mobile-menu {
                display: block;
            }
            
            nav {
                position: fixed;
                top: 70px;
                left: 0;
                width: 100%;
                background: white;
                box-shadow: 0 5px 10px rgba(0,0,0,0.1);
                transform: translateY(-150%);
                transition: transform 0.3s;
                opacity: 0;
            }
            
            nav.active {
                transform: translateY(0);
                opacity: 1;
            }
            
            nav ul {
                flex-direction: column;
                padding: 20px;
            }
            
            nav ul li {
                margin: 0 0 15px 0;
            }
            
            .hero h1 {
                font-size: 2.2rem;
            }
            
            .about-content {
                flex-direction: column;
            }
            
            .contact-content {
                flex-direction: column;
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <div class="container header-container">
            <a href="#" class="logo">Sakura <span>Garden</span></a>
            <div class="mobile-menu">
                <i class="fas fa-bars"></i>
            </div>
            <nav>
                <ul>
                    <li><a href="#home">Home</a></li>
                    <li><a href="#about">About</a></li>
                    <li><a href="#menu">Menu</a></li>
                    <li><a href="#contact">Contact</a></li>
                </ul>
            </nav>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero" id="home">
        <div class="container hero-content">
            <h1>Authentic Japanese Cuisine</h1>
            <p>Experience the delicate flavors of Japan with our traditional dishes prepared by master chefs using the freshest ingredients.</p>
            <a href="#menu" class="btn">View Our Menu</a>
        </div>
    </section>

    <!-- About Section -->
    <section class="about" id="about">
        <div class="container">
            <div class="section-title">
                <h2>Our Story</h2>
                <p>Discover the tradition and passion behind Sakura Garden</p>
            </div>
            <div class="about-content">
                <div class="about-img">
                    <img src="https://images.unsplash.com/photo-1549451371-64aa98a6f660?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1470&q=80" alt="Restaurant Interior">
                </div>
                <div class="about-text">
                    <h3>Traditional Japanese Dining</h3>
                    <p>Founded in 2005, Sakura Garden brings the authentic taste of Japan to your table. Our chefs have trained in Tokyo and Kyoto, mastering the art of Japanese cuisine.</p>
                    <p>We source the finest ingredients, from premium sushi-grade fish to organic vegetables, ensuring every dish meets our high standards of quality and flavor.</p>
                    <a href="#contact" class="btn">Visit Us</a>
                </div>
            </div>
        </div>
    </section>

    <!-- Menu Section -->
    <section class="menu" id="menu">
        <div class="container">
            <div class="section-title">
                <h2>Our Menu</h2>
                <p>Explore our selection of authentic Japanese dishes</p>
            </div>
            <div class="menu-categories">
                <button class="category-btn active" data-category="all">All</button>
                <button class="category-btn" data-category="sushi">Sushi</button>
                <button class="category-btn" data-category="ramen">Ramen</button>
                <button class="category-btn" data-category="appetizers">Appetizers</button>
            </div>
            <div class="menu-items">
                <!-- Sushi Items -->
                <div class="menu-item" data-category="sushi">
                    <div class="menu-item-img">
                        <img src="https://images.unsplash.com/photo-1579584425555-c3ce17fd4351?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1470&q=80" alt="Salmon Sushi">
                    </div>
                    <div class="menu-item-content">
                        <div class="menu-item-header">
                            <h3 class="menu-item-title">Salmon Nigiri</h3>
                            <span class="menu-item-price">$12.99</span>
                        </div>
                        <p class="menu-item-desc">Fresh salmon slices over seasoned sushi rice</p>
                    </div>
                </div>
                
                <div class="menu-item" data-category="sushi">
                    <div class="menu-item-img">
                        <img src="https://images.unsplash.com/photo-1563612116625-3012372fccce?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1480&q=80" alt="Tuna Roll">
                    </div>
                    <div class="menu-item-content">
                        <div class="menu-item-header">
                            <h3 class="menu-item-title">Spicy Tuna Roll</h3>
                            <span class="menu-item-price">$14.99</span>
                        </div>
                        <p class="menu-item-desc">Tuna mixed with spicy mayo, cucumber, and avocado</p>
                    </div>
                </div>
                
                <!-- Ramen Items -->
                <div class="menu-item" data-category="ramen">
                    <div class="menu-item-img">
                        <img src="https://images.unsplash.com/photo-1569718212165-3a8278d5f624?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1480&q=80" alt="Tonkotsu Ramen">
                    </div>
                    <div class="menu-item-content">
                        <div class="menu-item-header">
                            <h3 class="menu-item-title">Tonkotsu Ramen</h3>
                            <span class="menu-item-price">$15.99</span>
                        </div>
                        <p class="menu-item-desc">Rich pork bone broth with chashu pork and noodles</p>
                    </div>
                </div>
                
                <div class="menu-item" data-category="ramen">
                    <div class="menu-item-img">
                        <img src="https://images.unsplash.com/photo-1557872943-16a5ac26447e?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1412&q=80" alt="Miso Ramen">
                    </div>
                    <div class="menu-item-content">
                        <div class="menu-item-header">
                            <h3 class="menu-item-title">Miso Ramen</h3>
                            <span class="menu-item-price">$14.99</span>
                        </div>
                        <p class="menu-item-desc">Savory miso broth with corn, bean sprouts, and pork</p>
                    </div>
                </div>
                
                <!-- Appetizers -->
                <div class="menu-item" data-category="appetizers">
                    <div class="menu-item-img">
                        <img src="https://images.unsplash.com/photo-1583623025817-18019083d6a3?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1374&q=80" alt="Gyoza">
                    </div>
                    <div class="menu-item-content">
                        <div class="menu-item-header">
                            <h3 class="menu-item-title">Gyoza</h3>
                            <span class="menu-item-price">$8.99</span>
                        </div>
                        <p class="menu-item-desc">Pan-fried pork and vegetable dumplings</p>
                    </div>
                </div>
                
                <div class="menu-item" data-category="appetizers">
                    <div class="menu-item-img">
                        <img src="https://images.unsplash.com/photo-1631452180519-c014fe946bc7?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1374&q=80" alt="Edamame">
                    </div>
                    <div class="menu-item-content">
                        <div class="menu-item-header">
                            <h3 class="menu-item-title">Edamame</h3>
                            <span class="menu-item-price">$6.99</span>
                        </div>
                        <p class="menu-item-desc">Steamed young soybeans with sea salt</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section class="contact" id="contact">
        <div class="container">
            <div class="section-title">
                <h2>Contact Us</h2>
                <p>We'd love to hear from you. Make a reservation or ask any questions.</p>
            </div>
            <div class="contact-content">
                <div class="contact-info">
                    <div class="contact-info-item">
                        <div class="contact-icon">
                            <i class="fas fa-map-marker-alt"></i>
                        </div>
                        <div class="contact-details">
                            <h3>Location</h3>
                            <p>123 Sakura Street, Tokyo District<br>New York, NY 10001</p>
                        </div>
                    </div>
                    <div class="contact-info-item">
                        <div class="contact-icon">
                            <i class="fas fa-phone"></i>
                        </div>
                        <div class="contact-details">
                            <h3>Phone</h3>
                            <p>(555) 123-4567</p>
                        </div>
                    </div>
                    <div class="contact-info-item">
                        <div class="contact-icon">
                            <i class="fas fa-envelope"></i>
                        </div>
                        <div class="contact-details">
                            <h3>Email</h3>
                            <p>info@sakuragarden.com</p>
                        </div>
                    </div>
                    <div class="contact-info-item">
                        <div class="contact-icon">
                            <i class="fas fa-clock"></i>
                        </div>
                        <div class="contact-details">
                            <h3>Opening Hours</h3>
                            <p>Monday - Sunday: 11:00 AM - 10:00 PM</p>
                        </div>
                    </div>
                </div>
                <div class="contact-form">
                    <form>
                        <div class="form-group">
                            <input type="text" class="form-control" placeholder="Your Name" required>
                        </div>
                        <div class="form-group">
                            <input type="email" class="form-control" placeholder="Your Email" required>
                        </div>
                        <div class="form-group">
                            <input type="text" class="form-control" placeholder="Subject">
                        </div>
                        <div class="form-group">
                            <textarea class="form-control" placeholder="Your Message" required></textarea>
                        </div>
                        <button type="submit" class="btn">Send Message</button>
                    </form>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="footer-col">
                    <h3>Sakura Garden</h3>
                    <p>Authentic Japanese cuisine served with passion and tradition since 2005.</p>
                    <div class="social-links">
                        <a href="#"><i class="fab fa-facebook-f"></i></a>
                        <a href="#"><i class="fab fa-twitter"></i></a>
                        <a href="#"><i class="fab fa-instagram"></i></a>
                    </div>
                </div>
                <div class="footer-col">
                    <h3>Quick Links</h3>
                    <ul class="footer-links">
                        <li><a href="#home">Home</a></li>
                        <li><a href="#about">About</a></li>
                        <li><a href="#menu">Menu</a></li>
                        <li><a href="#contact">Contact</a></li>
                    </ul>
                </div>
                <div class="footer-col">
                    <h3>Contact Info</h3>
                    <ul class="footer-links">
                        <li><i class="fas fa-map-marker-alt"></i> 123 Sakura Street, NY 10001</li>
                        <li><i class="fas fa-phone"></i> (555) 123-4567</li>
                        <li><i class="fas fa-envelope"></i> info@sakuragarden.com</li>
                    </ul>
                </div>
                <div class="footer-col">
                    <h3>Opening Hours</h3>
                    <ul class="footer-links">
                        <li>Monday - Sunday</li>
                        <li>11:00 AM - 10:00 PM</li>
                    </ul>
                </div>
            </div>
            <div class="copyright">
                <p>&copy; 2023 Sakura Garden. All Rights Reserved.</p>
            </div>
        </div>
    </footer>

    <script>
        // Mobile Menu Toggle
        const mobileMenu = document.querySelector('.mobile-menu');
        const nav = document.querySelector('nav');
        
        mobileMenu.addEventListener('click', () => {
            nav.classList.toggle('active');
            mobileMenu.querySelector('i').classList.toggle('fa-bars');
            mobileMenu.querySelector('i').classList.toggle('fa-times');
        });
        
        // Menu Category Filter
        const categoryBtns = document.querySelectorAll('.category-btn');
        const menuItems = document.querySelectorAll('.menu-item');
        
        categoryBtns.forEach(btn => {
            btn.addEventListener('click', () => {
                // Remove active class from all buttons
                categoryBtns.forEach(b => b.classList.remove('active'));
                // Add active class to clicked button
                btn.classList.add('active');
                
                const category = btn.getAttribute('data-category');
                
                menuItems.forEach(item => {
                    if (category === 'all' || item.getAttribute('data-category') === category) {
                        item.style.display = 'block';
                    } else {
                        item.style.display = 'none';
                    }
                });
            });
        });
        
        // Smooth Scrolling for Anchor Links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function(e) {
                e.preventDefault();
                
                const targetId = this.getAttribute('href');
                if (targetId === '#') return;
                
                const targetElement = document.querySelector(targetId);
                if (targetElement) {
                    window.scrollTo({
                        top: targetElement.offsetTop - 80,
                        behavior: 'smooth'
                    });
                    
                    // Close mobile menu if open
                    if (nav.classList.contains('active')) {
                        nav.classList.remove('active');
                        mobileMenu.querySelector('i').classList.add('fa-bars');
                        mobileMenu.querySelector('i').classList.remove('fa-times');
                    }
                }
            });
        });
    </script>
</body>
</html>
```

## OUTPUT:

![alt text](<Screenshot 2025-10-11 142844.png>)
![alt text](<Screenshot 2025-10-11 142854.png>)

## RESULT:
The program for designing software company website using HTML and CSS is completed successfully.
