<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title> Lizette Rodriguez - Physics & Astronomy Undergraduate </title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Arial', sans-serif;
            background: #0a0a0f;
            color: #ffffff;
            overflow-x: hidden;
            line-height: 1.6;
        }

        /* Animated background stars */
        .stars {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
        }

        .star {
            position: absolute;
            width: 2px;
            height: 2px;
            background: white;
            border-radius: 50%;
            animation: twinkle 3s infinite;
        }

        @keyframes twinkle {
            0%, 100% { opacity: 0.3; }
            50% { opacity: 1; }
        }

        /* Navigation */
        nav {
            position: fixed;
            top: 0;
            width: 100%;
            padding: 1rem 2rem;
            background: rgba(10, 10, 15, 0.9);
            backdrop-filter: blur(20px);
            z-index: 1000;
            border-bottom: 1px solid rgba(138, 43, 226, 0.3);
            height: 70px; /* Fixed height for consistent spacing */
            display: flex;
            align-items: center;
        }

        .nav-container {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            justify-content: center;
            align-items: center;
        }

        .logo {
            font-size: 1.5rem;
            font-weight: bold;
            background: linear-gradient(45deg, #8a2be2, #4169e1);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .nav-links {
            display: flex;
            list-style: none;
            gap: 2rem;
        }

        .nav-links a {
            color: #ffffff;
            text-decoration: none;
            transition: all 0.3s ease;
            position: relative;
        }

        .nav-links a:hover {
            color: #8a2be2;
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background: linear-gradient(45deg, #8a2be2, #4169e1);
            transition: width 0.3s ease;
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        /* Hero Section */
        .hero {
            height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            position: relative;
        }

        .hero-content {
            max-width: 800px;
            z-index: 2;
        }

        .hero h1 {
            font-size: 3.5rem;
            margin-bottom: 1rem;
            background: linear-gradient(45deg, #ffffff, #8a2be2, #4169e1);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            animation: fadeInUp 1s ease-out;
        }

        .hero p {
            font-size: 1.2rem;
            margin-bottom: 2rem;
            opacity: 0.9;
            animation: fadeInUp 1s ease-out 0.3s both;
        }

        .cta-button {
            display: inline-block;
            padding: 1rem 2rem;
            background: linear-gradient(45deg, #8a2be2, #4169e1);
            text-decoration: none;
            color: white;
            border-radius: 50px;
            transition: all 0.3s ease;
            animation: fadeInUp 1s ease-out 0.6s both;
        }

        .cta-button:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 30px rgba(138, 43, 226, 0.4);
        }

        /* Constellation background */
        .constellation {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            width: 600px;
            height: 600px;
            opacity: 0.1;
        }

        .constellation svg {
            width: 100%;
            height: 100%;
            animation: rotate 60s linear infinite;
        }

        @keyframes rotate {
            from { transform: rotate(0deg); }
            to { transform: rotate(360deg); }
        }

        /* Sections */
        section {
            padding: 5rem 2rem;
            max-width: 1200px;
            margin: 0 auto;
            scroll-margin-top: 80px; /* Offset for fixed navbar */
        }

        .section-title {
            font-size: 2.5rem;
            text-align: center;
            margin-bottom: 3rem;
            background: linear-gradient(45deg, #8a2be2, #4169e1);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        /* About Section */
        .about-content {
            display: grid;
            grid-template-columns: 1fr 2fr;
            gap: 3rem;
            align-items: center;
        }

        .profile-image {
            width: 250px;
            height: 250px;
            border-radius: 50%;
            background: linear-gradient(45deg, #8a2be2, #4169e1);
            padding: 4px;
            margin: 0 auto;
        }

        .profile-image img {
            width: 100%;
            height: 100%;
            border-radius: 50%;
            object-fit: cover;
        }

        .profile-placeholder {
            width: 100%;
            height: 100%;
            background: #1a1a2e;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 4rem;
            color: #8a2be2;
        }

        /* Research Cards */
        .research-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin-top: 2rem;
        }

        .research-card {
            background: rgba(26, 26, 46, 0.6);
            border: 1px solid rgba(138, 43, 226, 0.3);
            border-radius: 15px;
            padding: 2rem;
            transition: all 0.3s ease;
            backdrop-filter: blur(10px);
        }

        .research-card:hover {
            transform: translateY(-10px);
            border-color: rgba(138, 43, 226, 0.8);
            box-shadow: 0 15px 40px rgba(138, 43, 226, 0.2);
        }

        .research-card h3 {
            color: #8a2be2;
            margin-bottom: 1rem;
        }

        /* Contact Section */
        .contact-info {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            text-align: center;
        }

        .contact-item {
            padding: 2rem;
            background: rgba(26, 26, 46, 0.6);
            border-radius: 15px;
            border: 1px solid rgba(138, 43, 226, 0.3);
            transition: all 0.3s ease;
        }

        .contact-item:hover {
            border-color: rgba(138, 43, 226, 0.8);
            transform: translateY(-5px);
        }

        .contact-item i {
            font-size: 2rem;
            color: #8a2be2;
            margin-bottom: 1rem;
        }

        /* Animations */
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

        .fade-in {
            opacity: 0;
            animation: fadeInUp 1s ease-out forwards;
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .hero h1 {
                font-size: 2.5rem;
            }
            
            .nav-links {
                display: none;
            }
            
            .about-content {
                grid-template-columns: 1fr;
                text-align: center;
            }
            
            section {
                padding: 3rem 1rem;
            }
        }

        /* Scroll indicator */
        .scroll-indicator {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 3px;
            background: linear-gradient(90deg, #8a2be2, #4169e1);
            transform-origin: left;
            transform: scaleX(0);
            z-index: 1001;
        }
    </style>
</head>
<body>
    <div class="scroll-indicator"></div>
    <div class="stars"></div>

    <nav>
        <div class="nav-container">
            <ul class="nav-links">
                <li><a href="#home">Home</a></li>
                <li><a href="#about">About</a></li>
                <li><a href="#research">Research</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </div>
    </nav>

    <section id="home" class="hero">
        <div class="constellation">
            <svg viewBox="0 0 600 600">
                <circle cx="100" cy="100" r="2" fill="rgba(138, 43, 226, 0.8)"/>
                <circle cx="200" cy="150" r="2" fill="rgba(138, 43, 226, 0.8)"/>
                <circle cx="300" cy="120" r="2" fill="rgba(138, 43, 226, 0.8)"/>
                <circle cx="400" cy="180" r="2" fill="rgba(138, 43, 226, 0.8)"/>
                <circle cx="150" cy="250" r="2" fill="rgba(138, 43, 226, 0.8)"/>
                <circle cx="350" cy="280" r="2" fill="rgba(138, 43, 226, 0.8)"/>
                <circle cx="450" cy="320" r="2" fill="rgba(138, 43, 226, 0.8)"/>
                <circle cx="250" cy="400" r="2" fill="rgba(138, 43, 226, 0.8)"/>
                <circle cx="180" cy="450" r="2" fill="rgba(138, 43, 226, 0.8)"/>
                
                <line x1="100" y1="100" x2="200" y2="150" stroke="rgba(138, 43, 226, 0.3)" stroke-width="1"/>
                <line x1="200" y1="150" x2="300" y2="120" stroke="rgba(138, 43, 226, 0.3)" stroke-width="1"/>
                <line x1="300" y1="120" x2="400" y2="180" stroke="rgba(138, 43, 226, 0.3)" stroke-width="1"/>
                <line x1="150" y1="250" x2="350" y2="280" stroke="rgba(138, 43, 226, 0.3)" stroke-width="1"/>
                <line x1="350" y1="280" x2="450" y2="320" stroke="rgba(138, 43, 226, 0.3)" stroke-width="1"/>
                <line x1="250" y1="400" x2="180" y2="450" stroke="rgba(138, 43, 226, 0.3)" stroke-width="1"/>
            </svg>
        </div>
        <div class="hero-content">
            <h1>Your Name</h1>
            <p>Physics Undergraduate | Astronomy Enthusiast | Future Researcher</p>
            <a href="#about" class="cta-button">Explore My Universe</a>
        </div>
    </section>

    <section id="about" class="fade-in">
        <h2 class="section-title">About Me</h2>
        <div class="about-content">
            <div class="profile-image">
            <img src="lizette.rodriguez.jpg" alt="Lizette Rodriguez">
            </div>
            <div>
                <p>Lizette Rodriguez is a fourth-year student at UTSA, majoring in physics with a minor in astronomy. She conducts research in planetary nebulae, with her latest focus on utilizing the Chandra X-ray Telescope to perform computational astrophysics on observation NGC 6543, also known as the Cat’s Eye Nebula. Her primary job is to determine how to best use a clustering algorithm called DBSCAN (Density-Based Spatial Clustering of Applications with Noise) to analyze high-energy X-rays emitted from the Cat’s Eye Nebula. 
                In addition to this, Lizette is actively developing a research pipeline centered on open cluster analysis with Gaia data, where she applies statistical methods, dimensionality reduction techniques, and visualization tools to improve the census of local clusters. This work builds on her broader interest in algorithmic applications to astrophysical datasets and connects computational theory with observational evidence.
                In the past, she has participated in other research involving astrophysical radio applications, which included using instrumentation such as antennas and SDRs to better understand phenomena like interference. This experience also allowed her to contribute to a student-led NASA initiative program named CubeSat, a unique collaboration between multiple student organizations, one of which she currently serves as an officer.
                Beyond research, Lizette volunteers for outreach with SPS (Society of Physics Students), where she shares her passion for astronomy and works to make science more accessible to the community.
                </p>
                <br>
                <p>Currently pursuing my degree in Physics with a focus on astrophysics, I'm particularly interested in stellar evolution, exoplanet detection, and cosmological phenomena. I believe that through scientific inquiry, we can unlock the secrets of the universe and expand humanity's understanding of our place in the cosmos.</p>
                <br>
                <p>When I'm not studying or conducting research, you can find me at the local observatory, participating in astronomy clubs, or working on computational models of celestial mechanics.</p>
            </div>
        </div>
    </section>

    <section id="research" class="fade-in">
        <h2 class="section-title">Research & Projects</h2>
        <div class="research-grid">
            <div class="research-card">
                <h3>Stellar Classification Analysis</h3>
                <p>Developing machine learning algorithms to classify stellar spectra and identify unique stellar populations in our galaxy. This project combines computational physics with observational astronomy data.</p>
            </div>
            <div class="research-card">
                <h3>Exoplanet Transit Modeling</h3>
                <p>Creating predictive models for exoplanet transit events using Python and astronomical databases. Focus on identifying potentially habitable worlds in nearby star systems.</p>
            </div>
            <div class="research-card">
                <h3>Dark Matter Simulation</h3>
                <p>Undergraduate research project simulating dark matter interactions in galactic halos using N-body computational methods and comparing results with observational data.</p>
            </div>
            <div class="research-card">
                <h3>Radio Astronomy Data Analysis</h3>
                <p>Processing and analyzing radio telescope data to study pulsars and their magnetic field structures. Collaboration with the local radio astronomy facility.</p>
            </div>
        </div>
    </section>

    <section id="contact" class="fade-in">
        <h2 class="section-title">Get In Touch</h2>
        <div class="contact-info">
            <div class="contact-item">
                <div style="font-size: 2rem; color: #8a2be2; margin-bottom: 1rem;">✉️</div>
                <h3>Email</h3>
                <p>lizette.rodriguez@my.utsa.edu</p>
            </div>
            <div class="contact-item">
                <div style="font-size: 2rem; color: #8a2be2; margin-bottom: 1rem;">🔗</div>
                <h3>LinkedIn</h3>
                <p>www.linkedin.com/in/lizette-rodriguez-295b5b24b</p>
            </div>
            <div class="contact-item">
                <div style="font-size: 2rem; color: #8a2be2; margin-bottom: 1rem;">📚</div>
                <h3>GitHub</h3>
                <p>lizetterod</p>
            </div>
        </div>
    </section>

    <script>
        // Create animated stars
        function createStars() {
            const starsContainer = document.querySelector('.stars');
            const numStars = 100;
            
            for (let i = 0; i < numStars; i++) {
                const star = document.createElement('div');
                star.className = 'star';
                star.style.left = Math.random() * 100 + '%';
                star.style.top = Math.random() * 100 + '%';
                star.style.animationDelay = Math.random() * 3 + 's';
                starsContainer.appendChild(star);
            }
        }

        // Scroll progress indicator
        function updateScrollProgress() {
            const scrollTop = window.pageYOffset;
            const docHeight = document.body.scrollHeight - window.innerHeight;
            const scrollPercent = scrollTop / docHeight;
            document.querySelector('.scroll-indicator').style.transform = `scaleX(${scrollPercent})`;
        }

        // Smooth scrolling for navigation links
        function initSmoothScrolling() {
            document.querySelectorAll('a[href^="#"]').forEach(anchor => {
                anchor.addEventListener('click', function (e) {
                    e.preventDefault();
                    const target = document.querySelector(this.getAttribute('href'));
                    if (target) {
                        const offsetTop = target.offsetTop - 70; // Account for fixed navbar
                        window.scrollTo({
                            top: offsetTop,
                            behavior: 'smooth'
                        });
                    }
                });
            });
        }

        // Intersection Observer for fade-in animations
        function initFadeInAnimation() {
            const observer = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.style.animationPlayState = 'running';
                    }
                });
            }, { threshold: 0.1 });

            document.querySelectorAll('.fade-in').forEach(el => {
                el.style.animationPlayState = 'paused';
                observer.observe(el);
            });
        }

        // Initialize everything
        document.addEventListener('DOMContentLoaded', function() {
            createStars();
            initSmoothScrolling();
            initFadeInAnimation();
        });

        window.addEventListener('scroll', updateScrollProgress);
    </script>
</body>
</html>
