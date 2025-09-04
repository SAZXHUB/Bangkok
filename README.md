<!DOCTYPE html>
<html lang="th">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>นับถอยหลัง Blue Archive Event บางซื่อ</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            color: white;
        }

        .container {
            text-align: center;
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            padding: 40px;
            box-shadow: 0 8px 32px rgba(31, 38, 135, 0.37);
            border: 1px solid rgba(255, 255, 255, 0.18);
            max-width: 600px;
            width: 90%;
        }

        .title {
            font-size: 2.5rem;
            margin-bottom: 10px;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
            background: linear-gradient(45deg, #ff6b6b, #4ecdc4, #45b7d1);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            animation: shimmer 3s ease-in-out infinite alternate;
        }

        @keyframes shimmer {
            0% {
                background-position: 0% 50%;
            }
            100% {
                background-position: 100% 50%;
            }
        }

        .subtitle {
            font-size: 1.2rem;
            margin-bottom: 30px;
            opacity: 0.9;
        }

        .countdown {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(100px, 1fr));
            gap: 20px;
            margin: 30px 0;
        }

        .time-unit {
            background: rgba(255, 255, 255, 0.2);
            border-radius: 15px;
            padding: 20px;
            backdrop-filter: blur(5px);
            border: 1px solid rgba(255, 255, 255, 0.3);
            transition: transform 0.3s ease;
        }

        .time-unit:hover {
            transform: translateY(-5px);
        }

        .time-number {
            font-size: 3rem;
            font-weight: bold;
            display: block;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
        }

        .time-label {
            font-size: 1rem;
            opacity: 0.8;
            margin-top: 10px;
        }

        .gps-button {
            background: linear-gradient(45deg, #ff6b6b, #ee5a5a);
            color: white;
            border: none;
            padding: 15px 30px;
            font-size: 1.1rem;
            border-radius: 50px;
            cursor: pointer;
            transition: all 0.3s ease;
            margin-top: 30px;
            text-decoration: none;
            display: inline-block;
            box-shadow: 0 4px 15px rgba(255, 107, 107, 0.4);
        }

        .gps-button:hover {
            transform: translateY(-2px);
            box-shadow: 0 6px 20px rgba(255, 107, 107, 0.6);
            background: linear-gradient(45deg, #ee5a5a, #ff6b6b);
        }

        .gps-button:active {
            transform: translateY(0);
        }

        .event-info {
            margin-top: 20px;
            padding: 15px;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 10px;
            font-size: 0.9rem;
        }

        .finished {
            font-size: 2rem;
            color: #4ecdc4;
            animation: pulse 1.5s ease-in-out infinite;
        }

        @keyframes pulse {
            0%, 100% {
                opacity: 1;
            }
            50% {
                opacity: 0.7;
            }
        }

        @media (max-width: 480px) {
            .title {
                font-size: 2rem;
            }
            
            .time-number {
                font-size: 2rem;
            }
            
            .container {
                padding: 20px;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <h1 class="title">นับถอยหลัง Blue Archive Event</h1>
        <p class="subtitle">บางซื่อ</p>
        
        <div id="countdown" class="countdown">
            <div class="time-unit">
                <span id="days" class="time-number">0</span>
                <div class="time-label">วัน</div>
            </div>
            <div class="time-unit">
                <span id="hours" class="time-number">0</span>
                <div class="time-label">ชั่วโมง</div>
            </div>
            <div class="time-unit">
                <span id="minutes" class="time-number">0</span>
                <div class="time-label">นาที</div>
            </div>
            <div class="time-unit">
                <span id="seconds" class="time-number">0</span>
                <div class="time-label">วินาที</div>
            </div>
        </div>

        <button class="gps-button" onclick="openGPS()">
            📍 เปิด GPS ไปยังสถานที่จัดงาน
        </button>

        <div class="event-info">
            <strong>วันที่:</strong> 8 พฤศจิกายน 2025<br>
            <strong>เวลา:</strong> 11:00 น.<br>
            <strong>สถานที่:</strong> บางซื่อ (13°48'18"N, 100°32'30"E)
        </div>
    </div>

    <script>
        // กำหนดวันที่และเวลาเป้าหมาย
        const targetDate = new Date('2025-11-08T11:00:00+07:00'); // เวลาไทย (UTC+7)

        // ฟังก์ชันเปิด GPS
        function openGPS() {
            const latitude = 13.805; // 13°48'18"N
            const longitude = 100.541667; // 100°32'30"E
            
            // ลองเปิด Google Maps ก่อน
            const googleMapsUrl = `https://www.google.com/maps/search/?api=1&query=${latitude},${longitude}`;
            
            // ตรวจสอบว่าเป็นมือถือหรือไม่
            const isMobile = /Android|webOS|iPhone|iPad|iPod|BlackBerry|IEMobile|Opera Mini/i.test(navigator.userAgent);
            
            if (isMobile) {
                // สำหรับมือถือ ลองเปิดแอพ maps ก่อน
                const mapsUrl = `maps:${latitude},${longitude}`;
                window.open(mapsUrl);
                
                // ถ้าไม่ได้ ให้เปิด Google Maps ใน browser
                setTimeout(() => {
                    window.open(googleMapsUrl, '_blank');
                }, 1000);
            } else {
                // สำหรับเดสก์ท็อป เปิด Google Maps
                window.open(googleMapsUrl, '_blank');
            }
        }

        // ฟังก์ชันอัปเดตเวลานับถอยหลัง
        function updateCountdown() {
            const now = new Date().getTime();
            const distance = targetDate - now;

            if (distance > 0) {
                const days = Math.floor(distance / (1000 * 60 * 60 * 24));
                const hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
                const minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
                const seconds = Math.floor((distance % (1000 * 60)) / 1000);

                document.getElementById('days').textContent = days.toString().padStart(2, '0');
                document.getElementById('hours').textContent = hours.toString().padStart(2, '0');
                document.getElementById('minutes').textContent = minutes.toString().padStart(2, '0');
                document.getElementById('seconds').textContent = seconds.toString().padStart(2, '0');
            } else {
                // เมื่อหมดเวลา
                document.getElementById('countdown').innerHTML = '<div class="finished">🎉 Event เริ่มแล้ว! 🎉</div>';
            }
        }

        // เริ่มนับถอยหลัง
        updateCountdown();
        setInterval(updateCountdown, 1000);

        // แสดงเวลาปัจจุบันในคอนโซล (สำหรับการตรวจสอบ)
        console.log('เวลาปัจจุบัน:', new Date());
        console.log('เวลาเป้าหมาย:', targetDate);
    </script>
</body>
</html>
