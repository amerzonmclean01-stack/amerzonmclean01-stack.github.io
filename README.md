<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>The Definitive Word - Ebook Store</title>
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

        /* Simple Admin Panel */
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

        /* Footer */
        footer {
            background: var(--primary);
            color: white;
            padding: 40px 0 20px;
            text-align: center;
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
        }
    </style>
</head>
<body>
    <!-- Simple Admin Panel -->
    <div class="admin-panel">
        <h3 style="color: var(--primary); margin-bottom: 15px;">Admin Controls</h3>
        <button class="admin-btn" onclick="openAddBookModal()">
            <i class="fas fa-plus"></i> Add New Book
        </button>
        <button class="admin-btn" onclick="showBookList()">
            <i class="fas fa-list"></i> Manage Books
        </button>
        <button class="admin-btn" onclick="resetStore()">
            <i class="fas fa-redo"></i> Reset Store
        </button>
    </div>

    <!-- Add Book Modal -->
    <div class="modal" id="addBookModal">
        <div class="modal-content">
            <h2 style="margin-bottom: 20px;">Add New Book</h2>
            <form id="addBookForm">
                <div class="form-group">
                    <label>Book Title</label>
                    <input type="text" id="bookTitle" required>
                </div>
                <div class="form-group">
                    <label>Author</label>
                    <input type="text" id="bookAuthor" required>
                </div>
                <div class="form-group">
                    <label>Price ($)</label>
                    <input type="number" id="bookPrice" step="0.01" required>
                </div>
                <div class="form-group">
                    <label>Image URL</label>
                    <input type="url" id="bookImage" placeholder="https://example.com/image.jpg">
                </div>
                <button type="submit" class="btn" style="width: 100%; margin-top: 15px;">
                    Add Book to Store
                </button>
            </form>
            <button class="btn" onclick="closeModal('addBookModal')" style="width: 100%; margin-top: 10px; background: #666;">
                Cancel
            </button>
        </div>
    </div>

    <!-- Book List Modal -->
    <div class="modal" id="bookListModal">
        <div class="modal-content">
            <h2 style="margin-bottom: 20px;">Manage Books</h2>
            <div id="bookListContent">
                <!-- Books will be listed here -->
            </div>
            <button class="btn" onclick="closeModal('bookListModal')" style="width: 100%; margin-top: 15px; background: #666;">
                Close
            </button>
        </div>
    </div>

    <!-- Header -->
    <header>
        <div class="container">
            <div class="header-top">
                <a href="#" class="logo">
                    <i class="fas fa-book-open"></i>
                    The Definitive Word
                </a>
                <div class="search-bar">
                    <input type="text" placeholder="Search books...">
                </div>
                <div class="user-actions">
                    <a href="#" class="cart-icon">
                        <i class="fas fa-shopping-cart"></i>
                        <span class="cart-count">0</span>
                    </a>
                </div>
            </div>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero">
        <div class="container">
            <h1>Welcome to Your Ebook Store</h1>
            <p>Add and manage books using the admin panel in the top right corner</p>
            <a href="#" class="btn">Start Shopping</a>
        </div>
    </section>

    <!-- Books Section -->
    <section class="container">
        <h2 style="text-align: center; margin: 40px 0 20px; color: var(--primary);">Featured Books</h2>
        <div class="books-grid" id="booksGrid">
            <!-- Books will be loaded here -->
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="container">
            <p>&copy; 2024 The Definitive Word. All rights reserved.</p>
        </div>
    </footer>

    <script>
        // Initialize books array
        let books = JSON.parse(localStorage.getItem('simpleEbookStore')) || [
            {
                id: 1,
                title: "Sample Book One",
                author: "Author One",
                price: 9.99,
                image: "https://images.unsplash.com/photo-1544947950-fa07a98d237f?ixlib=rb-4.0.3&auto=format&fit=crop&w=500&q=80"
            },
            {
                id: 2,
                title: "Sample Book Two", 
                author: "Author Two",
                price: 12.99,
                image: "https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?ixlib=rb-4.0.3&auto=format&fit=crop&w=500&q=80"
            }
        ];

        let cartCount = 0;

        // Initialize the store
        function initializeStore() {
            displayBooks();
            updateCartCount();
        }

        // Display all books
        function displayBooks() {
            const booksGrid = document.getElementById('booksGrid');
            booksGrid.innerHTML = '';

            if (books.length === 0) {
                booksGrid.innerHTML = '<p style="text-align: center; grid-column: 1 / -1; padding: 40px;">No books in store. Use the admin panel to add books.</p>';
                return;
            }

            books.forEach(book => {
                const bookCard = document.createElement('div');
                bookCard.className = 'book-card';
                bookCard.innerHTML = `
                    <div class="book-cover">
                        <img src="${book.image}" alt="${book.title}">
                    </div>
                    <div class="book-info">
                        <h3 class="book-title">${book.title}</h3>
                        <p class="book-author">by ${book.author}</p>
                        <div class="book-price">
                            <span class="price">$${book.price}</span>
                            <button class="btn" onclick="addToCart(${book.id})">Add to Cart</button>
                        </div>
                    </div>
                `;
                booksGrid.appendChild(bookCard);
            });
        }

        // Add to cart function
        function addToCart(bookId) {
            cartCount++;
            updateCartCount();
            
            // Find the button that was clicked and show feedback
            const buttons = document.querySelectorAll('.btn');
            buttons.forEach(button => {
                if (button.textContent === 'Added!') {
                    button.textContent = 'Add to Cart';
                    button.style.background = '';
                }
            });
            
            // Show temporary feedback
            event.target.textContent = 'Added!';
            event.target.style.background = '#27ae60';
            
            setTimeout(() => {
                event.target.textContent = 'Add to Cart';
                event.target.style.background = '';
            }, 1500);
        }

        // Update cart count display
        function updateCartCount() {
            document.querySelector('.cart-count').textContent = cartCount;
        }

        // Modal functions
        function openAddBookModal() {
            document.getElementById('addBookModal').style.display = 'flex';
        }

        function closeModal(modalId) {
            document.getElementById(modalId).style.display = 'none';
        }

        // Show book list in modal
        function showBookList() {
            const bookListContent = document.getElementById('bookListContent');
            bookListContent.innerHTML = '';

            if (books.length === 0) {
                bookListContent.innerHTML = '<p>No books in store.</p>';
            } else {
                books.forEach(book => {
                    const bookItem = document.createElement('div');
                    bookItem.style.cssText = 'padding: 10px; border-bottom: 1px solid #eee; display: flex; justify-content: space-between; align-items: center;';
                    bookItem.innerHTML = `
                        <div>
                            <strong>${book.title}</strong><br>
                            <small>by ${book.author} - $${book.price}</small>
                        </div>
                        <button class="btn" onclick="deleteBook(${book.id})" style="padding: 5px 10px; background: #e74c3c;">
                            <i class="fas fa-trash"></i>
                        </button>
                    `;
                    bookListContent.appendChild(bookItem);
                });
            }

            document.getElementById('bookListModal').style.display = 'flex';
        }

        // Add new book
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
            saveBooks();
            displayBooks();
            closeModal('addBookModal');
            this.reset();
            
            alert('Book added successfully!');
        });

        // Delete book
        function deleteBook(bookId) {
            if (confirm('Are you sure you want to delete this book?')) {
                books = books.filter(book => book.id !== bookId);
                saveBooks();
                displayBooks();
                showBookList(); // Refresh the book list modal
                alert('Book deleted successfully!');
            }
        }

        // Reset store
        function resetStore() {
            if (confirm('Are you sure you want to reset the store? This will remove all books.')) {
                books = [];
                saveBooks();
                displayBooks();
                alert('Store reset successfully!');
            }
        }

        // Save books to localStorage
        function saveBooks() {
            localStorage.setItem('simpleEbookStore', JSON.stringify(books));
        }

        // Close modals when clicking outside
        window.onclick = function(event) {
            const modals = document.querySelectorAll('.modal');
            modals.forEach(modal => {
                if (event.target === modal) {
                    modal.style.display = 'none';
                }
            });
        }

        // Initialize the store when page loads
        document.addEventListener('DOMContentLoaded', initializeStore);
    </script>
</body>
</html>
