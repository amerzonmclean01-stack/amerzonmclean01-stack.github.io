<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>The Definitive Word - Admin Ebook Store</title>
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

        /* Admin Control Panel */
        .admin-panel {
            position: fixed;
            top: 50%;
            left: 0;
            transform: translateY(-50%);
            z-index: 2000;
            background: var(--primary);
            border-radius: 0 10px 10px 0;
            box-shadow: 2px 0 10px rgba(0,0,0,0.3);
            transition: var(--transition);
        }

        .admin-panel.collapsed {
            left: -50px;
        }

        .admin-toggle {
            background: var(--accent);
            color: white;
            border: none;
            padding: 15px;
            border-radius: 0 10px 10px 0;
            cursor: pointer;
            font-size: 1.2rem;
            transition: var(--transition);
        }

        .admin-toggle:hover {
            background: #c0392b;
        }

        .admin-content {
            background: white;
            padding: 20px;
            width: 350px;
            border-radius: 0 10px 10px 0;
            box-shadow: 2px 0 10px rgba(0,0,0,0.2);
            max-height: 80vh;
            overflow-y: auto;
        }

        .admin-section {
            margin-bottom: 20px;
            padding-bottom: 15px;
            border-bottom: 1px solid #eee;
        }

        .admin-section h3 {
            color: var(--primary);
            margin-bottom: 10px;
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .form-group {
            margin-bottom: 15px;
        }

        .form-group label {
            display: block;
            margin-bottom: 5px;
            font-weight: 600;
            color: var(--primary);
        }

        .form-group input, .form-group textarea, .form-group select {
            width: 100%;
            padding: 8px 12px;
            border: 1px solid #ddd;
            border-radius: 4px;
            font-size: 0.9rem;
        }

        .form-group textarea {
            height: 80px;
            resize: vertical;
        }

        .btn {
            display: inline-block;
            padding: 10px 20px;
            background: var(--secondary);
            color: white;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            transition: var(--transition);
            font-weight: 600;
        }

        .btn:hover {
            background: #2980b9;
        }

        .btn-accent {
            background: var(--accent);
        }

        .btn-accent:hover {
            background: #c0392b;
        }

        .btn-success {
            background: var(--success);
        }

        .btn-success:hover {
            background: #27ae60;
        }

        .btn-small {
            padding: 5px 10px;
            font-size: 0.8rem;
        }

        .book-list {
            max-height: 200px;
            overflow-y: auto;
            border: 1px solid #ddd;
            border-radius: 4px;
            padding: 10px;
            background: #f9f9f9;
        }

        .book-item {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 8px;
            border-bottom: 1px solid #eee;
        }

        .book-item:last-child {
            border-bottom: none;
        }

        .book-item-info {
            flex: 1;
        }

        .book-item-title {
            font-weight: 600;
            font-size: 0.9rem;
        }

        .book-item-author {
            font-size: 0.8rem;
            color: #666;
        }

        .book-actions {
            display: flex;
            gap: 5px;
        }

        .quick-stats {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 10px;
            margin-top: 10px;
        }

        .stat-box {
            background: var(--light);
            padding: 10px;
            border-radius: 4px;
            text-align: center;
        }

        .stat-number {
            font-size: 1.5rem;
            font-weight: 700;
            color: var(--primary);
        }

        .stat-label {
            font-size: 0.8rem;
            color: #666;
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
            flex-wrap: wrap;
        }

        nav li {
            margin: 0 15px;
        }

        nav a {
            color: white;
            font-weight: 500;
            transition: var(--transition);
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
            transition: var(--transition);
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

        /* Notifications */
        .notification {
            position: fixed;
            top: 20px;
            right: 20px;
            padding: 15px 20px;
            background: var(--success);
            color: white;
            border-radius: 4px;
            box-shadow: var(--shadow);
            z-index: 3000;
            transform: translateX(400px);
            transition: var(--transition);
        }

        .notification.show {
            transform: translateX(0);
        }

        .notification.error {
            background: var(--accent);
        }

        @media (max-width: 768px) {
            .admin-panel {
                top: auto;
                bottom: 0;
                left: 0;
                transform: none;
                width: 100%;
                border-radius: 10px 10px 0 0;
            }
            
            .admin-panel.collapsed {
                left: 0;
                bottom: -400px;
            }
            
            .admin-toggle {
                border-radius: 10px 10px 0 0;
                width: 100%;
                text-align: center;
            }
            
            .admin-content {
                width: 100%;
                border-radius: 10px 10px 0 0;
            }
        }
    </style>
</head>
<body>
    <!-- Admin Control Panel -->
    <div class="admin-panel" id="admin-panel">
        <button class="admin-toggle" id="admin-toggle" title="Admin Control Panel">
            <i class="fas fa-tools"></i>
        </button>
        <div class="admin-content" id="admin-content">
            <h2 style="color: var(--primary); margin-bottom: 20px; text-align: center;">
                <i class="fas fa-crown"></i> Admin Control Panel
            </h2>
            
            <!-- Quick Stats -->
            <div class="admin-section">
                <h3><i class="fas fa-chart-bar"></i> Store Stats</h3>
                <div class="quick-stats">
                    <div class="stat-box">
                        <div class="stat-number" id="total-books">0</div>
                        <div class="stat-label">Total Books</div>
                    </div>
                    <div class="stat-box">
                        <div class="stat-number" id="total-sales">0</div>
                        <div class="stat-label">Books Sold</div>
                    </div>
                </div>
            </div>
            
            <!-- Add New Book -->
            <div class="admin-section">
                <h3><i class="fas fa-plus-circle"></i> Add New Book</h3>
                <form id="add-book-form">
                    <div class="form-group">
                        <label for="book-title">Title</label>
                        <input type="text" id="book-title" required>
                    </div>
                    <div class="form-group">
                        <label for="book-author">Author</label>
                        <input type="text" id="book-author" required>
                    </div>
                    <div class="form-group">
                        <label for="book-price">Price ($)</label>
                        <input type="number" id="book-price" step="0.01" required>
                    </div>
                    <div class="form-group">
                        <label for="book-original-price">Original Price ($)</label>
                        <input type="number" id="book-original-price" step="0.01">
                    </div>
                    <div class="form-group">
                        <label for="book-category">Category</label>
                        <select id="book-category">
                            <option value="Fiction">Fiction</option>
                            <option value="Non-Fiction">Non-Fiction</option>
                            <option value="Science">Science</option>
                            <option value="Technology">Technology</option>
                            <option value="Business">Business</option>
                            <option value="Self-Help">Self-Help</option>
                            <option value="Mystery">Mystery</option>
                            <option value="Romance">Romance</option>
                        </select>
                    </div>
                    <div class="form-group">
                        <label for="book-image">Image URL</label>
                        <input type="url" id="book-image" placeholder="https://example.com/image.jpg">
                    </div>
                    <div class="form-group">
                        <label for="book-description">Description</label>
                        <textarea id="book-description"></textarea>
                    </div>
                    <button type="submit" class="btn btn-success" style="width: 100%;">
                        <i class="fas fa-plus"></i> Add Book to Store
                    </button>
                </form>
            </div>
            
            <!-- Manage Existing Books -->
            <div class="admin-section">
                <h3><i class="fas fa-edit"></i> Manage Books</h3>
                <div class="book-list" id="book-list">
                    <!-- Books will be listed here -->
                </div>
            </div>
            
            <!-- Quick Actions -->
            <div class="admin-section">
                <h3><i class="fas fa-bolt"></i> Quick Actions</h3>
                <div style="display: flex; gap: 10px; flex-wrap: wrap;">
                    <button class="btn btn-accent btn-small" id="export-books">
                        <i class="fas fa-download"></i> Export
                    </button>
                    <button class="btn btn-small" id="import-books">
                        <i class="fas fa-upload"></i> Import
                    </button>
                    <button class="btn btn-small" id="clear-all">
                        <i class="fas fa-trash"></i> Clear All
                    </button>
                </div>
            </div>
        </div>
    </div>

    <!-- Notification System -->
    <div class="notification" id="notification"></div>

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

    <script>
        // Book Management System
        let books = JSON.parse(localStorage.getItem('ebookStoreBooks')) || [
            {
                id: 1,
                title: "The Silent Observer",
                author: "Megan Foster",
                price: 12.99,
                originalPrice: 15.99,
                image: "https://images.unsplash.com/photo-1544947950-fa07a98d237f?ixlib=rb-4.0.3&auto=format&fit=crop&w=500&q=80",
                category: "Mystery",
                description: "A thrilling mystery novel about a quiet observer who witnesses a crime."
            },
            {
                id: 2,
                title: "Digital Revolution",
                author: "Alex Chen",
                price: 14.99,
                originalPrice: null,
                image: "https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?ixlib=rb-4.0.3&auto=format&fit=crop&w=500&q=80",
                category: "Technology",
                description: "Exploring the impact of digital technology on modern society."
            }
        ];

        let salesData = JSON.parse(localStorage.getItem('ebookStoreSales')) || {
            totalSales: 0,
            booksSold: 0
        };

        // DOM Elements
        const adminPanel = document.getElementById('admin-panel');
        const adminToggle = document.getElementById('admin-toggle');
        const adminContent = document.getElementById('admin-content');
        const addBookForm = document.getElementById('add-book-form');
        const bookList = document.getElementById('book-list');
        const featuredBooks = document.getElementById('featured-books');
        const notification = document.getElementById('notification');
        const totalBooksElement = document.getElementById('total-books');
        const totalSalesElement = document.getElementById('total-sales');

        // Initialize
        updateBookDisplay();
        updateAdminStats();
        renderBookList();

        // Toggle admin panel
        adminToggle.addEventListener('click', function() {
            adminPanel.classList.toggle('collapsed');
        });

        // Add new book
        addBookForm.addEventListener('submit', function(e) {
            e.preventDefault();
            
            const newBook = {
                id: Date.now(), // Simple ID generation
                title: document.getElementById('book-title').value,
                author: document.getElementById('book-author').value,
                price: parseFloat(document.getElementById('book-price').value),
                originalPrice: document.getElementById('book-original-price').value ? 
                    parseFloat(document.getElementById('book-original-price').value) : null,
                category: document.getElementById('book-category').value,
                image: document.getElementById('book-image').value || 'https://images.unsplash.com/photo-1544947950-fa07a98d237f?ixlib=rb-4.0.3&auto=format&fit=crop&w=500&q=80',
                description: document.getElementById('book-description').value
            };
            
            books.push(newBook);
            saveBooks();
            updateBookDisplay();
            renderBookList();
            showNotification('Book added successfully!', 'success');
            
            // Reset form
            addBookForm.reset();
        });

        // Render book list in admin panel
        function renderBookList() {
            bookList.innerHTML = '';
            
            if (books.length === 0) {
                bookList.innerHTML = '<div style="text-align: center; color: #666; padding: 20px;">No books in store</div>';
                return;
            }
            
            books.forEach(book => {
                const bookItem = document.createElement('div');
                bookItem.className = 'book-item';
                bookItem.innerHTML = `
                    <div class="book-item-info">
                        <div class="book-item-title">${book.title}</div>
                        <div class="book-item-author">by ${book.author} • $${book.price}</div>
                    </div>
                    <div class="book-actions">
                        <button class="btn btn-accent btn-small" onclick="editBook(${book.id})" title="Edit">
                            <i class="fas fa-edit"></i>
                        </button>
                        <button class="btn btn-small" onclick="deleteBook(${book.id})" title="Delete">
                            <i class="fas fa-trash"></i>
                        </button>
                    </div>
                `;
                bookList.appendChild(bookItem);
            });
        }

        // Delete book
        function deleteBook(bookId) {
            if (confirm('Are you sure you want to delete this book?')) {
                books = books.filter(book => book.id !== bookId);
                saveBooks();
                updateBookDisplay();
                renderBookList();
                showNotification('Book deleted successfully!', 'success');
            }
        }

        // Edit book (simplified - in real app you'd have a proper edit form)
        function editBook(bookId) {
            const book = books.find(b => b.id === bookId);
            if (book) {
                // Pre-fill the form with book data
                document.getElementById('book-title').value = book.title;
                document.getElementById('book-author').value = book.author;
                document.getElementById('book-price').value = book.price;
                document.getElementById('book-original-price').value = book.originalPrice || '';
                document.getElementById('book-category').value = book.category;
                document.getElementById('book-image').value = book.image;
                document.getElementById('book-description').value = book.description;
                
                // Remove the old book
                books = books.filter(b => b.id !== bookId);
                saveBooks();
                updateBookDisplay();
                
                showNotification('Book loaded for editing. Update fields and click "Add Book" to save changes.', 'success');
            }
        }

        // Update book display on main page
        function updateBookDisplay() {
            featuredBooks.innerHTML = '';
            
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
                
                featuredBooks.appendChild(bookCard);
            });
            
            // Re-attach event listeners to new buttons
            attachCartEventListeners();
        }

        // Update admin statistics
        function updateAdminStats() {
            totalBooksElement.textContent = books.length;
            totalSalesElement.textContent = salesData.booksSold;
        }

        // Save books to localStorage
        function saveBooks() {
            localStorage.setItem('ebookStoreBooks', JSON.stringify(books));
            localStorage.setItem('ebookStoreSales', JSON.stringify(salesData));
        }

        // Show notification
        function showNotification(message, type = 'success') {
            notification.textContent = message;
            notification.className = `notification ${type} show`;
            
            setTimeout(() => {
                notification.classList.remove('show');
            }, 3000);
        }

        // Export books
        document.getElementById('export-books').addEventListener('click', function() {
            const dataStr = JSON.stringify(books, null, 2);
            const dataBlob = new Blob([dataStr], {type: 'application/json'});
            
            const link = document.createElement('a');
            link.href = URL.createObjectURL(dataBlob);
            link.download = 'ebook-store-backup.json';
            link.click();
            
            showNotification('Books exported successfully!', 'success');
        });

        // Import books
        document.getElementById('import-books').addEventListener('click', function() {
            const input = document.createElement('input');
            input.type = 'file';
            input.accept = '.json';
            
            input.onchange = function(e) {
                const file = e.target.files[0];
                const reader = new FileReader();
                
                reader.onload = function(e) {
                    try {
                        const importedBooks = JSON.parse(e.target.result);
                        books = importedBooks;
                        saveBooks();
                        updateBookDisplay();
                        renderBookList();
                        showNotification('Books imported successfully!', 'success');
                    } catch (error) {
                        showNotification('Error importing books. Invalid file format.', 'error');
                    }
                };
                
                reader.readAsText(file);
            };
            
            input.click();
        });

        // Clear all books
        document.getElementById('clear-all').addEventListener('click', function() {
            if (confirm('Are you sure you want to clear ALL books? This cannot be undone.')) {
                books = [];
                saveBooks();
                updateBookDisplay();
                renderBookList();
                showNotification('All books cleared!', 'success');
            }
        });

        // Cart functionality
        let cartCount = 0;
        const cartCountElement = document.querySelector('.cart-count');

        function attachCartEventListeners() {
            document.querySelectorAll('.add-to-cart').forEach(button => {
                button.addEventListener('click', function() {
                    cartCount++;
                    cartCountElement.textContent = cartCount;
                    
                    // Update sales data
                    salesData.booksSold++;
                    salesData.totalSales += parseFloat(books.find(b => b.id == this.dataset.id).price);
                    saveBooks();
                    updateAdminStats();
                    
                    // Show confirmation
                    const originalText = this.textContent;
                    this.textContent = 'Added!';
                    this.style.background = '#2ecc71';
                    
                    setTimeout(() => {
                        this.textContent = originalText;
                        this.style.background = '';
                    }, 1500);
                });
            });
        }

        // Initial cart event attachment
        attachCartEventListeners();
    </script>
</body>
</html>
