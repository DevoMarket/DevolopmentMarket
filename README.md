<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CodeHire - Find Expert Programmers for Your Projects</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
            line-height: 1.6;
            color: #333;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Header */
        header {
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(10px);
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.1);
            position: sticky;
            top: 0;
            z-index: 1000;
            border-bottom: 1px solid rgba(255, 255, 255, 0.2);
        }

        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 1rem 0;
        }

        .logo {
            font-size: 1.8rem;
            font-weight: 800;
            color: #667eea;
            text-decoration: none;
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }

        .logo::before {
            content: "{ }";
            font-size: 1.5rem;
            color: #764ba2;
        }

        .nav-links {
            display: flex;
            list-style: none;
            gap: 2rem;
        }

        .nav-links a {
            text-decoration: none;
            color: #333;
            font-weight: 500;
            transition: all 0.3s ease;
            padding: 0.5rem 1rem;
            border-radius: 8px;
        }

        .nav-links a:hover {
            background: rgba(102, 126, 234, 0.1);
            color: #667eea;
            transform: translateY(-2px);
        }

        .auth-buttons {
            display: flex;
            gap: 1rem;
        }

        .btn {
            padding: 0.75rem 1.5rem;
            border: none;
            border-radius: 12px;
            font-weight: 600;
            text-decoration: none;
            cursor: pointer;
            transition: all 0.3s ease;
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
        }

        .btn-primary {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            box-shadow: 0 4px 15px rgba(102, 126, 234, 0.4);
        }

        .btn-primary:hover {
            transform: translateY(-2px);
            box-shadow: 0 8px 25px rgba(102, 126, 234, 0.6);
        }

        .btn-secondary {
            background: transparent;
            color: #667eea;
            border: 2px solid #667eea;
        }

        .btn-secondary:hover {
            background: #667eea;
            color: white;
            transform: translateY(-2px);
        }

        /* Hero Section */
        .hero {
            padding: 4rem 0;
            text-align: center;
            color: white;
        }

        .hero h1 {
            font-size: 3.5rem;
            font-weight: 800;
            margin-bottom: 1rem;
            text-shadow: 0 4px 20px rgba(0, 0, 0, 0.3);
            animation: fadeInUp 0.8s ease-out;
        }

        .hero p {
            font-size: 1.3rem;
            margin-bottom: 2rem;
            opacity: 0.9;
            max-width: 600px;
            margin-left: auto;
            margin-right: auto;
            animation: fadeInUp 0.8s ease-out 0.2s both;
        }

        .search-bar {
            max-width: 600px;
            margin: 0 auto 3rem;
            position: relative;
            animation: fadeInUp 0.8s ease-out 0.4s both;
        }

        .search-input {
            width: 100%;
            padding: 1.2rem 4rem 1.2rem 1.5rem;
            border: none;
            border-radius: 50px;
            font-size: 1.1rem;
            box-shadow: 0 10px 40px rgba(0, 0, 0, 0.2);
            backdrop-filter: blur(10px);
            background: rgba(255, 255, 255, 0.95);
        }

        .search-btn {
            position: absolute;
            right: 8px;
            top: 50%;
            transform: translateY(-50%);
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            border: none;
            padding: 0.8rem 1.5rem;
            border-radius: 50px;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .search-btn:hover {
            transform: translateY(-50%) scale(1.05);
        }

        /* Skills Tags */
        .skills-tags {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 1rem;
            margin-bottom: 3rem;
            animation: fadeInUp 0.8s ease-out 0.6s both;
        }

        .skill-tag {
            background: rgba(255, 255, 255, 0.2);
            backdrop-filter: blur(10px);
            color: white;
            padding: 0.5rem 1rem;
            border-radius: 25px;
            text-decoration: none;
            transition: all 0.3s ease;
            border: 1px solid rgba(255, 255, 255, 0.3);
        }

        .skill-tag:hover {
            background: rgba(255, 255, 255, 0.3);
            transform: translateY(-2px);
        }

        /* Main Content */
        .main-content {
            background: white;
            border-radius: 20px 20px 0 0;
            margin-top: 2rem;
            box-shadow: 0 -10px 40px rgba(0, 0, 0, 0.1);
        }

        .section {
            padding: 4rem 0;
        }

        .section-title {
            text-align: center;
            font-size: 2.5rem;
            font-weight: 800;
            margin-bottom: 3rem;
            color: #333;
        }

        /* Service Cards */
        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 2rem;
            margin-top: 3rem;
        }

        .service-card {
            background: white;
            border-radius: 16px;
            box-shadow: 0 8px 30px rgba(0, 0, 0, 0.1);
            overflow: hidden;
            transition: all 0.3s ease;
            border: 1px solid rgba(0, 0, 0, 0.05);
        }

        .service-card:hover {
            transform: translateY(-8px);
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.15);
        }

        .service-image {
            height: 200px;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 3rem;
            color: white;
        }

        .service-content {
            padding: 1.5rem;
        }

        .service-title {
            font-size: 1.3rem;
            font-weight: 700;
            margin-bottom: 0.5rem;
            color: #333;
        }

        .service-description {
            color: #666;
            margin-bottom: 1rem;
            line-height: 1.6;
        }

        .service-meta {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 1rem;
        }

        .service-price {
            font-size: 1.2rem;
            font-weight: 700;
            color: #667eea;
        }

        .service-rating {
            display: flex;
            align-items: center;
            gap: 0.3rem;
            color: #ffa500;
        }

        .freelancer-info {
            display: flex;
            align-items: center;
            gap: 0.75rem;
            margin-bottom: 1rem;
        }

        .freelancer-avatar {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-weight: 600;
        }

        .freelancer-name {
            font-weight: 600;
            color: #333;
        }

        /* Categories */
        .categories-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            margin-top: 3rem;
        }

        /* Job Board Styles */
        .job-card {
            border-left: 4px solid #667eea;
        }

        .job-urgent .service-image {
            background: linear-gradient(135deg, #ff6b6b 0%, #ee5a52 100%);
        }

        .job-ai .service-image {
            background: linear-gradient(135deg, #4ecdc4 0%, #44a08d 100%);
        }

        .job-mobile .service-image {
            background: linear-gradient(135deg, #a8edea 0%, #fed6e3 100%);
            color: #333;
        }

        .job-blockchain .service-image {
            background: linear-gradient(135deg, #ffecd2 0%, #fcb69f 100%);
            color: #333;
        }

        .job-devops .service-image {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
        }

        .job-game .service-image {
            background: linear-gradient(135deg, #f093fb 0%, #f5576c 100%);
        }

        .job-meta-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 1rem;
        }

        .job-type {
            background: rgba(102, 126, 234, 0.1);
            color: #667eea;
            padding: 0.3rem 0.8rem;
            border-radius: 15px;
            font-size: 0.8rem;
            font-weight: 600;
        }

        .job-urgency {
            padding: 0.3rem 0.8rem;
            border-radius: 15px;
            font-size: 0.8rem;
            font-weight: 600;
        }

        .job-urgency.urgent {
            background: rgba(255, 107, 107, 0.1);
            color: #ff6b6b;
        }

        .job-urgency.high {
            background: rgba(255, 165, 0, 0.1);
            color: #ffa500;
        }

        .job-urgency.normal {
            background: rgba(76, 175, 80, 0.1);
            color: #4caf50;
        }

        .job-details {
            margin: 1.5rem 0;
        }

        .job-budget {
            margin-bottom: 1rem;
            color: #667eea;
            font-size: 1.1rem;
        }

        .job-skills {
            display: flex;
            flex-wrap: wrap;
            gap: 0.5rem;
            margin-bottom: 1rem;
        }

        .skill-badge {
            background: rgba(102, 126, 234, 0.1);
            color: #667eea;
            padding: 0.3rem 0.7rem;
            border-radius: 12px;
            font-size: 0.8rem;
            font-weight: 500;
        }

        .job-footer {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 1rem;
            color: #666;
            font-size: 0.9rem;
        }

        .job-applications {
            font-weight: 600;
            color: #667eea;
        }

        .category-card {
            background: white;
            border-radius: 16px;
            padding: 2rem;
            text-align: center;
            box-shadow: 0 8px 30px rgba(0, 0, 0, 0.1);
            transition: all 0.3s ease;
            border: 1px solid rgba(0, 0, 0, 0.05);
        }

        .category-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 45px rgba(0, 0, 0, 0.15);
        }

        .category-icon {
            font-size: 3rem;
            margin-bottom: 1rem;
        }

        .category-title {
            font-size: 1.3rem;
            font-weight: 700;
            margin-bottom: 0.5rem;
            color: #333;
        }

        .category-count {
            color: #666;
            font-size: 0.9rem;
        }

        /* Footer */
        footer {
            background: #2d3748;
            color: white;
            padding: 3rem 0;
            text-align: center;
        }

        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            margin-bottom: 2rem;
        }

        .footer-section h3 {
            margin-bottom: 1rem;
            color: #667eea;
        }

        .footer-section ul {
            list-style: none;
        }

        .footer-section a {
            color: #cbd5e0;
            text-decoration: none;
            transition: color 0.3s ease;
            line-height: 2;
        }

        .footer-section a:hover {
            color: #667eea;
        }

        /* Animations */
        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* Responsive */
        @media (max-width: 768px) {
            .nav-links {
                display: none;
            }

            .hero h1 {
                font-size: 2.5rem;
            }

            .hero p {
                font-size: 1.1rem;
            }

            .services-grid,
            .categories-grid {
                grid-template-columns: 1fr;
            }

            .skills-tags {
                gap: 0.5rem;
            }
        }
    </style>
</head>
<body>
    <header>
        <nav class="container">
            <a href="#" class="logo">CodeHire</a>
            <ul class="nav-links">
                <li><a href="#services">Browse Services</a></li>
                <li><a href="#categories">Categories</a></li>
                <li><a href="#job-board">Job Board</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
            <div class="auth-buttons">
                <a href="#" class="btn btn-secondary">Sign In</a>
                <a href="#" class="btn btn-primary">Join as Freelancer</a>
            </div>
        </nav>
    </header>

    <main>
        <section class="hero">
            <div class="container">
                <h1>Find Expert Programmers for Any Task</h1>
                <p>Connect with skilled developers for web development, mobile apps, AI solutions, and more. Get your project done by verified professionals.</p>
                
                <div class="search-bar">
                    <input type="text" class="search-input" placeholder="What programming task do you need help with?">
                    <button class="search-btn">Search</button>
                </div>

                <div class="skills-tags">
                    <a href="#" class="skill-tag">Python</a>
                    <a href="#" class="skill-tag">React</a>
                    <a href="#" class="skill-tag">Node.js</a>
                    <a href="#" class="skill-tag">AI/ML</a>
                    <a href="#" class="skill-tag">Mobile Apps</a>
                    <a href="#" class="skill-tag">Blockchain</a>
                    <a href="#" class="skill-tag">DevOps</a>
                </div>
            </div>
        </section>

        <div class="main-content">
            <section id="services" class="section">
                <div class="container">
                    <h2 class="section-title">Featured Programming Services</h2>
                    <div class="services-grid">
                        <div class="service-card">
                            <div class="service-image">🤖</div>
                            <div class="service-content">
                                <div class="freelancer-info">
                                    <div class="freelancer-avatar">AM</div>
                                    <span class="freelancer-name">Alice Morgan</span>
                                </div>
                                <h3 class="service-title">I will create AI chatbots and ML models</h3>
                                <p class="service-description">Custom AI solutions using Python, TensorFlow, and GPT integration. From simple chatbots to complex machine learning models.</p>
                                <div class="service-meta">
                                    <span class="service-price">Starting at $99</span>
                                    <div class="service-rating">
                                        <span>⭐⭐⭐⭐⭐</span>
                                        <span>(32)</span>
                                    </div>
                                </div>
                                <a href="#" class="btn btn-primary">View Details</a>
                            </div>
                        </div>

                        <div class="service-card">
                            <div class="service-image">🛡️</div>
                            <div class="service-content">
                                <div class="freelancer-info">
                                    <div class="freelancer-avatar">DW</div>
                                    <span class="freelancer-name">David Wilson</span>
                                </div>
                                <h3 class="service-title">I will set up DevOps and cloud infrastructure</h3>
                                <p class="service-description">AWS, Docker, Kubernetes deployment pipelines. CI/CD automation and monitoring setup.</p>
                                <div class="service-meta">
                                    <span class="service-price">Starting at $149</span>
                                    <div class="service-rating">
                                        <span>⭐⭐⭐⭐⭐</span>
                                        <span>(41)</span>
                                    </div>
                                </div>
                                <a href="#" class="btn btn-primary">View Details</a>
                            </div>
                        </div>

                        <div class="service-card">
                            <div class="service-image">🚀</div>
                            <div class="service-content">
                                <div class="freelancer-info">
                                    <div class="freelancer-avatar">JS</div>
                                    <span class="freelancer-name">John Smith</span>
                                </div>
                                <h3 class="service-title">I will build a custom React web application</h3>
                                <p class="service-description">Full-stack React development with modern UI/UX, API integration, and responsive design. Perfect for startups and businesses.</p>
                                <div class="service-meta">
                                    <span class="service-price">Starting at $199</span>
                                    <div class="service-rating">
                                        <span>⭐⭐⭐⭐⭐</span>
                                        <span>(47)</span>
                                    </div>
                                </div>
                                <a href="#" class="btn btn-primary">View Details</a>
                            </div>
                        </div>

                        <div class="service-card">
                            <div class="service-image">🎮</div>
                            <div class="service-content">
                                <div class="freelancer-info">
                                    <div class="freelancer-avatar">LB</div>
                                    <span class="freelancer-name">Lisa Brown</span>
                                </div>
                                <h3 class="service-title">I will create Unity games and 3D applications</h3>
                                <p class="service-description">2D/3D game development, AR/VR experiences, and interactive applications using Unity and C#.</p>
                                <div class="service-meta">
                                    <span class="service-price">Starting at $249</span>
                                    <div class="service-rating">
                                        <span>⭐⭐⭐⭐⭐</span>
                                        <span>(24)</span>
                                    </div>
                                </div>
                                <a href="#" class="btn btn-primary">View Details</a>
                            </div>
                        </div>

                        <div class="service-card">
                            <div class="service-image">⛓️</div>
                            <div class="service-content">
                                <div class="freelancer-info">
                                    <div class="freelancer-avatar">SC</div>
                                    <span class="freelancer-name">Sarah Chen</span>
                                </div>
                                <h3 class="service-title">I will build smart contracts and DApps</h3>
                                <p class="service-description">Ethereum and Solidity development for DeFi, NFTs, and Web3 applications. Security audits included.</p>
                                <div class="service-meta">
                                    <span class="service-price">Starting at $299</span>
                                    <div class="service-rating">
                                        <span>⭐⭐⭐⭐⭐</span>
                                        <span>(19)</span>
                                    </div>
                                </div>
                                <a href="#" class="btn btn-primary">View Details</a>
                            </div>
                        </div>

                        <div class="service-card">
                            <div class="service-image">📱</div>
                            <div class="service-content">
                                <div class="freelancer-info">
                                    <div class="freelancer-avatar">MK</div>
                                    <span class="freelancer-name">Mike Kumar</span>
                                </div>
                                <h3 class="service-title">I will develop iOS and Android mobile apps</h3>
                                <p class="service-description">Cross-platform mobile development using React Native and Flutter. App store deployment included.</p>
                                <div class="service-meta">
                                    <span class="service-price">Starting at $399</span>
                                    <div class="service-rating">
                                        <span>⭐⭐⭐⭐⭐</span>
                                        <span>(28)</span>
                                    </div>
                                </div>
                                <a href="#" class="btn btn-primary">View Details</a>
                            </div>
                        </div>
                    </div>
                </div>
            </section>

            <section id="categories" class="section" style="background: #f8fafc;">
                <div class="container">
                    <h2 class="section-title">Browse by Category</h2>
                    <div class="categories-grid">
                        <div class="category-card">
                            <div class="category-icon">🌐</div>
                            <h3 class="category-title">Web Development</h3>
                            <p class="category-count">1,247 services available</p>
                        </div>
                        <div class="category-card">
                            <div class="category-icon">📱</div>
                            <h3 class="category-title">Mobile Development</h3>
                            <p class="category-count">856 services available</p>
                        </div>
                        <div class="category-card">
                            <div class="category-icon">🤖</div>
                            <h3 class="category-title">AI & Machine Learning</h3>
                            <p class="category-count">623 services available</p>
                        </div>
                        <div class="category-card">
                            <div class="category-icon">⛓️</div>
                            <h3 class="category-title">Blockchain & Crypto</h3>
                            <p class="category-count">389 services available</p>
                        </div>
                        <div class="category-card">
                            <div class="category-icon">🛡️</div>
                            <h3 class="category-title">DevOps & Cloud</h3>
                            <p class="category-count">734 services available</p>
                        </div>
                        <div class="category-card">
                            <div class="category-icon">🎮</div>
                            <h3 class="category-title">Game Development</h3>
                            <p class="category-count">412 services available</p>
                        </div>
                        <div class="category-card">
                            <div class="category-icon">📊</div>
                            <h3 class="category-title">Data Science</h3>
                            <p class="category-count">567 services available</p>
                        </div>
                        <div class="category-card">
                            <div class="category-icon">🔒</div>
                            <h3 class="category-title">Cybersecurity</h3>
                            <p class="category-count">298 services available</p>
                        </div>
                    </div>
                </div>
            </section>

            <section id="job-board" class="section">
                <div class="container">
                    <h2 class="section-title">Job Board - Open Programming Tasks</h2>
                    <p style="text-align: center; color: #666; margin-bottom: 3rem; font-size: 1.1rem;">Browse available programming jobs posted by clients looking for expert developers</p>
                    
                    <div class="services-grid">
                        <div class="service-card job-card">
                            <div class="service-image job-urgent">🚨</div>
                            <div class="service-content">
                                <div class="job-meta-header">
                                    <span class="job-type">Fixed Price</span>
                                    <span class="job-urgency urgent">Urgent</span>
                                </div>
                                <h3 class="service-title">Need React Dashboard Built ASAP</h3>
                                <p class="service-description">Looking for an experienced React developer to build a comprehensive admin dashboard with charts, user management, and API integration. Must be completed within 5 days.</p>
                                <div class="job-details">
                                    <div class="job-budget">
                                        <strong>Budget: $800 - $1,200</strong>
                                    </div>
                                    <div class="job-skills">
                                        <span class="skill-badge">React</span>
                                        <span class="skill-badge">JavaScript</span>
                                        <span class="skill-badge">API Integration</span>
                                    </div>
                                </div>
                                <div class="job-footer">
                                    <span class="job-posted">Posted 2 hours ago</span>
                                    <span class="job-applications">3 proposals</span>
                                </div>
                                <a href="#" class="btn btn-primary">Apply Now</a>
                            </div>
                        </div>

                        <div class="service-card job-card">
                            <div class="service-image job-ai">🤖</div>
                            <div class="service-content">
                                <div class="job-meta-header">
                                    <span class="job-type">Hourly</span>
                                    <span class="job-urgency normal">Normal</span>
                                </div>
                                <h3 class="service-title">AI Chatbot for Customer Support</h3>
                                <p class="service-description">Seeking an AI specialist to develop a conversational chatbot using GPT API for our e-commerce platform. Should handle common customer inquiries and integrate with our existing support system.</p>
                                <div class="job-details">
                                    <div class="job-budget">
                                        <strong>Rate: $40 - $60/hour</strong>
                                    </div>
                                    <div class="job-skills">
                                        <span class="skill-badge">Python</span>
                                        <span class="skill-badge">OpenAI API</span>
                                        <span class="skill-badge">Machine Learning</span>
                                    </div>
                                </div>
                                <div class="job-footer">
                                    <span class="job-posted">Posted 1 day ago</span>
                                    <span class="job-applications">8 proposals</span>
                                </div>
                                <a href="#" class="btn btn-primary">Apply Now</a>
                            </div>
                        </div>

                        <div class="service-card job-card">
                            <div class="service-image job-mobile">📱</div>
                            <div class="service-content">
                                <div class="job-meta-header">
                                    <span class="job-type">Fixed Price</span>
                                    <span class="job-urgency normal">Normal</span>
                                </div>
                                <h3 class="service-title">Cross-Platform Fitness App</h3>
                                <p class="service-description">Need a React Native developer to create a fitness tracking app with workout plans, progress tracking, and social features. Design mockups provided.</p>
                                <div class="job-details">
                                    <div class="job-budget">
                                        <strong>Budget: $2,000 - $3,500</strong>
                                    </div>
                                    <div class="job-skills">
                                        <span class="skill-badge">React Native</span>
                                        <span class="skill-badge">Firebase</span>
                                        <span class="skill-badge">Mobile UI/UX</span>
                                    </div>
                                </div>
                                <div class="job-footer">
                                    <span class="job-posted">Posted 3 days ago</span>
                                    <span class="job-applications">12 proposals</span>
                                </div>
                                <a href="#" class="btn btn-primary">Apply Now</a>
                            </div>
                        </div>

                        <div class="service-card job-card">
                            <div class="service-image job-blockchain">⛓️</div>
                            <div class="service-content">
                                <div class="job-meta-header">
                                    <span class="job-type">Fixed Price</span>
                                    <span class="job-urgency high">High Priority</span>
                                </div>
                                <h3 class="service-title">Smart Contract Audit & Optimization</h3>
                                <p class="service-description">Looking for a blockchain security expert to audit existing smart contracts and optimize gas usage. Previous DeFi experience required.</p>
                                <div class="job-details">
                                    <div class="job-budget">
                                        <strong>Budget: $1,500 - $2,500</strong>
                                    </div>
                                    <div class="job-skills">
                                        <span class="skill-badge">Solidity</span>
                                        <span class="skill-badge">Smart Contracts</span>
                                        <span class="skill-badge">Security Audit</span>
                                    </div>
                                </div>
                                <div class="job-footer">
                                    <span class="job-posted">Posted 5 days ago</span>
                                    <span class="job-applications">5 proposals</span>
                                </div>
                                <a href="#" class="btn btn-primary">Apply Now</a>
                            </div>
                        </div>

                        <div class="service-card job-card">
                            <div class="service-image job-devops">🛡️</div>
                            <div class="service-content">
                                <div class="job-meta-header">
                                    <span class="job-type">Hourly</span>
                                    <span class="job-urgency normal">Normal</span>
                                </div>
                                <h3 class="service-title">AWS Infrastructure Setup & Migration</h3>
                                <p class="service-description">Need a DevOps engineer to migrate our current hosting to AWS with proper CI/CD pipelines, monitoring, and auto-scaling setup.</p>
                                <div class="job-details">
                                    <div class="job-budget">
                                        <strong>Rate: $50 - $80/hour</strong>
                                    </div>
                                    <div class="job-skills">
                                        <span class="skill-badge">AWS</span>
                                        <span class="skill-badge">Docker</span>
                                        <span class="skill-badge">CI/CD</span>
                                    </div>
                                </div>
                                <div class="job-footer">
                                    <span class="job-posted">Posted 1 week ago</span>
                                    <span class="job-applications">15 proposals</span>
                                </div>
                                <a href="#" class="btn btn-primary">Apply Now</a>
                            </div>
                        </div>

                        <div class="service-card job-card">
                            <div class="service-image job-game">🎮</div>
                            <div class="service-content">
                                <div class="job-meta-header">
                                    <span class="job-type">Fixed Price</span>
                                    <span class="job-urgency normal">Normal</span>
                                </div>
                                <h3 class="service-title">2D Puzzle Game in Unity</h3>
                                <p class="service-description">Looking for a Unity developer to create a 2D puzzle game with 50 levels, power-ups, and social leaderboards. Game design document provided.</p>
                                <div class="job-details">
                                    <div class="job-budget">
                                        <strong>Budget: $3,000 - $5,000</strong>
                                    </div>
                                    <div class="job-skills">
                                        <span class="skill-badge">Unity</span>
                                        <span class="skill-badge">C#</span>
                                        <span class="skill-badge">2D Game Dev</span>
                                    </div>
                                </div>
                                <div class="job-footer">
                                    <span class="job-posted">Posted 1 week ago</span>
                                    <span class="job-applications">7 proposals</span>
                                </div>
                                <a href="#" class="btn btn-primary">Apply Now</a>
                            </div>
                        </div>
                    </div>

                    <div style="text-align: center; margin-top: 3rem;">
                        <a href="#" class="btn btn-secondary" style="margin-right: 1rem;">View All Jobs</a>
                        <a href="#" class="btn btn-primary">Post a Job</a>
                    </div>
                </div>
            </section>
        </div>
    </main>

    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="footer-section">
                    <h3>For Clients</h3>
                    <ul>
                        <li><a href="#">How to hire</a></li>
                        <li><a href="#">Project management</a></li>
                        <li><a href="#">Success stories</a></li>
                        <li><a href="#">Enterprise</a></li>
                    </ul>
                </div>
                <div class="footer-section">
                    <h3>For Freelancers</h3>
                    <ul>
                        <li><a href="#">How to sell</a></li>
                        <li><a href="#">Freelancer resources</a></li>
                        <li><a href="#">Community</a></li>
                        <li><a href="#">Success guide</a></li>
                    </ul>
                </div>
                <div class="footer-section">
                    <h3>Support</h3>
                    <ul>
                        <li><a href="#">Help center</a></li>
                        <li><a href="#">Contact us</a></li>
                        <li><a href="#">Safety center</a></li>
                        <li><a href="#">Trust & safety</a></li>
                    </ul>
                </div>
                <div class="footer-section">
                    <h3>Company</h3>
                    <ul>
                        <li><a href="#">About us</a></li>
                        <li><a href="#">Careers</a></li>
                        <li><a href="#">Press</a></li>
                        <li><a href="#">Terms of service</a></li>
                    </ul>
                </div>
            </div>
            <p>&copy; 2025 CodeHire. All rights reserved. Connecting clients with expert programmers worldwide.</p>
        </div>
    </footer>

    <script>
        // Add smooth scrolling for navigation links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({
                        behavior: 'smooth',
                        block: 'start'
                    });
                }
            });
        });

        // Add search functionality
        const searchInput = document.querySelector('.search-input');
        const searchBtn = document.querySelector('.search-btn');

        searchBtn.addEventListener('click', function() {
            const query = searchInput.value.trim();
            if (query) {
                alert(`Searching for: "${query}"\n\nThis would normally redirect to search results page.`);
            }
        });

        searchInput.addEventListener('keypress', function(e) {
            if (e.key === 'Enter') {
                searchBtn.click();
            }
        });

        // Add hover effects for service cards
        document.querySelectorAll('.service-card, .category-card').forEach(card => {
            card.addEventListener('mouseenter', function() {
                this.style.transform = 'translateY(-8px) scale(1.02)';
            });
            
            card.addEventListener('mouseleave', function() {
                this.style.transform = 'translateY(0) scale(1)';
            });
        });

        // Add click handlers for service buttons
        document.querySelectorAll('.service-card .btn').forEach(btn => {
            btn.addEventListener('click', function(e) {
                e.preventDefault();
                const serviceTitle = this.closest('.service-card').querySelector('.service-title').textContent;
                
                // Check if this is a job application or service view
                if (this.textContent === 'Apply Now') {
                    alert(`Applying for job: "${serviceTitle}"\n\nThis would normally open the job application form where you can submit your proposal.`);
                } else if (this.textContent === 'View All Jobs') {
                    alert(`Loading all available jobs...\n\nThis would show a complete list of all posted programming jobs with filters and search functionality.`);
                } else if (this.textContent === 'Post a Job') {
                    alert(`Opening job posting form...\n\nThis would allow clients to post new programming tasks with budget, timeline, and requirements.`);
                } else {
                    alert(`Opening service: "${serviceTitle}"\n\nThis would normally open the service details page.`);
                }
            });
        });

        // Add category card click handlers
        document.querySelectorAll('.category-card').forEach(card => {
            card.addEventListener('click', function() {
                const categoryTitle = this.querySelector('.category-title').textContent;
                alert(`Browsing category: "${categoryTitle}"\n\nThis would normally show all services in this category.`);
            });
        });

        // Add navigation menu interactivity
        document.querySelectorAll('.nav-links a, .auth-buttons a').forEach(link => {
            link.addEventListener('click', function(e) {
                if (!this.getAttribute('href').startsWith('#')) {
                    e.preventDefault();
                    const linkText = this.textContent;
                    alert(`Navigating to: "${linkText}"\n\nThis would normally redirect to the ${linkText.toLowerCase()} page.`);
                }
            });
        });

        // Add skill tag interactivity
        document.querySelectorAll('.skill-tag').forEach(tag => {
            tag.addEventListener('click', function(e) {
                e.preventDefault();
                const skill = this.textContent;
                alert(`Searching for ${skill} services...\n\nThis would show all services related to ${skill}.`);
            });
        });

        // Add scroll-based animations
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver(function(entries) {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = '1';
                    entry.target.style.transform = 'translateY(0)';
                }
            });
        }, observerOptions);

        // Observe service and category cards for scroll animations
        document.querySelectorAll('.service-card, .category-card').forEach(card => {
            card.style.opacity = '0';
            card.style.transform = 'translateY(30px)';
            card.style.transition = 'opacity 0.6s ease, transform 0.6s ease';
            observer.observe(card);
        });

        // Add header background change on scroll
        window.addEventListener('scroll', function() {
            const header = document.querySelector('header');
            if (window.scrollY > 100) {
                header.style.background = 'rgba(255, 255, 255, 0.98)';
                header.style.boxShadow = '0 8px 32px rgba(0, 0, 0, 0.15)';
            } else {
                header.style.background = 'rgba(255, 255, 255, 0.95)';
                header.style.boxShadow = '0 8px 32px rgba(0, 0, 0, 0.1)';
            }
        });
    </script>
</body>
</html>
