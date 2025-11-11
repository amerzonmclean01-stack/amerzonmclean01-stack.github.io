<!DOCTYPE html>
<html>
<head>
    <title>The Definitive Word - Ebook Store</title>
    <style>
        body { 
            font-family: Arial, sans-serif; 
            margin: 0; 
            padding: 0; 
            background: #f4f4f4;
        }
        .header {
            background: #2c3e50;
            color: white;
            padding: 2rem;
            text-align: center;
        }
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 2rem;
        }
        .book {
            background: white;
            padding: 1rem;
            margin: 1rem 0;
            border-radius: 5px;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
        }
        .btn {
            background: #e74c3c;
            color: white;
            padding: 10px 20px;
            border: none;
            border-radius: 3px;
            cursor: pointer;
        }
    </style>
</head>
<body>
    <div class="header">
        <h1>📚 The Definitive Word</h1>
        <p>Your Premier Ebook Store - Coming Soon!</p>
    </div>
    
    <div class="container">
        <h2>Welcome to Your New Ebook Store!</h2>
        <p>This is your basic website. We'll make it amazing soon!</p>
        
        <div class="book">
            <h3>Sample Book Title</h3>
            <p>By: Sample Author</p>
            <p>Price: $9.99</p>
            <button class="btn">Add to Cart</button>
        </div>
    </div>

    <script>
        // Simple button functionality
        document.querySelector('.btn').addEventListener('click', function() {
            alert('Book added to cart! This is working!');
        });
    </script>
</body>
</html>
