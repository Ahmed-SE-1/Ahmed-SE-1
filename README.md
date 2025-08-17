<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ahmed Ali - Developer Profile</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
            background: #0d1117;
            color: #c9d1d9;
            overflow-x: hidden;
        }

        .stars {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 1;
        }

        .star {
            position: absolute;
            background: #fff;
            border-radius: 50%;
            animation: twinkle 2s infinite alternate;
        }

        @keyframes twinkle {
            0% { opacity: 0.3; transform: scale(1); }
            100% { opacity: 1; transform: scale(1.2); }
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
            position: relative;
            z-index: 2;
        }

        .header {
            text-align: center;
            padding: 60px 0;
            background: linear-gradient(135deg, #1e3a8a 0%, #7c3aed 50%, #ec4899 100%);
            border-radius: 30px;
            margin-bottom: 40px;
            position: relative;
            overflow: hidden;
        }

        .header::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: linear-gradient(45deg, transparent 30%, rgba(255,255,255,0.1) 50%, transparent 70%);
            animation: shine 3s linear infinite;
        }

        @keyframes shine {
            0% { transform: translateX(-100%) translateY(-100%); }
            100% { transform: translateX(100%) translateY(100%); }
        }

        .avatar {
            width: 150px;
            height: 150px;
            border-radius: 50%;
            background: linear-gradient(45deg, #ff6b6b, #4ecdc4, #45b7d1, #96ceb4);
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 30px;
            font-size: 4rem;
            position: relative;
            z-index: 2;
            animation: float 3s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-20px); }
        }

        .name {
            font-size: 4rem;
            font-weight: 900;
            background: linear-gradient(135deg, #fff, #e2e8f0);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            margin-bottom: 15px;
            position: relative;
            z-index: 2;
        }

        .title {
            font-size: 1.5rem;
            color: #e2e8f0;
            margin-bottom: 20px;
            position: relative;
            z-index: 2;
        }

        .typing-text {
            border-right: 2px solid #fff;
            animation: typing 4s steps(40) infinite, blink 1s infinite;
        }

        @keyframes typing {
            0%, 50%, 100% { width: 0; }
            25%, 75% { width: 100%; }
        }

        @keyframes blink {
            0%, 50% { border-color: #fff; }
            51%, 100% { border-color: transparent; }
        }

        .location {
            color: #9ca3af;
            font-size: 1.1rem;
            margin-bottom: 30px;
            position: relative;
            z-index: 2;
        }

        .main-content {
            display: grid;
            grid-template-columns: 1fr 300px;
            gap: 40px;
            margin-bottom: 40px;
        }

        .left-column {
            background: linear-gradient(135deg, #1f2937 0%, #111827 100%);
            border-radius: 25px;
            padding: 40px;
            border: 1px solid #374151;
            box-shadow: 0 25px 50px -12px rgba(0, 0, 0, 0.5);
        }

        .right-column {
            display: flex;
            flex-direction: column;
            gap: 20px;
        }

        .section-title {
            font-size: 2rem;
            font-weight: 700;
            color: #f9fafb;
            margin-bottom: 25px;
            display: flex;
            align-items: center;
            gap: 15px;
        }

        .section-icon {
            width: 40px;
            height: 40px;
            background: linear-gradient(135deg, #3b82f6, #8b5cf6);
            border-radius: 12px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.2rem;
        }

        .about-text {
            font-size: 1.1rem;
            line-height: 1.8;
            color: #d1d5db;
            margin-bottom: 30px;
        }

        .highlight {
            background: linear-gradient(135deg, #3b82f6, #8b5cf6);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            font-weight: 600;
        }

        .skills-container {
            margin-bottom: 30px;
        }

        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
            gap: 15px;
            margin-bottom: 20px;
        }

        .skill-item {
            background: linear-gradient(135deg, #374151 0%, #1f2937 100%);
            padding: 15px;
            border-radius: 15px;
            text-align: center;
            border: 1px solid #4b5563;
            transition: all 0.3s ease;
            cursor: pointer;
        }

        .skill-item:hover {
            transform: translateY(-8px) scale(1.05);
            box-shadow: 0 20px 40px rgba(59, 130, 246, 0.3);
            border-color: #3b82f6;
        }

        .skill-icon {
            font-size: 2rem;
            margin-bottom: 8px;
        }

        .skill-name {
            font-size: 0.9rem;
            color: #d1d5db;
            font-weight: 500;
        }

        .stats-card {
            background: linear-gradient(135deg, #1e293b 0%, #0f172a 100%);
            border-radius: 20px;
            padding: 25px;
            border: 1px solid #334155;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
        }

        .stats-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 20px;
            margin-bottom: 20px;
        }

        .stat-item {
            text-align: center;
            padding: 15px;
            background: rgba(59, 130, 246, 0.1);
            border-radius: 12px;
            border: 1px solid rgba(59, 130, 246, 0.2);
        }

        .stat-number {
            font-size: 2rem;
            font-weight: 800;
            color: #3b82f6;
            display: block;
        }

        .stat-label {
            font-size: 0.8rem;
            color: #9ca3af;
            margin-top: 5px;
        }

        .contact-card {
            background: linear-gradient(135deg, #7c3aed 0%, #ec4899 100%);
            border-radius: 20px;
            padding: 25px;
            text-align: center;
            box-shadow: 0 10px 30px rgba(124, 58, 237, 0.3);
        }

        .contact-title {
            font-size: 1.5rem;
            font-weight: 700;
            margin-bottom: 20px;
            color: #fff;
        }

        .contact-links {
            display: flex;
            flex-direction: column;
            gap: 12px;
        }

        .contact-link {
            background: rgba(255, 255, 255, 0.2);
            color: #fff;
            padding: 12px 16px;
            border-radius: 12px;
            text-decoration: none;
            transition: all 0.3s ease;
            backdrop-filter: blur(10px);
            font-size: 0.9rem;
        }

        .contact-link:hover {
            background: rgba(255, 255, 255, 0.3);
            transform: translateX(5px);
        }

        .projects-section {
            background: linear-gradient(135deg, #1f2937 0%, #111827 100%);
            border-radius: 25px;
            padding: 40px;
            border: 1px solid #374151;
            box-shadow: 0 25px 50px -12px rgba(0, 0, 0, 0.5);
            margin-bottom: 30px;
        }

        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 25px;
            margin-top: 30px;
        }

        .project-card {
            background: linear-gradient(135deg, #374151 0%, #1f2937 100%);
            border-radius: 20px;
            padding: 25px;
            border: 1px solid #4b5563;
            transition: all 0.4s ease;
            position: relative;
            overflow: hidden;
        }

        .project-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 4px;
            background: linear-gradient(90deg, #3b82f6, #8b5cf6, #ec4899);
            transition: all 0.4s ease;
        }

        .project-card:hover::before {
            left: 0;
        }

        .project-card:hover {
            transform: translateY(-10px) scale(1.02);
            box-shadow: 0 25px 50px rgba(59, 130, 246, 0.2);
            border-color: #3b82f6;
        }

        .project-header {
            display: flex;
            align-items: center;
            gap: 15px;
            margin-bottom: 15px;
        }

        .project-icon {
            width: 50px;
            height: 50px;
            background: linear-gradient(135deg, #3b82f6, #8b5cf6);
            border-radius: 12px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.5rem;
        }

        .project-title {
            font-size: 1.3rem;
            font-weight: 600;
            color: #f9fafb;
        }

        .project-description {
            color: #d1d5db;
            line-height: 1.6;
            margin-bottom: 15px;
        }

        .tech-tags {
            display: flex;
            flex-wrap: wrap;
            gap: 8px;
            margin-bottom: 20px;
        }

        .tech-tag {
            background: rgba(59, 130, 246, 0.2);
            color: #93c5fd;
            padding: 4px 10px;
            border-radius: 8px;
            font-size: 0.75rem;
            border: 1px solid rgba(59, 130, 246, 0.3);
        }

        .project-links {
            display: flex;
            gap: 10px;
        }

        .project-link {
            background: linear-gradient(135deg, #3b82f6, #1d4ed8);
            color: #fff;
            padding: 8px 16px;
            border-radius: 8px;
            text-decoration: none;
            font-size: 0.85rem;
            transition: all 0.3s ease;
        }

        .project-link:hover {
            transform: translateY(-2px);
            box-shadow: 0 10px 20px rgba(59, 130, 246, 0.3);
        }

        .footer {
            text-align: center;
            padding: 40px;
            background: linear-gradient(135deg, #1e293b 0%, #0f172a 100%);
            border-radius: 25px;
            border: 1px solid #334155;
        }

        .footer-text {
            font-size: 1.1rem;
            color: #64748b;
            margin-bottom: 20px;
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 20px;
        }

        .social-link {
            width: 50px;
            height: 50px;
            background: linear-gradient(135deg, #3b82f6, #8b5cf6);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: #fff;
            text-decoration: none;
            font-size: 1.2rem;
            transition: all 0.3s ease;
        }

        .social-link:hover {
            transform: translateY(-5px) scale(1.1);
            box-shadow: 0 15px 30px rgba(59, 130, 246, 0.4);
        }

        @media (max-width: 768px) {
            .main-content {
                grid-template-columns: 1fr;
            }
            
            .name {
                font-size: 2.5rem;
            }
            
            .projects-grid {
                grid-template-columns: 1fr;
            }
            
            .skills-grid {
                grid-template-columns: repeat(auto-fit, minmax(100px, 1fr));
            }
        }
    </style>
</head>
<body>
    <div class="stars" id="stars"></div>
    
    <div class="container">
        <!-- Header Section -->
        <header class="header">
            <div class="avatar">👨‍💻</div>
            <h1 class="name">Ahmed Ali</h1>
            <div class="title">
                <span class="typing-text">Full Stack Developer & Mobile App Developer</span>
            </div>
            <div class="location">📍 Pakistan</div>
        </header>

        <!-- Main Content -->
        <div class="main-content">
            <div class="left-column">
                <!-- About Section -->
                <div class="about-section">
                    <h2 class="section-title">
                        <div class="section-icon">🚀</div>
                        About Me
                    </h2>
                    <p class="about-text">
                        I'm a passionate <span class="highlight">Full Stack Web Developer</span> and 
                        <span class="highlight">Flutter/Dart Mobile App Developer</span> from Pakistan, dedicated to 
                        creating innovative digital solutions that make a difference.
                    </p>
                    <p class="about-text">
                        🌱 I'm currently learning <span class="highlight">MERN Stack</span>, 
                        <span class="highlight">DevOps</span> and <span class="highlight">Cloud Technologies</span>
                    </p>
                </div>

                <!-- Skills Section -->
                <div class="skills-container">
                    <h2 class="section-title">
                        <div class="section-icon">⚡</div>
                        Tech Stack
                    </h2>
                    <div class="skills-grid">
                        <div class="skill-item">
                            <div class="skill-icon">⚛️</div>
                            <div class="skill-name">React</div>
                        </div>
                        <div class="skill-item">
                            <div class="skill-icon">📱</div>
                            <div class="skill-name">Flutter</div>
                        </div>
                        <div class="skill-item">
                            <div class="skill-icon">🟢</div>
                            <div class="skill-name">Node.js</div>
                        </div>
                        <div class="skill-item">
                            <div class="skill-icon">🍃</div>
                            <div class="skill-name">MongoDB</div>
                        </div>
                        <div class="skill-item">
                            <div class="skill-icon">🔥</div>
                            <div class="skill-name">Firebase</div>
                        </div>
                        <div class="skill-item">
                            <div class="skill-icon">🎯</div>
                            <div class="skill-name">Dart</div>
                        </div>
                        <div class="skill-item">
                            <div class="skill-icon">⚡</div>
                            <div class="skill-name">Express</div>
                        </div>
                        <div class="skill-item">
                            <div class="skill-icon">🔷</div>
                            <div class="skill-name">MySQL</div>
                        </div>
                    </div>
                </div>
            </div>

            <div class="right-column">
                <!-- Stats Card -->
                <div class="stats-card">
                    <h3 class="section-title">
                        <div class="section-icon">📊</div>
                        GitHub Stats
                    </h3>
                    <div class="stats-grid">
                        <div class="stat-item">
                            <span class="stat-number">50+</span>
                            <div class="stat-label">Repositories</div>
                        </div>
                        <div class="stat-item">
                            <span class="stat-number">500+</span>
                            <div class="stat-label">Contributions</div>
                        </div>
                        <div class="stat-item">
                            <span class="stat-number">20+</span>
                            <div class="stat-label">Projects</div>
                        </div>
                        <div class="stat-item">
                            <span class="stat-number">5+</span>
                            <div class="stat-label">Languages</div>
                        </div>
                    </div>
                </div>

                <!-- Contact Card -->
                <div class="contact-card">
                    <h3 class="contact-title">Let's Connect!</h3>
                    <div class="contact-links">
                        <a href="https://www.linkedin.com/in/ahmed-ali-69a697369" class="contact-link">
                            🔗 LinkedIn Profile
                        </a>
                        <a href="https://portfolio-ashen-five-fid1y22m2r.vercel.app/" class="contact-link">
                            🌐 Portfolio Website
                        </a>
                        <a href="mailto:ahmedaliqurexhi7867@gmail.com" class="contact-link">
                            📧 Email Me
                        </a>
                        <a href="tel:+923277889448" class="contact-link">
                            📱 +92 327 7889448
                        </a>
                    </div>
                </div>
            </div>
        </div>

        <!-- Projects Section -->
        <section class="projects-section">
            <h2 class="section-title">
                <div class="section-icon">💼</div>
                Featured Projects
            </h2>
            <div class="projects-grid">
                <div class="project-card">
                    <div class="project-header">
                        <div class="project-icon">🌐</div>
                        <h3 class="project-title">E-Commerce Platform</h3>
                    </div>
                    <p class="project-description">
                        A full-stack e-commerce solution built with MERN stack, featuring user authentication, 
                        payment integration, and admin dashboard.
                    </p>
                    <div class="tech-tags">
                        <span class="tech-tag">React</span>
                        <span class="tech-tag">Node.js</span>
                        <span class="tech-tag">MongoDB</span>
                        <span class="tech-tag">Stripe</span>
                    </div>
                    <div class="project-links">
                        <a href="#" class="project-link">Live Demo</a>
                        <a href="#" class="project-link">GitHub</a>
                    </div>
                </div>

                <div class="project-card">
                    <div class="project-header">
                        <div class="project-icon">📱</div>
                        <h3 class="project-title">Flutter Chat App</h3>
                    </div>
                    <p class="project-description">
                        Real-time messaging app with Firebase integration, featuring group chats, 
                        media sharing, and push notifications.
                    </p>
                    <div class="tech-tags">
                        <span class="tech-tag">Flutter</span>
                        <span class="tech-tag">Dart</span>
                        <span class="tech-tag">Firebase</span>
                        <span class="tech-tag">Cloud Functions</span>
                    </div>
                    <div class="project-links">
                        <a href="#" class="project-link">Download</a>
                        <a href="#" class="project-link">GitHub</a>
                    </div>
                </div>

                <div class="project-card">
                    <div class="project-header">
                        <div class="project-icon">📊</div>
                        <h3 class="project-title">Analytics Dashboard</h3>
                    </div>
                    <p class="project-description">
                        Interactive data visualization dashboard with real-time charts, 
                        custom filters, and export functionality.
                    </p>
                    <div class="tech-tags">
                        <span class="tech-tag">React</span>
                        <span class="tech-tag">D3.js</span>
                        <span class="tech-tag">Express</span>
                        <span class="tech-tag">PostgreSQL</span>
                    </div>
                    <div class="project-links">
                        <a href="#" class="project-link">Live Demo</a>
                        <a href="#" class="project-link">GitHub</a>
                    </div>
                </div>
            </div>
        </section>

        <!-- Footer -->
        <footer class="footer">
            <p class="footer-text">
                ✨ Always excited to collaborate on innovative projects! ✨
            </p>
            <div class="social-links">
                <a href="https://github.com/ahmed-ali" class="social-link">🐙</a>
                <a href="https://www.linkedin.com/in/ahmed-ali-69a697369" class="social-link">💼</a>
                <a href="mailto:ahmedaliqurexhi7867@gmail.com" class="social-link">📧</a>
                <a href="https://portfolio-ashen-five-fid1y22m2r.vercel.app/" class="social-link">🌐</a>
            </div>
        </footer>
    </div>

    <script>
        // Create animated stars
        function createStars() {
            const starsContainer = document.getElementById('stars');
            const starCount = 100;

            for (let i = 0; i < starCount; i++) {
                const star = document.createElement('div');
                star.className = 'star';
                star.style.left = Math.random() * 100 + '%';
                star.style.top = Math.random() * 100 + '%';
                star.style.width = Math.random() * 3 + 1 + 'px';
                star.style.height = star.style.width;
                star.style.animationDelay = Math.random() * 2 + 's';
                star.style.animationDuration = (Math.random() * 3 + 2) + 's';
                starsContainer.appendChild(star);
            }
        }

        // Typing effect
        function typeWriter() {
            const text = "Full Stack Developer & Mobile App Developer";
            const element = document.querySelector('.typing-text');
            let index = 0;
            let isDeleting = false;

            function type() {
                const currentText = text.substring(0, index);
                element.textContent = currentText;

                if (!isDeleting && index < text.length) {
                    index++;
                    setTimeout(type, 100);
                } else if (isDeleting && index > 0) {
                    index--;
                    setTimeout(type, 50);
                } else {
                    isDeleting = !isDeleting;
                    setTimeout(type, isDeleting ? 1000 : 500);
                }
            }

            type();
        }

        // Smooth scroll for internal links
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

        // Animate elements on scroll
        function animateOnScroll() {
            const elements = document.querySelectorAll('.project-card, .skill-item, .stat-item');
            
            const observer = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.style.opacity = '1';
                        entry.target.style.transform = 'translateY(0)';
                    }
                });
            }, {
                threshold: 0.1,
                rootMargin: '0px 0px -100px 0px'
            });

            elements.forEach(el => {
                el.style.opacity = '0';
                el.style.transform = 'translateY(30px)';
                el.style.transition = 'all 0.6s ease';
                observer.observe(el);
            });
        }

        // Initialize everything
        document.addEventListener('DOMContentLoaded', function() {
            createStars();
            typeWriter();
            animateOnScroll();
        });

        // Add parallax effect to header
        window.addEventListener('scroll', function() {
            const scrolled = window.pageYOffset;
            const header = document.querySelector('.header');
            const parallax = scrolled * 0.5;
            header.style.transform = `translateY(${parallax}px)`;
        });
    </script>
</body>
</html>
