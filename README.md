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
            --shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
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

        .user-actions a {
            margin-left: 15px;
            color: var(--primary);
            font-size: 1.2rem;
        }

        .cart-count {
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

        .cart-icon {
            position: relative;
        }

        nav {
            background: var(--primary);
            padding: 10px 0;
        }

        nav ul {
            display: flex;
            justify-content: center;
        }

        nav li {
            margin: 0 15px;
        }

        nav a {
            color: white;
            font-weight: 500;
            transition: all 0.3s ease;
        }

        nav a:hover {
            color: var(--secondary);
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

        .btn {
            display: inline-block;
            padding: 12px 25px;
            background: var(--secondary);
            color: white;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            transition: all 0.3s ease;
            font-weight: 600;
            margin: 5px;
        }

        .btn:hover {
            background: #2980b9;
            transform: translateY(-2px);
        }

        .btn-accent {
            background: var(--accent);
        }

        .btn-accent:hover {
            background: #c0392b;
        }

        /* Featured Books */
        .section-title {
            text-align: center;
            margin: 50px 0 30px;
            color: var(--primary);
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
            transition: all 0.3s ease;
        }

        .book-card:hover {
            transform: translateY(-5px);
        }

        .book-cover {
            height: 300px;
            overflow: hidden;
        }

        .book-cover img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .book-info {
            padding: 15px;
        }

        .book-title {
            font-weight: 600;
            margin-bottom: 5px;
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
            transition: all 0.3s ease;
        }

        .category-card:hover {
            transform: translateY(-5px);
            background: var(--secondary);
            color: white;
        }

        .category-card i {
            font-size: 2.5rem;
            margin-bottom: 15px;
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

        .copyright {
            text-align: center;
            padding-top: 20px;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
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
            transition: all 0.3s ease;
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

        .close-cart {
            background: none;
            border: none;
            font-size: 1.5rem;
            cursor: pointer;
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

        .cart-total {
            padding: 20px;
            border-top: 1px solid #eee;
            display: flex;
            justify-content: space-between;
            font-weight: 700;
        }

        .overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.5);
            z-index: 1000;
            display: none;
        }

        .overlay.active {
            display: block;
        }

        @media (max-width: 768px) {
            .header-top {
                flex-direction: column;
            }
            .search-bar {
                margin: 15px 0;
                max-width: 100%;
            }
            .hero h1 {
                font-size: 2.2rem;
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
                    <input type="text" placeholder="Search for books, authors, or categories...">
                    <button><i class="fas fa-search"></i></button>
                </div>
                <div class="user-actions">
                    <a href="#"><i class="fas fa-user"></i></a>
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
                    <li><a href="#">Fiction</a></li>
                    <li><a href="#">Non-Fiction</a></li>
                    <li><a href="#">Science</a></li>
                    <li><a href="#">Technology</a></li>
                    <li><a href="#">Business</a></li>
                    <li><a href="#">Self-Help</a></li>
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
            <a href="#" class="btn">View Bestsellers</a>
        </div>
    </section>

    <!-- Featured Books -->
    <section class="container">
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
                <div class="category-card">
                    <i class="fas fa-rocket"></i>
                    <h3>Science Fiction</h3>
                    <p>Explore other worlds and futures</p>
                </div>
                <div class="category-card">
                    <i class="fas fa-heart"></i>
                    <h3>Romance</h3>
                    <p>Stories of love and connection</p>
                </div>
                <div class="category-card">
                    <i class="fas fa-user-secret"></i>
                    <h3>Mystery</h3>
                    <p>Unravel puzzles and crimes</p>
                </div>
                <div class="category-card">
                    <i class="fas fa-chart-line"></i>
                    <h3>Business</h3>
                    <p>Grow your career and wealth</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="container">
            <div class="footer-content">
                <div>
                    <h3>The Definitive Word</h3>
                    <p>Your premier destination for quality ebooks.</p>
                </div>
                <div>
                    <h3>Quick Links</h3>
                    <ul>
                        <li><a href="#">Home</a></li>
                        <li><a href="#">About Us</a></li>
                        <li><a href="#">Contact</a></li>
                    </ul>
                </div>
                <div>
                    <h3>Categories</h3>
                    <ul>
                        <li><a href="#">Fiction</a></li>
                        <li><a href="#">Non-Fiction</a></li>
                        <li><a href="#">Business</a></li>
                    </ul>
                </div>
            </div>
            <div class="copyright">
                <p>&copy; 2023 The Definitive Word. All rights reserved.</p>
            </div>
        </div>
    </footer>

    <!-- Cart Modal -->
    <div class="overlay" id="overlay"></div>
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
        <div class="cart-actions" style="padding: 20px;">
            <button class="btn btn-accent" style="width: 100%;">Checkout</button>
        </div>
    </div>

    <script>
        // Book data
        const books = [
            {
                id: 1,
                title: "The Silent Observer",
                author: "Megan Foster",
                price: 12.99,
                originalPrice: 15.99,
                image: "https://images.unsplash.com/photo-1544947950-fa07a98d237f?ixlib=rb-4.0.3&auto=format&fit=crop&w=500&q=80",
                category: "Mystery"
            },
            {
                id: 2,
                title: "Digital Revolution",
                author: "Alex Chen",
                price: 14.99,
                originalPrice: null,
                image: "https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?ixlib=rb-4.0.3&auto=format&fit=crop&w=500&q=80",
                category: "Technology"
            },
            {
                id: 3,
                title: "Echoes of Tomorrow",
                author: "Sarah Johnson",
                price: 10.99,
                originalPrice: 12.99,
                image: "https://images.unsplash.com/photo-1512820790803-83ca734da794?ixlib=rb-4.0.3&auto=format&fit=crop&w=500&q=80",
                category: "Science Fiction"
            },
            {
                id: 4,
                title: "The Mindful Entrepreneur",
                author: "David Wilson",
                price: 16.99,
                originalPrice: null,
                image: "https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?ixlib=rb-4.0.3&auto=format&fit=crop&w=500&q=80",
                category: "Business"
            }
        ];

        // Cart functionality
        let cart = [];
        const cartCount = document.querySelector('.cart-count');
        const cartModal = document.getElementById('cart-modal');
        const overlay = document.getElementById('overlay');
        const closeCart = document.getElementById('close-cart');
        const cartItems = document.getElementById('cart-items');
        const cartTotal = document.getElementById('cart-total');
        const cartIcon = document.querySelector('.cart-icon');

        // Display featured books
        const featuredBooksContainer = document.getElementById('featured-books');
        
        books.forEach(book => {
            const bookCard = document.createElement('div');
            bookCard.className = 'book-card';
            
            const priceHTML = book.originalPrice 
                ? `<div class="price"><span class="original-price">$${book.originalPrice}</span> <span class="sale-price">$${book.price}</span></div>`
                : `<div class="price">$${book.price}</div>`;
            
            bookCard.innerHTML = `
                <div class="book-cover">
                    <img src="${book.image}" alt="${book.title}">
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
            
            featuredBooksContainer.appendChild(bookCard);
        });

        // Add to cart functionality
        document.addEventListener('click', function(e) {
            if (e.target.classList.contains('add-to-cart')) {
                const bookId = parseInt(e.target.getAttribute('data-id'));
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
                e.target.textContent = 'Added!';
                e.target.style.background = 'var(--success)';
                
                setTimeout(() => {
                    e.target.textContent = 'Add to Cart';
                    e.target.style.background = '';
                }, 1500);
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

        overlay.addEventListener('click', function() {
            cartModal.classList.remove('active');
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
                cartItems.innerHTML = '<p>Your cart is empty</p>';
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
                        <h4>${item.title}</h4>
                        <p>by ${item.author}</p>
                        <div>$${item.price} x ${item.quantity}</div>
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

        // Initialize cart
        updateCart();
    </script>
</body>
</html>
