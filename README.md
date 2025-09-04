
<html lang="th">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Blue Archive Event - บางซื่อ Official Gathering</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Noto+Sans:wght@300;400;500;600;700;800&family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Noto Sans', 'Inter', sans-serif;
            background: #0a1628;
            color: white;
            overflow-x: hidden;
            position: relative;
        }

        /* Blue Archive authentic background */
        .bg-container {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, #0a1628 0%, #1e3a5f 25%, #2d4f73 50%, #4a6fa5 75%, #6b93d6 100%);
            z-index: -3;
        }

        .bg-pattern {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-image: 
                radial-gradient(circle at 20% 50%, rgba(107, 147, 214, 0.1) 0%, transparent 50%),
                radial-gradient(circle at 80% 20%, rgba(139, 195, 74, 0.1) 0%, transparent 50%),
                radial-gradient(circle at 40% 80%, rgba(255, 193, 7, 0.08) 0%, transparent 50%);
            background-size: 800px 800px;
            animation: float 20s ease-in-out infinite;
            z-index: -2;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px) rotate(0deg); }
            33% { transform: translateY(-20px) rotate(1deg); }
            66% { transform: translateY(10px) rotate(-1deg); }
        }

        /* Blue Archive hexagon pattern */
        .hexagon-pattern {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-image: 
                repeating-linear-gradient(30deg, transparent, transparent 10px, rgba(107, 147, 214, 0.05) 10px, rgba(107, 147, 214, 0.05) 20px),
                repeating-linear-gradient(-30deg, transparent, transparent 10px, rgba(139, 195, 74, 0.03) 10px, rgba(139, 195, 74, 0.03) 20px);
            z-index: -1;
        }

        /* Header Navigation (Blue Archive style) */
        .header-nav {
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            background: rgba(10, 22, 40, 0.95);
            backdrop-filter: blur(20px);
            border-bottom: 1px solid rgba(107, 147, 214, 0.2);
            padding: 12px 0;
            z-index: 1000;
        }

        .nav-container {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            align-items: center;
            justify-content: space-between;
            padding: 0 20px;
        }

        .logo {
            font-size: 1.5rem;
            font-weight: 700;
            color: #6b93d6;
            text-decoration: none;
        }

        .nav-menu {
            display: flex;
            gap: 30px;
            align-items: center;
        }

        .nav-item {
            color: rgba(255, 255, 255, 0.8);
            text-decoration: none;
            font-weight: 500;
            transition: all 0.3s ease;
            position: relative;
        }

        .nav-item:hover {
            color: #6b93d6;
        }

        .nav-item.active::after {
            content: '';
            position: absolute;
            bottom: -8px;
            left: 0;
            right: 0;
            height: 2px;
            background: #6b93d6;
            border-radius: 1px;
        }

        /* Main Content Container */
        .main-container {
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            padding: 100px 20px 50px;
            position: relative;
        }

        /* Blue Archive style title section */
        .title-section {
            text-align: center;
            margin-bottom: 60px;
            position: relative;
        }

        .main-title {
            font-size: 4rem;
            font-weight: 800;
            background: linear-gradient(135deg, #6b93d6 0%, #4fc3f7 50%, #81c784 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            margin-bottom: 20px;
            text-shadow: 0 0 30px rgba(107, 147, 214, 0.3);
            letter-spacing: -0.02em;
            line-height: 0.9;
        }

        .subtitle {
            font-size: 1.8rem;
            color: rgba(255, 255, 255, 0.9);
            font-weight: 300;
            margin-bottom: 10px;
        }

        .tagline {
            font-size: 1rem;
            color: rgba(107, 147, 214, 0.8);
            font-weight: 400;
            font-style: italic;
        }

        /* Blue Archive authentic event card */
        .event-card {
            background: linear-gradient(135deg, rgba(255, 255, 255, 0.1) 0%, rgba(255, 255, 255, 0.05) 100%);
            backdrop-filter: blur(30px);
            border-radius: 24px;
            border: 1px solid rgba(107, 147, 214, 0.3);
            box-shadow: 
                0 20px 40px rgba(0, 0, 0, 0.3),
                inset 0 1px 0 rgba(255, 255, 255, 0.1),
                0 0 60px rgba(107, 147, 214, 0.1);
            max-width: 800px;
            width: 100%;
            padding: 50px;
            position: relative;
            overflow: hidden;
        }

        .event-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 3px;
            background: linear-gradient(90deg, #6b93d6, #4fc3f7, #81c784, #ffb74d, #f06292);
            background-size: 300% 100%;
            animation: rainbow-flow 4s linear infinite;
        }

        @keyframes rainbow-flow {
            0% { background-position: 0% 50%; }
            100% { background-position: 300% 50%; }
        }

        /* Countdown Grid */
        .countdown-wrapper {
            text-align: center;
            margin-bottom: 40px;
        }

        .countdown-title {
            font-size: 2rem;
            font-weight: 600;
            color: #6b93d6;
            margin-bottom: 30px;
            position: relative;
            display: inline-block;
        }

        .countdown-title::after {
            content: '';
            position: absolute;
            bottom: -8px;
            left: 50%;
            transform: translateX(-50%);
            width: 60px;
            height: 2px;
            background: linear-gradient(90deg, #6b93d6, #4fc3f7);
        }

        .countdown-grid {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 20px;
            margin: 40px 0;
        }

        .time-card {
            background: linear-gradient(135deg, rgba(107, 147, 214, 0.15) 0%, rgba(79, 195, 247, 0.1) 100%);
            border: 1px solid rgba(107, 147, 214, 0.3);
            border-radius: 20px;
            padding: 30px 20px;
            text-align: center;
            position: relative;
            transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
            overflow: hidden;
        }

        .time-card::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: linear-gradient(45deg, transparent, rgba(107, 147, 214, 0.1), transparent);
            transform: rotate(-45deg);
            transition: all 0.6s ease;
            opacity: 0;
        }

        .time-card:hover::before {
            animation: shimmer-sweep 1s ease-in-out;
        }

        @keyframes shimmer-sweep {
            0% { transform: translateX(-100%) rotate(-45deg); opacity: 0; }
            50% { opacity: 1; }
            100% { transform: translateX(100%) rotate(-45deg); opacity: 0; }
        }

        .time-card:hover {
            transform: translateY(-8px) scale(1.02);
            box-shadow: 0 20px 40px rgba(107, 147, 214, 0.2);
            border-color: rgba(107, 147, 214, 0.5);
        }

        .time-number {
            font-size: 3.5rem;
            font-weight: 800;
            color: white;
            display: block;
            line-height: 1;
            margin-bottom: 12px;
            text-shadow: 0 4px 12px rgba(107, 147, 214, 0.4);
        }

        .time-label {
            font-size: 1rem;
            color: rgba(107, 147, 214, 0.9);
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        /* Event Info Section */
        .event-info {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 30px;
            margin: 40px 0;
        }

        .info-card {
            background: linear-gradient(135deg, rgba(129, 199, 132, 0.15) 0%, rgba(139, 195, 74, 0.1) 100%);
            border: 1px solid rgba(129, 199, 132, 0.3);
            border-radius: 16px;
            padding: 25px;
            text-align: center;
            transition: all 0.3s ease;
        }

        .info-card:hover {
            transform: translateY(-4px);
            box-shadow: 0 12px 24px rgba(129, 199, 132, 0.2);
        }

        .info-icon {
            font-size: 2.5rem;
            margin-bottom: 15px;
            display: block;
        }

        .info-title {
            font-size: 1.1rem;
            font-weight: 600;
            color: #81c784;
            margin-bottom: 8px;
        }

        .info-text {
            color: rgba(255, 255, 255, 0.8);
            font-size: 1rem;
        }

        /* GPS Navigation Button */
        .nav-button {
            background: linear-gradient(135deg, #6b93d6 0%, #4fc3f7 100%);
            color: white;
            border: none;
            padding: 18px 40px;
            font-size: 1.2rem;
            font-weight: 600;
            border-radius: 50px;
            cursor: pointer;
            transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
            display: inline-flex;
            align-items: center;
            gap: 12px;
            text-decoration: none;
            box-shadow: 0 8px 24px rgba(107, 147, 214, 0.3);
            position: relative;
            overflow: hidden;
            margin-top: 30px;
        }

        .nav-button::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.3), transparent);
            transition: left 0.6s;
        }

        .nav-button:hover::before {
            left: 100%;
        }

        .nav-button:hover {
            transform: translateY(-3px) scale(1.05);
            box-shadow: 0 12px 32px rgba(107, 147, 214, 0.4);
            background: linear-gradient(135deg, #4fc3f7 0%, #6b93d6 100%);
        }

        .nav-button:active {
            transform: translateY(-1px) scale(1.02);
        }

        /* Celebration animation for when countdown ends */
        .celebration {
            text-align: center;
            padding: 60px 40px;
            background: linear-gradient(135deg, rgba(129, 199, 132, 0.2) 0%, rgba(255, 193, 7, 0.15) 100%);
            border: 2px solid rgba(129, 199, 132, 0.4);
            border-radius: 20px;
            animation: celebrate 2s ease-in-out infinite;
        }

        @keyframes celebrate {
            0%, 100% { transform: scale(1) rotate(0deg); }
            25% { transform: scale(1.02) rotate(0.5deg); }
            75% { transform: scale(1.02) rotate(-0.5deg); }
        }

        .celebration-text {
            font-size: 3rem;
            font-weight: 800;
            background: linear-gradient(135deg, #81c784, #ffb74d, #f06292);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            margin-bottom: 20px;
        }

        .celebration-subtitle {
            font-size: 1.4rem;
            color: rgba(255, 255, 255, 0.9);
            font-weight: 400;
        }

        /* Footer */
        .footer {
            margin-top: 50px;
            padding-top: 30px;
            border-top: 1px solid rgba(107, 147, 214, 0.2);
            text-align: center;
            color: rgba(255, 255, 255, 0.6);
        }

        .footer-tagline {
            font-size: 1.1rem;
            margin-bottom: 10px;
            color: rgba(107, 147, 214, 0.8);
            font-style: italic;
        }

        .coordinates {
            font-size: 0.9rem;
            font-family: 'Courier New', monospace;
            color: rgba(255, 255, 255, 0.5);
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .main-title {
                font-size: 2.5rem;
            }

            .event-card {
                padding: 30px 25px;
                margin: 0 15px;
            }

            .countdown-grid {
                grid-template-columns: repeat(2, 1fr);
                gap: 15px;
            }

            .time-number {
                font-size: 2.5rem;
            }

            .nav-menu {
                display: none;
            }

            .info-card {
                padding: 20px;
            }
        }

        @media (max-width: 480px) {
            .main-title {
                font-size: 2rem;
            }

            .subtitle {
                font-size: 1.4rem;
            }

            .time-number {
                font-size: 2rem;
            }

            .event-card {
                padding: 25px 20px;
            }

            .nav-button {
                padding: 16px 32px;
                font-size: 1.1rem;
            }
        }

        /* Loading animation */
        .loading-indicator {
            display: flex;
            justify-content: center;
            gap: 8px;
            margin: 20px 0;
        }

        .loading-dot {
            width: 8px;
            height: 8px;
            border-radius: 50%;
            background: #6b93d6;
            animation: loading-pulse 1.5s ease-in-out infinite;
        }

        .loading-dot:nth-child(1) { animation-delay: -0.3s; }
        .loading-dot:nth-child(2) { animation-delay: -0.15s; }
        .loading-dot:nth-child(3) { animation-delay: 0s; }

        @keyframes loading-pulse {
            0%, 80%, 100% { opacity: 0.3; transform: scale(0.8); }
            40% { opacity: 1; transform: scale(1.2); }
        }
    </style>
</head>
<body>
    <!-- Background layers -->
    <div class="bg-container"></div>
    <div class="bg-pattern"></div>
    <div class="hexagon-pattern"></div>

    <!-- Header Navigation -->
    <header class="header-nav">
        <div class="nav-container">
            <a href="#" class="logo">Blue Archive Events</a>
            <nav class="nav-menu">
                <a href="#" class="nav-item">Home</a>
                <a href="#" class="nav-item active">Events</a>
                <a href="#" class="nav-item">News</a>
                <a href="#" class="nav-item">Characters</a>
                <a href="#" class="nav-item">Community</a>
            </nav>
        </div>
    </header>

    <!-- Main Content -->
    <main class="main-container">
        <!-- Title Section -->
        <div class="title-section">
            <h1 class="main-title">Special Event</h1>
            <h2 class="subtitle">Bangkok Gathering</h2>
            <p class="tagline">Our Story Together, Blue Archive</p>
        </div>

        <!-- Event Card -->
        <div class="event-card">
            <div class="countdown-wrapper">
                <h3 class="countdown-title">Event Countdown</h3>
                
                <div id="countdown" class="countdown-grid">
                    <div class="time-card">
                        <span id="days" class="time-number">00</span>
                        <div class="time-label">Days</div>
                    </div>
                    <div class="time-card">
                        <span id="hours" class="time-number">00</span>
                        <div class="time-label">Hours</div>
                    </div>
                    <div class="time-card">
                        <span id="minutes" class="time-number">00</span>
                        <div class="time-label">Minutes</div>
                    </div>
                    <div class="time-card">
                        <span id="seconds" class="time-number">00</span>
                        <div class="time-label">Seconds</div>
                    </div>
                </div>
            </div>

            <!-- Event Information -->
            <div class="event-info">
                <div class="info-card">
                    <span class="info-icon">📅</span>
                    <div class="info-title">Date</div>
                    <div class="info-text">November 8, 2025</div>
                </div>
                <div class="info-card">
                    <span class="info-icon">🕐</span>
                    <div class="info-title">Time</div>
                    <div class="info-text">11:00 AM (ICT)</div>
                </div>
                <div class="info-card">
                    <span class="info-icon">📍</span>
                    <div class="info-title">Location</div>
                    <div class="info-text">Bang Sue, Bangkok</div>
                </div>
            </div>

            <!-- Navigation Button -->
            <div style="text-align: center;">
                <button class="nav-button" onclick="openGPS()">
                    <span>🎯</span>
                    Navigate to Event Location
                </button>
            </div>

            <!-- Loading Indicator -->
            <div class="loading-indicator">
                <div class="loading-dot"></div>
                <div class="loading-dot"></div>
                <div class="loading-dot"></div>
            </div>

            <!-- Footer -->
            <footer class="footer">
                <div class="footer-tagline">"A story kept within the heart"</div>
                <div class="coordinates">Coordinates: 13°48'18"N, 100°32'30"E</div>
            </footer>
        </div>
    </main>

    <script>
        // Target date and time (November 8, 2025, 11:00 AM ICT)
        const targetDate = new Date('2025-11-08T11:00:00+07:00');
        let lastSecond = -1;

        // GPS navigation function
        function openGPS() {
            const latitude = 13.805; // 13°48'18"N
            const longitude = 100.541667; // 100°32'30"E
            
            // Button click animation
            const button = event.target.closest('.nav-button');
            button.style.transform = 'scale(0.95) translateY(-1px)';
            setTimeout(() => {
                button.style.transform = 'translateY(-3px) scale(1.05)';
            }, 150);
            
            const googleMapsUrl = `https://www.google.com/maps/search/?api=1&query=${latitude},${longitude}`;
            const isMobile = /Android|webOS|iPhone|iPad|iPod|BlackBerry|IEMobile|Opera Mini/i.test(navigator.userAgent);
            
            if (isMobile) {
                const mapsUrl = `maps:${latitude},${longitude}`;
                window.open(mapsUrl);
                setTimeout(() => {
                    window.open(googleMapsUrl, '_blank');
                }, 1000);
            } else {
                window.open(googleMapsUrl, '_blank');
            }
        }

        // Countdown update function
        function updateCountdown() {
            const now = new Date().getTime();
            const distance = targetDate - now;

            if (distance > 0) {
                const days = Math.floor(distance / (1000 * 60 * 60 * 24));
                const hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
                const minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
                const seconds = Math.floor((distance % (1000 * 60)) / 1000);

                // Update display with animation
                updateTimeDisplay('days', days);
                updateTimeDisplay('hours', hours);
                updateTimeDisplay('minutes', minutes);
                updateTimeDisplay('seconds', seconds);

                // Special animation for seconds
                if (seconds !== lastSecond) {
                    animateTimeChange('seconds');
                    lastSecond = seconds;
                }
            } else {
                // Event has started
                document.getElementById('countdown').innerHTML = `
                    <div class="celebration" style="grid-column: 1/-1;">
                        <div class="celebration-text">🎉 Event Started! 🎉</div>
                        <div class="celebration-subtitle">Welcome to Blue Archive Bangkok Gathering!</div>
                    </div>
                `;
            }
        }

        // Update time display with formatting
        function updateTimeDisplay(elementId, value) {
            const element = document.getElementById(elementId);
            const formattedValue = value.toString().padStart(2, '0');
            element.textContent = formattedValue;
        }

        // Animate time change
        function animateTimeChange(elementId) {
            const element = document.getElementById(elementId);
            element.style.transform = 'scale(1.15)';
            element.style.color = '#4fc3f7';
            setTimeout(() => {
                element.style.transform = 'scale(1)';
                element.style.color = 'white';
            }, 200);
        }

        // Smooth page load animation
        window.addEventListener('load', function() {
            document.body.style.opacity = '0';
            document.body.style.transition = 'opacity 0.8s ease';
            setTimeout(() => {
                document.body.style.opacity = '1';
            }, 100);
        });

        // Add hover effects to time cards
        document.querySelectorAll('.time-card').forEach(card => {
            card.addEventListener('mouseenter', function() {
                this.style.transform = 'translateY(-8px) scale(1.02)';
            });
            
            card.addEventListener('mouseleave', function() {
                this.style.transform = 'translateY(0) scale(1)';
            });
        });

        // Initialize countdown
        updateCountdown();
        setInterval(updateCountdown, 1000);

        // Console logs for debugging
        console.log('🎯 Blue Archive Official Event System');
        console.log('📅 Current Time:', new Date());
        console.log('🎯 Target Time:', targetDate);
        console.log('🌐 User Agent:', navigator.userAgent);
        console.log('💫 Our Story Together, Blue Archive');
    </script>
</body>
</html>
