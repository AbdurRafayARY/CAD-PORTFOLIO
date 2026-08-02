<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Abdur Rafay Yousuf | Mechanical Design & CAD Engineer</title>
  
  <!-- Font Awesome 6 & Google Fonts -->
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;500;600;700&family=Plus+Jakarta+Sans:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">

  <style>
    /* ==========================================================================
       1. LIGHT BLUEPRINT DESIGN SYSTEM & DESIGN VARIABLES
       ========================================================================== */
    :root {
      --bg-main: #f8fafc;
      --bg-card: #ffffff;
      --bg-alt: #f1f5f9;
      --border-color: #e2e8f0;
      --border-accent: rgba(37, 99, 235, 0.3);
      
      --primary: #2563eb;         /* Engineering Royal Blue */
      --primary-hover: #1d4ed8;
      --primary-light: #eff6ff;
      --secondary: #0f172a;       /* Deep Slate / Charcoal */
      --text-main: #0f172a;
      --text-muted: #64748b;
      --accent-green: #059669;
      
      --grid-line: rgba(37, 99, 235, 0.05);
      --font-main: 'Plus Jakarta Sans', sans-serif;
      --font-mono: 'JetBrains Mono', monospace;
      
      --shadow-sm: 0 1px 3px rgba(0, 0, 0, 0.05);
      --shadow-md: 0 4px 20px -2px rgba(15, 23, 42, 0.08);
      --shadow-hover: 0 12px 30px -4px rgba(37, 99, 235, 0.15);
      --transition: all 0.25s cubic-bezier(0.4, 0, 0.2, 1);
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
      background-color: var(--bg-main);
      color: var(--text-main);
      font-family: var(--font-main);
      line-height: 1.6;
      overflow-x: hidden;
    }

    /* Subtle Technical Blueprint Grid Background */
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
      background-size: 32px 32px;
      z-index: -1;
      pointer-events: none;
    }

    section {
      padding: 90px 8%;
      max-width: 1320px;
      margin: 0 auto;
    }

    /* Section Headings */
    .section-header {
      margin-bottom: 3.5rem;
    }

    .section-tag {
      display: inline-flex;
      align-items: center;
      gap: 0.5rem;
      font-family: var(--font-mono);
      color: var(--primary);
      font-size: 0.85rem;
      font-weight: 600;
      text-transform: uppercase;
      letter-spacing: 1px;
      margin-bottom: 0.5rem;
      background: var(--primary-light);
      padding: 0.25rem 0.75rem;
      border-radius: 4px;
      border: 1px solid var(--border-accent);
    }

    .section-title {
      font-size: 2.25rem;
      font-weight: 800;
      color: var(--secondary);
      letter-spacing: -0.02em;
    }

    .section-subtitle {
      color: var(--text-muted);
      margin-top: 0.5rem;
      font-size: 1.05rem;
      max-width: 620px;
    }

    /* UI Cards */
    .card {
      background: var(--bg-card);
      border: 1px solid var(--border-color);
      border-radius: 16px;
      box-shadow: var(--shadow-md);
      transition: var(--transition);
    }

    .card:hover {
      border-color: var(--border-accent);
      box-shadow: var(--shadow-hover);
      transform: translateY(-3px);
    }

    /* Buttons */
    .btn {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      gap: 0.6rem;
      padding: 0.85rem 1.6rem;
      border-radius: 8px;
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
      color: #ffffff;
      box-shadow: 0 4px 14px rgba(37, 99, 235, 0.3);
    }

    .btn-primary:hover {
      background: var(--primary-hover);
      transform: translateY(-2px);
      box-shadow: 0 6px 20px rgba(37, 99, 235, 0.4);
    }

    .btn-secondary {
      background: #ffffff;
      color: var(--secondary);
      border-color: var(--border-color);
    }

    .btn-secondary:hover {
      border-color: var(--primary);
      color: var(--primary);
      background: var(--primary-light);
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
      background: rgba(255, 255, 255, 0.9);
      backdrop-filter: blur(12px);
      z-index: 1000;
      border-bottom: 1px solid var(--border-color);
    }

    .logo {
      font-size: 1.25rem;
      font-weight: 800;
      font-family: var(--font-mono);
      color: var(--secondary);
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
      gap: 2rem;
      list-style: none;
      align-items: center;
    }

    .nav-links a {
      font-size: 0.925rem;
      font-weight: 600;
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
      gap: 8px;
      font-family: var(--font-mono);
      font-size: 0.75rem;
      font-weight: 600;
      padding: 6px 14px;
      border-radius: 20px;
      background: rgba(5, 150, 105, 0.08);
      border: 1px solid rgba(5, 150, 105, 0.25);
      color: var(--accent-green);
    }

    .status-dot {
      width: 7px;
      height: 7px;
      background: var(--accent-green);
      border-radius: 50%;
      box-shadow: 0 0 8px var(--accent-green);
    }

    .menu-toggle {
      display: none;
      font-size: 1.4rem;
      cursor: pointer;
      color: var(--secondary);
    }

    /* ==========================================================================
       3. HERO SECTION (Who are you? What do you design? Why hire you?)
       ========================================================================== */
    #hero {
      min-height: 100vh;
      padding-top: 140px;
      padding-bottom: 60px;
      display: grid;
      grid-template-columns: 1.2fr 0.8fr;
      gap: 4rem;
      align-items: center;
    }

    .hero-greeting {
      font-family: var(--font-mono);
      color: var(--primary);
      font-weight: 600;
      font-size: 1rem;
      margin-bottom: 0.5rem;
    }

    .hero-title {
      font-size: 3.25rem;
      font-weight: 800;
      line-height: 1.15;
      color: var(--secondary);
      margin-bottom: 1.25rem;
      letter-spacing: -0.03em;
    }

    .hero-subtitle {
      font-size: 1.2rem;
      color: var(--primary);
      margin-bottom: 1rem;
      font-weight: 700;
    }

    .hero-bio {
      color: var(--text-muted);
      margin-bottom: 2.25rem;
      font-size: 1.05rem;
      max-width: 580px;
    }

    .hero-highlights {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 1rem;
      margin-bottom: 2.5rem;
      padding-top: 1.5rem;
      border-top: 1px dashed var(--border-color);
    }

    .metric-item strong {
      display: block;
      font-size: 1.5rem;
      font-weight: 800;
      color: var(--secondary);
      font-family: var(--font-mono);
    }

    .metric-item span {
      font-size: 0.825rem;
      color: var(--text-muted);
      font-weight: 500;
    }

    .hero-btns {
      display: flex;
      gap: 1rem;
      flex-wrap: wrap;
    }

    /* Profile Photo Card */
    .hero-image-wrapper {
      position: relative;
      display: flex;
      justify-content: center;
      align-items: center;
    }

    .profile-card {
      position: relative;
      padding: 1.25rem;
      background: #ffffff;
      border: 1px solid var(--border-color);
      border-radius: 24px;
      box-shadow: var(--shadow-hover);
      text-align: center;
      width: 100%;
      max-width: 380px;
    }

    .profile-img-container {
      width: 220px;
      height: 220px;
      margin: 0 auto 1.5rem auto;
      border-radius: 50%;
      overflow: hidden;
      border: 4px solid #ffffff;
      box-shadow: 0 0 0 2px var(--primary);
      background: #f1f5f9;
      position: relative;
    }

    .profile-img-container img {
      width: 100%;
      height: 100%;
      object-fit: cover;
    }

    .profile-info h3 {
      font-size: 1.25rem;
      font-weight: 800;
      color: var(--secondary);
    }

    .profile-info p {
      font-size: 0.875rem;
      color: var(--text-muted);
      font-family: var(--font-mono);
      margin-top: 2px;
    }

    .blueprint-badge {
      display: inline-flex;
      align-items: center;
      gap: 6px;
      margin-top: 1rem;
      padding: 6px 12px;
      background: var(--primary-light);
      border: 1px solid var(--border-accent);
      border-radius: 6px;
      font-size: 0.75rem;
      font-family: var(--font-mono);
      color: var(--primary);
      font-weight: 600;
    }

    /* ==========================================================================
       4. CORE COMPETENCIES & SKILLS (With Engineering Icons)
       ========================================================================== */
    .skills-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
      gap: 1.5rem;
    }

    .skill-card {
      padding: 1.75rem;
    }

    .skill-icon-header {
      display: flex;
      align-items: center;
      gap: 14px;
      margin-bottom: 1rem;
    }

    .skill-icon {
      width: 48px;
      height: 48px;
      border-radius: 12px;
      background: var(--primary-light);
      border: 1px solid var(--border-accent);
      color: var(--primary);
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 1.25rem;
    }

    .skill-title-group h3 {
      font-size: 1.05rem;
      font-weight: 700;
      color: var(--secondary);
    }

    .skill-title-group span {
      font-size: 0.75rem;
      font-family: var(--font-mono);
      color: var(--primary);
      font-weight: 600;
    }

    .skill-desc {
      font-size: 0.9rem;
      color: var(--text-muted);
      margin-bottom: 1.25rem;
    }

    .progress-bar {
      width: 100%;
      height: 7px;
      background: #e2e8f0;
      border-radius: 10px;
      overflow: hidden;
    }

    .progress-fill {
      height: 100%;
      background: var(--primary);
      border-radius: 10px;
    }

    /* ==========================================================================
       5. WORK EXPERIENCE & MILESTONES (TIMELINE)
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
      left: 20px;
      height: 100%;
      width: 2px;
      background: var(--border-color);
    }

    .timeline-item {
      position: relative;
      padding-left: 60px;
      margin-bottom: 2.5rem;
    }

    .timeline-icon {
      position: absolute;
      left: 0;
      top: 0;
      width: 42px;
      height: 42px;
      border-radius: 50%;
      background: #ffffff;
      border: 2px solid var(--primary);
      color: var(--primary);
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 1rem;
      box-shadow: var(--shadow-sm);
    }

    .timeline-content {
      padding: 1.75rem;
    }

    .timeline-header {
      display: flex;
      justify-content: space-between;
      align-items: flex-start;
      margin-bottom: 0.5rem;
      flex-wrap: wrap;
      gap: 8px;
    }

    .timeline-role {
      font-size: 1.2rem;
      font-weight: 800;
      color: var(--secondary);
    }

    .timeline-company {
      color: var(--primary);
      font-weight: 600;
      font-size: 0.95rem;
    }

    .timeline-date {
      font-family: var(--font-mono);
      font-size: 0.8rem;
      padding: 3px 10px;
      background: var(--primary-light);
      color: var(--primary);
      border-radius: 4px;
      font-weight: 600;
    }

    .timeline-body p {
      color: var(--text-muted);
      font-size: 0.95rem;
      margin-top: 0.75rem;
    }

    .timeline-tags {
      display: flex;
      gap: 6px;
      flex-wrap: wrap;
      margin-top: 1rem;
    }

    .tag-sm {
      font-family: var(--font-mono);
      font-size: 0.725rem;
      padding: 2px 8px;
      background: #f1f5f9;
      color: var(--text-muted);
      border-radius: 4px;
      border: 1px solid var(--border-color);
    }

    /* ==========================================================================
       6. FEATURED CAD PROJECTS & MANUFACTURING DRAWINGS
       ========================================================================== */
    .filter-menu {
      display: flex;
      gap: 10px;
      margin-bottom: 2.5rem;
      flex-wrap: wrap;
    }

    .filter-btn {
      padding: 8px 18px;
      background: #ffffff;
      border: 1px solid var(--border-color);
      color: var(--text-muted);
      border-radius: 30px;
      cursor: pointer;
      font-size: 0.875rem;
      font-weight: 600;
      font-family: var(--font-mono);
      transition: var(--transition);
    }

    .filter-btn.active, .filter-btn:hover {
      background: var(--primary);
      color: #ffffff;
      border-color: var(--primary);
      box-shadow: 0 4px 12px rgba(37, 99, 235, 0.25);
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
      background-color: #f1f5f9;
      overflow: hidden;
      position: relative;
      border-bottom: 1px solid var(--border-color);
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
      background: var(--primary-light);
      color: var(--primary);
      border-radius: 4px;
      border: 1px solid var(--border-accent);
      font-weight: 600;
    }

    .project-title {
      font-size: 1.2rem;
      font-weight: 800;
      color: var(--secondary);
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
      font-weight: 700;
      display: inline-flex;
      align-items: center;
      gap: 8px;
      font-size: 0.9rem;
      cursor: pointer;
      background: none;
      border: none;
      font-family: inherit;
    }

    /* Drawings & Renders Showcase Grid */
    .drawings-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
      gap: 1.25rem;
      margin-top: 2rem;
    }

    .drawing-item {
      position: relative;
      border-radius: 12px;
      overflow: hidden;
      height: 200px;
      cursor: pointer;
      border: 1px solid var(--border-color);
      background: #ffffff;
    }

    .drawing-item img {
      width: 100%;
      height: 100%;
      object-fit: cover;
      transition: var(--transition);
    }

    .drawing-overlay {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: rgba(15, 23, 42, 0.85);
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      opacity: 0;
      transition: var(--transition);
      padding: 1rem;
      text-align: center;
      color: #ffffff;
    }

    .drawing-item:hover .drawing-overlay {
      opacity: 1;
    }

    .drawing-item:hover img {
      transform: scale(1.08);
    }

    /* ==========================================================================
       7. CLIENT & PROFESSOR TESTIMONIALS
       ========================================================================== */
    .testimonials-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
      gap: 2rem;
    }

    .testimonial-card {
      padding: 2rem;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
    }

    .quote-icon {
      font-size: 1.75rem;
      color: var(--primary);
      margin-bottom: 1rem;
      opacity: 0.6;
    }

    .testimonial-text {
      color: var(--text-muted);
      font-size: 0.975rem;
      font-style: italic;
      margin-bottom: 1.5rem;
    }

    .author-group {
      display: flex;
      align-items: center;
      gap: 12px;
      border-top: 1px solid var(--border-color);
      padding-top: 1rem;
    }

    .author-avatar {
      width: 44px;
      height: 44px;
      border-radius: 50%;
      background: var(--primary-light);
      color: var(--primary);
      display: flex;
      align-items: center;
      justify-content: center;
      font-weight: 700;
      font-family: var(--font-mono);
      border: 1px solid var(--border-accent);
    }

    .author-details h4 {
      font-size: 0.95rem;
      font-weight: 700;
      color: var(--secondary);
    }

    .author-details span {
      font-size: 0.8rem;
      color: var(--text-muted);
    }

    /* ==========================================================================
       8. CONTACT SECTION & FOOTER
       ========================================================================== */
    .contact-container {
      display: grid;
      grid-template-columns: 1fr 1.2fr;
      gap: 3.5rem;
    }

    .contact-info p {
      color: var(--text-muted);
      margin-bottom: 2rem;
      font-size: 1.025rem;
    }

    .info-list {
      display: flex;
      flex-direction: column;
      gap: 1.25rem;
      margin-bottom: 2rem;
    }

    .info-item {
      display: flex;
      align-items: center;
      gap: 16px;
    }

    .info-icon {
      width: 48px;
      height: 48px;
      border-radius: 10px;
      background: var(--primary-light);
      border: 1px solid var(--border-accent);
      color: var(--primary);
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 1.2rem;
    }

    .contact-form {
      padding: 2.25rem;
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
      font-size: 0.875rem;
      font-weight: 600;
      color: var(--secondary);
    }

    .form-group input, .form-group textarea {
      padding: 0.85rem 1rem;
      background: #f8fafc;
      border: 1px solid var(--border-color);
      border-radius: 8px;
      color: var(--text-main);
      font-family: inherit;
      transition: var(--transition);
      font-size: 0.95rem;
    }

    .form-group input:focus, .form-group textarea:focus {
      outline: none;
      border-color: var(--primary);
      background: #ffffff;
      box-shadow: 0 0 0 3px rgba(37, 99, 235, 0.15);
    }

    footer {
      padding: 40px 8%;
      border-top: 1px solid var(--border-color);
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
      width: 38px;
      height: 38px;
      border-radius: 50%;
      background: #ffffff;
      border: 1px solid var(--border-color);
      color: var(--text-muted);
      display: flex;
      align-items: center;
      justify-content: center;
      transition: var(--transition);
      text-decoration: none;
    }

    .social-links a:hover {
      color: var(--primary);
      border-color: var(--primary);
      background: var(--primary-light);
      transform: translateY(-2px);
    }

    /* Modal Component */
    .modal {
      display: none;
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: rgba(15, 23, 42, 0.7);
      backdrop-filter: blur(4px);
      z-index: 2000;
      justify-content: center;
      align-items: center;
      padding: 20px;
    }

    .modal-container {
      max-width: 700px;
      width: 100%;
      padding: 2.25rem;
      position: relative;
    }

    .modal-title {
      font-size: 1.5rem;
      color: var(--secondary);
      margin-bottom: 1rem;
      font-weight: 800;
    }

    .spec-table {
      width: 100%;
      border-collapse: collapse;
      margin: 1.25rem 0;
      font-family: var(--font-mono);
      font-size: 0.875rem;
    }

    .spec-table td {
      padding: 0.75rem 1rem;
      border-bottom: 1px solid var(--border-color);
    }

    .spec-table td:first-child {
      color: var(--text-muted);
      font-weight: 500;
    }

    .spec-table td:last-child {
      color: var(--secondary);
      font-weight: 700;
    }

    .close-modal {
      position: absolute;
      top: 20px;
      right: 25px;
      color: var(--text-muted);
      font-size: 1.75rem;
      cursor: pointer;
    }

    .close-modal:hover {
      color: var(--secondary);
    }

    /* Responsive Queries */
    @media (max-width: 992px) {
      #hero, .contact-container {
        grid-template-columns: 1fr;
      }
      .hero-title {
        font-size: 2.75rem;
      }
      .hero-image-wrapper {
        order: -1;
      }
    }

    @media (max-width: 768px) {
      .nav-links {
        display: none;
        position: absolute;
        top: 80px;
        left: 0;
        width: 100%;
        background: #ffffff;
        flex-direction: column;
        padding: 20px 8%;
        border-bottom: 1px solid var(--border-color);
        box-shadow: var(--shadow-md);
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

      .hero-highlights {
        grid-template-columns: 1fr;
      }

      section {
        padding: 60px 6%;
      }
    }
  </style>
</head>
<body>

  <!-- NAVBAR -->
  <header>
    <a href="#" class="logo">
      <i class="fa-solid fa-drafting-compass"></i> ABDUR RAFAY<span>.DESIGNS</span>
    </a>
    <div class="status-badge"><span class="status-dot"></span> OPEN FOR CAD CONSULTATION</div>
    <div class="menu-toggle" id="mobile-menu">
      <i class="fa-solid fa-bars"></i>
    </div>
    <ul class="nav-links">
      <li><a href="#about">About</a></li>
      <li><a href="#skills">Competencies</a></li>
      <li><a href="#experience">Experience</a></li>
      <li><a href="#projects">CAD Projects</a></li>
      <li><a href="#testimonials">Reviews</a></li>
      <li><a href="#contact">Contact</a></li>
    </ul>
  </header>

  <main>
    <!-- HERO SECTION -->
    <section id="hero">
      <div class="hero-left">
        <div class="hero-greeting">Hi, I am Abdur Rafay Yousuf</div>
        <h1 class="hero-title">Mechanical CAD Engineer & Product Designer</h1>
        <h2 class="hero-subtitle">I transform complex engineering problems into production-ready 3D assemblies & DFM drawings.</h2>
        <p class="hero-bio">
          Founder of 3D Mech Design & Mechanical Engineering Specialist. I craft mathematically accurate involute gears, fluid/thermal CFD simulations, and lightweight structural assemblies optimized for modern manufacturing.
        </p>

        <div class="hero-highlights">
          <div class="metric-item">
            <strong>3+ Years</strong>
            <span>Parametric CAD Modeling</span>
          </div>
          <div class="metric-item">
            <strong>±0.01 mm</strong>
            <span>Precision Machining GD&T</span>
          </div>
          <div class="metric-item">
            <strong>100% DFM</strong>
            <span>Manufacturing Compliant</span>
          </div>
        </div>

        <div class="hero-btns">
          <a href="#projects" class="btn btn-primary"><i class="fa-solid fa-layer-group"></i> Explore CAD Portfolio</a>
          <a href="Abdur_Rafay_Resume.pdf" target="_blank" class="btn btn-secondary"><i class="fa-solid fa-file-pdf"></i> Download Resume</a>
        </div>
      </div>

      <!-- PROFESSIONAL PROFILE PHOTO CARD -->
      <div class="hero-image-wrapper">
        <div class="profile-card">
          <div class="profile-img-container">
            <!-- Replace with your clean profile photo -->
            <img src="https://images.unsplash.com/photo-1534528741775-53994a69daeb?auto=format&fit=crop&w=600&q=80" alt="Abdur Rafay Yousuf - Mechanical Engineer">
          </div>
          <div class="profile-info">
            <h3>Abdur Rafay Yousuf</h3>
            <p>Mechanical Design Consultant</p>
            <div class="blueprint-badge">
              <i class="fa-solid fa-certificate"></i> SolidWorks & CFD Certified
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- SKILLS SECTION WITH ICONS -->
    <section id="skills">
      <div class="section-header">
        <div class="section-tag"><i class="fa-solid fa-gears"></i> Technical Stack</div>
        <h2 class="section-title">Core Engineering Competencies</h2>
        <p class="section-subtitle">Specialized software suites and mechanical design principles applied across every project.</p>
      </div>

      <div class="skills-grid">
        <div class="skill-card card">
          <div class="skill-icon-header">
            <div class="skill-icon"><i class="fa-solid fa-cube"></i></div>
            <div class="skill-title-group">
              <h3>SolidWorks & 3D CAD</h3>
              <span>Parametric Modeling</span>
            </div>
          </div>
          <p class="skill-desc">Complex assembly design, motion simulation, parametric feature trees, and sheet metal design.</p>
          <div class="progress-bar"><div class="progress-fill" style="width: 95%;"></div></div>
        </div>

        <div class="skill-card card">
          <div class="skill-icon-header">
            <div class="skill-icon"><i class="fa-solid fa-wind"></i></div>
            <div class="skill-title-group">
              <h3>CFD & Thermal Analysis</h3>
              <span>ANSYS / Flow Simulation</span>
            </div>
          </div>
          <p class="skill-desc">Internal flow distribution, thermal energy storage modeling, forced convection, and turbulence estimation.</p>
          <div class="progress-bar"><div class="progress-fill" style="width: 88%;"></div></div>
        </div>

        <div class="skill-card card">
          <div class="skill-icon-header">
            <div class="skill-icon"><i class="fa-solid fa-gear"></i></div>
            <div class="skill-title-group">
              <h3>Involute Gear Engineering</h3>
              <span>MATLAB & Custom Arbors</span>
            </div>
          </div>
          <p class="skill-desc">Mathematical involute tooth profile calculations, diametral pitch analysis, hobbing & inspection arbors.</p>
          <div class="progress-bar"><div class="progress-fill" style="width: 92%;"></div></div>
        </div>

        <div class="skill-card card">
          <div class="skill-icon-header">
            <div class="skill-icon"><i class="fa-solid fa-compass-drafting"></i></div>
            <div class="skill-title-group">
              <h3>AutoCAD & GD&T Drafting</h3>
              <span>ASME Y14.5 Standards</span>
            </div>
          </div>
          <p class="skill-desc">Production drawings with geometric dimensioning and tolerancing, datum reference frames, and BOMs.</p>
          <div class="progress-bar"><div class="progress-fill" style="width: 90%;"></div></div>
        </div>
      </div>
    </section>

    <!-- WORK EXPERIENCE TIMELINE -->
    <section id="experience">
      <div class="section-header">
        <div class="section-tag"><i class="fa-solid fa-briefcase"></i> Track Record</div>
        <h2 class="section-title">Work Experience & R&D Milestones</h2>
        <p class="section-subtitle">Engineering roles, consulting projects, and industrial prototype developments.</p>
      </div>

      <div class="timeline">
        <div class="timeline-item">
          <div class="timeline-icon"><i class="fa-solid fa-building"></i></div>
          <div class="timeline-content card">
            <div class="timeline-header">
              <div>
                <div class="timeline-role">Founder & Principal Design Engineer</div>
                <div class="timeline-company">3D Mech Design • Consultancy</div>
              </div>
              <span class="timeline-date">2025 - Present</span>
            </div>
            <div class="timeline-body">
              <p>Leading mechanical engineering consultancy providing custom 3D CAD modeling, DFM drawing sheets, and FEA/CFD analysis for industrial clients.</p>
              <div class="timeline-tags">
                <span class="tag-sm">SolidWorks</span>
                <span class="tag-sm">DFM/DFA</span>
                <span class="tag-sm">Client Consulting</span>
              </div>
            </div>
          </div>
        </div>

        <div class="timeline-item">
          <div class="timeline-icon"><i class="fa-solid fa-wheelchair"></i></div>
          <div class="timeline-content card">
            <div class="timeline-header">
              <div>
                <div class="timeline-role">Lead Mechanical Engineer (FYDP)</div>
                <div class="timeline-company">Mahfooz Stair-Lifting Mobility Project</div>
              </div>
              <span class="timeline-date">2025 - 2026</span>
            </div>
            <div class="timeline-body">
              <p>Engineered a stair-ascending assistive mobility mechanism featuring custom torque reduction gearboxes, structural frame loading FEA, and local manufacturing integration.</p>
              <div class="timeline-tags">
                <span class="tag-sm">Kinematics</span>
                <span class="tag-sm">Structural FEA</span>
                <span class="tag-sm">Prototyping</span>
              </div>
            </div>
          </div>
        </div>

        <div class="timeline-item">
          <div class="timeline-icon"><i class="fa-solid fa-fire-flame-curved"></i></div>
          <div class="timeline-content card">
            <div class="timeline-header">
              <div>
                <div class="timeline-role">Thermal Systems Research Engineer</div>
                <div class="timeline-company">Thermal Energy Storage Sand Battery</div>
              </div>
              <span class="timeline-date">2025 - 2026</span>
            </div>
            <div class="timeline-body">
              <p>Designed a high-temperature insulated silica sand thermal storage vessel. Simulated internal heat exchanger coil fluid dynamics and velocity contours.</p>
              <div class="timeline-tags">
                <span class="tag-sm">CFD Analysis</span>
                <span class="tag-sm">Heat Transfer</span>
                <span class="tag-sm">Thermal Storage</span>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- FEATURED CAD PROJECTS -->
    <section id="projects">
      <div class="section-header">
        <div class="section-tag"><i class="fa-solid fa-folder-open"></i> Portfolio</div>
        <h2 class="section-title">Featured CAD & Engineering Projects</h2>
        <p class="section-subtitle">Explore selected mechanical assemblies, thermal CFD models, and manufacturing drawings.</p>
      </div>

      <div class="filter-menu">
        <button class="filter-btn active" data-filter="all">All Work</button>
        <button class="filter-btn" data-filter="mobility">Mobility Systems</button>
        <button class="filter-btn" data-filter="thermal">Thermal & CFD</button>
        <button class="filter-btn" data-filter="gears">Precision Gears</button>
      </div>

      <div class="projects-grid">
        <!-- Project 1 -->
        <div class="project-card card" data-category="mobility">
          <div class="project-img">
            <img src="https://images.unsplash.com/photo-1581092160607-ee22621dd758?auto=format&fit=crop&w=600&q=80" alt="Stair-Lifting Assistive Mechanism">
          </div>
          <div class="project-content">
            <div class="project-tags">
              <span class="tag">SolidWorks</span>
              <span class="tag">Kinematics</span>
              <span class="tag">FEA</span>
            </div>
            <h3 class="project-title">Stair-Ascending Mobility Chassis</h3>
            <p class="project-desc">Locally manufacturable stair-lifting mechanism with custom high-torque gearing and FEA load factor validation.</p>
            <button class="project-link" onclick="openSpecModal('Stair-Ascending Mobility Chassis', 'AL 6061-T6 Frame', '3.2 FEA Safety Factor', 'SolidWorks / Motion Study', '±0.05 mm')">View Engineering Specs <i class="fa-solid fa-arrow-right"></i></button>
          </div>
        </div>

        <!-- Project 2 -->
        <div class="project-card card" data-category="thermal">
          <div class="project-img">
            <img src="https://images.unsplash.com/photo-1531403009284-440f080d1e12?auto=format&fit=crop&w=600&q=80" alt="Sand Battery Thermal Vessel">
          </div>
          <div class="project-content">
            <div class="project-tags">
              <span class="tag">CFD</span>
              <span class="tag">Heat Transfer</span>
              <span class="tag">Thermal Storage</span>
            </div>
            <h3 class="project-title">Sand Thermal Energy Battery</h3>
            <p class="project-desc">High-temperature silica sand energy storage unit equipped with internal heat exchanger coil flow contours.</p>
            <button class="project-link" onclick="openSpecModal('Sand Thermal Energy Battery', 'Insulated Mild Steel + Silica Sand', 'Flow & Heat Transfer Simulation', 'CFD / ANSYS', 'Sealed Thermal Fit')">View Engineering Specs <i class="fa-solid fa-arrow-right"></i></button>
          </div>
        </div>

        <!-- Project 3 -->
        <div class="project-card card" data-category="gears">
          <div class="project-img">
            <img src="https://images.unsplash.com/photo-1581092580497-e0d23cbdf1dc?auto=format&fit=crop&w=600&q=80" alt="Involute Inspection Arbor">
          </div>
          <div class="project-content">
            <div class="project-tags">
              <span class="tag">Involute Gear</span>
              <span class="tag">MATLAB</span>
              <span class="tag">GD&T</span>
            </div>
            <h3 class="project-title">Involute Gear Hobbing Arbor</h3>
            <p class="project-desc">Custom arbor engineered with exact mathematical pitch diameter scripts and tight tolerance GD&T callouts.</p>
            <button class="project-link" onclick="openSpecModal('Involute Gear Hobbing Arbor', 'Tool Steel (HRC 58-60)', 'Pitch Dia Profile Scripts', 'MATLAB / AutoCAD', '±0.01 mm')">View Engineering Specs <i class="fa-solid fa-arrow-right"></i></button>
          </div>
        </div>
      </div>

      <!-- MANUFACTURING DRAWINGS GALLERY -->
      <div style="margin-top: 4rem;">
        <h3 style="font-size: 1.5rem; font-weight: 800; color: var(--secondary); margin-bottom: 1rem;">2D GD&T Drawings & Renders Gallery</h3>
        <div class="drawings-grid">
          <div class="drawing-item">
            <img src="https://images.unsplash.com/photo-1581092335397-9583fe92d232?auto=format&fit=crop&w=500&q=80" alt="2D GD&T Technical Drawing Sheet">
            <div class="drawing-overlay">
              <i class="fa-solid fa-magnifying-glass-plus" style="font-size: 1.5rem; margin-bottom: 8px;"></i>
              <strong>GD&T Assembly Drawing</strong>
              <small style="font-size: 0.75rem;">ASME Y14.5 Compliant</small>
            </div>
          </div>

          <div class="drawing-item">
            <img src="https://images.unsplash.com/photo-1581091226825-a6a2a5aee158?auto=format&fit=crop&w=500&q=80" alt="Photorealistic 3D Model Render">
            <div class="drawing-overlay">
              <i class="fa-solid fa-magnifying-glass-plus" style="font-size: 1.5rem; margin-bottom: 8px;"></i>
              <strong>Photorealistic 3D Render</strong>
              <small style="font-size: 0.75rem;">KeyShot / SolidWorks Visualize</small>
            </div>
          </div>

          <div class="drawing-item">
            <img src="https://images.unsplash.com/photo-1581092580497-e0d23cbdf1dc?auto=format&fit=crop&w=500&q=80" alt="Gear Profile Geometry Drawing">
            <div class="drawing-overlay">
              <i class="fa-solid fa-magnifying-glass-plus" style="font-size: 1.5rem; margin-bottom: 8px;"></i>
              <strong>Involute Profile Geometry</strong>
              <small style="font-size: 0.75rem;">Pitch Diameter Blueprint</small>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- CLIENT & PROFESSOR TESTIMONIALS -->
    <section id="testimonials">
      <div class="section-header">
        <div class="section-tag"><i class="fa-solid fa-comment-dots"></i> Endorsements</div>
        <h2 class="section-title">Client & Academic Feedback</h2>
        <p class="section-subtitle">What faculty mentors and consulting clients say about my work quality.</p>
      </div>

      <div class="testimonials-grid">
        <div class="testimonial-card card">
          <i class="fa-solid fa-quote-left quote-icon"></i>
          <p class="testimonial-text">"Rafay delivered flawless DFM-ready CAD drawings for our mechanical assembly. His attention to geometric tolerances saved us significant re-machining costs."</p>
          <div class="author-group">
            <div class="author-avatar">3D</div>
            <div class="author-details">
              <h4>Industrial Design Client</h4>
              <span>3D Mech Design Client</span>
            </div>
          </div>
        </div>

        <div class="testimonial-card card">
          <i class="fa-solid fa-quote-left quote-icon"></i>
          <p class="testimonial-text">"His work on the Thermal Energy Storage sand battery prototype showed deep understanding of both fluid flow CFD and solid modeling."</p>
          <div class="author-group">
            <div class="author-avatar">DU</div>
            <div class="author-details">
              <h4>Senior Faculty Advisor</h4>
              <span>DHA Suffa University</span>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- CONTACT SECTION -->
    <section id="contact">
      <div class="section-header">
        <div class="section-tag"><i class="fa-solid fa-paper-plane"></i> Get In Touch</div>
        <h2 class="section-title">Let's Discuss Your CAD Project</h2>
        <p class="section-subtitle">Have a mechanical design requirement, gear calculation task, or CFD simulation need? Reach out today.</p>
      </div>

      <div class="contact-container">
        <div class="contact-info">
          <p>Available for freelance CAD design, mechanical engineering consultations, and full 3D assembly modeling projects.</p>
          
          <div class="info-list">
            <div class="info-item">
              <div class="info-icon"><i class="fa-solid fa-briefcase"></i></div>
              <div>
                <small style="color:var(--text-muted)">Consultancy Brand</small>
                <div style="font-weight: 700; color: var(--secondary);">3D Mech Design</div>
              </div>
            </div>

            <div class="info-item">
              <div class="info-icon"><i class="fa-solid fa-location-dot"></i></div>
              <div>
                <small style="color:var(--text-muted)">Location</small>
                <div style="font-weight: 700; color: var(--secondary);">Karachi, Pakistan / Remote Worldwide</div>
              </div>
            </div>

            <div class="info-item">
              <div class="info-icon"><i class="fa-solid fa-envelope"></i></div>
              <div>
                <small style="color:var(--text-muted)">Email Address</small>
                <div style="font-weight: 700; color: var(--secondary);">rafay.yousuf.mech@gmail.com</div>
              </div>
            </div>
          </div>
        </div>

        <form class="contact-form card" onsubmit="event.preventDefault(); alert('Thank you! Your message has been sent successfully.');">
          <div class="form-group">
            <label for="name">Your Name / Organization</label>
            <input type="text" id="name" placeholder="John Doe" required>
          </div>

          <div class="form-group">
            <label for="email">Your Email Address</label>
            <input type="email" id="email" placeholder="john@example.com" required>
          </div>

          <div class="form-group">
            <label for="message">Project Requirements</label>
            <textarea id="message" rows="4" placeholder="Describe your CAD modeling, gear calculation, or CFD needs..." required></textarea>
          </div>

          <button type="submit" class="btn btn-primary"><i class="fa-solid fa-paper-plane"></i> Send Specifications</button>
        </form>
      </div>
    </section>
  </main>

  <!-- LIGHTBOX SPEC MODAL -->
  <div class="modal" id="specModal">
    <div class="modal-container card">
      <span class="close-modal" onclick="closeSpecModal()">&times;</span>
      <h3 class="modal-title" id="mTitle">Project Specifications</h3>
      <table class="spec-table">
        <tr><td>Material Specification:</td><td id="mMat">AL 6061-T6</td></tr>
        <tr><td>Stress & FEA Status:</td><td id="mAnalysis">Passed DFM Verification</td></tr>
        <tr><td>Software Stack:</td><td id="mStack">SolidWorks / ANSYS</td></tr>
        <tr><td>Machining Tolerance:</td><td id="mTol">±0.02 mm</td></tr>
      </table>
      <button class="btn btn-secondary" onclick="closeSpecModal()">Close Spec Sheet</button>
    </div>
  </div>

  <!-- FOOTER -->
  <footer>
    <div>&copy; 2026 Abdur Rafay Yousuf • 3D Mech Design. All rights reserved.</div>
    <div class="social-links">
      <a href="https://github.com" target="_blank" title="GitHub"><i class="fa-brands fa-github"></i></a>
      <a href="https://linkedin.com" target="_blank" title="LinkedIn"><i class="fa-brands fa-linkedin"></i></a>
      <a href="mailto:rafay.yousuf.mech@gmail.com" title="Email"><i class="fa-solid fa-envelope"></i></a>
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

    // Project Category Filtering System
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

    // Technical Spec Modal Handler
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
