<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Lizette Rodriguez - Astrophysics Portfolio</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <style>
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
        height: 70px;
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
        scroll-margin-top: 80px;
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

    /* CV/Resume Section */
    .cv-section {
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
        gap: 2rem;
        margin-top: 2rem;
    }

    .cv-card {
        background: rgba(26, 26, 46, 0.6);
        border: 1px solid rgba(138, 43, 226, 0.3);
        border-radius: 15px;
        padding: 2.5rem;
        text-align: center;
        transition: all 0.3s ease;
        backdrop-filter: blur(10px);
    }

    .cv-card:hover {
        transform: translateY(-10px);
        border-color: rgba(138, 43, 226, 0.8);
        box-shadow: 0 15px 40px rgba(138, 43, 226, 0.2);
    }

    .cv-card i {
        font-size: 3rem;
        color: #8a2be2;
        margin-bottom: 1.5rem;
    }

    .cv-card h3 {
        color: #8a2be2;
        margin-bottom: 1rem;
        font-size: 1.5rem;
    }

    .cv-card p {
        margin-bottom: 2rem;
        opacity: 0.9;
    }

    .download-btn {
        display: inline-block;
        padding: 0.8rem 2rem;
        background: linear-gradient(45deg, #8a2be2, #4169e1);
        color: white;
        text-decoration: none;
        border-radius: 25px;
        transition: all 0.3s ease;
        font-weight: bold;
    }

    .download-btn:hover {
        transform: translateY(-2px);
        box-shadow: 0 8px 25px rgba(138, 43, 226, 0.4);
    }

    .download-btn i {
        margin-right: 0.5rem;
        font-size: 1rem;
    }

    /* Media Portfolio Section */
    .media-grid {
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
        gap: 2rem;
        margin-top: 2rem;
    }

    .media-item {
        background: rgba(26, 26, 46, 0.6);
        border: 1px solid rgba(138, 43, 226, 0.3);
        border-radius: 15px;
        overflow: hidden;
        transition: all 0.3s ease;
        backdrop-filter: blur(10px);
    }

    .media-item:hover {
        transform: translateY(-10px);
        border-color: rgba(138, 43, 226, 0.8);
        box-shadow: 0 15px 40px rgba(138, 43, 226, 0.2);
    }

    .media-preview {
        height: 200px;
        background: linear-gradient(45deg, #1a1a2e, #16213e);
        display: flex;
        align-items: center;
        justify-content: center;
        position: relative;
        overflow: hidden;
    }

    .media-preview img {
        width: 100%;
        height: 100%;
        object-fit: cover;
        transition: transform 0.3s ease;
    }

    .media-preview:hover img {
        transform: scale(1.1);
    }

    .media-placeholder {
        font-size: 3rem;
        color: #8a2be2;
        opacity: 0.5;
    }

    .media-content {
        padding: 1.5rem;
    }

    .media-content h3 {
        color: #8a2be2;
        margin-bottom: 0.5rem;
        font-size: 1.3rem;
    }

    .media-content .media-type {
        color: #4169e1;
        font-size: 0.9rem;
        font-weight: bold;
        margin-bottom: 1rem;
        text-transform: uppercase;
        letter-spacing: 1px;
    }

    .media-content p {
        margin-bottom: 1.5rem;
        opacity: 0.9;
        font-size: 0.95rem;
    }

    .media-actions {
        display: flex;
        gap: 1rem;
        flex-wrap: wrap;
    }

    .media-btn {
        padding: 0.6rem 1.2rem;
        border-radius: 20px;
        text-decoration: none;
        font-size: 0.9rem;
        font-weight: bold;
        transition: all 0.3s ease;
        flex: 1;
        text-align: center;
        min-width: 100px;
    }

    .view-btn {
        background: linear-gradient(45deg, #8a2be2, #4169e1);
        color: white;
    }

    .view-btn:hover {
        transform: translateY(-2px);
        box-shadow: 0 8px 25px rgba(138, 43, 226, 0.4);
    }

    .download-btn-small {
        background: transparent;
        color: #8a2be2;
        border: 2px solid #8a2be2;
    }

    .download-btn-small:hover {
        background: #8a2be2;
        color: white;
        transform: translateY(-2px);
    }

    /* Filter buttons for media */
    .media-filters {
        display: flex;
        justify-content: center;
        gap: 1rem;
        margin-bottom: 2rem;
        flex-wrap: wrap;
    }

    .filter-btn {
        padding: 0.8rem 1.5rem;
        background: transparent;
        border: 2px solid rgba(138, 43, 226, 0.5);
        color: #ffffff;
        border-radius: 25px;
        cursor: pointer;
        transition: all 0.3s ease;
        font-weight: bold;
    }

    .filter-btn:hover,
    .filter-btn.active {
        background: linear-gradient(45deg, #8a2be2, #4169e1);
        border-color: transparent;
        transform: translateY(-2px);
    }

    /* Modal for viewing media */
    .media-modal {
        display: none;
        position: fixed;
        z-index: 2000;
        left: 0;
        top: 0;
        width: 100%;
        height: 100%;
        background-color: rgba(0, 0, 0, 0.9);
        backdrop-filter: blur(10px);
    }

    .modal-content {
        position: relative;
        margin: 2% auto;
        padding: 20px;
        width: 90%;
        max-width: 800px;
        background: rgba(26, 26, 46, 0.95);
        border-radius: 15px;
        border: 1px solid rgba(138, 43, 226, 0.3);
    }

    .close-modal {
        color: #aaa;
        float: right;
        font-size: 28px;
        font-weight: bold;
        cursor: pointer;
        transition: color 0.3s ease;
    }

    .close-modal:hover {
        color: #8a2be2;
    }

    .modal-media {
        width: 100%;
        max-height: 600px;
        object-fit: contain;
        border-radius: 10px;
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
        
        .cv-section,
        .media-grid {
            grid-template-columns: 1fr;
        }
        
        .media-filters {
            flex-direction: column;
            align-items: center;
        }
        
        .media-actions {
            flex-direction: column;
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
    <!-- Animated background stars -->
    <div class="stars" id="stars"></div>

    <!-- Navigation -->
    <nav>
        <div class="nav-container">
            <ul class="nav-links">
                <li><a href="#home">Home</a></li>
                <li><a href="#about">About</a></li>
                <li><a href="#research">Research</a></li>
                <li><a href="#cv">CV & Resume</a></li>
                <li><a href="#portfolio">Portfolio</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </div>
    </nav>

    <!-- Hero Section -->
    <section id="home" class="hero">
        <div class="hero-content">
            <h1>Lizette Rodriguez</h1>
            <p>Astrophysics Research Student | Computational Physics | Space Science</p>
            <a href="#about" class="cta-button">Explore My Research</a>
        </div>
        
        <!-- Constellation background -->
        <div class="constellation">
            <svg viewBox="0 0 400 400">
                <defs>
                    <filter id="glow">
                        <feGaussianBlur stdDeviation="3" result="coloredBlur"/>
                        <feMerge> 
                            <feMergeNode in="coloredBlur"/>
                            <feMergeNode in="SourceGraphic"/>
                        </feMerge>
                    </filter>
                </defs>
                <!-- Constellation lines -->
                <line x1="50" y1="80" x2="120" y2="60" stroke="#8a2be2" stroke-width="1" opacity="0.5"/>
                <line x1="120" y1="60" x2="180" y2="100" stroke="#8a2be2" stroke-width="1" opacity="0.5"/>
                <line x1="180" y1="100" x2="220" y2="150" stroke="#8a2be2" stroke-width="1" opacity="0.5"/>
                <line x1="220" y1="150" x2="280" y2="120" stroke="#8a2be2" stroke-width="1" opacity="0.5"/>
                <!-- Stars -->
                <circle cx="50" cy="80" r="2" fill="white" filter="url(#glow)"/>
                <circle cx="120" cy="60" r="3" fill="white" filter="url(#glow)"/>
                <circle cx="180" cy="100" r="2" fill="white" filter="url(#glow)"/>
                <circle cx="220" cy="150" r="4" fill="white" filter="url(#glow)"/>
                <circle cx="280" cy="120" r="2" fill="white" filter="url(#glow)"/>
            </svg>
        </div>
    </section>

    <!-- About Section -->
    <section id="about" class="fade-in">
        <h2 class="section-title">About Me</h2>
        <div class="about-content">
            <div class="profile-image">
                <img src="images/profile-photo.jpg" alt="Lizette Rodriguez">
                <!-- Replace with: <img src="your-photo.jpg" alt="Your Name"> -->
            </div>
            <div>
                <p>Lizette Rodriguez is a fourth-year student at UTSA, majoring in physics with a minor in astronomy. She conducts research in planetary nebulae, with her latest focus on utilizing the Chandra X-ray Telescope to perform computational astrophysics on observation NGC 6543, also known as the Cat's Eye Nebula. Her primary job is to determine how to best use a clustering algorithm called DBSCAN (Density-Based Spatial Clustering of Applications with Noise) to analyze high-energy X-rays emitted from the Cat's Eye Nebula. 
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

    <!-- Research Section -->
    <section id="research" class="fade-in">
        <h2 class="section-title">Research</h2>
        <div class="research-grid">
            <div class="research-card">
                <h3>X-ray Analysis of NGC 6543</h3>
                <p>Utilizing the Chandra X-ray Telescope to perform computational astrophysics on the Cat's Eye Nebula, applying DBSCAN clustering algorithms to analyze high-energy X-ray emissions and understand the complex structure of this planetary nebula.</p>
            </div>
            
            <div class="research-card">
                <h3>Open Cluster Analysis with Gaia Data</h3>
                <p>Developing a comprehensive research pipeline using Gaia DR3 data to improve the census of local stellar clusters through statistical methods, dimensionality reduction techniques, and advanced visualization tools.</p>
            </div>
            
            <div class="research-card">
                <h3>Radio Astronomy & Interference Analysis</h3>
                <p>Investigating astrophysical radio applications using SDRs and antenna arrays to better understand and mitigate interference in astronomical observations, contributing to improved data quality in radio astronomy.</p>
            </div>
            
            <div class="research-card">
                <h3>CubeSat Mission Development</h3>
                <p>Contributing to a student-led NASA initiative program involving the design and implementation of CubeSat missions, focusing on collaborative engineering solutions and space-based scientific instrumentation.</p>
            </div>
        </div>
    </section>

    <!-- CV & Resume Section -->
    <section id="cv" class="fade-in">
        <h2 class="section-title">CV & Resume</h2>
        <div class="cv-section">
            <div class="cv-card">
                <i class="fas fa-file-alt"></i>
                <h3>Curriculum Vitae</h3>
                <p>Comprehensive academic CV including research experience, publications, presentations, and academic achievements in astrophysics and computational physics.</p>
                <a href="documents/Lizette_Rodriguez_CV.pdf" class="download-btn" target="_blank">
                    <i class="fas fa-download"></i>Download CV
                </a>
            </div>
            
            <div class="cv-card">
                <i class="fas fa-briefcase"></i>
                <h3>Professional Resume</h3>
                <p>Industry-focused resume highlighting technical skills, research projects, programming experience, and leadership roles suitable for career opportunities.</p>
                <a href="documents/Lizette_Rodriguez_Resume.pdf" class="download-btn" target="_blank">
                    <i class="fas fa-download"></i>Download Resume
                </a>
            </div>
        </div>
    </section>

    <!-- Media Portfolio Section -->
    <section id="portfolio" class="fade-in">
        <h2 class="section-title">Research Portfolio</h2>
        
        <!-- Filter buttons -->
        <div class="media-filters">
            <button class="filter-btn active" data-filter="all">All</button>
            <button class="filter-btn" data-filter="posters">Posters</button>
            <button class="filter-btn" data-filter="papers">Papers</button>
            <button class="filter-btn" data-filter="presentations">Presentations</button>
        </div>

        <div class="media-grid">
            <!-- AAS 2025 Research Poster -->
            <div class="media-item" data-category="posters">
                <div class="media-preview">
                    <img src="Screenshot 2025-08-23 at 20.52.25.png" alt="Cat's Eye Nebula Research Poster">
                </div>
                <div class="media-content">
                    <h3>Applying Clustering Algorithms to X-ray Emission from Planetary Nebulae</h3>
                    <div class="media-type">Research Poster</div>
                    <p>Computational astrophysics poster presenting DBSCAN clustering analysis of Chandra X-ray observations. Presented at American Astronomical Society (AAS) Symposium January 2025.</p>
                    <div class="media-actions">
                        <a href="https://aas245-aas.ipostersessions.com/default.aspx?s=98-BA-5E-50-15-C0-D8-FD-4E-49-0B-7D-B5-AC-BA-80&guestview=true" class="media-btn view-btn" target="_blank">
                            <i class="fas fa-eye"></i> View
                        </a>
                        <a href="aas (iPosterSessions - an aMuze! Interactive system).pdf" class="media-btn download-btn-small" target="_blank">
                            <i class="fas fa-download"></i> Download
                        </a>
                    </div>
                </div>
            </div>

            <!-- UTSA Spring Research Poster -->
            <div class="media-item" data-category="posters">
                <div class="media-preview">
                    <img src="1Poster_Template.pdf" alt="Cat's Eye Nebula Research Poster">
                </div>
                <div class="media-content">
                    <h3>Understanding Clustering Algorithm Applied to Planetary Nebulae</h3>
                    <div class="media-type">Research Poster</div>
                    <p>Computational astrophysics poster presenting a parameter study of DBSCAN clustering analysis of Chandra X-ray observations. Presented at UTSA Research Symposium Spring 2025.</p>
                    <div class="media-actions">
                        <a href="1Poster_Template.pdf" class="media-btn download-btn-small" target="_blank">
                            <i class="fas fa-download"></i> Download
                        </a>
                    </div>
                </div>
            </div>

            <!-- Microwave Research Poster -->
            <div class="media-item" data-category="posters">
                <div class="media-preview">
                    <img src="Screenshot 2025-08-23 at 23.48.52.png" alt="Microwave Research Poster">
                </div>
                <div class="media-content">
                    <h3>Microwave and Millimeter-Wave Systems: Propagation Studies at 5G Wireless Bands</h3>
                    <div class="media-type">Research Poster</div>
                    <p>Computational astrophysics poster presenting behavioral analysis of 5G wireless bands using signal generators, spectrum analyzers, and HyperLog® antennas. Presented at American Astronomical Society (AAS) Symposium January 2024.</p>
                    <div class="media-actions">
                        <a href="https://aas243-aas.ipostersessions.com/Default.aspx?s=7D-A1-6B-81-B9-9D-83-63-AE-22-7F-7E-4D-B9-C2-38" class="media-btn view-btn" target="_blank">
                            <i class="fas fa-eye"></i> View
                        </a>
                        <a href="1aas (iPosterSessions - an aMuze! Interactive system).pdf" class="media-btn download-btn-small" target="_blank">
                            <i class="fas fa-download"></i> Download
                        </a>
                    </div>
                </div>
            </div>

            <!-- Research Paper: Clustering Algorithms -->
            <div class="media-item" data-category="papers">
                <div class="media-preview">
                    <img src="Understanding_Clustering_Algorithm_Applied_to_Planetary_Nebulae-6.pdf" alt="Cat's Eye Nebula Research Poster">
                </div>
                <div class="media-content">
                    <h3>Understanding Clustering Algorithm Applied to Planetary Nebulae</h3>
                    <div class="media-type">Research Paper</div>
                    <p>The parameter study research paper that reviews the results of in-depth analysis of the most robust parameters of DBSCAN clustering analysis of Chandra X-ray observations.</p>
                    <div class="media-actions">
                        <a href="Understanding_Clustering_Algorithm_Applied_to_Planetary_Nebulae-6.pdf" class="media-btn download-btn-small" target="_blank">
                            <i class="fas fa-download"></i> Download
                        </a>
                    </div>
                </div>
            </div>
            
            <!-- Research Paper: Microwave Systems -->
            <div class="media-item" data-category="papers">
                <div class="media-preview">
                    <img src="Microwave_and_Millimeter_Wave_Systems__Propagation_Studies_at_5G_Wireless_Bands.pdf" alt="Cat's Eye Nebula Research Poster">
                </div>
                <div class="media-content">
                    <h3>Microwave and Millimeter-Wave Systems: Propagation Studies at 5G Wireless Bands</h3>
                    <div class="media-type">Research Paper</div>
                    <p>This research paper investigated wave propagation characteristics at millimeter-wave frequencies under varying environmental conditions.</p>
                    <div class="media-actions">
                        <a href="Microwave_and_Millimeter_Wave_Systems__Propagation_Studies_at_5G_Wireless_Bands.pdf" class="media-btn download-btn-small" target="_blank">
                            <i class="fas fa-download"></i> Download
                        </a>
                    </div>
                </div>
            </div>

            <!-- Research Paper: MEEPsat -->
            <div class="media-item" data-category="papers">
                <div class="media-preview">
                    <img src="Final Proposal Draft.pdf" alt="Cat's Eye Nebula Research Poster">
                </div>
                <div class="media-content">
                    <h3>MEEPsat (Methane Emissions from Permafrost Satellite Tracker)</h3>
                    <div class="media-type">Research Paper</div>
                    <p>Co-authored MEEPsat, a CubeSat mission proposal submitted to NASA, in collaboration with three UTSA student organizations; designed to monitor methane emissions over the North Pole and raise public awareness of climate change.</p>
                    <div class="media-actions">
                        <a href="Final Proposal Draft.pdf" class="media-btn download-btn-small" target="_blank">
                            <i class="fas fa-download"></i> Download
                        </a>
                    </div>
                </div>
            </div>

            <!-- Presentation: CfA Research -->
            <div class="media-item" data-category="presentations">
                <div class="media-preview">
                    <img src="1CREATE_PRES_24.pdf" alt="Cat's Eye Nebula Research Poster">
                </div>
                <div class="media-content">
                    <h3>Applying Clustering Algorithms to X-ray Emission from Planetary Nebulae</h3>
                    <div class="media-type">Presentation</div>
                    <p>Computational astrophysics poster presenting DBSCAN clustering analysis of Chandra X-ray observations. Presented at Center for Astrophysics August (CfA) 2025.</p>
                    <div class="media-actions">
                        <a href="1CREATE_PRES_24.pdf" class="media-btn download-btn-small" target="_blank">
                            <i class="fas fa-download"></i> Download
                        </a>
                    </div>
                </div>
            </div>

            <!-- Presentation: AI in Astronomy -->
            <div class="media-item" data-category="presentations">
                <div class="media-preview">
                    <img src="Adobe presentation.pdf" alt="Cat's Eye Nebula Research Poster">
                </div>
                <div class="media-content">
                    <h3>Astronomy 3013 AI Assignment 2</h3>
                    <div class="media-type">Presentation</div>
                    <p>A presentation given to educators during the Digital Literacy Cafe on the impact of AI and its implications in astronomy. Presented at the Digital Literacy Cafe showcase in April 2025.</p>
                    <div class="media-actions">
                        <a href="https://www.adobeforeducation.com/higher-ed/events/digital-literacy-cafe-series" class="media-btn view-btn" target="_blank">
                            <i class="fas fa-eye"></i> View
                        </a>
                        <a href="Adobe presentation.pdf" class="media-btn download-btn-small" target="_blank">
                            <i class="fas fa-download"></i> Download
                        </a>
                    </div>
                </div>
            </div>
            
            <!-- Presentation: REU Experiences -->
            <div class="media-item" data-category="presentations">
                <div class="media-preview">
                    <img src="Force in Space Education Presentation in Black White Hand Drawn Lightly Textured Style-4.pdf" alt="Cat's Eye Nebula Research Poster">
                </div>
                <div class="media-content">
                    <h3>HOW MY WORK IN ASTROPHYSICS TAUGHT ME EVERYTHING I KNOW</h3>
                    <div class="media-type">Presentation</div>
                    <p>A comprehensive timeline of all past REU experiences. Presented at the Roadrunner Experience Showcase UTSA November 2024.</p>
                    <div class="media-actions">
                        <a href="Force in Space Education Presentation in Black White Hand Drawn Lightly Textured Style-4.pdf" class="media-btn download-btn-small" target="_blank">
                            <i class="fas fa-download"></i> Download
                        </a>
                    </div>
                </div>
            </div>

            <!-- Presentation: Microwave Final -->
            <div class="media-item" data-category="presentations">
                <div class="media-preview">
                    <img src="TemplateFinalPresentation.pdf" alt="Cat's Eye Nebula Research Poster">
                </div>
                <div class="media-content">
                    <h3>Microwave and Millimeter-wave Systems: Propagation studies at 5G Wireless Bands</h3>
                    <div class="media-type">Presentation</div>
                    <p>A final presentation summarizing all the results from a multiphase experiment focused on radio astronomy interference. Presented at the University of Puerto Rico, Mayaguez, August 2023.</p>
                    <div class="media-actions">
                        <a href="TemplateFinalPresentation.pdf" class="media-btn download-btn-small" target="_blank">
                            <i class="fas fa-download"></i> Download
                        </a>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="fade-in">
        <h2 class="section-title">Contact</h2>
        <div class="contact-info">
            <div class="contact-item">
                <i class="fas fa-envelope"></i>
                <h3>Email</h3>
                <p>lizette.rodriguez@my.utsa.edu</p>
            </div>
            
            <div class="contact-item">
                <i class="fab fa-linkedin"></i>
                <h3>LinkedIn</h3>
                <p>Connect with me professionally</p>
            </div>
            
            <div class="contact-item">
                <i class="fab fa-github"></i>
                <h3>GitHub</h3>
                <p>View my code repositories</p>
            </div>
        </div>
    </section>

    <!-- Modal for viewing images -->
    <div id="mediaModal" class="media-modal">
        <div class="modal-content">
            <span class="close-modal">&times;</span>
            <img class="modal-media" id="modalImage" src="" alt="">
        </div>
    </div>

    <script>
        // Create animated stars
        function createStars() {
            const starsContainer = document.getElementById('stars');
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

        // Portfolio filtering
        function initPortfolioFilter() {
            const filterBtns = document.querySelectorAll('.filter-btn');
            const mediaItems = document.querySelectorAll('.media-item');

            filterBtns.forEach(btn => {
                btn.addEventListener('click', () => {
                    // Remove active class from all buttons
                    filterBtns.forEach(b => b.classList.remove('active'));
                    // Add active class to clicked button
                    btn.classList.add('active');
                    
                    const filter = btn.getAttribute('data-filter');
