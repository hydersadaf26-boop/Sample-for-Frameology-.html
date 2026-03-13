<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Frameology10 - Premium Custom Frames</title>
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;700&family=Inter:wght@300;400;500;600&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Inter', sans-serif;
            line-height: 1.6;
            color: #333;
            overflow-x: hidden;
        }

        /* Hero Section */
        .hero {
            height: 100vh;
            background: linear-gradient(135deg, #1a1a2e 0%, #16213e 50%, #0f3460 100%);
            position: relative;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            color: white;
            overflow: hidden;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100"><defs><pattern id="grain" width="100" height="100" patternUnits="userSpaceOnUse"><circle cx="25" cy="25" r="1" fill="rgba(255,255,255,0.1)"/><circle cx="75" cy="75" r="0.5" fill="rgba(255,255,255,0.05)"/></pattern></defs><rect width="100" height="100" fill="url(%23grain)"/></svg>');
            opacity: 0.3;
        }

        .hero-content {
            position: relative;
            z-index: 2;
            max-width: 800px;
            padding: 0 20px;
            animation: fadeInUp 1.2s ease-out;
        }

        .logo {
            font-family: 'Playfair Display', serif;
            font-size: 3.5rem;
            font-weight: 700;
            margin-bottom: 1rem;
            background: linear-gradient(45deg, #ffd700, #ffed4e);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .hero h1 {
            font-family: 'Playfair Display', serif;
            font-size: 4rem;
            margin-bottom: 1.5rem;
            opacity: 0.95;
        }

        .hero p {
            font-size: 1.3rem;
            margin-bottom: 2rem;
            opacity: 0.9;
        }

        .cta-button {
            display: inline-block;
            background: linear-gradient(45deg, #ffd700, #ffed4e);
            color: #1a1a2e;
            padding: 18px 40px;
            font-size: 1.1rem;
            font-weight: 600;
            text-decoration: none;
            border-radius: 50px;
            transition: all 0.3s ease;
            box-shadow: 0 10px 30px rgba(255, 215, 0, 0.4);
        }

        .cta-button:hover {
            transform: translateY(-3px);
            box-shadow: 0 15px 40px rgba(255, 215, 0, 0.6);
        }

        /* Products Section */
        .products {
            padding: 120px 20px;
            max-width: 1400px;
            margin: 0 auto;
        }

        .section-title {
            text-align: center;
            font-family: 'Playfair Display', serif;
            font-size: 3rem;
            margin-bottom: 4rem;
            background: linear-gradient(45deg, #1a1a2e, #0f3460);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .products-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 40px;
            margin-bottom: 80px;
        }

        .product-card {
            position: relative;
            background: white;
            border-radius: 20px;
            overflow: hidden;
            box-shadow: 0 20px 60px rgba(0,0,0,0.1);
            transition: all 0.4s ease;
            cursor: pointer;
        }

        .product-card:hover {
            transform: translateY(-15px);
            box-shadow: 0 30px 80px rgba(0,0,0,0.2);
        }

        .product-image {
            height: 300px;
            background: linear-gradient(45deg, #f0f0f0, #e0e0e0);
            position: relative;
            overflow: hidden;
        }

        .product-image::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            opacity: 0;
            transition: opacity 0.3s ease;
        }

        .product-card:hover .product-image::before {
            opacity: 0.7;
        }

        .product-image i {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            font-size: 2rem;
            color: white;
            opacity: 0;
            transition: opacity 0.3s ease;
            z-index: 2;
        }

        .product-card:hover .product-image i {
            opacity: 1;
        }

        .product-info {
            padding: 30px;
        }

        .product-title {
            font-family: 'Playfair Display', serif;
            font-size: 1.5rem;
            margin-bottom: 10px;
            color: #1a1a2e;
        }

        .product-price {
            font-size: 1.3rem;
            font-weight: 600;
            color: #ffd700;
            margin-bottom: 15px;
        }

        .product-features {
            list-style: none;
            margin-bottom: 20px;
        }

        .product-features li {
            padding: 5px 0;
            color: #666;
            font-size: 0.95rem;
        }

        .product-features li i {
            color: #ffd700;
            margin-right: 10px;
            width: 15px;
        }

        /* Features Section */
        .features {
            background: linear-gradient(135deg, #f8f9ff 0%, #e8ecff 100%);
            padding: 120px 20px;
        }

        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 40px;
            max-width: 1200px;
            margin: 0 auto;
        }

        .feature-item {
            text-align: center;
            padding: 40px 20px;
        }

        .feature-icon {
            width: 80px;
            height: 80px;
            background: linear-gradient(45deg, #ffd700, #ffed4e);
            border-radius: 20px;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 20px;
            font-size: 2rem;
            color: #1a1a2e;
        }

        .feature-title {
            font-size: 1.5rem;
            margin-bottom: 15px;
            color: #1a1a2e;
        }

        /* CTA Section */
        .cta-section {
            background: linear-gradient(135deg, #1a1a2e 0%, #0f3460 100%);
            color: white;
            text-align: center;
            padding: 100px 20px;
        }

        .cta-section h2 {
            font-family: 'Playfair Display', serif;
            font-size: 3rem;
            margin-bottom: 20px;
        }

        /* Footer */
        .footer {
            background: #1a1a2e;
            color: #ccc;
            text-align: center;
            padding: 40px 20px;
        }

        /* Animations */
        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(50px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .fade-in {
            opacity: 0;
            transform: translateY(30px);
            transition: all 0.8s ease;
        }

        .fade-in.visible {
            opacity: 1;
            transform: translateY(0);
        }

        /* Responsive */
        @media (max-width: 768px) {
            .logo {
                font-size: 2.5rem;
            }
            
            .hero h1 {
                font-size: 2.5rem;
            }
            
            .section-title {
                font-size: 2.2rem;
            }
        }

        /* Scroll animations */
        .products-grid, .features-grid {
            opacity: 0;
            transform: translateY(50px);
            transition: all 0.8s ease;
        }

        .products-grid.animate, .features-grid.animate {
            opacity: 1;
            transform: translateY(0);
        }
    </style>
</head>
<body>
    <!-- Hero Section -->
    <section class="hero">
        <div class="hero-content">
            <div class="logo">FRAMEOLOGY10</div>
            <h1>Custom Frames That<br>Tell Your Story</h1>
            <p>Premium quality custom framing for your most cherished memories. Handcrafted with precision and style.</p>
            <a href="#products" class="cta-button">Explore Collections</a>
        </div>
    </section>

    <!-- Products Section -->
    <section class="products fade-in" id="products">
        <h2 class="section-title">Featured Collections</h2>
        <div class="products-grid">
            <div class="product-card">
                <div class="product-image">
                    <i class="fas fa-search-plus"></i>
                </div>
                <div class="product-info">
                    <h3 class="product-title">Gallery Wall Frames</h3>
                    <div class="product-price">$89 - $249</div>
                    <ul class="product-features">
                        <li><i class="fas fa-check"></i>Handcrafted wood frames</li>
                        <li><i class="fas fa-check"></i>Museum-quality glass</li>
                        <li><i class="fas fa-check"></i>Custom sizes available</li>
                        <li><i class="fas fa-check"></i>UV protection</li>
                    </ul>
                </div>
            </div>

            <div class="product-card">
                <div class="product-image">
                    <i class="fas fa-search-plus"></i>
                </div>
                <div class="product-info">
                    <h3 class="product-title">Floating Acrylic Frames</h3>
                    <div class="product-price">$129 - $399</div>
                    <ul class="product-features">
                        <li><i class="fas fa-check"></i>Modern acrylic design</li>
                        <li><i class="fas fa-check"></i>3D floating effect</li>
                        <li><i class="fas fa-check"></i>Anti-glare coating</li>
                        <li><i class="fas fa-check"></i>Wall mount hardware</li>
                    </ul>
                </div>
            </div>

            <div class="product-card">
                <div class="product-image">
                    <i class="fas fa-search-plus"></i>
                </div>
                <div class="product-info">
                    <h3 class="product-title">Ornate Gold Frames</h3>
                    <div class="product-price">$159 - $499</div>
                    <ul class="product-features">
                        <li><i class="fas fa-check"></i>24K gold leaf finish</li>
                        <li><i class="fas fa-check"></i>Antique styling</li>
                        <li><i class="fas fa-check"></i>Hand-carved details</li>
                        <li><i class="fas fa-check"></i>Art gallery quality</li>
                    </ul>
                </div>
            </div>

            <div class="product-card">
                <div class="product-image">
                    <i class="fas fa-search-plus"></i>
                </div>
                <div class="product-info">
                    <h3 class="product-title">Minimalist Black Frames</h3>
                    <div class="product-price">$69 - $199</div>
                    <ul class="product-features">
                        <li><i class="fas fa-check"></i>Sleek matte black</li>
                        <li><i class="fas fa-check"></i>Modern design</li>
                        <li><i class="fas fa-check"></i>Float mounting option</li>
                        <li><i class="fas fa-check"></i>Quick shipping</li>
                    </ul>
                </div>
            </div>

            <div class="product-card">
                <div class="product-image">
                    <i class="fas fa-search-plus"></i>
                </div>
                <div class="product-info">
                    <h3 class="product-title">Canvas Float Frames</h3>
                    <div class="product-price">$99 - $299</div>
                    <ul class="product-features">
                        <li><i class="fas fa-check"></i>Perfect for canvas art</li>
                        <li><i class="fas fa-check"></i>Shadowbox depth</li>
                        <li><i class="fas fa-check"></i>Multiple wood finishes</li>
                        <li><i class="fas fa-check"></i>Secure mounting</li>
                    </ul>
                </div>
            </div>

            <div class="product-card">
                <div class="product-image">
                    <i class="fas fa-search-plus"></i>
                </div>
                <div class="product-info">
                    <h3 class="product-title">Luxury Mirror Frames</h3>
                    <div class="product-price">$199 - $599</div>
                    <ul class="product-features">
                        <li><i class="fas fa-check"></i>Premium bevelled mirrors</li>
                        <li><i class="fas fa-check"></i>Ornate frame designs</li>
                        <li><i class="fas fa-check"></i>Heavy-duty construction</li>
                        <li><i class="fas fa-check"></i>Custom dimensions</li>
                    </ul>
                </div>
            </div>
        </div>
    </section>

    <!-- Features Section -->
    <section class="features">
        <div class="features-grid fade-in">
            <div class="feature-item">
                <div class="feature-icon">
                    <i class="fas fa-tools"></i>
                </div>
                <h3 class="feature-title">Handcrafted Quality</h3>
                <p>Every frame is meticulously handcrafted by skilled artisans using premium materials that last a lifetime.</p>
            </div>
            <div class="feature-item">
                <div class="feature-icon">
                    <i class="fas fa-shipping-fast"></i>
                </div>
                <h3 class="feature-title">Fast & Free Shipping</h3>
                <p>Get your custom frames delivered quickly with free shipping on orders over $100 anywhere in the country.</p>
            </div>
            <div class="feature-item">
                <div class="feature-icon">
                    <i class="fas fa-undo"></i>
                </div>
                <h3 class="feature-title">100% Satisfaction</h3>
                <p>Love it or your money back. We stand behind every frame with our satisfaction guarantee.</p>
            </div>
        </div>
    </section>

    <!-- CTA Section -->
    <section class="cta-section">
        <h2>Ready to Frame Your Memories?</h2>
        <p>Transform your artwork, photos, and memories into stunning displays</p>
        <a href="#" class="cta-button" style="background: linear-gradient(45deg, #ffd700, #ffed4e); color: #1a1a2e; margin-top: 30px;">Get Started Today</a>
    </section>

    <!-- Footer -->
    <footer class="footer">
        <p>&copy; 2024 Frameology10. All rights reserved. | Premium Custom Framing</p>
        <p style="margin-top: 10px; font-size: 0.9rem;">Follow us on <a href="https://www.instagram.com/frameology10" style="color: #ffd700;">Instagram</a></p>
    </footer>

    <script>
        // Smooth scrolling
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                document.querySelector(this.getAttribute('href')).scrollIntoView({
                    behavior: 'smooth'
                });
            });
        });

        // Scroll animations
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver(function(entries) {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('visible', 'animate');
                }
            });
        }, observerOptions);

        // Observe elements
        observer.observe(document.querySelector('.products'));
        observer.observe(document.querySelector('.features'));
        observer.observe(document.querySelector('.products-grid'));
        observer.observe(document.querySelector('.features-grid'));

        // Product card hover effects
        document.querySelectorAll('.product-card').forEach(card => {
            card.addEventListener('mouseenter', function() {
                this.style.transform = 'translateY(-15px) scale(1.02)';
            });
            
            card.addEvent
