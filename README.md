# CAD-PORTFOLIO
CAD Design Portfolio
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Mechanical & CAD Design Engineer Portfolio</title>
  
  <!-- Google Fonts & Font Awesome Icons -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;500;700&family=Plus+Jakarta+Sans:wght@300;400;600;700;800&display=swap" rel="stylesheet">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css" />

  <style>
    /* ==========================================================================
       1. VARIABLES & RESET
       ========================================================================== */
    :root {
      --bg-dark: #0b0f17;
      --bg-card: rgba(18, 26, 41, 0.75);
      --bg-card-border: rgba(0, 195, 255, 0.15);
      --primary: #00e5ff;
      --primary-glow: rgba(0, 229, 255, 0.35);
      --secondary: #3b82f6;
      --text-main: #f1f5f9;
      --text-muted: #94a3b8;
      --accent-grid: rgba(0, 229, 255, 0.05);
      --font-heading: 'Plus Jakarta Sans', sans-serif;
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
      font-family: var(--font-heading);
      line-height: 1.6;
      overflow-x: hidden;
    }

    /* Blueprint Grid Background Effect */
    body::before {
      content: "";
      position: fixed;
      top: 0;
      left: 0;
      width: 100vw;
      height: 100vh;
      background-image: 
        linear-gradient(var(--accent-grid) 1px, transparent 1px),
        linear-gradient(90deg, var(--accent-grid) 1px, transparent 1px);
      background-size: 40px 40px;
      z-index: -2;
      pointer-events: none;
    }

    /* Interactive Particle Canvas */
    #bg-canvas {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      z-index: -1;
      pointer-events: none;
    }

    /* Standard Utilities */
    .container {
      max-width: 1240px;
      margin: 0 auto;
      padding: 0 2rem;
    }

    .section {
      padding: 6rem 0;
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
      font-size: 1rem;
    }

    .section-subtitle {
      color: var(--text-muted);
      margin-bottom: 3rem;
      max-width: 600px;
    }

    .badge {
      font-family: var(--font-mono);
      font-size: 0.75rem;
      padding: 0.35rem 0.75rem;
      border-radius: 4px;
      background: rgba(0, 229, 255, 0.1);
      color: var(--primary);
      border: 1px solid var(--primary-glow);
      text-transform: uppercase;
      letter-spacing: 0.5px;
    }

    /* Buttons */
    .btn {
      display: inline-flex;
      align-items: center;
      gap: 0.5rem;
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

    .btn-outline {
      background: transparent;
      color: var(--text-main);
      border-color: rgba(255, 255, 255, 0.2);
    }

    .btn-outline:hover {
      border-color: var(--primary);
      color: var(--primary);
      background: rgba(0, 229, 255, 0.05);
      transform: translateY(-2px);
    }

    /* ==========================================================================
       2. NAVIGATION
       ========================================================================== */
    .navbar {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      z-index: 1000;
      background: rgba(11, 15, 23, 0.85);
      backdrop-filter: blur(12px);
      border-bottom: 1px solid rgba(255, 255, 255, 0.05);
      transition: var(--transition);
    }

    .nav-container {
      display: flex;
      justify-content: space-between;
      align-items: center;
      height: 80px;
    }

    .logo {
      font-weight: 800;
      font-size: 1.25rem;
      color: var(--text-main);
      text-decoration: none;
      display: flex;
      align-items: center;
      gap: 0.5rem;
      font-family: var(--font-mono);
    }

    .logo span {
      color: var(--primary);
    }

    .nav-links {
      display: flex;
      gap: 2rem;
      list-style: none;
      align-items: center;
    }

    .nav-links a {
      color: var(--text-muted);
      text-decoration: none;
      font-size: 0.9rem;
      font-weight: 500;
      transition: var(--transition);
    }

    .nav-links a:hover {
      color: var(--primary);
    }

    /* ==========================================================================
       3. HERO SECTION
       ========================================================================== */
    .hero {
      padding-top: 180px;
      padding-bottom: 100px;
      display: grid;
      grid-template-columns: 1.2fr 0.8fr;
      gap: 4rem;
      align-items: center;
    }

    .hero-tag {
      display: inline-flex;
      align-items: center;
      gap: 0.5rem;
      font-family: var(--font-mono);
      color: var(--primary);
      font-size: 0.875rem;
      margin-bottom: 1rem;
    }

    .hero-title {
      font-size: 3.5rem;
      font-weight: 800;
      line-height: 1.1;
      margin-bottom: 1.25rem;
      background: linear-gradient(135deg, #ffffff 30%, #94a3b8 100%);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
    }

    .hero-description {
      font-size: 1.1rem;
      color: var(--text-muted);
      margin-bottom: 2rem;
      max-width: 540px;
    }

    .hero-btns {
      display: flex;
      gap: 1rem;
      margin-bottom: 3rem;
    }

    .stats-bar {
      display: flex;
      gap: 2.5rem;
      padding-top: 2rem;
      border-top: 1px solid rgba(255, 255, 255, 0.1);
    }

    .stat-item h3 {
      font-size: 1.75rem;
      color: var(--primary);
      font-family: var(--font-mono);
    }

    .stat-item p {
      font-size: 0.8rem;
      color: var(--text-muted);
      text-transform: uppercase;
      letter-spacing: 0.5px;
    }

    /* Interactive 3D Wireframe Visual Card */
    .cad-preview-card {
      background: var(--bg-card);
      border: 1px solid var(--bg-card-border);
      border-radius: 12px;
      padding: 1.5rem;
      box-shadow: 0 20px 40px rgba(0, 0, 0, 0.5);
      position: relative;
      overflow: hidden;
    }

    .cad-viewport {
      width: 100%;
      height: 320px;
      background: rgba(4, 9, 20, 0.8);
      border-radius: 8px;
      border: 1px dashed rgba(0, 229, 255, 0.3);
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      position: relative;
    }

    .wireframe-cube {
      width: 100px;
      height: 100px;
      position: relative;
      transform-style: preserve-3d;
      animation: rotateCube 12s infinite linear;
    }

    @keyframes rotateCube {
      0% { transform: rotateX(0deg) rotateY(0deg) rotateZ(0deg); }
      100% { transform: rotateX(360deg) rotateY(360deg) rotateZ(360deg); }
    }

    .cube-face {
      position: absolute;
      width: 100px;
      height: 100px;
      border: 1.5px solid var(--primary);
      background: rgba(0, 229, 255, 0.03);
      box-shadow: inset 0 0 15px rgba(0, 229, 255, 0.1);
    }

    .front  { transform: translateZ(50px); }
    .back   { transform: rotateY(180deg) translateZ(50px); }
    .right  { transform: rotateY(90deg) translateZ(50px); }
    .left   { transform: rotateY(-90deg) translateHere is a complete, single-file CAD & Engineering Portfolio website template (`index.html`). It features a dark graphite theme, glassmorphism card styling, responsive layouts, interactive project filtering, an image modal/lightbox, and smooth navigation.

Save the code below as **`index.html`** and open it directly in any browser.

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Mechanical Design & CAD Portfolio</title>
  
  <!-- Font Awesome Icons -->
  <link rel="stylesheet" href="[https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css](https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css)">
  
  <!-- Google Fonts -->
  <link href="[https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&family=JetBrains+Mono:wght@400;500;700&display=swap](https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&family=JetBrains+Mono:wght@400;500;700&display=swap)" rel="stylesheet">

  <style>
    /* ==========================================
       CSS VARIABLES & BASE STYLES
       ========================================== */
    :root {
      --bg-dark: #0a0c10;
      --bg-card: rgba(22, 27, 34, 0.7);
      --bg-card-hover: rgba(33, 38, 45, 0.9);
      --accent-blue: #00d2ff;
      --accent-glow: rgba(0, 210, 255, 0.25);
      --text-main: #f0f6fc;
      --text-muted: #8b949e;
      --border-color: rgba(255, 255, 255, 0.1);
      --font-sans: 'Inter', sans-serif;
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
    }

    body {
      background-color: var(--bg-dark);
      color: var(--text-main);
      font-family: var(--font-sans);
      line-height: 1.6;
      overflow-x: hidden;
    }

    /* Grid Overlay Background Effect */
    body::before {
      content: "";
      position: fixed;
      top: 0;
      left: 0;
      width: 100vw;
      height: 100vh;
      background-image: 
        linear-gradient(to right, rgba(255, 255, 255, 0.03) 1px, transparent 1px),
        linear-gradient(to bottom, rgba(255, 255, 255, 0.03) 1px, transparent 1px);
      background-size: 40px 40px;
      z-index: -1;
      pointer-events: none;
    }

    a {
      color: inherit;
      text-decoration: none;
    }

    section {
      padding: 100px 8%;
      max-width: 1300px;
      margin: 0 auto;
    }

    .section-title {
      font-size: 2rem;
      font-weight: 700;
      margin-bottom: 10px;
      display: flex;
      align-items: center;
      gap: 12px;
    }

    .section-title span {
      color: var(--accent-blue);
      font-family: var(--font-mono);
      font-size: 1.2rem;
    }

    .section-subtitle {
      color: var(--text-muted);
      margin-bottom: 40px;
      font-size: 1rem;
    }

    /* Glassmorphism Card Style */
    .glass-card {
      background: var(--bg-card);
      backdrop-filter: blur(12px);
      -webkit-backdrop-filter: blur(12px);
      border: 1px solid var(--border-color);
      border-radius: 12px;
      transition: var(--transition);
    }

    .glass-card:hover {
      border-color: rgba(0, 210, 255, 0.4);
      box-shadow: 0 10px 30px -10px var(--accent-glow);
    }

    /* Buttons */
    .btn {
      display: inline-flex;
      align-items: center;
      gap: 10px;
      padding: 12px 24px;
      border-radius: 8px;
      font-weight: 600;
      font-size: 0.95rem;
      cursor: pointer;
      transition: var(--transition);
      border: none;
    }

    .btn-primary {
      background: var(--accent-blue);
      color: #000;
    }

    .btn-primary:hover {
      background: #33d9ff;
      box-shadow: 0 0 20px var(--accent-glow);
      transform: translateY(-2px);
    }

    .btn-secondary {
      background: transparent;
      color: var(--text-main);
      border: 1px solid var(--border-color);
    }

    .btn-secondary:hover {
      border-color: var(--accent-blue);
      color: var(--accent-blue);
      transform: translateY(-2px);
    }

    /* ==========================================
       NAVBAR
       ========================================== */
    header {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      padding: 20px 8%;
      display: flex;
      justify-content: space-between;
      align-items: center;
      background: rgba(10, 12, 16, 0.85);
      backdrop-filter: blur(15px);
      z-index: 1000;
      border-bottom: 1px solid var(--border-color);
    }

    .logo {
      font-size: 1.3rem;
      font-weight: 700;
      font-family: var(--font-mono);
      display: flex;
      align-items: center;
      gap: 8px;
    }

    .logo span {
      color: var(--accent-blue);
    }

    .nav-links {
      display: flex;
      gap: 30px;
      list-style: none;
    }

    .nav-links a {
      font-size: 0.95rem;
      color: var(--text-muted);
      transition: var(--transition);
    }

    .nav-links a:hover {
      color: var(--accent-blue);
    }

    .menu-toggle {
      display: none;
      font-size: 1.5rem;
      cursor: pointer;
    }

    /* ==========================================
       HERO SECTION
       ========================================== */
    #hero {
      min-height: 100vh;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: flex-start;
      padding-top: 140px;
    }

    .hero-tag {
      font-family: var(--font-mono);
      color: var(--accent-blue);
      font-size: 0.95rem;
      margin-bottom: 15px;
      display: flex;
      align-items: center;
      gap: 10px;
    }

    .hero-tag::before {
      content: "";
      width: 30px;
      height: 2px;
      background: var(--accent-blue);
    }

    .hero-title {
      font-size: 3.5rem;
      font-weight: 800;
      line-height: 1.1;
      margin-bottom: 15px;
    }

    .hero-subtitle {
      font-size: 1.5rem;
      color: var(--text-muted);
      margin-bottom: 25px;
    }

    .hero-bio {
      max-width: 600px;
      color: var(--text-muted);
      margin-bottom: 40px;
      font-size: 1.05rem;
    }

    .hero-btns {
      display: flex;
      gap: 20px;
      flex-wrap: wrap;
    }

    /* ==========================================
       ABOUT SECTION
       ========================================== */
    .about-container {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 50px;
      align-items: center;
    }

    .about-text p {
      color: var(--text-muted);
      margin-bottom: 20px;
    }

    .stats-grid {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 20px;
    }

    .stat-card {
      padding: 25px;
      text-align: center;
    }

    .stat-number {
      font-size: 2.5rem;
      font-weight: 700;
      color: var(--accent-blue);
      font-family: var(--font-mono);
    }

    .stat-label {
      color: var(--text-muted);
      font-size: 0.9rem;
      margin-top: 5px;
    }

    /* ==========================================
       SKILLS SECTION
       ========================================== */
    .skills-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
      gap: 25px;
    }

    .skill-card {
      padding: 25px;
    }

    .skill-header {
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin-bottom: 12px;
    }

    .skill-title {
      font-weight: 600;
      display: flex;
      align-items: center;
      gap: 10px;
    }

    .skill-percent {
      font-family: var(--font-mono);
      color: var(--accent-blue);
      font-size: 0.9rem;
    }

    .progress-bar {
      width: 100%;
      height: 8px;
      background: rgba(255, 255, 255, 0.08);
      border-radius: 4px;
      overflow: hidden;
    }

    .progress-fill {
      height: 100%;
      background: linear-gradient(90deg, #0088ff, var(--accent-blue));
      border-radius: 4px;
      transition: width 1s ease-in-out;
    }

    /* ==========================================
       PROJECTS SECTION
       ========================================== */
    .filter-menu {
      display: flex;
      gap: 15px;
      margin-bottom: 35px;
      flex-wrap: wrap;
    }

    .filter-btn {
      padding: 8px 18px;
      background: transparent;
      border: 1px solid var(--border-color);
      color: var(--text-muted);
      border-radius: 20px;
      cursor: pointer;
      font-size: 0.9rem;
      transition: var(--transition);
    }

    .filter-btn.active, .filter-btn:hover {
      background: var(--accent-blue);
      color: #000;
      border-color: var(--accent-blue);
    }

    .projects-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(340px, 1fr));
      gap: 30px;
    }

    .project-card {
      overflow: hidden;
      display: flex;
      flex-direction: column;
    }

    .project-img {
      width: 100%;
      height: 220px;
      background-color: #1e242c;
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
      transform: scale(1.05);
    }

    .project-content {
      padding: 25px;
      flex-grow: 1;
      display: flex;
      flex-direction: column;
    }

    .project-tags {
      display: flex;
      gap: 8px;
      margin-bottom: 12px;
      flex-wrap: wrap;
    }

    .tag {
      font-family: var(--font-mono);
      font-size: 0.75rem;
      padding: 4px 10px;
      background: rgba(0, 210, 255, 0.1);
      color: var(--accent-blue);
      border-radius: 4px;
    }

    .project-title {
      font-size: 1.3rem;
      margin-bottom: 10px;
    }

    .project-desc {
      color: var(--text-muted);
      font-size: 0.95rem;
      margin-bottom: 20px;
      flex-grow: 1;
    }

    .project-link {
      color: var(--accent-blue);
      font-weight: 600;
      display: inline-flex;
      align-items: center;
      gap: 8px;
      font-size: 0.9rem;
    }

    /* ==========================================
       CAD GALLERY (MASONRY GRID)
       ========================================== */
    .gallery-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
      gap: 20px;
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
      background: rgba(10, 12, 16, 0.8);
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      opacity: 0;
      transition: var(--transition);
      padding: 20px;
      text-align: center;
    }

    .gallery-item:hover .gallery-overlay {
      opacity: 1;
    }

    .gallery-item:hover img {
      transform: scale(1.1);
    }

    .gallery-overlay h4 {
      font-size: 1.1rem;
      margin-bottom: 5px;
    }

    .gallery-overlay p {
      color: var(--accent-blue);
      font-size: 0.85rem;
      font-family: var(--font-mono);
    }

    /* ==========================================
       CONTACT SECTION
       ========================================== */
    .contact-container {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 50px;
    }

    .contact-info p {
      color: var(--text-muted);
      margin-bottom: 30px;
    }

    .info-list {
      display: flex;
      flex-direction: column;
      gap: 20px;
    }

    .info-item {
      display: flex;
      align-items: center;
      gap: 15px;
    }

    .info-icon {
      width: 45px;
      height: 45px;
      border-radius: 8px;
      background: rgba(0, 210, 255, 0.1);
      color: var(--accent-blue);
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 1.2rem;
    }

    .contact-form {
      padding: 30px;
      display: flex;
      flex-direction: column;
      gap: 20px;
    }

    .form-group {
      display: flex;
      flex-direction: column;
      gap: 8px;
    }

    .form-group label {
      font-size: 0.9rem;
      color: var(--text-muted);
    }

    .form-group input, .form-group textarea {
      padding: 12px 16px;
      background: rgba(255, 255, 255, 0.03);
      border: 1px solid var(--border-color);
      border-radius: 6px;
      color: var(--text-main);
      font-family: inherit;
      transition: var(--transition);
    }

    .form-group input:focus, .form-group textarea:focus {
      outline: none;
      border-color: var(--accent-blue);
      box-shadow: 0 0 10px var(--accent-glow);
    }

    /* ==========================================
       LIGHTBOX MODAL
       ========================================== */
    .modal {
      display: none;
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: rgba(0, 0, 0, 0.9);
      z-index: 2000;
      justify-content: center;
      align-items: center;
      padding: 20px;
    }

    .modal-content {
      max-width: 90%;
      max-height: 85vh;
      border-radius: 8px;
      box-shadow: 0 0 30px rgba(0, 0, 0, 0.8);
    }

    .close-modal {
      position: absolute;
      top: 25px;
      right: 35px;
      color: #fff;
      font-size: 2rem;
      cursor: pointer;
    }

    /* ==========================================
       FOOTER
       ========================================== */
    footer {
      padding: 40px 8%;
      border-top: 1px solid var(--border-color);
      display: flex;
      justify-content: space-between;
      align-items: center;
      color: var(--text-muted);
      font-size: 0.9rem;
      max-width: 1300px;
      margin: 0 auto;
    }

    .social-links {
      display: flex;
      gap: 20px;
    }

    .social-links a {
      font-size: 1.2rem;
      transition: var(--transition);
    }

    .social-links a:hover {
      color: var(--accent-blue);
    }

    /* ==========================================
       RESPONSIVE DESIGN
       ========================================== */
    @media (max-width: 992px) {
      .about-container, .contact-container {
        grid-template-columns: 1fr;
      }
      .hero-title {
        font-size: 2.8rem;
      }
    }

    @media (max-width: 768px) {
      .nav-links {
        display: none;
        position: absolute;
        top: 100%;
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
      <i class="fa-solid fa-cube"></i> CAD<span>.DEVS</span>
    </a>
    <div class="menu-toggle" id="mobile-menu">
      <i class="fa-solid fa-bars"></i>
    </div>
    <ul class="nav-links">
      <li><a href="#about">About</a></li>
      <li><a href="#skills">Skills</a></li>
      <li><a href="#projects">Projects</a></li>
      <li><a href="#gallery">Gallery</a></li>
      <li><a href="#contact">Contact</a></li>
    </ul>
  </header>

  <main>
    <!-- HERO SECTION -->
    <section id="hero">
      <div class="hero-tag">MECHANICAL & CAD ENGINEER</div>
      <h1 class="hero-title">Precision Engineering.<br>Functional Design.</h1>
      <h2 class="hero-subtitle">Transforming complex concepts into production-ready CAD models.</h2>
      <p class="hero-bio">
        Specializing in 3D parametric modeling, mechanical assembly design, sheet metal enclosures, 
        and high-quality photorealistic rendering using SolidWorks, Fusion 360, and AutoCAD.
      </p>
      <div class="hero-btns">
        <a href="#projects" class="btn btn-primary"><i class="fa-solid fa-layer-group"></i> View CAD Projects</a>
        <a href="#" class="btn btn-secondary"><i class="fa-solid fa-file-arrow-down"></i> Download Resume</a>
      </div>
    </section>

    <!-- ABOUT SECTION -->
    <section id="about">
      <h2 class="section-title"><span>01.</span> About Me</h2>
      <p class="section-subtitle">A brief overview of my engineering background and approach.</p>
      
      <div class="about-container">
        <div class="about-text">
          <p>
            I am a Mechanical Design Engineer passionate about product design, rapid prototyping, and manufacturing optimization. My engineering focus combines mechanical integrity with sleek aesthetics.
          </p>
          <p>
            Whether designing complex internal gear mechanisms, sheet metal chassis, or consumer electronic housings, I focus heavily on Design for Manufacturing (DFM) and Design for Assembly (DFA).
          </p>
        </div>
        <div class="stats-grid">
          <div class="stat-card glass-card">
            <div class="stat-number">25+</div>
            <div class="stat-label">CAD Projects Completed</div>
          </div>
          <div class="stat-card glass-card">
            <div class="stat-number">4+</div>
            <div class="stat-label">CAD & FEA Suites</div>
          </div>
          <div class="stat-card glass-card">
            <div class="stat-number">3+</div>
            <div class="stat-label">Years Design Experience</div>
          </div>
          <div class="stat-card glass-card">
            <div class="stat-number">100%</div>
            <div class="stat-label">Precision & DFM Focused</div>
          </div>
        </div>
      </div>
    </section>

    <!-- SKILLS SECTION -->
    <section id="skills">
      <h2 class="section-title"><span>02.</span> Software & Competencies</h2>
      <p class="section-subtitle">Core software proficiencies and engineering tools.</p>

      <div class="skills-grid">
        <div class="skill-card glass-card">
          <div class="skill-header">
            <span class="skill-title"><i class="fa-solid fa-gear"></i> SolidWorks</span>
            <span class="skill-percent">95%</span>
          </div>
          <div class="progress-bar">
            <div class="progress-fill" style="width: 95%;"></div>
          </div>
        </div>

        <div class="skill-card glass-card">
          <div class="skill-header">
            <span class="skill-title"><i class="fa-solid fa-compass-drafting"></i> AutoCAD</span>
            <span class="skill-percent">90%</span>
          </div>
          <div class="progress-bar">
            <div class="progress-fill" style="width: 90%;"></div>
          </div>
        </div>

        <div class="skill-card glass-card">
          <div class="skill-header">
            <span class="skill-title"><i class="fa-solid fa-cube"></i> Autodesk Fusion 360</span>
            <span class="skill-percent">85%</span>
          </div>
          <div class="progress-bar">
            <div class="progress-fill" style="width: 85%;"></div>
          </div>
        </div>

        <div class="skill-card glass-card">
          <div class="skill-header">
            <span class="skill-title"><i class="fa-solid fa-chart-line"></i> ANSYS / FEA Simulation</span>
            <span class="skill-percent">75%</span>
          </div>
          <div class="progress-bar">
            <div class="progress-fill" style="width: 75%;"></div>
          </div>
        </div>
      </div>
    </section>

    <!-- PROJECTS SECTION -->
    <section id="projects">
      <h2 class="section-title"><span>03.</span> Featured CAD Projects</h2>
      <p class="section-subtitle">Filter through mechanical assemblies, product designs, and renderings.</p>

      <div class="filter-menu">
        <button class="filter-btn active" data-filter="all">All Projects</button>
        <button class="filter-btn" data-filter="mechanical">Mechanical</button>
        <button class="filter-btn" data-filter="product">Product Design</button>
        <button class="filter-btn" data-filter="sheet-metal">Sheet Metal</button>
      </div>

      <div class="projects-grid">
        <!-- Project 1 -->
        <div class="project-card glass-card" data-category="mechanical">
          <div class="project-img">
            <img src="[https://images.unsplash.com/photo-1581092160607-ee22621dd758?auto=format&fit=crop&w=600&q=80](https://images.unsplash.com/photo-1581092160607-ee22621dd758?auto=format&fit=crop&w=600&q=80)" alt="Robotic Arm Assembly">
          </div>
          <div class="project-content">
            <div class="project-tags">
              <span class="tag">SolidWorks</span>
              <span class="tag">Kinematics</span>
            </div>
            <h3 class="project-title">6-Axis Robotic Arm Assembly</h3>
            <p class="project-desc">Complete parametric assembly featuring planetary gearbox integration, cable routing channels, and stress simulation.</p>
            <a href="#" class="project-link">View Specifications <i class="fa-solid fa-arrow-right"></i></a>
          </div>
        </div>

        <!-- Project 2 -->
        <div class="project-card glass-card" data-category="product">
          <div class="project-img">
            <img src="[https://images.unsplash.com/photo-1581092335397-9583fe92d232?auto=format&fit=crop&w=600&q=80](https://images.unsplash.com/photo-1581092335397-9583fe92d232?auto=format&fit=crop&w=600&q=80)" alt="Ergonomic Mouse">
          </div>
          <div class="project-content">
            <div class="project-tags">
              <span class="tag">Fusion 360</span>
              <span class="tag">Surfacing</span>
            </div>
            <h3 class="project-title">Ergonomic Wireless Mouse</h3>
            <p class="project-desc">Class-A surface modeling focused on palm ergonomics, internal PCB mount positioning, and injection mold draft analysis.</p>
            <a href="#" class="project-link">View Specifications <i class="fa-solid fa-arrow-right"></i></a>
          </div>
        </div>

        <!-- Project 3 -->
        <div class="project-card glass-card" data-category="sheet-metal">
          <div class="project-img">
            <img src="[https://images.unsplash.com/photo-1581092580497-e0d23cbdf1dc?auto=format&fit=crop&w=600&q=80](https://images.unsplash.com/photo-1581092580497-e0d23cbdf1dc?auto=format&fit=crop&w=600&q=80)" alt="Server Enclosure">
          </div>
          <div class="project-content">
            <div class="project-tags">
              <span class="tag">SolidWorks</span>
              <span class="tag">Sheet Metal</span>
            </div>
            <h3 class="project-title">Rackmount Server Enclosure</h3>
            <p class="project-desc">Sheet metal enclosure design featuring bend allowances, PEM nut insertions, heat dissipation ventilation, and DXF exports.</p>
            <a href="#" class="project-link">View Specifications <i class="fa-solid fa-arrow-right"></i></a>
          </div>
        </div>
      </div>
    </section>

    <!-- GALLERY SECTION -->
    <section id="gallery">
      <h2 class="section-title"><span>04.</span> Renders & Technical Drawings</h2>
      <p class="section-subtitle">Click any image to view high-resolution CAD renders and 2D blueprints.</p>

      <div class="gallery-grid">
        <div class="gallery-item glass-card" onclick="openModal(this)">
          <img src="[https://images.unsplash.com/photo-1581092160607-ee22621dd758?auto=format&fit=crop&w=800&q=80](https://images.unsplash.com/photo-1581092160607-ee22621dd758?auto=format&fit=crop&w=800&q=80)" alt="Gearbox Assembly">
          <div class="gallery-overlay">
            <h4>Planetary Gearbox</h4>
            <p>KeyShot Render</p>
          </div>
        </div>

        <div class="gallery-item glass-card" onclick="openModal(this)">
          <img src="[https://images.unsplash.com/photo-1581092335397-9583fe92d232?auto=format&fit=crop&w=800&q=80](https://images.unsplash.com/photo-1581092335397-9583fe92d232?auto=format&fit=crop&w=800&q=80)" alt="2D Blueprint">
          <div class="gallery-overlay">
            <h4>GD&T Blueprint</h4>
            <p>AutoCAD Technical Drawing</p>
          </div>
        </div>

        <div class="gallery-item glass-card" onclick="openModal(this)">
          <img src="[https://images.unsplash.com/photo-1581092580497-e0d23cbdf1dc?auto=format&fit=crop&w=800&q=80](https://images.unsplash.com/photo-1581092580497-e0d23cbdf1dc?auto=format&fit=crop&w=800&q=80)" alt="Drone Frame">
          <div class="gallery-overlay">
            <h4>Quadcopter Carbon Frame</h4>
            <p>Fusion 360 Render</p>
          </div>
        </div>

        <div class="gallery-item glass-card" onclick="openModal(this)">
          <img src="[https://images.unsplash.com/photo-1531403009284-440f080d1e12?auto=format&fit=crop&w=800&q=80](https://images.unsplash.com/photo-1531403009284-440f080d1e12?auto=format&fit=crop&w=800&q=80)" alt="Turbine Blade FEA">
          <div class="gallery-overlay">
            <h4>Turbine Stress Analysis</h4>
            <p>ANSYS Simulation</p>
          </div>
        </div>
      </div>
    </section>

    <!-- CONTACT SECTION -->
    <section id="contact">
      <h2 class="section-title"><span>05.</span> Get In Touch</h2>
      <p class="section-subtitle">Available for freelance CAD work, design consultations, or full-time roles.</p>

      <div class="contact-container">
        <div class="contact-info">
          <p>Feel free to reach out if you need parametric 3D models, manufacturing drawings, or product design assistance.</p>
          
          <div class="info-list">
            <div class="info-item">
              <div class="info-icon"><i class="fa-solid fa-envelope"></i></div>
              <div>
                <small style="color:var(--text-muted)">Email</small>
                <div>engineer@example.com</div>
              </div>
            </div>

            <div class="info-item">
              <div class="info-icon"><i class="fa-solid fa-location-dot"></i></div>
              <div>
                <small style="color:var(--text-muted)">Location</small>
                <div>San Francisco, CA / Remote</div>
              </div>
            </div>
          </div>
        </div>

        <form class="contact-form glass-card" onsubmit="event.preventDefault(); alert('Message sent!');">
          <div class="form-group">
            <label for="name">Your Name</label>
            <input type="text" id="name" placeholder="John Doe" required>
          </div>

          <div class="form-group">
            <label for="email">Your Email</label>
            <input type="email" id="email" placeholder="john@example.com" required>
          </div>

          <div class="form-group">
            <label for="message">Project Details</label>
            <textarea id="message" rows="5" placeholder="Describe your CAD requirements..." required></textarea>
          </div>

          <button type="submit" class="btn btn-primary"><i class="fa-solid fa-paper-plane"></i> Send Message</button>
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
    <div>&copy; 2026 CAD Portfolio. All rights reserved.</div>
    <div class="social-links">
      <a href="#"><i class="fa-brands fa-github"></i></a>
      <a href="#"><i class="fa-brands fa-linkedin"></i></a>
      <a href="#"><i class="fa-solid fa-envelope"></i></a>
    </div>
  </footer>

  <!-- JAVASCRIPT -->
  <script>
    // Mobile Navigation Toggle
    const mobileMenu = document.getElementById('mobile-menu');
    const navLinks = document.querySelector('.nav-links');

    mobileMenu.addEventListener('click', () => {
      navLinks.classList.toggle('active');
    });

    // Close mobile menu on link click
    document.querySelectorAll('.nav-links a').forEach(link => {
      link.addEventListener('click', () => {
        navLinks.classList.remove('active');
      });
    });

    // Project Filtering Logic
    const filterBtns = document.querySelectorAll('.filter-btn');
    const projectCards = document.querySelectorAll('.project-card');

    filterBtns.forEach(btn => {
      btn.addEventListener('click', () => {
        // Remove active class from all buttons
        filterBtns.forEach(b => b.classList.remove('active'));
        btn.classList.add('active');

        const filterValue = btn.getAttribute('data-filter');

        projectCards.forEach(card => {
          if (filterValue === 'all' || card.getAttribute('data-category') === filterValue) {
            card.style.display = 'flex';
          } else {
            card.style.display = 'none';
          }
        });
      });
    });

    // Lightbox Modal Logic
    const modal = document.getElementById('imageModal');
    const modalImg = document.getElementById('modalImg');

    function openModal(element) {
      const imgSrc = element.querySelector('img').src;
      modal.style.display = 'flex';
      modalImg.src = imgSrc;
    }

    function closeModal() {
      modal.style.display = 'none';
    }

    // Close modal on escape key
    document.addEventListener('keydown', (e) => {
      if (e.key === 'Escape') closeModal();
    });
  </script>
</body>
</html>
