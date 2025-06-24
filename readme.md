<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Hriday Sonar - Frontend Developer</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(-45deg, #ee7752, #e73c7e, #23a6d5, #23d5ab);
            background-size: 400% 400%;
            animation: gradientBG 15s ease infinite;
            color: white;
            overflow-x: hidden;
        }

        @keyframes gradientBG {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Floating particles animation */
        .particles {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 1;
        }

        .particle {
            position: absolute;
            width: 4px;
            height: 4px;
            background: rgba(255, 255, 255, 0.5);
            border-radius: 50%;
            animation: float 20s infinite linear;
        }

        @keyframes float {
            0% {
                transform: translateY(100vh) rotate(0deg);
                opacity: 0;
            }
            10% {
                opacity: 1;
            }
            90% {
                opacity: 1;
            }
            100% {
                transform: translateY(-100vh) rotate(360deg);
                opacity: 0;
            }
        }

        /* Header Section */
        .header {
            text-align: center;
            padding: 100px 0 80px;
            position: relative;
            z-index: 10;
        }

        .profile-img {
            width: 200px;
            height: 200px;
            border-radius: 50%;
            border: 5px solid rgba(255, 255, 255, 0.3);
            margin: 0 auto 30px;
            background: linear-gradient(45deg, #ff6b6b, #4ecdc4);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 80px;
            animation: pulse 2s ease-in-out infinite alternate;
        }

        @keyframes pulse {
            from { transform: scale(1); }
            to { transform: scale(1.05); }
        }

        .name {
            font-size: 3.5rem;
            font-weight: bold;
            margin-bottom: 20px;
            background: linear-gradient(45deg, #fff, #ff6b6b, #4ecdc4);
            background-size: 200% 200%;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            animation: textGradient 3s ease infinite;
        }

        @keyframes textGradient {
            0%, 100% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
        }

        .title {
            font-size: 1.5rem;
            margin-bottom: 10px;
            opacity: 0.9;
        }

        .location {
            font-size: 1.2rem;
            opacity: 0.8;
        }

        /* About Section */
        .about {
            background: rgba(255, 255, 255, 0.1);
            padding: 60px 0;
            margin: 50px 0;
            border-radius: 20px;
            backdrop-filter: blur(10px);
            position: relative;
            z-index: 10;
        }

        .section-title {
            font-size: 2.5rem;
            text-align: center;
            margin-bottom: 40px;
            position: relative;
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 100px;
            height: 3px;
            background: linear-gradient(45deg, #ff6b6b, #4ecdc4);
            border-radius: 2px;
        }

        .about-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 30px;
            margin-top: 40px;
        }

        .about-item {
            background: rgba(255, 255, 255, 0.1);
            padding: 30px;
            border-radius: 15px;
            text-align: center;
            transition: transform 0.3s ease;
            backdrop-filter: blur(5px);
        }

        .about-item:hover {
            transform: translateY(-10px);
        }

        .about-item h3 {
            color: #4ecdc4;
            margin-bottom: 15px;
            font-size: 1.3rem;
        }

        /* Skills Section */
        .skills {
            padding: 80px 0;
            position: relative;
            z-index: 10;
        }

        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
            gap: 30px;
            margin-top: 50px;
        }

        .skill-item {
            background: rgba(255, 255, 255, 0.1);
            padding: 30px 20px;
            border-radius: 15px;
            text-align: center;
            transition: all 0.3s ease;
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            position: relative;
            overflow: hidden;
        }

        .skill-item::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: linear-gradient(45deg, transparent, rgba(255, 255, 255, 0.1), transparent);
            transform: rotate(45deg);
            transition: all 0.5s ease;
            opacity: 0;
        }

        .skill-item:hover::before {
            animation: shine 0.8s ease-in-out;
        }

        @keyframes shine {
            0% { transform: translateX(-100%) translateY(-100%) rotate(45deg); opacity: 0; }
            50% { opacity: 1; }
            100% { transform: translateX(100%) translateY(100%) rotate(45deg); opacity: 0; }
        }

        .skill-item:hover {
            transform: translateY(-10px) scale(1.05);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.3);
        }

        .skill-logo {
            font-size: 3rem;
            margin-bottom: 15px;
            display: block;
            transition: transform 0.3s ease;
        }

        .skill-item:hover .skill-logo {
            transform: rotateY(360deg);
        }

        .skill-name {
            font-size: 1rem;
            font-weight: 600;
            color: white;
        }

        /* Stats Section */
        .stats {
            background: rgba(255, 255, 255, 0.1);
            padding: 60px 0;
            margin: 50px 0;
            border-radius: 20px;
            backdrop-filter: blur(10px);
            position: relative;
            z-index: 10;
        }

        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 40px;
            margin-top: 40px;
        }

        .stat-item {
            text-align: center;
            padding: 30px;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 15px;
            transition: transform 0.3s ease;
        }

        .stat-item:hover {
            transform: translateY(-5px);
        }

        .stat-number {
            font-size: 3rem;
            font-weight: bold;
            color: #4ecdc4;
            display: block;
        }

        .stat-label {
            font-size: 1.1rem;
            margin-top: 10px;
            opacity: 0.9;
        }

        /* Contact Section */
        .contact {
            padding: 80px 0;
            text-align: center;
            position: relative;
            z-index: 10;
        }

        .contact-links {
            display: flex;
            justify-content: center;
            gap: 30px;
            margin-top: 40px;
            flex-wrap: wrap;
        }

        .contact-link {
            display: inline-block;
            padding: 15px 30px;
            background: linear-gradient(45deg, #ff6b6b, #4ecdc4);
            color: white;
            text-decoration: none;
            border-radius: 50px;
            font-weight: 600;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
            z-index: 1;
        }

        .contact-link::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(45deg, #4ecdc4, #ff6b6b);
            transition: left 0.3s ease;
            z-index: -1;
        }

        .contact-link:hover::before {
            left: 0;
        }

        .contact-link:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.3);
        }

        /* Footer */
        .footer {
            text-align: center;
            padding: 40px 0;
            background: rgba(0, 0, 0, 0.3);
            position: relative;
            z-index: 10;
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .name {
                font-size: 2.5rem;
            }
            
            .skills-grid {
                grid-template-columns: repeat(auto-fit, minmax(100px, 1fr));
                gap: 20px;
            }
            
            .skill-logo {
                font-size: 2.5rem;
            }
            
            .contact-links {
                flex-direction: column;
                align-items: center;
            }
        }

        /* Skill specific colors */
        .html5 { color: #E34F26; }
        .css3 { color: #1572B6; }
        .bootstrap { color: #7952B3; }
        .tailwind { color: #38B2AC; }
        .javascript { color: #F7DF1E; }
        .react { color: #61DAFB; }
        .nodejs { color: #43853D; }
        .express { color: #000000; background: white; border-radius: 5px; }
        .mongodb { color: #4EA94B; }
        .firebase { color: #FFCA28; }
        .jwt { color: #000000; background: white; border-radius: 5px; }
        .mongoose { color: #880000; }
        .git { color: #F05032; }
        .linux { color: #FCC624; }
        .vscode { color: #007ACC; }
        .figma { color: #F24E1E; }
    </style>
</head>
<body>
    <!-- Floating Particles Background -->
    <div class="particles" id="particles"></div>

    <!-- Header Section -->
    <section class="header">
        <div class="container">
            <div class="profile-img">👨‍💻</div>
            <h1 class="name">HRIDAY SONAR</h1>
            <p class="title">Frontend Developer | MERN Stack Enthusiast</p>
            <p class="location">📍 Bangladesh 🇧🇩</p>
        </div>
    </section>

    <!-- About Section -->
    <section class="about">
        <div class="container">
            <h2 class="section-title">About Me</h2>
            <div class="about-content">
                <div class="about-item">
                    <h3>🔥 Currently Building</h3>
                    <p>Modern MERN Stack Applications with cutting-edge technologies</p>
                </div>
                <div class="about-item">
                    <h3>📚 Currently Learning</h3>
                    <p>Advanced React, Next.js, and TypeScript concepts</p>
                </div>
                <div class="about-item">
                    <h3>💡 Passion</h3>
                    <p>Creating interactive and user-friendly web applications</p>
                </div>
                <div class="about-item">
                    <h3>🎯 Focus</h3>
                    <p>Frontend Development Best Practices & Latest Web Technologies</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Skills Section -->
    <section class="skills">
        <div class="container">
            <h2 class="section-title">Tech Stack & Skills</h2>
            <div class="skills-grid">
                <div class="skill-item">
                    <span class="skill-logo html5">🌐</span>
                    <div class="skill-name">HTML5</div>
                </div>
                <div class="skill-item">
                    <span class="skill-logo css3">🎨</span>
                    <div class="skill-name">CSS3</div>
                </div>
                <div class="skill-item">
                    <span class="skill-logo bootstrap">🅱️</span>
                    <div class="skill-name">Bootstrap</div>
                </div>
                <div class="skill-item">
                    <span class="skill-logo tailwind">🌊</span>
                    <div class="skill-name">Tailwind CSS</div>
                </div>
                <div class="skill-item">
                    <span class="skill-logo javascript">⚡</span>
                    <div class="skill-name">JavaScript</div>
                </div>
                <div class="skill-item">
                    <span class="skill-logo react">⚛️</span>
                    <div class="skill-name">React</div>
                </div>
                <div class="skill-item">
                    <span class="skill-logo nodejs">💚</span>
                    <div class="skill-name">Node.js</div>
                </div>
                <div class="skill-item">
                    <span class="skill-logo express">🚀</span>
                    <div class="skill-name">Express.js</div>
                </div>
                <div class="skill-item">
                    <span class="skill-logo mongodb">🍃</span>
                    <div class="skill-name">MongoDB</div>
                </div>
                <div class="skill-item">
                    <span class="skill-logo firebase">🔥</span>
                    <div class="skill-name">Firebase</div>
                </div>
                <div class="skill-item">
                    <span class="skill-logo jwt">🔐</span>
                    <div class="skill-name">JWT</div>
                </div>
                <div class="skill-item">
                    <span class="skill-logo mongoose">🦫</span>
                    <div class="skill-name">Mongoose</div>
                </div>
                <div class="skill-item">
                    <span class="skill-logo git">📝</span>
                    <div class="skill-name">Git</div>
                </div>
                <div class="skill-item">
                    <span class="skill-logo linux">🐧</span>
                    <div class="skill-name">Linux</div>
                </div>
                <div class="skill-item">
                    <span class="skill-logo vscode">💻</span>
                    <div class="skill-name">VS Code</div>
                </div>
                <div class="skill-item">
                    <span class="skill-logo figma">🎨</span>
                    <div class="skill-name">Figma</div>
                </div>
            </div>
        </div>
    </section>

    <!-- Stats Section -->
    <section class="stats">
        <div class="container">
            <h2 class="section-title">GitHub Stats</h2>
            <div class="stats-grid">
                <div class="stat-item">
                    <span class="stat-number">50+</span>
                    <div class="stat-label">Projects Completed</div>
                </div>
                <div class="stat-item">
                    <span class="stat-number">500+</span>
                    <div class="stat-label">Commits This Year</div>
                </div>
                <div class="stat-item">
                    <span class="stat-number">15+</span>
                    <div class="stat-label">Technologies</div>
                </div>
                <div class="stat-item">
                    <span class="stat-number">2+</span>
                    <div class="stat-label">Years Experience</div>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section class="contact">
        <div class="container">
            <h2 class="section-title">Let's Connect!</h2>
            <p>Ready to build something amazing together? Let's chat!</p>
            <div class="contact-links">
                <a href="https://linkedin.com/in/hridoy-sonar-94b42a331" class="contact-link">LinkedIn</a>
                <a href="https://fb.com/profile.php?id=61557692312244" class="contact-link">Facebook</a>
                <a href="mailto:mdhridaysonar@gmail.com" class="contact-link">Email</a>
                <a href="https://phenomenal-cuchufli-fef911.netlify.app/" class="contact-link">Portfolio</a>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="footer">
        <div class="container">
            <p>&copy; 2024 Hriday Sonar. Made with ❤️ and lots of ☕</p>
            <p>💻 Happy Coding! Keep Building Amazing Things!</p>
        </div>
    </footer>

    <script>
        // Create floating particles
        function createParticles() {
            const particles = document.getElementById('particles');
            const particleCount = 50;

            for (let i = 0; i < particleCount; i++) {
                const particle = document.createElement('div');
                particle.className = 'particle';
                particle.style.left = Math.random() * 100 + '%';
                particle.style.animationDelay = Math.random() * 20 + 's';
                particle.style.animationDuration = (Math.random() * 10 + 10) + 's';
                particles.appendChild(particle);
            }
        }

        // Smooth scrolling for links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                document.querySelector(this.getAttribute('href')).scrollIntoView({
                    behavior: 'smooth'
                });
            });
        });

        // Add scroll animations
        function animateOnScroll() {
            const elements = document.querySelectorAll('.skill-item, .about-item, .stat-item');
            
            elements.forEach(element => {
                const elementTop = element.getBoundingClientRect().top;
                const elementVisible = 150;
                
                if (elementTop < window.innerHeight - elementVisible) {
                    element.style.opacity = '1';
                    element.style.transform = 'translateY(0)';
                }
            });
        }

        // Initialize animations
        document.addEventListener('DOMContentLoaded', function() {
            createParticles();
            
            // Set initial state for scroll animations
            document.querySelectorAll('.skill-item, .about-item, .stat-item').forEach(element => {
                element.style.opacity = '0';
                element.style.transform = 'translateY(30px)';
                element.style.transition = 'all 0.6s ease';
            });
            
            // Trigger animations on scroll
            window.addEventListener('scroll', animateOnScroll);
            animateOnScroll(); // Run once on load
        });

        // Add interactive cursor effect
        document.addEventListener('mousemove', function(e) {
            const cursor = document.querySelector('.cursor');
            if (!cursor) {
                const newCursor = document.createElement('div');
                newCursor.className = 'cursor';
                newCursor.style.cssText = `
                    position: fixed;
                    width: 20px;
                    height: 20px;
                    background: radial-gradient(circle, rgba(255,255,255,0.3) 0%, transparent 70%);
                    border-radius: 50%;
                    pointer-events: none;
                    z-index: 9999;
                    transition: all 0.1s ease;
                `;
                document.body.appendChild(newCursor);
            }
            
            const cursorElement = document.querySelector('.cursor');
            cursorElement.style.left = e.clientX - 10 + 'px';
            cursorElement.style.top = e.clientY - 10 + 'px';
        });
    </script>
</body>
</html>
