<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>The Definitive Word - FULL CONTROL Ebook Store</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary: #2c3e50;
            --secondary: #3498db;
            --accent: #e74c3c;
            --light: #ecf0f1;
            --background: #f9f9f9;
            --text-color: #333;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            line-height: 1.6;
            color: var(--text-color);
            background: var(--background);
        }

        .container {
            width: 90%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 15px;
        }

        /* === ADMIN PANEL - ALWAYS VISIBLE === */
        .admin-panel {
            background: #1a252f;
            color: white;
            padding: 15px 0;
            position: sticky;
            top: 0;
            z-index: 1000;
            box-shadow: 0 2px 10px rgba(0,0,0,0.3);
        }

        .admin-controls {
            display: flex;
            gap: 10px;
            flex-wrap: wrap;
            align-items: center;
        }

        .admin-section {
            background: #2c3e50;
            padding: 10px;
            border-radius: 5px;
            margin: 5px 0;
        }

        .admin-section h4 {
            margin-bottom: 8px;
            color: #3498db;
        }

        .admin-btn {
            background: var(--secondary);
            color: white;
            border: none;
            padding: 8px 15px;
            border-radius: 4px;
            cursor: pointer;
            margin: 2px;
            font-weight: 600;
            transition: all 0.3s ease;
        }

        .admin-btn:hover {
            background: #2980b9;
            transform: translateY(-2px);
        }

        .admin-btn.danger {
            background: var(--accent);
        }

        .admin-btn.danger:hover {
            background: #c0392b;
        }

        .admin-btn.success {
            background: #27ae60;
        }

        .admin-btn.success:hover {
            background: #219a52;
        }

        /* Color Customization */
        .color-picker {
            display: flex;
            gap: 5px;
            flex-wrap: wrap;
        }

        .color-option {
            width: 30px;
            height: 30px;
            border-radius: 50%;
            cursor: pointer;
            border: 2px solid transparent;
            transition: all 0.3s ease;
        }

        .color-option:hover {
            transform: scale(1.1);
        }

        .color-option.active {
            border-color: white;
            transform: scale(1.1);
        }

        /* Header */
        header {
            background: var(--primary);
            color: white;
            padding: 20px 0;
        }

        .header-top {
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
        }

        .logo {
            display: flex;
            align-items: center;
            font-size: 2rem;
            font-weight: 700;
        }

        .logo i {
            color: var(--secondary);
            margin-right: 10px;
        }

        .store-title {
            font-size: 1.5rem;
            font-weight: 300;
            opacity: 0.9;
        }

        .search-bar {
            flex: 1;
            max-width: 400px;
            margin: 0 20px;
        }

        .search-bar input {
            width: 100%;
            padding: 10px 15px;
            border: none;
            border-radius: 25px;
            font-size: 1rem;
        }

        .cart-count {
            background: var(--accent);
            color: white;
            border-radius: 50%;
            width: 20px;
            height: 20px;
            font-size: 0.8rem;
            display: flex;
            align-items: center;
            justify-content: center;
            position: absolute;
            top: -5px;
            right: -5px;
        }

        .cart-icon {
            position: relative;
            font-size: 1.3rem;
        }

        /* Hero Section */
        .hero {
            background: linear-gradient(135deg, var(--primary) 0%, var(--secondary) 100%);
            color: white;
            padding: 80px 0;
            text-align: center;
        }

        .hero h1 {
            font-size: 3rem;
            margin-bottom: 20px;
        }

        .btn {
            display: inline-block;
            padding: 12px 25px;
            background: var(--accent);
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-weight: 600;
            margin: 5px;
            text-decoration: none;
            transition: all 0.3s ease;
        }

        .btn:hover {
            background: #c0392b;
            transform: translateY(-2px);
        }

        /* Books Grid */
        .books-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 30px;
            margin: 40px 0;
        }

        .book-card {
            background: white;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            transition: all 0.3s ease;
            border: 2px solid transparent;
        }

        .book-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 25px rgba(0,0,0,0.15);
            border-color: var(--secondary);
        }

        .book-cover {
            height: 320px;
            overflow: hidden;
        }

        .book-cover img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.3s ease;
        }

        .book-card:hover .book-cover img {
            transform: scale(1.05);
        }

        .book-info {
            padding: 20px;
        }

        .book-title {
            font-weight: 600;
            margin-bottom: 5px;
            font-size: 1.2rem;
            color: var(--primary);
        }

        .book-author {
            color: #666;
            margin-bottom: 10px;
        }

        .book-price {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .price {
            font-weight: 700;
            color: var(--accent);
            font-size: 1.3rem;
        }

        /* Modal */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0,0,0,0.5);
            z-index: 2000;
            align-items: center;
            justify-content: center;
        }

        .modal.active {
            display: flex;
        }

        .modal-content {
            background: white;
            padding: 30px;
            border-radius: 10px;
            max-width: 500px;
            width: 90%;
            max-height: 80vh;
            overflow-y: auto;
        }

        .form-group {
            margin-bottom: 20px;
        }

        .form-group label {
            display: block;
            margin-bottom: 8px;
            font-weight: 600;
            color: var(--primary);
        }

        .form-group input, .form-group textarea, .form-group select {
            width: 100%;
            padding: 10px 15px;
            border: 2px solid #ddd;
            border-radius: 5px;
            font-size: 1rem;
            transition: border-color 0.3s ease;
        }

        .form-group input:focus, .form-group textarea:focus, .form-group select:focus {
            border-color: var(--secondary);
            outline: none;
        }

        /* Cart Modal */
        .cart-modal {
            position: fixed;
            top: 0;
            right: -400px;
            width: 380px;
            height: 100vh;
            background: white;
            box-shadow: -5px 0 15px rgba(0,0,0,0.1);
            transition: right 0.3s ease;
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
            border-bottom: 2px solid #eee;
            background: var(--primary);
            color: white;
        }

        .cart-items {
            padding: 20px;
        }

        .cart-item {
            display: flex;
            margin-bottom: 15px;
            padding-bottom: 15px;
            border-bottom: 1px solid #eee;
        }

        .cart-item img {
            width: 60px;
            height: 80px;
            object-fit: cover;
            margin-right: 15px;
            border-radius: 5px;
        }

        .cart-total {
            padding: 20px;
            border-top: 2px solid #eee;
            display: flex;
            justify-content: space-between;
            font-weight: 700;
            font-size: 1.2rem;
            background: var(--light);
        }

        /* Footer */
        footer {
            background: var(--primary);
            color: white;
            padding: 40px 0 20px;
            text-align: center;
        }

        /* Notification */
        .notification {
            position: fixed;
            top: 20px;
            left: 50%;
            transform: translateX(-50%);
            background: #27ae60;
            color: white;
            padding: 15px 25px;
            border-radius: 5px;
            box-shadow: 0 4px 15px rgba(0,0,0,0.2);
            z-index: 3000;
            display: none;
        }

        .notification.show {
            display: block;
        }

        .notification.error {
            background: #e74c3c;
        }

        @media (max-width: 768px) {
            .admin-controls {
                flex-direction: column;
                align-items: stretch;
            }
            
            .header-top {
                flex-direction: column;
                gap: 15px;
            }
            
            .search-bar {
                margin: 10px 0;
                max-width: 100%;
            }
            
            .hero h1 {
                font-size: 2rem;
            }
            
            .cart-modal {
                width: 100%;
                right: -100%;
            }
        }
    </style>
</head>
<body>
    <!-- Notification -->
    <div class="notification" id="notification"></div>

    <!-- === ADMIN CONTROL PANEL - ALWAYS VISIBLE === -->
    <div class="admin-panel">
        <div class="container">
            <h3 style="color: #3498db; margin-bottom: 15px; text-align: center;">
                🎛️ STORE CONTROL PANEL - You're in control!
            </h3>
            
            <div class="admin-controls">
                <!-- Book Management -->
                <div class="admin-section">
                    <h4>📚 Book Management</h4>
                    <button class="admin-btn success" onclick="openModal('addBookModal')">
                        <i class="fas fa-plus"></i> Add New Book
                    </button>
                    <button class="admin-btn" onclick="openModal('bookListModal')">
                        <i class="fas fa-list"></i> Manage Books
                    </button>
                </div>

                <!-- Store Customization -->
                <div class="admin-section">
                    <h4>🎨 Store Colors</h4>
                    <div class="color-picker">
                        <div class="color-option active" style="background: #2c3e50;" onclick="changeColor('primary', '#2c3e50')"></div>
                        <div class="color-option" style="background: #3498db;" onclick="changeColor('primary', '#3498db')"></div>
                        <div class="color-option" style="background: #e74c3c;" onclick="changeColor('primary', '#e74c3c')"></div>
                        <div class="color-option" style="background: #27ae60;" onclick="changeColor('primary', '#27ae60')"></div>
                        <div class="color-option" style="background: #8e44ad;" onclick="changeColor('primary', '#8e44ad')"></div>
                    </div>
                </div>

                <!-- Store Actions -->
                <div class="admin-section">
                    <h4>⚡ Quick Actions</h4>
                    <button class="admin-btn" onclick="addSampleBooks()">
                        <i class="fas fa-magic"></i> Add Sample Books
                    </button>
                    <button class="admin-btn danger" onclick="resetStore()">
                        <i class="fas fa-trash"></i> Reset Everything
                    </button>
                </div>

                <!-- Store Info -->
                <div class="admin-section">
                    <h4>📊 Store Stats</h4>
                    <div style="color: #ecf0f1; font-size: 0.9rem;">
                        Books: <span id="bookCount">0</span> | 
                        Cart: <span id="cartCountDisplay">0</span> items
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- Add Book Modal -->
    <div class="modal" id="addBookModal">
        <div class="modal-content">
            <h2 style="margin-bottom: 20px; color: var(--primary);">📖 Add New Book</h2>
            <form id="addBookForm">
                <div class="form-group">
                    <label>Book Title *</label>
                    <input type="text" id="bookTitle" required placeholder="Enter an amazing book title">
                </div>
                <div class="form-group">
                    <label>Author *</label>
                    <input type="text" id="bookAuthor" required placeholder="Who wrote this book?">
                </div>
                <div class="form-group">
                    <label>Price ($) *</label>
                    <input type="number" id="bookPrice" step="0.01" required placeholder="9.99">
                </div>
                <div class="form-group">
                    <label>Category</label>
                    <select id="bookCategory">
                        <option value="Fiction">Fiction</option>
                        <option value="Non-Fiction">Non-Fiction</option>
                        <option value="Business">Business</option>
                        <option value="Technology">Technology</option>
                        <option value="Self-Help">Self-Help</option>
                        <option value="Mystery">Mystery</option>
                    </select>
                </div>
                <div class="form-group">
                    <label>Book Description</label>
                    <textarea id="bookDescription" placeholder="What's this book about?"></textarea>
                </div>
                <div class="form-group">
                    <label>Cover Image URL</label>
                    <input type="url" id="bookImage" placeholder="https://example.com/book-cover.jpg">
                </div>
                
                <button type="submit" class="btn" style="width: 100%; margin-top: 15px; background: var(--secondary);">
                    ✅ ADD BOOK TO STORE
                </button>
            </form>
            <button class="btn" onclick="closeAllModals()" style="width: 100%; margin-top: 10px; background: #666;">
                ❌ CANCEL
            </button>
        </div>
    </div>

    <!-- Book List Modal -->
    <div class="modal" id="bookListModal">
        <div class="modal-content">
            <h2 style="margin-bottom: 20px; color: var(--primary);">📚 Manage Your Books</h2>
            <div id="bookListContent">
                <!-- Books will be listed here -->
            </div>
            <button class="btn" onclick="closeAllModals()" style="width: 100%; margin-top: 15px; background: #666;">
                ✅ CLOSE
            </button>
        </div>
    </div>

    <!-- Cart Modal -->
    <div class="cart-modal" id="cartModal">
        <div class="cart-header">
            <h2>🛒 Your Shopping Cart</h2>
            <button onclick="closeCart()" style="background: none; border: none; font-size: 1.5rem; cursor: pointer; color: white;">❌</button>
        </div>
        <div class="cart-items" id="cartItems">
            <!-- Cart items will appear here -->
        </div>
        <div class="cart-total">
            <span>Total:</span>
            <span id="cartTotal">$0.00</span>
        </div>
        <div style="padding: 20px;">
            <button class="btn" style="width: 100%;" onclick="checkout()">
                💳 CHECKOUT NOW
            </button>
        </div>
    </div>

    <!-- Header -->
    <header>
        <div class="container">
            <div class="header-top">
                <div>
                    <div class="logo">
                        <i class="fas fa-book-open"></i>
                        The Definitive Word
                    </div>
                    <div class="store-title">Your Custom Ebook Store</div>
                </div>
                <div class="search-bar">
                    <input type="text" placeholder="🔍 Search books..." onkeypress="handleSearch(event)">
                </div>
                <div class="user-actions">
                    <a href="#" class="cart-icon" onclick="openCart()">
                        <i class="fas fa-shopping-cart"></i>
                        <span class="cart-count" id="cartCount">0</span>
                    </a>
                </div>
            </div>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero">
        <div class="container">
            <h1>Welcome to Your Ebook Store! 🎉</h1>
            <p style="font-size: 1.2rem; margin-bottom: 25px;">Use the control panel above to customize everything!</p>
            <button class="btn" onclick="showNotification('🚀 Store is fully functional! Try adding books and shopping!')">
                TEST STORE FEATURES
            </button>
        </div>
    </section>

    <!-- Books Section -->
    <section class="container">
        <h2 style="text-align: center; margin: 50px 0 30px; color: var(--primary); font-size: 2rem;">
            📖 Featured Books
        </h2>
        <div class="books-grid" id="booksGrid">
            <!-- Books will be loaded here -->
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="container">
            <p>© 2024 The Definitive Word - <strong>FULLY CUSTOMIZABLE EBOOK STORE</strong> 🚀</p>
        </div>
    </footer>

    <script>
        // ===== STORE DATA =====
        let books = JSON.parse(localStorage.getItem('ebookStoreData')) || [];
        let cart = [];
        let cartCount = 0;

        // ===== INITIALIZE STORE =====
        function initializeStore() {
            console.log("🔄 Initializing store...");
            displayBooks();
            updateCartDisplay();
            updateStats();
            showNotification('🎉 Store loaded! Use the control panel to manage your store.');
        }

        // ===== BOOK MANAGEMENT =====
        function displayBooks() {
            const booksGrid = document.getElementById('booksGrid');
            booksGrid.innerHTML = '';

            if (books.length === 0) {
                booksGrid.innerHTML = `
                    <div style="text-align: center; grid-column: 1 / -1; padding: 60px; color: #666;">
                        <i class="fas fa-book-open" style="font-size: 4rem; margin-bottom: 20px; display: block; opacity: 0.5;"></i>
                        <h3 style="margin-bottom: 15px;">No books in your store yet!</h3>
                        <p style="margin-bottom: 25px;">Click "Add New Book" in the control panel to get started.</p>
                        <button class="btn" onclick="addSampleBooks()" style="background: var(--secondary);">
                            🚀 Add Sample Books
                        </button>
                    </div>
                `;
                return;
            }

            books.forEach(book => {
                const bookCard = document.createElement('div');
                bookCard.className = 'book-card';
                bookCard.innerHTML = `
                    <div class="book-cover">
                        <img src="${book.image}" alt="${book.title}" onerror="this.src='https://images.unsplash.com/photo-1544947950-fa07a98d237f?ixlib=rb-4.0.3&auto=format&fit=crop&w=500&q=80'">
                    </div>
                    <div class="book-info">
                        <h3 class="book-title">${book.title}</h3>
                        <p class="book-author">by ${book.author}</p>
                        ${book.category ? `<p style="color: var(--secondary); font-size: 0.9rem; margin-bottom: 10px;">${book.category}</p>` : ''}
                        <div class="book-price">
                            <span class="price">$${book.price}</span>
                            <button class="btn" onclick="addToCart(${book.id})">
                                🛒 Add to Cart
                            </button>
                        </div>
                    </div>
                `;
                booksGrid.appendChild(bookCard);
            });
        }

        // ===== CART FUNCTIONALITY =====
        function addToCart(bookId) {
            const book = books.find(b => b.id === bookId);
            if (!book) return;

            const existingItem = cart.find(item => item.id === bookId);
            if (existingItem) {
                existingItem.quantity += 1;
            } else {
                cart.push({
                    ...book,
                    quantity: 1
                });
            }

            cartCount = cart.reduce((total, item) => total + item.quantity, 0);
            updateCartDisplay();
            updateStats();
            
            // Visual feedback
            const button = event.target;
            const originalText = button.innerHTML;
            button.innerHTML = '✅ Added!';
            button.style.background = '#27ae60';
            
            setTimeout(() => {
                button.innerHTML = originalText;
                button.style.background = '';
            }, 1500);

            showNotification(`"${book.title}" added to cart!`);
        }

        function updateCartDisplay() {
            document.getElementById('cartCount').textContent = cartCount;
            
            const cartItems = document.getElementById('cartItems');
            const cartTotal = document.getElementById('cartTotal');
            
            cartItems.innerHTML = '';
            
            if (cart.length === 0) {
                cartItems.innerHTML = `
                    <div style="text-align: center; padding: 40px; color: #666;">
                        <i class="fas fa-shopping-cart" style="font-size: 3rem; margin-bottom: 15px; display: block; opacity: 0.5;"></i>
                        <p>Your cart is empty</p>
                        <p style="font-size: 0.9rem; margin-top: 10px;">Add some books to get started!</p>
                    </div>
                `;
                cartTotal.textContent = '$0.00';
                return;
            }
            
            let total = 0;
            cart.forEach(item => {
                const itemTotal = item.price * item.quantity;
                total += itemTotal;
                
                const cartItem = document.createElement('div');
                cartItem.className = 'cart-item';
                cartItem.innerHTML = `
                    <img src="${item.image}" alt="${item.title}">
                    <div style="flex: 1;">
                        <h4 style="margin-bottom: 5px; color: var(--primary);">${item.title}</h4>
                        <p style="color: #666; margin-bottom: 5px;">by ${item.author}</p>
                        <div style="display: flex; justify-content: space-between; align-items: center;">
                            <span style="font-weight: 600; color: var(--accent);">$${item.price} x ${item.quantity}</span>
                            <button onclick="removeFromCart(${item.id})" style="background: var(--accent); color: white; border: none; padding: 5px 10px; border-radius: 3px; cursor: pointer;">
                                ❌ Remove
                            </button>
                        </div>
                    </div>
                `;
                cartItems.appendChild(cartItem);
            });
            
            cartTotal.textContent = `$${total.toFixed(2)}`;
        }

        function removeFromCart(bookId) {
            cart = cart.filter(item => item.id !== bookId);
            cartCount = cart.reduce((total, item) => total + item.quantity, 0);
            updateCartDisplay();
            updateStats();
            showNotification('Item removed from cart');
        }

        function openCart() {
            document.getElementById('cartModal').classList.add('active');
        }

        function closeCart() {
            document.getElementById('cartModal').classList.remove('active');
        }

        function checkout() {
            if (cart.length === 0) {
                showNotification('Your cart is empty! Add some books first.', true);
                return;
            }
            
            const total = cart.reduce((sum, item) => sum + (item.price * item.quantity), 0);
            showNotification(`🎉 Order placed! Thank you for your purchase of $${total.toFixed(2)}`);
            cart = [];
            cartCount = 0;
            updateCartDisplay();
            updateStats();
            closeCart();
        }

        // ===== ADMIN FUNCTIONS =====
        function openModal(modalId) {
            closeAllModals();
            document.getElementById(modalId).classList.add('active');
            
            if (modalId === 'bookListModal') {
                renderBookList();
            }
        }

        function closeAllModals() {
            document.querySelectorAll('.modal').forEach(modal => {
                modal.classList.remove('active');
            });
        }

        function renderBookList() {
            const bookListContent = document.getElementById('bookListContent');
            bookListContent.innerHTML = '';

            if (books.length === 0) {
                bookListContent.innerHTML = `
                    <div style="text-align: center; padding: 40px; color: #666;">
                        <i class="fas fa-book" style="font-size: 3rem; margin-bottom: 15px; display: block; opacity: 0.5;"></i>
                        <p>No books in your store yet.</p>
                    </div>
                `;
                return;
            }

            books.forEach(book => {
                const bookItem = document.createElement('div');
                bookItem.style.cssText = 'padding: 20px; border: 2px solid #eee; border-radius: 8px; margin-bottom: 15px;';
                bookItem.innerHTML = `
                    <div style="display: flex; justify-content: space-between; align-items: start; gap: 15px;">
                        <div style="flex: 1;">
                            <strong style="display: block; margin-bottom: 8px; color: var(--primary); font-size: 1.1rem;">${book.title}</strong>
                            <div style="color: #666; margin-bottom: 8px;">by ${book.author}</div>
                            <div style="display: flex; gap: 15px; font-size: 0.9rem;">
                                <span style="color: var(--accent); font-weight: 600;">$${book.price}</span>
                                ${book.category ? `<span style="background: var(--secondary); color: white; padding: 2px 8px; border-radius: 10px;">${book.category}</span>` : ''}
                            </div>
                        </div>
                        <button onclick="deleteBook(${book.id})" style="background: var(--accent); color: white; border: none; padding: 8px 12px; border-radius: 4px; cursor: pointer; white-space: nowrap;">
                            🗑️ Delete
                        </button>
                    </div>
                `;
                bookListContent.appendChild(bookItem);
            });
        }

        // Add new book form
        document.getElementById('addBookForm').addEventListener('submit', function(e) {
            e.preventDefault();
            
            const newBook = {
                id: Date.now(),
                title: document.getElementById('bookTitle').value,
                author: document.getElementById('bookAuthor').value,
                price: parseFloat(document.getElementById('bookPrice').value),
                category: document.getElementById('bookCategory').value,
                description: document.getElementById('bookDescription').value,
                image: document.getElementById('bookImage').value || 'https://images.unsplash.com/photo-1544947950-fa07a98d237f?ixlib=rb-4.0.3&auto=format&fit=crop&w=500&q=80'
            };

            books.push(newBook);
            saveData();
            displayBooks();
            updateStats();
            closeAllModals();
            this.reset();
            
            showNotification(`✅ "${newBook.title}" added to your store!`);
        });

        function deleteBook(bookId) {
            if (confirm('Are you sure you want to delete this book from your store?')) {
                books = books.filter(book => book.id !== bookId);
                saveData();
                displayBooks();
                updateStats();
                renderBookList();
                showNotification('Book deleted from store');
            }
        }

        function addSampleBooks() {
            const sampleBooks = [
                {
                    id: Date.now() + 1,
                    title: "The Silent Observer",
                    author: "Megan Foster",
                    price: 12.99,
                    category: "Mystery",
                    description: "A thrilling mystery about a quiet observer",
                    image: "https://images.unsplash.com/photo-1544947950-fa07a98d237f?ixlib=rb-4.0.3&auto=format&fit=crop&w=500&q=80"
                },
                {
                    id: Date.now() + 2,
                    title: "Digital Revolution", 
                    author: "Alex Chen",
                    price: 14.99,
                    category: "Technology",
                    description: "Exploring the impact of digital technology",
                    image: "https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?ixlib=rb-4.0.3&auto=format&fit=crop&w=500&q=80"
                },
                {
                    id: Date.now() + 3,
                    title: "Business Mastery",
                    author: "Sarah Johnson",
                    price: 16.99,
                    category: "Business",
                    description: "Essential strategies for business success",
                    image: "https://images.unsplash.com/photo-1512820790803-83ca734da794?ixlib=rb-4.0.3&auto=format&fit=crop&w=500&q=80"
                }
            ];

            books.push(...sampleBooks);
            saveData();
            displayBooks();
            updateStats();
            showNotification('🎉 Sample books added to your store!');
        }

        function resetStore() {
            if (confirm('⚠️ ARE YOU SURE?\n\nThis will delete ALL books and reset your store to empty. This cannot be undone!')) {
                books = [];
                cart = [];
                cartCount = 0;
                saveData();
                displayBooks();
                updateCartDisplay();
                updateStats();
                showNotification('Store reset successfully');
            }
        }

        // ===== CUSTOMIZATION FUNCTIONS =====
        function changeColor(type, color) {
            document.documentElement.style.setProperty(`--${type}`, color);
            
            // Update active state for color picker
            document.querySelectorAll('.color-option').forEach(option => {
                option.classList.remove('active');
            });
            event.target.classList.add('active');
            
            showNotification(`🎨 Color theme updated!`);
        }

        function updateStats() {
            document.getElementById('bookCount').textContent = books.length;
            document.getElementById('cartCountDisplay').textContent = cartCount;
        }

        // ===== UTILITY FUNCTIONS =====
        function saveData() {
            localStorage.setItem('ebookStoreData', JSON.stringify(books));
        }

        function showNotification(message, isError = false) {
            const notification = document.getElementById('notification');
            notification.textContent = message;
            notification.style.background = isError ? '#e74c3c' : '#27ae60';
            notification.className = `notification ${isError ? 'error' : ''} show`;
            
            setTimeout(() => {
                notification.classList.remove('show');
            }, 4000);
        }

        function handleSearch(event) {
            if (event.key === 'Enter') {
                const query = event.target.value.toLowerCase();
                if (query.trim()) {
                    const results = books.filter(book => 
                        book.title.toLowerCase().includes(query) || 
                        book.author.toLowerCase().includes(query) ||
                        (book.category && book.category.toLowerCase().includes(query))
                    );
                    
                    if (results.length > 0) {
                        showNotification(`🔍 Found ${results.length} books matching "${query}"`);
                    } else {
                        showNotification(`No books found matching "${query}"`, true);
                    }
                }
                event.target.value = '';
            }
        }

        // ===== INITIALIZE =====
        document.addEventListener('DOMContentLoaded', initializeStore);

        // Close modals when clicking outside
        window.addEventListener('click', function(event) {
            if (event.target.classList.contains('modal')) {
                closeAllModals();
            }
        });
    </script>
</body>
</html>
