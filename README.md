<!DOCTYPE html>
<html>
<head>
    <title>Digital Book Store - Quality eBooks</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: #333;
        }
        .container {
            background: white;
            border-radius: 15px;
            padding: 30px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.2);
        }
        .header {
            text-align: center;
            padding: 40px 20px;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            border-radius: 10px;
            margin-bottom: 40px;
        }
        .header h1 {
            margin: 0;
            font-size: 2.5em;
        }
        .header p {
            font-size: 1.2em;
            opacity: 0.9;
        }
        .ebooks-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
            margin: 40px 0;
        }
        .ebook-card {
            background: #f8f9fa;
            border-radius: 10px;
            padding: 25px;
            text-align: center;
            border: 1px solid #e9ecef;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }
        .ebook-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 5px 20px rgba(0,0,0,0.1);
        }
        .ebook-title {
            color: #495057;
            font-size: 1.4em;
            margin: 15px 0;
        }
        .ebook-description {
            color: #6c757d;
            line-height: 1.6;
            margin: 15px 0;
        }
        .price {
            font-size: 1.8em;
            color: #28a745;
            font-weight: bold;
            margin: 15px 0;
        }
        .buy-button {
            background: linear-gradient(135deg, #28a745, #20c997);
            color: white;
            padding: 12px 30px;
            text-decoration: none;
            border-radius: 25px;
            display: inline-block;
            font-weight: bold;
            transition: all 0.3s ease;
            border: none;
            cursor: pointer;
        }
        .buy-button:hover {
            transform: scale(1.05);
            box-shadow: 0 5px 15px rgba(40, 167, 69, 0.3);
        }
        .features {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            margin: 50px 0;
        }
        .feature {
            text-align: center;
            padding: 20px;
        }
        .feature-icon {
            font-size: 2.5em;
            margin-bottom: 15px;
        }
        .coming-soon {
            background: #ffc107;
            color: #856404;
            padding: 8px 15px;
            border-radius: 15px;
            font-size: 0.9em;
            display: inline-block;
            margin: 10px 0;
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">
            <h1>📚 Digital Book Store</h1>
            <p>Premium eBooks for Instant Download</p>
        </div>

        <div class="ebooks-grid">
            <!-- eBook 1 -->
            <div class="ebook-card">
                <div class="feature-icon">🚀</div>
                <h3 class="ebook-title">Getting Started with Programming</h3>
                <p class="ebook-description">Learn the fundamentals of coding with this beginner-friendly guide. Perfect for absolute starters.</p>
                <div class="price">$12.99</div>
                <a href="#" class="buy-button">Buy Now</a>
                <div class="coming-soon">Available Now</div>
            </div>

            <!-- eBook 2 -->
            <div class="ebook-card">
                <div class="feature-icon">💼</div>
                <h3 class="ebook-title">Business Success Strategies</h3>
                <p class="ebook-description">Proven methods to grow your business and increase revenue. Real-world examples included.</p>
                <div class="price">$14.99</div>
                <a href="#" class="buy-button">Buy Now</a>
                <div class="coming-soon">Available Now</div>
            </div>

            <!-- eBook 3 -->
            <div class="ebook-card">
                <div class="feature-icon">🧠</div>
                <h3 class="ebook-title">Productivity Mastery</h3>
                <p class="ebook-description">Double your productivity with these simple yet powerful techniques and workflow optimizations.</p>
                <div class="price">$9.99</div>
                <a href="#" class="buy-button">Buy Now</a>
                <div class="coming-soon">Available Now</div>
            </div>
        </div>

        <div class="features">
            <div class="feature">
                <div class="feature-icon">⚡</div>
                <h3>Instant Delivery</h3>
                <p>Get immediate access to your eBook after purchase</p>
            </div>
            <div class="feature">
                <div class="feature-icon">🛡</div>
                <h3>Secure Payment</h3>
                <p>All transactions are 100% secure and encrypted</p>
            </div>
            <div class="feature">
                <div class="feature-icon">📱</div>
                <h3>Any Device</h3>
                <p>Read on your phone, tablet, or computer</p>
            </div>
            <div class="feature">
                <div class="feature-icon">💯</div>
                <h3>Money Back Guarantee</h3>
                <p>30-day satisfaction guarantee</p>
            </div>
        </div>
    </div>
</body>
</html>
