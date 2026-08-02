<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Mechanical Design & CAD Engineering Portfolio</title>
  
  <!-- Font Awesome Icons & Google Fonts -->
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:ital,wght@0,300;0,400;0,500;0,700;1,400&family=Plus+Jakarta+Sans:wght@300;400;600;700;800&display=swap" rel="stylesheet">

  <style>
    /* ==========================================================================
       1. CORE DESIGN VARIABLES & RESET
       ========================================================================== */
    :root {
      --bg-dark: #070a10;
      --bg-card: rgba(13, 20, 34, 0.75);
      --bg-card-hover: rgba(20, 30, 50, 0.85);
      --border-color: rgba(0, 229, 255, 0.15);
      --border-focus: rgba(0, 229, 255, 0.5);
      --primary: #00e5ff;
      --primary-glow: rgba(0, 229, 255, 0.3);
      --secondary: #3b82f6;
      --text-main: #f1f5f9;
      --text-muted: #94a3b8;
      --grid-line: rgba(0, 229, 255, 0.04);
      --font-main: 'Plus Jakarta Sans', sans-serif;
      --font-mono: 'JetBrains Mono', monospace;
      --transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
    }

    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    html {
      scroll-behavior: smooth;
      color-scheme: dark;
    }

    body {
      background-color: var(--bg-dark);
      color: var(--text-main);
      font-family: var(--font-main);
      line-height: 1.6;
      overflow-x: hidden;
    }

    /* Technical Blueprint Grid Pattern */
    body::before {
      content: "";
      position: fixed;
      top: 0;
      left: 0;
      width: 100vw;
      height: 100vh;
      background-image: 
        linear-gradient(var(--grid-line) 1px, transparent 1px),
        linear-gradient(90deg, var(--grid-line) 1px, transparent 1px);
      background-size: 36px 36px;
      z-index: -1;
      pointer-events: none;
    }

    section {
      padding: 100px 8%;
      max-width: 1320px;
      margin: 0 auto;
    }

    .section-title {
      font-size: 2.25rem;
      font-weight: 800;
      margin-bottom: 0.5rem;
      display: flex;
      align-items: center;
      gap: 0.75rem;
    }

    .section-title span {
      color: var(--primary);
      font-family: var(--font-mono);
      font-size: 1.1rem;
    }

    .section-subtitle {
      color: var(--text-muted);
      margin-bottom: 3.5rem;
      font-size: 1rem;
      max-width: 620px;
    }

    /* Glassmorphism Cards */
    .glass-card {
      background: var(--bg-card);
      backdrop-filter: blur(16px);
      -webkit-backdrop-filter: blur(16px);
      border: 1px solid var(--border-color);
      border-radius: 12px;
      transition: var(--transition);
    }

    .glass-card:hover {
      border-color: var(--border-focus);
      box-shadow: 0 12px 30px -10px var(--primary-glow);
    }

    /* Buttons */
    .btn {
      display: inline-flex;
      align-items: center;
      gap: 0.6rem;
      padding: 0.85rem 1.75rem;
      border-radius: 6px;
      font-weight: 600;
      font-size: 0.95rem;
      text-decoration: none;
      cursor: pointer;
      transition: var(--transition);
      border: 1px solid transparent;
    }

    .btn-primary {
      background: var(--primary);
      color: #040914;
      box-shadow: 0 0 20px var(--primary-glow);
    }

    .btn-primary:hover {
      background: #33ecff;
      transform: translateY(-2px);
      box-shadow: 0 0 30px var(--primary-glow);
    }

    .btn-secondary {
      background: transparent;
      color: var(--text-main);
      border-color: var(--border-color);
    }

    .btn-secondary:hover {
      border-color: var(--primary);
      color: var(--primary);
      background: rgba(0, 229, 255, 0.05);
      transform: translateY(-2px);
    }

    /* ==========================================================================
       2. HEADER & NAVIGATION
       ========================================================================== */
    header {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      padding: 0 8%;
      height: 80px;
      display: flex;
      justify-content: space-between;
      align-items: center;
      background: rgba(7, 10, 16, 0.88);
      backdrop-filter: blur(16px);
      z-index: 1000;
      border-bottom: 1px solid rgba(255, 255, 255, 0.05);
    }

    .logo {
      font-size: 1.25rem;
      font-weight: 800;
      font-family: var(--font-mono);
      color: var(--text-main);
      text-decoration: none;
      display: flex;
      align-items: center;
      gap: 10px;
    }

    .logo span {
      color: var(--primary);
    }

    .nav-links {
      display: flex;
      gap: 2.2rem;
      list-style: none;
      align-items: center;
    }

    .nav-links a {
      font-size: 0.9rem;
      font-weight: 500;
      color: var(--text-muted);
      text-decoration: none;
      transition: var(--transition);
    }

    .nav-links a:hover {
      color: var(--primary);
    }

    .menu-toggle {
      display: none;
      font-size: 1.5rem;
      cursor: pointer;
      color: var(--text-main);
    }

    /* ==========================================================================
       3. HERO SECTION & 3D INTERACTIVE VIEWPORT
       ========================================================================== */
    #hero {
      min-height: 100vh;
      padding-top: 130px;
      display: grid;
      grid-template-columns: 1.1fr 0.9fr;
      gap: 3.5rem;
      align-items: center;
    }

    .hero-tag {
      display: inline-flex;
      align-items: center;
      gap: 0.5rem;
      font-family: var(--font-mono);
      color: var(--primary);
      font-size: 0.85rem;
      margin-bottom: 1rem;
      padding: 0.35rem 0.85rem;
      background: rgba(0, 229, 255, 0.08);
      border: 1px solid var(--primary-glow);
      border-radius: 4px;
    }

    .hero-title {
      font-size: 3.25rem;
      font-weight: 800;
      line-height: 1.15;
      margin-bottom: 1.25rem;
      background: linear-gradient(135deg, #ffffff 40%, #94a3b8 100%);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
    }

    .hero-subtitle {
      font-size: 1.25rem;
      color: var(--primary);
      margin-bottom: 1rem;
      font-weight: 600;
    }

    .hero-bio {
      color: var(--text-muted);
      margin-bottom: 2rem;
      font-size: 1.025rem;
      max-width: 560px;
    }

    .hero-btns {
      display: flex;
      gap: 1rem;
      margin-bottom: 3rem;
      flex-wrap: wrap;
    }

    /* CAD Viewport Box Widget */
    .cad-viewport-card {
      position: relative;
      padding: 1.5rem;
      overflow: hidden;
      display: flex;
      flex-direction: column;
      gap: 1rem;
    }

    .viewport-header {
      display: flex;
      justify-content: space-between;
      align-items: center;
      font-family: var(--font-mono);
      font-size: 0.75rem;
      color: var(--text-muted);
      border-bottom: 1px solid var(--border-color);
      padding-bottom: 0.75rem;
    }

    .viewport-status {
      display: flex;
      align-items: center;
      gap: 6px;
      color: #10b981;
    }

    .status-dot {
      width: 8px;
      height: 8px;
      background: #10b981;
      border-radius: 50%;
      box-shadow: 0 0 10px #10b981;
    }

    .cad-stage {
      width: 100%;
      height: 280px;
      background: rgba(4, 8, 15, 0.95);
      border-radius: 8px;
      border: 1px dashed rgba(0, 229, 255, 0.25);
      display: flex;
      align-items: center;
      justify-content: center;
      perspective: 900px;
      position: relative;
      cursor: grab;
    }

    .cad-stage:active {
      cursor: grabbing;
    }

    /* CSS 3D Model Visualizer */
    .wireframe-cube {
      width: 110px;
      height: 110px;
      position: relative;
      transform-style: preserve-3d;
      transition: transform 0.1s ease-out;
    }

    .wireframe-cube.animating {
      animation: spinCube 14s infinite linear;
    }

    @keyframes spinCube {
      0% { transform: rotateX(15deg) rotateY(0deg); }
      100% { transform: rotateX(15deg) rotateY(360deg); }
    }

    .cube-face {
      position: absolute;
      width: 110px;
      height: 110px;
      border: 1.5px solid var(--primary);
      background: rgba(0, 229, 255, 0.04);
      box-shadow: inset 0 0 15px rgba(0, 229, 255, 0.12);
      display: flex;
      align-items: center;
      justify-content: center;
      font-family: var(--font-mono);
      font-size: 0.65rem;
      color: var(--primary);
    }

    .front  { transform: translateZ(55px); }
    .back   { transform: rotateY(180deg) translateZ(55px); }
    .right  { transform: rotateY(90deg) translateZ(55px); }
    .left   { transform: rotateY(-90deg) translateZ(55px); }
    .top    { transform: rotateX(90deg) translateZ(55px); }
    .bottom { transform: rotateX(-90deg) translateZ(55px); }

    .viewport-controls {
      display: flex;
      justify-content: space-between;
      align-items: center;
      background: rgba(0, 0, 0, 0.4);
      padding: 0.6rem 0.8rem;
      border-radius: 6px;
      font-family: var(--font-mono);
      font-size: 0.75rem;
    }

    .view-btn {
      background: rgba(0, 229, 255, 0.1);
      border: 1px solid var(--border-color);
      color: var(--primary);
      padding: 4px 10px;
      border-radius: 4px;
      cursor: pointer;
      transition: var(--transition);
    }

    .view-btn:hover {
      background: var(--primary);
      color: #000;
    }

    .viewport-telemetry {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 0.75rem;
      font-family: var(--font-mono);
      font-size: 0.75rem;
      text-align: center;
      background: rgba(0, 0, 0, 0.3);
      padding: 0.75rem;
      border-radius: 6px;
    }

    .telemetry-item label {
      display: block;
      color: var(--text-muted);
      font-size: 0.65rem;
    }

    .telemetry-item val {
      color: var(--primary);
      font-weight: 700;
    }

    /* ==========================================================================
       4. ABOUT & ENGINEERING STATS
       ========================================================================== */
    .about-container {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 3.5rem;
      align-items: center;
    }

    .about-text p {
      color: var(--text-muted);
      margin-bottom: 1.25rem;
      font-size: 1.05rem;
    }

    .stats-grid {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 1.25rem;
    }

    .stat-card {
      padding: 1.75rem;
      text-align: center;
    }

    .stat-number {
      font-size: 2.5rem;
      font-weight: 800;
      color: var(--primary);
      font-family: var(--font-mono);
    }

    .stat-label {
      color: var(--text-muted);
      font-size: 0.85rem;
      margin-top: 4px;
      text-transform: uppercase;
      letter-spacing: 0.5px;
    }

    /* ==========================================================================
       5. SKILLS & COMPETENCIES
       ========================================================================== */
    .skills-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
      gap: 1.5rem;
    }

    .skill-card {
      padding: 1.5rem;
    }

    .skill-header {
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin-bottom: 0.75rem;
    }

    .skill-title {
      font-weight: 600;
      display: flex;
      align-items: center;
      gap: 10px;
    }

    .skill-title i {
      color: var(--primary);
    }

    .skill-percent {
      font-family: var(--font-mono);
      color: var(--primary);
      font-size: 0.85rem;
    }

    .progress-bar {
      width: 100%;
      height: 8px;
      background: rgba(255, 255, 255, 0.06);
      border-radius: 4px;
      overflow: hidden;
    }

    .progress-fill {
      height: 100%;
      background: linear-gradient(90deg, var(--secondary), var(--primary));
      border-radius: 4px;
    }

    /* ==========================================================================
       6. FEATURED PROJECTS SECTION
       ========================================================================== */
    .filter-menu {
      display: flex;
      gap: 10px;
      margin-bottom: 2.5rem;
      flex-wrap: wrap;
    }

    .filter-btn {
      padding: 8px 18px;
      background: transparent;
      border: 1px solid var(--border-color);
      color: var(--text-muted);
      border-radius: 20px;
      cursor: pointer;
      font-size: 0.85rem;
      font-family: var(--font-mono);
      transition: var(--transition);
    }

    .filter-btn.active, .filter-btn:hover {
      background: var(--primary);
      color: #040914;
      border-color: var(--primary);
      font-weight: 700;
    }

    .projects-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(340px, 1fr));
      gap: 2rem;
    }

    .project-card {
      overflow: hidden;
      display: flex;
      flex-direction: column;
    }

    .project-img {
      width: 100%;
      height: 220px;
      background-color: #111827;
      overflow: hidden;
      position: relative;
    }

    .project-img img {
      width: 100%;
      height: 100%;
      object-fit: cover;
      transition: var(--transition);
    }

    .project-card:hover .project-img img {
      transform: scale(1.06);
    }

    .project-content {
      padding: 1.5rem;
      flex-grow: 1;
      display: flex;
      flex-direction: column;
    }

    .project-tags {
      display: flex;
      gap: 6px;
      margin-bottom: 0.75rem;
      flex-wrap: wrap;
    }

    .tag {
      font-family: var(--font-mono);
      font-size: 0.7rem;
      padding: 3px 8px;
      background: rgba(0, 229, 255, 0.1);
      color: var(--primary);
      border-radius: 4px;
      border: 1px solid rgba(0, 229, 255, 0.2);
    }

    .project-title {
      font-size: 1.25rem;
      margin-bottom: 0.5rem;
    }

    .project-desc {
      color: var(--text-muted);
      font-size: 0.925rem;
      margin-bottom: 1.5rem;
      flex-grow: 1;
    }

    .project-link {
      color: var(--primary);
      font-weight: 600;
      display: inline-flex;
      align-items: center;
      gap: 8px;
      font-size: 0.9rem;
      text-decoration: none;
    }

    /* ==========================================================================
       7. RENDERS & BLUEPRINTS GALLERY
       ========================================================================== */
    .gallery-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
      gap: 1.25rem;
    }

    .gallery-item {
      position: relative;
      border-radius: 10px;
      overflow: hidden;
      height: 220px;
      cursor: pointer;
    }

    .gallery-item img {
      width: 100%;
      height: 100%;
      object-fit: cover;
      transition: var(--transition);
    }

    .gallery-overlay {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: rgba(7, 10, 16, 0.88);
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      opacity: 0;
      transition: var(--transition);
      padding: 1.5rem;
      text-align: center;
    }

    .gallery-item:hover .gallery-overlay {
      opacity: 1;
    }

    .gallery-item:hover img {
      transform: scale(1.08);
    }

    .gallery-overlay h4 {
      font-size: 1.1rem;
      margin-bottom: 4px;
    }

    .gallery-overlay p {
      color: var(--primary);
      font-size: 0.825rem;
      font-family: var(--font-mono);
    }

    /* ==========================================================================
       8. CONTACT SECTION & FOOTER
       ========================================================================== */
    .contact-container {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 3.5rem;
    }

    .contact-info p {
      color: var(--text-muted);
      margin-bottom: 2rem;
    }

    .info-list {
      display: flex;
      flex-direction: column;
      gap: 1.25rem;
    }

    .info-item {
      display: flex;
      align-items: center;
      gap: 15px;
    }

    .info-icon {
      width: 46px;
      height: 46px;
      border-radius: 8px;
      background: rgba(0, 229, 255, 0.1);
      border: 1px solid var(--primary-glow);
      color: var(--primary);
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 1.2rem;
    }

    .contact-form {
      padding: 2rem;
      display: flex;
      flex-direction: column;
      gap: 1.25rem;
    }

    .form-group {
      display: flex;
      flex-direction: column;
      gap: 6px;
    }

    .form-group label {
      font-size: 0.85rem;
      color: var(--text-muted);
    }

    .form-group input, .form-group textarea {
      padding: 0.85rem 1rem;
      background: rgba(0, 0, 0, 0.3);
      border: 1px solid var(--border-color);
      border-radius: 6px;
      color: var(--text-main);
      font-family: inherit;
      transition: var(--transition);
    }

    .form-group input:focus, .form-group textarea:focus {
      outline: none;
      border-color: var(--primary);
      box-shadow: 0 0 12px var(--primary-glow);
    }

    /* Lightbox Modal */
    .modal {
      display: none;
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: rgba(0, 0, 0, 0.92);
      z-index: 2000;
      justify-content: center;
      align-items: center;
      padding: 20px;
    }

    .modal-content {
      max-width: 90%;
      max-height: 80vh;
      border-radius: 8px;
      border: 1px solid var(--border-color);
      box-shadow: 0 0 40px rgba(0, 229, 255, 0.2);
    }

    .close-modal {
      position: absolute;
      top: 25px;
      right: 35px;
      color: #fff;
      font-size: 2.2rem;
      cursor: pointer;
    }

    footer {
      padding: 40px 8%;
      border-top: 1px solid rgba(255, 255, 255, 0.05);
      display: flex;
      justify-content: space-between;
      align-items: center;
      color: var(--text-muted);
      font-size: 0.875rem;
      max-width: 1320px;
      margin: 0 auto;
    }

    .social-links {
      display: flex;
      gap: 1.25rem;
    }

    .social-links a {
      font-size: 1.2rem;
      color: var(--text-muted);
      transition: var(--transition);
    }

    .social-links a:hover {
      color: var(--primary);
    }

    @media (max-width: 992px) {
      #hero, .about-container, .contact-container {
        grid-template-columns: 1fr;
      }
      .hero-title {
        font-size: 2.75rem;
      }
    }

    @media (max-width: 768px) {
      .nav-links {
        display: none;
        position: absolute;
        top: 80px;
        left: 0;
        width: 100%;
        background: var(--bg-dark);
        flex-direction: column;
        padding: 20px 8%;
        border-bottom: 1px solid var(--border-color);
      }

      .nav-links.active {
        display: flex;
      }

      .menu-toggle {
        display: block;
      }

      .hero-title {
        font-size: 2.2rem;
      }

      section {
        padding: 70px 6%;
      }
    }
  </style>
</head>
<body>

  <!-- NAVBAR -->
  <header>
    <a href="#" class="logo">
      <i class="fa-solid fa-cube"></i> 3D MECH<span>.DESIGN</span>
    </a>
    <div class="menu-toggle" id="mobile-menu">
      <i class="fa-solid fa-bars"></i>
    </div>
    <ul class="nav-links">
      <li><a href="#about">About</a></li>
      <li><a href="#skills">Competencies</a></li>
      <li><a href="#projects">Projects</a></li>
      <li><a href="#gallery">Gallery</a></li>
      <li><a href="#contact">Contact</a></li>
    </ul>
  </header>

  <main>
    <!-- HERO SECTION -->
    <section id="hero">
      <div class="hero-left">
        <div class="hero-tag"><i class="fa-solid fa-gear"></i> MECHANICAL & CAD DESIGN CONSULTANT</div>
        <h1 class="hero-title">Precision Parametric.<br>Functional Design.</h1>
        <h2 class="hero-subtitle">Engineering innovative mechanical assemblies, gear systems, & thermal storage solutions.</h2>
        <p class="hero-bio">
          Specializing in 3D CAD modeling, Computational Fluid Dynamics (CFD), involute gear profiling, and DFM/DFA optimization across SolidWorks, AutoCAD, and Fusion 360.
        </p>
        <div class="hero-btns">
          <a href="#projects" class="btn btn-primary"><i class="fa-solid fa-layer-group"></i> Explore CAD Projects</a>
          <a href="#contact" class="btn btn-secondary"><i class="fa-solid fa-paper-plane"></i> Request Consultation</a>
        </div>
      </div>

      <!-- 3D INTERACTIVE CAD VIEWPORT -->
      <div class="cad-viewport-card glass-card">
        <div class="viewport-header">
          <span><i class="fa-solid fa-compass-drafting"></i> VIEWPORT: INVOLUTE_GEAR_ARBOR.SLDPRT</span>
          <div class="viewport-status"><span class="status-dot"></span> LIVE CAD</div>
        </div>

        <div class="cad-stage" id="cadStage">
          <div class="wireframe-cube animating" id="wireframeCube">
            <div class="cube-face front">TOP</div>
            <div class="cube-face back">BOTTOM</div>
            <div class="cube-face right">RIGHT</div>
            <div class="cube-face left">LEFT</div>
            <div class="cube-face top">FRONT</div>
            <div class="cube-face bottom">BACK</div>
          </div>
        </div>

        <div class="viewport-controls">
          <span>DRAG MOUSE TO ROTATE MODEL</span>
          <button class="view-btn" id="toggleAnimBtn">PAUSE SPIN</button>
        </div>

        <div class="viewport-telemetry">
          <div class="telemetry-item">
            <label>MATERIAL</label>
            <val>AL 6061-T6</val>
          </div>
          <div class="telemetry-item">
            <label>PITCH DIA</label>
            <val>120.00 mm</val>
          </div>
          <div class="telemetry-item">
            <label>DFM STATUS</label>
            <val style="color:#10b981;">VERIFIED</val>
          </div>
        </div>
      </div>
    </section>

    <!-- ABOUT SECTION -->
    <section id="about">
      <h2 class="section-title"><span>01.</span> Engineering Approach</h2>
      <p class="section-subtitle">Blending rigorous mathematical analysis with manufacturing efficiency.</p>
      
      <div class="about-container">
        <div class="about-text">
          <p>
            As a Mechanical Engineer and primary design consultant at 3D Mech Design, I focus on transforming challenging physical concepts into production-ready mechanical hardware.
          </p>
          <p>
            My engineering expertise encompasses calculating mathematically accurate gear tooth profiles, executing CFD thermal/pressure flow simulations, and prototyping assistive mobility hardware for real-world manufacturing.
          </p>
        </div>
        <div class="stats-grid">
          <div class="stat-card glass-card">
            <div class="stat-number">30+</div>
            <div class="stat-label">Parametric Models</div>
          </div>
          <div class="stat-card glass-card">
            <div class="stat-number">100%</div>
            <div class="stat-label">DFM & GD&T Standard</div>
          </div>
          <div class="stat-card glass-card">
            <div class="stat-number">4+</div>
            <div class="stat-label">CAD / FEA Platforms</div>
          </div>
          <div class="stat-card glass-card">
            <div class="stat-number">±0.02</div>
            <div class="stat-label">Machining Tolerance (mm)</div>
          </div>
        </div>
      </div>
    </section>

    <!-- SKILLS SECTION -->
    <section id="skills">
      <h2 class="section-title"><span>02.</span> Core Competencies</h2>
      <p class="section-subtitle">Primary software suites and specialized mechanical capabilities.</p>

      <div class="skills-grid">
        <div class="skill-card glass-card">
          <div class="skill-header">
            <span class="skill-title"><i class="fa-solid fa-cube"></i> SolidWorks (3D CAD & Drafting)</span>
            <span class="skill-percent">95%</span>
          </div>
          <div class="progress-bar">
            <div class="progress-fill" style="width: 95%;"></div>
          </div>
        </div>

        <div class="skill-card glass-card">
          <div class="skill-header">
            <span class="skill-title"><i class="fa-solid fa-wind"></i> Computational Fluid Dynamics (CFD)</span>
            <span class="skill-percent">88%</span>
          </div>
          <div class="progress-bar">
            <div class="progress-fill" style="width: 88%;"></div>
          </div>
        </div>

        <div class="skill-card glass-card">
          <div class="skill-header">
            <span class="skill-title"><i class="fa-solid fa-gear"></i> Gear Engineering & Involute Profiles</span>
            <span class="skill-percent">92%</span>
          </div>
          <div class="progress-bar">
            <div class="progress-fill" style="width: 92%;"></div>
          </div>
        </div>

        <div class="skill-card glass-card">
          <div class="skill-header">
            <span class="skill-title"><i class="fa-solid fa-compass-drafting"></i> AutoCAD & Technical Drawings</span>
            <span class="skill-percent">90%</span>
          </div>
          <div class="progress-bar">
            <div class="progress-fill" style="width: 90%;"></div>
          </div>
        </div>
      </div>
    </section>

    <!-- PROJECTS SECTION -->
    <section id="projects">
      <h2 class="section-title"><span>03.</span> Featured CAD Projects</h2>
      <p class="section-subtitle">Filter through mechanical assemblies, thermal energy storage, and mobility prototypes.</p>

      <div class="filter-menu">
        <button class="filter-btn active" data-filter="all">All Work</button>
        <button class="filter-btn" data-filter="mobility">Mobility & Kinematics</button>
        <button class="filter-btn" data-filter="thermal">Thermal & Fluid</button>
        <button class="filter-btn" data-filter="gears">Gear Engineering</button>
      </div>

      <div class="projects-grid">
        <!-- Project 1 -->
        <div class="project-card glass-card" data-category="mobility">
          <div class="project-img">
            <img src="https://images.unsplash.com/photo-1581092160607-ee22621dd758?auto=format&fit=crop&w=600&q=80" alt="Assistive Stair Lifting Device">
          </div>
          <div class="project-content">
            <div class="project-tags">
              <span class="tag">SolidWorks</span>
              <span class="tag">Kinematics</span>
              <span class="tag">Mobility</span>
            </div>
            <h3 class="project-title">Stair-Lifting Mobility Chassis</h3>
            <p class="project-desc">Locally manufacturable stair-ascending mechanism optimized for structural load resistance and compact torque transmission.</p>
            <a href="#contact" class="project-link">Inquire Spec Sheet <i class="fa-solid fa-arrow-right"></i></a>
          </div>
        </div>

        <!-- Project 2 -->
        <div class="project-card glass-card" data-category="thermal">
          <div class="project-img">
            <img src="https://images.unsplash.com/photo-1531403009284-440f080d1e12?auto=format&fit=crop&w=600&q=80" alt="Sand Battery Heat Exchanger">
          </div>
          <div class="project-content">
            <div class="project-tags">
              <span class="tag">CFD</span>
              <span class="tag">Thermal Storage</span>
              <span class="tag">Heat Transfer</span>
            </div>
            <h3 class="project-title">Thermal Energy Sand Battery</h3>
            <p class="project-desc">High-temperature silica sand thermal storage tank with internal heat-exchanger coil array and velocity distribution CFD.</p>
            <a href="#contact" class="project-link">Inquire Spec Sheet <i class="fa-solid fa-arrow-right"></i></a>
          </div>
        </div>

        <!-- Project 3 -->
        <div class="project-card glass-card" data-category="gears">
          <div class="project-img">
            <img src="https://images.unsplash.com/photo-1581092580497-e0d23cbdf1dc?auto=format&fit=crop&w=600&q=80" alt="Involute Gear Milling Arbor">
          </div>
          <div class="project-content">
            <div class="project-tags">
              <span class="tag">Parametric Gear</span>
              <span class="tag">MATLAB</span>
              <span class="tag">GD&T</span>
            </div>
            <h3 class="project-title">Custom Involute Hobbing Arbor</h3>
            <p class="project-desc">Custom-machined gear inspection arbor with precise pitch diameter calculations, backlash control, and GD&T drafting.</p>
            <a href="#contact" class="project-link">Inquire Spec Sheet <i class="fa-solid fa-arrow-right"></i></a>
          </div>
        </div>
      </div>
    </section>

    <!-- GALLERY SECTION -->
    <section id="gallery">
      <h2 class="section-title"><span>04.</span> Technical Renders & Blueprints</h2>
      <p class="section-subtitle">Click to expand high-resolution CAD renders, CFD flow maps, and GD&T production drawings.</p>

      <div class="gallery-grid">
        <div class="gallery-item glass-card" onclick="openModal(this)">
          <img src="https://images.unsplash.com/photo-1581092160607-ee22621dd758?auto=format&fit=crop&w=800&q=80" alt="Exploded Gearbox Assembly">
          <div class="gallery-overlay">
            <h4>Precision Gear Assembly</h4>
            <p>SolidWorks Photorealistic Render</p>
          </div>
        </div>

        <div class="gallery-item glass-card" onclick="openModal(this)">
          <img src="https://images.unsplash.com/photo-1581092335397-9583fe92d232?auto=format&fit=crop&w=800&q=80" alt="2D Mechanical Blueprint">
          <div class="gallery-overlay">
            <h4>2D Machining Blueprint</h4>
            <p>AutoCAD GD&T Production Sheet</p>
          </div>
        </div>

        <div class="gallery-item glass-card" onclick="openModal(this)">
          <img src="https://images.unsplash.com/photo-1581092580497-e0d23cbdf1dc?auto=format&fit=crop&w=800&q=80" alt="Structural Chassis CAD">
          <div class="gallery-overlay">
            <h4>Assistive Wheelchair Frame</h4>
            <p>3D Wireframe & Structural FEA</p>
          </div>
        </div>

        <div class="gallery-item glass-card" onclick="openModal(this)">
          <img src="https://images.unsplash.com/photo-1531403009284-440f080d1e12?auto=format&fit=crop&w=800&q=80" alt="CFD Velocity Contour">
          <div class="gallery-overlay">
            <h4>Thermal Flow Velocity Simulation</h4>
            <p>CFD Pressure Distribution Plot</p>
          </div>
        </div>
      </div>
    </section>

    <!-- CONTACT SECTION -->
    <section id="contact">
      <h2 class="section-title"><span>05.</span> Get In Touch</h2>
      <p class="section-subtitle">Available for 3D CAD modeling, CFD fluid analysis, gear calculations, and design consultations.</p>

      <div class="contact-container">
        <div class="contact-info">
          <p>Have a mechanical design requirement or need production drawings? Send your specs below.</p>
          
          <div class="info-list">
            <div class="info-item">
              <div class="info-icon"><i class="fa-solid fa-briefcase"></i></div>
              <div>
                <small style="color:var(--text-muted)">Firm</small>
                <div>3D Mech Design</div>
              </div>
            </div>

            <div class="info-item">
              <div class="info-icon"><i class="fa-solid fa-location-dot"></i></div>
              <div>
                <small style="color:var(--text-muted)">Location</small>
                <div>Karachi, Pakistan / Remote</div>
              </div>
            </div>
          </div>
        </div>

        <form class="contact-form glass-card" onsubmit="event.preventDefault(); alert('Thank you for reaching out! Your mechanical inquiry has been submitted.');">
          <div class="form-group">
            <label for="name">Your Name / Organization</label>
            <input type="text" id="name" placeholder="e.g. John Doe" required>
          </div>

          <div class="form-group">
            <label for="email">Your Email</label>
            <input type="email" id="email" placeholder="john@example.com" required>
          </div>

          <div class="form-group">
            <label for="message">Project Requirements</label>
            <textarea id="message" rows="4" placeholder="Describe your CAD modeling, gear calculation, or CFD needs..." required></textarea>
          </div>

          <button type="submit" class="btn btn-primary"><i class="fa-solid fa-paper-plane"></i> Send Specs</button>
        </form>
      </div>
    </section>
  </main>

  <!-- LIGHTBOX MODAL -->
  <div class="modal" id="imageModal">
    <span class="close-modal" onclick="closeModal()">&times;</span>
    <img class="modal-content" id="modalImg" alt="Expanded CAD Image">
  </div>

  <!-- FOOTER -->
  <footer>
    <div>&copy; 2026 3D Mech Design. All rights reserved.</div>
    <div class="social-links">
      <a href="#"><i class="fa-brands fa-github"></i></a>
      <a href="#"><i class="fa-brands fa-linkedin"></i></a>
      <a href="#"><i class="fa-solid fa-envelope"></i></a>
    </div>
  </footer>

  <!-- INTERACTIVE JAVASCRIPT -->
  <script>
    // Mobile Drawer Navigation Toggle
    const mobileMenu = document.getElementById('mobile-menu');
    const navLinks = document.querySelector('.nav-links');

    mobileMenu.addEventListener('click', () => {
      navLinks.classList.toggle('active');
    });

    document.querySelectorAll('.nav-links a').forEach(link => {
      link.addEventListener('click', () => navLinks.classList.remove('active'));
    });

    // Interactive 3D Model Orbit Control
    const cadStage = document.getElementById('cadStage');
    const wireframeCube = document.getElementById('wireframeCube');
    const toggleAnimBtn = document.getElementById('toggleAnimBtn');
    let isDragging = false;
    let previousMouseX = 0;
    let previousMouseY = 0;
    let rotX = 15;
    let rotY = 0;

    toggleAnimBtn.addEventListener('click', () => {
      wireframeCube.classList.toggle('animating');
      toggleAnimBtn.textContent = wireframeCube.classList.contains('animating') ? 'PAUSE SPIN' : 'RESUME SPIN';
    });

    cadStage.addEventListener('mousedown', (e) => {
      isDragging = true;
      wireframeCube.classList.remove('animating');
      toggleAnimBtn.textContent = 'RESUME SPIN';
      previousMouseX = e.clientX;
      previousMouseY = e.clientY;
    });

    window.addEventListener('mousemove', (e) => {
      if (!isDragging) return;
      const deltaX = e.clientX - previousMouseX;
      const deltaY = e.clientY - previousMouseY;
      rotY += deltaX * 0.8;
      rotX -= deltaY * 0.8;
      wireframeCube.style.transform = `rotateX(${rotX}deg) rotateY(${rotY}deg)`;
      previousMouseX = e.clientX;
      previousMouseY = e.clientY;
    });

    window.addEventListener('mouseup', () => { isDragging = false; });

    // Project Discipline Filter System
    const filterBtns = document.querySelectorAll('.filter-btn');
    const projectCards = document.querySelectorAll('.project-card');

    filterBtns.forEach(btn => {
      btn.addEventListener('click', () => {
        filterBtns.forEach(b => b.classList.remove('active'));
        btn.classList.add('active');

        const filter = btn.getAttribute('data-filter');

        projectCards.forEach(card => {
          if (filter === 'all' || card.getAttribute('data-category') === filter) {
            card.style.display = 'flex';
          } else {
            card.style.display = 'none';
          }
        });
      });
    });

    // Fullscreen Modal Inspection
    const modal = document.getElementById('imageModal');
    const modalImg = document.getElementById('modalImg');

    function openModal(element) {
      modal.style.display = 'flex';
      modalImg.src = element.querySelector('img').src;
    }

    function closeModal() {
      modal.style.display = 'none';
    }

    document.addEventListener('keydown', (e) => {
      if (e.key === 'Escape') closeModal();
    });
  </script>
</body>
</html>
