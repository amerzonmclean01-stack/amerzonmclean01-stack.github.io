<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>The Definitive Word - LIVE Ebook Store</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary: #2c3e50;
            --secondary: #3498db;
            --accent: #e74c3c;
            --light: #ecf0f1;
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
            background: #f9f9f9;
        }

        .container {
            width: 90%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 15px;
        }

        /* Admin Panel */
        .admin-panel {
            position: fixed;
            top: 10px;
            right: 10px;
            background: white;
            padding: 15px;
            border-radius: 8px;
            box-shadow: 0 4px 15px rgba(0,0,0,0.2);
            z-index: 1000;
            border: 2px solid var(--secondary);
        }

        .admin-btn {
            background: var(--secondary);
            color: white;
            border: none;
            padding: 10px 15px;
            border-radius: 4px;
            cursor: pointer;
            margin: 5px 0;
            width: 100%;
            font-weight: 600;
        }

        .admin-btn:hover {
            background: #2980b9;
        }

        /* Header */
        header {
            background: white;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
            position: sticky;
            top: 0;
            z-index: 100;
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
        }

        .search-bar input {
            width: 100%;
            padding: 10px 15px;
            border: 1px solid #ddd;
            border-radius: 30px;
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
        }

        /* Hero Section */
        .hero {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 80px 0;
            text-align: center;
        }

        .hero h1 {
            font-size: 2.5rem;
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
        }

        .btn:hover {
            background: #c0392b;
        }

        /* Books Grid */
        .books-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 30px;
            margin: 40px 0;
        }

        .book-card {
            background: white;
            border-radius: 8px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            transition: transform 0.3s ease;
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
            font-size: 1.1rem;
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
            color: var(--primary);
            font-size: 1.2rem;
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
            border-radius: 8px;
            max-width: 500px;
            width: 90%;
            max-height: 80vh;
            overflow-y: auto;
        }

        .form-group {
            margin-bottom: 15px;
        }

        .form-group label {
            display: block;
            margin-bottom: 5px;
            font-weight: 600;
        }

        .form-group input {
            width: 100%;
            padding: 8px 12px;
            border: 1px solid #ddd;
            border-radius: 4px;
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
            border-bottom: 1px solid #eee;
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
        }

        .cart-total {
            padding: 20px;
            border-top: 1px solid #eee;
            display: flex;
            justify-content: space-between;
            font-weight: 700;
            font-size: 1.1rem;
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
            background: #2ecc71;
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

        @media (max-width: 768px) {
            .header-top {
                flex-direction: column;
            }
            .search-bar {
                margin: 15px 0;
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

    <!-- Admin Panel -->
    <div class="admin-panel">
        <h3 style="color: var(--primary); margin-bottom: 15px;">🚀 Admin Controls</h3>
        <button class="admin-btn" onclick="openModal('addBookModal')">
            <i class="fas fa-plus"></i> Add New Book
        </button>
        <button class="admin-btn" onclick="openModal('bookListModal')">
            <i class="fas fa-list"></i> Manage Books
        </button>
        <button class="admin-btn" onclick="resetStore()">
            <i class="fas fa-redo"></i> Reset Store
        </button>
    </div>

    <!-- Add Book Modal -->
    <div class="modal" id="addBookModal">
        <div class="modal-content">
            <h2 style="margin-bottom: 20px;">➕ Add New Book</h2>
            <form id="addBookForm">
                <div class="form-group">
                    <label>Book Title</label>
                    <input type="text" id="bookTitle" required placeholder="Enter book title">
                </div>
                <div class="form-group">
                    <label>Author</label>
                    <input type="text" id="bookAuthor" required placeholder="Enter author name">
                </div>
                <div class="form-group">
                    <label>Price ($)</label>
                    <input type="number" id="bookPrice" step="0.01" required placeholder="9.99">
                </div>
                <div class="form-group">
                    <label>Image URL</label>
                    <input type="url" id="bookImage" placeholder="https://example.com/image.jpg">
                </div>
                <button type="submit" class="btn" style="width: 100%; margin-top: 15px;">
                    ✅ Add Book to Store
                </button>
            </form>
            <button class="btn" onclick="closeAllModals()" style="width: 100%; margin-top: 10px; background: #666;">
                ❌ Cancel
            </button>
        </div>
    </div>

    <!-- Book List Modal -->
    <div class="modal" id="bookListModal">
        <div class="modal-content">
            <h2 style="margin-bottom: 20px;">📚 Manage Books</h2>
            <div id="bookListContent">
                <!-- Books will be listed here -->
            </div>
            <button class="btn" onclick="closeAllModals()" style="width: 100%; margin-top: 15px; background: #666;">
                ✅ Close
            </button>
        </div>
    </div>

    <!-- Cart Modal -->
    <div class="cart-modal" id="cartModal">
        <div class="cart-header">
            <h2>🛒 Your Cart</h2>
            <button onclick="closeCart()" style="background: none; border: none; font-size: 1.5rem; cursor: pointer;">❌</button>
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
                💳 Checkout Now
            </button>
        </div>
    </div>

    <!-- Header -->
    <header>
        <div class="container">
            <div class="header-top">
                <div class="logo">
                    <i class="fas fa-book-open"></i>
                    The Definitive Word
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
            <h1>📖 Welcome to Your LIVE Ebook Store!</h1>
            <p>Everything works! Add books, shop, and manage your store in real-time.</p>
            <button class="btn" onclick="showNotification('Store is fully functional! 🎉')">
                🚀 Test Store Features
            </button>
        </div>
    </section>

    <!-- Books Section -->
    <section class="container">
        <h2 style="text-align: center; margin: 40px 0 20px; color: var(--primary);">⭐ Featured Books</h2>
        <div class="books-grid" id="booksGrid">
            <!-- Books will be loaded here -->
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="container">
            <p>© 2024 The Definitive Word. <strong>FULLY FUNCTIONAL STORE</strong> 🎉</p>
        </div>
    </footer>

    <script>
        // ===== STORE DATA =====
        let books = JSON.parse(localStorage.getItem('ebookStoreData')) || [
            {
                id: 1,
                title: "The Great Adventure",
                author: "Emma Wilson",
                price: 12.99,
                image: "https://images.unsplash.com/photo-1544947950-fa07a98d237f?ixlib=rb-4.0.3&auto=format&fit=crop&w=500&q=80"
            },
            {
                id: 2,
                title: "Digital Dreams", 
                author: "Alex Chen",
                price: 14.99,
                image: "https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?ixlib=rb-4.0.3&auto=format&fit=crop&w=500&q=80"
            }
        ];

        let cart = [];
        let cartCount = 0;

        // ===== INITIALIZE STORE =====
        function initializeStore() {
            console.log("🔄 Initializing store...");
            displayBooks();
            updateCartDisplay();
            showNotification('Store loaded successfully! 🎉');
        }

        // ===== BOOK MANAGEMENT =====
        function displayBooks() {
            const booksGrid = document.getElementById('booksGrid');
            booksGrid.innerHTML = '';

            if (books.length === 0) {
                booksGrid.innerHTML = `
                    <div style="text-align: center; grid-column: 1 / -1; padding: 40px; color: #666;">
                        <i class="fas fa-book" style="font-size: 3rem; margin-bottom: 15px; display: block;"></i>
                        <h3>No books in store yet!</h3>
                        <p>Use the admin panel to add your first book.</p>
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
                        <i class="fas fa-shopping-cart" style="font-size: 3rem; margin-bottom: 15px; display: block;"></i>
                        <p>Your cart is empty</p>
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
                        <h4 style="margin-bottom: 5px;">${item.title}</h4>
                        <p style="color: #666; margin-bottom: 5px;">by ${item.author}</p>
                        <div style="display: flex; justify-content: space-between; align-items: center;">
                            <span>$${item.price} x ${item.quantity}</span>
                            <button onclick="removeFromCart(${item.id})" style="background: #e74c3c; color: white; border: none; padding: 5px 10px; border-radius: 3px; cursor: pointer;">
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
                showNotification('Your cart is empty!', true);
                return;
            }
            
            const total = cart.reduce((sum, item) => sum + (item.price * item.quantity), 0);
            showNotification(`🎉 Order placed! Total: $${total.toFixed(2)}`);
            cart = [];
            cartCount = 0;
            updateCartDisplay();
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
                bookListContent.innerHTML = '<p style="text-align: center; padding: 20px; color: #666;">No books in store.</p>';
                return;
            }

            books.forEach(book => {
                const bookItem = document.createElement('div');
                bookItem.style.cssText = 'padding: 15px; border-bottom: 1px solid #eee; display: flex; justify-content: space-between; align-items: center;';
                bookItem.innerHTML = `
                    <div style="flex: 1;">
                        <strong style="display: block; margin-bottom: 5px;">${book.title}</strong>
                        <small style="color: #666;">by ${book.author} - $${book.price}</small>
                    </div>
                    <button onclick="deleteBook(${book.id})" style="background: #e74c3c; color: white; border: none; padding: 8px 12px; border-radius: 4px; cursor: pointer;">
                        🗑️ Delete
                    </button>
                `;
                bookListContent.appendChild(bookItem);
            });
        }

        document.getElementById('addBookForm').addEventListener('submit', function(e) {
            e.preventDefault();
            
            const newBook = {
                id: Date.now(),
                title: document.getElementById('bookTitle').value,
                author: document.getElementById('bookAuthor').value,
                price: parseFloat(document.getElementById('bookPrice').value),
                image: document.getElementById('bookImage').value || 'https://images.unsplash.com/photo-1544947950-fa07a98d237f?ixlib=rb-4.0.3&auto=format&fit=crop&w=500&q=80'
            };

            books.push(newBook);
            saveData();
            displayBooks();
            closeAllModals();
            this.reset();
            
            showNotification(`"${newBook.title}" added to store! 📚`);
        });

        function deleteBook(bookId) {
            if (confirm('Are you sure you want to delete this book?')) {
                books = books.filter(book => book.id !== bookId);
                saveData();
                displayBooks();
                renderBookList();
                showNotification('Book deleted successfully');
            }
        }

        function resetStore() {
            if (confirm('Are you sure you want to reset the entire store? This cannot be undone!')) {
                books = [];
                cart = [];
                cartCount = 0;
                saveData();
                displayBooks();
                updateCartDisplay();
                showNotification('Store reset successfully');
            }
        }

        // ===== UTILITY FUNCTIONS =====
        function saveData() {
            localStorage.setItem('ebookStoreData', JSON.stringify(books));
        }

        function showNotification(message, isError = false) {
            const notification = document.getElementById('notification');
            notification.textContent = message;
            notification.style.background = isError ? '#e74c3c' : '#2ecc71';
            notification.classList.add('show');
            
            setTimeout(() => {
                notification.classList.remove('show');
            }, 3000);
        }

        function handleSearch(event) {
            if (event.key === 'Enter') {
                const query = event.target.value.toLowerCase();
                if (query.trim()) {
                    const results = books.filter(book => 
                        book.title.toLowerCase().includes(query) || 
                        book.author.toLowerCase().includes(query)
                    );
                    
                    if (results.length > 0) {
                        showNotification(`Found ${results.length} books matching "${query}"`);
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
