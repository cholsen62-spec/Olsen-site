# Olsen-site
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Olsen World • Univers Créatif</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.6.0/css/all.min.css">
    <style>
        :root {
            --primary: #c026d3;
            --secondary: #7c3aed;
            --accent: #f472b6;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Segoe UI', system-ui, sans-serif;
            background: radial-gradient(circle at 50% 20%, #2a1b4a 0%, #0f071f 40%, #000 80%);
            color: #e0d9ff;
            overflow-x: hidden;
            line-height: 1.6;
        }

        /* Background Particles */
        #particles {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            opacity: 0.6;
        }

        /* Navigation */
        nav {
            position: fixed;
            top: 0;
            width: 100%;
            z-index: 1000;
            padding: 20px 5%;
            display: flex;
            justify-content: space-between;
            align-items: center;
            background: rgba(15, 7, 31, 0.85);
            backdrop-filter: blur(16px);
            border-bottom: 1px solid rgba(192, 38, 211, 0.2);
            transition: all 0.4s ease;
        }
        
        .logo {
            font-size: 1.8rem;
            font-weight: 800;
            background: linear-gradient(90deg, var(--primary), var(--accent));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        
        .nav-links {
            display: flex;
            gap: 40px;
        }
        
        .nav-links a {
            color: #e0d9ff;
            text-decoration: none;
            font-weight: 500;
            transition: all 0.3s ease;
            position: relative;
        }
        
        .nav-links a::after {
            content: '';
            position: absolute;
            width: 0;
            height: 2px;
            bottom: -6px;
            left: 0;
            background: linear-gradient(90deg, var(--primary), var(--accent));
            transition: width 0.4s ease;
        }
        
        .nav-links a:hover::after {
            width: 100%;
        }

        /* Mobile Menu */
        .mobile-menu {
            display: none;
            font-size: 1.8rem;
            cursor: pointer;
        }

        /* Hero */
        .hero {
            height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            position: relative;
        }
        
        .hero-content {
            z-index: 2;
            max-width: 900px;
            padding: 0 20px;
        }
        
        .hero h1 {
            font-size: clamp(3.5rem, 8vw, 7rem);
            font-weight: 900;
            line-height: 1.05;
            margin-bottom: 20px;
            background: linear-gradient(90deg, #e0d9ff, #c026d3, #f472b6);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            text-shadow: 0 0 60px rgba(192, 38, 211, 0.5);
        }
        
        .hero p {
            font-size: 1.5rem;
            margin-bottom: 40px;
            opacity: 0.9;
            max-width: 600px;
            margin-left: auto;
            margin-right: auto;
        }
        
        .btn {
            padding: 16px 40px;
            font-size: 1.2rem;
            font-weight: 600;
            border-radius: 50px;
            background: linear-gradient(90deg, var(--primary), var(--accent));
            color: white;
            text-decoration: none;
            display: inline-flex;
            align-items: center;
            gap: 12px;
            transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
            box-shadow: 0 10px 30px rgba(192, 38, 211, 0.4);
        }
        
        .btn:hover {
            transform: translateY(-8px) scale(1.05);
            box-shadow: 0 20px 40px rgba(192, 38, 211, 0.6);
        }

        /* Sections */
        section {
            padding: 120px 5%;
            max-width: 1100px;
            margin: 0 auto;
        }
        
        h2 {
            font-size: 3.2rem;
            text-align: center;
            margin-bottom: 60px;
            background: linear-gradient(90deg, var(--primary), var(--accent));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        /* Cards */
        .card {
            background: rgba(255, 255, 255, 0.06);
            border-radius: 24px;
            padding: 40px;
            margin-bottom: 30px;
            border: 1px solid rgba(192, 38, 211, 0.15);
            transition: all 0.5s ease;
            backdrop-filter: blur(12px);
        }
        
        .card:hover {
            transform: translateY(-15px);
            border-color: rgba(192, 38, 211, 0.4);
            box-shadow: 0 25px 50px rgba(0, 0, 0, 0.4);
        }

        /* Projects Grid */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(340px, 1fr));
            gap: 30px;
        }
        
        .project-card {
            height: 420px;
            border-radius: 24px;
            overflow: hidden;
            position: relative;
            background: linear-gradient(145deg, #1f1138, #120a22);
            border: 1px solid rgba(192, 38, 211, 0.2);
        }
        
        .project-img {
            height: 55%;
            background-size: cover;
            background-position: center;
            position: relative;
        }
        
        .project-overlay {
            position: absolute;
            inset: 0;
            background: linear-gradient(transparent, rgba(0,0,0,0.9));
            display: flex;
            align-items: flex-end;
            padding: 30px;
            transition: all 0.4s ease;
        }
        
        .project-card:hover .project-overlay {
            padding-bottom: 40px;
        }
        
        .project-info h3 {
            font-size: 1.6rem;
            margin-bottom: 8px;
        }

        /* Contact */
        .contact-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 30px;
        }
        
        .social-link {
            display: flex;
            align-items: center;
            gap: 20px;
            padding: 25px;
            background: rgba(255,255,255,0.05);
            border-radius: 20px;
            text-decoration: none;
            color: inherit;
            transition: all 0.4s ease;
        }
        
        .social-link:hover {
            background: rgba(192, 38, 211, 0.15);
            transform: translateX(15px);
        }

        /* Footer */
        footer {
            text-align: center;
            padding: 60px 20px 40px;
            border-top: 1px solid rgba(192, 38, 211, 0.15);
            font-size: 0.95rem;
            opacity: 0.7;
        }

        /* Scroll animations */
        .reveal {
            opacity: 0;
            transform: translateY(60px);
            transition: all 1s cubic-bezier(0.25, 0.1, 0.25, 1);
        }
        
        .reveal.active {
            opacity: 1;
            transform: translateY(0);
        }
    </style>
</head>
<body>
    <!-- Background Particles -->
    <canvas id="particles"></canvas>

    <!-- Navigation -->
    <nav>
        <div class="logo">Olsen World</div>
        <div class="nav-links">
            <a href="#home">Accueil</a>
            <a href="#about">À propos</a>
            <a href="#projects">Projets</a>
            <a href="#contact">Contact</a>
        </div>
        <div class="mobile-menu">☰</div>
    </nav>

    <!-- Hero -->
    <section id="home" class="hero">
        <div class="hero-content">
            <h1>OLSEN WORLD</h1>
            <p>Un univers personnel où les idées prennent vie, où la créativité n'a pas de limites.</p>
            <a href="#about" class="btn">
                Explorer l'univers 
                <i class="fas fa-arrow-down"></i>
            </a>
        </div>
    </section>

    <!-- About -->
    <section id="about">
        <h2>Mon Histoire</h2>
        <div class="card reveal">
            <p style="font-size: 1.25rem;">
                Je suis <strong>Olsen</strong>, créateur, rêveur et bâtisseur d'univers.<br><br>
                Ce site est bien plus qu'un portfolio : c'est mon espace de liberté créative. 
                Ici, je partage mes passions, mes projets, mes réflexions et tout ce qui me fait vibrer.
            </p>
        </div>
    </section>

    <!-- Projects -->
    <section id="projects">
        <h2>Créations &amp; Projets</h2>
        <div class="projects-grid">
            
            <div class="project-card reveal">
                <div class="project-img" style="background-image: url('https://picsum.photos/id/1015/800/600')"></div>
                <div class="project-overlay">
                    <div class="project-info">
                        <h3>Univers Visuel</h3>
                        <p>Photographie • Vidéographie • Motion Design</p>
                    </div>
                </div>
            </div>
            
            <div class="project-card reveal">
                <div class="project-img" style="background-image: url('https://picsum.photos/id/201/800/600')"></div>
                <div class="project-overlay">
                    <div class="project-info">
                        <h3>Contenu TikTok / Reels</h3>
                        <p>Séries créatives • Storytelling visuel</p>
                    </div>
                </div>
            </div>
            
            <div class="project-card reveal">
                <div class="project-img" style="background-image: url('https://picsum.photos/id/237/800/600')"></div>
                <div class="project-overlay">
                    <div class="project-info">
                        <h3>Écriture &amp; Idées</h3>
                        <p>Scénarios • Poésie • Réflexions</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact -->
    <section id="contact">
        <h2>Restons Connectés</h2>
        <div class="contact-grid">
            <a href="#" class="social-link card reveal">
                <i class="fab fa-tiktok" style="font-size: 2.8rem; color: #ff0050;"></i>
                <div>
                    <strong>TikTok</strong><br>
                    <span>@tonpseudo</span>
                </div>
            </a>
            
            <a href="#" class="social-link card reveal">
                <i class="fab fa-instagram" style="font-size: 2.8rem; color: #e1306c;"></i>
                <div>
                    <strong>Instagram</strong><br>
                    <span>@tonpseudo</span>
                </div>
            </a>
            
            <a href="#" class="social-link card reveal">
                <i class="fab fa-youtube" style="font-size: 2.8rem; color: #ff0000;"></i>
                <div>
                    <strong>YouTube</strong><br>
                    <span>@olsenworld</span>
                </div>
            </a>
        </div>
    </section>

    <footer>
        © 2026 Olsen World — Tous droits réservés<br>
        Fait avec passion et un peu de magie violette ✨
    </footer>

    <script>
        // Simple Particle Background
        const canvas = document.getElementById('particles');
        const ctx = canvas.getContext('2d');
        
        let particles = [];
        
        function resizeCanvas() {
            canvas.width = window.innerWidth;
            canvas.height = window.innerHeight;
        }
        
        class Particle {
            constructor() {
                this.x = Math.random() * canvas.width;
                this.y = Math.random() * canvas.height;
                this.size = Math.random() * 3 + 0.5;
                this.speedX = Math.random() * 0.5 - 0.25;
                this.speedY = Math.random() * 0.5 - 0.25;
            }
            
            update() {
                this.x += this.speedX;
                this.y += this.speedY;
                
                if (this.x < 0 || this.x > canvas.width) this.speedX *= -1;
                if (this.y < 0 || this.y > canvas.height) this.speedY *= -1;
            }
            
            draw() {
                ctx.fillStyle = 'rgba(192, 38, 211, 0.7)';
                ctx.beginPath();
                ctx.arc(this.x, this.y, this.size, 0, Math.PI * 2);
                ctx.fill();
            }
        }
        
        function initParticles() {
            particles = [];
            for (let i = 0; i < 120; i++) {
                particles.push(new Particle());
            }
        }
        
        function animateParticles() {
            ctx.clearRect(0, 0, canvas.width, canvas.height);
            
            for (let i = 0; i < particles.length; i++) {
                particles[i].update();
                particles[i].draw();
            }
            requestAnimationFrame(animateParticles);
        }
        
        // Smooth Scroll
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function(e) {
                if (this.getAttribute('href') !== '#') {
                    e.preventDefault();
                    const target = document.querySelector(this.getAttribute('href'));
                    if (target) {
                        target.scrollIntoView({
                            behavior: 'smooth'
                        });
                    }
                }
            });
        });
        
        // Reveal on scroll
        function revealOnScroll() {
            const reveals = document.querySelectorAll('.reveal');
            reveals.forEach(reveal => {
                const windowHeight = window.innerHeight;
                const revealTop = reveal.getBoundingClientRect().top;
                if (revealTop < windowHeight - 100) {
                    reveal.classList.add('active');
                }
            });
        }
        
        // Init everything
        window.addEventListener('load', () => {
            resizeCanvas();
            initParticles();
            animateParticles();
            revealOnScroll();
        });
        
        window.addEventListener('resize', () => {
            resizeCanvas();
        });
        
        window.addEventListener('scroll', revealOnScroll);
        
        // Mobile menu (you can expand this)
        console.log("%cOlsen World chargé avec succès ✨", "color:#c026d3; font-size:14px; font-weight:bold");
    </script>
</body>
</html>
