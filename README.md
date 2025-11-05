[johanna_portfolio (3).html](https://github.com/user-attachments/files/23373504/johanna_portfolio.3.html)
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Johanna Rodriguez - Portfolio</title>
    <style>
        /* ===== COLOR THEME - EDIT THESE! ===== */
        :root {
            --primary: #9B7EDE;        /* Purple - Main brand color */
            --secondary: #FD79A8;      /* Pink - Accent color */
            --accent: #FDCB6E;         /* Gold - Highlight color */
            --bg-dark: #0F0F0F;        /* Background */
            --text-light: #FFFFFF;     /* White text */
            --text-gray: rgba(255,255,255,0.7);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
            background: var(--bg-dark);
            color: var(--text-light);
            overflow-x: hidden;
        }

        /* ===== NAVIGATION ===== */
        .nav {
            position: fixed;
            top: 0;
            width: 100%;
            padding: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 100;
            background: #1a1a1a;
        }

        .nav-links {
            display: flex;
            gap: 0;
        }

        .nav-links a {
            color: var(--text-gray);
            text-decoration: none;
            font-size: 1rem;
            font-weight: 500;
            padding: 1.5rem 3rem;
            transition: all 0.3s;
            border-bottom: 3px solid transparent;
        }

        .nav-links a:hover,
        .nav-links a.active {
            color: var(--text-light);
            background: rgba(155, 126, 222, 0.1);
            border-bottom-color: var(--primary);
        }

        /* ===== PAGE SECTIONS ===== */
        .page-section {
            display: none;
            min-height: 100vh;
            padding-top: 5rem;
        }

        .page-section.active {
            display: block;
        }

        /* ===== HERO ===== */
        .hero {
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            padding: 6rem 2rem 4rem;
            position: relative;
            overflow: hidden;
        }

        .hero::before {
            content: '';
            position: absolute;
            width: 600px;
            height: 600px;
            background: radial-gradient(circle, var(--primary) 0%, transparent 70%);
            opacity: 0.15;
            top: -200px;
            left: -200px;
            animation: float 20s ease-in-out infinite;
        }

        .hero::after {
            content: '';
            position: absolute;
            width: 500px;
            height: 500px;
            background: radial-gradient(circle, var(--secondary) 0%, transparent 70%);
            opacity: 0.15;
            bottom: -150px;
            right: -150px;
            animation: float 25s ease-in-out infinite reverse;
        }

        @keyframes float {
            0%, 100% { transform: translate(0, 0); }
            50% { transform: translate(100px, -100px); }
        }

        .hero-content {
            text-align: center;
            z-index: 2;
            max-width: 1000px;
        }

        .hero h1 {
            font-size: clamp(3rem, 10vw, 8rem);
            font-weight: 900;
            line-height: 0.95;
            margin-bottom: 2rem;
            background: linear-gradient(135deg, var(--primary) 0%, var(--secondary) 50%, var(--accent) 100%);
            -webkit-background-clip: text;
            background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .hero-tagline {
            font-size: clamp(1.1rem, 2vw, 1.5rem);
            color: var(--text-gray);
            margin-bottom: 3rem;
            line-height: 1.6;
        }

        .cta-btn {
            display: inline-block;
            padding: 1.2rem 3rem;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            color: white;
            text-decoration: none;
            border-radius: 50px;
            font-weight: 600;
            font-size: 1rem;
            transition: all 0.3s;
            box-shadow: 0 10px 30px rgba(155, 126, 222, 0.3);
        }

        .cta-btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 15px 40px rgba(155, 126, 222, 0.5);
        }

        /* ===== SECTIONS ===== */
        .section {
            padding: 6rem 2rem;
            max-width: 1400px;
            margin: 0 auto;
        }

        .section-title {
            font-size: clamp(2.5rem, 6vw, 4.5rem);
            font-weight: 900;
            margin-bottom: 4rem;
            text-align: center;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            -webkit-background-clip: text;
            background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        /* ===== STATS (UPDATED DESIGN) ===== */
        .stats-section {
            padding: 6rem 2rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 2rem;
        }

        .stat-card {
            background: #1a1a1a;
            padding: 3rem 2rem;
            border-radius: 20px;
            text-align: center;
            border: 1px solid rgba(255,255,255,0.1);
            transition: all 0.3s;
        }

        .stat-card:hover {
            transform: translateY(-10px);
            border-color: var(--primary);
            box-shadow: 0 20px 40px rgba(155, 126, 222, 0.2);
        }

        .stat-number {
            font-size: 4rem;
            font-weight: 900;
            color: var(--primary);
            margin-bottom: 1rem;
        }

        .stat-label {
            color: var(--text-gray);
            font-size: 1.1rem;
        }

        /* ===== PROJECTS GRID ===== */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 2.5rem;
        }

        .project-card {
            background: rgba(255,255,255,0.03);
            border-radius: 20px;
            overflow: hidden;
            border: 1px solid rgba(255,255,255,0.1);
            transition: all 0.4s;
            cursor: pointer;
        }

        .project-card:hover {
            transform: translateY(-10px);
            border-color: var(--primary);
            box-shadow: 0 20px 60px rgba(155, 126, 222, 0.3);
        }

        .project-image {
            height: 250px;
            background: linear-gradient(135deg, var(--primary) 0%, var(--secondary) 100%);
            display: flex;
            align-items: center;
            justify-content: center;
            position: relative;
            overflow: hidden;
        }

        .project-card:nth-child(1) .project-image { background: linear-gradient(135deg, #A29BFE 0%, #6C5CE7 100%); }
        .project-card:nth-child(2) .project-image { background: linear-gradient(135deg, #FD79A8 0%, #E84393 100%); }
        .project-card:nth-child(3) .project-image { background: linear-gradient(135deg, #FDCB6E 0%, #F39C12 100%); }
        .project-card:nth-child(4) .project-image { background: linear-gradient(135deg, #74B9FF 0%, #0984E3 100%); }
        .project-card:nth-child(5) .project-image { background: linear-gradient(135deg, #55EFC4 0%, #00B894 100%); }
        .project-card:nth-child(6) .project-image { background: linear-gradient(135deg, #FF7675 0%, #D63031 100%); }

        .project-icon {
            font-size: 4rem;
            font-weight: 900;
            opacity: 0.3;
            color: white;
        }

        .project-content {
            padding: 2rem;
        }

        .project-title {
            font-size: 1.5rem;
            font-weight: 700;
            margin-bottom: 0.5rem;
        }

        .project-meta {
            color: var(--secondary);
            font-size: 0.9rem;
            font-weight: 600;
            margin-bottom: 1rem;
        }

        .project-desc {
            color: var(--text-gray);
            line-height: 1.6;
            font-size: 0.95rem;
        }

        .click-hint {
            margin-top: 1rem;
            color: var(--primary);
            font-size: 0.85rem;
            font-weight: 600;
        }

        /* ===== ABOUT SECTION WITH IMAGE UPLOAD ===== */
        .about-container {
            max-width: 1200px;
            margin: 0 auto;
        }

        .about-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 5rem;
            align-items: start;
            margin-bottom: 6rem;
        }

        .about-text {
            font-size: 1.1rem;
            line-height: 1.8;
            color: var(--text-gray);
        }

        .about-text p {
            margin-bottom: 1.5rem;
        }

        .about-text strong {
            color: var(--primary);
            font-weight: 700;
        }

        /* ===== IMAGE UPLOAD AREAS ===== */
        .image-upload-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 1.5rem;
        }

        .image-placeholder {
            aspect-ratio: 3/4;
            background: rgba(255,255,255,0.05);
            border: 2px dashed rgba(255,255,255,0.2);
            border-radius: 15px;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            color: var(--text-gray);
            font-size: 0.9rem;
            text-align: center;
            padding: 2rem;
            transition: all 0.3s;
        }

        .image-placeholder:hover {
            border-color: var(--primary);
            background: rgba(155, 126, 222, 0.1);
        }

        .image-placeholder span {
            font-size: 3rem;
            margin-bottom: 1rem;
        }

        /* ===== FUN FACTS ===== */
        .funfacts-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin-top: 3rem;
        }

        .funfact-card {
            background: rgba(255,255,255,0.05);
            padding: 2rem;
            border-radius: 15px;
            border: 1px solid rgba(255,255,255,0.1);
            text-align: center;
        }

        .funfact-card .emoji {
            font-size: 3rem;
            margin-bottom: 1rem;
        }

        .funfact-card p {
            color: var(--text-gray);
            line-height: 1.6;
        }

        /* ===== CERTIFICATIONS ===== */
        .cert-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 2rem;
        }

        .cert-card {
            aspect-ratio: 3/4;
            background: rgba(255,255,255,0.05);
            border: 2px dashed rgba(255,255,255,0.2);
            border-radius: 15px;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            padding: 2rem;
            text-align: center;
            transition: all 0.3s;
        }

        .cert-card:hover {
            border-color: var(--primary);
            background: rgba(155, 126, 222, 0.1);
        }

        .cert-card span {
            font-size: 3rem;
            margin-bottom: 1rem;
        }

        .cert-card p {
            color: var(--text-gray);
            font-size: 0.9rem;
        }

        /* ===== SKILLS ===== */
        .skills-container {
            display: flex;
            flex-wrap: wrap;
            gap: 1.5rem;
            justify-content: center;
            max-width: 1000px;
            margin: 0 auto;
        }

        .skill-pill {
            padding: 1rem 2rem;
            background: rgba(255,255,255,0.05);
            border: 2px solid rgba(255,255,255,0.1);
            border-radius: 50px;
            font-weight: 600;
            font-size: 1rem;
            transition: all 0.3s;
            cursor: pointer;
        }

        .skill-pill:hover {
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            border-color: transparent;
            transform: translateY(-3px) scale(1.05);
            box-shadow: 0 10px 25px rgba(155, 126, 222, 0.3);
        }

        /* ===== MODAL ===== */
        .modal {
            display: none;
            position: fixed;
            z-index: 1000;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            background: rgba(0,0,0,0.9);
            animation: fadeIn 0.3s;
        }

        .modal.active {
            display: flex;
            align-items: center;
            justify-content: center;
            padding: 2rem;
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        .modal-content {
            background: var(--bg-dark);
            border: 1px solid rgba(255,255,255,0.1);
            border-radius: 20px;
            max-width: 900px;
            width: 100%;
            max-height: 90vh;
            overflow-y: auto;
            position: relative;
            animation: slideUp 0.3s;
        }

        @keyframes slideUp {
            from { transform: translateY(50px); opacity: 0; }
            to { transform: translateY(0); opacity: 1; }
        }

        .modal-header {
            padding: 3rem 3rem 2rem;
            border-bottom: 1px solid rgba(255,255,255,0.1);
        }

        .modal-header h2 {
            font-size: 2.5rem;
            margin-bottom: 0.5rem;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            -webkit-background-clip: text;
            background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .modal-header .meta {
            color: var(--secondary);
            font-weight: 600;
        }

        .modal-body {
            padding: 3rem;
        }

        .modal-section {
            margin-bottom: 3rem;
        }

        .modal-section h3 {
            font-size: 1.5rem;
            margin-bottom: 1rem;
            color: var(--primary);
        }

        .modal-section p, .modal-section ul {
            color: var(--text-gray);
            line-height: 1.8;
            font-size: 1rem;
        }

        .modal-section ul {
            list-style: none;
            padding-left: 0;
        }

        .modal-section li {
            padding: 0.5rem 0;
            padding-left: 1.5rem;
            position: relative;
        }

        .modal-section li:before {
            content: "→";
            position: absolute;
            left: 0;
            color: var(--primary);
        }

        .media-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 1.5rem;
            margin-top: 1.5rem;
        }

        .media-item {
            aspect-ratio: 16/9;
            background: rgba(255,255,255,0.05);
            border-radius: 10px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--text-gray);
            font-size: 0.9rem;
            border: 2px dashed rgba(255,255,255,0.2);
        }

        .close-modal {
            position: absolute;
            top: 2rem;
            right: 2rem;
            font-size: 2rem;
            color: var(--text-gray);
            cursor: pointer;
            background: none;
            border: none;
            width: 40px;
            height: 40px;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: all 0.3s;
        }

        .close-modal:hover {
            color: var(--primary);
            transform: rotate(90deg);
        }

        /* ===== CONTACT ===== */
        .contact-section {
            padding: 8rem 2rem;
            text-align: center;
        }

        .contact-section h2 {
            font-size: clamp(2.5rem, 6vw, 5rem);
            font-weight: 900;
            margin-bottom: 2rem;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            -webkit-background-clip: text;
            background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .contact-text {
            font-size: 1.2rem;
            color: var(--text-gray);
            max-width: 700px;
            margin: 0 auto 3rem;
            line-height: 1.8;
        }

        .contact-buttons {
            display: flex;
            gap: 1.5rem;
            justify-content: center;
            flex-wrap: wrap;
        }

        .contact-btn {
            padding: 1.2rem 2.5rem;
            font-size: 1rem;
            font-weight: 700;
            border-radius: 50px;
            text-decoration: none;
            transition: all 0.3s;
        }

        .btn-primary {
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            color: white;
            border: none;
        }

        .btn-primary:hover {
            transform: translateY(-3px);
            box-shadow: 0 15px 35px rgba(155, 126, 222, 0.4);
        }

        .btn-secondary {
            background: transparent;
            color: var(--primary);
            border: 2px solid var(--primary);
        }

        .btn-secondary:hover {
            background: var(--primary);
            color: white;
        }

        /* ===== RESPONSIVE ===== */
        @media (max-width: 968px) {
            .nav-links a {
                padding: 1.2rem 1.5rem;
                font-size: 0.9rem;
            }

            .about-grid {
                grid-template-columns: 1fr;
                gap: 3rem;
            }

            .image-upload-grid {
                grid-template-columns: 1fr;
            }

            .projects-grid {
                grid-template-columns: 1fr;
            }

            .modal-content {
                margin: 1rem;
            }

            .modal-header, .modal-body {
                padding: 2rem;
            }

            .media-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <!-- ========== NAVIGATION ========== -->
    <nav class="nav">
        <div class="nav-links">
            <a href="#" onclick="showPage('home')" class="active">Home</a>
            <a href="#" onclick="showPage('work')">Work</a>
            <a href="#" onclick="showPage('about')">About</a>
            <a href="#" onclick="showPage('skills')">Skills</a>
            <a href="#" onclick="showPage('contact')">Contact</a>
        </div>
    </nav>

    <!-- ========== HOME PAGE ========== -->
    <div id="home" class="page-section active">
        <section class="hero">
            <div class="hero-content">
                <h1>JOHANNA RODRIGUEZ</h1>
                <p class="hero-tagline">
                    Strategic communicator • Data storyteller • Partnership builder<br>
                    Transforming insights into impact, from Santiago to Boston and beyond.
                </p>
                <a href="#" onclick="showPage('work')" class="cta-btn">View My Work</a>
            </div>
        </section>
    </div>

    <!-- ========== WORK PAGE ========== -->
    <div id="work" class="page-section">
        <section class="section">
            <h2 class="section-title">Featured Work</h2>
            <div class="projects-grid">
                
                <div class="project-card" onclick="openModal('modal1')">
                    <div class="project-image">
                        <div class="project-icon">DFX</div>
                    </div>
                    <div class="project-content">
                        <h3 class="project-title">Strategic Partnerships</h3>
                        <p class="project-meta">DFX • Summer 2025</p>
                        <p class="project-desc">Built partnerships with JP Morgan, Fidelity, and Silicon Valley Bank. Generated 300+ qualified B2B leads.</p>
                        <p class="click-hint">Click to see details →</p>
                    </div>
                </div>

                <div class="project-card" onclick="openModal('modal2')">
                    <div class="project-image">
                        <div class="project-icon">VIZ</div>
                    </div>
                    <div class="project-content">
                        <h3 class="project-title">Influencer Analytics</h3>
                        <p class="project-meta">Vizsense • Fall 2024</p>
                        <p class="project-desc">Optimized campaigns with 4-8% engagement rates, driving 20% boost in audience engagement.</p>
                        <p class="click-hint">Click to see details →</p>
                    </div>
                </div>

                <div class="project-card" onclick="openModal('modal3')">
                    <div class="project-image">
                        <div class="project-icon">$$</div>
                    </div>
                    <div class="project-content">
                        <h3 class="project-title">Market Expansion</h3>
                        <p class="project-meta">Brunks Industries • Summer 2024</p>
                        <p class="project-desc">Analyzed competitor pricing and developed financial models for strategic growth.</p>
                        <p class="click-hint">Click to see details →</p>
                    </div>
                </div>

                <div class="project-card" onclick="openModal('modal4')">
                    <div class="project-image">
                        <div class="project-icon">HB</div>
                    </div>
                    <div class="project-content">
                        <h3 class="project-title">Gen Z Marketing</h3>
                        <p class="project-meta">Hugo Boss • Fall 2023</p>
                        <p class="project-desc">Developed digital engagement strategies targeting Gen Z demographics.</p>
                        <p class="click-hint">Click to see details →</p>
                    </div>
                </div>

                <div class="project-card" onclick="openModal('modal5')">
                    <div class="project-image">
                        <div class="project-icon">PWC</div>
                    </div>
                    <div class="project-content">
                        <h3 class="project-title">Educational Strategy</h3>
                        <p class="project-meta">PwC • Spring 2023</p>
                        <p class="project-desc">Designed strategies to enhance resource use and student success.</p>
                        <p class="click-hint">Click to see details →</p>
                    </div>
                </div>

                <div class="project-card" onclick="openModal('modal6')">
                    <div class="project-image">
                        <div class="project-icon">🌍</div>
                    </div>
                    <div class="project-content">
                        <h3 class="project-title">International Consulting</h3>
                        <p class="project-meta">OWF Group • London 2022</p>
                        <p class="project-desc">Optimized Europe-Africa trade strategies and secured funding.</p>
                        <p class="click-hint">Click to see details →</p>
                    </div>
                </div>

            </div>
        </section>
    </div>

    <!-- ========== ABOUT PAGE ========== -->
    <div id="about" class="page-section">
        <section class="section">
            <h2 class="section-title">About Me</h2>
            <div class="about-container">
                <!-- ABOUT ME WITH IMAGES -->
                <div class="about-grid">
                    <div class="about-text">
                        <p>From <strong>Santiago, Dominican Republic</strong> to <strong>Boston</strong>, my journey has been driven by curiosity and a passion for creating meaningful impact.</p>
                        <p>Currently pursuing my <strong>Master's in Corporate & Organizational Communication</strong> at Northeastern University, with a BBA in Management from Hult International Business School (3.8 GPA).</p>
                        <p>I thrive at the intersection of <strong>data-driven insights</strong> and <strong>strategic storytelling</strong>. Whether analyzing engagement metrics, building cross-industry partnerships, or developing campaigns for global brands, I'm focused on creating connections that drive real results.</p>
                        <p><strong>My mission:</strong> Launch a consulting firm that combines global perspective with detailed strategy to help businesses navigate complex markets.</p>
                    </div>
                    <div class="image-upload-grid">
                        <div class="image-placeholder">
                            <span>📸</span>
                            <p>Add your photo here<br><small>Replace this div with:<br>&lt;img src="your-image.jpg" style="width:100%; height:100%; object-fit:cover; border-radius:15px;"&gt;</small></p>
                        </div>
                        <div class="image-placeholder">
                            <span>📸</span>
                            <p>Add your photo here<br><small>Replace this div with:<br>&lt;img src="your-image.jpg" style="width:100%; height:100%; object-fit:cover; border-radius:15px;"&gt;</small></p>
                        </div>
                    </div>
                </div>

                <!-- FUN FACTS -->
                <h3 style="font-size: 2.5rem; text-align: center; margin-bottom: 3rem; color: var(--primary);">Fun Facts</h3>
                <div class="funfacts-grid">
                    <div class="funfact-card">
                        <div class="emoji">🏂</div>
                        <p>I thrive on adopting extreme activities to challenge myself and push beyond my comfort zone.</p>
                    </div>
                    <div class="funfact-card">
                        <div class="emoji">👨‍👩‍👧‍👦</div>
                        <p>I appreciate my family for always being there for me and reminding me that there's always hope and strength.</p>
                    </div>
                    <div class="funfact-card">
                        <div class="emoji">🌲</div>
                        <p>I love connecting with nature, spending quality time with my friends, and sharing endless laughter.</p>
                    </div>
                    <div class="funfact-card">
                        <div class="emoji">🎉</div>
                        <p>I enjoy attending events with my friends, making unforgettable memories and experiencing new things together.</p>
                    </div>
                    <div class="funfact-card">
                        <div class="emoji">🐺</div>
                        <p>I love my dog, Kiki—she's a bundle of joy and energy who never fails to brighten my day.</p>
                    </div>
                    <div class="funfact-card">
                        <div class="emoji">🌆</div>
                        <p>I love taking walks with a view of the city, clearing my mind, and enjoying the peaceful atmosphere.</p>
                    </div>
                </div>
            </div>
        </section>
    </div>

    <!-- ========== SKILLS PAGE ========== -->
    <div id="skills" class="page-section">
        <!-- STATS SECTION -->
        <section class="stats-section">
            <h2 class="section-title">Impact by Numbers</h2>
            <div class="stats-grid">
                <div class="stat-card">
                    <div class="stat-number">300+</div>
                    <div class="stat-label">B2B Leads Generated</div>
                </div>
                <div class="stat-card">
                    <div class="stat-number">20%</div>
                    <div class="stat-label">Engagement Boost</div>
                </div>
                <div class="stat-card">
                    <div class="stat-number">10%</div>
                    <div class="stat-label">Portfolio Growth</div>
                </div>
                <div class="stat-card">
                    <div class="stat-number">3.8</div>
                    <div class="stat-label">GPA Excellence</div>
                </div>
            </div>
        </section>

        <!-- SKILLS & EXPERTISE -->
        <section class="section">
            <h2 class="section-title">Skills & Expertise</h2>
            <div class="skills-container">
                <div class="skill-pill">Strategic Communication</div>
                <div class="skill-pill">Data Analysis</div>
                <div class="skill-pill">Digital Marketing</div>
                <div class="skill-pill">Partnership Building</div>
                <div class="skill-pill">Market Research</div>
                <div class="skill-pill">Content Creation</div>
                <div class="skill-pill">SEO Strategy</div>
                <div class="skill-pill">HubSpot</div>
                <div class="skill-pill">Crisis Management</div>
                <div class="skill-pill">Hootsuite</div>
                <div class="skill-pill">Monday.com</div>
                <div class="skill-pill">Asana</div>
                <div class="skill-pill">Bilingual (EN/ES)</div>
            </div>
        </section>

        <!-- CERTIFICATIONS -->
        <section class="section">
            <h2 class="section-title">Certifications</h2>
            <div class="cert-grid">
                <div class="cert-card">
                    <span>🏆</span>
                    <p>Hult Business School<br>Dean's List Certificate<br><small>Add image: Replace this div with &lt;img&gt;</small></p>
                </div>
                <div class="cert-card">
                    <span>🏆</span>
                    <p>LVMH<br>Inside Certificate<br><small>Add image: Replace this div with &lt;img&gt;</small></p>
                </div>
                <div class="cert-card">
                    <span>🏆</span>
                    <p>OWF Consulting<br>Internship Certificate<br><small>Add image: Replace this div with &lt;img&gt;</small></p>
                </div>
                <div class="cert-card">
                    <span>🏆</span>
                    <p>Voices for Change<br>Certificate<br><small>Add image: Replace this div with &lt;img&gt;</small></p>
                </div>
                <div class="cert-card">
                    <span>🏆</span>
                    <p>Management Consulting<br>Level 1: Analyst<br><small>Add image: Replace this div with &lt;img&gt;</small></p>
                </div>
                <div class="cert-card">
                    <span>🏆</span>
                    <p>PEVO Academic<br>Excellence Award<br><small>Add image: Replace this div with &lt;img&gt;</small></p>
                </div>
                <div class="cert-card">
                    <span>🏆</span>
                    <p>Accenture Strategy<br>Virtual Experience<br><small>Add image: Replace this div with &lt;img&gt;</small></p>
                </div>
                <div class="cert-card">
                    <span>🏆</span>
                    <p>Patémar<br>All-Cohorts Winner<br><small>Add image: Replace this div with &lt;img&gt;</small></p>
                </div>
            </div>
        </section>
    </div>

    <!-- ========== CONTACT PAGE ========== -->
    <div id="contact" class="page-section">
        <section class="contact-section">
            <h2>Let's Connect</h2>
            <p class="contact-text">
                Interested in collaborating? Have a project in mind? Or just want to chat about strategy and growth? I'd love to hear from you.
            </p>
            <div class="contact-buttons">
                <a href="mailto:johanna0808@icloud.com" class="contact-btn btn-primary">Email Me</a>
                <a href="https://www.linkedin.com/in/johannamrr" target="_blank" class="contact-btn btn-secondary">LinkedIn</a>
                <a href="tel:8579997732" class="contact-btn btn-secondary">(857) 999-7732</a>
            </div>
        </section>
    </div>

    <!-- ========== MODALS (Same as before) ========== -->
    <div id="modal1" class="modal">
        <div class="modal-content">
            <button class="close-modal" onclick="closeModal('modal1')">×</button>
            <div class="modal-header">
                <h2>Strategic Partnerships at DFX</h2>
                <p class="meta">Boston, MA • June - August 2025</p>
            </div>
            <div class="modal-body">
                <div class="modal-section">
                    <h3>Overview</h3>
                    <p>During my summer internship at DFX, I focused on building strategic partnerships with major financial institutions and accelerators.</p>
                </div>
                <div class="modal-section">
                    <h3>Key Achievements</h3>
                    <ul>
                        <li>Built partnerships with JP Morgan, Fidelity, Gaingels, and Silicon Valley Bank</li>
                        <li>Expanded portfolio by 10%</li>
                        <li>Sourced 300+ B2B leads with 50% pipeline accuracy</li>
                        <li>Hosted brand events across Boston</li>
                    </ul>
                </div>
                <div class="modal-section">
                    <h3>Media</h3>
                    <div class="media-grid">
                        <div class="media-item">📸 Add images/videos here</div>
                        <div class="media-item">🎥 Add media here</div>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- Additional modals 2-6 similar structure -->
    <div id="modal2" class="modal"><div class="modal-content"><button class="close-modal" onclick="closeModal('modal2')">×</button><div class="modal-header"><h2>Vizsense</h2><p class="meta">Fall 2024</p></div><div class="modal-body"><div class="modal-section"><h3>Details</h3><p>Add your project details here.</p></div></div></div></div>
    <div id="modal3" class="modal"><div class="modal-content"><button class="close-modal" onclick="closeModal('modal3')">×</button><div class="modal-header"><h2>Brunks Industries</h2><p class="meta">Summer 2024</p></div><div class="modal-body"><div class="modal-section"><h3>Details</h3><p>Add your project details here.</p></div></div></div></div>
    <div id="modal4" class="modal"><div class="modal-content"><button class="close-modal" onclick="closeModal('modal4')">×</button><div class="modal-header"><h2>Hugo Boss</h2><p class="meta">Fall 2023</p></div><div class="modal-body"><div class="modal-section"><h3>Details</h3><p>Add your project details here.</p></div></div></div></div>
    <div id="modal5" class="modal"><div class="modal-content"><button class="close-modal" onclick="closeModal('modal5')">×</button><div class="modal-header"><h2>PwC</h2><p class="meta">Spring 2023</p></div><div class="modal-body"><div class="modal-section"><h3>Details</h3><p>Add your project details here.</p></div></div></div></div>
    <div id="modal6" class="modal"><div class="modal-content"><button class="close-modal" onclick="closeModal('modal6')">×</button><div class="modal-header"><h2>OWF Group</h2><p class="meta">2022</p></div><div class="modal-body"><div class="modal-section"><h3>Details</h3><p>Add your project details here.</p></div></div></div></div>

    <script>
        // Page navigation
        function showPage(pageId) {
            // Hide all pages
            document.querySelectorAll('.page-section').forEach(page => {
                page.classList.remove('active');
            });
            
            // Show selected page
            document.getElementById(pageId).classList.add('active');
            
            // Update nav links
            document.querySelectorAll('.nav-links a').forEach(link => {
                link.classList.remove('active');
            });
            event.target.classList.add('active');
        }

        // Modal functions
        function openModal(modalId) {
            document.getElementById(modalId).classList.add('active');
            document.body.style.overflow = 'hidden';
        }

        function closeModal(modalId) {
            document.getElementById(modalId).classList.remove('active');
            document.body.style.overflow = 'auto';
        }

        window.onclick = function(event) {
            if (event.target.classList.contains('modal')) {
                event.target.classList.remove('active');
                document.body.style.overflow = 'auto';
            }
        }

        document.addEventListener('keydown', function(event) {
            if (event.key === 'Escape') {
                document.querySelectorAll('.modal').forEach(modal => {
                    modal.classList.remove('active');
                });
                document.body.style.overflow = 'auto';
            }
        });
    </script>
</body>
</html>
