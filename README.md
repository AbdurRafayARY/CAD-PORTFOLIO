<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Mechanical Design & CAD Engineering Portfolio</title>
  
  <!-- Font Awesome 6 & Google Fonts -->
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:ital,wght@0,300;0,400;0,500;0,700;1,400&family=Plus+Jakarta+Sans:wght@300;400;600;700;800&display=swap" rel="stylesheet">

  <style>
    /* ==========================================================================
       1. CORE DESIGN SYSTEM & DARK BLUEPRINT THEME
       ========================================================================== */
    :root {
      --bg-dark: #070a10;
      --bg-card: rgba(13, 20, 34, 0.8);
      --bg-card-hover: rgba(20, 32, 54, 0.9);
      --border-color: rgba(0, 229, 255, 0.18);
      --border-focus: rgba(0, 229, 255, 0.6);
      --primary: #00e5ff;
      --primary-glow: rgba(0, 229, 255, 0.35);
      --secondary: #3b82f6;
      --accent-green: #10b981;
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

    /* Technical CAD Grid Background Pattern */
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
      max-width: 1360px;
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
      max-width: 650px;
    }

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
      font-family: var(--font-main);
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

    .status-badge {
      display: inline-flex;
      align-items: center;
      gap: 6px;
      font-family: var(--font-mono);
      font-size: 0.75rem;
      padding: 4px 12px;
      border-radius: 20px;
      background: rgba(16, 185, 129, 0.1);
      border: 1px solid rgba(16, 185, 129, 0.3);
      color: var(--accent-green);
    }

    .status-dot {
      width: 6px;
      height: 6px;
      background: var(--accent-green);
      border-radius: 50%;
      box-shadow: 0 0 8px var(--accent-green);
    }

    .menu-toggle {
      display: none;
      font-size: 1.5rem;
      cursor: pointer;
      color: var(--text-main);
    }

    /* ==========================================================================
       3. HERO SECTION & INTERACTIVE 3D CAD VIEWPORT
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

    /* 3D CAD Stage Card */
    .cad-viewport-card {
      position: relative;
      padding: 1.5rem;
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

    .cad-stage {
      width: 100%;
      height: 290px;
      background: rgba(4, 8, 15, 0.95);
      border-radius: 8px;
      border: 1px dashed rgba(0, 229, 255, 0.25);
      display: flex;
      align-items: center;
      justify-content: center;
      perspective: 900px;
      position: relative;
      cursor: grab;
      user-select: none;
    }

    .cad-stage:active {
      cursor: grabbing;
    }

    /* 3D Cube Visualizer */
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
      0% { transform: rotateX(20deg) rotateY(0deg); }
      100% { transform: rotateX(20deg) rotateY(360deg); }
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
      transition: var(--transition);
    }

    .front  { transform: translateZ(55px); }
    .back   { transform: rotateY(180deg) translateZ(55px); }
    .right  { transform: rotateY(90deg) translateZ(55px); }
    .left   { transform: rotateY(-90deg) translateZ(55px); }
    .top    { transform: rotateX(90deg) translateZ(55px); }
    .bottom { transform: rotateX(-90deg) translateZ(55px); }

    /* CAD View Modes */
    .mode-solid .cube-face {
      background: rgba(0, 229, 255, 0.25);
      border-color: #fff;
    }
    .mode-xray .cube-face {
      background: rgba(59, 130, 246, 0.15);
      border-style: dashed;
    }

    .viewport-controls {
      display: flex;
      justify-content: space-between;
      align-items: center;
      background: rgba(0, 0, 0, 0.4);
      padding: 0.6rem 0.8rem;
      border-radius: 6px;
      font-family: var(--font-mono);
      font-size: 0.75rem;
      flex-wrap: wrap;
      gap: 6px;
    }

    .mode-btn-group {
      display: flex;
      gap: 4px;
    }

    .view-btn {
      background: rgba(0, 229, 255, 0.1);
      border: 1px solid var(--border-color);
      color: var(--text-main);
      padding: 4px 10px;
      border-radius: 4px;
      cursor: pointer;
      font-size: 0.7rem;
      font-family: var(--font-mono);
      transition: var(--transition);
    }

    .view-btn.active, .view-btn:hover {
      background: var(--primary);
      color: #000;
      font-weight: 700;
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
       4. NEW FEATURE: INTERACTIVE GEAR CALCULATOR WIDGET
       ========================================================================== */
    #calculator {
      padding-top: 40px;
      padding-bottom: 60px;
    }

    .calc-card {
      padding: 2rem;
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 2.5rem;
      align-items: center;
    }

    .calc-inputs {
      display: flex;
      flex-direction: column;
      gap: 1.25rem;
    }

    .input-row {
      display: flex;
      flex-direction: column;
      gap: 6px;
    }

    .input-row label {
      font-family: var(--font-mono);
      font-size: 0.85rem;
      color: var(--text-muted);
    }

    .input-row input {
      padding: 0.75rem 1rem;
      background: rgba(0, 0, 0, 0.4);
      border: 1px solid var(--border-color);
      border-radius: 6px;
      color: var(--primary);
      font-family: var(--font-mono);
      font-size: 1rem;
    }

    .calc-results {
      background: rgba(0, 0, 0, 0.5);
      border: 1px solid var(--border-color);
      border-radius: 8px;
      padding: 1.5rem;
      display: flex;
      flex-direction: column;
      gap: 1rem;
    }

    .result-item {
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding-bottom: 0.75rem;
      border-bottom: 1px solid rgba(255, 255, 255, 0.05);
      font-family: var(--font-mono);
    }

    .result-item:last-child {
      border-bottom: none;
      padding-bottom: 0;
    }

    .result-value {
      color: var(--primary);
      font-weight: 700;
      font-size: 1.1rem;
    }

    /* ==========================================================================
       5. ENGINEERING TIMELINE SECTION
       ========================================================================== */
    .timeline {
      position: relative;
      max-width: 900px;
      margin: 0 auto;
    }

    .timeline::before {
      content: "";
      position: absolute;
      top: 0;
      left: 18px;
      height: 100%;
      width: 2px;
      background: var(--border-color);
    }

    .timeline-item {
      position: relative;
      padding-left: 50px;
      margin-bottom: 2.5rem;
    }

    .timeline-icon {
      position: absolute;
      left: 0;
      top: 0;
      width: 38px;
      height: 38px;
      border-radius: 50%;
      background: var(--bg-dark);
      border: 2px solid var(--primary);
      color: var(--primary);
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 0.9rem;
    }

    .timeline-content {
      padding: 1.5rem;
    }

    .timeline-date {
      font-family: var(--font-mono);
      font-size: 0.8rem;
      color: var(--primary);
      margin-bottom: 0.35rem;
    }

    .timeline-title {
      font-size: 1.2rem;
      font-weight: 700;
      margin-bottom: 0.5rem;
    }

    /* ==========================================================================
       6. CORE COMPETENCIES & SKILLS
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
       7. FEATURED PROJECTS GRID & FILTERS
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
      cursor: pointer;
      background: none;
      border: none;
      font-family: inherit;
    }

    /* ==========================================================================
       8. GALLERY & LIGHTBOX MODAL
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

    /* Lightbox Spec Modal */
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

    .modal-container {
      max-width: 800px;
      width: 100%;
      padding: 2rem;
      position: relative;
    }

    .modal-title {
      font-size: 1.5rem;
      color: var(--primary);
      margin-bottom: 1rem;
    }

    .spec-table {
      width: 100%;
      border-collapse: collapse;
      margin: 1.25rem 0;
      font-family: var(--font-mono);
      font-size: 0.85rem;
    }

    .spec-table td {
      padding: 0.6rem 1rem;
      border-bottom: 1px solid rgba(255, 255, 255, 0.08);
    }

    .spec-table td:first-child {
      color: var(--text-muted);
    }

    .close-modal {
      position: absolute;
      top: 20px;
      right: 25px;
      color: #fff;
      font-size: 2rem;
      cursor: pointer;
    }

    /* ==========================================================================
       9. CONTACT SECTION & FOOTER
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

    footer {
      padding: 40px 8%;
      border-top: 1px solid rgba(255, 255, 255, 0.05);
      display: flex;
      justify-content: space-between;
      align-items: center;
      color: var(--text-muted);
      font-size: 0.875rem;
      max-width: 1360px;
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
      #hero, .calc-card, .contact-container {
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
    <div class="status-badge"><span class="status-dot"></span> OPEN FOR CAD CONSULTATION</div>
    <div class="menu-toggle" id="mobile-menu">
      <i class="fa-solid fa-bars"></i>
    </div>
    <ul class="nav-links">
      <li><a href="#about">About</a></li>
      <li><a href="#calculator">Gear Tool</a></li>
      <li><a href="#timeline">Milestones</a></li>
      <li><a href="#skills">Competencies</a></li>
      <li><a href="#projects">Projects</a></li>
      <li><a href="#contact">Contact</a></li>
    </ul>
  </header>

  <main>
    <!-- HERO SECTION WITH INTERACTIVE 3D CAD STAGE -->
    <section id="hero">
      <div class="hero-left">
        <div class="hero-tag"><i class="fa-solid fa-gear"></i> MECHANICAL DESIGN & CAD CONSULTANT</div>
        <h1 class="hero-title">Precision Parametric.<br>Functional Design.</h1>
        <h2 class="hero-subtitle">Specialized in mechanical assemblies, gear profiling, and thermal/fluid CFD analysis.</h2>
        <p class="hero-bio">
          Combining mathematical gear calculations, CFD thermal simulations, and production-ready DFM drafting across SolidWorks, AutoCAD, and Fusion 360.
        </p>
        <div class="hero-btns">
          <a href="#projects" class="btn btn-primary"><i class="fa-solid fa-layer-group"></i> Explore CAD Projects</a>
          <a href="#calculator" class="btn btn-secondary"><i class="fa-solid fa-calculator"></i> Launch Gear Tool</a>
        </div>
      </div>

      <!-- 3D INTERACTIVE VIEWPORT CARD -->
      <div class="cad-viewport-card glass-card">
        <div class="viewport-header">
          <span><i class="fa-solid fa-compass-drafting"></i> VIEWPORT: INVOLUTE_HOBBING_ARBOR.SLDPRT</span>
          <span style="color:var(--primary)">PITCH DIA: 120mm</span>
        </div>

        <div class="cad-stage" id="cadStage">
          <div class="wireframe-cube animating" id="wireframeCube">
            <div class="cube-face front">FRONT</div>
            <div class="cube-face back">BACK</div>
            <div class="cube-face right">RIGHT</div>
            <div class="cube-face left">LEFT</div>
            <div class="cube-face top">TOP</div>
            <div class="cube-face bottom">BOTTOM</div>
          </div>
        </div>

        <div class="viewport-controls">
          <span>MODE:</span>
          <div class="mode-btn-group">
            <button class="view-btn active" id="btnWireframe">WIRE</button>
            <button class="view-btn" id="btnSolid">SOLID</button>
            <button class="view-btn" id="btnXray">X-RAY</button>
          </div>
          <button class="view-btn" id="toggleAnimBtn">PAUSE SPIN</button>
        </div>

        <div class="viewport-telemetry">
          <div class="telemetry-item">
            <label>MATERIAL</label>
            <val>AL 6061-T6</val>
          </div>
          <div class="telemetry-item">
            <label>TOLERANCE</label>
            <val>±0.02 mm</val>
          </div>
          <div class="telemetry-item">
            <label>DFM STATUS</label>
            <val style="color:#10b981;">PASSED</val>
          </div>
        </div>
      </div>
    </section>

    <!-- NEW FEATURE: INTERACTIVE GEAR CALCULATOR WIDGET -->
    <section id="calculator">
      <h2 class="section-title"><span>01.</span> Involute Gear Parameter Calculator</h2>
      <p class="section-subtitle">Live interactive engineering utility for calculating pitch diameter and circular pitch based on module and tooth counts.</p>

      <div class="calc-card glass-card">
        <div class="calc-inputs">
          <div class="input-row">
            <label for="numTeeth">Number of Teeth ($N$)</label>
            <input type="number" id="numTeeth" value="24" min="6" max="200">
          </div>
          <div class="input-row">
            <label for="moduleVal">Gear Module ($m$ in mm)</label>
            <input type="number" id="moduleVal" value="2.5" step="0.1" min="0.5" max="20">
          </div>
          <div class="input-row">
            <label for="pressAngle">Pressure Angle ($\alpha$)</label>
            <input type="number" id="pressAngle" value="20" disabled style="opacity: 0.6;">
          </div>
        </div>

        <div class="calc-results">
          <div class="result-item">
            <span>Pitch Diameter ($D = N \times m$):</span>
            <span class="result-value" id="resPitchDia">60.00 mm</span>
          </div>
          <div class="result-item">
            <span>Circular Pitch ($p = \pi \times m$):</span>
            <span class="result-value" id="resCircPitch">7.85 mm</span>
          </div>
          <div class="result-item">
            <span>Addendum ($a = m$):</span>
            <span class="result-value" id="resAddendum">2.50 mm</span>
          </div>
          <div class="result-item">
            <span>Dedendum ($b = 1.25 \times m$):</span>
            <span class="result-value" id="resDedendum">3.13 mm</span>
          </div>
        </div>
      </div>
    </section>

    <!-- ENGINEERING TIMELINE -->
    <section id="timeline">
      <h2 class="section-title"><span>02.</span> Milestones & Engineering History</h2>
      <p class="section-subtitle">Timeline of technical consulting projects and R&D milestones.</p>

      <div class="timeline">
        <div class="timeline-item">
          <div class="timeline-icon"><i class="fa-solid fa-wheelchair"></i></div>
          <div class="timeline-content glass-card">
            <div class="timeline-date">PROJECT R&D</div>
            <h3 class="timeline-title">Stair-Lifting Assistive Mobility Device</h3>
            <p style="color:var(--text-muted)">Designed and prototyped a locally producible stair-ascending mobility mechanism with custom torque reduction gearboxes and dynamic load frame simulation.</p>
          </div>
        </div>

        <div class="timeline-item">
          <div class="timeline-icon"><i class="fa-solid fa-fire-flame-curved"></i></div>
          <div class="timeline-content glass-card">
            <div class="timeline-date">THERMAL ANALYSIS</div>
            <h3 class="timeline-title">Thermal Energy Storage Sand Battery Prototype</h3>
            <p style="color:var(--text-muted)">Engineered an insulated thermal energy storage vessel using silica sand media. Conducted full CFD flow distribution and heat transfer modeling.</p>
          </div>
        </div>

        <div class="timeline-item">
          <div class="timeline-icon"><i class="fa-solid fa-gear"></i></div>
          <div class="timeline-content glass-card">
            <div class="timeline-date">MACHINING & GEARING</div>
            <h3 class="timeline-title">Custom Involute Hobbing & Inspection Arbors</h3>
            <p style="color:var(--text-muted)">Formulated custom mathematical algorithms to calculate exact involute pitch profiles, designing specialized hobbing and inspection arbors.</p>
          </div>
        </div>
      </div>
    </section>

    <!-- SKILLS SECTION -->
    <section id="skills">
      <h2 class="section-title"><span>03.</span> Core Competencies</h2>
      <p class="section-subtitle">Core software suites and mechanical design capabilities.</p>

      <div class="skills-grid">
        <div class="skill-card glass-card">
          <div class="skill-header">
            <span class="skill-title"><i class="fa-solid fa-cube"></i> SolidWorks (3D Parametric CAD)</span>
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
            <span class="skill-title"><i class="fa-solid fa-compass-drafting"></i> AutoCAD & GD&T Technical Drafting</span>
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
      <h2 class="section-title"><span>04.</span> Featured CAD Projects</h2>
      <p class="section-subtitle">Filter through mechanical assemblies, thermal energy storage, and mobility prototypes.</p>

      <div class="filter-menu">
        <button class="filter-btn active" data-filter="all">All Work</button>
        <button class="filter-btn" data-filter="mobility">Mobility Systems</button>
        <button class="filter-btn" data-filter="thermal">Thermal & Fluid</button>
        <button class="filter-btn" data-filter="gears">Gear Engineering</button>
      </div>

      <div class="projects-grid">
        <!-- Project 1 -->
        <div class="project-card glass-card" data-category="mobility">
          <div class="project-img">
            <img src="https://images.unsplash.com/photo-1581092160607-ee22621dd758?auto=format&fit=crop&w=600&q=80" alt="Stair Climbing Frame">
          </div>
          <div class="project-content">
            <div class="project-tags">
              <span class="tag">SolidWorks</span>
              <span class="tag">Kinematics</span>
              <span class="tag">Mobility</span>
            </div>
            <h3 class="project-title">Stair-Ascending Mobility Frame</h3>
            <p class="project-desc">Locally producible stair-ascending mechanism optimized for load distribution and torque transmission.</p>
            <button class="project-link" onclick="openSpecModal('Stair-Ascending Mobility Frame', 'AL 6061-T6 Chassis', '3.2 FEA Factor', 'SolidWorks / Kinematics', '±0.05 mm')">View Specifications <i class="fa-solid fa-arrow-right"></i></button>
          </div>
        </div>

        <!-- Project 2 -->
        <div class="project-card glass-card" data-category="thermal">
          <div class="project-img">
            <img src="https://images.unsplash.com/photo-1531403009284-440f080d1e12?auto=format&fit=crop&w=600&q=80" alt="Sand Battery CFD">
          </div>
          <div class="project-content">
            <div class="project-tags">
              <span class="tag">CFD</span>
              <span class="tag">Thermal Storage</span>
              <span class="tag">Heat Transfer</span>
            </div>
            <h3 class="project-title">Sand Thermal Battery Vessel</h3>
            <p class="project-desc">High-temperature silica sand thermal storage vessel with internal heat exchanger coil fluid analysis.</p>
            <button class="project-link" onclick="openSpecModal('Sand Thermal Battery Vessel', 'Insulated Steel + Silica Sand', 'Velocity Flow Contours', 'CFD / ANSYS', 'High Temp Sealed')">View Specifications <i class="fa-solid fa-arrow-right"></i></button>
          </div>
        </div>

        <!-- Project 3 -->
        <div class="project-card glass-card" data-category="gears">
          <div class="project-img">
            <img src="https://images.unsplash.com/photo-1581092580497-e0d23cbdf1dc?auto=format&fit=crop&w=600&q=80" alt="Involute Hobbing Arbor">
          </div>
          <div class="project-content">
            <div class="project-tags">
              <span class="tag">Involute Gear</span>
              <span class="tag">MATLAB</span>
              <span class="tag">GD&T</span>
            </div>
            <h3 class="project-title">Involute Gear Inspection Arbor</h3>
            <p class="project-desc">Custom gear arbor designed with exact pitch diameter formula scripts and tight tolerance GD&T callouts.</p>
            <button class="project-link" onclick="openSpecModal('Involute Gear Inspection Arbor', 'Tool Steel (HRC 58-60)', 'Pitch Dia: 120.00mm', 'MATLAB / AutoCAD', '±0.01 mm')">View Specifications <i class="fa-solid fa-arrow-right"></i></button>
          </div>
        </div>
      </div>
    </section>

    <!-- CONTACT SECTION -->
    <section id="contact">
      <h2 class="section-title"><span>05.</span> Get In Touch</h2>
      <p class="section-subtitle">Inquire about 3D CAD modeling, gear calculations, CFD thermal simulations, or mechanical consultations.</p>

      <div class="contact-container">
        <div class="contact-info">
          <p>Have a mechanical design requirement or need production-ready CAD drawings? Send your requirements below.</p>
          
          <div class="info-list">
            <div class="info-item">
              <div class="info-icon"><i class="fa-solid fa-briefcase"></i></div>
              <div>
                <small style="color:var(--text-muted)">Firm / Brand</small>
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

        <form class="contact-form glass-card" onsubmit="event.preventDefault(); alert('Message submitted successfully!');">
          <div class="form-group">
            <label for="name">Your Name / Organization</label>
            <input type="text" id="name" placeholder="John Doe" required>
          </div>

          <div class="form-group">
            <label for="email">Your Email</label>
            <input type="email" id="email" placeholder="john@example.com" required>
          </div>

          <div class="form-group">
            <label for="message">Project Specifications</label>
            <textarea id="message" rows="4" placeholder="Describe your CAD modeling, gear calculation, or CFD needs..." required></textarea>
          </div>

          <button type="submit" class="btn btn-primary"><i class="fa-solid fa-paper-plane"></i> Send Specs</button>
        </form>
      </div>
    </section>
  </main>

  <!-- LIGHTBOX SPEC MODAL -->
  <div class="modal" id="specModal">
    <div class="modal-container glass-card">
      <span class="close-modal" onclick="closeSpecModal()">&times;</span>
      <h3 class="modal-title" id="mTitle">Project Specifications</h3>
      <table class="spec-table">
        <tr><td>Material Spec:</td><td id="mMat">AL 6061-T6</td></tr>
        <tr><td>Stress / Analysis:</td><td id="mAnalysis">Passed DFM Verification</td></tr>
        <tr><td>Software Stack:</td><td id="mStack">SolidWorks / ANSYS</td></tr>
        <tr><td>Machining Tolerance:</td><td id="mTol">±0.02 mm</td></tr>
      </table>
      <button class="btn btn-secondary" onclick="closeSpecModal()">Close Specification Sheet</button>
    </div>
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
    // Mobile Drawer Navigation
    const mobileMenu = document.getElementById('mobile-menu');
    const navLinks = document.querySelector('.nav-links');

    mobileMenu.addEventListener('click', () => {
      navLinks.classList.toggle('active');
    });

    document.querySelectorAll('.nav-links a').forEach(link => {
      link.addEventListener('click', () => navLinks.classList.remove('active'));
    });

    // 3D Viewport Controls & Display Modes
    const cadStage = document.getElementById('cadStage');
    const wireframeCube = document.getElementById('wireframeCube');
    const toggleAnimBtn = document.getElementById('toggleAnimBtn');
    const btnWireframe = document.getElementById('btnWireframe');
    const btnSolid = document.getElementById('btnSolid');
    const btnXray = document.getElementById('btnXray');

    let isDragging = false, previousMouseX = 0, previousMouseY = 0, rotX = 20, rotY = 0;

    toggleAnimBtn.addEventListener('click', () => {
      wireframeCube.classList.toggle('animating');
      toggleAnimBtn.textContent = wireframeCube.classList.contains('animating') ? 'PAUSE SPIN' : 'RESUME SPIN';
    });

    // View Mode Toggles
    btnWireframe.addEventListener('click', () => {
      wireframeCube.className = 'wireframe-cube animating';
      setActiveModeBtn(btnWireframe);
    });

    btnSolid.addEventListener('click', () => {
      wireframeCube.className = 'wireframe-cube mode-solid animating';
      setActiveModeBtn(btnSolid);
    });

    btnXray.addEventListener('click', () => {
      wireframeCube.className = 'wireframe-cube mode-xray animating';
      setActiveModeBtn(btnXray);
    });

    function setActiveModeBtn(activeBtn) {
      [btnWireframe, btnSolid, btnXray].forEach(btn => btn.classList.remove('active'));
      activeBtn.classList.add('active');
    }

    // Orbit Drag Controls
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

    // Live Involute Gear Calculator JS
    const numTeethInput = document.getElementById('numTeeth');
    const moduleValInput = document.getElementById('moduleVal');

    function calculateGear() {
      const N = parseFloat(numTeethInput.value) || 0;
      const m = parseFloat(moduleValInput.value) || 0;

      const pitchDia = N * m;
      const circPitch = Math.PI * m;
      const addendum = m;
      const dedendum = 1.25 * m;

      document.getElementById('resPitchDia').textContent = pitchDia.toFixed(2) + ' mm';
      document.getElementById('resCircPitch').textContent = circPitch.toFixed(2) + ' mm';
      document.getElementById('resAddendum').textContent = addendum.toFixed(2) + ' mm';
      document.getElementById('resDedendum').textContent = dedendum.toFixed(2) + ' mm';
    }

    numTeethInput.addEventListener('input', calculateGear);
    moduleValInput.addEventListener('input', calculateGear);

    // Filter System
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

    // Technical Spec Modal
    const specModal = document.getElementById('specModal');

    function openSpecModal(title, mat, analysis, stack, tol) {
      document.getElementById('mTitle').textContent = title;
      document.getElementById('mMat').textContent = mat;
      document.getElementById('mAnalysis').textContent = analysis;
      document.getElementById('mStack').textContent = stack;
      document.getElementById('mTol').textContent = tol;
      specModal.style.display = 'flex';
    }

    function closeSpecModal() {
      specModal.style.display = 'none';
    }

    document.addEventListener('keydown', (e) => {
      if (e.key === 'Escape') closeSpecModal();
    });
  </script>
</body>
</html>
