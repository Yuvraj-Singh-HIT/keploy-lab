<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Keploy - 3D Animated README</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: #fff;
            overflow-x: hidden;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }

        /* Animated Background */
        .animated-bg {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
        }

        .floating-shapes {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            overflow: hidden;
        }

        .shape {
            position: absolute;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 50%;
            animation: float 20s infinite;
        }

        .shape:nth-child(1) { width: 80px; height: 80px; left: 10%; animation-delay: 0s; }
        .shape:nth-child(2) { width: 120px; height: 120px; left: 30%; animation-delay: 2s; }
        .shape:nth-child(3) { width: 100px; height: 100px; left: 50%; animation-delay: 4s; }
        .shape:nth-child(4) { width: 90px; height: 90px; left: 70%; animation-delay: 6s; }
        .shape:nth-child(5) { width: 110px; height: 110px; left: 85%; animation-delay: 8s; }

        @keyframes float {
            0%, 100% { transform: translateY(0) rotate(0deg); opacity: 0.3; }
            50% { transform: translateY(-100vh) rotate(360deg); opacity: 0.6; }
        }

        /* 3D Logo Container */
        .logo-container {
            text-align: center;
            padding: 60px 20px;
            perspective: 1000px;
        }

        .logo-3d {
            display: inline-block;
            animation: rotate3d 10s infinite ease-in-out;
            transform-style: preserve-3d;
            transition: transform 0.3s;
        }

        .logo-3d:hover {
            animation-play-state: paused;
            transform: scale(1.1) rotateY(15deg);
        }

        .logo-3d img {
            width: 400px;
            max-width: 90vw;
            filter: drop-shadow(0 20px 40px rgba(0, 0, 0, 0.3));
        }

        @keyframes rotate3d {
            0%, 100% { transform: rotateY(0deg) rotateX(0deg); }
            25% { transform: rotateY(5deg) rotateX(-5deg); }
            50% { transform: rotateY(0deg) rotateX(5deg); }
            75% { transform: rotateY(-5deg) rotateX(0deg); }
        }

        /* Title Section */
        .title-section {
            text-align: center;
            margin: 40px 0;
        }

        .main-title {
            font-size: 2.5em;
            font-weight: bold;
            background: linear-gradient(45deg, #ff6b6b, #ffd93d, #6bcf7f, #4ecdc4);
            background-size: 300% 300%;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            animation: gradientShift 3s ease infinite;
            text-shadow: 0 4px 6px rgba(0, 0, 0, 0.2);
        }

        .subtitle {
            font-size: 1.5em;
            margin: 20px 0;
            opacity: 0;
            animation: fadeInUp 1s forwards 0.5s;
        }

        @keyframes gradientShift {
            0%, 100% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
        }

        @keyframes fadeInUp {
            from { opacity: 0; transform: translateY(30px); }
            to { opacity: 1; transform: translateY(0); }
        }

        /* Badge Section */
        .badges {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 15px;
            margin: 40px 0;
        }

        .badge {
            display: inline-block;
            padding: 10px 20px;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 25px;
            backdrop-filter: blur(10px);
            border: 2px solid rgba(255, 255, 255, 0.2);
            transition: all 0.3s;
            cursor: pointer;
            animation: popIn 0.5s forwards;
            opacity: 0;
        }

        .badge:nth-child(1) { animation-delay: 0.1s; }
        .badge:nth-child(2) { animation-delay: 0.2s; }
        .badge:nth-child(3) { animation-delay: 0.3s; }
        .badge:nth-child(4) { animation-delay: 0.4s; }
        .badge:nth-child(5) { animation-delay: 0.5s; }
        .badge:nth-child(6) { animation-delay: 0.6s; }

        .badge:hover {
            transform: translateY(-5px) scale(1.1);
            background: rgba(255, 255, 255, 0.2);
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
        }

        @keyframes popIn {
            from { opacity: 0; transform: scale(0.5); }
            to { opacity: 1; transform: scale(1); }
        }

        /* Card Section */
        .card {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(20px);
            border-radius: 20px;
            padding: 40px;
            margin: 30px 0;
            border: 2px solid rgba(255, 255, 255, 0.2);
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.3);
            transition: all 0.3s;
            animation: slideIn 0.8s forwards;
            opacity: 0;
        }

        .card:hover {
            transform: translateY(-10px);
            box-shadow: 0 30px 80px rgba(0, 0, 0, 0.4);
        }

        @keyframes slideIn {
            from { opacity: 0; transform: translateX(-50px); }
            to { opacity: 1; transform: translateX(0); }
        }

        .card h2 {
            font-size: 2em;
            margin-bottom: 20px;
            background: linear-gradient(45deg, #ffd93d, #ff6b6b);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .card h3 {
            font-size: 1.5em;
            margin: 20px 0 10px 0;
            color: #ffd93d;
        }

        .card p, .card li {
            line-height: 1.8;
            font-size: 1.1em;
            color: rgba(255, 255, 255, 0.9);
        }

        .card ul {
            list-style: none;
            padding-left: 0;
        }

        .card li:before {
            content: "✓ ";
            color: #6bcf7f;
            font-weight: bold;
            margin-right: 10px;
        }

        /* Feature Grid */
        .feature-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 30px;
            margin: 40px 0;
        }

        .feature-card {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(20px);
            border-radius: 15px;
            padding: 30px;
            text-align: center;
            border: 2px solid rgba(255, 255, 255, 0.2);
            transition: all 0.3s;
            animation: scaleIn 0.6s forwards;
            opacity: 0;
            transform-style: preserve-3d;
        }

        .feature-card:nth-child(1) { animation-delay: 0.1s; }
        .feature-card:nth-child(2) { animation-delay: 0.2s; }
        .feature-card:nth-child(3) { animation-delay: 0.3s; }
        .feature-card:nth-child(4) { animation-delay: 0.4s; }

        .feature-card:hover {
            transform: translateZ(20px) rotateX(5deg) rotateY(5deg);
            box-shadow: 0 20px 50px rgba(0, 0, 0, 0.4);
        }

        @keyframes scaleIn {
            from { opacity: 0; transform: scale(0.8); }
            to { opacity: 1; transform: scale(1); }
        }

        .feature-icon {
            font-size: 3em;
            margin-bottom: 15px;
            animation: bounce 2s infinite;
        }

        @keyframes bounce {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-10px); }
        }

        /* Code Block */
        .code-block {
            background: rgba(0, 0, 0, 0.3);
            border-radius: 10px;
            padding: 20px;
            margin: 20px 0;
            font-family: 'Courier New', monospace;
            position: relative;
            overflow: hidden;
        }

        .code-block:before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.1), transparent);
            animation: shimmer 3s infinite;
        }

        @keyframes shimmer {
            0% { left: -100%; }
            100% { left: 100%; }
        }

        .code-block code {
            color: #6bcf7f;
            font-size: 1.1em;
        }

        /* CTA Button */
        .cta-button {
            display: inline-block;
            padding: 15px 40px;
            margin: 20px 10px;
            background: linear-gradient(45deg, #ff6b6b, #ffd93d);
            border: none;
            border-radius: 50px;
            color: #000;
            font-size: 1.2em;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s;
            text-decoration: none;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
            animation: pulse 2s infinite;
        }

        .cta-button:hover {
            transform: translateY(-5px) scale(1.05);
            box-shadow: 0 15px 40px rgba(0, 0, 0, 0.4);
        }

        @keyframes pulse {
            0%, 100% { box-shadow: 0 10px 30px rgba(255, 107, 107, 0.5); }
            50% { box-shadow: 0 10px 50px rgba(255, 217, 61, 0.7); }
        }

        /* Language Tags */
        .language-tags {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 15px;
            margin: 30px 0;
        }

        .language-tag {
            padding: 10px 20px;
            background: rgba(255, 255, 255, 0.15);
            border-radius: 20px;
            border: 2px solid rgba(255, 255, 255, 0.3);
            transition: all 0.3s;
            cursor: pointer;
        }

        .language-tag:hover {
            background: rgba(255, 255, 255, 0.25);
            transform: translateY(-3px);
        }

        /* Footer */
        .footer {
            text-align: center;
            padding: 40px 20px;
            margin-top: 60px;
            border-top: 2px solid rgba(255, 255, 255, 0.2);
        }

        .footer h3 {
            font-size: 2em;
            margin-bottom: 20px;
            background: linear-gradient(45deg, #ff6b6b, #ffd93d);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        /* Responsive */
        @media (max-width: 768px) {
            .main-title { font-size: 1.8em; }
            .subtitle { font-size: 1.2em; }
            .card { padding: 20px; }
            .logo-3d img { width: 300px; }
        }

        .scroll-indicator {
            position: fixed;
            bottom: 30px;
            left: 50%;
            transform: translateX(-50%);
            animation: bounce 2s infinite;
            font-size: 2em;
            opacity: 0.7;
        }
    </style>
</head>
<body>
    <!-- Animated Background -->
    <div class="animated-bg"></div>
    <div class="floating-shapes">
        <div class="shape"></div>
        <div class="shape"></div>
        <div class="shape"></div>
        <div class="shape"></div>
        <div class="shape"></div>
    </div>

    <div class="container">
        <!-- Logo Section -->
        <div class="logo-container">
            <div class="logo-3d">
                <img src="https://raw.githubusercontent.com/keploy/keploy/main/pkg/assets/keploy-logo-dark.svg" alt="Keploy Logo" onerror="this.src='data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iNDAwIiBoZWlnaHQ9IjEwMCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj48dGV4dCB4PSI1MCUiIHk9IjUwJSIgZm9udC1zaXplPSI0OCIgZmlsbD0iI0ZGOTUwMCIgdGV4dC1hbmNob3I9Im1pZGRsZSIgZG9taW5hbnQtYmFzZWxpbmU9Im1pZGRsZSIgZm9udC13ZWlnaHQ9ImJvbGQiPmtlcGxveTwvdGV4dD48L3N2Zz4='">
            </div>
        </div>

        <!-- Title Section -->
        <div class="title-section">
            <h1 class="main-title">⚡️ API Tests Faster Than Unit Tests, From User Traffic ⚡️</h1>
            <p class="subtitle">🌟 The Must-Have Tool for Developers in the AI-Gen Era for 90% Test Coverage 🌟</p>
        </div>

        <!-- Badges -->
        <div class="badges">
            <div class="badge">⭐ GitHub Stars</div>
            <div class="badge">📦 Latest Release</div>
            <div class="badge">📜 Apache 2.0 License</div>
            <div class="badge">✅ Coverage Status</div>
            <div class="badge">💬 Join Slack</div>
            <div class="badge">🌐 CNCF Landscape</div>
        </div>

        <!-- What is Keploy -->
        <div class="card">
            <h2>🚀 What is Keploy?</h2>
            <p>
                <strong>Keploy</strong> is a <strong>developer-centric API and integration testing tool</strong> that auto-generates tests and data-mocks <strong>faster than unit tests</strong>.
            </p>
            <p style="margin-top: 20px;">
                It records API calls, database queries, and streaming events — then replays them as tests. Under the hood, Keploy uses <strong>eBPF</strong> to capture traffic at the network layer, making it <strong>completely code-less</strong> and <strong>language-agnostic</strong>.
            </p>

            <div class="code-block">
                <code># Record real API traffic as tests<br>
keploy record -c "python main.py"<br><br>
# Replay as deterministic tests<br>
keploy test -c "python main.py" --delay 10</code>
            </div>

            <p style="text-align: center; margin-top: 20px;">
                <strong>🐰 Fun Fact:</strong> Keploy uses itself for testing!
            </p>
        </div>

        <!-- Key Features -->
        <div class="card">
            <h2>✨ Key Highlights</h2>
            <div class="feature-grid">
                <div class="feature-card">
                    <div class="feature-icon">🎯</div>
                    <h3>Zero Code Changes</h3>
                    <p>Just run your app with <code>keploy record</code>. Powered by eBPF — No SDKs needed!</p>
                </div>

                <div class="feature-card">
                    <div class="feature-icon">📹</div>
                    <h3>Record & Replay</h3>
                    <p>Complex, distributed API flows as mocks and stubs. It's like a time machine for tests!</p>
                </div>

                <div class="feature-card">
                    <div class="feature-icon">🐇</div>
                    <h3>Infra-Virtualization</h3>
                    <p>Records databases, message queues, external APIs, and streaming events. No infra needed!</p>
                </div>

                <div class="feature-card">
                    <div class="feature-icon">🤖</div>
                    <h3>AI-Powered Tests</h3>
                    <p>Expands coverage by finding boundary values, missing fields, and edge cases automatically!</p>
                </div>
            </div>
        </div>

        <!-- Quick Start -->
        <div class="card">
            <h2>🎬 Quick Start</h2>
            
            <h3>1️⃣ Install Keploy Agent</h3>
            <div class="code-block">
                <code>curl --silent -O -L https://keploy.io/install.sh && source install.sh</code>
            </div>

            <h3>2️⃣ Record Test Cases</h3>
            <div class="code-block">
                <code>keploy record -c "CMD_TO_RUN_APP"</code>
            </div>
            <p>Examples:</p>
            <div class="code-block">
                <code>keploy record -c "python main.py"<br>
keploy record -c "node app.js"<br>
keploy record -c "./app"<br>
keploy record -c "java -jar app.jar"</code>
            </div>

            <h3>3️⃣ Run Tests</h3>
            <div class="code-block">
                <code>keploy test -c "CMD_TO_RUN_APP" --delay 10</code>
            </div>
        </div>

        <!-- Language Support -->
        <div class="card">
            <h2>🌍 Works With Any Language & Framework</h2>
            <p style="text-align: center; margin-bottom: 20px;">
                Because Keploy intercepts at the <strong>network layer (eBPF)</strong>, it works with <strong>any language, framework, or runtime</strong> — no SDK required!
            </p>
            <div class="language-tags">
                <div class="language-tag">🐍 Python</div>
                <div class="language-tag">📜 JavaScript</div>
                <div class="language-tag">🔷 TypeScript</div>
                <div class="language-tag">🔵 Go</div>
                <div class="language-tag">☕ Java</div>
                <div class="language-tag">💎 Ruby</div>
                <div class="language-tag">🐘 PHP</div>
                <div class="language-tag">🦀 Rust</div>
                <div class="language-tag">🔷 .NET</div>
                <div class="language-tag">⚡ FastAPI</div>
                <div class="language-tag">🌿 Django</div>
                <div class="language-tag">🍃 Flask</div>
                <div class="language-tag">🚂 Express</div>
                <div class="language-tag">🍂 Spring</div>
                <div class="language-tag">🍸 Gin</div>
            </div>
        </div>

        <!-- Other Capabilities -->
        <div class="card">
            <h2>🛠️ Other Capabilities</h2>
            <ul>
                <li>🌐 <strong>CI/CD Integration:</strong> Run tests in Jenkins, GitHub Actions, GitLab CI, or Kubernetes</li>
                <li>🎭 <strong>Multi-Purpose Mocks:</strong> Use Keploy-generated mocks as server tests</li>
                <li>📊 <strong>Unified Reporting:</strong> API, integration, unit, and e2e coverage with CI/PR insights</li>
                <li>🖥️ <strong>Developer Console:</strong> View, manage, and debug recorded tests and mocks</li>
                <li>⏱️ <strong>Time Freezing:</strong> Deterministic test replay by freezing system time</li>
                <li>📚 <strong>Mock Registry:</strong> Centralized registry to manage, reuse, and version mocks</li>
            </ul>
        </div>

        <!-- CTA Section -->
        <div style="text-align: center; margin: 60px 0;">
            <h2 style="font-size: 2.5em; margin-bottom: 30px;">🚀 Ready to Get Started?</h2>
            <a href="https://keploy.io/docs/getting-started" class="cta-button">📘 Read Documentation</a>
            <a href="https://join.slack.com/t/keploy/shared_invite/zt-2dno1yetd-Ec3el~tTwHYIHgGI0jPe7A" class="cta-button">💬 Join Community</a>
            <a href="mailto:sales@keploy.io" class="cta-button">📧 Book Live Demo</a>
        </div>

        <!-- Footer -->
        <div class="footer">
            <h3>Made with ❤️ by the Keploy Community</h3>
            <p style="margin-top: 20px; font-size: 1.2em;">
                ⭐ <strong>Star us on GitHub</strong> — Help us reach 20k stars!
            </p>
            <div class="badges" style="margin-top: 30px;">
                <div class="badge">📜 Apache 2.0 License</div>
                <div class="badge">🏆 CNCF Landscape</div>
                <div class="badge">🤝 Open Source</div>
            </div>
        </div>
    </div>

    <div class="scroll-indicator">⬇️</div>

    <script>
        // Parallax effect for floating shapes
        document.addEventListener('mousemove', (e) => {
            const shapes = document.querySelectorAll('.shape');
            const x = e.clientX / window.innerWidth;
            const y = e.clientY / window.innerHeight;
            
            shapes.forEach((shape, index) => {
                const speed = (index + 1) * 10;
                shape.style.transform = `translate(${x * speed}px, ${y * speed}px)`;
            });
        });

        // Hide scroll indicator after scroll
        window.addEventListener('scroll', () => {
            const indicator = document.querySelector('.scroll-indicator');
            if (window.scrollY > 100) {
                indicator.style.opacity = '0';
            } else {
                indicator.style.opacity = '0.7';
            }
        });

        // Intersection Observer for animations
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = '1';
                    entry.target.style.transform = 'translateY(0)';
                }
            });
        }, { threshold: 0.1 });

        document.querySelectorAll('.card, .feature-card').forEach(el => {
            observer.observe(el);
        });
    </script>
</body>
</html>
