<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>GitHub Profile README</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'JetBrains Mono', 'Fira Code', 'Consolas', monospace;
            background: #000000;
            color: #ffffff;
            overflow-x: hidden;
            min-height: 100vh;
        }

        /* Grid pattern background */
        body::before {
            content: '';
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-image: 
                radial-gradient(circle at 25% 25%, #111111 2px, transparent 2px),
                radial-gradient(circle at 75% 75%, #111111 1px, transparent 1px);
            background-size: 50px 50px;
            opacity: 0.3;
            z-index: 0;
            animation: gridMove 20s linear infinite;
        }

        @keyframes gridMove {
            0% { transform: translate(0, 0); }
            100% { transform: translate(50px, 50px); }
        }

        /* Floating glow effects */
        .glow-orb {
            position: fixed;
            border-radius: 50%;
            filter: blur(40px);
            opacity: 0.1;
            z-index: 0;
            animation: float 8s ease-in-out infinite;
        }

        .glow-1 {
            top: 10%;
            left: 10%;
            width: 200px;
            height: 200px;
            background: radial-gradient(circle, #333333, transparent);
            animation-delay: 0s;
        }

        .glow-2 {
            top: 60%;
            right: 15%;
            width: 150px;
            height: 150px;
            background: radial-gradient(circle, #222222, transparent);
            animation-delay: 3s;
        }

        .glow-3 {
            bottom: 20%;
            left: 20%;
            width: 180px;
            height: 180px;
            background: radial-gradient(circle, #2a2a2a, transparent);
            animation-delay: 6s;
        }

        @keyframes float {
            0%, 100% { transform: translate(0, 0) scale(1); }
            33% { transform: translate(30px, -30px) scale(1.1); }
            66% { transform: translate(-20px, 20px) scale(0.9); }
        }

        .container {
            max-width: 1000px;
            margin: 0 auto;
            padding: 60px 20px;
            position: relative;
            z-index: 1;
        }

        /* Header Section */
        .header {
            text-align: center;
            margin-bottom: 80px;
        }

        .glitch-text {
            font-size: 4rem;
            font-weight: 900;
            color: #ffffff;
            text-transform: uppercase;
            letter-spacing: 8px;
            position: relative;
            display: inline-block;
            animation: glitch 2s ease-in-out infinite;
        }

        @keyframes glitch {
            0%, 100% { transform: translate(0); }
            20% { transform: translate(-2px, 2px); }
            40% { transform: translate(-2px, -2px); }
            60% { transform: translate(2px, 2px); }
            80% { transform: translate(2px, -2px); }
        }

        .typing-text {
            font-size: 1.4rem;
            color: #888888;
            margin-top: 20px;
            font-weight: 600;
            border-right: 2px solid #ffffff;
            white-space: nowrap;
            overflow: hidden;
            animation: typing 3s steps(30) 1s both, blink-cursor 1s infinite;
        }

        @keyframes typing {
            from { width: 0; }
            to { width: 100%; }
        }

        @keyframes blink-cursor {
            0%, 50% { border-right-color: #ffffff; }
            51%, 100% { border-right-color: transparent; }
        }

        /* Main Content Section */
        .main-content {
            display: flex;
            gap: 60px;
            align-items: center;
            margin-bottom: 100px;
            position: relative;
        }

        .content-left {
            flex: 1;
        }

        .section-title {
            font-size: 2.5rem;
            font-weight: 800;
            color: #ffffff;
            margin-bottom: 30px;
            position: relative;
        }

        .section-title::before {
            content: '>';
            color: #666666;
            margin-right: 15px;
            font-family: monospace;
        }

        .bio-text {
            font-size: 1.2rem;
            line-height: 1.8;
            color: #cccccc;
            margin-bottom: 40px;
            font-weight: 500;
        }

        .tech-stack {
            display: flex;
            flex-wrap: wrap;
            gap: 15px;
            margin-bottom: 40px;
        }

        .tech-badge {
            background: transparent;
            border: 1px solid #333333;
            padding: 10px 20px;
            font-size: 0.9rem;
            font-weight: 700;
            color: #ffffff;
            position: relative;
            transition: all 0.3s ease;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .tech-badge:hover {
            border-color: #555555;
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(255, 255, 255, 0.1);
        }

        .tech-badge::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 0;
            height: 100%;
            background: linear-gradient(45deg, transparent, rgba(255, 255, 255, 0.1), transparent);
            transition: width 0.3s ease;
        }

        .tech-badge:hover::before {
            width: 100%;
        }

        .photo-container {
            flex: 0 0 350px;
            height: 400px;
            position: relative;
            border: 2px solid #222222;
            background: #111111;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.1rem;
            color: #666666;
            font-weight: 600;
            overflow: hidden;
        }

        .photo-container::before {
            content: '';
            position: absolute;
            top: -2px;
            left: -2px;
            right: -2px;
            bottom: -2px;
            background: linear-gradient(45deg, #333333, #111111, #333333, #111111);
            background-size: 400% 400%;
            animation: gradientShift 8s ease infinite;
            z-index: -1;
        }

        @keyframes gradientShift {
            0%, 100% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
        }

        .photo-container::after {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.1), transparent);
            animation: scan 3s ease-in-out infinite;
        }

        @keyframes scan {
            0% { left: -100%; }
            100% { left: 100%; }
        }

        /* Stats Section */
        .stats-section {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 0;
            margin-bottom: 80px;
        }

        .stat-card {
            background: transparent;
            border: 1px solid #222222;
            padding: 40px 30px;
            text-align: center;
            position: relative;
            transition: all 0.3s ease;
        }

        .stat-card:hover {
            border-color: #444444;
            background: rgba(255, 255, 255, 0.02);
        }

        .stat-number {
            font-size: 3rem;
            font-weight: 900;
            color: #ffffff;
            display: block;
            margin-bottom: 10px;
            font-family: monospace;
        }

        .stat-label {
            font-size: 1rem;
            color: #888888;
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 2px;
        }

        /* Activity Section */
        .activity-section {
            margin-bottom: 80px;
        }

        .activity-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 0;
        }

        .activity-card {
            background: transparent;
            border: 1px solid #1a1a1a;
            padding: 30px;
            position: relative;
            transition: all 0.3s ease;
        }

        .activity-card:hover {
            border-color: #333333;
            background: rgba(255, 255, 255, 0.01);
        }

        .activity-title {
            font-size: 1.3rem;
            font-weight: 800;
            color: #ffffff;
            margin-bottom: 15px;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .activity-text {
            color: #aaaaaa;
            line-height: 1.6;
            font-weight: 500;
        }

        /* Terminal-like footer */
        .terminal-footer {
            background: transparent;
            border: 1px solid #333333;
            padding: 30px;
            font-family: 'JetBrains Mono', monospace;
            position: relative;
        }

        .terminal-header {
            display: flex;
            align-items: center;
            gap: 10px;
            margin-bottom: 20px;
            padding-bottom: 15px;
            border-bottom: 1px solid #222222;
        }

        .terminal-dot {
            width: 12px;
            height: 12px;
            border-radius: 50%;
            background: #444444;
        }

        .terminal-content {
            color: #00ff00;
            font-size: 1rem;
            line-height: 1.6;
        }

        .terminal-prompt {
            color: #666666;
        }

        /* Responsive */
        @media (max-width: 768px) {
            .main-content {
                flex-direction: column;
                text-align: center;
                gap: 40px;
            }
            
            .photo-container {
                flex: none;
                width: 100%;
                max-width: 350px;
                margin: 0 auto;
            }
            
            .glitch-text {
                font-size: 2.5rem;
                letter-spacing: 4px;
            }
            
            .stats-section {
                grid-template-columns: repeat(2, 1fr);
            }
        }
    </style>
</head>
<body>
    <div class="glow-orb glow-1"></div>
    <div class="glow-orb glow-2"></div>
    <div class="glow-orb glow-3"></div>

    <div class="container">
        <!-- Header -->
        <div class="header">
            <h1 class="glitch-text">SENIN ADIN</h1>
            <p class="typing-text">Full Stack Developer & Problem Solver</p>
        </div>

        <!-- Main Content -->
        <div class="main-content">
            <div class="content-left">
                <h2 class="section-title">Ben Kimim?</h2>
                <p class="bio-text">
                    Kod yazmayı seven, teknolojiye tutkulu bir geliştiriciyim. 
                    Karmaşık problemleri basit çözümlerle çözmeyi ve sürekli 
                    yeni teknolojiler öğrenmeyi seviyorum. Clean code ve 
                    user experience odaklı projeler geliştiriyorum.
                </p>
                <div class="tech-stack">
                    <span class="tech-badge">JavaScript</span>
                    <span class="tech-badge">Python</span>
                    <span class="tech-badge">React</span>
                    <span class="tech-badge">Node.js</span>
                    <span class="tech-badge">TypeScript</span>
                    <span class="tech-badge">Docker</span>
                    <span class="tech-badge">AWS</span>
                    <span class="tech-badge">MongoDB</span>
                </div>
            </div>
            <div class="photo-container">
                🚗 Fotoğrafını buraya koy (araba ile)
            </div>
        </div>

        <!-- Stats -->
        <div class="stats-section">
            <div class="stat-card">
                <span class="stat-number">50+</span>
                <span class="stat-label">Projects</span>
            </div>
            <div class="stat-card">
                <span class="stat-number">3</span>
                <span class="stat-label">Years Exp</span>
            </div>
            <div class="stat-card">
                <span class="stat-number">1000+</span>
                <span class="stat-label">Commits</span>
            </div>
            <div class="stat-card">
                <span class="stat-number">24/7</span>
                <span class="stat-label">Learning</span>
            </div>
        </div>

        <!-- Activity -->
        <div class="activity-section">
            <h2 class="section-title">Ne Yapıyorum?</h2>
            <div class="activity-grid">
                <div class="activity-card">
                    <h3 class="activity-title">
                        🚀 Projeler
                    </h3>
                    <p class="activity-text">
                        Açık kaynak projelere katkıda bulunuyor, kişisel projeler 
                        geliştiriyorum. Modern teknolojilerle scalable uygulamalar yapıyorum.
                    </p>
                </div>
                <div class="activity-card">
                    <h3 class="activity-title">
                        📚 Öğrenme
                    </h3>
                    <p class="activity-text">
                        Sürekli yeni teknolojiler öğreniyor, online kurslar alıyorum. 
                        Tech blog'ları takip ediyor, konferansları izliyorum.
                    </p>
                </div>
                <div class="activity-card">
                    <h3 class="activity-title">
                        💡 İnovasyon
                    </h3>
                    <p class="activity-text">
                        Yeni fikirler üretiyor, prototype'lar geliştiriyorum. 
                        AI ve machine learning alanında deneyimler yapıyorum.
                    </p>
                </div>
                <div class="activity-card">
                    <h3 class="activity-title">
                        🤝 Topluluk
                    </h3>
                    <p class="activity-text">
                        Developer toplulukları ile etkileşim kuruyorum. 
                        Stack Overflow'da sorulara cevap veriyor, mentor oluyorum.
                    </p>
                </div>
            </div>
        </div>

        <!-- Terminal Footer -->
        <div class="terminal-footer">
            <div class="terminal-header">
                <div class="terminal-dot"></div>
                <div class="terminal-dot"></div>
                <div class="terminal-dot"></div>
                <span style="color: #666; margin-left: 10px;">terminal</span>
            </div>
            <div class="terminal-content">
                <span class="terminal-prompt">visitor@github:~$</span> cat bio.txt<br>
                <span class="terminal-prompt">></span> Kod ile dünyayı değiştirmeye çalışan bir developer<br>
                <span class="terminal-prompt">></span> Her gün yeni bir şey öğrenmeye açık<br>
                <span class="terminal-prompt">></span> Kahve ile kodlama, problem çözme tutkusu<br>
                <span class="terminal-prompt">visitor@github:~$</span> <span style="animation: blink-cursor 1s infinite;">█</span>
            </div>
        </div>
    </div>
</body>
</html>
