<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Wsfrog - Cybersecurity & Java Developer</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Consolas', 'Courier New', monospace;
        }
        
        body {
            background: #0a0f1b;
            color: #00ff41;
            line-height: 1.6;
            padding: 20px;
            position: relative;
            overflow-x: hidden;
        }
        
        body::before {
            content: "";
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: 
                radial-gradient(circle at 15% 50%, rgba(0, 40, 83, 0.15) 0%, rgba(0, 0, 0, 0) 25%),
                radial-gradient(circle at 85% 30%, rgba(0, 40, 83, 0.1) 0%, rgba(0, 0, 0, 0) 25%);
            z-index: -1;
        }
        
        .container {
            max-width: 1100px;
            margin: 0 auto;
            padding: 20px;
            position: relative;
        }
        
        header {
            text-align: center;
            padding: 40px 0;
            border-bottom: 1px solid #1e2a4a;
            position: relative;
            overflow: hidden;
        }
        
        .hacker-text {
            font-size: 2.8rem;
            margin-bottom: 15px;
            text-shadow: 0 0 10px #00ff41;
            position: relative;
            display: inline-block;
        }
        
        .hacker-text::after {
            content: "|";
            position: absolute;
            right: -15px;
            animation: blink 1s infinite;
        }
        
        @keyframes blink {
            0%, 100% { opacity: 1; }
            50% { opacity: 0; }
        }
        
        .subtitle {
            color: #7df9ff;
            font-size: 1.2rem;
            margin-bottom: 30px;
        }
        
        .scan-line {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 3px;
            background: linear-gradient(to right, transparent, #00ff41, transparent);
            animation: scan 4s linear infinite;
        }
        
        @keyframes scan {
            0% { top: 0%; }
            100% { top: 100%; }
        }
        
        .section {
            background: rgba(10, 20, 40, 0.6);
            border: 1px solid #1e2a4a;
            border-radius: 8px;
            padding: 25px;
            margin-bottom: 30px;
            box-shadow: 0 0 15px rgba(0, 255, 65, 0.1);
            position: relative;
            overflow: hidden;
        }
        
        .section-title {
            font-size: 1.8rem;
            margin-bottom: 20px;
            color: #7df9ff;
            position: relative;
            display: inline-block;
        }
        
        .section-title::after {
            content: "";
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 100%;
            height: 2px;
            background: linear-gradient(to right, transparent, #00ff41, transparent);
        }
        
        .about-content {
            display: flex;
            gap: 30px;
            flex-wrap: wrap;
        }
        
        .about-text {
            flex: 1;
            min-width: 300px;
        }
        
        .about-text p {
            margin-bottom: 15px;
            padding-left: 20px;
            position: relative;
            font-size: 1.1rem;
        }
        
        .about-text p::before {
            content: ">";
            position: absolute;
            left: 0;
            color: #ff5555;
        }
        
        .terminal {
            flex: 1;
            min-width: 300px;
            background: rgba(0, 10, 20, 0.8);
            border: 1px solid #00ff41;
            border-radius: 5px;
            padding: 15px;
            font-family: monospace;
            position: relative;
        }
        
        .terminal-header {
            display: flex;
            align-items: center;
            margin-bottom: 15px;
        }
        
        .terminal-btn {
            width: 12px;
            height: 12px;
            border-radius: 50%;
            margin-right: 5px;
        }
        
        .btn-red { background: #ff5555; }
        .btn-yellow { background: #ffcc00; }
        .btn-green { background: #00ff41; }
        
        .terminal-content {
            line-height: 1.8;
        }
        
        .terminal-content div {
            animation: type 3s steps(40, end);
            overflow: hidden;
            white-space: nowrap;
        }
        
        .terminal-content div:nth-child(1) { animation-delay: 0s; }
        .terminal-content div:nth-child(2) { animation-delay: 1s; }
        .terminal-content div:nth-child(3) { animation-delay: 2s; }
        
        @keyframes type {
            from { width: 0; }
            to { width: 100%; }
        }
        
        .skills {
            display: flex;
            flex-wrap: wrap;
            gap: 20px;
            margin-top: 20px;
        }
        
        .skill-card {
            background: rgba(0, 20, 40, 0.7);
            border: 1px solid #1e2a4a;
            border-radius: 8px;
            padding: 15px;
            text-align: center;
            min-width: 120px;
            transition: all 0.3s ease;
        }
        
        .skill-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 5px 15px rgba(0, 255, 65, 0.2);
            border-color: #00ff41;
        }
        
        .skill-card i {
            font-size: 2.5rem;
            margin-bottom: 10px;
        }
        
        .stats {
            display: flex;
            flex-wrap: wrap;
            gap: 20px;
            justify-content: center;
        }
        
        .stat-card {
            background: rgba(0, 20, 40, 0.7);
            border: 1px solid #1e2a4a;
            border-radius: 8px;
            padding: 20px;
            text-align: center;
            min-width: 250px;
            flex: 1;
        }
        
        .stat-card h3 {
            margin-bottom: 15px;
            color: #7df9ff;
        }
        
        .social-links {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 15px;
            margin-top: 20px;
        }
        
        .social-btn {
            display: flex;
            align-items: center;
            gap: 8px;
            padding: 10px 20px;
            border-radius: 30px;
            text-decoration: none;
            font-weight: bold;
            transition: all 0.3s ease;
            border: 1px solid;
        }
        
        .social-btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(0, 255, 65, 0.3);
        }
        
        .social-btn i {
            font-size: 1.2rem;
        }
        
        .instagram { background: linear-gradient(45deg, #405DE6, #5851DB, #833AB4, #C13584, #E1306C, #FD1D1D); color: white; border-color: #C13584; }
        .twitch { background: linear-gradient(45deg, #6441a5, #2a0845); color: white; border-color: #6441a5; }
        .gmail { background: linear-gradient(45deg, #D44638, #EA4335); color: white; border-color: #D44638; }
        .linkedin { background: linear-gradient(45deg, #0077B5, #00A0DC); color: white; border-color: #0077B5; }
        
        .hacker-gif {
            position: absolute;
            right: 30px;
            top: 200px;
            width: 150px;
            border: 2px solid #00ff41;
            border-radius: 5px;
            box-shadow: 0 0 15px rgba(0, 255, 65, 0.3);
        }
        
        .cyber-badge {
            position: absolute;
            top: 20px;
            right: 20px;
            background: linear-gradient(45deg, #ff5555, #ffcc00);
            color: #0a0f1b;
            padding: 5px 10px;
            border-radius: 5px;
            font-weight: bold;
            font-size: 0.8rem;
            transform: rotate(15deg);
            box-shadow: 0 0 10px rgba(255, 85, 85, 0.5);
        }
        
        .pulse {
            animation: pulse 2s infinite;
        }
        
        @keyframes pulse {
            0% { box-shadow: 0 0 0 0 rgba(0, 255, 65, 0.7); }
            70% { box-shadow: 0 0 0 10px rgba(0, 255, 65, 0); }
            100% { box-shadow: 0 0 0 0 rgba(0, 255, 65, 0); }
        }
        
        footer {
            text-align: center;
            margin-top: 40px;
            padding-top: 20px;
            border-top: 1px solid #1e2a4a;
            color: #7df9ff;
            font-size: 0.9rem;
        }
        
        @media (max-width: 768px) {
            .hacker-text {
                font-size: 2rem;
            }
            
            .hacker-gif {
                position: static;
                margin: 20px auto;
                display: block;
            }
            
            .cyber-badge {
                top: 10px;
                right: 10px;
            }
        }
    </style>
</head>
<body>
    <div class="scan-line"></div>
    <div class="container">
        <header>
            <div class="cyber-badge">SECURITY FOCUSED</div>
            <h1 class="hacker-text">Wsfrog</h1>
            <p class="subtitle">Java Developer | Cybersecurity Enthusiast | Systems Analysis Student</p>
        </header>
        
        <div class="section">
            <h2 class="section-title">About Me</h2>
            <div class="about-content">
                <div class="about-text">
                    <p>Java Developer with a passion for secure coding practices</p>
                    <p>4th semester student of Systems Analysis and Development</p>
                    <p>Cybersecurity enthusiast focusing on application security</p>
                    <p>Currently learning ethical hacking and secure system design</p>
                </div>
                <div class="terminal">
                    <div class="terminal-header">
                        <div class="terminal-btn btn-red"></div>
                        <div class="terminal-btn btn-yellow"></div>
                        <div class="terminal-btn btn-green"></div>
                    </div>
                    <div class="terminal-content">
                        <div>> security-scan --profile wsfrog</div>
                        <div>> Scanning credentials... [OK]</div>
                        <div>> Secure coding practices... [VERIFIED]</div>
                    </div>
                </div>
            </div>
        </div>
        
        <div class="section">
            <h2 class="section-title">Security & Development Skills</h2>
            <div class="skills">
                <div class="skill-card pulse">
                    <i class="fab fa-java"></i>
                    <div>Java</div>
                </div>
                <div class="skill-card">
                    <i class="fas fa-database"></i>
                    <div>MySQL</div>
                </div>
                <div class="skill-card">
                    <i class="fab fa-html5"></i>
                    <div>HTML5</div>
                </div>
                <div class="skill-card">
                    <i class="fab fa-css3-alt"></i>
                    <div>CSS3</div>
                </div>
                <div class="skill-card">
                    <i class="fab fa-git-alt"></i>
                    <div>Git</div>
                </div>
                <div class="skill-card">
                    <i class="fab fa-github"></i>
                    <div>GitHub</div>
                </div>
                <div class="skill-card">
                    <i class="fas fa-shield-alt"></i>
                    <div>App Security</div>
                </div>
                <div class="skill-card">
                    <i class="fas fa-lock"></i>
                    <div>Encryption</div>
                </div>
            </div>
        </div>
        
        <div class="section">
            <h2 class="section-title">GitHub Activity</h2>
            <div class="stats">
                <div class="stat-card">
                    <h3>Commit Analysis</h3>
                    <p>Consistent development activity</p>
                    <p>Secure coding patterns detected</p>
                </div>
                <div class="stat-card">
                    <h3>Language Distribution</h3>
                    <p>Java: 65%</p>
                    <p>SQL: 20%</p>
                    <p>Web: 15%</p>
                </div>
            </div>
        </div>
        
        <div class="section">
            <h2 class="section-title">Connect With Me</h2>
            <div class="social-links">
                <a href="#" class="social-btn instagram">
                    <i class="fab fa-instagram"></i>
                    <span>Instagram</span>
                </a>
                <a href="#" class="social-btn twitch">
                    <i class="fab fa-twitch"></i>
                    <span>Twitch</span>
                </a>
                <a href="#" class="social-btn gmail">
                    <i class="fas fa-envelope"></i>
                    <span>Gmail</span>
                </a>
                <a href="#" class="social-btn linkedin">
                    <i class="fab fa-linkedin"></i>
                    <span>LinkedIn</span>
                </a>
            </div>
        </div>
        
        <img src="https://media.giphy.com/media/jTq2i1lVj4G8JpGZ6a/giphy.gif" alt="Hacker animation" class="hacker-gif">
    </div>
    
    <footer>
        <p>🔒 Security is a process, not a product</p>
        <p>© 2023 Wsfrog | Secure by Design</p>
    </footer>
</body>
</html>
