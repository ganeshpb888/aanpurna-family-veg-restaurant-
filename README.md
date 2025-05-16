<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Aanpurna Pure Veg Hotel</title>
    <style>
        /* Common Styles */
        body { 
            font-family: 'Poppins', sans-serif; 
            margin: 0; 
            background-color: #f5f5f5;
            color: #333;
        }
        nav { 
            background: #8B4513; 
            padding: 15px; 
            text-align: center; 
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
        }
        nav a { 
            color: white; 
            text-decoration: none; 
            margin: 0 15px;
            font-weight: 500;
            transition: color 0.3s ease;
            padding: 5px 10px;
            border-radius: 5px;
        }
        nav a:hover {
            color: #FFD700;
            background: rgba(255,255,255,0.1);
        }
        .content {
            margin-top: 80px;
            padding: 20px;
        }
        .section {
            display: none;
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }
        .section.active {
            display: block;
            animation: fadeIn 0.5s ease;
        }
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }
        h1, h2, h3 {
            color: #8B4513;
        }
        h1 {
            font-size: 2.5em;
            margin-bottom: 20px;
            text-align: center;
            position: relative;
        }
        h1:after {
            content: '';
            display: block;
            width: 100px;
            height: 3px;
            background: #FFD700;
            margin: 15px auto;
        }

        /* Home Section */
        .hero {
            background: linear-gradient(rgba(0,0,0,0.6), rgba(0,0,0,0.6)), url('https://images.unsplash.com/photo-1517248135467-4c7edcad34c4?ixlib=rb-4.0.3');
            background-size: cover;
            background-position: center;
            height: 500px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            text-align: center;
            border-radius: 10px;
            margin-bottom: 40px;
        }
        .hero-content {
            max-width: 800px;
            padding: 20px;
        }
        .hero h1 {
            font-size: 3.5em;
            color: white;
            margin-bottom: 20px;
        }
        .hero p {
            font-size: 1.2em;
            margin-bottom: 30px;
        }
        .btn {
            background: #FFD700;
            color: #8B4513;
            padding: 12px 30px;
            border: none;
            border-radius: 30px;
            font-size: 1.1em;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s ease;
            box-shadow: 0 4px 8px rgba(0,0,0,0.2);
        }
        .btn:hover {
            background: #8B4513;
            color: #FFD700;
            transform: translateY(-3px);
            box-shadow: 0 6px 12px rgba(0,0,0,0.3);
        }
        .features {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 30px;
            margin: 40px 0;
        }
        .feature-card {
            background: white;
            padding: 25px;
            border-radius: 10px;
            text-align: center;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            transition: transform 0.3s ease;
        }
        .feature-card:hover {
            transform: translateY(-10px);
        }
        .feature-icon {
            font-size: 2.5em;
            color: #8B4513;
            margin-bottom: 15px;
        }

        /* About Section */
        .about-content {
            background: white;
            padding: 40px;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 40px;
            align-items: center;
        }
        .about-image {
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0,0,0,0.2);
        }
        .about-image img {
            width: 100%;
            height: auto;
            display: block;
        }
        .about-text p {
            margin-bottom: 20px;
            line-height: 1.6;
        }
        .management-team {
            margin-top: 40px;
        }
        .management-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            margin-top: 20px;
        }
        .manager-card {
            background: white;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            text-align: center;
        }
        .manager-card img {
            width: 120px;
            height: 120px;
            border-radius: 50%;
            object-fit: cover;
            margin-bottom: 15px;
            border: 3px solid #FFD700;
        }

        /* Menu Section */
        .menu-tabs {
            display: flex;
            justify-content: center;
            margin-bottom: 30px;
            flex-wrap: wrap;
        }
        .menu-tab {
            padding: 10px 20px;
            margin: 0 10px;
            cursor: pointer;
            background: #f0f0f0;
            border-radius: 30px;
            transition: all 0.3s ease;
        }
        .menu-tab.active {
            background: #8B4513;
            color: white;
        }
        .menu-tab:hover:not(.active) {
            background: #ddd;
        }
        .menu-category {
            display: none;
        }
        .menu-category.active {
            display: block;
        }
        .menu-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }
        .menu-item {
            background: white;
            padding: 25px;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            transition: transform 0.3s ease;
        }
        .menu-item:hover {
            transform: translateY(-5px);
        }
        .menu-item h3 {
            color: #8B4513;
            margin-bottom: 15px;
            padding-bottom: 10px;
            border-bottom: 1px dashed #ddd;
        }
        .menu-item ul {
            list-style: none;
            padding: 0;
        }
        .menu-item li {
            display: flex;
            justify-content: space-between;
            margin-bottom: 10px;
            padding-bottom: 10px;
            border-bottom: 1px dashed #eee;
        }
        .item-price {
            color: #8B4513;
            font-weight: bold;
        }
        .special-badge {
            background: #FFD700;
            color: #8B4513;
            padding: 3px 8px;
            border-radius: 5px;
            font-size: 0.8em;
            margin-left: 10px;
            font-weight: bold;
        }

        /* Gallery Section */
        .gallery-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
        }
        .gallery-item {
            position: relative;
            overflow: hidden;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            height: 250px;
            cursor: pointer;
        }
        .gallery-item img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.5s ease;
        }
        .gallery-item:hover img {
            transform: scale(1.1);
        }
        .gallery-caption {
            position: absolute;
            bottom: 0;
            left: 0;
            right: 0;
            background: rgba(139, 69, 19, 0.8);
            color: white;
            padding: 15px;
            transform: translateY(100%);
            transition: transform 0.3s ease;
        }
        .gallery-item:hover .gallery-caption {
            transform: translateY(0);
        }

        /* Staff Section */
        .staff-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 30px;
        }
        .staff-card {
            background: white;
            padding: 25px;
            border-radius: 10px;
            text-align: center;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            transition: transform 0.3s ease;
        }
        .staff-card:hover {
            transform: translateY(-10px);
        }
        .staff-image {
            width: 150px;
            height: 150px;
            border-radius: 50%;
            object-fit: cover;
            margin: 0 auto 15px;
            border: 3px solid #FFD700;
        }
        .staff-social {
            margin-top: 15px;
        }
        .staff-social a {
            color: #8B4513;
            margin: 0 5px;
            font-size: 1.2em;
        }

        /* Offers Section */
        .offers-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 30px;
        }
        .offer-card {
            background: white;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            transition: transform 0.3s ease;
        }
        .offer-card:hover {
            transform: translateY(-10px);
        }
        .offer-image {
            height: 200px;
            overflow: hidden;
        }
        .offer-image img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.5s ease;
        }
        .offer-card:hover .offer-image img {
            transform: scale(1.1);
        }
        .offer-content {
            padding: 20px;
        }
        .offer-tag {
            background: #FFD700;
            color: #8B4513;
            padding: 5px 10px;
            border-radius: 5px;
            font-weight: bold;
            display: inline-block;
            margin-bottom: 10px;
        }
        .offer-valid {
            color: #777;
            font-size: 0.9em;
            margin-top: 10px;
        }

        /* Events Section */
        .events-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }
        .event-card {
            background: white;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }
        .event-date {
            background: #8B4513;
            color: white;
            padding: 10px;
            text-align: center;
            font-weight: bold;
        }
        .event-content {
            padding: 20px;
        }
        .event-time {
            color: #FFD700;
            font-weight: bold;
            margin: 10px 0;
        }

        /* Customer Reviews Section */
        .reviews-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }
        .review-card {
            background: white;
            padding: 25px;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            position: relative;
        }
        .review-card:before {
            content: '"';
            font-size: 5em;
            color: rgba(139, 69, 19, 0.1);
            position: absolute;
            top: 10px;
            right: 20px;
            line-height: 1;
        }
        .review-rating {
            color: #FFD700;
            margin-bottom: 10px;
        }
        .reviewer {
            display: flex;
            align-items: center;
            margin-top: 20px;
        }
        .reviewer img {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            object-fit: cover;
            margin-right: 15px;
        }

        /* Booking Section */
        .booking-container {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 40px;
        }
        .booking-info {
            background: white;
            padding: 30px;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }
        .info-item {
            margin-bottom: 25px;
        }
        .info-item h3 {
            color: #8B4513;
            margin-bottom: 10px;
        }
        .booking-form {
            background: white;
            padding: 30px;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }
        .form-group {
            margin-bottom: 20px;
        }
        label {
            display: block;
            margin-bottom: 8px;
            color: #555;
            font-weight: 500;
        }
        input, select, textarea {
            width: 100%;
            padding: 12px;
            border: 1px solid #ddd;
            border-radius: 5px;
            font-family: 'Poppins', sans-serif;
            transition: border-color 0.3s ease;
        }
        input:focus, select:focus, textarea:focus {
            border-color: #8B4513;
            outline: none;
        }
        textarea {
            min-height: 100px;
            resize: vertical;
        }
        .form-submit {
            text-align: center;
            margin-top: 30px;
        }

        /* Contact Section */
        .contact-container {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 40px;
        }
        .contact-info {
            background: white;
            padding: 30px;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }
        .contact-details {
            margin-top: 30px;
        }
        .contact-item {
            display: flex;
            align-items: center;
            margin-bottom: 20px;
        }
        .contact-icon {
            width: 40px;
            height: 40px;
            background: #8B4513;
            color: white;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin-right: 15px;
            flex-shrink: 0;
        }
        .map-container {
            height: 400px;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }
        .map-container iframe {
            width: 100%;
            height: 100%;
            border: none;
        }

        /* Footer */
        footer {
            background: #8B4513;
            color: white;
            padding: 60px 0 20px;
            margin-top: 50px;
        }
        .footer-container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 40px;
        }
        .footer-section h3 {
            color: #FFD700;
            margin-bottom: 20px;
            font-size: 1.2em;
        }
        .footer-links ul {
            list-style: none;
            padding: 0;
        }
        .footer-links li {
            margin-bottom: 10px;
        }
        .footer-links a {
            color: white;
            text-decoration: none;
            transition: color 0.3s ease;
        }
        .footer-links a:hover {
            color: #FFD700;
        }
        .footer-social {
            display: flex;
            gap: 15px;
            margin-top: 20px;
        }
        .footer-social a {
            color: white;
            font-size: 1.5em;
            transition: color 0.3s ease;
        }
        .footer-social a:hover {
            color: #FFD700;
        }
        .footer-newsletter input {
            width: 100%;
            padding: 10px;
            margin-bottom: 10px;
            border: none;
            border-radius: 5px;
        }
        .footer-bottom {
            text-align: center;
            padding-top: 20px;
            margin-top: 40px;
            border-top: 1px solid rgba(255,255,255,0.1);
        }
        .back-to-top {
            position: fixed;
            bottom: 20px;
            right: 20px;
            background: #8B4513;
            color: white;
            width: 40px;
            height: 40px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            text-decoration: none;
            opacity: 0;
            transition: opacity 0.3s ease;
            z-index: 1000;
        }
        .back-to-top.visible {
            opacity: 1;
        }

        /* Enhanced Mobile Menu Styles */
        .mobile-menu-toggle {
            display: none;
            background: none;
            border: none;
            color: white;
            font-size: 1.5em;
            cursor: pointer;
            padding: 5px;
        }

        @media (max-width: 768px) {
            .mobile-menu-toggle {
                display: block;
            }
            nav {
                flex-direction: column;
                align-items: flex-start;
                padding: 10px;
            }
            nav a {
                display: none;
                width: 100%;
                text-align: left;
                padding: 12px;
                margin: 0;
                border-bottom: 1px solid rgba(255,255,255,0.1);
            }
            nav.active a {
                display: block;
            }
        }

        /* Enhanced Form Validation Styles */
        .form-group {
            position: relative;
        }
        .validation-message {
            position: absolute;
            bottom: -20px;
            left: 0;
            font-size: 0.8em;
            color: #ff4444;
            display: none;
        }
        .form-group.error input,
        .form-group.error select,
        .form-group.error textarea {
            border-color: #ff4444;
        }
        .form-group.error .validation-message {
            display: block;
        }
        .form-group.success input,
        .form-group.success select,
        .form-group.success textarea {
            border-color: #00C851;
        }
    </style>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap" rel="stylesheet">
</head>
<body>
    <nav>
        <a href="#home" onclick="showSection('home')"><i class="fas fa-home"></i> Home</a>
        <a href="#about" onclick="showSection('about')"><i class="fas fa-info-circle"></i> About</a>
        <a href="#menu" onclick="showSection('menu')"><i class="fas fa-utensils"></i> Menu</a>
        <a href="#gallery" onclick="showSection('gallery')"><i class="fas fa-images"></i> Gallery</a>
        <a href="#staff" onclick="showSection('staff')"><i class="fas fa-users"></i> Staff</a>
        <a href="#offers" onclick="showSection('offers')"><i class="fas fa-tag"></i> Offers</a>
        <a href="#events" onclick="showSection('events')"><i class="fas fa-calendar-alt"></i> Events</a>
        <a href="#reviews" onclick="showSection('reviews')"><i class="fas fa-star"></i> Reviews</a>
        <a href="#contact" onclick="showSection('contact')"><i class="fas fa-envelope"></i> Contact</a>
        <a href="#booking" onclick="showSection('booking')"><i class="fas fa-calendar-check"></i> Booking</a>
    </nav>

    <div class="content">
        <!-- Home Section -->
        <section id="home" class="section active">
            <div class="hero">
                <div class="hero-content">
                    <h1>Welcome to Aanpurna Pure Veg Hotel</h1>
                    <p>Experience the finest vegetarian cuisine in Sambhajinagar, where tradition meets taste</p>
                    <button class="btn" onclick="showSection('booking')">Book a Table Now</button>
                </div>
            </div>

            <div class="features">
                <div class="feature-card">
                    <div class="feature-icon">
                        <i class="fas fa-leaf"></i>
                    </div>
                    <h3>100% Vegetarian</h3>
                    <p>We serve only the freshest vegetarian dishes prepared with traditional recipes</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">
                        <i class="fas fa-award"></i>
                    </div>
                    <h3>Award Winning</h3>
                    <p>Recognized as the best vegetarian restaurant in Maharashtra for 3 consecutive years</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">
                        <i class="fas fa-heart"></i>
                    </div>
                    <h3>Family Friendly</h3>
                    <p>Perfect environment for family gatherings and special celebrations</p>
                </div>
            </div>

            <div style="text-align: center; margin: 50px 0;">
                <h2>Our Specialties</h2>
                <p>Discover our signature dishes that keep customers coming back</p>
            </div>

            <div class="menu-grid">
                <div class="menu-item">
                    <h3>Signature Thalis</h3>
                    <ul>
                        <li>Maharashtrian Thali <span class="item-price">₹250</span></li>
                        <li>Punjabi Thali <span class="item-price">₹280</span></li>
                        <li>South Indian Thali <span class="item-price">₹220</span></li>
                    </ul>
                </div>
                <div class="menu-item">
                    <h3>Chef's Special</h3>
                    <ul>
                        <li>Paneer Lababdar <span class="item-price">₹320</span></li>
                        <li>Veg Kolhapuri <span class="item-price">₹280</span></li>
                        <li>Mushroom Masala <span class="item-price">₹300</span></li>
                    </ul>
                </div>
                <div class="menu-item">
                    <h3>Sweet Delights</h3>
                    <ul>
                        <li>Gulab Jamun <span class="item-price">₹80</span></li>
                        <li>Gajar Halwa <span class="item-price">₹120</span></li>
                        <li>Malai Kulfi <span class="item-price">₹90</span></li>
                    </ul>
                </div>
            </div>
        </section>

        <!-- About Section -->
        <section id="about" class="section">
            <h1>About Our Hotel</h1>
            
            <div class="about-content">
                <div class="about-text">
                    <p>Welcome to Aanpurna Pure Veg Hotel, a culinary landmark in Sambhajinagar since 1995. Our restaurant was founded with a simple mission: to serve authentic vegetarian cuisine that celebrates India's rich culinary heritage while maintaining the highest standards of hygiene and quality.</p>
                    
                    <p>What began as a small 20-seater restaurant has now grown into one of the most beloved dining destinations in the region, serving over 500 customers daily. Our success is built on three pillars: exceptional food, warm hospitality, and an unwavering commitment to vegetarian values.</p>
                    
                    <p>We take pride in sourcing our ingredients locally, supporting regional farmers and producers. Our spices are freshly ground daily, and our vegetables are hand-picked each morning to ensure maximum freshness and flavor.</p>
                    
                    <div class="management-team">
                        <h2>Our Management Team</h2>
                        <div class="management-grid">
                            <div class="manager-card">
                                <img src="https://randomuser.me/api/portraits/men/60.jpg" alt="Owner">
                                <h3>Rajesh Patil</h3>
                                <p>Founder & Owner</p>
                                <p>25+ years in hospitality</p>
                            </div>
                            <div class="manager-card">
                                <img src="https://randomuser.me/api/portraits/women/45.jpg" alt="Manager">
                                <h3>Priya Deshmukh</h3>
                                <p>General Manager</p>
                                <p>15+ years experience</p>
                            </div>
                            <div class="manager-card">
                                <img src="https://randomuser.me/api/portraits/men/32.jpg" alt="Head Chef">
                                <h3>Vikram Joshi</h3>
                                <p>Head Chef</p>
                                <p>Specializes in Maharashtrian cuisine</p>
                            </div>
                        </div>
                    </div>
                </div>
                
                <div class="about-image">
                    <img src="https://images.unsplash.com/photo-1555396273-367ea4eb4db5?ixlib=rb-4.0.3" alt="Restaurant Interior">
                </div>
            </div>
        </section>

        <!-- Menu Section -->
        <section id="menu" class="section">
            <h1>Our Menu</h1>
            
            <div class="menu-tabs">
                <div class="menu-tab active" onclick="changeMenuTab('starters')">Starters</div>
                <div class="menu-tab" onclick="changeMenuTab('main-course')">Main Course</div>
                <div class="menu-tab" onclick="changeMenuTab('breads')">Breads</div>
                <div class="menu-tab" onclick="changeMenuTab('rice')">Rice Dishes</div>
                <div class="menu-tab" onclick="changeMenuTab('desserts')">Desserts</div>
                <div class="menu-tab" onclick="changeMenuTab('beverages')">Beverages</div>
            </div>
            
            <div id="starters" class="menu-category active">
                <div class="menu-grid">
                    <div class="menu-item">
                        <h3>Indian Starters</h3>
                        <ul>
                            <li>Paneer Tikka <span class="item-price">₹220</span></li>
                            <li>Hara Bhara Kabab <span class="item-price">₹180</span></li>
                            <li>Veg Seekh Kabab <span class="item-price">₹200</span></li>
                            <li>Corn Chaat <span class="item-price">₹150</span></li>
                            <li>Aloo Tikki <span class="item-price">₹120</span></li>
                        </ul>
                    </div>
                    <div class="menu-item">
                        <h3>Chinese Starters</h3>
                        <ul>
                            <li>Veg Spring Roll <span class="item-price">₹160</span></li>
                            <li>Chilli Paneer <span class="item-price">₹200</span></li>
                            <li>Veg Manchurian <span class="item-price">₹180</span></li>
                            <li>Crispy Corn <span class="item-price">₹170</span></li>
                        </ul>
                    </div>
                    <div class="menu-item">
                        <h3>Special Starters</h3>
                        <ul>
                            <li>Tandoori Mushroom <span class="item-price">₹240</span></li>
                            <li>Paneer Achari <span class="item-price">₹250</span></li>
                            <li>Cheese Garlic Bread <span class="item-price">₹180</span></li>
                            <li>Stuffed Baby Corn <span class="item-price">₹220</span></li>
                        </ul>
                    </div>
                </div>
            </div>
            
            <div id="main-course" class="menu-category">
                <div class="menu-grid">
                    <div class="menu-item">
                        <h3>Paneer Specialties</h3>
                        <ul>
                            <li>Paneer Butter Masala <span class="item-price">₹280</span></li>
                            <li>Kadai Paneer <span class="item-price">₹270</span></li>
                            <li>Shahi Paneer <span class="item-price">₹290</span></li>
                            <li>Paneer Lababdar <span class="item-price">₹300</span></li>
                            <li>Paneer Tikka Masala <span class="item-price">₹280</span></li>
                        </ul>
                    </div>
                    <div class="menu-item">
                        <h3>Vegetable Curries</h3>
                        <ul>
                            <li>Mix Veg <span class="item-price">₹220</span></li>
                            <li>Aloo Gobi <span class="item-price">₹200</span></li>
                            <li>Bhindi Masala <span class="item-price">₹210</span></li>
                            <li>Baingan Bharta <span class="item-price">₹230</span></li>
                            <li>Malai Kofta <span class="item-price">₹260</span></li>
                        </ul>
                    </div>
                    <div class="menu-item">
                        <h3>Special Curries</h3>
                        <ul>
                            <li>Veg Kolhapuri <span class="item-price">₹240</span></li>
                            <li>Dal Makhani <span class="item-price">₹220</span></li>
                            <li>Chana Masala <span class="item-price">₹200</span></li>
                            <li>Mushroom Masala <span class="item-price">₹250</span></li>
                            <li>Navratan Korma <span class="item-price">₹270</span></li>
                        </ul>
                    </div>
                </div>
            </div>
            
            <!-- Additional menu categories would follow the same pattern -->
            
            <div class="special-menu" style="margin-top: 50px;">
                <h2>Chef's Special Menu</h2>
                <p>Our exclusive dishes created by our master chefs</p>
                
                <div class="menu-grid">
                    <div class="menu-item">
                        <h3>Signature Dishes <span class="special-badge">Must Try</span></h3>
                        <ul>
                            <li>Paneer Saagwala <span class="item-price">₹320</span></li>
                            <li>Stuffed Bell Pepper <span class="item-price">₹280</span></li>
                            <li>Cheese Corn Ball <span class="item-price">₹260</span></li>
                            <li>Veg Dum Biryani <span class="item-price">₹300</span></li>
                        </ul>
                    </div>
                    <div class="menu-item">
                        <h3>Seasonal Specials <span class="special-badge">Limited Time</span></h3>
                        <ul>
                            <li>Jackfruit Biryani <span class="item-price">₹290</span></li>
                            <li>Stuffed Pumpkin <span class="item-price">₹310</span></li>
                            <li>Mango Lassi <span class="item-price">₹120</span></li>
                            <li>Seasonal Fruit Custard <span class="item-price">₹150</span></li>
                        </ul>
                    </div>
                    <div class="menu-item">
                        <h3>Healthy Options <span class="special-badge">Low Calorie</span></h3>
                        <ul>
                            <li>Quinoa Salad <span class="item-price">₹220</span></li>
                            <li>Steamed Veg Platter <span class="item-price">₹240</span></li>
                            <li>Avocado Sandwich <span class="item-price">₹200</span></li>
                            <li>Detox Juice <span class="item-price">₹180</span></li>
                        </ul>
                    </div>
                </div>
            </div>
        </section>

        <!-- Gallery Section -->
        <section id="gallery" class="section">
            <h1>Gallery</h1>
            
            <div class="gallery-grid">
                <div class="gallery-item">
                    <img src="https://images.unsplash.com/photo-1517248135467-4c7edcad34c4?ixlib=rb-4.0.3" alt="Restaurant Interior">
                    <div class="gallery-caption">Our Elegant Dining Area</div>
                </div>
                <div class="gallery-item">
                    <img src="https://images.unsplash.com/photo-1414235077428-338989a2e8c0?ixlib=rb-4.0.3" alt="Food Presentation">
                    <div class="gallery-caption">Signature Dishes</div>
                </div>
                <div class="gallery-item">
                    <img src="https://images.unsplash.com/photo-1559847844-5315695dadae?ixlib=rb-4.0.3" alt="Chef Cooking">
                    <div class="gallery-caption">Our Master Chefs at Work</div>
                </div>
                <div class="gallery-item">
                    <img src="https://images.unsplash.com/photo-1555396273-367ea4eb4db5?ixlib=rb-4.0.3" alt="Dining Experience">
                    <div class="gallery-caption">Fine Dining Experience</div>
                </div>
                <div class="gallery-item">
                    <img src="https://images.unsplash.com/photo-1585032226651-759b368d7246?ixlib=rb-4.0.3" alt="South Indian Food">
                    <div class="gallery-caption">Authentic South Indian</div>
                </div>
                <div class="gallery-item">
                    <img src="https://images.unsplash.com/photo-1546069901-ba9599a7e63c?ixlib=rb-4.0.3" alt="Thali">
                    <div class="gallery-caption">Traditional Thali</div>
                </div>
            </div>
        </section>

        <!-- Staff Section -->
        <section id="staff" class="section">
            <h1>Our Team</h1>
            
            <div class="staff-grid">
                <div class="staff-card">
                    <img src="https://randomuser.me/api/portraits/men/32.jpg" class="staff-image" alt="Head Chef">
                    <h3>Vikram Joshi</h3>
                    <p>Head Chef</p>
                    <p>Specializes in North Indian cuisine with 18 years of experience</p>
                    <div class="staff-social">
                        <a href="#"><i class="fab fa-facebook"></i></a>
                        <a href="#"><i class="fab fa-twitter"></i></a>
                        <a href="#"><i class="fab fa-instagram"></i></a>
                    </div>
                </div>
            </div>
        </section>

        <!-- Offers Section -->
        <section id="offers" class="section">
            <h1>Special Offers</h1>
            
            <div class="offers-container">
                <div class="offer-card">
                    <div class="offer-image">
                        <img src="https://images.unsplash.com/photo-1555396273-367ea4eb4db5?ixlib=rb-4.0.3" alt="Offer Image">
                    </div>
                    <div class="offer-content">
                        <h2>Special Offer Title</h2>
                        <p>Description of the offer. This could be a brief description or a longer paragraph.</p>
                        <p>Valid until: <span class="offer-valid">Date</span></p>
                        <button class="btn">Book Now</button>
                    </div>
                </div>
                <div class="offer-card">
                    <div class="offer-image">
                        <img src="https://images.unsplash.com/photo-1555396273-367ea4eb4db5?ixlib=rb-4.0.3" alt="Offer Image">
                    </div>
                    <div class="offer-content">
                        <h2>Special Offer Title</h2>
                        <p>Description of the offer. This could be a brief description or a longer paragraph.</p>
                        <p>Valid until: <span class="offer-valid">Date</span></p>
                        <button class="btn">Book Now</button>
                    </div>
                </div>
            </div>
        </section>

        <!-- Events Section -->
        <section id="events" class="section">
            <h1>Upcoming Events</h1>
            
            <div class="events-container">
                <div class="event-card">
                    <div class="event-date">
                        <h2>Event Date</h2>
                    </div>
                    <div class="event-content">
                        <h2>Event Title</h2>
                        <p>Description of the event. This could be a brief description or a longer paragraph.</p>
                        <p>Time: <span class="event-time">Time</span></p>
                        <button class="btn">Learn More</button>
                    </div>
                </div>
                <div class="event-card">
                    <div class="event-date">
                        <h2>Event Date</h2>
                    </div>
                    <div class="event-content">
                        <h2>Event Title</h2>
                        <p>Description of the event. This could be a brief description or a longer paragraph.</p>
                        <p>Time: <span class="event-time">Time</span></p>
                        <button class="btn">Learn More</button>
                    </div>
                </div>
            </div>
        </section>

        <!-- Customer Reviews Section -->
        <section id="reviews" class="section">
            <h1>Customer Reviews</h1>
            
            <div class="reviews-container">
                <div class="review-card">
                    <div class="review-rating">
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                    </div>
                    <p>"Great experience! The food was delicious and the service was excellent."</p>
                    <div class="reviewer">
                        <img src="https://randomuser.me/api/portraits/men/32.jpg" alt="Reviewer">
                        <p>John Doe</p>
                    </div>
                </div>
                <div class="review-card">
                    <div class="review-rating">
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                    </div>
                    <p>"I had an amazing time at Aanpurna Pure Veg Hotel. The food was amazing and the staff was very friendly."</p>
                    <div class="reviewer">
                        <img src="https://randomuser.me/api/portraits/women/45.jpg" alt="Reviewer">
                        <p>Jane Smith</p>
                    </div>
                </div>
            </div>
        </section>

        <!-- Booking Section -->
        <section id="booking" class="section">
            <h1>Book a Table</h1>
            
            <div class="booking-container">
                <div class="booking-info">
                    <h2>Booking Information</h2>
                    <div class="info-item">
                        <h3>Date</h3>
                        <input type="date">
                    </div>
                    <div class="info-item">
                        <h3>Time</h3>
                        <input type="time">
                    </div>
                    <div class="info-item">
                        <h3>Guests</h3>
                        <input type="number">
                    </div>
                    <button class="btn">Find a Table</button>
                </div>
                <div class="booking-form">
                    <h2>Booking Form</h2>
                    <div class="form-group">
                        <label for="name">Name</label>
                        <input type="text" id="name" required>
                    </div>
                    <div class="form-group">
                        <label for="email">Email</label>
                        <input type="email" id="email" required>
                    </div>
                    <div class="form-group">
                        <label for="phone">Phone</label>
                        <input type="tel" id="phone" required>
                    </div>
                    <div class="form-group">
                        <label for="occasion">Occasion</label>
                        <select id="occasion" required>
                            <option value="">Select an occasion</option>
                            <option value="Birthday">Birthday</option>
                            <option value="Anniversary">Anniversary</option>
                            <option value="Business Meeting">Business Meeting</option>
                            <option value="Other">Other</option>
                        </select>
                    </div>
                    <div class="form-group">
                        <label for="message">Special Requests</label>
                        <textarea id="message" rows="4"></textarea>
                    </div>
                    <button class="btn">Book Now</button>
                </div>
            </div>
        </section>

        <!-- Contact Section -->
        <section id="contact" class="section">
            <h1>Contact Us</h1>
            
            <div class="contact-container">
                <div class="contact-info">
                    <h2>Contact Information</h2>
                    <div class="contact-item">
                        <i class="fas fa-phone"></i>
                        <p>+91 1234567890</p>
                    </div>
                    <div class="contact-item">
                        <i class="fas fa-envelope"></i>
                        <p>info@aanpurna.com</p>
                    </div>
                    <div class="contact-item">
                        <i class="fas fa-map-marker-alt"></i>
                        <p>123 Main Street, Sambhajinagar</p>
                    </div>
                </div>
                <div class="map-container">
                    <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3782.244778726294!2d75.62574247499999!3d16.70501778232484!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x3bc11e3d685453d5%3A0x6c44d5e6f4e6e68!2sSai%20Prasad%20Pure%20Veg%20Hotel!5e0!3m2!1sen!2sin!4v1682344800000!5m2!1sen!2sin" width="100%" height="300" style="border:0;" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>
                </div>
            </div>
        </section>
    </div>

    <!-- Enhanced Footer -->
    <footer>
        <div class="footer-container">
            <div class="footer-section">
                <h3>About Aanpurna</h3>
                <h3>About Sai Prasad</h3>
                <p>Experience the finest vegetarian cuisine in Sambhajinagar, where tradition meets taste. Our commitment to quality and authentic flavors has made us a favorite destination for food lovers.</p>
                <div class="footer-social">
                    <a href="#"><i class="fab fa-facebook"></i></a>
                    <a href="#"><i class="fab fa-instagram"></i></a>
                    <a href="#"><i class="fab fa-twitter"></i></a>
                    <a href="#"><i class="fab fa-youtube"></i></a>
                </div>
            </div>
            
            <div class="footer-section">
                <h3>Quick Links</h3>
                <div class="footer-links">
                    <ul>
                        <li><a href="#home" onclick="showSection('home')">Home</a></li>
                        <li><a href="#menu" onclick="showSection('menu')">Menu</a></li>
                        <li><a href="#gallery" onclick="showSection('gallery')">Gallery</a></li>
                        <li><a href="#booking" onclick="showSection('booking')">Book a Table</a></li>
                        <li><a href="#contact" onclick="showSection('contact')">Contact</a></li>
                    </ul>
                </div>
            </div>
            
            <div class="footer-section">
                <h3>Opening Hours</h3>
                <ul class="footer-links">
                    <li>Monday - Friday: 11:00 AM - 11:00 PM</li>
                    <li>Saturday - Sunday: 10:00 AM - 11:00 PM</li>
                    <li>Public Holidays: 10:00 AM - 11:00 PM</li>
                </ul>
            </div>
            
            <div class="footer-section">
                <h3>Newsletter</h3>
                <div class="footer-newsletter">
                    <input type="email" placeholder="Enter your email" id="newsletter-email">
                    <button class="btn" onclick="subscribeNewsletter()">Subscribe</button>
                </div>
            </div>
        </div>
        
        <div class="footer-bottom">
            <p>&copy; 2024 Sai Prasad Pure Veg Hotel. All rights reserved.</p>
        </div>
    </footer>

    <a href="#" class="back-to-top" id="backToTop">
        <i class="fas fa-arrow-up"></i>
    </a>

    <script>
        // Fix for section navigation
        function showSection(sectionId) {
            // Hide all sections
            document.querySelectorAll('.section').forEach(section => {
                section.classList.remove('active');
            });
            
            // Show selected section
            const selectedSection = document.getElementById(sectionId);
            if (selectedSection) {
                selectedSection.classList.add('active');
                // Update URL hash
                window.location.hash = sectionId;
                // Scroll to top of section
                window.scrollTo({
                    top: 0,
                    behavior: 'smooth'
                });
            }
        }

        // Fix for form validation
        function validateForm(form) {
            const inputs = form.querySelectorAll('input, select, textarea');
            let isValid = true;

            inputs.forEach(input => {
                const formGroup = input.closest('.form-group');
                formGroup.classList.remove('error', 'success');

                if (input.hasAttribute('required') && !input.value.trim()) {
                    isValid = false;
                    formGroup.classList.add('error');
                    showValidationMessage(formGroup, 'This field is required');
                } else if (input.type === 'email' && !isValidEmail(input.value)) {
                    isValid = false;
                    formGroup.classList.add('error');
                    showValidationMessage(formGroup, 'Please enter a valid email address');
                } else if (input.type === 'tel' && !isValidPhone(input.value)) {
                    isValid = false;
                    formGroup.classList.add('error');
                    showValidationMessage(formGroup, 'Please enter a valid phone number');
                } else if (input.value.trim()) {
                    formGroup.classList.add('success');
                }
            });

            return isValid;
        }

        function showValidationMessage(formGroup, message) {
            let validationMessage = formGroup.querySelector('.validation-message');
            if (!validationMessage) {
                validationMessage = document.createElement('div');
                validationMessage.className = 'validation-message';
                formGroup.appendChild(validationMessage);
            }
            validationMessage.textContent = message;
        }

        function isValidEmail(email) {
            return /^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(email);
        }

        function isValidPhone(phone) {
            return /^[0-9]{10}$/.test(phone.replace(/\D/g, ''));
        }

        // Back to Top Button
        const backToTopButton = document.getElementById('backToTop');
        window.addEventListener('scroll', () => {
            if (window.pageYOffset > 300) {
                backToTopButton.classList.add('visible');
            } else {
                backToTopButton.classList.remove('visible');
            }
        });

        backToTopButton.addEventListener('click', (e) => {
            e.preventDefault();
            window.scrollTo({
                top: 0,
                behavior: 'smooth'
            });
        });

        // Newsletter Subscription
        function subscribeNewsletter() {
            const emailInput = document.getElementById('newsletter-email');
            if (isValidEmail(emailInput.value)) {
                alert('Thank you for subscribing to our newsletter!');
                emailInput.value = '';
            } else {
                alert('Please enter a valid email address.');
            }
        }

        // Enhanced Mobile Menu
        function toggleMobileMenu() {
            const nav = document.querySelector('nav');
            nav.classList.toggle('active');
            
            // Close menu when clicking outside
            if (nav.classList.contains('active')) {
                document.addEventListener('click', closeMenuOnClickOutside);
            } else {
                document.removeEventListener('click', closeMenuOnClickOutside);
            }
        }

        function closeMenuOnClickOutside(e) {
            const nav = document.querySelector('nav');
            const menuButton = document.querySelector('.mobile-menu-toggle');
            
            if (!nav.contains(e.target) && !menuButton.contains(e.target)) {
                nav.classList.remove('active');
                document.removeEventListener('click', closeMenuOnClickOutside);
            }
        }

        // Initialize on page load
        document.addEventListener('DOMContentLoaded', () => {
            // Show section based on URL hash
            const hash = window.location.hash.slice(1) || 'home';
            showSection(hash);

            // Add input event listeners for real-time validation
            document.querySelectorAll('input, select, textarea').forEach(input => {
                input.addEventListener('input', () => {
                    const formGroup = input.closest('.form-group');
                    if (formGroup) {
                        validateForm(input.closest('form'));
                    }
                });
            });
        });
    </script>
</body>
</html>
