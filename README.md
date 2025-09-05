
<html lang="th">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Blue Archive Official - Bangkok Special Event</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Noto+Sans:wght@300;400;500;600;700;800&family=Inter:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
    <link rel="icon" type="image/x-icon" href="data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 100 100'><text y='.9em' font-size='90'>🎯</text></svg>">
    <style>
        /* Blue Archive Splash Screen */
        .splash-screen {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: #000;
            z-index: 9999;
            display: flex;
            justify-content: center;
            align-items: center;
            opacity: 1;
            transition: opacity 1s ease-out;
        }

        .splash-screen.fade-out {
            opacity: 0;
            pointer-events: none;
        }

        .splash-bg {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, #000428 0%, #004e92 100%);
            animation: splash-bg-pulse 3s ease-in-out infinite;
        }

        @keyframes splash-bg-pulse {
            0%, 100% { opacity: 0.8; }
            50% { opacity: 1; }
        }

        .splash-content {
            position: relative;
            z-index: 2;
            text-align: center;
            animation: splash-content-enter 2s cubic-bezier(0.175, 0.885, 0.32, 1.275);
        }

        @keyframes splash-content-enter {
            0% {
                opacity: 0;
                transform: scale(0.5) translateY(50px);
                filter: blur(10px);
            }
            60% {
                opacity: 0.8;
                transform: scale(1.1) translateY(-10px);
                filter: blur(2px);
            }
            100% {
                opacity: 1;
                transform: scale(1) translateY(0);
                filter: blur(0);
            }
        }

        .splash-logo {
            width: 300px;
            height: auto;
            max-width: 80vw;
            margin-bottom: 30px;
            filter: drop-shadow(0 10px 30px rgba(59, 130, 246, 0.5));
            animation: splash-logo-glow 2s ease-in-out infinite;
        }

        @keyframes splash-logo-glow {
            0%, 100% {
                filter: drop-shadow(0 10px 30px rgba(59, 130, 246, 0.5));
                transform: scale(1);
            }
            50% {
                filter: drop-shadow(0 15px 40px rgba(59, 130, 246, 0.8));
                transform: scale(1.02);
            }
        }

        .splash-title {
            font-size: 2.5rem;
            font-weight: 900;
            background: linear-gradient(135deg, #60a5fa 0%, #06b6d4 50%, #10b981 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            margin-bottom: 20px;
            text-shadow: 0 0 30px rgba(96, 165, 250, 0.5);
            animation: splash-title-shimmer 3s ease-in-out infinite;
        }

        @keyframes splash-title-shimmer {
            0%, 100% { opacity: 0.9; }
            50% { opacity: 1; }
        }

        .splash-subtitle {
            font-size: 1.2rem;
            color: rgba(255, 255, 255, 0.8);
            font-weight: 500;
            margin-bottom: 40px;
            animation: splash-subtitle-fade 2s ease-in-out infinite;
        }

        @keyframes splash-subtitle-fade {
            0%, 100% { opacity: 0.6; }
            50% { opacity: 1; }
        }

        .splash-loading {
            display: flex;
            justify-content: center;
            gap: 15px;
            margin-top: 30px;
        }

        .splash-dot {
            width: 15px;
            height: 15px;
            border-radius: 50%;
            background: linear-gradient(135deg, #60a5fa, #06b6d4);
            animation: splash-loading 2s ease-in-out infinite;
            box-shadow: 0 5px 15px rgba(96, 165, 250, 0.4);
        }

        .splash-dot:nth-child(1) { animation-delay: -0.4s; }
        .splash-dot:nth-child(2) { animation-delay: -0.2s; }
        .splash-dot:nth-child(3) { animation-delay: 0s; }

        @keyframes splash-loading {
            0%, 80%, 100% {
                opacity: 0.3;
                transform: scale(0.8);
                box-shadow: 0 5px 15px rgba(96, 165, 250, 0.2);
            }
            40% {
                opacity: 1;
                transform: scale(1.3);
                box-shadow: 0 10px 25px rgba(96, 165, 250, 0.6);
            }
        }

        .splash-progress {
            position: absolute;
            bottom: 100px;
            left: 50%;
            transform: translateX(-50%);
            width: 300px;
            max-width: 80vw;
        }

        .splash-progress-bar {
            width: 100%;
            height: 4px;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 2px;
            overflow: hidden;
            margin-bottom: 15px;
        }

        .splash-progress-fill {
            height: 100%;
            background: linear-gradient(90deg, #60a5fa, #06b6d4, #10b981);
            border-radius: 2px;
            width: 0%;
            animation: splash-progress 3s ease-out forwards;
            box-shadow: 0 0 10px rgba(96, 165, 250, 0.6);
        }

        @keyframes splash-progress {
            0% { width: 0%; }
            20% { width: 15%; }
            40% { width: 40%; }
            70% { width: 75%; }
            90% { width: 95%; }
            100% { width: 100%; }
        }

        .splash-progress-text {
            text-align: center;
            font-size: 0.9rem;
            color: rgba(255, 255, 255, 0.6);
            font-weight: 500;
        }

        /* Blue Archive particles effect */
        .splash-particles {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            overflow: hidden;
        }

        .particle {
            position: absolute;
            width: 4px;
            height: 4px;
            background: rgba(96, 165, 250, 0.6);
            border-radius: 50%;
            animation: particle-float 8s linear infinite;
        }

        @keyframes particle-float {
            0% {
                opacity: 0;
                transform: translateY(100vh) scale(0);
            }
            10% {
                opacity: 1;
                transform: translateY(90vh) scale(1);
            }
            90% {
                opacity: 1;
                transform: translateY(10vh) scale(1);
            }
            100% {
                opacity: 0;
                transform: translateY(0) scale(0);
            }
        }

        /* Main content blur effect */
        .main-content.blurred {
            filter: blur(20px);
            transition: filter 0.8s ease;
        }

        .nexon-header.blurred {
            filter: blur(10px);
            transition: filter 0.8s ease;
        }

        /* Responsive splash screen */
        @media (max-width: 768px) {
            .splash-logo {
                width: 250px;
            }
            
            .splash-title {
                font-size: 2rem;
            }
            
            .splash-subtitle {
                font-size: 1rem;
            }
            
            .splash-progress {
                bottom: 80px;
                width: 250px;
            }
        }

        @media (max-width: 480px) {
            .splash-logo {
                width: 200px;
            }
            
            .splash-title {
                font-size: 1.6rem;
            }
            
            .splash-progress {
                bottom: 60px;
                width: 200px;
            }
        }
            --primary-blue: #1e3a8a;
            --secondary-blue: #3b82f6;
            --light-blue: #60a5fa;
            --accent-cyan: #06b6d4;
            --bg-dark: #0f172a;
            --bg-medium: #1e293b;
            --text-primary: #ffffff;
            --text-secondary: #cbd5e1;
            --nexon-orange: #ff6b35;
            --success-green: #10b981;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Inter', 'Noto Sans', -apple-system, BlinkMacSystemFont, sans-serif;
            background: var(--bg-dark);
            color: var(--text-primary);
            overflow-x: hidden;
            line-height: 1.6;
        }

        /* Official Nexon Background */
        .nexon-bg {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, 
                #0f172a 0%, 
                #1e293b 25%, 
                #334155 50%, 
                #475569 75%, 
                #64748b 100%);
            z-index: -10;
        }

        .nexon-bg::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background-image: 
                radial-gradient(circle at 25% 25%, rgba(59, 130, 246, 0.1) 0%, transparent 50%),
                radial-gradient(circle at 75% 75%, rgba(6, 182, 212, 0.08) 0%, transparent 50%),
                linear-gradient(45deg, transparent 49%, rgba(255, 255, 255, 0.02) 50%, transparent 51%);
            background-size: 200px 200px, 300px 300px, 50px 50px;
            animation: drift 30s linear infinite;
        }

        @keyframes drift {
            0% { background-position: 0% 0%, 0% 0%, 0% 0%; }
            100% { background-position: 100% 100%, -100% 100%, 50px 50px; }
        }

        /* Official Nexon Header */
        .nexon-header {
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            background: rgba(15, 23, 42, 0.95);
            backdrop-filter: blur(24px);
            border-bottom: 1px solid rgba(59, 130, 246, 0.2);
            padding: 0;
            z-index: 1000;
            box-shadow: 0 4px 24px rgba(0, 0, 0, 0.1);
        }

        .header-container {
            max-width: 1400px;
            margin: 0 auto;
            display: flex;
            align-items: center;
            justify-content: space-between;
            padding: 16px 24px;
        }

        .nexon-logo {
            display: flex;
            align-items: center;
            gap: 16px;
            text-decoration: none;
        }

        .nexon-logo-text {
            font-size: 1.8rem;
            font-weight: 800;
            background: linear-gradient(135deg, var(--secondary-blue) 0%, var(--accent-cyan) 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            letter-spacing: -0.025em;
        }

        .nexon-subtitle {
            font-size: 0.85rem;
            color: var(--text-secondary);
            font-weight: 500;
            margin-top: -4px;
        }

        .header-nav {
            display: flex;
            gap: 32px;
            align-items: center;
        }

        .nav-link {
            color: var(--text-secondary);
            text-decoration: none;
            font-weight: 500;
            font-size: 0.95rem;
            padding: 8px 16px;
            border-radius: 8px;
            transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
            position: relative;
        }

        .nav-link:hover {
            color: var(--text-primary);
            background: rgba(59, 130, 246, 0.1);
        }

        .nav-link.active {
            color: var(--secondary-blue);
            background: rgba(59, 130, 246, 0.15);
        }

        .nav-link.active::after {
            content: '';
            position: absolute;
            bottom: -20px;
            left: 50%;
            transform: translateX(-50%);
            width: 24px;
            height: 3px;
            background: var(--secondary-blue);
            border-radius: 2px;
        }

        /* Main Content */
        .main-content {
            min-height: 100vh;
            padding: 120px 24px 80px;
            display: flex;
            flex-direction: column;
            align-items: center;
            position: relative;
        }

        /* Official Event Banner */
        .official-banner {
            text-align: center;
            margin-bottom: 64px;
            position: relative;
        }

        .official-badge {
            display: inline-block;
            background: linear-gradient(135deg, var(--nexon-orange) 0%, #ff8f65 100%);
            color: white;
            padding: 8px 20px;
            border-radius: 20px;
            font-size: 0.85rem;
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 0.5px;
            margin-bottom: 24px;
            box-shadow: 0 4px 12px rgba(255, 107, 53, 0.3);
        }

        .event-title {
            font-size: 4.5rem;
            font-weight: 900;
            background: linear-gradient(135deg, 
                var(--secondary-blue) 0%, 
                var(--light-blue) 30%, 
                var(--accent-cyan) 70%, 
                #38bdf8 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            margin-bottom: 16px;
            letter-spacing: -0.02em;
            line-height: 0.95;
            text-shadow: 0 0 40px rgba(59, 130, 246, 0.3);
        }

        .event-subtitle {
            font-size: 1.5rem;
            color: var(--text-secondary);
            font-weight: 400;
            margin-bottom: 12px;
        }

        .official-tagline {
            font-size: 1.1rem;
            color: var(--light-blue);
            font-weight: 500;
            font-style: italic;
            opacity: 0.9;
        }

        /* Professional Event Card */
        .event-container {
            background: linear-gradient(135deg, 
                rgba(255, 255, 255, 0.08) 0%, 
                rgba(255, 255, 255, 0.03) 100%);
            backdrop-filter: blur(32px);
            border-radius: 32px;
            border: 1px solid rgba(59, 130, 246, 0.2);
            box-shadow: 
                0 32px 64px rgba(0, 0, 0, 0.25),
                inset 0 1px 0 rgba(255, 255, 255, 0.1),
                0 0 0 1px rgba(59, 130, 246, 0.05);
            max-width: 1000px;
            width: 100%;
            padding: 64px;
            position: relative;
            overflow: hidden;
        }

        .event-container::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 4px;
            background: linear-gradient(90deg, 
                var(--secondary-blue) 0%, 
                var(--light-blue) 25%, 
                var(--accent-cyan) 50%, 
                var(--success-green) 75%, 
                var(--nexon-orange) 100%);
            background-size: 400% 100%;
            animation: official-gradient 6s linear infinite;
        }

        @keyframes official-gradient {
            0% { background-position: 0% 50%; }
            100% { background-position: 400% 50%; }
        }

        /* Countdown Section */
        .countdown-section {
            text-align: center;
            margin-bottom: 48px;
        }

        .countdown-header {
            margin-bottom: 40px;
        }

        .countdown-title {
            font-size: 2.2rem;
            font-weight: 700;
            color: var(--text-primary);
            margin-bottom: 12px;
            position: relative;
            display: inline-block;
        }

        .countdown-title::after {
            content: '';
            position: absolute;
            bottom: -8px;
            left: 50%;
            transform: translateX(-50%);
            width: 80px;
            height: 3px;
            background: linear-gradient(90deg, var(--secondary-blue), var(--accent-cyan));
            border-radius: 2px;
        }

        .countdown-subtitle {
            font-size: 1.1rem;
            color: var(--text-secondary);
            font-weight: 500;
        }

        /* Professional Timer Grid */
        .timer-grid {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 24px;
            margin: 48px 0;
            max-width: 800px;
            margin-left: auto;
            margin-right: auto;
        }

        .timer-card {
            background: linear-gradient(135deg, 
                rgba(59, 130, 246, 0.1) 0%, 
                rgba(6, 182, 212, 0.08) 100%);
            border: 2px solid rgba(59, 130, 246, 0.2);
            border-radius: 24px;
            padding: 32px 24px;
            text-align: center;
            position: relative;
            transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            overflow: hidden;
        }

        .timer-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, 
                transparent, 
                rgba(59, 130, 246, 0.1), 
                transparent);
            transition: left 0.8s ease;
        }

        .timer-card:hover {
            transform: translateY(-12px) scale(1.05);
            box-shadow: 0 24px 48px rgba(59, 130, 246, 0.25);
            border-color: rgba(59, 130, 246, 0.4);
        }

        .timer-card:hover::before {
            left: 100%;
        }

        .timer-number {
            font-size: 4rem;
            font-weight: 900;
            color: var(--text-primary);
            display: block;
            line-height: 1;
            margin-bottom: 16px;
            text-shadow: 0 4px 16px rgba(59, 130, 246, 0.3);
            font-family: 'Inter', monospace;
        }

        .timer-label {
            font-size: 1rem;
            color: var(--light-blue);
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        /* Event Details Grid */
        .details-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 32px;
            margin: 48px 0;
        }

        .detail-card {
            background: linear-gradient(135deg, 
                rgba(16, 185, 129, 0.1) 0%, 
                rgba(6, 182, 212, 0.08) 100%);
            border: 1px solid rgba(16, 185, 129, 0.2);
            border-radius: 20px;
            padding: 32px;
            text-align: center;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .detail-card:hover {
            transform: translateY(-8px);
            box-shadow: 0 16px 32px rgba(16, 185, 129, 0.15);
            border-color: rgba(16, 185, 129, 0.3);
        }

        .detail-icon {
            font-size: 3rem;
            margin-bottom: 20px;
            display: block;
            filter: drop-shadow(0 4px 8px rgba(16, 185, 129, 0.2));
        }

        .detail-title {
            font-size: 1.3rem;
            font-weight: 700;
            color: var(--success-green);
            margin-bottom: 12px;
        }

        .detail-text {
            color: var(--text-secondary);
            font-size: 1.1rem;
            font-weight: 500;
        }

        /* Official Action Buttons */
        .action-buttons {
            display: flex;
            flex-direction: column;
            gap: 20px;
            align-items: center;
            margin-top: 48px;
        }

        .btn-primary {
            background: linear-gradient(135deg, var(--secondary-blue) 0%, var(--light-blue) 100%);
            color: white;
            border: none;
            padding: 20px 48px;
            font-size: 1.2rem;
            font-weight: 700;
            border-radius: 60px;
            cursor: pointer;
            transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            display: inline-flex;
            align-items: center;
            gap: 16px;
            text-decoration: none;
            box-shadow: 0 12px 32px rgba(59, 130, 246, 0.3);
            position: relative;
            overflow: hidden;
            min-width: 280px;
            justify-content: center;
        }

        .btn-secondary {
            background: linear-gradient(135deg, #1877f2 0%, #42a5f5 100%);
            box-shadow: 0 12px 32px rgba(24, 119, 242, 0.3);
        }

        .btn-primary::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, 
                transparent, 
                rgba(255, 255, 255, 0.2), 
                transparent);
            transition: left 0.6s ease;
        }

        .btn-primary:hover::before {
            left: 100%;
        }

        .btn-primary:hover {
            transform: translateY(-4px) scale(1.05);
            box-shadow: 0 16px 40px rgba(59, 130, 246, 0.4);
        }

        .btn-secondary:hover {
            box-shadow: 0 16px 40px rgba(24, 119, 242, 0.4);
        }

        .btn-primary:active {
            transform: translateY(-2px) scale(1.02);
        }

        .btn-icon {
            font-size: 1.3em;
            filter: drop-shadow(0 2px 4px rgba(0, 0, 0, 0.1));
        }

        /* Celebration Mode */
        .celebration-mode {
            text-align: center;
            padding: 80px 48px;
            background: linear-gradient(135deg, 
                rgba(16, 185, 129, 0.15) 0%, 
                rgba(255, 193, 7, 0.12) 50%,
                rgba(244, 63, 94, 0.1) 100%);
            border: 3px solid rgba(16, 185, 129, 0.3);
            border-radius: 32px;
            animation: celebration-pulse 2s ease-in-out infinite;
            position: relative;
            overflow: hidden;
        }

        @keyframes celebration-pulse {
            0%, 100% { transform: scale(1); box-shadow: 0 0 0 rgba(16, 185, 129, 0.4); }
            50% { transform: scale(1.02); box-shadow: 0 0 32px rgba(16, 185, 129, 0.4); }
        }

        .celebration-title {
            font-size: 4rem;
            font-weight: 900;
            background: linear-gradient(135deg, 
                var(--success-green) 0%, 
                #fbbf24 50%, 
                #f97316 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            margin-bottom: 24px;
            text-shadow: 0 0 32px rgba(16, 185, 129, 0.3);
        }

        .celebration-text {
            font-size: 1.6rem;
            color: var(--text-primary);
            font-weight: 600;
            opacity: 0.95;
        }

        /* Professional Footer */
        .official-footer {
            margin-top: 64px;
            padding: 48px 0 32px;
            border-top: 1px solid rgba(59, 130, 246, 0.15);
            text-align: center;
            background: linear-gradient(135deg, 
                rgba(15, 23, 42, 0.8) 0%, 
                rgba(30, 41, 59, 0.6) 100%);
            backdrop-filter: blur(16px);
            border-radius: 24px 24px 0 0;
        }

        .footer-content {
            max-width: 800px;
            margin: 0 auto;
            padding: 0 24px;
        }

        .official-tagline-footer {
            font-size: 1.4rem;
            color: var(--light-blue);
            font-weight: 600;
            margin-bottom: 16px;
            font-style: italic;
        }

        .nexon-copyright {
            font-size: 1rem;
            color: var(--text-secondary);
            margin-bottom: 20px;
            font-weight: 500;
        }

        .coordinates-info {
            font-size: 0.95rem;
            color: rgba(156, 163, 175, 0.8);
            font-family: 'Courier New', monospace;
            background: rgba(59, 130, 246, 0.05);
            padding: 12px 24px;
            border-radius: 12px;
            display: inline-block;
            border: 1px solid rgba(59, 130, 246, 0.1);
        }

        /* Professional Loading Animation */
        .loading-animation {
            display: flex;
            justify-content: center;
            gap: 12px;
            margin: 32px 0;
        }

        .loading-circle {
            width: 12px;
            height: 12px;
            border-radius: 50%;
            background: var(--secondary-blue);
            animation: professional-loading 2s ease-in-out infinite;
        }

        .loading-circle:nth-child(1) { animation-delay: -0.4s; }
        .loading-circle:nth-child(2) { animation-delay: -0.2s; }
        .loading-circle:nth-child(3) { animation-delay: 0s; }

        @keyframes professional-loading {
            0%, 80%, 100% { 
                opacity: 0.3; 
                transform: scale(0.8); 
            }
            40% { 
                opacity: 1; 
                transform: scale(1.2); 
            }
        }

        /* Responsive Design */
        @media (max-width: 1024px) {
            .event-container {
                padding: 48px 32px;
            }
            
            .timer-grid {
                grid-template-columns: repeat(2, 1fr);
                gap: 20px;
            }
        }

        @media (max-width: 768px) {
            .header-nav {
                display: none;
            }
            
            .event-title {
                font-size: 3rem;
            }
            
            .event-container {
                margin: 0 16px;
                padding: 40px 24px;
            }
            
            .timer-number {
                font-size: 3rem;
            }
            
            .details-grid {
                grid-template-columns: 1fr;
                gap: 24px;
            }
            
            .action-buttons {
                gap: 16px;
            }
            
            .btn-primary {
                min-width: 240px;
                padding: 18px 36px;
                font-size: 1.1rem;
            }
        }

        @media (max-width: 480px) {
            .main-content {
                padding: 100px 16px 60px;
            }
            
            .event-title {
                font-size: 2.2rem;
            }
            
            .timer-grid {
                grid-template-columns: 1fr 1fr;
                gap: 16px;
            }
            
            .timer-number {
                font-size: 2.5rem;
            }
            
            .timer-card {
                padding: 24px 16px;
            }
            
            .celebration-title {
                font-size: 2.8rem;
            }
        }

        /* Performance optimizations */
        * {
            -webkit-font-smoothing: antialiased;
            -moz-osx-font-smoothing: grayscale;
        }

        .timer-number {
            will-change: transform;
        }

        .btn-primary {
            will-change: transform, box-shadow;
        }
    </style>
</head>
<body>
    <!-- Blue Archive Splash Screen -->
    <div id="splashScreen" class="splash-screen">
        <div class="splash-bg"></div>
        
        <!-- Floating particles -->
        <div class="splash-particles" id="splashParticles"></div>
        
        <div class="splash-content">
            <img src="https://i.ibb.co/vx8zmzGG/1315080.png" alt="Blue Archive Logo" class="splash-logo" id="splashLogo">
            
            <h1 class="splash-title">Blue Archive</h1>
            <p class="splash-subtitle">Bangkok Official Event</p>
            
            <div class="splash-loading">
                <div class="splash-dot"></div>
                <div class="splash-dot"></div>
                <div class="splash-dot"></div>
            </div>
        </div>
        
        <div class="splash-progress">
            <div class="splash-progress-bar">
                <div class="splash-progress-fill" id="splashProgressFill"></div>
            </div>
            <div class="splash-progress-text" id="splashProgressText">Loading... 0%</div>
        </div>
    </div>

    <!-- Official Background -->
    <div class="nexon-bg"></div>

    <!-- Official Header -->
    <header class="nexon-header">
        <div class="header-container">
            <a href="#" class="nexon-logo">
                <div>
                    <div class="nexon-logo-text">Blue Archive</div>
                    <div class="nexon-subtitle">Official Event Portal</div>
                </div>
            </a>
            <nav class="header-nav">
                <a href="#" class="nav-link">Home</a>
                <a href="#" class="nav-link active">Events</a>
                <a href="#" class="nav-link">News</a>
                <a href="#" class="nav-link">Characters</a>
                <a href="#" class="nav-link">Community</a>
                <a href="#" class="nav-link">Download</a>
            </nav>
        </div>
    </header>

    <!-- Main Content -->
    <main class="main-content">
        <!-- Official Event Banner -->
        <section class="official-banner">
            <div class="official-badge">Official Nexon Event</div>
            <h1 class="event-title">Bangkok Special Event</h1>
            <p class="event-subtitle">Sensei Gathering 2025</p>
            <p class="official-tagline">"Our Story Together, Blue Archive"</p>
        </section>

        <!-- Professional Event Container -->
        <div class="event-container">
            <!-- Countdown Section -->
            <section class="countdown-section">
                <div class="countdown-header">
                    <h2 class="countdown-title">Event Countdown</h2>
                    <p class="countdown-subtitle">Time until the official gathering begins</p>
                </div>

                <div id="countdown" class="timer-grid">
                    <div class="timer-card">
                        <span id="days" class="timer-number">00</span>
                        <div class="timer-label">Days</div>
                    </div>
                    <div class="timer-card">
                        <span id="hours" class="timer-number">00</span>
                        <div class="timer-label">Hours</div>
                    </div>
                    <div class="timer-card">
                        <span id="minutes" class="timer-number">00</span>
                        <div class="timer-label">Minutes</div>
                    </div>
                    <div class="timer-card">
                        <span id="seconds" class="timer-number">00</span>
                        <div class="timer-label">Seconds</div>
                    </div>
                </div>
            </section>

            <!-- Event Details -->
            <section class="details-grid">
                <div class="detail-card">
                    <span class="detail-icon">📅</span>
                    <h3 class="detail-title">Event Date</h3>
                    <p class="detail-text">November 8, 2025</p>
                </div>
                <div class="detail-card">
                    <span class="detail-icon">🕐</span>
                    <h3 class="detail-title">Start Time</h3>
                    <p class="detail-text">11:00 AM (ICT+7)</p>
                </div>
                <div class="detail-card">
                    <span class="detail-icon">📍</span>
                    <h3 class="detail-title">Location</h3>
                    <p class="detail-text">Bang Sue, Bangkok</p>
                </div>
            </section>

            <!-- Official Action Buttons -->
            <div class="action-buttons">
                <button class="btn-primary" onclick="openGPS()">
                    <span class="btn-icon">🎯</span>
                    Navigate to Event Location
                </button>
                
                <a href="https://www.facebook.com/share/1HdVaDgkqo/" target="_blank" class="btn-primary btn-secondary">
                    <span class="btn-icon">📘</span>
                    View Official Announcement
                </a>
            </div>

            <!-- Professional Loading Animation -->
            <div class="loading-animation">
                <div class="loading-circle"></div>
                <div class="loading-circle"></div>
                <div class="loading-circle"></div>
            </div>
        </div>

        <!-- Official Footer -->
        <footer class="official-footer">
            <div class="footer-content">
                <div class="official-tagline-footer">"Our Story Together, Blue Archive"</div>
                <div class="nexon-copyright">
                    © 2025 NEXON Games Co., Ltd. & MX Studio. All Rights Reserved.<br>
                    Blue Archive Official Bangkok Event
                </div>
                <div class="coordinates-info">
                    Event Coordinates: 13°48'18"N, 100°32'30"E
                </div>
            </div>
        </footer>
    </main>

    <script>
        // Blue Archive Splash Screen System
        class BlueArchiveSplashScreen {
            constructor() {
                this.splashElement = document.getElementById('splashScreen');
                this.progressFill = document.getElementById('splashProgressFill');
                this.progressText = document.getElementById('splashProgressText');
                this.particlesContainer = document.getElementById('splashParticles');
                this.mainContent = document.querySelector('.main-content');
                this.header = document.querySelector('.nexon-header');
                
                this.loadingStages = [
                    { progress: 15, text: 'Initializing Blue Archive System...' },
                    { progress: 30, text: 'Loading Event Data...' },
                    { progress: 50, text: 'Connecting to Nexon Servers...' },
                    { progress: 70, text: 'Preparing Bangkok Event...' },
                    { progress: 85, text: 'Loading Character Data...' },
                    { progress: 95, text: 'Finalizing Setup...' },
                    { progress: 100, text: 'Welcome, Sensei!' }
                ];
                
                this.currentStage = 0;
                this.isComplete = false;
            }

            async initialize() {
                this.createParticles();
                this.blurBackground();
                await this.startLoadingSequence();
                await this.exitSplash();
            }

            createParticles() {
                const particleCount = 30;
                
                for (let i = 0; i < particleCount; i++) {
                    const particle = document.createElement('div');
                    particle.className = 'particle';
                    particle.style.left = Math.random() * 100 + '%';
                    particle.style.animationDelay = Math.random() * 8 + 's';
                    particle.style.animationDuration = (8 + Math.random() * 4) + 's';
                    
                    // Random particle colors from Blue Archive palette
                    const colors = [
                        'rgba(96, 165, 250, 0.6)',
                        'rgba(6, 182, 212, 0.5)',
                        'rgba(16, 185, 129, 0.4)',
                        'rgba(255, 183, 77, 0.3)'
                    ];
                    
                    particle.style.background = colors[Math.floor(Math.random() * colors.length)];
                    this.particlesContainer.appendChild(particle);
                }
            }

            blurBackground() {
                if (this.mainContent) this.mainContent.classList.add('blurred');
                if (this.header) this.header.classList.add('blurred');
            }

            removeBlurBackground() {
                if (this.mainContent) this.mainContent.classList.remove('blurred');
                if (this.header) this.header.classList.remove('blurred');
            }

            async startLoadingSequence() {
                return new Promise((resolve) => {
                    const loadingInterval = setInterval(() => {
                        if (this.currentStage < this.loadingStages.length) {
                            const stage = this.loadingStages[this.currentStage];
                            this.updateProgress(stage.progress, stage.text);
                            this.currentStage++;
                        } else {
                            clearInterval(loadingInterval);
                            setTimeout(resolve, 800); // Extra pause at 100%
                        }
                    }, 600); // 600ms per stage
                });
            }

            updateProgress(progress, text) {
                if (this.progressFill) {
                    this.progressFill.style.width = progress + '%';
                }
                
                if (this.progressText) {
                    this.progressText.textContent = text;
                }

                // Add special effects at certain milestones
                if (progress === 50) {
                    this.addLogoGlow();
                } else if (progress === 100) {
                    this.addCompletionEffect();
                }
            }

            addLogoGlow() {
                const logo = document.getElementById('splashLogo');
                if (logo) {
                    logo.style.filter = 'drop-shadow(0 15px 40px rgba(59, 130, 246, 0.8)) drop-shadow(0 0 60px rgba(6, 182, 212, 0.6))';
                    logo.style.transform = 'scale(1.05)';
                }
            }

            addCompletionEffect() {
                const splashContent = document.querySelector('.splash-content');
                if (splashContent) {
                    splashContent.style.animation = 'splash-content-complete 1s ease-out forwards';
                }
                
                // Add completion keyframe if not exists
                if (!document.querySelector('#completion-animation')) {
                    const style = document.createElement('style');
                    style.id = 'completion-animation';
                    style.textContent = `
                        @keyframes splash-content-complete {
                            0% { transform: scale(1) translateY(0); }
                            50% { transform: scale(1.1) translateY(-10px); }
                            100% { transform: scale(1.05) translateY(0); }
                        }
                    `;
                    document.head.appendChild(style);
                }
            }

            async exitSplash() {
                return new Promise((resolve) => {
                    // Add exit animation
                    this.splashElement.style.animation = 'splash-exit 1.5s cubic-bezier(0.4, 0, 0.2, 1) forwards';
                    
                    // Add exit keyframe if not exists
                    if (!document.querySelector('#exit-animation')) {
                        const style = document.createElement('style');
                        style.id = 'exit-animation';
                        style.textContent = `
                            @keyframes splash-exit {
                                0% { 
                                    opacity: 1; 
                                    transform: scale(1); 
                                    filter: blur(0px);
                                }
                                70% { 
                                    opacity: 0.3; 
                                    transform: scale(1.1); 
                                    filter: blur(5px);
                                }
                                100% { 
                                    opacity: 0; 
                                    transform: scale(1.2); 
                                    filter: blur(20px);
                                    pointer-events: none;
                                }
                            }
                        `;
                        document.head.appendChild(style);
                    }
                    
                    setTimeout(() => {
                        this.splashElement.classList.add('fade-out');
                        this.removeBlurBackground();
                        
                        setTimeout(() => {
                            this.splashElement.style.display = 'none';
                            resolve();
                        }, 1000);
                    }, 1500);
                });
            }
        }

        // Initialize Blue Archive Loading System
        async function initializeBluearchiveSystem() {
            const splash = new BlueArchiveSplashScreen();
            await splash.initialize();
            
            // After splash, initialize the main event system
            initializeOfficialEvent();
            monitorPerformance();
        }

        // Official Event Configuration
        const CONFIG = {
            TARGET_DATE: new Date('2025-11-08T11:00:00+07:00'),
            COORDINATES: {
                lat: 13.805,
                lng: 100.541667
            },
            ANIMATION_DURATION: 200
        };

        let previousSecond = -1;

        // Professional GPS Navigation
        function openGPS() {
            const button = event.target.closest('.btn-primary');
            
            // Professional button feedback
            button.style.transform = 'scale(0.96) translateY(-2px)';
            setTimeout(() => {
                button.style.transform = 'translateY(-4px) scale(1.05)';
            }, CONFIG.ANIMATION_DURATION);

            const { lat, lng } = CONFIG.COORDINATES;
            const googleMapsUrl = `https://www.google.com/maps/search/?api=1&query=${lat},${lng}`;
            const isMobile = /Android|webOS|iPhone|iPad|iPod|BlackBerry|IEMobile|Opera Mini/i.test(navigator.userAgent);
            
            if (isMobile) {
                const mapsUrl = `maps:${lat},${lng}`;
                window.open(mapsUrl);
                setTimeout(() => {
                    window.open(googleMapsUrl, '_blank');
                }, 1000);
            } else {
                window.open(googleMapsUrl, '_blank');
            }
        }

        // Professional Countdown System
        function updateCountdown() {
            const now = new Date().getTime();
            const distance = CONFIG.TARGET_DATE - now;

            if (distance > 0) {
                const timeUnits = {
                    days: Math.floor(distance / (1000 * 60 * 60 * 24)),
                    hours: Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60)),
                    minutes: Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60)),
                    seconds: Math.floor((distance % (1000 * 60)) / 1000)
                };

                // Update display with professional formatting
                Object.entries(timeUnits).forEach(([unit, value]) => {
                    updateTimeDisplay(unit, value);
                });

                // Professional second animation
                if (timeUnits.seconds !== previousSecond) {
                    animateSecondChange();
                    previousSecond = timeUnits.seconds;
                }
            } else {
                displayEventStart();
            }
        }

        // Professional Time Display Update
        function updateTimeDisplay(unit, value) {
            const element = document.getElementById(unit);
            if (element) {
                const formattedValue = value.toString().padStart(2, '0');
                element.textContent = formattedValue;
            }
        }

        // Professional Second Animation
        function animateSecondChange() {
            const secondsElement = document.getElementById('seconds');
            if (secondsElement) {
                secondsElement.style.transform = 'scale(1.1)';
                secondsElement.style.color = 'var(--accent-cyan)';
                
                setTimeout(() => {
                    secondsElement.style.transform = 'scale(1)';
                    secondsElement.style.color = 'var(--text-primary)';
                }, CONFIG.ANIMATION_DURATION);
            }
        }

        // Event Started Display
        function displayEventStart() {
            const countdownElement = document.getElementById('countdown');
            if (countdownElement) {
                countdownElement.innerHTML = `
                    <div class="celebration-mode" style="grid-column: 1/-1;">
                        <div class="celebration-title">🎉 Event Started! 🎉</div>
                        <div class="celebration-text">
                            Welcome to Blue Archive Bangkok Official Event!<br>
                            <small style="font-size: 1.2rem; opacity: 0.8; margin-top: 16px; display: block;">
                                Sensei, let's create our story together!
                            </small>
                        </div>
                    </div>
                `;
            }
        }

        // Professional Page Initialization
        function initializeOfficialEvent() {
            // Smooth page load
            document.body.style.opacity = '0';
            document.body.style.transition = 'opacity 0.8s cubic-bezier(0.4, 0, 0.2, 1)';
            
            setTimeout(() => {
                document.body.style.opacity = '1';
            }, 100);

            // Initialize countdown
            updateCountdown();
            setInterval(updateCountdown, 1000);

            // Professional timer card interactions
            initializeTimerCardEffects();
            
            // Log official event system
            logOfficialEventInfo();
        }

        // Timer Card Professional Effects
        function initializeTimerCardEffects() {
            document.querySelectorAll('.timer-card').forEach(card => {
                card.addEventListener('mouseenter', function() {
                    this.style.transform = 'translateY(-12px) scale(1.05)';
                });
                
                card.addEventListener('mouseleave', function() {
                    this.style.transform = 'translateY(0) scale(1)';
                });
            });
        }

        // Official Event System Logging
        function logOfficialEventInfo() {
            console.log('🎯 Blue Archive Official Event System Initialized');
            console.log('📅 Current Time:', new Date().toLocaleString('th-TH', { timeZone: 'Asia/Bangkok' }));
            console.log('🎯 Target Event Time:', CONFIG.TARGET_DATE.toLocaleString('th-TH', { timeZone: 'Asia/Bangkok' }));
            console.log('📍 Event Coordinates:', `${CONFIG.COORDINATES.lat}°N, ${CONFIG.COORDINATES.lng}°E`);
            console.log('🏢 Powered by NEXON Games Co., Ltd.');
            console.log('💫 "Our Story Together, Blue Archive"');
        }

        // Professional Performance Monitoring
        function monitorPerformance() {
            if (window.performance && window.performance.mark) {
                window.performance.mark('blue-archive-event-start');
                
                window.addEventListener('load', () => {
                    window.performance.mark('blue-archive-event-loaded');
                    
                    if (window.performance.measure) {
                        window.performance.measure(
                            'blue-archive-load-time',
                            'blue-archive-event-start',
                            'blue-archive-event-loaded'
                        );
                    }
                });
            }
        }

        // Official Event System Initialization
        document.addEventListener('DOMContentLoaded', () => {
            initializeBluearchiveSystem();
        });

        // Professional Error Handling
        window.addEventListener('error', (event) => {
            console.error('Blue Archive Official Event Error:', event.error);
        });

        // Professional Visibility Change Handling
        document.addEventListener('visibilitychange', () => {
            if (document.visibilityState === 'visible') {
                updateCountdown();
            }
        });

        // Professional Resize Handling
        let resizeTimeout;
        window.addEventListener('resize', () => {
            clearTimeout(resizeTimeout);
            resizeTimeout = setTimeout(() => {
                // Re-optimize layouts if needed
                const timerCards = document.querySelectorAll('.timer-card');
                timerCards.forEach(card => {
                    card.style.transform = 'translateY(0) scale(1)';
                });
            }, 250);
        });
    </script>
</body>
</html>
