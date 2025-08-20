<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Salil Gupta - Interactive Developer Portfolio</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background: linear-gradient(-45deg, #ee7752, #e73c7e, #23a6d5, #23d5ab);
            background-size: 400% 400%;
            animation: gradientShift 15s ease infinite;
            font-family: 'Courier New', monospace;
            overflow-x: hidden;
            color: white;
        }

        @keyframes gradientShift {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        /* Floating Particles Background */
        .particles {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: -1;
        }

        .particle {
            position: absolute;
            width: 4px;
            height: 4px;
            background: rgba(255, 255, 255, 0.8);
            border-radius: 50%;
            animation: float 6s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px) rotate(0deg); opacity: 1; }
            50% { transform: translateY(-100px) rotate(180deg); opacity: 0.5; }
        }

        /* Header Section */
        .header {
            text-align: center;
            padding: 50px 20px;
            position: relative;
        }

        .main-title {
            font-size: 4rem;
            font-weight: bold;
            background: linear-gradient(45deg, #ff6b6b, #4ecdc4, #45b7d1, #96ceb4);
            background-size: 400% 400%;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            animation: gradientShift 3s ease infinite, titleBounce 2s ease-in-out infinite;
            margin-bottom: 20px;
            text-shadow: 0 0 30px rgba(255, 255, 255, 0.5);
        }

        @keyframes titleBounce {
            0%, 100% { transform: scale(1) rotateX(0deg); }
            50% { transform: scale(1.05) rotateX(5deg); }
        }

        .subtitle {
            font-size: 1.5rem;
            margin-bottom: 30px;
            animation: typewriter 4s steps(40, end), blink 0.75s step-end infinite;
            white-space: nowrap;
            overflow: hidden;
            border-right: 3px solid #ff6b6b;
            display: inline-block;
        }

        @keyframes typewriter {
            from { width: 0; }
            to { width: 100%; }
        }

        @keyframes blink {
            from, to { border-color: transparent; }
            50% { border-color: #ff6b6b; }
        }

        /* Interactive Skill Dashboard */
        .skill-dashboard {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 30px;
            margin: 50px 20px;
        }

        .skill-card {
            background: linear-gradient(135deg, rgba(255, 255, 255, 0.1), rgba(255, 255, 255, 0.05));
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.2);
            border-radius: 20px;
            padding: 30px;
            cursor: pointer;
            transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            position: relative;
            overflow: hidden;
        }

        .skill-card::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: conic-gradient(transparent, rgba(255, 107, 107, 0.3), transparent 30%);
            animation: rotate 4s linear infinite;
            opacity: 0;
            transition: opacity 0.3s ease;
        }

        .skill-card:hover::before {
            opacity: 1;
        }

        @keyframes rotate {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }

        .skill-card:hover {
            transform: translateY(-20px) rotateX(10deg) rotateY(10deg) scale(1.05);
            box-shadow: 
                0 30px 60px rgba(255, 107, 107, 0.4),
                0 0 50px rgba(255, 107, 107, 0.2),
                inset 0 0 20px rgba(255, 255, 255, 0.1);
            border-color: rgba(255, 107, 107, 0.6);
        }

        .skill-title {
            font-size: 1.8rem;
            margin-bottom: 20px;
            position: relative;
            z-index: 2;
        }

        .progress-container {
            width: 100%;
            height: 15px;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 10px;
            overflow: hidden;
            margin: 15px 0;
            position: relative;
        }

        .progress-bar {
            height: 100%;
            background: linear-gradient(90deg, #ff6b6b, #4ecdc4, #45b7d1);
            border-radius: 10px;
            position: relative;
            transition: width 2s cubic-bezier(0.25, 0.46, 0.45, 0.94);
            animation: progressGlow 2s ease infinite alternate;
        }

        @keyframes progressGlow {
            0% { box-shadow: 0 0 10px rgba(255, 107, 107, 0.5); }
            100% { box-shadow: 0 0 20px rgba(255, 107, 107, 0.8), 0 0 30px rgba(255, 107, 107, 0.4); }
        }

        .progress-bar::after {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.6), transparent);
            animation: shimmer 2s infinite;
        }

        @keyframes shimmer {
            0% { left: -100%; }
            100% { left: 100%; }
        }

        /* Project Cards */
        .projects-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(400px, 1fr));
            gap: 40px;
            margin: 50px 20px;
        }

        .project-card {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            border-radius: 25px;
            padding: 35px;
            position: relative;
            cursor: pointer;
            transition: all 0.5s cubic-bezier(0.23, 1, 0.320, 1);
            overflow: hidden;
        }

        .project-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.2), transparent);
            transition: left 0.5s ease;
        }

        .project-card:hover::before {
            left: 100%;
        }

        .project-card:hover {
            transform: translateY(-15px) rotateY(15deg) rotateX(10deg);
            box-shadow: 
                0 40px 80px rgba(102, 126, 234, 0.4),
                0 0 50px rgba(118, 75, 162, 0.3);
        }

        .project-title {
            font-size: 1.8rem;
            margin-bottom: 15px;
            animation: textPulse 2s ease-in-out infinite;
        }

        @keyframes textPulse {
            0%, 100% { opacity: 1; }
            50% { opacity: 0.8; }
        }

        /* Interactive Buttons */
        .interactive-btn {
            background: linear-gradient(45deg, #ff6b6b, #4ecdc4);
            border: none;
            border-radius: 50px;
            padding: 15px 30px;
            color: white;
            font-size: 1.2rem;
            font-weight: bold;
            cursor: pointer;
            position: relative;
            overflow: hidden;
            transition: all 0.3s ease;
            margin: 10px;
        }

        .interactive-btn::before {
            content: '';
            position: absolute;
            top: 50%;
            left: 50%;
            width: 0;
            height: 0;
            background: rgba(255, 255, 255, 0.3);
            border-radius: 50%;
            transition: all 0.5s ease;
            transform: translate(-50%, -50%);
        }

        .interactive-btn:hover::before {
            width: 300px;
            height: 300px;
        }

        .interactive-btn:hover {
            transform: scale(1.1) rotate(5deg);
            box-shadow: 0 15px 30px rgba(255, 107, 107, 0.4);
        }

        .interactive-btn:active {
            transform: scale(0.95) rotate(-5deg);
        }

        /* Floating Action Buttons */
        .floating-actions {
            position: fixed;
            right: 30px;
            bottom: 30px;
            z-index: 1000;
        }

        .fab {
            width: 60px;
            height: 60px;
            border-radius: 50%;
            background: linear-gradient(45deg, #ff6b6b, #4ecdc4);
            border: none;
            color: white;
            font-size: 1.5rem;
            cursor: pointer;
            margin: 10px 0;
            display: block;
            position: relative;
            transition: all 0.3s cubic-bezier(0.68, -0.55, 0.265, 1.55);
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.2);
        }

        .fab:hover {
            transform: scale(1.2) rotate(360deg);
            box-shadow: 0 20px 40px rgba(255, 107, 107, 0.4);
        }

        /* Achievement System */
        .achievement-popup {
            position: fixed;
            top: 20px;
            right: 20px;
            background: linear-gradient(45deg, #ff6b6b, #4ecdc4);
            color: white;
            padding: 20px;
            border-radius: 15px;
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.2);
            transform: translateX(400px);
            transition: transform 0.5s cubic-bezier(0.68, -0.55, 0.265, 1.55);
            z-index: 1001;
            max-width: 300px;
        }

        .achievement-popup.show {
            transform: translateX(0);
        }

        /* Stats Counter */
        .stats-container {
            display: flex;
            justify-content: space-around;
            flex-wrap: wrap;
            margin: 50px 20px;
        }

        .stat-item {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.2);
            border-radius: 20px;
            padding: 30px;
            text-align: center;
            cursor: pointer;
            transition: all 0.4s ease;
            margin: 15px;
            min-width: 200px;
        }

        .stat-item:hover {
            transform: translateY(-10px) scale(1.05);
            background: rgba(255, 255, 255, 0.2);
            box-shadow: 0 25px 50px rgba(255, 107, 107, 0.3);
        }

        .stat-number {
            font-size: 3rem;
            font-weight: bold;
            background: linear-gradient(45deg, #ff6b6b, #4ecdc4);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            animation: countUp 2s ease-out;
        }

        @keyframes countUp {
            from { transform: scale(0) rotate(180deg); }
            to { transform: scale(1) rotate(0deg); }
        }

        .stat-label {
            font-size: 1.2rem;
            margin-top: 10px;
            opacity: 0.9;
        }

        /* Mouse Trail Effect */
        .mouse-trail {
            position: fixed;
            width: 20px;
            height: 20px;
            background: radial-gradient(circle, rgba(255, 107, 107, 0.8), transparent);
            border-radius: 50%;
            pointer-events: none;
            z-index: 999;
            animation: trailFade 0.5s ease-out forwards;
        }

        @keyframes trailFade {
            to {
                transform: scale(0);
                opacity: 0;
            }
        }

        /* Scroll Animations */
        .scroll-reveal {
            opacity: 0;
            transform: translateY(50px);
            transition: all 0.8s cubic-bezier(0.25, 0.46, 0.45, 0.94);
        }

        .scroll-reveal.revealed {
            opacity: 1;
            transform: translateY(0);
        }

        /* Contact Form */
        .contact-form {
            max-width: 600px;
            margin: 50px auto;
            padding: 40px;
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border-radius: 25px;
            border: 1px solid rgba(255, 255, 255, 0.2);
        }

        .form-group {
            margin: 25px 0;
            position: relative;
        }

        .form-input {
            width: 100%;
            padding: 15px 20px;
            background: rgba(255, 255, 255, 0.1);
            border: 2px solid rgba(255, 255, 255, 0.2);
            border-radius: 15px;
            color: white;
            font-size: 1rem;
            transition: all 0.3s ease;
            outline: none;
        }

        .form-input:focus {
            border-color: #ff6b6b;
            box-shadow: 0 0 20px rgba(255, 107, 107, 0.3);
            transform: scale(1.02);
        }

        .form-input::placeholder {
            color: rgba(255, 255, 255, 0.6);
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .main-title { font-size: 2.5rem; }
            .subtitle { font-size: 1.2rem; }
            .skill-dashboard { grid-template-columns: 1fr; }
            .projects-container { grid-template-columns: 1fr; }
            .stats-container { flex-direction: column; align-items: center; }
        }

        /* Loading Animation */
        .loading-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(-45deg, #ee7752, #e73c7e, #23a6d5, #23d5ab);
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 10000;
            animation: gradientShift 3s ease infinite;
        }

        .loading-spinner {
            width: 100px;
            height: 100px;
            border: 5px solid rgba(255, 255, 255, 0.3);
            border-top: 5px solid white;
            border-radius: 50%;
            animation: spin 1s linear infinite;
        }

        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }

        .loading-text {
            color: white;
            font-size: 1.5rem;
            margin-left: 20px;
            animation: pulse 1.5s ease-in-out infinite;
        }

        @keyframes pulse {
            0%, 100% { opacity: 0.5; }
            50% { opacity: 1; }
        }
    </style>
</head>
<body>
    <!-- Loading Screen -->
    <div class="loading-overlay" id="loading">
        <div class="loading-spinner"></div>
        <div class="loading-text">Loading Awesomeness...</div>
    </div>

    <!-- Floating Particles -->
    <div class="particles" id="particles"></div>

    <!-- Header Section -->
    <div class="header scroll-reveal">
        <h1 class="main-title">SALIL GUPTA</h1>
        <div class="subtitle">CS Student @ GL Bajaj | Interactive Developer</div>
        <button class="interactive-btn" onclick="triggerConfetti()">🚀 Hire Me Now!</button>
        <button class="interactive-btn" onclick="showAchievement('Visitor', 'Welcome to my portfolio!')">✨ Explore Magic</button>
    </div>

    <!-- Skills Dashboard -->
    <div class="skill-dashboard">
        <div class="skill-card scroll-reveal" onclick="animateSkill(this, 90)">
            <div class="skill-title">🎨 Frontend Development</div>
            <div class="progress-container">
                <div class="progress-bar" data-width="90"></div>
            </div>
            <p>React, Next.js, Vue.js, HTML5/CSS3, JavaScript/TypeScript</p>
        </div>

        <div class="skill-card scroll-reveal" onclick="animateSkill(this, 85)">
            <div class="skill-title">⚙️ Backend Development</div>
            <div class="progress-container">
                <div class="progress-bar" data-width="85"></div>
            </div>
            <p>Node.js, Express.js, Python, Java, RESTful APIs</p>
        </div>

        <div class="skill-card scroll-reveal" onclick="animateSkill(this, 80)">
            <div class="skill-title">🗄️ Database Management</div>
            <div class="progress-container">
                <div class="progress-bar" data-width="80"></div>
            </div>
            <p>MongoDB, MySQL, PostgreSQL, Database Design</p>
        </div>

        <div class="skill-card scroll-reveal" onclick="animateSkill(this, 95)">
            <div class="skill-title">🛠️ Development Tools</div>
            <div class="progress-container">
                <div class="progress-bar" data-width="95"></div>
            </div>
            <p>Git, GitHub, VS Code, Docker, Linux, AWS</p>
        </div>
    </div>

    <!-- Projects Section -->
    <div class="projects-container">
        <div class="project-card scroll-reveal" onclick="projectClick(this)">
            <div class="project-title">🏪 E-Commerce Platform</div>
            <p><strong>Tech Stack:</strong> React, Node.js, MongoDB, Stripe API</p>
            <p><strong>Features:</strong> Shopping cart, payment integration, admin dashboard</p>
            <button class="interactive-btn">View Project</button>
        </div>

        <div class="project-card scroll-reveal" onclick="projectClick(this)">
            <div class="project-title">📊 Task Management System</div>
            <p><strong>Tech Stack:</strong> Next.js, TypeScript, PostgreSQL</p>
            <p><strong>Features:</strong> Team collaboration, real-time updates, analytics</p>
            <button class="interactive-btn">View Project</button>
        </div>

        <div class="project-card scroll-reveal" onclick="projectClick(this)">
            <div class="project-title">🌤️ Weather Dashboard</div>
            <p><strong>Tech Stack:</strong> Vue.js, Python Flask, Chart.js</p>
            <p><strong>Features:</strong> Real-time data, interactive charts, forecasts</p>
            <button class="interactive-btn">View Project</button>
        </div>

        <div class="project-card scroll-reveal" onclick="projectClick(this)">
            <div class="project-title">🎓 Student Portal</div>
            <p><strong>Tech Stack:</strong> Java Spring Boot, MySQL, Thymeleaf</p>
            <p><strong>Features:</strong> Grade tracking, course enrollment, attendance</p>
            <button class="interactive-btn">View Project</button>
        </div>
    </div>

    <!-- Stats Section -->
    <div class="stats-container">
        <div class="stat-item scroll-reveal" onclick="animateCounter(this)">
            <div class="stat-number" data-target="15">0</div>
            <div class="stat-label">Projects Completed</div>
        </div>
        <div class="stat-item scroll-reveal" onclick="animateCounter(this)">
            <div class="stat-number" data-target="500">0</div>
            <div class="stat-label">GitHub Contributions</div>
        </div>
        <div class="stat-item scroll-reveal" onclick="animateCounter(this)">
            <div class="stat-number" data-target="3">0</div>
            <div class="stat-label">Hackathons Won</div>
        </div>
        <div class="stat-item scroll-reveal" onclick="animateCounter(this)">
            <div class="stat-number" data-target="85">0</div>
            <div class="stat-label">CGPA (x10)</div>
        </div>
    </div>

    <!-- Contact Form -->
    <div class="contact-form scroll-reveal">
        <h2 style="text-align: center; margin-bottom: 30px;">Let's Connect!</h2>
        <div class="form-group">
            <input type="text" class="form-input" placeholder="Your Name" required>
        </div>
        <div class="form-group">
            <input type="email" class="form-input" placeholder="Your Email" required>
        </div>
        <div class="form-group">
            <textarea class="form-input" rows="5" placeholder="Your Message" required></textarea>
        </div>
        <button class="interactive-btn" onclick="submitForm()">Send Message 🚀</button>
    </div>

    <!-- Floating Action Buttons -->
    <div class="floating-actions">
        <button class="fab" onclick="scrollToTop()" title="Scroll to Top">↑</button>
        <button class="fab" onclick="toggleDarkMode()" title="Toggle Theme">🌙</button>
        <button class="fab" onclick="shareProfile()" title="Share Profile">📤</button>
    </div>

    <!-- Achievement Popup -->
    <div class="achievement-popup" id="achievement">
        <h3>🏆 Achievement Unlocked!</h3>
        <p id="achievement-text">Welcome to my portfolio!</p>
    </div>

    <script>
        // Variables
        let achievementCount = 0;
        let mouseTrails = [];
        let animatedElements = new Set();

        // Initialize everything when page loads
        window.addEventListener('load', function() {
            setTimeout(() => {
                document.getElementById('loading').style.display = 'none';
                createParticles();
                initScrollAnimations();
                showAchievement('Portfolio Loaded', 'Welcome to my interactive world!');
            }, 2000);
        });

        // Create floating particles
        function createParticles() {
            const particlesContainer = document.getElementById('particles');
            for (let i = 0; i < 50; i++) {
                const particle = document.createElement('div');
                particle.className = 'particle';
                particle.style.left = Math.random() * 100 + '%';
                particle.style.top = Math.random() * 100 + '%';
                particle.style.animationDelay = Math.random() * 6 + 's';
                particle.style.animationDuration = (Math.random() * 3 + 3) + 's';
                particlesContainer.appendChild(particle);
            }
        }

        // Mouse trail effect
        document.addEventListener('mousemove', function(e) {
            const trail = document.createElement('div');
            trail.className = 'mouse-trail';
            trail.style.left = e.clientX - 10 + 'px';
            trail.style.top = e.clientY - 10 + 'px';
            document.body.appendChild(trail);

            setTimeout(() => {
                if (trail.parentNode) {
                    trail.parentNode.removeChild(trail);
                }
            }, 500);
        });

        // Scroll animations
        function initScrollAnimations() {
            const observer = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.classList.add('revealed');
                        
                        // Animate progress bars
                        const progressBars = entry.target.querySelectorAll('.progress-bar');
                        progressBars.forEach(bar => {
                            const width = bar.dataset.width;
                            setTimeout(() => {
                                bar.style.width = width + '%';
                            }, 300);
                        });
                    }
                });
            }, { threshold: 0.1 });

            document.querySelectorAll('.scroll-reveal').forEach(el => {
                observer.observe(el);
            });
        }

        // Skill card animation
        function animateSkill(card, percentage) {
            const progressBar = card.querySelector('.progress-bar');
            progressBar.style.width = '0%';
            setTimeout(() => {
                progressBar.style.width = percentage + '%';
            }, 100);
            
            showAchievement('Skill Explored', `You checked out a skill worth ${percentage}%!`);
        }

        // Counter animation
        function animateCounter(statItem) {
            if (animatedElements.has(statItem)) return;
            animatedElements.add(statItem);

            const counter = statItem.querySelector('.stat-number');
            const target = parseInt(counter.dataset.target);
            let current = 0;
            const increment = target / 50;
            const timer = setInterval(() => {
                current += increment;
                if (current >= target) {
                    counter.textContent = target;
                    clearInterval(timer);
                } else {
                    counter.textContent = Math.floor(current);
                }
            }, 40);

            showAchievement('Stats Viewed', 'You discovered my achievements!');
        }

        // Project click handler
        function projectClick(project) {
            project.style.transform = 'scale(0.95) rotateY(180deg)';
            setTimeout(() => {
                project.style.transform = 'scale(1) rotateY(0deg)';
            }, 300);
            
            showAchievement('Project Interest', 'Thanks for checking out my work!');
        }

        // Achievement system
        function showAchievement(title, message) {
            const popup = document.getElementById('achievement');
            const textEl = document.getElementById('achievement-text');
            
            textEl.textContent = message;
            popup.classList.add('show');
            
            setTimeout(() => {
                popup.classList.remove('show');
            }, 3000);
            
            achievementCount++;
            if (achievementCount === 5) {
                setTimeout(() => {
                    showAchievement('Explorer', 'You\'ve unlocked 5 achievements! 🎉');
                }, 3500);
            }
        }

        // Confetti effect
        function triggerConfetti() {
            for (let i = 0; i < 100; i++) {
                createConfetti();
            }
            showAchievement('Hire Me!', 'Thanks for considering me! 🚀');
        }

        function createConfetti() {
            const colors = ['#ff6b6b', '#4ecdc4', '#45b7d1', '#96ceb4', '#ffeaa7'];
            const confetti = document.createElement('div');
            confetti.style.position = 'fixed';
            confetti.style.left = Math.random() * window.innerWidth + 'px';
            confetti.style.top = '-10px';
            confetti.style.width = '10px';
            confetti.style.height = '10px';
            confetti.style.backgroundColor = colors[Math.floor(Math.random() * colors.length)];
            confetti.style.pointerEvents = 'none';
            confetti.style.zIndex = '1002';
            document.body.appendChild(confetti);

            const animation = confetti.animate([
                { 
                    transform: 'translateY(0) rotate(0deg)',
                    opacity: 1 
                },
                { 
                    transform: `translateY(${window.innerHeight + 10}px) rotate(720deg)`,
                    opacity: 0 
                }
            ], {
                duration: Math.random() * 2000 + 1000,
                easing: 'cubic-bezier(0.25, 0.46, 0.45, 0.94)'
            });

            animation.onfinish = () => confetti.remove();
        }

        // Utility functions
        function scrollToTop() {
            window.scrollTo({ top: 0, behavior: 'smooth' });
            showAchievement('Back to Top', 'Smooth scrolling activated!');
        }

        function toggleDarkMode() {
            document.body.style.filter = document.body.style.filter === 'invert(1)' ? 'invert(0)' : 'invert(1)';
            showAchievement('Theme Toggle', 'Dark mode activated!');
        }

        function shareProfile() {
            if (navigator.share) {
                navigator.share({
                    title: 'Salil Gupta - Interactive Developer Portfolio',
                    text: 'Check out this amazing interactive portfolio!',
                    url: window.location.href
                });
            } else {
                navigator.clipboard.writeText(window.location.href);
                showAchievement('Link Copied', 'Portfolio link copied to clipboard!');
            }
        }

        function submitForm() {
            const inputs = document.querySelectorAll('.form-input');
            let allFilled = true;
            
            inputs.forEach(input => {
                if (!input.value.trim()) {
                    allFilled = false;
                    input.style.borderColor = '#ff6b6b';
                    input.style.animation = 'shake 0.5s ease-in-out';
                } else {
                    input.style.borderColor = '#4ecdc4';
                }
            });

            if (allFilled) {
                showAchievement('Form Submitted', 'Thanks for reaching out! I\'ll get back to you soon!');
                inputs.forEach(input => input.value = '');
                triggerConfetti();
            } else {
                showAchievement('Form Error', 'Please fill in all fields!');
            }
        }

        // Keyboard shortcuts
        document.addEventListener('keydown', function(e) {
            if (e.ctrlKey) {
                switch(e.key) {
                    case 'h':
                        e.preventDefault();
                        scrollToTop();
                        break;
                    case 't':
                        e.preventDefault();
                        toggleDarkMode();
                        break;
                    case 's':
                        e.preventDefault();
                        shareProfile();
                        break;
                    case 'c':
                        e.preventDefault();
                        triggerConfetti();
                        break;
                }
            }
        });

        // Auto-scroll effect for skill cards
        let skillIndex = 0;
        function autoHighlightSkills() {
            const skills = document.querySelectorAll('.skill-card');
            skills.forEach((skill, index) => {
                if (index === skillIndex) {
                    skill.style.transform = 'scale(1.02)';
                    skill.style.boxShadow = '0 20px 40px rgba(255, 107, 107, 0.3)';
                } else {
                    skill.style.transform = 'scale(1)';
                    skill.style.boxShadow = 'none';
                }
            });
            skillIndex = (skillIndex + 1) % skills.length;
        }

        // Start auto-highlighting after page load
        setTimeout(() => {
            setInterval(autoHighlightSkills, 3000);
        }, 5000);

        // Parallax effect
        window.addEventListener('scroll', () => {
            const scrolled = window.pageYOffset;
            const particles = document.querySelectorAll('.particle');
            particles.forEach((particle, index) => {
                const speed = (index % 3 + 1) * 0.5;
                particle.style.transform = `translateY(${scrolled * speed}px)`;
            });
        });

        // Click sound effect (visual feedback)
        document.addEventListener('click', function(e) {
            const ripple = document.createElement('div');
            ripple.style.position = 'absolute';
            ripple.style.left = e.clientX - 25 + 'px';
            ripple.style.top = e.clientY - 25 + 'px';
            ripple.style.width = '50px';
            ripple.style.height = '50px';
            ripple.style.background = 'radial-gradient(circle, rgba(255,107,107,0.6), transparent)';
            ripple.style.borderRadius = '50%';
            ripple.style.pointerEvents = 'none';
            ripple.style.zIndex = '1000';
            ripple.style.animation = 'rippleEffect 0.6s ease-out';
            document.body.appendChild(ripple);

            setTimeout(() => ripple.remove(), 600);
        });

        // Add ripple effect keyframes
        const style = document.createElement('style');
        style.textContent = `
            @keyframes rippleEffect {
                0% {
                    transform: scale(0);
                    opacity: 1;
                }
                100% {
                    transform: scale(4);
                    opacity: 0;
                }
            }
            
            @keyframes shake {
                0% { transform: translateX(0); }
                25% { transform: translateX(-5px); }
                50% { transform: translateX(5px); }
                75% { transform: translateX(-5px); }
                100% { transform: translateX(0); }
            }
        `;
        document.head.appendChild(style);

        // Easter eggs
        let konamiCode = [];
        const konamiSequence = [38, 38, 40, 40, 37, 39, 37, 39, 66, 65]; // ↑↑↓↓←→←→BA

        document.addEventListener('keydown', function(e) {
            konamiCode.push(e.keyCode);
            if (konamiCode.length > 10) konamiCode.shift();
            
            if (konamiCode.join('') === konamiSequence.join('')) {
                showAchievement('Konami Code!', 'You found the secret! 🎮');
                triggerMegaConfetti();
                konamiCode = [];
            }
        });

        function triggerMegaConfetti() {
            for (let i = 0; i < 200; i++) {
                setTimeout(() => createConfetti(), i * 10);
            }
            
            // Rainbow background flash
            const originalBg = document.body.style.background;
            const colors = ['#ff0000', '#ff8000', '#ffff00', '#80ff00', '#00ff00', '#00ff80', '#00ffff', '#0080ff', '#0000ff', '#8000ff', '#ff00ff', '#ff0080'];
            let colorIndex = 0;
            
            const flashInterval = setInterval(() => {
                document.body.style.background = colors[colorIndex];
                colorIndex = (colorIndex + 1) % colors.length;
            }, 100);
            
            setTimeout(() => {
                clearInterval(flashInterval);
                document.body.style.background = originalBg;
            }, 2000);
        }

        // Mobile optimizations
        if (window.innerWidth <= 768) {
            // Reduce particle count for mobile
            const particles = document.querySelectorAll('.particle');
            particles.forEach((particle, index) => {
                if (index > 20) particle.remove();
            });
            
            // Simplify animations for better performance
            document.body.style.setProperty('--animation-duration', '0.3s');
        }

        // Performance monitoring
        let frameCount = 0;
        let lastTime = performance.now();

        function measurePerformance() {
            frameCount++;
            const currentTime = performance.now();
            
            if (currentTime >= lastTime + 1000) {
                const fps = Math.round((frameCount * 1000) / (currentTime - lastTime));
                if (fps < 30) {
                    // Reduce effects for better performance
                    document.querySelectorAll('.particle').forEach(p => p.style.display = 'none');
                }
                frameCount = 0;
                lastTime = currentTime;
            }
            
            requestAnimationFrame(measurePerformance);
        }

        requestAnimationFrame(measurePerformance);

        // Welcome message
        setTimeout(() => {
            showAchievement('Welcome!', 'Try hovering over elements and pressing Ctrl+H, Ctrl+T, Ctrl+S, or Ctrl+C!');
        }, 3000);
    </script>
</body>
</html>
