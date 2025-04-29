
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Earning Platform</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <style>
        :root {
            --dark-blue: #0a1a2e;
            --medium-blue: #1a2d4d;
            --light-blue: #2d4a7a;
            --highlight: #3a6aab;
            --text-color: #e0e0e0;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Arial', sans-serif;
        }
        
        body {
            background-color: var(--dark-blue);
            color: var(--text-color);
            position: relative;
            overflow-x: hidden;
            background-image: url('bk.jpg');
            background-size: cover;
            background-attachment: fixed;
            background-position: center;
            background-blend-mode: overlay;
        }
        
        /* Coin animation */
        .coins {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: -1;
        }
        
        .coin {
            position: absolute;
            font-size: 20px;
            color: gold;
            animation: fall linear infinite;
            opacity: 0.7;
        }
        
        .dollar {
            position: absolute;
            font-size: 20px;
            color: lightgreen;
            animation: fall linear infinite;
            opacity: 0.7;
        }
        
        @keyframes fall {
            to {
                transform: translateY(100vh);
            }
        }
        
        /* Header styles */
        header {
            background-color: var(--medium-blue);
            padding: 15px 20px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.3);
        }
        
        .logo {
            font-size: 24px;
            font-weight: bold;
            color: var(--highlight);
        }
        
        .header-links {
            display: flex;
            gap: 20px;
        }
        
        .header-links a {
            color: var(--text-color);
            text-decoration: none;
            font-weight: bold;
            transition: color 0.3s;
        }
        
        .header-links a:hover {
            color: var(--highlight);
        }
        
        /* Main layout */
        .container {
            display: flex;
            min-height: calc(100vh - 60px);
        }
        
        /* Sidebar styles */
        .sidebar {
            width: 250px;
            background-color: var(--medium-blue);
            padding: 20px;
            display: flex;
            flex-direction: column;
            gap: 30px;
            box-shadow: 2px 0 10px rgba(0, 0, 0, 0.2);
        }
        
        .profile {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 10px;
        }
        
        .profile-pic {
            width: 80px;
            height: 80px;
            border-radius: 50%;
            background-color: var(--light-blue);
            display: flex;
            align-items: center;
            justify-content: center;
            overflow: hidden;
            border: 3px solid var(--highlight);
        }
        
        .profile-pic img {
            width: 100%;
            height: auto;
        }
        
        .profile-name {
            font-weight: bold;
            font-size: 18px;
        }
        
        .earn-amount {
            background-color: var(--light-blue);
            padding: 10px 15px;
            border-radius: 5px;
            text-align: center;
            font-weight: bold;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);
        }
        
        .sidebar-links {
            display: flex;
            flex-direction: column;
            gap: 15px;
        }
        
        .sidebar-link {
            display: flex;
            align-items: center;
            gap: 10px;
            color: var(--text-color);
            text-decoration: none;
            padding: 10px;
            border-radius: 5px;
            transition: background-color 0.3s;
        }
        
        .sidebar-link i {
            font-size: 20px;
            width: 30px;
            text-align: center;
        }
        
        .sidebar-link:hover {
            background-color: var(--light-blue);
        }
        
        .sidebar-link.active {
            background-color: var(--light-blue);
            font-weight: bold;
        }
        
        .withdraw-btn, .action-btn {
            display: inline-block;
            background-color: var(--highlight);
            color: white;
            padding: 10px 20px;
            border-radius: 5px;
            text-decoration: none;
            font-weight: bold;
            text-align: center;
            transition: background-color 0.3s;
            border: none;
            cursor: pointer;
            margin-top: 5px;
        }
        
        .withdraw-btn:hover, .action-btn:hover {
            background-color: #2d5999;
        }
        
        /* Main content styles */
        .main-content {
            flex: 1;
            padding: 30px;
            display: flex;
            flex-direction: column;
            gap: 30px;
            background-color: rgba(10, 26, 46, 0.8);
            backdrop-filter: blur(5px);
        }
        
        .earn-section {
            background-color: var(--medium-blue);
            padding: 30px;
            border-radius: 10px;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
            text-align: center;
        }
        
        .earn-section h2 {
            color: var(--highlight);
            margin-bottom: 15px;
            font-size: 28px;
        }
        
        .earn-section p {
            margin-bottom: 20px;
            line-height: 1.6;
        }
        
        .unlimited-icons {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin: 20px 0;
            flex-wrap: wrap;
        }
        
        .unlimited-icons i {
            font-size: 30px;
            color: var(--highlight);
        }
        
        .comments-section {
            display: flex;
            flex-direction: column;
            gap: 20px;
        }
        
        .comment {
            background-color: var(--medium-blue);
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
        }
        
        .comment-header {
            display: flex;
            align-items: center;
            gap: 10px;
            margin-bottom: 10px;
        }
        
        .comment-pic {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            background-color: var(--light-blue);
            display: flex;
            align-items: center;
            justify-content: center;
            overflow: hidden;
        }
        
        .comment-name {
            font-weight: bold;
        }
        
        .comment-stars {
            color: gold;
            margin-left: auto;
        }
        
        .comment-text {
            line-height: 1.5;
        }
        
        /* Footer styles */
        footer {
            background-color: var(--medium-blue);
            padding: 20px;
            text-align: center;
            margin-top: auto;
            box-shadow: 0 -2px 10px rgba(0, 0, 0, 0.2);
        }
        
        .footer-links {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin-bottom: 15px;
        }
        
        .footer-links a {
            color: var(--text-color);
            text-decoration: none;
        }
        
        .footer-links a:hover {
            text-decoration: underline;
        }
        
        .copyright {
            font-size: 14px;
            opacity: 0.8;
        }
        
        /* Mobile responsiveness */
        @media (max-width: 768px) {
            .container {
                flex-direction: column;
            }
            
            .sidebar {
                width: 100%;
                padding: 15px;
                flex-direction: row;
                flex-wrap: wrap;
                justify-content: space-around;
                gap: 15px;
            }
            
            .profile {
                flex: 1 0 100%;
            }
            
            .earn-amount {
                margin-bottom: 15px;
            }
            
            .sidebar-links {
                flex-direction: row;
                flex-wrap: wrap;
                justify-content: center;
            }
            
            .sidebar-link {
                flex: 1 0 calc(50% - 20px);
                justify-content: center;
            }
            
            .main-content {
                padding: 20px;
            }
            
            .header-links {
                display: none;
            }
        }
    </style>
</head>
<body>
    <!-- Animated coins and dollars -->
    <div class="coins" id="coins"></div>
    
    <!-- Header -->
    <header>
        <div class="logo">EarnEasy</div>
        <div class="header-links">
            <a href="https://www.profitableratecpm.com/wab8wrtnp?key=ff331281825f02c5c50f2b92db0bc276">Home</a>
            <a href="https://www.profitableratecpm.com/wab8wrtnp?key=ff331281825f02c5c50f2b92db0bc276">Earn</a>
            <a href="https://www.profitableratecpm.com/wab8wrtnp?key=ff331281825f02c5c50f2b92db0bc276">Withdraw</a>
            <a href="https://www.profitableratecpm.com/wab8wrtnp?key=ff331281825f02c5c50f2b92db0bc276">Contact</a>
        </div>
    </header>
    
    <div class="container">
        <!-- Sidebar -->
        <div class="sidebar">
            <div class="profile">
                <div class="profile-pic">
                    <img src="bk.jpg" alt="Profile Picture">
                </div>
                <div class="profile-name">Your Profile</div>
                <a href="https://www.profitableratecpm.com/wab8wrtnp?key=ff331281825f02c5c50f2b92db0bc276" class="withdraw-btn">Your Profile</a>
            </div>
            
            <div class="earn-amount">
                Earnings: $2.50
                <div style="font-size: 12px; color: var(--highlight);">Available to withdraw</div>
            </div>
            
            <div class="sidebar-links">
                <a href="https://www.profitableratecpm.com/wab8wrtnp?key=ff331281825f02c5c50f2b92db0bc276" class="sidebar-link active">
                    <i class="fas fa-home"></i>
                    <span>Home</span>
                </a>
                <a href="https://www.profitableratecpm.com/wab8wrtnp?key=ff331281825f02c5c50f2b92db0bc276" class="sidebar-link">
                    <i class="fas fa-coins"></i>
                    <span>Earn Coins</span>
                </a>
                <a href="https://www.profitableratecpm.com/wab8wrtnp?key=ff331281825f02c5c50f2b92db0bc276" class="sidebar-link">
                    <i class="fas fa-video"></i>
                    <span>Watch Videos</span>
                </a>
                <a href="https://www.profitableratecpm.com/wab8wrtnp?key=ff331281825f02c5c50f2b92db0bc276" class="sidebar-link">
                    <i class="fas fa-money-bill-wave"></i>
                    <span>Earn Money</span>
                </a>
                <a href="https://www.profitableratecpm.com/wab8wrtnp?key=ff331281825f02c5c50f2b92db0bc276" class="sidebar-link">
                    <i class="fas fa-wallet"></i>
                    <span>Withdraw</span>
                </a>
                <a href="https://www.profitableratecpm.com/wab8wrtnp?key=ff331281825f02c5c50f2b92db0bc276" class="sidebar-link">
                    <i class="fas fa-cog"></i>
                    <span>Settings</span>
                </a>
            </div>
        </div>
        
        <!-- Main content -->
        <div class="main-content">
            <div class="earn-section">
                <h2>Start Earning Today!</h2>
                <p>Earn money easily by completing simple tasks, watching videos, and participating in surveys. Our platform offers unlimited earning potential with instant withdrawals.</p>
                <p>Join thousands of users who are already making money online every day. It's fast, simple, and 100% legitimate!</p>
                
                <a href="https://www.profitableratecpm.com/wab8wrtnp?key=ff331281825f02c5c50f2b92db0bc276" class="action-btn">Click Here To Earn Unlimited Money</a>
                
                <div class="unlimited-icons">
                    <i class="fas fa-infinity"></i>
                    <i class="fas fa-dollar-sign"></i>
                    <i class="fas fa-coins"></i>
                    <i class="fas fa-gem"></i>
                    <i class="fas fa-money-bill-wave"></i>
                </div>
            </div>
            
            <div class="comments-section">
                <h3>What Our Users Say</h3>
                
                <div class="comment">
                    <div class="comment-header">
                        <div class="comment-pic">
                            <i class="fas fa-user"></i>
                        </div>
                        <div class="comment-name">Sarah Johnson</div>
                        <div class="comment-stars">
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                        </div>
                    </div>
                    <div class="comment-text">
                        I've earned over $200 in just two weeks! This platform is amazing and payments are instant. Highly recommend to anyone looking to make extra money online.
                    </div>
                </div>
                
                <div class="comment">
                    <div class="comment-header">
                        <div class="comment-pic">
                            <i class="fas fa-user"></i>
                        </div>
                        <div class="comment-name">Michael Chen</div>
                        <div class="comment-stars">
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                        </div>
                    </div>
                    <div class="comment-text">
                        Best earning app I've found. The tasks are simple and the withdrawal process is smooth. I use it during my commute to work.
                    </div>
                </div>
                
                <div class="comment">
                    <div class="comment-header">
                        <div class="comment-pic">
                            <i class="fas fa-user"></i>
                        </div>
                        <div class="comment-name">David Wilson</div>
                        <div class="comment-stars">
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star-half-alt"></i>
                        </div>
                    </div>
                    <div class="comment-text">
                        Made $50 in my first week. The platform is user-friendly and the support team is responsive. Will continue using it!
                    </div>
                </div>
                
                <div class="comment">
                    <div class="comment-header">
                        <div class="comment-pic">
                            <i class="fas fa-user"></i>
                        </div>
                        <div class="comment-name">Emma Thompson</div>
                        <div class="comment-stars">
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                        </div>
                    </div>
                    <div class="comment-text">
                        I was skeptical at first but after my first withdrawal, I'm a believer! Easy money while watching TV in the evening.
                    </div>
                </div>
                
                <div class="comment">
                    <div class="comment-header">
                        <div class="comment-pic">
                            <i class="fas fa-user"></i>
                        </div>
                        <div class="comment-name">Robert Garcia</div>
                        <div class="comment-stars">
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                        </div>
                    </div>
                    <div class="comment-text">
                        Perfect for students! I use it between classes and it helps cover my expenses. Withdrew $100 last month without issues.
                    </div>
                </div>
            </div>
        </div>
    </div>
    
    <!-- Footer -->
    <footer>
        <div class="footer-links">
            <a href="https://www.profitableratecpm.com/wab8wrtnp?key=ff331281825f02c5c50f2b92db0bc276">About Us</a>
            <a href="https://www.profitableratecpm.com/wab8wrtnp?key=ff331281825f02c5c50f2b92db0bc276">Privacy Policy</a>
            <a href="https://www.profitableratecpm.com/wab8wrtnp?key=ff331281825f02c5c50f2b92db0bc276">Terms of Service</a>
            <a href="https://www.profitableratecpm.com/wab8wrtnp?key=ff331281825f02c5c50f2b92db0bc276">Contact Support</a>
        </div>
        <div class="copyright">
            © 2023 EarnEasy. All rights reserved.
        </div>
    </footer>
    
    <script>
        // Create falling coins and dollars
        function createCoins() {
            const coinsContainer = document.getElementById('coins');
            const coinsCount = 20;
            
            for (let i = 0; i < coinsCount; i++) {
                setTimeout(() => {
                    const coin = document.createElement('div');
                    coin.className = Math.random() > 0.5 ? 'coin' : 'dollar';
                    coin.innerHTML = Math.random() > 0.5 ? '<i class="fas fa-coins"></i>' : '<i class="fas fa-dollar-sign"></i>';
                    
                    // Random position
                    const startPos = Math.random() * 100;
                    coin.style.left = `${startPos}%`;
                    coin.style.top = '-30px';
                    
                    // Random animation duration
                    const duration = 5 + Math.random() * 10;
                    coin.style.animationDuration = `${duration}s`;
                    
                    // Random delay
                    const delay = Math.random() * 5;
                    coin.style.animationDelay = `${delay}s`;
                    
                    coinsContainer.appendChild(coin);
                    
                    // Remove coin after animation completes
                    setTimeout(() => {
                        coin.remove();
                    }, duration * 1000);
                }, i * 300);
            }
        }
        
        // Create coins periodically
        createCoins();
        setInterval(createCoins, 15000);
    </script>
</body>
</html>
