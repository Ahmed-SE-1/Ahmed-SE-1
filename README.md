<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ahmed Ali - Full Stack Developer</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', 'Noto Sans', Helvetica, Arial, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            padding: 20px;
        }

        .readme-container {
            max-width: 1200px;
            margin: 0 auto;
            background: white;
            border-radius: 20px;
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.1);
            overflow: hidden;
            animation: fadeInUp 0.8s ease-out;
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .header {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 50px 40px;
            text-align: center;
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
            background: repeating-linear-gradient(
                45deg,
                transparent,
                transparent 10px,
                rgba(255, 255, 255, 0.05) 10px,
                rgba(255, 255, 255, 0.05) 20px
            );
            animation: shimmer 4s linear infinite;
        }

        @keyframes shimmer {
            0% { transform: translateX(-100px) translateY(-100px) rotate(45deg); }
            100% { transform: translateX(100px) translateY(100px) rotate(45deg); }
        }

        .developer-avatar {
            width: 120px;
            height: 120px;
            border-radius: 50%;
            background: rgba(255, 255, 255, 0.2);
            border: 4px solid rgba(255, 255, 255, 0.3);
            margin: 0 auto 20px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 3rem;
            backdrop-filter: blur(10px);
            position: relative;
            z-index: 2;
        }

        .developer-name {
            font-size: 3.5rem;
            font-weight: 700;
            margin-bottom: 10px;
            position: relative;
            z-index: 2;
        }

        .developer-title {
            font-size: 1.4rem;
            opacity: 0.9;
            margin-bottom: 20px;
            position: relative;
            z-index: 2;
        }

        .location {
            font-size: 1rem;
            opacity: 0.8;
            margin-bottom: 30px;
            position: relative;
            z-index: 2;
        }

        .badges {
            display: flex;
            justify-content: center;
            gap: 15px;
            flex-wrap: wrap;
            position: relative;
            z-index: 2;
        }

        .badge {
            padding: 10px 18px;
            background: rgba(255, 255, 255, 0.2);
            border: 1px solid rgba(255, 255, 255, 0.3);
            border-radius: 25px;
            font-size: 0.9rem;
            transition: all 0.3s ease;
            backdrop-filter: blur(10px);
        }

        .badge:hover {
            background: rgba(255, 255, 255, 0.3);
            transform: translateY(-3px);
        }

        .content {
            padding: 40px;
        }

        .nav-tabs {
            display: flex;
            border-bottom: 2px solid #f6f8fa;
            margin-bottom: 40px;
            overflow-x: auto;
        }

        .nav-tab {
            padding: 15px 25px;
            background: none;
            border: none;
            font-size: 1rem;
            font-weight: 500;
            color: #656d76;
            cursor: pointer;
            border-bottom: 3px solid transparent;
            transition: all 0.3s ease;
            white-space: nowrap;
        }

        .nav-tab.active {
            color: #667eea;
            border-bottom-color: #667eea;
        }

        .nav-tab:hover {
            color: #667eea;
        }

        .tab-content {
            display: none;
            animation: fadeIn 0.5s ease-in-out;
        }

        .tab-content.active {
            display: block;
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        .about-section {
            background: linear-gradient(135deg, #f8f9fa 0%, #e9ecef 100%);
            padding: 30px;
            border-radius: 15px;
            margin-bottom: 30px;
            border-left: 5px solid #667eea;
        }

        .about-text {
            font-size: 1.1rem;
            line-height: 1.8;
            color: #24292f;
            margin-bottom: 20px;
        }

        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 25px;
            margin: 30px 0;
        }

        .skill-category {
            background: white;
            border: 1px solid #e1e4e8;
            padding: 25px;
            border-radius: 15px;
            transition: all 0.3s ease;
            box-shadow: 0 2px 8px rgba(0, 0, 0, 0.05);
        }

        .skill-category:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 30px rgba(102, 126, 234, 0.1);
            border-color: #667eea;
        }

        .skill-title {
            font-size: 1.3rem;
            font-weight: 600;
            margin-bottom: 15px;
            color: #24292f;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .skill-icon {
            width: 40px;
            height: 40px;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            border-radius: 8px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.2rem;
        }

        .skill-tags {
            display: flex;
            flex-wrap: wrap;
            gap: 8px;
        }

        .skill-tag {
            background: #f1f3f4;
            color: #24292f;
            padding: 6px 12px;
            border-radius: 15px;
            font-size: 0.85rem;
            transition: all 0.3s ease;
        }

        .skill-tag:hover {
            background: #667eea;
            color: white;
            transform: scale(1.05);
        }

        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 25px;
            margin: 30px 0;
        }

        .project-card {
            background: white;
            border: 1px solid #e1e4e8;
            border-radius: 15px;
            padding: 25px;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .project-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 4px;
            background: linear-gradient(90deg, #667eea, #764ba2);
        }

        .project-card:hover {
            transform: translateY(-8px);
            box-shadow: 0 20px 40px rgba(102, 126, 234, 0.15);
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
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            border-radius: 10px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.5rem;
        }

        .project-title {
            font-size: 1.3rem;
            font-weight: 600;
            color: #24292f;
        }

        .project-description {
            color: #656d76;
            line-height: 1.6;
            margin-bottom: 15px;
        }

        .project-tech {
            display: flex;
            flex-wrap: wrap;
            gap: 6px;
            margin-bottom: 20px;
        }

        .tech-tag {
            background: #f1f3f4;
            color: #24292f;
            padding: 4px 8px;
            border-radius: 10px;
            font-size: 0.75rem;
        }

        .project-links {
            display: flex;
            gap: 10px;
        }

        .project-link {
            background: #667eea;
            color: white;
            padding: 8px 16px;
            border-radius: 8px;
            text-decoration: none;
            font-size: 0.85rem;
            transition: all 0.3s ease;
        }

        .project-link:hover {
            background: #5a6fd8;
            transform: translateY(-2px);
        }

        .contact-section {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 40px;
            border-radius: 15px;
            text-align: center;
            margin-top: 30px;
        }

        .contact-title {
            font-size: 2rem;
            margin-bottom: 20px;
        }

        .contact-links {
            display: flex;
            justify-content: center;
            gap: 20px;
            flex-wrap: wrap;
        }

        .contact-link {
            background: rgba(255, 255, 255, 0.2);
            color: white;
            padding: 12px 20px;
            border-radius: 25px;
            text-decoration: none;
            transition: all 0.3s ease;
            backdrop-filter: blur(10px);
        }

        .contact-link:hover {
            background: rgba(255, 255, 255, 0.3);
            transform: translateY(-3px);
        }

        .stats-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            margin: 30px 0;
        }

        .stat-card {
            background: white;
            border: 1px solid #e1e4e8;
            border-radius: 10px;
            padding: 20px;
            text-align: center;
            transition: all 0.3s ease;
        }

        .stat-card:hover {
            border-color: #667eea;
            box-shadow: 0 5px 15px rgba(102, 126, 234, 0.1);
        }

        .stat-number {
            font-size: 2rem;
            font-weight: 700;
            color: #667eea;
            display: block;
        }

        .stat-label {
            color: #656d76;
            font-size: 0.9rem;
            margin-top: 5px;
        }

        .learning-section {
            background: linear-gradient(135deg, #f8f9fa 0%, #e9ecef 100%);
            padding: 25px;
            border-radius: 15px;
            margin: 20px 0;
        }

        .learning-title {
            font-size: 1.5rem;
            font-weight: 600;
            color: #24292f;
            margin-bottom: 15px;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .learning-items {
            display: flex;
            flex-wrap: wrap;
            gap: 12px;
        }

        .learning-item {
            background: #667eea;
            color: white;
            padding: 8px 16px;
            border-radius: 20px;
            font-size: 0.9rem;
        }

        @media (max-width: 768px) {
            .developer-name {
                font-size: 2.5rem;
            }
            
            .badges {
                flex-direction: column;
                align-items: center;
            }
            
            .nav-tabs {
                flex-wrap: wrap;
            }
            
            .skills-grid,
            .projects-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <div class="readme-container">
        <div class="header">
            <div class="developer-avatar">👨‍💻</div>
            <h1 class="developer-name">Ahmed Ali</h1>
            <p class="developer-title">Full Stack Web Developer & Flutter/Dart Mobile App Developer</p>
            <p class="location">🇵🇰 Pakistan</p>
            <div class="badges">
                <span class="badge">🌐 Full Stack</span>
                <span class="badge">📱 Mobile Dev</span>
                <span class="badge">☁️ Cloud Tech</span>
                <span class="badge">🚀 MERN Stack</span>
            </div>
        </div>

        <div class="content">
            <nav class="nav-tabs">
                <button class="nav-tab active" onclick="showTab('about')">🏠 About</button>
                <button class="nav-tab" onclick="showTab('skills')">💻 Skills</button>
                <button class="nav-tab" onclick="showTab('projects')">🚀 Projects</button>
                <button class="nav-tab" onclick="showTab('learning')">📚 Learning</button>
                <button class="nav-tab" onclick="showTab('stats')">📊 Stats</button>
                <button class="nav-tab" onclick="showTab('contact')">📞 Contact</button>
            </nav>

            <div id="about" class="tab-content active">
                <div class="about-section">
                    <p class="about-text">
                        👋 Hi there! I'm Ahmed Ali, a passionate Full Stack Web Developer and Flutter/Dart Mobile App Developer 
                        from Pakistan, dedicated to creating innovative digital solutions that make a difference.
                    </p>
                    <p class="about-text">
                        💡 I believe coding is like solving puzzles - addictive and rewarding! Every line of code is an opportunity 
                        to create something amazing and solve real-world problems.
                    </p>
                    <p class="about-text">
                        🎯 My mission is to bridge the gap between complex technical solutions and user-friendly experiences, 
                        creating applications that are both powerful and intuitive.
                    </p>
                </div>

                <div class="learning-section">
                    <h3 class="learning-title">🌱 Currently Learning</h3>
                    <div class="learning-items">
                        <span class="learning-item">MERN Stack</span>
                        <span class="learning-item">DevOps</span>
                        <span class="learning-item">Cloud Technologies</span>
                        <span class="learning-item">Microservices</span>
                        <span class="learning-item">Kubernetes</span>
                    </div>
                </div>
            </div>

            <div id="skills" class="tab-content">
                <div class="skills-grid">
                    <div class="skill-category">
                        <h3 class="skill-title">
                            <div class="skill-icon">🌐</div>
                            Frontend Development
                        </h3>
                        <div class="skill-tags">
                            <span class="skill-tag">ReactJS</span>
                            <span class="skill-tag">NextJS</span>
                            <span class="skill-tag">JavaScript</span>
                            <span class="skill-tag">TypeScript</span>
                            <span class="skill-tag">HTML5</span>
                            <span class="skill-tag">CSS3</span>
                            <span class="skill-tag">Tailwind CSS</span>
                            <span class="skill-tag">Material-UI</span>
                        </div>
                    </div>
                    
                    <div class="skill-category">
                        <h3 class="skill-title">
                            <div class="skill-icon">⚙️</div>
                            Backend Development
                        </h3>
                        <div class="skill-tags">
                            <span class="skill-tag">NodeJS</span>
                            <span class="skill-tag">Express.js</span>
                            <span class="skill-tag">MongoDB</span>
                            <span class="skill-tag">PostgreSQL</span>
                            <span class="skill-tag">RESTful APIs</span>
                            <span class="skill-tag">GraphQL</span>
                            <span class="skill-tag">JWT Auth</span>
                        </div>
                    </div>
                    
                    <div class="skill-category">
                        <h3 class="skill-title">
                            <div class="skill-icon">📱</div>
                            Mobile Development
                        </h3>
                        <div class="skill-tags">
                            <span class="skill-tag">Flutter</span>
                            <span class="skill-tag">Dart</span>
                            <span class="skill-tag">Firebase</span>
                            <span class="skill-tag">State Management</span>
                            <span class="skill-tag">Native APIs</span>
                            <span class="skill-tag">Cross-Platform</span>
                        </div>
                    </div>
                    
                    <div class="skill-category">
                        <h3 class="skill-title">
                            <div class="skill-icon">☁️</div>
                            DevOps & Cloud
                        </h3>
                        <div class="skill-tags">
                            <span class="skill-tag">AWS</span>
                            <span class="skill-tag">Docker</span>
                            <span class="skill-tag">CI/CD</span>
                            <span class="skill-tag">GitHub Actions</span>
                            <span class="skill-tag">Vercel</span>
                            <span class="skill-tag">Netlify</span>
                        </div>
                    </div>
                </div>
            </div>

            <div id="projects" class="tab-content">
                <div class="projects-grid">
                    <div class="project-card">
                        <div class="project-header">
                            <div class="project-icon">🌐</div>
                            <h3 class="project-title">E-Commerce Platform</h3>
                        </div>
                        <p class="project-description">
                            Full-featured e-commerce platform with admin dashboard, payment integration, and real-time inventory management.
                        </p>
                        <div class="project-tech">
                            <span class="tech-tag">Next.js</span>
                            <span class="tech-tag">Node.js</span>
                            <span class="tech-tag">MongoDB</span>
                            <span class="tech-tag">Stripe</span>
                        </div>
                        <div class="project-links">
                            <a href="#" class="project-link">🔗 Live Demo</a>
                            <a href="#" class="project-link">📂 Code</a>
                        </div>
                    </div>
                    
                    <div class="project-card">
                        <div class="project-header">
                            <div class="project-icon">📱</div>
                            <h3 class="project-title">Fitness Tracker App</h3>
                        </div>
                        <p class="project-description">
                            Cross-platform mobile app for tracking workouts, nutrition, and fitness goals with social features.
                        </p>
                        <div class="project-tech">
                            <span class="tech-tag">Flutter</span>
                            <span class="tech-tag">Dart</span>
                            <span class="tech-tag">Firebase</span>
                            <span class="tech-tag">Bloc</span>
                        </div>
                        <div class="project-links">
                            <a href="#" class="project-link">📱 App Store</a>
                            <a href="#" class="project-link">📂 Code</a>
                        </div>
                    </div>
                    
                    <div class="project-card">
                        <div class="project-header">
                            <div class="project-icon">📊</div>
                            <h3 class="project-title">Business Analytics Dashboard</h3>
                        </div>
                        <p class="project-description">
                            Real-time analytics dashboard for business metrics with interactive charts and reporting features.
                        </p>
                        <div class="project-tech">
                            <span class="tech-tag">React</span>
                            <span class="tech-tag">D3.js</span>
                            <span class="tech-tag">Express</span>
                            <span class="tech-tag">PostgreSQL</span>
                        </div>
                        <div class="project-links">
                            <a href="#" class="project-link">🔗 Live Demo</a>
                            <a href="#" class="project-link">📂 Code</a>
                        </div>
                    </div>
                    
                    <div class="project-card">
                        <div class="project-header">
                            <div class="project-icon">🎓</div>
                            <h3 class="project-title">Learning Management System</h3>
                        </div>
                        <p class="project-description">
                            Complete LMS with course creation, student progress tracking, and interactive learning modules.
                        </p>
                        <div class="project-tech">
                            <span class="tech-tag">MERN</span>
                            <span class="tech-tag">Socket.io</span>
                            <span class="tech-tag">AWS S3</span>
                            <span class="tech-tag">JWT</span>
                        </div>
                        <div class="project-links">
                            <a href="#" class="project-link">🔗 Live Demo</a>
                            <a href="#" class="project-link">📂 Code</a>
                        </div>
                    </div>
                </div>
            </div>

            <div id="learning" class="tab-content">
                <div class="learning-section">
                    <h3 class="learning-title">🚀 Current Focus Areas</h3>
                    <p style="margin-bottom: 20px; color: #656d76;">
                        Continuously expanding my skillset to stay at the forefront of technology
                    </p>
                    <div class="skills-grid">
                        <div class="skill-category">
                            <h3 class="skill-title">
                                <div class="skill-icon">📚</div>
                                MERN Stack Mastery
                            </h3>
                            <p style="color: #656d76; margin-bottom: 15px;">
                                Deep diving into full-stack JavaScript development with MongoDB, Express, React, and Node.js
                            </p>
                            <div class="skill-tags">
                                <span class="skill-tag">Advanced React Patterns</span>
                                <span class="skill-tag">Node.js Performance</span>
                                <span class="skill-tag">MongoDB Aggregation</span>
                                <span class="skill-tag">Express Middleware</span>
                            </div>
                        </div>
                        
                        <div class="skill-category">
                            <h3 class="skill-title">
                                <div class="skill-icon">🛠️</div>
                                DevOps & Deployment
                            </h3>
                            <p style="color: #656d76; margin-bottom: 15px;">
                                Learning modern deployment strategies and infrastructure management
                            </p>
                            <div class="skill-tags">
                                <span class="skill-tag">Docker Containers</span>
                                <span class="skill-tag">CI/CD Pipelines</span>
                                <span class="skill-tag">AWS Services</span>
                                <span class="skill-tag">Monitoring & Logging</span>
                            </div>
                        </div>
                        
                        <div class="skill-category">
                            <h3 class="skill-title">
                                <div class="skill-icon">☁️</div>
                                Cloud Technologies
                            </h3>
                            <p style="color: #656d76; margin-bottom: 15px;">
                                Exploring cloud-native solutions and scalable architectures
                            </p>
                            <div class="skill-tags">
                                <span class="skill-tag">Serverless</span>
                                <span class="skill-tag">Microservices</span>
                                <span class="skill-tag">Kubernetes</span>
                                <span class="skill-tag">Cloud Functions</span>
                            </div>
                        </div>
                    </div>
                </div>
            </div>

            <div id="stats" class="tab-content">
                <div class="stats-container">
                    <div class="stat-card">
                        <span class="stat-number">50+</span>
                        <div class="stat-label">Projects Completed</div>
                    </div>
                    <div class="stat-card">
                        <span class="stat-number">3+</span>
                        <div class="stat-label">Years Experience</div>
                    </div>
                    <div class="stat-card">
                        <span class="stat-number">15+</span>
                        <div class="stat-label">Technologies</div>
                    </div>
                    <div class="stat-card">
                        <span class="stat-number">100%</span>
                        <div class="stat-label">Client Satisfaction</div>
                    </div>
                </div>
                
                <div class="learning-section" style="margin-top: 30px;">
                    <h3 class="learning-title">🏆 Key Achievements</h3>
                    <div class="skills-grid">
                        <div class="skill-category">
                            <h3 class="skill-title">
                                <div class="skill-icon">🚀</div>
                                Performance Excellence
                            </h3>
                            <p style="color: #656d76;">
                                Optimized applications achieving 90+ PageSpeed scores and sub-second load times
                            </p>
                        </div>
                        
                        <div class="skill-category">
                            <h3 class="skill-title">
                                <div class="skill-icon">📱</div>
                                Cross-Platform Success
                            </h3>
                            <p style="color: #656d76;">
                                Delivered mobile apps with 4.8+ star ratings on both iOS and Android platforms
                            </p>
                        </div>
                        
                        <div class="skill-category">
                            <h3 class="skill-title">
                                <div class="skill-icon">💼</div>
                                Business Impact
                            </h3>
                            <p style="color: #656d76;">
                                Helped businesses increase online revenue by 200%+ through optimized web solutions
                            </p>
                        </div>
                    </div>
                </div>
            </div>

            <div id="contact" class="tab-content">
                <div class="contact-section">
                    <h2 class="contact-title">Let's Connect! 🤝</h2>
                    <p style="margin-bottom: 30px; opacity: 0.9;">
                        Ready to bring your ideas to life? Let's discuss how we can work together!
                    </p>
                    <div class="contact-links">
                        <a href="mailto:abdullahmunir467.@gmail.com" class="contact-link">📧 Email</a>
                        <a href="https://abdullah-munir.vercel.app" class="contact-link">🌐 Portfolio</a>
                        <a href="#" class="contact-link">💼 LinkedIn</a>
                        <a href="#" class="contact-link">🐦 Twitter</a>
                        <a href="#" class="contact-link">📱 WhatsApp</a>
                    </div>
                </div>
                
                <div class="learning-section" style="margin-top: 30px;">
                    <h3 class="learning-title">💬 Let's Talk About</h3>
                    <div class="learning-items">
                        <span class="learning-item">ReactJS</span>
                        <span class="learning-item">NextJS</span>
                        <span class="learning-item">NodeJS</span>
                        <span class="learning-item">Flutter</span>
                        <span class="learning-item">MongoDB</span>
                        <span class="learning-item">Full Stack Development</span>
                        <span class="learning-item">Mobile App Development</span>
                        <span class="learning-item">Project Collaboration</span>
                    </div>
                </div>
                
                <div class="about-section" style="margin-top: 30px;">
                    <h3 style="font-size: 1.5rem; margin-bottom: 15px; color: #24292f;">⚡ Fun Fact</h3>
                    <p class="about-text" style="margin-bottom: 0;">
                        I think coding is like solving puzzles - addictive and rewarding! Every bug fixed and feature implemented 
                        feels like completing a challenging puzzle piece. 🧩✨
                    </p>
                </div>
            </div>
        </div>
    </div>

    <script>
        function showTab(tabName) {
            // Hide all tab contents
            const contents = document.querySelectorAll('.tab-content');
            contents.forEach(content => content.classList.remove('active'));
            
            // Remove active class from all tabs
            const tabs = document.querySelectorAll('.nav-tab');
            tabs.forEach(tab => tab.classList.remove('active'));
            
            // Show selected tab content
            document.getElementById(tabName).classList.add('active');
            
            // Add active class to clicked tab
            event.target.classList.add('active');
        }

        // Add interactive animations
        document.addEventListener('DOMContentLoaded', () => {
            // Skill tags hover effect
            const skillTags = document.querySelectorAll('.skill-tag');
            skillTags.forEach(tag => {
                tag.addEventListener('mouseenter', () => {
                    tag.style.transform = 'scale(1.1)';
                });
                
                tag.addEventListener('mouseleave', () => {
                    tag.style.transform = 'scale(1)';
                });
            });

            // Project cards interactive effect
            const projectCards = document.querySelectorAll('.project-card');
            projectCards.forEach(card => {
                card.addEventListener('mouseenter', () => {
                    card.style.transform = 'translateY(-10px) scale(1.02)';
                });
                
                card.addEventListener('mouseleave', () => {
                    card.style.transform = 'translateY(0) scale(1)';
                });
            });

            // Stat cards animation
            const statCards = document.querySelectorAll('.stat-card');
            statCards.forEach(card => {
                card.addEventListener('mouseenter', () => {
                    const number = card.querySelector('.stat-number');
                    number.style.transform = 'scale(1.2)';
                });
                
                card.addEventListener('mouseleave', () => {
                    const number = card.querySelector('.stat-number');
                    number.style.transform = 'scale(1)';
                });
            });

            // Learning items pulse effect
            const learningItems = document.querySelectorAll('.learning-item');
            learningItems.forEach((item, index) => {
                setTimeout(() => {
                    item.style.animation = `pulse 2s infinite ${index * 0.1}s`;
                }, index * 100);
            });

            // Avatar rotation on hover
            const avatar = document.querySelector('.developer-avatar');
            avatar.addEventListener('mouseenter', () => {
                avatar.style.transform = 'rotate(360deg) scale(1.1)';
            });
            
            avatar.addEventListener('mouseleave', () => {
                avatar.style.transform = 'rotate(0deg) scale(1)';
            });

            // Typing animation for developer title
            const title = document.querySelector('.developer-title');
            const originalText = title.textContent;
            let index = 0;
            
            function typeWriter() {
                if (index < originalText.length) {
                    title.textContent = originalText.substring(0, index + 1) + '|';
                    index++;
                    setTimeout(typeWriter, 100);
                } else {
                    title.textContent = originalText;
                    setTimeout(() => {
                        index = 0;
                        title.textContent = '';
                        setTimeout(typeWriter, 2000);
                    }, 3000);
                }
            }
            
            // Start typing animation after page load
            setTimeout(typeWriter, 1000);
        });

        // Add pulse animation keyframes
        const style = document.createElement('style');
        style.textContent = `
            @keyframes pulse {
                0% { transform: scale(1); }
                50% { transform: scale(1.05); }
                100% { transform: scale(1); }
            }
            
            @keyframes glow {
                0% { box-shadow: 0 0 5px rgba(102, 126, 234, 0.3); }
                50% { box-shadow: 0 0 20px rgba(102, 126, 234, 0.6); }
                100% { box-shadow: 0 0 5px rgba(102, 126, 234, 0.3); }
            }
            
            .skill-category:hover {
                animation: glow 2s infinite;
            }
            
            .project-card:hover {
                animation: glow 2s infinite;
            }
        `;
        document.head.appendChild(style);

        // Add smooth scrolling between sections
        function smoothScrollTo(element) {
            element.scrollIntoView({
                behavior: 'smooth',
                block: 'start'
            });
        }

        // Add random gradient colors to project icons
        const projectIcons = document.querySelectorAll('.project-icon');
        const gradients = [
            'linear-gradient(135deg, #667eea 0%, #764ba2 100%)',
            'linear-gradient(135deg, #f093fb 0%, #f5576c 100%)',
            'linear-gradient(135deg, #4facfe 0%, #00f2fe 100%)',
            'linear-gradient(135deg, #43e97b 0%, #38f9d7 100%)'
        ];

        projectIcons.forEach((icon, index) => {
            icon.style.background = gradients[index % gradients.length];
        });

        // Add progress bars for skills (visual enhancement)
        const skillCategories = document.querySelectorAll('.skill-category');
        skillCategories.forEach(category => {
            const progressBar = document.createElement('div');
            progressBar.style.cssText = `
                width: 0%;
                height: 3px;
                background: linear-gradient(90deg, #667eea, #764ba2);
                border-radius: 2px;
                margin-top: 15px;
                transition: width 2s ease-in-out;
            `;
            category.appendChild(progressBar);
            
            // Animate progress bar on hover
            category.addEventListener('mouseenter', () => {
                progressBar.style.width = '100%';
            });
            
            category.addEventListener('mouseleave', () => {
                progressBar.style.width = '0%';
            });
        });

        // Add floating particles effect to header
        function createParticle() {
            const particle = document.createElement('div');
            particle.style.cssText = `
                position: absolute;
                width: 4px;
                height: 4px;
                background: rgba(255, 255, 255, 0.3);
                border-radius: 50%;
                pointer-events: none;
                animation: float ${Math.random() * 3 + 2}s linear infinite;
                left: ${Math.random() * 100}%;
                top: 100%;
            `;
            
            document.querySelector('.header').appendChild(particle);
            
            setTimeout(() => {
                particle.remove();
            }, 5000);
        }

        // Create particles periodically
        setInterval(createParticle, 300);

        // Add float animation
        const floatStyle = document.createElement('style');
        floatStyle.textContent = `
            @keyframes float {
                0% {
                    transform: translateY(0px) rotate(0deg);
                    opacity: 1;
                }
                100% {
                    transform: translateY(-100vh) rotate(360deg);
                    opacity: 0;
                }
            }
        `;
        document.head.appendChild(floatStyle);
    </script>
</body>
</html>
