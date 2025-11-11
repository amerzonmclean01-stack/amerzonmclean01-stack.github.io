<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>The Definitive Word - Premium Ebook Store</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary: #2c3e50;
            --secondary: #3498db;
            --accent: #e74c3c;
            --light: #ecf0f1;
            --dark: #2c3e50;
            --success: #2ecc71;
            --warning: #f39c12;
            --shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
            --transition: all 0.3s ease;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            line-height: 1.6;
            color: #333;
            background-color: #f9f9f9;
        }

        .container {
            width: 90%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 15px;
        }

        /* Header Styles */
        header {
            background: white;
            box-shadow: var(--shadow);
            position: sticky;
            top: 0;
            z-index: 1000;
        }

        .header-top {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 15px 0;
        }

        .logo {
            display: flex;
            align-items: center;
            font-size: 1.8rem;
            font-weight: 700;
            color: var(--primary);
        }

        .logo i {
            color: var(--secondary);
            margin-right: 10px;
        }

        .search-bar {
            flex: 1;
            max-width: 500px;
            margin: 0 20px;
            position: relative;
        }

        .search-bar input {
            width: 100%;
            padding: 10px 15px;
            border: 1px solid #ddd;
            border-radius: 30px;
            font-size: 1rem;
        }

        .search-results {
            position: absolute;
            top: 100%;
            left: 0;
            right: 0;
            background: white;
            border-radius: 8px;
            box-shadow: var(--shadow);
            max-height: 300px;
            overflow-y: auto;
            display: none;
            z-index: 1001;
        }

        .search-results.active {
            display: block;
        }

        .search-result-item {
            padding: 10px 15px;
            border-bottom: 1px solid #eee;
            cursor: pointer;
            display: flex;
            align-items: center;
            transition: var(--transition);
        }

        .search-result-item:hover {
            background: #f5f5f5;
        }

        .search-result-item img {
            width: 40px;
            height: 50px;
            object-fit: cover;
            margin-right: 10px;
        }

        .search-result-info {
            flex: 1;
        }

        .search-result-title {
            font-weight: 600;
            font-size: 0.9rem;
        }

        .search-result-author {
            font-size: 0.8rem;
            color: #666;
        }

        .user-actions {
            display: flex;
            align-items: center;
        }

        .user-actions a {
            margin-left: 15px;
            color: var(--primary);
            font-size: 1.2rem;
            transition: var(--transition);
            position: relative;
        }

        .user-actions a:hover {
            color: var(--secondary);
        }

        .cart-count, .wishlist-count {
            background: var(--accent);
            color: white;
            border-radius: 50%;
            width: 18px;
            height: 18px;
            font-size: 0.7rem;
            display: flex;
            align-items: center;
            justify-content: center;
            position: absolute;
            top: -5px;
            right: -5px;
        }

        .cart-icon, .wishlist-icon {
            position: relative;
        }

        nav {
            background: var(--primary);
            padding: 10px 0;
        }

        nav ul {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
        }

        nav li {
            margin: 0 15px;
        }

        nav a {
            color: white;
            font-weight: 500;
            padding: 5px 0;
            transition: var(--transition);
            position: relative;
        }

        nav a:hover {
            color: var(--secondary);
        }

        nav a::after {
            content: '';
            position: absolute;
            width: 0;
            height: 2px;
            bottom: 0;
            left: 0;
            background: var(--secondary);
            transition: var(--transition);
        }

        nav a:hover::after {
            width: 100%;
        }

        /* Hero Section */
        .hero {
            background: linear-gradient(rgba(44, 62, 80, 0.8), rgba(44, 62, 80, 0.8)), url('https://images.unsplash.com/photo-1507842217343-583bb7270b66?ixlib=rb-4.0.3');
            background-size: cover;
            background-position: center;
            color: white;
            padding: 100px 0;
            text-align: center;
        }

        .hero h1 {
            font-size: 3rem;
            margin-bottom: 20px;
        }

        .hero p {
            font-size: 1.2rem;
            max-width: 700px;
            margin: 0 auto 30px;
        }

        .btn {
            display: inline-block;
            padding: 12px 25px;
            background: var(--secondary);
            color: white;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            transition: var(--transition);
            font-weight: 600;
            margin: 5px;
        }

        .btn:hover {
            background: #2980b9;
            transform: translateY(-2px);
            box-shadow: 0 4px 8px rgba(0,0,0,0.2);
        }

        .btn-accent {
            background: var(--accent);
        }

        .btn-accent:hover {
            background: #c0392b;
        }

        .btn-outline {
            background: transparent;
            border: 2px solid white;
        }

        .btn-outline:hover {
            background: white;
            color: var(--primary);
        }

        /* Featured Books */
        .section-title {
            text-align: center;
            margin: 50px 0 30px;
            color: var(--primary);
            position: relative;
        }

        .section-title::after {
            content: '';
            width: 80px;
            height: 3px;
            background: var(--secondary);
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
        }

        .books-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 30px;
            margin-bottom: 50px;
        }

        .book-card {
            background: white;
            border-radius: 8px;
            overflow: hidden;
            box-shadow: var(--shadow);
            transition: var(--transition);
            position: relative;
        }

        .book-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.15);
        }

        .book-badge {
            position: absolute;
            top: 10px;
            right: 10px;
            background: var(--accent);
            color: white;
            padding: 5px 10px;
            border-radius: 3px;
            font-size: 0.8rem;
            font-weight: 600;
            z-index: 2;
        }

        .book-cover {
            height: 300px;
            overflow: hidden;
            position: relative;
        }

        .book-cover img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: var(--transition);
        }

        .book-card:hover .book-cover img {
            transform: scale(1.05);
        }

        .book-actions {
            position: absolute;
            bottom: 10px;
            right: 10px;
            display: flex;
            gap: 5px;
            opacity: 0;
            transition: var(--transition);
        }

        .book-card:hover .book-actions {
            opacity: 1;
        }

        .action-btn {
            width: 36px;
            height: 36px;
            background: white;
            border: none;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            transition: var(--transition);
            box-shadow: var(--shadow);
        }

        .action-btn:hover {
            background: var(--secondary);
            color: white;
            transform: scale(1.1);
        }

        .book-info {
            padding: 15px;
        }

        .book-title {
            font-weight: 600;
            margin-bottom: 5px;
            font-size: 1.1rem;
        }

        .book-author {
            color: #666;
            font-size: 0.9rem;
            margin-bottom: 10px;
        }

        .book-price {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-top: 10px;
        }

        .price {
            font-weight: 700;
            color: var(--primary);
        }

        .original-price {
            text-decoration: line-through;
            color: #999;
            margin-right: 5px;
        }

        .sale-price {
            color: var(--accent);
        }

        /* Search Results Section */
        .search-results-section {
            display: none;
            padding: 20px 0;
        }

        .search-results-section.active {
            display: block;
        }

        .search-info {
            text-align: center;
            margin-bottom: 20px;
        }

        .clear-search {
            background: var(--accent);
            color: white;
            border: none;
            padding: 8px 15px;
            border-radius: 4px;
            cursor: pointer;
            margin-left: 10px;
            transition: var(--transition);
        }

        .clear-search:hover {
            background: #c0392b;
        }

        /* Categories */
        .categories {
            background: var(--light);
            padding: 50px 0;
        }

        .categories-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
            gap: 20px;
        }

        .category-card {
            background: white;
            border-radius: 8px;
            padding: 20px;
            text-align: center;
            box-shadow: var(--shadow);
            transition: var(--transition);
            cursor: pointer;
        }

        .category-card:hover {
            transform: translateY(-5px);
            background: var(--secondary);
            color: white;
        }

        .category-card i {
            font-size: 2.5rem;
            margin-bottom: 15px;
            color: var(--secondary);
        }

        .category-card:hover i {
            color: white;
        }

        /* Newsletter */
        .newsletter {
            background: var(--primary);
            color: white;
            padding: 60px 0;
            text-align: center;
        }

        .newsletter h2 {
            margin-bottom: 20px;
        }

        .newsletter p {
            max-width: 600px;
            margin: 0 auto 30px;
        }

        .newsletter-form {
            display: flex;
            max-width: 500px;
            margin: 0 auto;
        }

        .newsletter-form input {
            flex: 1;
            padding: 12px 15px;
            border: none;
            border-radius: 4px 0 0 4px;
            font-size: 1rem;
        }

        .newsletter-form button {
            background: var(--accent);
            color: white;
            border: none;
            padding: 0 20px;
            border-radius: 0 4px 4px 0;
            cursor: pointer;
            transition: var(--transition);
        }

        .newsletter-form button:hover {
            background: #c0392b;
        }

        /* Footer */
        footer {
            background: #1a252f;
            color: white;
            padding: 50px 0 20px;
        }

        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 30px;
            margin-bottom: 30px;
        }

        .footer-column h3 {
            margin-bottom: 20px;
            font-size: 1.2rem;
            position: relative;
            padding-bottom: 10px;
        }

        .footer-column h3::after {
            content: '';
            position: absolute;
            left: 0;
            bottom: 0;
            width: 40px;
            height: 2px;
            background: var(--secondary);
        }

        .footer-column ul li {
            margin-bottom: 10px;
        }

        .footer-column ul li a {
            transition: var(--transition);
        }

        .footer-column ul li a:hover {
            color: var(--secondary);
            padding-left: 5px;
        }

        .social-links {
            display: flex;
            margin-top: 20px;
        }

        .social-links a {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 36px;
            height: 36px;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 50%;
            margin-right: 10px;
            transition: var(--transition);
        }

        .social-links a:hover {
            background: var(--secondary);
            transform: translateY(-3px);
        }

        .copyright {
            text-align: center;
            padding-top: 20px;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            font-size: 0.9rem;
            color: #aaa;
        }

        /* Modals */
        .modal {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.5);
            display: flex;
            align-items: center;
            justify-content: center;
            z-index: 2000;
            opacity: 0;
            visibility: hidden;
            transition: var(--transition);
        }

        .modal.active {
            opacity: 1;
            visibility: visible;
        }

        .modal-content {
            background: white;
            border-radius: 8px;
            max-width: 500px;
            width: 90%;
            max-height: 90vh;
            overflow-y: auto;
            transform: translateY(-20px);
            transition: var(--transition);
        }

        .modal.active .modal-content {
            transform: translateY(0);
        }

        .modal-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px;
            border-bottom: 1px solid #eee;
        }

        .close-modal {
            background: none;
            border: none;
            font-size: 1.5rem;
            cursor: pointer;
            color: var(--primary);
        }

        .modal-body {
            padding: 20px;
        }

        /* Cart Modal */
        .cart-modal {
            position: fixed;
            top: 0;
            right: -400px;
            width: 380px;
            height: 100vh;
            background: white;
            box-shadow: -5px 0 15px rgba(0, 0, 0, 0.1);
            transition: var(--transition);
            z-index: 1100;
            overflow-y: auto;
        }

        .cart-modal.active {
            right: 0;
        }

        .cart-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px;
            border-bottom: 1px solid #eee;
        }

        .cart-header h2 {
            color: var(--primary);
        }

        .close-cart {
            background: none;
            border: none;
            font-size: 1.5rem;
            cursor: pointer;
            color: var(--primary);
        }

        .cart-items {
            padding: 20px;
        }

        .cart-item {
            display: flex;
            margin-bottom: 20px;
            padding-bottom: 20px;
            border-bottom: 1px solid #eee;
        }

        .cart-item img {
            width: 80px;
            height: 100px;
            object-fit: cover;
            margin-right: 15px;
        }

        .cart-item-details {
            flex: 1;
        }

        .cart-item-title {
            font-weight: 600;
            margin-bottom: 5px;
        }

        .cart-item-price {
            color: var(--primary);
            font-weight: 600;
        }

        .cart-item-remove {
            background: none;
            border: none;
            color: var(--accent);
            cursor: pointer;
            font-size: 0.9rem;
        }

        .cart-total {
            padding: 20px;
            border-top: 1px solid #eee;
            display: flex;
            justify-content: space-between;
            font-weight: 700;
            font-size: 1.1rem;
        }

        .cart-actions {
            padding: 0 20px 20px;
        }

        .empty-state {
            text-align: center;
            padding: 40px 20px;
            color: #666;
        }

        .empty-state i {
            font-size: 3rem;
            margin-bottom: 15px;
            color: #ddd;
        }

        /* Responsive Styles */
        @media (max-width: 768px) {
            .header-top {
                flex-direction: column;
            }
            .logo {
                margin-bottom: 15px;
            }
            .search-bar {
                margin: 15px 0;
                max-width: 100%;
            }
            nav ul {
                flex-wrap: wrap;
            }
            nav li {
                margin: 5px 10px;
            }
            .hero h1 {
                font-size: 2.2rem;
            }
            .newsletter-form {
                flex-direction: column;
            }
            .newsletter-form input {
                border-radius: 4px;
                margin-bottom: 10px;
            }
            .newsletter-form button {
                border-radius: 4px;
                padding: 12px;
            }
            .cart-modal {
                width: 100%;
                right: -100%;
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <div class="container">
            <div class="header-top">
                <a href="#" class="logo">
                    <i class="fas fa-book-open"></i>
                    The Definitive Word
                </a>
                <div class="search-bar">
                    <input type="text" id="search-input" placeholder="Search for books, authors, or categories...">
                    <div class="search-results" id="search-results">
                        <!-- Search results will appear here -->
                    </div>
                </div>
                <div class="user-actions">
                    <a href="#" id="wishlist-icon" class="wishlist-icon">
                        <i class="fas fa-heart"></i>
                        <span class="wishlist-count">0</span>
                    </a>
                    <a href="#" class="cart-icon">
                        <i class="fas fa-shopping-cart"></i>
                        <span class="cart-count">0</span>
                    </a>
                </div>
            </div>
        </div>
        <nav>
            <div class="container">
                <ul>
                    <li><a href="#" data-category="Fiction">Fiction</a></li>
                    <li><a href="#" data-category="Non-Fiction">Non-Fiction</a></li>
                    <li><a href="#" data-category="Science">Science</a></li>
                    <li><a href="#" data-category="Technology">Technology</a></li>
                    <li><a href="#" data-category="Business">Business</a></li>
                    <li><a href="#" data-category="Self-Help">Self-Help</a></li>
                </ul>
            </div>
        </nav>
    </header>

    <!-- Hero Section -->
    <section class="hero">
        <div class="container">
            <h1>Discover Your Next Favorite Read</h1>
            <p>Explore thousands of ebooks across all genres. Download instantly and start reading today.</p>
            <a href="#" class="btn btn-accent">Browse Collection</a>
            <a href="#" class="btn btn-outline">View Bestsellers</a>
        </div>
    </section>

    <!-- Search Results Section -->
    <section class="search-results-section" id="search-results-section">
        <div class="container">
            <div class="search-info">
                <h2 id="search-results-title">Search Results</h2>
                <button class="clear-search" id="clear-search">Show All Books</button>
            </div>
            <div class="books-grid" id="search-results-books">
                <!-- Search results books will appear here -->
            </div>
        </div>
    </section>

    <!-- Featured Books -->
    <section class="container" id="featured-section">
        <h2 class="section-title">Featured Books</h2>
        <div class="books-grid" id="featured-books">
            <!-- Books will be loaded by JavaScript -->
        </div>
    </section>

    <!-- Categories -->
    <section class="categories">
        <div class="container">
            <h2 class="section-title">Browse Categories</h2>
            <div class="categories-grid">
                <div class="category-card" data-category="Science Fiction">
                    <i class="fas fa-rocket"></i>
                    <h3>Science Fiction</h3>
                    <p>Explore other worlds and futures</p>
                </div>
                <div class="category-card" data-category="Romance">
                    <i class="fas fa-heart"></i>
                    <h3>Romance</h3>
                    <p>Stories of love and connection</p>
                </div>
                <div class="category-card" data-category="Mystery">
                    <i class="fas fa-user-secret"></i>
                    <h3>Mystery</h3>
                    <p>Unravel puzzles and crimes</p>
                </div>
                <div class="category-card" data-category="Business">
                    <i class="fas fa-chart-line"></i>
                    <h3>Business</h3>
                    <p>Grow your career and wealth</p>
                </div>
                <div class="category-card" data-category="Self-Help">
                    <i class="fas fa-brain"></i>
                    <h3>Self-Help</h3>
                    <p>Improve your life and mindset</p>
                </div>
                <div class="category-card" data-category="Technology">
                    <i class="fas fa-laptop-code"></i>
                    <h3>Technology</h3>
                    <p>Stay ahead in the digital world</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Newsletter -->
    <section class="newsletter">
        <div class="container">
            <h2>Stay Updated</h2>
            <p>Subscribe to our newsletter and get the latest book recommendations, exclusive deals, and more.</p>
            <form class="newsletter-form" id="newsletter-form">
                <input type="email" placeholder="Your email address" required>
                <button type="submit">Subscribe</button>
            </form>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="footer-column">
                    <h3>The Definitive Word</h3>
                    <p>Your premier destination for quality ebooks. Discover, read, and enjoy literature in the digital age.</p>
                    <div class="social-links">
                        <a href="#"><i class="fab fa-facebook-f"></i></a>
                        <a href="#"><i class="fab fa-twitter"></i></a>
                        <a href="#"><i class="fab fa-instagram"></i></a>
                        <a href="#"><i class="fab fa-pinterest"></i></a>
                    </div>
                </div>
                <div class="footer-column">
                    <h3>Quick Links</h3>
                    <ul>
                        <li><a href="#">Home</a></li>
                        <li><a href="#">About Us</a></li>
                        <li><a href="#">Contact</a></li>
                        <li><a href="#">FAQ</a></li>
                        <li><a href="#">Blog</a></li>
                    </ul>
                </div>
                <div class="footer-column">
                    <h3>Categories</h3>
                    <ul>
                        <li><a href="#">Fiction</a></li>
                        <li><a href="#">Non-Fiction</a></li>
                        <li><a href="#">Science</a></li>
                        <li><a href="#">Business</a></li>
                        <li><a href="#">Self-Help</a></li>
                    </ul>
                </div>
                <div class="footer-column">
                    <h3>Contact Us</h3>
                    <ul>
                        <li><i class="fas fa-map-marker-alt"></i> 123 Book Street, Knowledge City</li>
                        <li><i class="fas fa-phone"></i> +1 (555) 123-4567</li>
                        <li><i class="fas fa-envelope"></i> info@thedefinitiveword.com</li>
                    </ul>
                </div>
            </div>
            <div class="copyright">
                <p>&copy; 2023 The Definitive Word. All rights reserved.</p>
            </div>
        </div>
    </footer>

    <!-- Cart Modal -->
    <div class="cart-modal" id="cart-modal">
        <div class="cart-header">
            <h2>Your Cart</h2>
            <button class="close-cart" id="close-cart"><i class="fas fa-times"></i></button>
        </div>
        <div class="cart-items" id="cart-items">
            <!-- Cart items will be added here -->
        </div>
        <div class="cart-total">
            <span>Total:</span>
            <span id="cart-total">$0.00</span>
        </div>
        <div class="cart-actions">
            <button class="btn btn-accent" style="width: 100%;">Proceed to Checkout</button>
        </div>
    </div>

    <!-- Wishlist Modal -->
    <div class="modal" id="wishlist-modal">
        <div class="modal-content">
            <div class="modal-header">
                <h2>Your Wishlist</h2>
                <button class="close-modal" data-modal="wishlist-modal"><i class="fas fa-times"></i></button>
            </div>
            <div class="modal-body">
                <div id="wishlist-items">
                    <!-- Wishlist items will be added here -->
                </div>
            </div>
        </div>
    </div>

    <!-- Overlay -->
    <div class="overlay" id="overlay"></div>

    <script>
        // Enhanced book data
        const books = [
            {
                id: 1,
                title: "The Silent Observer",
                author: "Megan Foster",
                price: 12.99,
                originalPrice: 15.99,
                image: "https://images.unsplash.com/photo-1544947950-fa07a98d237f?ixlib=rb-4.0.3&auto=format&fit=crop&w=500&q=80",
                category: "Mystery",
                description: "A thrilling mystery novel about a quiet observer who witnesses a crime.",
                badge: "Bestseller"
            },
            {
                id: 2,
                title: "Digital Revolution",
                author: "Alex Chen",
                price: 14.99,
                originalPrice: null,
                image: "https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?ixlib=rb-4.0.3&auto=format&fit=crop&w=500&q=80",
                category: "Technology",
                description: "Exploring the impact of digital technology on modern society.",
                badge: "New"
            },
            {
                id: 3,
                title: "Echoes of Tomorrow",
                author: "Sarah Johnson",
                price: 10.99,
                originalPrice: 12.99,
                image: "https://images.unsplash.com/photo-1512820790803-83ca734da794?ixlib=rb-4.0.3&auto=format&fit=crop&w=500&q=80",
                category: "Science Fiction",
                description: "A science fiction adventure through time and space.",
                badge: "Sale"
            },
            {
                id: 4,
                title: "The Mindful Entrepreneur",
                author: "David Wilson",
                price: 16.99,
                originalPrice: null,
                image: "https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?ixlib=rb-4.0.3&auto=format&fit=crop&w=500&q=80",
                category: "Business",
                description: "A guide to mindfulness in business and entrepreneurship.",
                badge: null
            },
            {
                id: 5,
                title: "Business Strategy Fundamentals",
                author: "Robert Kim",
                price: 18.99,
                originalPrice: 22.99,
                image: "https://images.unsplash.com/photo-1544947950-fa07a98d237f?ixlib=rb-4.0.3&auto=format&fit=crop&w=500&q=80",
                category: "Business",
                description: "Essential strategies for business growth and success.",
                badge: "Sale"
            },
            {
                id: 6,
                title: "Romantic Escapades",
                author: "Emma Thompson",
                price: 11.99,
                originalPrice: null,
                image: "https://images.unsplash.com/photo-1512820790803-83ca734da794?ixlib=rb-4.0.3&auto=format&fit=crop&w=500&q=80",
                category: "Romance",
                description: "A heartwarming romance about unexpected love.",
                badge: "Popular"
            },
            {
                id: 7,
                title: "Future Technologies",
                author: "Alex Chen",
                price: 15.99,
                originalPrice: 19.99,
                image: "https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?ixlib=rb-4.0.3&auto=format&fit=crop&w=500&q=80",
                category: "Technology",
                description: "Exploring emerging technologies and their potential impact.",
                badge: "New"
            },
            {
                id: 8,
                title: "The Mystery of Hollow Creek",
                author: "Megan Foster",
                price: 13.99,
                originalPrice: null,
                image: "https://images.unsplash.com/photo-1544947950-fa07a98d237f?ixlib=rb-4.0.3&auto=format&fit=crop&w=500&q=80",
                category: "Mystery",
                description: "A small town with a big secret in this gripping mystery.",
                badge: "Bestseller"
            }
        ];

        // Initialize cart and wishlist
        let cart = [];
        let wishlist = [];

        // DOM Elements
        const cartCount = document.querySelector('.cart-count');
        const wishlistCount = document.querySelector('.wishlist-count');
        const cartModal = document.getElementById('cart-modal');
        const wishlistModal = document.getElementById('wishlist-modal');
        const overlay = document.getElementById('overlay');
        const closeCart = document.getElementById('close-cart');
        const cartItems = document.getElementById('cart-items');
        const cartTotal = document.getElementById('cart-total');
        const cartIcon = document.querySelector('.cart-icon');
        const wishlistIcon = document.getElementById('wishlist-icon');
        const wishlistItems = document.getElementById('wishlist-items');

        // Search elements
        const searchInput = document.getElementById('search-input');
        const searchResults = document.getElementById('search-results');
        const searchResultsSection = document.getElementById('search-results-section');
        const searchResultsBooks = document.getElementById('search-results-books');
        const searchResultsTitle = document.getElementById('search-results-title');
        const clearSearchBtn = document.getElementById('clear-search');
        const featuredSection = document.getElementById('featured-section');

        // Display books function
        function displayBooks(booksArray, container) {
            container.innerHTML = '';
            
            if (booksArray.length === 0) {
                container.innerHTML = `
                    <div class="empty-state">
                        <i class="fas fa-book-open"></i>
                        <h3>No books found</h3>
                        <p>Try adjusting your search or browse our categories</p>
                    </div>
                `;
                return;
            }
            
            booksArray.forEach(book => {
                const bookCard = document.createElement('div');
                bookCard.className = 'book-card';
                
                const priceHTML = book.originalPrice 
                    ? `<div class="price"><span class="original-price">$${book.originalPrice}</span> <span class="sale-price">$${book.price}</span></div>`
                    : `<div class="price">$${book.price}</div>`;
                
                const badgeHTML = book.badge 
                    ? `<div class="book-badge">${book.badge}</div>` 
                    : '';
                
                // Check if book is in wishlist
                const isInWishlist = wishlist.some(item => item.id === book.id);
                const wishlistIconClass = isInWishlist ? 'fas fa-heart' : 'far fa-heart';
                const wishlistTitle = isInWishlist ? 'Remove from Wishlist' : 'Add to Wishlist';
                
                bookCard.innerHTML = `
                    ${badgeHTML}
                    <div class="book-cover">
                        <img src="${book.image}" alt="${book.title}">
                        <div class="book-actions">
                            <button class="action-btn add-to-wishlist" data-id="${book.id}" title="${wishlistTitle}">
                                <i class="${wishlistIconClass}"></i>
                            </button>
                            <button class="action-btn quick-view" data-id="${book.id}" title="Quick View">
                                <i class="fas fa-eye"></i>
                            </button>
                        </div>
                    </div>
                    <div class="book-info">
                        <h3 class="book-title">${book.title}</h3>
                        <p class="book-author">by ${book.author}</p>
                        <div class="book-price">
                            ${priceHTML}
                            <button class="btn add-to-cart" data-id="${book.id}">Add to Cart</button>
                        </div>
                    </div>
                `;
                
                container.appendChild(bookCard);
            });
        }

        // Initial display of featured books
        displayBooks(books, document.getElementById('featured-books'));

        // Search functionality
        function performSearch(query) {
            if (!query.trim()) {
                searchResultsSection.classList.remove('active');
                featuredSection.style.display = 'block';
                return;
            }
            
            const lowerQuery = query.toLowerCase();
            
            // Filter books based on search query
            const filteredBooks = books.filter(book => 
                book.title.toLowerCase().includes(lowerQuery) ||
                book.author.toLowerCase().includes(lowerQuery) ||
                book.category.toLowerCase().includes(lowerQuery) ||
                book.description.toLowerCase().includes(lowerQuery)
            );
            
            // Update UI with search results
            searchResultsTitle.textContent = `Search Results for "${query}" (${filteredBooks.length} books found)`;
            displayBooks(filteredBooks, searchResultsBooks);
            
            // Show search results section, hide featured section
            searchResultsSection.classList.add('active');
            featuredSection.style.display = 'none';
            
            // Hide the dropdown search results
            searchResults.classList.remove('active');
        }

        // Real-time search suggestions
        function showSearchSuggestions(query) {
            if (!query.trim()) {
                searchResults.classList.remove('active');
                return;
            }
            
            const lowerQuery = query.toLowerCase();
            const matchedBooks = books.filter(book => 
                book.title.toLowerCase().includes(lowerQuery) ||
                book.author.toLowerCase().includes(lowerQuery)
            ).slice(0, 5); // Limit to 5 suggestions
            
            if (matchedBooks.length === 0) {
                searchResults.innerHTML = '<div class="search-result-item">No results found</div>';
            } else {
                searchResults.innerHTML = matchedBooks.map(book => `
                    <div class="search-result-item" data-id="${book.id}">
                        <img src="${book.image}" alt="${book.title}">
                        <div class="search-result-info">
                            <div class="search-result-title">${book.title}</div>
                            <div class="search-result-author">by ${book.author}</div>
                        </div>
                    </div>
                `).join('');
            }
            
            searchResults.classList.add('active');
        }

        // Event listeners for search
        searchInput.addEventListener('input', function() {
            showSearchSuggestions(this.value);
        });

        searchInput.addEventListener('keypress', function(e) {
            if (e.key === 'Enter') {
                performSearch(this.value);
            }
        });

        // Click on search suggestion
        searchResults.addEventListener('click', function(e) {
            if (e.target.closest('.search-result-item')) {
                const item = e.target.closest('.search-result-item');
                const bookId = parseInt(item.getAttribute('data-id'));
                const book = books.find(b => b.id === bookId);
                
                if (book) {
                    searchInput.value = book.title;
                    performSearch(book.title);
                }
            }
        });

        // Clear search
        clearSearchBtn.addEventListener('click', function() {
            searchInput.value = '';
            searchResultsSection.classList.remove('active');
            featuredSection.style.display = 'block';
            searchResults.classList.remove('active');
        });

        // Category search
        document.querySelectorAll('.category-card, nav a[data-category]').forEach(element => {
            element.addEventListener('click', function(e) {
                e.preventDefault();
                const category = this.getAttribute('data-category');
                searchInput.value = category;
                performSearch(category);
            });
        });

        // Close search results when clicking outside
        document.addEventListener('click', function(e) {
            if (!e.target.closest('.search-bar')) {
                searchResults.classList.remove('active');
            }
        });

        // Add to cart functionality
        document.addEventListener('click', function(e) {
            if (e.target.classList.contains('add-to-cart') || e.target.closest('.add-to-cart')) {
                const button = e.target.classList.contains('add-to-cart') ? e.target : e.target.closest('.add-to-cart');
                const bookId = parseInt(button.getAttribute('data-id'));
                const book = books.find(b => b.id === bookId);
                
                // Check if book is already in cart
                const existingItem = cart.find(item => item.id === bookId);
                
                if (existingItem) {
                    existingItem.quantity += 1;
                } else {
                    cart.push({
                        ...book,
                        quantity: 1
                    });
                }
                
                updateCart();
                
                // Show confirmation
                const originalText = button.textContent;
                button.textContent = 'Added!';
                button.style.background = 'var(--success)';
                
                setTimeout(() => {
                    button.textContent = originalText;
                    button.style.background = '';
                }, 1500);
            }
        });

        // Add to wishlist functionality
        document.addEventListener('click', function(e) {
            if (e.target.classList.contains('add-to-wishlist') || e.target.closest('.add-to-wishlist')) {
                const button = e.target.classList.contains('add-to-wishlist') ? e.target : e.target.closest('.add-to-wishlist');
                const bookId = parseInt(button.getAttribute('data-id'));
                const book = books.find(b => b.id === bookId);
                
                // Check if book is already in wishlist
                const existingIndex = wishlist.findIndex(item => item.id === bookId);
                
                if (existingIndex !== -1) {
                    // Remove from wishlist
                    wishlist.splice(existingIndex, 1);
                    button.innerHTML = '<i class="far fa-heart"></i>';
                    button.title = 'Add to Wishlist';
                } else {
                    // Add to wishlist
                    wishlist.push(book);
                    button.innerHTML = '<i class="fas fa-heart"></i>';
                    button.title = 'Remove from Wishlist';
                }
                
                updateWishlist();
            }
        });

        // Open cart
        cartIcon.addEventListener('click', function(e) {
            e.preventDefault();
            cartModal.classList.add('active');
            overlay.classList.add('active');
        });

        // Close cart
        closeCart.addEventListener('click', function() {
            cartModal.classList.remove('active');
            overlay.classList.remove('active');
        });

        // Open wishlist
        wishlistIcon.addEventListener('click', function(e) {
            e.preventDefault();
            wishlistModal.classList.add('active');
            overlay.classList.add('active');
        });

        // Close modals
        document.querySelectorAll('.close-modal').forEach(button => {
            button.addEventListener('click', function() {
                const modalId = this.getAttribute('data-modal');
                document.getElementById(modalId).classList.remove('active');
                overlay.classList.remove('active');
            });
        });

        overlay.addEventListener('click', function() {
            cartModal.classList.remove('active');
            document.querySelectorAll('.modal').forEach(modal => {
                modal.classList.remove('active');
            });
            overlay.classList.remove('active');
        });

        // Update cart
        function updateCart() {
            // Update cart count
            const totalItems = cart.reduce((total, item) => total + item.quantity, 0);
            cartCount.textContent = totalItems;
            
            // Update cart items
            cartItems.innerHTML = '';
            
            if (cart.length === 0) {
                cartItems.innerHTML = `
                    <div class="empty-state">
                        <i class="fas fa-shopping-cart"></i>
                        <h3>Your cart is empty</h3>
                        <p>Add some books to get started</p>
                    </div>
                `;
                cartTotal.textContent = '$0.00';
                return;
            }
            
            let totalPrice = 0;
            
            cart.forEach(item => {
                const itemTotal = item.price * item.quantity;
                totalPrice += itemTotal;
                
                const cartItem = document.createElement('div');
                cartItem.className = 'cart-item';
                cartItem.innerHTML = `
                    <img src="${item.image}" alt="${item.title}">
                    <div class="cart-item-details">
                        <h4 class="cart-item-title">${item.title}</h4>
                        <p>by ${item.author}</p>
                        <div class="cart-item-price">$${item.price} x ${item.quantity}</div>
                        <button class="cart-item-remove" data-id="${item.id}">Remove</button>
                    </div>
                `;
                
                cartItems.appendChild(cartItem);
            });
            
            cartTotal.textContent = `$${totalPrice.toFixed(2)}`;
            
            // Add event listeners to remove buttons
            document.querySelectorAll('.cart-item-remove').forEach(button => {
                button.addEventListener('click', function() {
                    const itemId = parseInt(this.getAttribute('data-id'));
                    cart = cart.filter(item => item.id !== itemId);
                    updateCart();
                });
            });
        }

        // Update wishlist
        function updateWishlist() {
            // Update wishlist count
            wishlistCount.textContent = wishlist.length;
            
            // Update wishlist items
            wishlistItems.innerHTML = '';
            
            if (wishlist.length === 0) {
                wishlistItems.innerHTML = `
                    <div class="empty-state">
                        <i class="fas fa-heart"></i>
                        <h3>Your wishlist is empty</h3>
                        <p>Add some books you'd like to save for later</p>
                    </div>
                `;
                return;
            }
            
            wishlist.forEach(book => {
                const wishlistItem = document.createElement('div');
                wishlistItem.className = 'cart-item';
                wishlistItem.innerHTML = `
                    <img src="${book.image}" alt="${book.title}">
                    <div class="cart-item-details">
                        <h4 class="cart-item-title">${book.title}</h4>
                        <p>by ${book.author}</p>
                        <div class="cart-item-price">$${book.price}</div>
                        <button class="btn add-to-cart" data-id="${book.id}" style="padding: 5px 10px; font-size: 0.9rem;">Add to Cart</button>
                        <button class="cart-item-remove remove-from-wishlist" data-id="${book.id}">Remove</button>
                    </div>
                `;
                
                wishlistItems.appendChild(wishlistItem);
            });
            
            // Add event listeners to remove buttons
            document.querySelectorAll('.remove-from-wishlist').forEach(button => {
                button.addEventListener('click', function() {
                    const itemId = parseInt(this.getAttribute('data-id'));
                    wishlist = wishlist.filter(item => item.id !== itemId);
                    updateWishlist();
                    
                    // Also update the heart icons in the book cards
                    const wishlistButton = document.querySelector(`.add-to-wishlist[data-id="${itemId}"]`);
                    if (wishlistButton) {
                        wishlistButton.innerHTML = '<i class="far fa-heart"></i>';
                        wishlistButton.title = 'Add to Wishlist';
                    }
                });
            });
        }

        // Newsletter form
        document.getElementById('newsletter-form').addEventListener('submit', function(e) {
            e.preventDefault();
            const email = this.querySelector('input').value;
            if (email) {
                alert(`Thank you for subscribing with: ${email}`);
                this.reset();
            }
        });

        // Initialize
        updateCart();
        updateWishlist();
    </script>
</body>
</html>
