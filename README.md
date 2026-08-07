**<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Abdur Rafay Yousuf | Premium Engineering Portfolio</title>
    
    <!-- External Assets -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@300;400;500;600;700;800&family=Plus+Jakarta+Sans:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">

    <style>
        /* ==========================================================================
           0. CSS RESET & GLOBAL VARIABLES
           ========================================================================== */
        *, *::before, *::after {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            cursor: none; /* Custom cursor implementation */
        }

        html {
            scroll-behavior: smooth;
            scroll-padding-top: 100px;
        }

        :root {
            /* Light Theme (Default) */
            --bg-base: #f8fafc;
            --bg-gradient-1: #eef6ff;
            --bg-gradient-2: #f1f5f9;
            --text-primary: #0f172a;
            --text-secondary: #475569;
            --text-muted: #64748b;
            
            --brand-primary: #2563eb;
            --brand-primary-hover: #1d4ed8;
            --brand-primary-light: rgba(37, 99, 235, 0.1);
            --brand-secondary: #0f172a;
            --brand-accent: #8b5cf6;
            --brand-success: #059669;
            --brand-warning: #d97706;
            --brand-danger: #e11d48;

            --glass-bg: rgba(255, 255, 255, 0.65);
            --glass-border: rgba(15, 23, 42, 0.1);
            --glass-highlight: rgba(255, 255, 255, 0.8);
            
            --grid-line: rgba(37, 99, 235, 0.05);
            --particle-color: rgba(37, 99, 235, 0.2);
            
            --shadow-sm: 0 2px 4px rgba(0,0,0,0.02);
            --shadow-md: 0 10px 40px rgba(15, 23, 42, 0.06);
            --shadow-lg: 0 20px 60px rgba(37, 99, 235, 0.12);
            --shadow-glow: 0 0 30px rgba(37, 99, 235, 0.3);
            
            --radius-sm: 8px;
            --radius-md: 16px;
            --radius-lg: 24px;
            --radius-full: 9999px;

            --font-sans: 'Plus Jakarta Sans', sans-serif;
            --font-mono: 'JetBrains Mono', monospace;
            
            --transition-fast: 0.2s cubic-bezier(0.4, 0, 0.2, 1);
            --transition-normal: 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            --transition-slow: 0.8s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            
            --z-negative: -1;
            --z-normal: 1;
            --z-sticky: 100;
            --z-drawer: 200;
            --z-modal: 300;
            --z-popover: 400;
            --z-toast: 500;
            --z-cursor: 9999;
        }

        [data-theme="dark"] {
            /* Dark Theme Overrides */
            --bg-base: #030712;
            --bg-gradient-1: #0f172a;
            --bg-gradient-2: #020617;
            --text-primary: #f8fafc;
            --text-secondary: #cbd5e1;
            --text-muted: #94a3b8;
            
            --brand-primary: #3b82f6;
            --brand-primary-hover: #60a5fa;
            --brand-primary-light: rgba(59, 130, 246, 0.15);
            --brand-secondary: #f8fafc;
            --brand-accent: #a855f7;
            --brand-success: #10b981;
            
            --glass-bg: rgba(15, 23, 42, 0.55);
            --glass-border: rgba(255, 255, 255, 0.08);
            --glass-highlight: rgba(255, 255, 255, 0.05);
            
            --grid-line: rgba(59, 130, 246, 0.08);
            --particle-color: rgba(96, 165, 250, 0.15);
            
            --shadow-md: 0 10px 40px rgba(0, 0, 0, 0.4);
            --shadow-lg: 0 20px 60px rgba(0, 0, 0, 0.6);
            --shadow-glow: 0 0 30px rgba(59, 130, 246, 0.2);
        }

        /* ==========================================================================
           1. BASE STYLES & TYPOGRAPHY
           ========================================================================== */
        body {
            font-family: var(--font-sans);
            color: var(--text-primary);
            background-color: var(--bg-base);
            line-height: 1.6;
            overflow-x: hidden;
            position: relative;
            min-height: 100vh;
        }

        /* Custom Scrollbar */
        ::-webkit-scrollbar { width: 12px; }
        ::-webkit-scrollbar-track { background: var(--bg-base); }
        ::-webkit-scrollbar-thumb { background: var(--glass-border); border-radius: var(--radius-full); border: 3px solid var(--bg-base); }
        ::-webkit-scrollbar-thumb:hover { background: var(--brand-primary); }

        /* Typography Hierarchy */
        h1, h2, h3, h4, h5, h6 { font-weight: 800; line-height: 1.2; color: var(--text-primary); letter-spacing: -0.02em; }
        p { margin-bottom: 1rem; color: var(--text-secondary); }
        a { color: var(--brand-primary); text-decoration: none; transition: var(--transition-fast); }
        strong { font-weight: 700; color: var(--text-primary); }

        .text-gradient {
            background: linear-gradient(135deg, var(--brand-primary), var(--brand-accent), var(--brand-primary));
            background-size: 200% auto;
            color: transparent;
            -webkit-background-clip: text;
            background-clip: text;
            animation: gradientText 5s linear infinite;
        }

        .mono { font-family: var(--font-mono); }

        /* ==========================================================================
           2. ADVANCED BACKGROUND ENGINE (Aurora + Mesh + Particles)
           ========================================================================== */
        .bg-engine {
            position: fixed;
            inset: 0;
            z-index: var(--z-negative);
            pointer-events: none;
            overflow: hidden;
            background: linear-gradient(135deg, var(--bg-base), var(--bg-gradient-1));
        }

        .bg-mesh {
            position: absolute;
            inset: 0;
            background-image: 
                radial-gradient(at 0% 0%, rgba(37,99,235,0.15) 0px, transparent 50%),
                radial-gradient(at 100% 0%, rgba(139,92,246,0.15) 0px, transparent 50%),
                radial-gradient(at 100% 100%, rgba(6,182,212,0.15) 0px, transparent 50%),
                radial-gradient(at 0% 100%, rgba(37,99,235,0.15) 0px, transparent 50%);
            filter: blur(80px);
            opacity: 0.8;
            animation: breatheMesh 20s ease-in-out infinite alternate;
        }

        .bg-grid {
            position: absolute;
            inset: 0;
            background-image: 
                linear-gradient(var(--grid-line) 1px, transparent 1px),
                linear-gradient(90deg, var(--grid-line) 1px, transparent 1px);
            background-size: 40px 40px;
            mask-image: radial-gradient(ellipse 80% 80% at 50% 50%, black 20%, transparent 80%);
            -webkit-mask-image: radial-gradient(ellipse 80% 80% at 50% 50%, black 20%, transparent 80%);
            opacity: 0.5;
        }

        #particle-canvas {
            position: absolute;
            inset: 0;
            width: 100%;
            height: 100%;
        }

        /* ==========================================================================
           3. CUSTOM INTERACTIVE CURSOR
           ========================================================================== */
        .cursor-dot {
            width: 8px; height: 8px;
            background: var(--brand-primary);
            border-radius: 50%;
            position: fixed;
            top: 0; left: 0;
            transform: translate(-50%, -50%);
            z-index: var(--z-cursor);
            pointer-events: none;
            transition: width 0.2s, height 0.2s, background 0.2s;
        }

        .cursor-outline {
            width: 40px; height: 40px;
            border: 2px solid var(--brand-primary-light);
            border-radius: 50%;
            position: fixed;
            top: 0; left: 0;
            transform: translate(-50%, -50%);
            z-index: var(--z-cursor);
            pointer-events: none;
            transition: width 0.2s, height 0.2s, border-color 0.2s;
            transition-timing-function: ease-out;
        }

        body:hover .cursor-dot, body:hover .cursor-outline { opacity: 1; }
        
        .cursor-hover .cursor-dot {
            width: 50px; height: 50px;
            background: var(--brand-primary-light);
            border: 1px solid var(--brand-primary);
            backdrop-filter: blur(2px);
        }
        .cursor-hover .cursor-outline { width: 0; height: 0; opacity: 0; }

        /* ==========================================================================
           4. PRELOADER (Engineering Gear)
           ========================================================================== */
        .preloader {
            position: fixed; inset: 0;
            background: var(--bg-base);
            z-index: 99999;
            display: flex; flex-direction: column;
            justify-content: center; align-items: center;
            transition: opacity 0.8s ease, visibility 0.8s;
        }
        .preloader.hidden { opacity: 0; visibility: hidden; }

        .gear-loader {
            width: 80px; height: 80px;
            border: 6px dashed var(--brand-primary);
            border-radius: 50%;
            animation: spinGear 4s linear infinite;
            margin-bottom: 20px;
            position: relative;
        }
        .gear-loader::before {
            content: ''; position: absolute;
            inset: 10px; border: 4px solid var(--brand-accent);
            border-radius: 50%;
            animation: spinGear 2s linear infinite reverse;
        }
        .loading-text {
            font-family: var(--font-mono); font-size: 14px;
            color: var(--brand-primary); letter-spacing: 4px;
            text-transform: uppercase;
            animation: pulse 1.5s ease-in-out infinite;
        }

        /* ==========================================================================
           5. UI COMPONENTS (Glassmorphism, Buttons, Cards)
           ========================================================================== */
        .glass-panel {
            background: var(--glass-bg);
            backdrop-filter: blur(20px);
            -webkit-backdrop-filter: blur(20px);
            border: 1px solid var(--glass-border);
            border-radius: var(--radius-lg);
            box-shadow: var(--shadow-md);
            position: relative;
            overflow: hidden;
        }
        .glass-panel::after {
            content: ''; position: absolute; top: 0; left: 0; right: 0; height: 1px;
            background: linear-gradient(90deg, transparent, var(--glass-highlight), transparent);
        }

        .btn {
            display: inline-flex; align-items: center; justify-content: center;
            gap: 10px; padding: 14px 28px; border-radius: var(--radius-md);
            font-family: var(--font-sans); font-weight: 600; font-size: 1rem;
            cursor: pointer; transition: var(--transition-normal);
            border: 1px solid transparent; text-decoration: none;
            position: relative; overflow: hidden;
            z-index: 1;
        }
        
        .btn-primary {
            background: linear-gradient(135deg, var(--brand-primary), var(--brand-accent));
            color: #ffffff !important;
            box-shadow: 0 4px 15px rgba(37, 99, 235, 0.3);
            border: 1px solid rgba(255,255,255,0.1);
        }
        .btn-primary::before {
            content: ''; position: absolute; inset: 0;
            background: linear-gradient(135deg, var(--brand-accent), var(--brand-primary));
            opacity: 0; transition: var(--transition-normal); z-index: -1;
        }
        .btn-primary:hover::before { opacity: 1; }
        .btn-primary:hover { transform: translateY(-3px) scale(1.02); box-shadow: var(--shadow-lg); }

        .btn-secondary {
            background: var(--glass-bg); color: var(--text-primary);
            border-color: var(--glass-border); backdrop-filter: blur(10px);
        }
        .btn-secondary:hover {
            border-color: var(--brand-primary); color: var(--brand-primary);
            background: var(--brand-primary-light); transform: translateY(-3px);
        }

        .btn-icon {
            width: 45px; height: 45px; padding: 0; border-radius: 50%;
            display: flex; align-items: center; justify-content: center;
            background: var(--glass-bg); border: 1px solid var(--glass-border);
            color: var(--text-primary); font-size: 1.2rem;
            transition: var(--transition-normal); backdrop-filter: blur(10px);
        }
        .btn-icon:hover {
            background: var(--brand-primary); color: white;
            border-color: var(--brand-primary); transform: translateY(-3px) rotate(10deg);
        }

        .badge {
            display: inline-flex; align-items: center; gap: 6px;
            padding: 6px 14px; border-radius: var(--radius-full);
            font-family: var(--font-mono); font-size: 0.75rem; font-weight: 600;
            background: var(--brand-primary-light); color: var(--brand-primary);
            border: 1px solid rgba(37, 99, 235, 0.2); text-transform: uppercase;
            letter-spacing: 1px;
        }

        /* Interactive 3D Tilt Wrapper */
        .js-tilt { transform-style: preserve-3d; transform: perspective(1000px); }
        .js-tilt-inner { transform: translateZ(30px); }

        /* ==========================================================================
           6. LAYOUT & NAVIGATION
           ========================================================================== */
        .container {
            width: 100%; max-width: 1400px; margin: 0 auto;
            padding: 0 5%; position: relative;
        }
        
        section { padding: 120px 0; position: relative; }

        .section-header { text-align: center; max-width: 700px; margin: 0 auto 60px auto; }
        .section-header .badge { margin-bottom: 20px; }
        .section-title { font-size: 3rem; margin-bottom: 20px; }
        .section-desc { font-size: 1.1rem; color: var(--text-muted); }

        /* Header / Navbar */
        header {
            position: fixed; top: 0; left: 0; width: 100%; height: 90px;
            display: flex; align-items: center; z-index: var(--z-sticky);
            transition: var(--transition-normal); border-bottom: 1px solid transparent;
        }
        header.scrolled {
            height: 75px; background: var(--glass-bg);
            backdrop-filter: blur(24px); border-bottom: 1px solid var(--glass-border);
            box-shadow: var(--shadow-sm);
        }

        .nav-wrapper { display: flex; justify-content: space-between; align-items: center; width: 100%; }
        
        .logo {
            font-family: var(--font-mono); font-size: 1.5rem; font-weight: 800;
            color: var(--text-primary); text-decoration: none; display: flex; align-items: center; gap: 10px;
        }
        .logo-icon {
            width: 40px; height: 40px; background: var(--brand-primary); color: white;
            border-radius: var(--radius-sm); display: flex; align-items: center; justify-content: center;
            font-size: 1.2rem; transform: rotate(45deg); transition: var(--transition-normal);
        }
        .logo-icon i { transform: rotate(-45deg); }
        .logo:hover .logo-icon { transform: rotate(135deg); border-radius: 50%; }

        .nav-links { display: flex; gap: 2.5rem; list-style: none; }
        .nav-link {
            font-size: 0.95rem; font-weight: 600; color: var(--text-secondary);
            text-decoration: none; transition: var(--transition-fast); position: relative;
        }
        .nav-link::after {
            content: ''; position: absolute; bottom: -5px; left: 0; width: 0; height: 2px;
            background: var(--brand-primary); transition: var(--transition-normal);
        }
        .nav-link:hover, .nav-link.active { color: var(--brand-primary); }
        .nav-link:hover::after, .nav-link.active::after { width: 100%; }

        .nav-actions { display: flex; align-items: center; gap: 15px; }
        
        .mobile-toggle {
            display: none; font-size: 1.5rem; color: var(--text-primary);
            background: none; border: none; cursor: pointer;
        }

        /* ==========================================================================
           7. HERO SECTION
           ========================================================================== */
        #hero {
            min-height: 100vh; display: flex; align-items: center;
            padding-top: 100px; padding-bottom: 50px;
        }
        
        .hero-grid {
            display: grid; grid-template-columns: 1.2fr 0.8fr;
            gap: 4rem; align-items: center;
        }

        .hero-content .badge { margin-bottom: 30px; animation: slideDown 1s ease forwards; opacity: 0; }
        .hero-title {
            font-size: clamp(3rem, 5vw, 4.5rem); line-height: 1.1;
            margin-bottom: 25px; opacity: 0; animation: slideUp 1s ease 0.2s forwards;
        }
        .typewriter-box { display: inline-block; color: var(--brand-primary); border-right: 3px solid var(--brand-primary); white-space: nowrap; overflow: hidden; animation: typing 3.5s steps(40, end), blink-caret .75s step-end infinite; }
        
        .hero-desc {
            font-size: 1.2rem; color: var(--text-muted); max-width: 600px;
            margin-bottom: 40px; opacity: 0; animation: slideUp 1s ease 0.4s forwards;
        }

        .hero-metrics {
            display: grid; grid-template-columns: repeat(3, 1fr);
            gap: 20px; margin-bottom: 40px;
            padding-top: 30px; border-top: 1px dashed var(--glass-border);
            opacity: 0; animation: slideUp 1s ease 0.6s forwards;
        }
        .metric { display: flex; flex-direction: column; gap: 5px; }
        .metric-value { font-family: var(--font-mono); font-size: 2rem; font-weight: 800; color: var(--text-primary); }
        .metric-label { font-size: 0.85rem; color: var(--text-muted); font-weight: 600; text-transform: uppercase; }

        .hero-btns {
            display: flex; gap: 15px; opacity: 0;
            animation: slideUp 1s ease 0.8s forwards;
        }

        /* Hero Image/Card 3D Composition */
        .hero-visual { position: relative; opacity: 0; animation: fadeIn 1.5s ease 1s forwards; }
        
        .profile-card {
            padding: 40px; text-align: center; z-index: 2;
        }
        .profile-img-wrap {
            width: 280px; height: 280px; margin: 0 auto 30px auto;
            border-radius: 50%; padding: 8px;
            background: linear-gradient(135deg, var(--brand-primary), var(--brand-accent));
            position: relative;
        }
        .profile-img-wrap::before {
            content: ''; position: absolute; inset: -20px;
            background: radial-gradient(circle, var(--brand-primary) 0%, transparent 70%);
            opacity: 0.3; filter: blur(30px); animation: pulseGlow 4s infinite alternate; z-index: -1;
        }
        .profile-img {
            width: 100%; height: 100%; border-radius: 50%;
            object-fit: cover; border: 4px solid var(--bg-base);
        }
        
        .profile-card h3 { font-size: 1.8rem; margin-bottom: 5px; }
        .profile-card p { font-family: var(--font-mono); color: var(--brand-primary); margin-bottom: 20px; }
        
        /* Floating elements in hero */
        .float-badge {
            position: absolute; background: var(--glass-bg); backdrop-filter: blur(10px);
            border: 1px solid var(--glass-border); padding: 12px 20px; border-radius: var(--radius-md);
            display: flex; align-items: center; gap: 12px; box-shadow: var(--shadow-md);
            z-index: 3; animation: float 6s ease-in-out infinite;
        }
        .float-1 { top: 10%; right: -20px; animation-delay: 0s; }
        .float-2 { bottom: 20%; left: -30px; animation-delay: 2s; }
        .float-icon { width: 40px; height: 40px; border-radius: 50%; background: var(--brand-primary-light); color: var(--brand-primary); display: flex; justify-content: center; align-items: center; font-size: 1.2rem; }
        .float-text { font-weight: 700; font-size: 0.9rem; display: flex; flex-direction: column; }
        .float-text span { font-size: 0.7rem; color: var(--text-muted); font-weight: 500; }

        /* ==========================================================================
           8. ABOUT & PHILOSOPHY
           ========================================================================== */
        .about-grid {
            display: grid; grid-template-columns: 1fr 1fr;
            gap: 4rem; align-items: center;
        }
        .about-image-wrapper { position: relative; }
        .about-image { width: 100%; border-radius: var(--radius-lg); border: 1px solid var(--glass-border); box-shadow: var(--shadow-lg); }
        .about-exp-badge {
            position: absolute; bottom: -20px; right: -20px;
            background: var(--brand-primary); color: white; padding: 30px;
            border-radius: var(--radius-full); text-align: center;
            border: 8px solid var(--bg-base); box-shadow: var(--shadow-md);
        }
        .about-exp-badge h4 { font-size: 2.5rem; color: white; margin: 0; }
        .about-exp-badge span { font-size: 0.85rem; font-weight: 600; font-family: var(--font-mono); }

        .philosophy-steps {
            display: grid; grid-template-columns: repeat(2, 1fr); gap: 20px;
            margin-top: 40px;
        }
        .step-card { padding: 25px; transition: var(--transition-normal); border: 1px solid transparent; }
        .step-card:hover { border-color: var(--brand-primary); transform: translateY(-5px); background: var(--brand-primary-light); }
        .step-icon { font-size: 2rem; color: var(--brand-primary); margin-bottom: 15px; }
        .step-card h4 { margin-bottom: 10px; font-size: 1.2rem; }
        .step-card p { font-size: 0.9rem; margin: 0; }

        /* ==========================================================================
           9. SKILLS MATRIX
           ========================================================================== */
        .skills-container {
            display: grid; grid-template-columns: 1.2fr 0.8fr; gap: 3rem;
        }
        
        .skills-list { display: flex; flex-direction: column; gap: 25px; }
        .skill-item { background: var(--glass-bg); padding: 25px; border-radius: var(--radius-md); border: 1px solid var(--glass-border); }
        .skill-header { display: flex; justify-content: space-between; align-items: center; margin-bottom: 15px; }
        .skill-title { display: flex; align-items: center; gap: 15px; font-weight: 700; font-size: 1.1rem; }
        .skill-icon { width: 45px; height: 45px; border-radius: 10px; background: var(--brand-primary-light); color: var(--brand-primary); display: flex; justify-content: center; align-items: center; font-size: 1.2rem; }
        .skill-pct { font-family: var(--font-mono); font-weight: 800; color: var(--brand-primary); }
        
        .progress-track { width: 100%; height: 8px; background: var(--glass-border); border-radius: var(--radius-full); overflow: hidden; position: relative; }
        .progress-fill { position: absolute; top: 0; left: 0; height: 100%; background: linear-gradient(90deg, var(--brand-primary), var(--brand-accent)); border-radius: var(--radius-full); width: 0; transition: width 1.5s cubic-bezier(0.175, 0.885, 0.32, 1.275); }

        .tools-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 15px; }
        .tool-card {
            background: var(--glass-bg); border: 1px solid var(--glass-border);
            padding: 20px; border-radius: var(--radius-md); text-align: center;
            transition: var(--transition-normal);
        }
        .tool-card:hover { border-color: var(--brand-primary); transform: translateY(-5px) scale(1.05); }
        .tool-card i { font-size: 2.5rem; color: var(--text-primary); margin-bottom: 15px; transition: color 0.3s; }
        .tool-card:hover i { color: var(--brand-primary); }
        .tool-card span { display: block; font-size: 0.85rem; font-weight: 600; font-family: var(--font-mono); }

        /* ==========================================================================
           10. EXPERIENCE & EDUCATION TIMELINE
           ========================================================================== */
        .timeline-wrapper { position: relative; max-width: 1000px; margin: 0 auto; }
        .timeline-wrapper::before {
            content: ''; position: absolute; top: 0; left: 50%; transform: translateX(-50%);
            width: 2px; height: 100%; background: var(--glass-border);
        }
        
        .timeline-item { width: 100%; margin-bottom: 50px; position: relative; display: flex; justify-content: space-between; align-items: center; }
        .timeline-item:nth-child(even) { flex-direction: row-reverse; }
        
        .timeline-content { width: calc(50% - 40px); }
        .timeline-dot {
            width: 24px; height: 24px; background: var(--brand-primary); border: 4px solid var(--bg-base);
            border-radius: 50%; position: absolute; left: 50%; transform: translateX(-50%); z-index: 2;
            box-shadow: 0 0 0 4px var(--brand-primary-light);
        }
        
        .timeline-card { padding: 30px; text-align: left; }
        .timeline-date { font-family: var(--font-mono); color: var(--brand-primary); font-size: 0.9rem; font-weight: 600; margin-bottom: 10px; display: inline-block; padding: 5px 12px; background: var(--brand-primary-light); border-radius: var(--radius-sm); }
        .timeline-title { font-size: 1.4rem; margin-bottom: 5px; }
        .timeline-company { font-weight: 600; color: var(--text-secondary); margin-bottom: 15px; font-size: 1rem; }
        .timeline-tags { display: flex; flex-wrap: wrap; gap: 8px; margin-top: 15px; }
        .timeline-tags span { font-size: 0.75rem; padding: 4px 10px; background: var(--bg-base); border: 1px solid var(--glass-border); border-radius: var(--radius-sm); color: var(--text-muted); }

        /* ==========================================================================
           11. MASSIVE PORTFOLIO SECTION
           ========================================================================== */
        .portfolio-filters { display: flex; justify-content: center; flex-wrap: wrap; gap: 15px; margin-bottom: 50px; }
        .filter-btn {
            background: var(--glass-bg); border: 1px solid var(--glass-border);
            padding: 10px 24px; border-radius: var(--radius-full);
            font-family: var(--font-mono); font-weight: 600; font-size: 0.9rem;
            color: var(--text-secondary); cursor: pointer; transition: var(--transition-normal);
        }
        .filter-btn.active, .filter-btn:hover {
            background: var(--brand-primary); color: white; border-color: var(--brand-primary);
            box-shadow: 0 5px 15px rgba(37, 99, 235, 0.3); transform: translateY(-2px);
        }

        .portfolio-grid {
            display: grid; grid-template-columns: repeat(auto-fill, minmax(380px, 1fr));
            gap: 30px;
        }

        .portfolio-card {
            display: flex; flex-direction: column; overflow: hidden;
            padding: 0; group: relative; cursor: none;
        }
        
        .port-img-wrap {
            width: 100%; height: 260px; overflow: hidden; position: relative;
            background: var(--glass-border);
        }
        .port-img-wrap img {
            width: 100%; height: 100%; object-fit: cover;
            transition: transform 0.6s cubic-bezier(0.175, 0.885, 0.32, 1.275);
        }
        .portfolio-card:hover .port-img-wrap img { transform: scale(1.1) rotate(2deg); }
        
        .port-overlay {
            position: absolute; inset: 0; background: rgba(15, 23, 42, 0.7);
            display: flex; justify-content: center; align-items: center;
            opacity: 0; transition: var(--transition-normal); backdrop-filter: blur(5px);
        }
        .portfolio-card:hover .port-overlay { opacity: 1; }
        .port-view-btn {
            width: 60px; height: 60px; background: var(--brand-primary); color: white;
            border-radius: 50%; display: flex; justify-content: center; align-items: center;
            font-size: 1.5rem; transform: translateY(20px); transition: var(--transition-normal);
        }
        .portfolio-card:hover .port-view-btn { transform: translateY(0); }

        .port-content { padding: 25px; flex-grow: 1; display: flex; flex-direction: column; }
        .port-cat { font-family: var(--font-mono); font-size: 0.75rem; color: var(--brand-primary); font-weight: 700; margin-bottom: 10px; text-transform: uppercase; }
        .port-title { font-size: 1.3rem; margin-bottom: 10px; }
        .port-desc { font-size: 0.9rem; color: var(--text-muted); margin-bottom: 20px; flex-grow: 1; }
        .port-meta { display: flex; justify-content: space-between; align-items: center; border-top: 1px solid var(--glass-border); padding-top: 15px; }
        .port-tool { display: flex; gap: 10px; color: var(--text-secondary); font-size: 1.1rem; }

        /* ==========================================================================
           12. SERVICES & PRICING
           ========================================================================== */
        .pricing-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 30px; }
        .price-card {
            padding: 40px 30px; text-align: center; position: relative;
            display: flex; flex-direction: column;
        }
        .price-card.featured {
            border-color: var(--brand-primary);
            box-shadow: 0 10px 50px rgba(37, 99, 235, 0.15);
            transform: scale(1.05); z-index: 2;
        }
        .featured-badge {
            position: absolute; top: -15px; left: 50%; transform: translateX(-50%);
            background: var(--brand-primary); color: white; padding: 5px 15px;
            border-radius: var(--radius-full); font-size: 0.8rem; font-weight: 700;
        }
        .price-icon { font-size: 3rem; color: var(--brand-primary); margin-bottom: 20px; }
        .price-title { font-size: 1.5rem; margin-bottom: 15px; }
        .price-amount { font-family: var(--font-mono); font-size: 2.5rem; font-weight: 800; color: var(--text-primary); margin-bottom: 20px; }
        .price-amount span { font-size: 1rem; color: var(--text-muted); font-weight: 500; }
        .price-features { list-style: none; margin-bottom: 30px; text-align: left; flex-grow: 1; }
        .price-features li { margin-bottom: 15px; display: flex; gap: 10px; color: var(--text-secondary); font-size: 0.95rem; }
        .price-features i { color: var(--brand-success); margin-top: 4px; }
        .price-features .disabled { color: var(--glass-border); }
        .price-features .disabled i { color: var(--glass-border); }

        /* ==========================================================================
           13. TESTIMONIALS SLIDER
           ========================================================================== */
        .testimonial-container { max-width: 900px; margin: 0 auto; position: relative; }
        .testi-slider { display: flex; overflow: hidden; }
        .testi-slide { min-width: 100%; padding: 20px; transition: transform 0.5s ease; }
        .testi-card { padding: 50px; text-align: center; }
        .quote-icon { font-size: 3rem; color: var(--brand-primary-light); margin-bottom: 20px; }
        .testi-text { font-size: 1.2rem; font-style: italic; color: var(--text-primary); margin-bottom: 30px; line-height: 1.8; }
        .testi-author { display: flex; flex-direction: column; align-items: center; gap: 10px; }
        .author-img { width: 70px; height: 70px; border-radius: 50%; background: var(--brand-primary); color: white; display: flex; justify-content: center; align-items: center; font-size: 1.5rem; font-weight: 700; border: 3px solid var(--bg-base); box-shadow: var(--shadow-sm); }
        .author-info h4 { font-size: 1.1rem; margin-bottom: 2px; }
        .author-info span { font-size: 0.85rem; color: var(--brand-primary); font-family: var(--font-mono); }
        
        .slider-controls { display: flex; justify-content: center; gap: 15px; margin-top: 30px; }
        .slider-btn { width: 50px; height: 50px; border-radius: 50%; border: 1px solid var(--glass-border); background: var(--glass-bg); color: var(--text-primary); cursor: pointer; transition: var(--transition-fast); }
        .slider-btn:hover { background: var(--brand-primary); color: white; border-color: var(--brand-primary); }

        /* ==========================================================================
           14. FAQ ACCORDION
           ========================================================================== */
        .faq-container { max-width: 800px; margin: 0 auto; }
        .accordion-item { margin-bottom: 15px; border: 1px solid var(--glass-border); border-radius: var(--radius-md); background: var(--glass-bg); overflow: hidden; }
        .accordion-header { padding: 20px 25px; display: flex; justify-content: space-between; align-items: center; cursor: pointer; font-weight: 700; font-size: 1.1rem; transition: var(--transition-fast); }
        .accordion-header:hover { color: var(--brand-primary); }
        .accordion-icon { font-size: 1.2rem; transition: transform 0.3s ease; color: var(--brand-primary); }
        .accordion-item.active .accordion-icon { transform: rotate(180deg); }
        .accordion-content { padding: 0 25px; max-height: 0; overflow: hidden; transition: max-height 0.3s ease, padding 0.3s ease; color: var(--text-secondary); }
        .accordion-item.active .accordion-content { padding: 0 25px 20px 25px; max-height: 500px; }

        /* ==========================================================================
           15. CONTACT & FOOTER
           ========================================================================== */
        .contact-grid { display: grid; grid-template-columns: 1fr 1.5fr; gap: 4rem; }
        .contact-info { display: flex; flex-direction: column; gap: 30px; }
        .contact-card { padding: 25px; display: flex; align-items: flex-start; gap: 20px; }
        .contact-icon { width: 60px; height: 60px; border-radius: var(--radius-md); background: var(--brand-primary-light); color: var(--brand-primary); display: flex; justify-content: center; align-items: center; font-size: 1.5rem; flex-shrink: 0; }
        .contact-details h4 { margin-bottom: 5px; font-size: 1.2rem; }
        .contact-details p, .contact-details a { color: var(--text-secondary); font-size: 1rem; text-decoration: none; }
        
        .contact-form-wrap { padding: 40px; }
        .form-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 20px; margin-bottom: 20px; }
        .input-group { display: flex; flex-direction: column; gap: 8px; }
        .input-group label { font-size: 0.9rem; font-weight: 600; color: var(--text-primary); }
        .form-control {
            padding: 15px 20px; border-radius: var(--radius-md);
            background: var(--bg-base); border: 1px solid var(--glass-border);
            color: var(--text-primary); font-family: var(--font-sans); font-size: 1rem;
            transition: var(--transition-fast); width: 100%;
        }
        .form-control:focus { outline: none; border-color: var(--brand-primary); box-shadow: 0 0 0 4px var(--brand-primary-light); }
        textarea.form-control { resize: vertical; min-height: 150px; }
        .form-submit { margin-top: 10px; width: 100%; }

        footer {
            background: var(--bg-gradient-1); border-top: 1px solid var(--glass-border);
            padding: 80px 0 30px 0; margin-top: 100px;
        }
        .footer-grid { display: grid; grid-template-columns: 2fr 1fr 1fr; gap: 4rem; margin-bottom: 60px; }
        .footer-brand p { margin-top: 20px; color: var(--text-muted); max-width: 400px; }
        .social-links { display: flex; gap: 15px; margin-top: 25px; }
        .footer-title { font-size: 1.2rem; margin-bottom: 25px; color: var(--text-primary); }
        .footer-links { list-style: none; display: flex; flex-direction: column; gap: 12px; }
        .footer-links a { color: var(--text-muted); transition: var(--transition-fast); }
        .footer-links a:hover { color: var(--brand-primary); padding-left: 5px; }
        .footer-bottom { display: flex; justify-content: space-between; align-items: center; padding-top: 30px; border-top: 1px solid var(--glass-border); color: var(--text-muted); font-size: 0.9rem; }

        /* Modals */
        .modal { position: fixed; inset: 0; background: rgba(0,0,0,0.8); backdrop-filter: blur(8px); z-index: var(--z-modal); display: flex; justify-content: center; align-items: center; opacity: 0; visibility: hidden; transition: var(--transition-normal); padding: 20px; }
        .modal.active { opacity: 1; visibility: visible; }
        .modal-content { width: 100%; max-width: 800px; max-height: 90vh; overflow-y: auto; padding: 40px; position: relative; transform: translateY(30px); transition: var(--transition-normal); }
        .modal.active .modal-content { transform: translateY(0); }
        .modal-close { position: absolute; top: 20px; right: 20px; width: 40px; height: 40px; border-radius: 50%; background: var(--bg-base); border: 1px solid var(--glass-border); color: var(--text-primary); display: flex; justify-content: center; align-items: center; font-size: 1.5rem; cursor: pointer; transition: var(--transition-fast); }
        .modal-close:hover { background: var(--brand-danger); color: white; border-color: var(--brand-danger); transform: rotate(90deg); }

        /* ==========================================================================
           16. ANIMATIONS & MEDIA QUERIES
           ========================================================================== */
        @keyframes slideUp { from { opacity: 0; transform: translateY(40px); } to { opacity: 1; transform: translateY(0); } }
        @keyframes slideDown { from { opacity: 0; transform: translateY(-40px); } to { opacity: 1; transform: translateY(0); } }
        @keyframes fadeIn { from { opacity: 0; } to { opacity: 1; } }
        @keyframes spinGear { 100% { transform: rotate(360deg); } }
        @keyframes pulse { 0%, 100% { opacity: 1; } 50% { opacity: 0.5; } }
        @keyframes pulseGlow { 0% { transform: scale(0.95); opacity: 0.2; } 100% { transform: scale(1.1); opacity: 0.5; } }
        @keyframes float { 0%, 100% { transform: translateY(0); } 50% { transform: translateY(-20px); } }
        @keyframes breatheMesh { 0% { filter: blur(80px) brightness(1); } 100% { filter: blur(100px) brightness(1.2); } }
        @keyframes gradientText { 0% { background-position: 0% center; } 100% { background-position: 200% center; } }
        
        /* Typewriter Animation */
        @keyframes typing { from { width: 0 } to { width: 100% } }
        @keyframes blink-caret { from, to { border-color: transparent } 50% { border-color: var(--brand-primary); } }

        /* Scroll Reveals */
        .reveal { opacity: 0; transform: translateY(50px); transition: all 0.8s cubic-bezier(0.175, 0.885, 0.32, 1.275); }
        .reveal.active { opacity: 1; transform: translateY(0); }
        .reveal-left { opacity: 0; transform: translateX(-50px); transition: all 0.8s cubic-bezier(0.175, 0.885, 0.32, 1.275); }
        .reveal-left.active { opacity: 1; transform: translateX(0); }
        .reveal-right { opacity: 0; transform: translateX(50px); transition: all 0.8s cubic-bezier(0.175, 0.885, 0.32, 1.275); }
        .reveal-right.active { opacity: 1; transform: translateX(0); }

        /* Responsive Breakpoints */
        @media (max-width: 1200px) {
            .hero-title { font-size: 3.5rem; }
            .portfolio-grid { grid-template-columns: repeat(2, 1fr); }
            .pricing-grid { grid-template-columns: repeat(2, 1fr); gap: 20px; }
        }
        @media (max-width: 992px) {
            .hero-grid, .about-grid, .skills-container, .contact-grid { grid-template-columns: 1fr; }
            .hero-visual { order: -1; display: flex; justify-content: center; }
            .timeline-wrapper::before { left: 30px; }
            .timeline-item, .timeline-item:nth-child(even) { flex-direction: column; align-items: flex-start; padding-left: 80px; }
            .timeline-dot { left: 30px; transform: translateX(-50%); }
            .timeline-content { width: 100%; margin-bottom: 20px; }
            .footer-grid { grid-template-columns: 1fr 1fr; }
        }
        @media (max-width: 768px) {
            .nav-links { position: absolute; top: 90px; left: 0; width: 100%; background: var(--glass-bg); backdrop-filter: blur(20px); flex-direction: column; padding: 30px; gap: 20px; border-bottom: 1px solid var(--glass-border); clip-path: polygon(0 0, 100% 0, 100% 0, 0 0); transition: clip-path 0.4s ease; }
            .nav-links.nav-active { clip-path: polygon(0 0, 100% 0, 100% 100%, 0% 100%); }
            .mobile-toggle { display: block; }
            .hero-metrics { grid-template-columns: 1fr; }
            .tools-grid { grid-template-columns: repeat(2, 1fr); }
            .pricing-grid, .portfolio-grid { grid-template-columns: 1fr; }
            .form-grid { grid-template-columns: 1fr; }
            .footer-grid { grid-template-columns: 1fr; }
            .cursor-dot, .cursor-outline { display: none; } /* Disable custom cursor on mobile */
            * { cursor: auto !important; }
        }
    </style>
</head>
<body class="light-mode">

    <!-- Custom Cursor -->
    <div class="cursor-dot"></div>
    <div class="cursor-outline"></div>

    <!-- Preloader -->
    <div class="preloader" id="preloader">
        <div class="gear-loader"></div>
        <div class="loading-text">Initializing Systems...</div>
    </div>

    <!-- Advanced Background Engine -->
    <div class="bg-engine">
        <canvas id="particle-canvas"></canvas>
        <div class="bg-mesh"></div>
        <div class="bg-grid"></div>
    </div>

    <!-- Floating Tools -->
    <a href="https://wa.me/920000000000" target="_blank" class="btn-icon" style="position: fixed; bottom: 30px; right: 30px; z-index: var(--z-sticky); background: #25D366; color: white; border-color: #25D366; width: 60px; height: 60px; font-size: 2rem;">
        <i class="fab fa-whatsapp"></i>
    </a>

    <!-- Header Navigation -->
    <header id="header">
        <div class="container nav-wrapper">
            <a href="#" class="logo">
                <div class="logo-icon"><i class="fas fa-cube"></i></div>
                3D Mech<span>Design</span>
            </a>
            
            <ul class="nav-links">
                <li><a href="#hero" class="nav-link active">Home</a></li>
                <li><a href="#about" class="nav-link">About</a></li>
                <li><a href="#skills" class="nav-link">Expertise</a></li>
                <li><a href="#portfolio" class="nav-link">Projects</a></li>
                <li><a href="#pricing" class="nav-link">Services</a></li>
                <li><a href="#contact" class="nav-link">Contact</a></li>
            </ul>
            
            <div class="nav-actions">
                <button id="theme-toggle" class="btn-icon" aria-label="Toggle Dark Mode">
                    <i class="fas fa-moon"></i>
                </button>
                <button class="mobile-toggle">
                    <i class="fas fa-bars"></i>
                </button>
            </div>
        </div>
    </header>

    <!-- Main Content -->
    <main>
        <!-- HERO SECTION -->
        <section id="hero">
            <div class="container hero-grid">
                <div class="hero-content">
                    <div class="badge"><i class="fas fa-rocket"></i> Available for Freelance</div>
                    <h1 class="hero-title">
                        Engineering the <br>
                        <span class="typewriter-box">Future of Design</span>
                    </h1>
                    <p class="hero-desc">
                        I am Abdur Rafay Yousuf, a Mechanical Engineer & CAD Consultant. I specialize in complex parametric modeling, computational fluid dynamics (CFD), and thermodynamic prototyping.
                    </p>
                    
                    <div class="hero-metrics">
                        <div class="metric">
                            <span class="metric-value" data-target="150">0</span>
                            <span class="metric-label">CAD Models</span>
                        </div>
                        <div class="metric">
                            <span class="metric-value" data-target="15">0</span>
                            <span class="metric-label">CFD Analyses</span>
                        </div>
                        <div class="metric">
                            <span class="metric-value">100%</span>
                            <span class="metric-label">Precision</span>
                        </div>
                    </div>

                    <div class="hero-btns">
                        <a href="#portfolio" class="btn btn-primary">
                            View Portfolio <i class="fas fa-arrow-right"></i>
                        </a>
                        <a href="#contact" class="btn btn-secondary">
                            Hire Me <i class="fas fa-briefcase"></i>
                        </a>
                    </div>
                </div>

                <div class="hero-visual js-tilt">
                    <div class="float-badge float-1 js-tilt-inner">
                        <div class="float-icon"><i class="fas fa-wind"></i></div>
                        <div class="float-text">CFD Analysis <span>Advanced Flow Regimes</span></div>
                    </div>
                    <div class="float-badge float-2 js-tilt-inner">
                        <div class="float-icon"><i class="fas fa-cogs"></i></div>
                        <div class="float-text">Gear Engineering <span>Involute Math Profiles</span></div>
                    </div>

                    <div class="glass-panel profile-card js-tilt-inner">
                        <div class="profile-img-wrap">
                            <img src="https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?fit=crop&w=500&h=500" alt="Abdur Rafay Yousuf" class="profile-img">
                        </div>
                        <h3>Abdur Rafay Yousuf</h3>
                        <p>Founder, 3D Mech Design</p>
                        <div class="badge"><i class="fas fa-university"></i> DHA Suffa University</div>
                    </div>
                </div>
            </div>
        </section>

        <!-- ABOUT & PHILOSOPHY -->
        <section id="about">
            <div class="container">
                <div class="section-header reveal">
                    <div class="badge">Who I Am</div>
                    <h2 class="section-title">Bridging Theory & <span class="text-gradient">Manufacturing</span></h2>
                    <p class="section-desc">With a deep academic background in Mechanical Engineering, I turn abstract physics and thermodynamic concepts into manufacturable, high-precision CAD models.</p>
                </div>

                <div class="about-grid">
                    <div class="about-image-wrapper reveal-left js-tilt">
                        <img src="https://images.unsplash.com/photo-1581092160562-40aa08e78837?fit=crop&w=800&h=600" alt="Engineering Workspace" class="about-image js-tilt-inner">
                        <div class="about-exp-badge js-tilt-inner">
                            <h4>4+</h4>
                            <span>Years Exp.</span>
                        </div>
                    </div>
                    
                    <div class="about-content reveal-right">
                        <h3 style="font-size: 2rem; margin-bottom: 20px;">The Engineering Process</h3>
                        <p>My approach is rooted in academic rigor and industrial standards. From designing custom gear arbors using MATLAB to developing functional prototypes like the Mahfooz Wheelchair, I ensure every dimension serves a mechanical purpose.</p>
                        
                        <div class="philosophy-steps">
                            <div class="step-card glass-panel">
                                <div class="step-icon"><i class="fas fa-lightbulb"></i></div>
                                <h4>1. Ideation</h4>
                                <p>Mathematical formulation and conceptual sketches.</p>
                            </div>
                            <div class="step-card glass-panel">
                                <div class="step-icon"><i class="fas fa-drafting-compass"></i></div>
                                <h4>2. CAD Modeling</h4>
                                <p>Parametric design in SolidWorks & Fusion 360.</p>
                            </div>
                            <div class="step-card glass-panel">
                                <div class="step-icon"><i class="fas fa-chart-line"></i></div>
                                <h4>3. Simulation (FEA/CFD)</h4>
                                <p>Stress testing and fluid dynamics validation.</p>
                            </div>
                            <div class="step-card glass-panel">
                                <div class="step-icon"><i class="fas fa-cogs"></i></div>
                                <h4>4. Prototyping</h4>
                                <p>Manufacturing drawings and physical assembly.</p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- SKILLS MATRIX -->
        <section id="skills">
            <div class="container">
                <div class="section-header reveal">
                    <div class="badge">Technical Arsenal</div>
                    <h2 class="section-title">Engineering <span class="text-gradient">Expertise</span></h2>
                    <p class="section-desc">A comprehensive breakdown of my software proficiency and theoretical engineering domains.</p>
                </div>

                <div class="skills-container">
                    <div class="skills-list reveal-left">
                        <div class="skill-item">
                            <div class="skill-header">
                                <div class="skill-title"><div class="skill-icon"><i class="fas fa-cube"></i></div> 3D CAD & Drafting</div>
                                <div class="skill-pct">95%</div>
                            </div>
                            <div class="progress-track"><div class="progress-fill" style="width: 95%;"></div></div>
                        </div>
                        <div class="skill-item">
                            <div class="skill-header">
                                <div class="skill-title"><div class="skill-icon"><i class="fas fa-wind"></i></div> CFD & Flow Analysis</div>
                                <div class="skill-pct">88%</div>
                            </div>
                            <div class="progress-track"><div class="progress-fill" style="width: 88%;"></div></div>
                        </div>
                        <div class="skill-item">
                            <div class="skill-header">
                                <div class="skill-title"><div class="skill-icon"><i class="fas fa-cog"></i></div> Gear Math & MATLAB</div>
                                <div class="skill-pct">92%</div>
                            </div>
                            <div class="progress-track"><div class="progress-fill" style="width: 92%;"></div></div>
                        </div>
                        <div class="skill-item">
                            <div class="skill-header">
                                <div class="skill-title"><div class="skill-icon"><i class="fas fa-fire-alt"></i></div> Thermodynamics</div>
                                <div class="skill-pct">85%</div>
                            </div>
                            <div class="progress-track"><div class="progress-fill" style="width: 85%;"></div></div>
                        </div>
                    </div>

                    <div class="tools-grid reveal-right">
                        <div class="tool-card"><i class="fa-solid fa-code"></i><span>SolidWorks</span></div>
                        <div class="tool-card"><i class="fa-solid fa-pen-ruler"></i><span>AutoCAD</span></div>
                        <div class="tool-card"><i class="fa-brands fa-hubspot"></i><span>Fusion 360</span></div>
                        <div class="tool-card"><i class="fa-solid fa-calculator"></i><span>MATLAB</span></div>
                        <div class="tool-card"><i class="fa-solid fa-network-wired"></i><span>Ansys</span></div>
                        <div class="tool-card"><i class="fa-brands fa-usb"></i><span>Arduino</span></div>
                    </div>
                </div>
            </div>
        </section>

        <!-- TIMELINE SECTION -->
        <section id="experience">
            <div class="container">
                <div class="section-header reveal">
                    <div class="badge">Journey</div>
                    <h2 class="section-title">Professional <span class="text-gradient">Timeline</span></h2>
                </div>

                <div class="timeline-wrapper">
                    <!-- Item 1 -->
                    <div class="timeline-item reveal">
                        <div class="timeline-content"></div>
                        <div class="timeline-dot"></div>
                        <div class="timeline-content">
                            <div class="timeline-card glass-panel js-tilt">
                                <div class="js-tilt-inner">
                                    <span class="timeline-date">2023 - Present</span>
                                    <h3 class="timeline-title">Founder & Consultant</h3>
                                    <h4 class="timeline-company">3D Mech Design</h4>
                                    <p>Managing end-to-end mechanical design consultancy. Drafting complex parametric proposals and manufacturing schematics for local and international clients.</p>
                                    <div class="timeline-tags"><span>Consultancy</span><span>CAD</span><span>Business</span></div>
                                </div>
                            </div>
                        </div>
                    </div>
                    <!-- Item 2 -->
                    <div class="timeline-item reveal">
                        <div class="timeline-content">
                            <div class="timeline-card glass-panel js-tilt">
                                <div class="js-tilt-inner">
                                    <span class="timeline-date">2025 - 2026</span>
                                    <h3 class="timeline-title">Lead Project Engineer</h3>
                                    <h4 class="timeline-company">Mahfooz Wheelchair</h4>
                                    <p>Engineered a locally producible stair-lifting wheelchair. Handled user-centric surveys, stress simulations, and received official recognition from Sindh HEC.</p>
                                    <div class="timeline-tags"><span>Prototyping</span><span>Accessibility</span><span>FEA</span></div>
                                </div>
                            </div>
                        </div>
                        <div class="timeline-dot"></div>
                        <div class="timeline-content"></div>
                    </div>
                    <!-- Item 3 -->
                    <div class="timeline-item reveal">
                        <div class="timeline-content"></div>
                        <div class="timeline-dot"></div>
                        <div class="timeline-content">
                            <div class="timeline-card glass-panel js-tilt">
                                <div class="js-tilt-inner">
                                    <span class="timeline-date">2026 (Ongoing)</span>
                                    <h3 class="timeline-title">B.E. Mechanical Engineering</h3>
                                    <h4 class="timeline-company">DHA Suffa University</h4>
                                    <p>Conducting advanced research in ICE emissions, autonomous robotics, and thermal energy storage systems (Sand Batteries) under the guidance of Dr. Usama.</p>
                                    <div class="timeline-tags"><span>Academics</span><span>Research</span><span>Thermodynamics</span></div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- MASSIVE PORTFOLIO -->
        <section id="portfolio">
            <div class="container">
                <div class="section-header reveal">
                    <div class="badge">Case Studies</div>
                    <h2 class="section-title">Featured <span class="text-gradient">Projects</span></h2>
                </div>

                <div class="portfolio-filters reveal">
                    <button class="filter-btn active" data-filter="all">All Specs</button>
                    <button class="filter-btn" data-filter="thermo">Thermodynamics</button>
                    <button class="filter-btn" data-filter="mech">Mechanical CAD</button>
                    <button class="filter-btn" data-filter="robotics">Robotics</button>
                </div>

                <div class="portfolio-grid" id="portfolioGrid">
                    <!-- Project 1 -->
                    <div class="portfolio-card glass-panel reveal port-item thermo">
                        <div class="port-img-wrap">
                            <img src="https://images.unsplash.com/photo-1497435334941-8c899ee9e8e9?fit=crop&w=600&h=400" alt="Sand Battery">
                            <div class="port-overlay">
                                <button class="port-view-btn open-modal" data-target="modal-battery"><i class="fas fa-search-plus"></i></button>
                            </div>
                        </div>
                        <div class="port-content">
                            <span class="port-cat">Thermodynamics</span>
                            <h3 class="port-title">Thermal Energy Sand Battery</h3>
                            <p class="port-desc">Engineered an insulated silica sand tank with internal heat exchanger coils for high-capacity industrial thermal storage.</p>
                            <div class="port-meta">
                                <div class="port-tool"><i class="fas fa-thermometer-half"></i> <i class="fas fa-cogs"></i></div>
                                <a href="#" class="open-modal" data-target="modal-battery">Read Case Study <i class="fas fa-arrow-right"></i></a>
                            </div>
                        </div>
                    </div>

                    <!-- Project 2 -->
                    <div class="portfolio-card glass-panel reveal port-item mech">
                        <div class="port-img-wrap">
                            <img src="https://images.unsplash.com/photo-1581092335397-9583eb92d232?fit=crop&w=600&h=400" alt="Wheelchair">
                            <div class="port-overlay">
                                <button class="port-view-btn open-modal" data-target="modal-wheelchair"><i class="fas fa-search-plus"></i></button>
                            </div>
                        </div>
                        <div class="port-content">
                            <span class="port-cat">Mechanical CAD</span>
                            <h3 class="port-title">Mahfooz Stair-Lift Wheelchair</h3>
                            <p class="port-desc">A highly specialized mechanical assembly designed for low-cost, local production to assist individuals with severe mobility limits.</p>
                            <div class="port-meta">
                                <div class="port-tool"><i class="fa-solid fa-code"></i> <i class="fas fa-wheelchair"></i></div>
                                <a href="#" class="open-modal" data-target="modal-wheelchair">Read Case Study <i class="fas fa-arrow-right"></i></a>
                            </div>
                        </div>
                    </div>

                    <!-- Project 3 -->
                    <div class="portfolio-card glass-panel reveal port-item robotics">
                        <div class="port-img-wrap">
                            <img src="https://images.unsplash.com/photo-1485827404703-89b55fcc595e?fit=crop&w=600&h=400" alt="Robot">
                            <div class="port-overlay">
                                <button class="port-view-btn open-modal" data-target="modal-robot"><i class="fas fa-search-plus"></i></button>
                            </div>
                        </div>
                        <div class="port-content">
                            <span class="port-cat">Mechatronics</span>
                            <h3 class="port-title">Autonomous Line-Follower</h3>
                            <p class="port-desc">Arduino Uno-based instrumentation system with complex wiring, sensor feedback loops, and real-time C++ processing code.</p>
                            <div class="port-meta">
                                <div class="port-tool"><i class="fa-brands fa-usb"></i> <i class="fas fa-microchip"></i></div>
                                <a href="#" class="open-modal" data-target="modal-robot">Read Case Study <i class="fas fa-arrow-right"></i></a>
                            </div>
                        </div>
                    </div>

                    <!-- Project 4 -->
                    <div class="portfolio-card glass-panel reveal port-item mech thermo">
                        <div class="port-img-wrap">
                            <img src="https://images.unsplash.com/photo-1581092580497-e0d23cbdf1dc?fit=crop&w=600&h=400" alt="CFD">
                            <div class="port-overlay">
                                <button class="port-view-btn open-modal" data-target="modal-cfd"><i class="fas fa-search-plus"></i></button>
                            </div>
                        </div>
                        <div class="port-content">
                            <span class="port-cat">CFD & Gear Math</span>
                            <h3 class="port-title">CFD & Involute Arbors</h3>
                            <p class="port-desc">Mathematical calculation of gear diametral pitch alongside computational fluid dynamics velocity/pressure mapping.</p>
                            <div class="port-meta">
                                <div class="port-tool"><i class="fa-solid fa-calculator"></i> <i class="fas fa-wind"></i></div>
                                <a href="#" class="open-modal" data-target="modal-cfd">Read Case Study <i class="fas fa-arrow-right"></i></a>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- SERVICES & PRICING -->
        <section id="pricing">
            <div class="container">
                <div class="section-header reveal">
                    <div class="badge">3D Mech Design</div>
                    <h2 class="section-title">Consulting <span class="text-gradient">Services</span></h2>
                </div>

                <div class="pricing-grid">
                    <div class="price-card glass-panel reveal js-tilt">
                        <div class="js-tilt-inner">
                            <div class="price-icon"><i class="fas fa-drafting-compass"></i></div>
                            <h3 class="price-title">2D/3D Drafting</h3>
                            <div class="price-amount">Basic <span>/project</span></div>
                            <ul class="price-features">
                                <li><i class="fas fa-check"></i> Basic 3D Part Modeling</li>
                                <li><i class="fas fa-check"></i> 2D Manufacturing Drawings</li>
                                <li><i class="fas fa-check"></i> 2 Revisions</li>
                                <li class="disabled"><i class="fas fa-times"></i> Assembly & Mates</li>
                                <li class="disabled"><i class="fas fa-times"></i> Simulation / FEA</li>
                            </ul>
                            <a href="#contact" class="btn btn-secondary" style="width: 100%;">Select Plan</a>
                        </div>
                    </div>

                    <div class="price-card glass-panel featured reveal js-tilt">
                        <div class="featured-badge">Most Popular</div>
                        <div class="js-tilt-inner">
                            <div class="price-icon"><i class="fas fa-cogs"></i></div>
                            <h3 class="price-title">Parametric Design</h3>
                            <div class="price-amount">Pro <span>/project</span></div>
                            <ul class="price-features">
                                <li><i class="fas fa-check"></i> Complex Assembly Modeling</li>
                                <li><i class="fas fa-check"></i> Parametric Design Tables</li>
                                <li><i class="fas fa-check"></i> Gear & Mechanism Logic</li>
                                <li><i class="fas fa-check"></i> High-Res Renders</li>
                                <li class="disabled"><i class="fas fa-times"></i> CFD / Thermal Analysis</li>
                            </ul>
                            <a href="#contact" class="btn btn-primary" style="width: 100%;">Select Plan</a>
                        </div>
                    </div>

                    <div class="price-card glass-panel reveal js-tilt">
                        <div class="js-tilt-inner">
                            <div class="price-icon"><i class="fas fa-chart-network"></i></div>
                            <h3 class="price-title">Simulation</h3>
                            <div class="price-amount">Advanced <span>/project</span></div>
                            <ul class="price-features">
                                <li><i class="fas fa-check"></i> Everything in Pro</li>
                                <li><i class="fas fa-check"></i> CFD Velocity/Pressure</li>
                                <li><i class="fas fa-check"></i> Finite Element Analysis</li>
                                <li><i class="fas fa-check"></i> Thermodynamic Prototyping</li>
                                <li><i class="fas fa-check"></i> Full Engineering Report</li>
                            </ul>
                            <a href="#contact" class="btn btn-secondary" style="width: 100%;">Select Plan</a>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- TESTIMONIALS SLIDER -->
        <section id="testimonials">
            <div class="container">
                <div class="section-header reveal">
                    <div class="badge">References</div>
                    <h2 class="section-title">Client & Academic <span class="text-gradient">Feedback</span></h2>
                </div>

                <div class="testimonial-container reveal">
                    <div class="glass-panel testi-card">
                        <div class="testi-slider" id="testiSlider">
                            <!-- Slide 1 -->
                            <div class="testi-slide">
                                <i class="fas fa-quote-left quote-icon"></i>
                                <p class="testi-text">"Abdur Rafay demonstrates exceptional diligence in complex design architecture. His work on the Thermal Sand Battery and computational fluid dynamics sets a remarkably high standard for mechanical engineering students."</p>
                                <div class="testi-author">
                                    <div class="author-img">U</div>
                                    <div class="author-info">
                                        <h4>Dr. Usama</h4>
                                        <span>Professor, DHA Suffa University</span>
                                    </div>
                                </div>
                            </div>
                            <!-- Slide 2 -->
                            <div class="testi-slide">
                                <i class="fas fa-quote-left quote-icon"></i>
                                <p class="testi-text">"Collaborating with Rafay on lab projects has been incredible. His precision in SolidWorks and ability to translate abstract mathematical gear equations into working CAD models is simply unmatched."</p>
                                <div class="testi-author">
                                    <div class="author-img">A</div>
                                    <div class="author-info">
                                        <h4>Ayaan Amir</h4>
                                        <span>Project Collaborator</span>
                                    </div>
                                </div>
                            </div>
                            <!-- Slide 3 -->
                            <div class="testi-slide">
                                <i class="fas fa-quote-left quote-icon"></i>
                                <p class="testi-text">"The mentorship provided by Rafay in computer-aided design has been invaluable to my growth. He breaks down complex geometric modeling into understandable, practical engineering logic."</p>
                                <div class="testi-author">
                                    <div class="author-img">F</div>
                                    <div class="author-info">
                                        <h4>Faizan Khan</h4>
                                        <span>Junior Associate & Mentee</span>
                                    </div>
                                </div>
                            </div>
                        </div>
                        <div class="slider-controls">
                            <button class="slider-btn" id="prevSlide"><i class="fas fa-chevron-left"></i></button>
                            <button class="slider-btn" id="nextSlide"><i class="fas fa-chevron-right"></i></button>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- FAQ ACCORDION -->
        <section id="faq">
            <div class="container">
                <div class="section-header reveal">
                    <div class="badge">Knowledge Base</div>
                    <h2 class="section-title">Frequently Asked <span class="text-gradient">Questions</span></h2>
                </div>

                <div class="faq-container reveal">
                    <div class="accordion-item">
                        <div class="accordion-header">What CAD software do you primarily use? <i class="fas fa-chevron-down accordion-icon"></i></div>
                        <div class="accordion-content">
                            <p style="margin-top: 15px;">I primarily use SolidWorks and Fusion 360 for complex parametric modeling and assembly design. For basic 2D drafting and schematics, I utilize AutoCAD. All simulation tasks (FEA/CFD) are generally handled within SolidWorks Simulation or exported to Ansys.</p>
                        </div>
                    </div>
                    <div class="accordion-item">
                        <div class="accordion-header">Can you assist with gear profile calculations? <i class="fas fa-chevron-down accordion-icon"></i></div>
                        <div class="accordion-content">
                            <p style="margin-top: 15px;">Yes. I have extensive experience writing custom MATLAB scripts to mathematically calculate involute tooth profiles, diametral pitches, and designing specialized hobbing arbors based on precise geometric math.</p>
                        </div>
                    </div>
                    <div class="accordion-item">
                        <div class="accordion-header">What is the Mahfooz Wheelchair Project? <i class="fas fa-chevron-down accordion-icon"></i></div>
                        <div class="accordion-content">
                            <p style="margin-top: 15px;">It is a specialized mobility device I engineered featuring stair-lifting capabilities. It was designed to be locally producible in Pakistan and received official recognition from the Sindh Higher Education Commission.</p>
                        </div>
                    </div>
                    <div class="accordion-item">
                        <div class="accordion-header">Do you take on international freelance clients? <i class="fas fa-chevron-down accordion-icon"></i></div>
                        <div class="accordion-content">
                            <p style="margin-top: 15px;">Absolutely. Through my consultancy, 3D Mech Design, I provide mechanical design and CAD drafting services to clients worldwide, maintaining communication via digital platforms and delivering universal CAD file formats (.STEP, .IGES, .STL).</p>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- CONTACT SECTION -->
        <section id="contact">
            <div class="container">
                <div class="contact-grid">
                    <div class="contact-info reveal-left">
                        <div class="badge">Let's Connect</div>
                        <h2 class="section-title" style="margin-bottom: 20px;">Ready to Engineer Your <span class="text-gradient">Idea?</span></h2>
                        <p style="margin-bottom: 40px;">Whether you need a quick CAD draft, a complex mechanical assembly, or advanced CFD simulation, I am ready to collaborate.</p>
                        
                        <div class="contact-card glass-panel">
                            <div class="contact-icon"><i class="fas fa-map-marker-alt"></i></div>
                            <div class="contact-details">
                                <h4>Location</h4>
                                <p>Karachi, Sindh, Pakistan (Open to Remote Global Work)</p>
                            </div>
                        </div>
                        <div class="contact-card glass-panel">
                            <div class="contact-icon"><i class="fas fa-envelope"></i></div>
                            <div class="contact-details">
                                <h4>Email Me</h4>
                                <a href="mailto:contact@example.com">contact@3dmechdesign.com</a>
                            </div>
                        </div>
                        <div class="contact-card glass-panel">
                            <div class="contact-icon"><i class="fas fa-briefcase"></i></div>
                            <div class="contact-details">
                                <h4>Consultancy</h4>
                                <p>3D Mech Design Firm</p>
                            </div>
                        </div>
                    </div>

                    <div class="contact-form-wrap glass-panel reveal-right">
                        <h3 style="font-size: 1.8rem; margin-bottom: 30px;">Send a Message</h3>
                        <form id="mainForm">
                            <div class="form-grid">
                                <div class="input-group">
                                    <label>First Name</label>
                                    <input type="text" class="form-control" required placeholder="John">
                                </div>
                                <div class="input-group">
                                    <label>Last Name</label>
                                    <input type="text" class="form-control" required placeholder="Doe">
                                </div>
                            </div>
                            <div class="input-group" style="margin-bottom: 20px;">
                                <label>Email Address</label>
                                <input type="email" class="form-control" required placeholder="john@company.com">
                            </div>
                            <div class="input-group" style="margin-bottom: 20px;">
                                <label>Project Scope / Details</label>
                                <textarea class="form-control" required placeholder="Please describe your mechanical engineering requirements..."></textarea>
                            </div>
                            <button type="submit" class="btn btn-primary form-submit">
                                Initiate Connection <i class="fas fa-paper-plane"></i>
                            </button>
                        </form>
                    </div>
                </div>
            </div>
        </section>
    </main>

    <!-- FOOTER -->
    <footer>
        <div class="container">
            <div class="footer-grid">
                <div class="footer-brand">
                    <a href="#" class="logo">
                        <div class="logo-icon"><i class="fas fa-cube"></i></div>
                        3D Mech<span>Design</span>
                    </a>
                    <p>Providing cutting-edge parametric design, thermodynamics prototyping, and computational fluid dynamics analysis for modern engineering solutions.</p>
                    <div class="social-links">
                        <a href="#" class="btn-icon"><i class="fab fa-linkedin-in"></i></a>
                        <a href="#" class="btn-icon"><i class="fab fa-github"></i></a>
                        <a href="#" class="btn-icon"><i class="fab fa-instagram"></i></a>
                    </div>
                </div>
                
                <div class="footer-nav">
                    <h4 class="footer-title">Navigation</h4>
                    <ul class="footer-links">
                        <li><a href="#hero"><i class="fas fa-angle-right"></i> Home</a></li>
                        <li><a href="#about"><i class="fas fa-angle-right"></i> About</a></li>
                        <li><a href="#skills"><i class="fas fa-angle-right"></i> Expertise</a></li>
                        <li><a href="#portfolio"><i class="fas fa-angle-right"></i> Portfolio</a></li>
                    </ul>
                </div>

                <div class="footer-nav">
                    <h4 class="footer-title">Legal & Info</h4>
                    <ul class="footer-links">
                        <li><a href="#pricing"><i class="fas fa-angle-right"></i> Pricing Models</a></li>
                        <li><a href="#faq"><i class="fas fa-angle-right"></i> FAQ</a></li>
                        <li><a href="#"><i class="fas fa-angle-right"></i> Privacy Policy</a></li>
                        <li><a href="#"><i class="fas fa-angle-right"></i> Terms of Service</a></li>
                    </ul>
                </div>
            </div>
            
            <div class="footer-bottom">
                <p>&copy; 2026 Abdur Rafay Yousuf. All Rights Reserved.</p>
                <p>Designed in Karachi, Pakistan</p>
            </div>
        </div>
    </footer>

    <!-- MODALS (Case Studies) -->
    <!-- Battery Modal -->
    <div class="modal glass-panel" id="modal-battery">
        <div class="modal-content glass-panel">
            <button class="modal-close"><i class="fas fa-times"></i></button>
            <div class="badge" style="margin-bottom: 20px;">Case Study</div>
            <h2 style="margin-bottom: 15px; font-size: 2rem;">Thermal Energy Sand Battery</h2>
            <img src="https://images.unsplash.com/photo-1497435334941-8c899ee9e8e9?fit=crop&w=800&h=400" alt="Battery" style="width: 100%; border-radius: var(--radius-md); margin-bottom: 20px; border: 1px solid var(--glass-border);">
            <p><strong>Overview:</strong> As a final year design project, this system explores high-capacity industrial thermal energy storage using silica sand as the primary retention medium.</p>
            <p><strong>Technical Scope:</strong> Designed physical layout of an insulated tank with complex internal heat exchanger coils. Simulated heat transfer rates using thermodynamics principles and integrated precision instrumentation sensors for data logging.</p>
            <ul style="margin-top: 15px; padding-left: 20px; color: var(--text-secondary);">
                <li>Material Selection: High-retention Silica Sand</li>
                <li>Thermodynamic modeling of heat loss over 72 hours</li>
                <li>CAD assembly in SolidWorks</li>
            </ul>
        </div>
    </div>
    
    <!-- CFD Modal -->
    <div class="modal glass-panel" id="modal-cfd">
        <div class="modal-content glass-panel">
            <button class="modal-close"><i class="fas fa-times"></i></button>
            <div class="badge" style="margin-bottom: 20px;">Case Study</div>
            <h2 style="margin-bottom: 15px; font-size: 2rem;">CFD & Involute Gear Arbors</h2>
            <p><strong>Overview:</strong> A highly mathematical approach to mechanical design combining fluid analysis with strict geometric principles for gear manufacturing.</p>
            <p><strong>Technical Scope:</strong> Programmed custom MATLAB equations to calculate true involute tooth profiles and exact diametral pitch. In tandem, executed Computational Fluid Dynamics (CFD) analysis to map pressure drops and velocity distributions across complex geometries.</p>
        </div>
    </div>

    <!-- MAIN JAVASCRIPT ENGINE -->
    <script>
        document.addEventListener("DOMContentLoaded", () => {
            
            // 1. PRELOADER LOGIC
            const preloader = document.getElementById('preloader');
            setTimeout(() => {
                preloader.classList.add('hidden');
                setTimeout(() => preloader.style.display = 'none', 800);
            }, 1500);

            // 2. CUSTOM CURSOR
            const cursorDot = document.querySelector('.cursor-dot');
            const cursorOutline = document.querySelector('.cursor-outline');
            
            if(window.innerWidth > 768) {
                window.addEventListener('mousemove', (e) => {
                    const posX = e.clientX;
                    const posY = e.clientY;
                    
                    cursorDot.style.left = `${posX}px`;
                    cursorDot.style.top = `${posY}px`;
                    
                    // Add slight delay to outline for smooth effect
                    cursorOutline.animate({
                        left: `${posX}px`,
                        top: `${posY}px`
                    }, { duration: 500, fill: "forwards" });
                });

                // Add hover effect to links and buttons
                const interactables = document.querySelectorAll('a, button, .js-tilt, .accordion-header, .port-item');
                interactables.forEach(el => {
                    el.addEventListener('mouseenter', () => document.body.classList.add('cursor-hover'));
                    el.addEventListener('mouseleave', () => document.body.classList.remove('cursor-hover'));
                });
            }

            // 3. THEME MANAGER
            const themeToggle = document.getElementById("theme-toggle");
            const savedTheme = localStorage.getItem("portfolio_theme");
            
            if (savedTheme) {
                document.documentElement.setAttribute("data-theme", savedTheme);
                themeToggle.innerHTML = savedTheme === "dark" ? '<i class="fas fa-sun"></i>' : '<i class="fas fa-moon"></i>';
            }
            
            themeToggle.addEventListener('click', () => {
                const isDark = document.documentElement.getAttribute("data-theme") === "dark";
                document.documentElement.setAttribute("data-theme", isDark ? "light" : "dark");
                localStorage.setItem("portfolio_theme", isDark ? "light" : "dark");
                themeToggle.innerHTML = isDark ? '<i class="fas fa-moon"></i>' : '<i class="fas fa-sun"></i>';
                // Update particle color based on theme
                initParticles(); 
            });

            // 4. NAVBAR SCROLL EFFECT & MOBILE MENU
            const header = document.getElementById('header');
            const mobileToggle = document.querySelector('.mobile-toggle');
            const navLinks = document.querySelector('.nav-links');
            const sections = document.querySelectorAll('section');
            const navItems = document.querySelectorAll('.nav-link');

            window.addEventListener('scroll', () => {
                if(window.scrollY > 50) header.classList.add('scrolled');
                else header.classList.remove('scrolled');

                // Scroll Spy
                let current = '';
                sections.forEach(section => {
                    const sectionTop = section.offsetTop;
                    if(pageYOffset >= sectionTop - 150) {
                        current = section.getAttribute('id');
                    }
                });

                navItems.forEach(li => {
                    li.classList.remove('active');
                    if(li.getAttribute('href') === `#${current}`) {
                        li.classList.add('active');
                    }
                });
            });

            mobileToggle.addEventListener('click', () => {
                navLinks.classList.toggle('nav-active');
                const i = mobileToggle.querySelector('i');
                i.classList.toggle('fa-bars');
                i.classList.toggle('fa-times');
            });

            // 5. METRICS COUNTER ANIMATION
            const metrics = document.querySelectorAll('.metric-value[data-target]');
            let counted = false;

            const runCounters = () => {
                metrics.forEach(metric => {
                    const target = +metric.getAttribute('data-target');
                    const count = +metric.innerText;
                    const speed = 200; // lower is faster
                    const inc = target / speed;

                    if(count < target) {
                        metric.innerText = Math.ceil(count + inc);
                        setTimeout(runCounters, 10);
                    } else {
                        metric.innerText = target + "+";
                    }
                });
            }

            // 6. INTERSECTION OBSERVER (Scroll Reveals)
            const revealElements = document.querySelectorAll('.reveal, .reveal-left, .reveal-right');
            const observerOptions = { root: null, rootMargin: '0px', threshold: 0.1 };

            const observer = new IntersectionObserver((entries, observer) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.classList.add('active');
                        // Trigger counters if hero metrics are visible
                        if(entry.target.classList.contains('hero-metrics') && !counted) {
                            runCounters();
                            counted = true;
                        }
                        observer.unobserve(entry.target);
                    }
                });
            }, observerOptions);

            revealElements.forEach(el => observer.observe(el));

            // 7. VANILLA 3D TILT EFFECT
            const tiltElements = document.querySelectorAll('.js-tilt');
            
            tiltElements.forEach(el => {
                if(window.innerWidth > 992) {
                    el.addEventListener('mousemove', (e) => {
                        const rect = el.getBoundingClientRect();
                        const x = e.clientX - rect.left;
                        const y = e.clientY - rect.top;
                        
                        const centerX = rect.width / 2;
                        const centerY = rect.height / 2;
                        
                        const tiltX = ((y - centerY) / centerY) * -10; // Max tilt degree
                        const tiltY = ((x - centerX) / centerX) * 10;
                        
                        el.style.transform = `perspective(1000px) rotateX(${tiltX}deg) rotateY(${tiltY}deg) scale3d(1.02, 1.02, 1.02)`;
                    });
                    
                    el.addEventListener('mouseleave', () => {
                        el.style.transform = `perspective(1000px) rotateX(0deg) rotateY(0deg) scale3d(1, 1, 1)`;
                        el.style.transition = `transform 0.5s ease`;
                        setTimeout(() => el.style.transition = '', 500);
                    });
                }
            });

            // 8. PORTFOLIO FILTERING
            const filterBtns = document.querySelectorAll('.portfolio-filters .filter-btn');
            const portItems = document.querySelectorAll('.port-item');

            filterBtns.forEach(btn => {
                btn.addEventListener('click', () => {
                    // Update active button
                    filterBtns.forEach(b => b.classList.remove('active'));
                    btn.classList.add('active');
                    
                    const filter = btn.getAttribute('data-filter');
                    
                    portItems.forEach(item => {
                        item.style.opacity = '0';
                        item.style.transform = 'scale(0.9)';
                        
                        setTimeout(() => {
                            if(filter === 'all' || item.classList.contains(filter)) {
                                item.style.display = 'flex';
                                setTimeout(() => {
                                    item.style.opacity = '1';
                                    item.style.transform = 'scale(1)';
                                }, 50);
                            } else {
                                item.style.display = 'none';
                            }
                        }, 300);
                    });
                });
            });

            // 9. TESTIMONIAL SLIDER LOGIC
            const slider = document.getElementById('testiSlider');
            const slides = document.querySelectorAll('.testi-slide');
            const prevBtn = document.getElementById('prevSlide');
            const nextBtn = document.getElementById('nextSlide');
            let currentSlide = 0;

            const updateSlider = () => {
                slider.style.transform = `translateX(-${currentSlide * 100}%)`;
            };

            nextBtn.addEventListener('click', () => {
                currentSlide = (currentSlide + 1) % slides.length;
                updateSlider();
            });

            prevBtn.addEventListener('click', () => {
                currentSlide = (currentSlide - 1 + slides.length) % slides.length;
                updateSlider();
            });

            // 10. FAQ ACCORDION LOGIC
            const accordionHeaders = document.querySelectorAll('.accordion-header');
            
            accordionHeaders.forEach(header => {
                header.addEventListener('click', () => {
                    const item = header.parentElement;
                    // Close others
                    document.querySelectorAll('.accordion-item').forEach(other => {
                        if(other !== item) other.classList.remove('active');
                    });
                    item.classList.toggle('active');
                });
            });

            // 11. MODAL MANAGER
            const modalTriggers = document.querySelectorAll('.open-modal');
            const modals = document.querySelectorAll('.modal');
            const closeBtns = document.querySelectorAll('.modal-close');

            modalTriggers.forEach(trigger => {
                trigger.addEventListener('click', (e) => {
                    e.preventDefault();
                    const targetId = trigger.getAttribute('data-target');
                    if(targetId) document.getElementById(targetId).classList.add('active');
                });
            });

            closeBtns.forEach(btn => {
                btn.addEventListener('click', () => {
                    modals.forEach(m => m.classList.remove('active'));
                });
            });

            window.addEventListener('click', (e) => {
                modals.forEach(m => {
                    if(e.target === m) m.classList.remove('active');
                });
            });

            // 12. FORM SUBMISSION MOCK
            const form = document.getElementById('mainForm');
            if(form) {
                form.addEventListener('submit', (e) => {
                    e.preventDefault();
                    const btn = form.querySelector('.form-submit');
                    const originalText = btn.innerHTML;
                    btn.innerHTML = '<i class="fas fa-circle-notch fa-spin"></i> Processing...';
                    
                    setTimeout(() => {
                        btn.innerHTML = '<i class="fas fa-check"></i> Request Sent';
                        btn.classList.add('btn-success');
                        form.reset();
                        setTimeout(() => {
                            btn.innerHTML = originalText;
                            btn.classList.remove('btn-success');
                        }, 3000);
                    }, 1500);
                });
            }

            // 13. VANILLA JS PARTICLE ENGINE (CFD SIMULATION)
            const canvas = document.getElementById('particle-canvas');
            const ctx = canvas.getContext('2d');
            let particlesArray = [];
            
            canvas.width = window.innerWidth;
            canvas.height = window.innerHeight;
            
            window.addEventListener('resize', () => {
                canvas.width = window.innerWidth;
                canvas.height = window.innerHeight;
                initParticles();
            });

            class Particle {
                constructor(x, y, directionX, directionY, size, color) {
                    this.x = x;
                    this.y = y;
                    this.directionX = directionX;
                    this.directionY = directionY;
                    this.size = size;
                    this.color = color;
                }
                
                draw() {
                    ctx.beginPath();
                    ctx.arc(this.x, this.y, this.size, 0, Math.PI * 2, false);
                    ctx.fillStyle = this.color;
                    ctx.fill();
                }
                
                update() {
                    if (this.x > canvas.width || this.x < 0) this.directionX = -this.directionX;
                    if (this.y > canvas.height || this.y < 0) this.directionY = -this.directionY;
                    
                    this.x += this.directionX;
                    this.y += this.directionY;
                    this.draw();
                }
            }

            function initParticles() {
                particlesArray = [];
                // Determine color based on theme
                const isDark = document.documentElement.getAttribute("data-theme") === "dark";
                const pColor = isDark ? 'rgba(96, 165, 250, 0.2)' : 'rgba(37, 99, 235, 0.15)';
                const numberOfParticles = (canvas.height * canvas.width) / 12000;
                
                for (let i = 0; i < numberOfParticles; i++) {
                    let size = (Math.random() * 3) + 1;
                    let x = (Math.random() * ((innerWidth - size * 2) - (size * 2)) + size * 2);
                    let y = (Math.random() * ((innerHeight - size * 2) - (size * 2)) + size * 2);
                    let directionX = (Math.random() * 2) - 1;
                    let directionY = (Math.random() * 2) - 1;
                    
                    particlesArray.push(new Particle(x, y, directionX, directionY, size, pColor));
                }
            }

            function animateParticles() {
                requestAnimationFrame(animateParticles);
                ctx.clearRect(0, 0, innerWidth, innerHeight);
                
                for (let i = 0; i < particlesArray.length; i++) {
                    particlesArray[i].update();
                }
                connectParticles();
            }

            function connectParticles() {
                let opacityValue = 1;
                for (let a = 0; a < particlesArray.length; a++) {
                    for (let b = a; b < particlesArray.length; b++) {
                        let distance = ((particlesArray[a].x - particlesArray[b].x) * (particlesArray[a].x - particlesArray[b].x))
                                     + ((particlesArray[a].y - particlesArray[b].y) * (particlesArray[a].y - particlesArray[b].y));
                                     
                        if (distance < (canvas.width / 10) * (canvas.height / 10)) {
                            const isDark = document.documentElement.getAttribute("data-theme") === "dark";
                            opacityValue = 1 - (distance / 20000);
                            ctx.strokeStyle = isDark ? `rgba(96, 165, 250, ${opacityValue * 0.2})` : `rgba(37, 99, 235, ${opacityValue * 0.2})`;
                            ctx.lineWidth = 1;
                            ctx.beginPath();
                            ctx.moveTo(particlesArray[a].x, particlesArray[a].y);
                            ctx.lineTo(particlesArray[b].x, particlesArray[b].y);
                            ctx.stroke();
                        }
                    }
                }
            }

            initParticles();
            animateParticles();

        });
    </script>
</body>
</html>
**<!DOCTYPE html>
<html lang="en">
<head>
    <!-- ======================================================================
         META TAGS & SEO
         ====================================================================== -->
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <meta name="description" content="Abdur Rafay Yousuf - Mechanical Engineer & CAD Consultant. Founder of 3D Mech Design, specializing in parametric modeling, CFD, and thermal systems.">
    <meta name="keywords" content="Mechanical Engineering, CAD Consultant, SolidWorks, CFD Analysis, Thermodynamics, 3D Mech Design, Karachi">
    <meta name="author" content="Abdur Rafay Yousuf">
    <meta name="robots" content="index, follow">
    <title>Abdur Rafay Yousuf | Advanced Engineering Portfolio</title>
    
    <!-- ======================================================================
         EXTERNAL ASSETS & FONTS
         ====================================================================== -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <!-- Plus Jakarta Sans for UI, JetBrains Mono for Technical Data -->
    <link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@300;400;500;600;700;800&family=Plus+Jakarta+Sans:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">

    <!-- ======================================================================
         MASTER CSS STYLESHEET
         ====================================================================== -->
    <style>
        /* --------------------------------------------------------------------
           01. CSS RESET & CUSTOM PROPERTIES
           -------------------------------------------------------------------- */
        *, *::before, *::after {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            -webkit-font-smoothing: antialiased;
            -moz-osx-font-smoothing: grayscale;
        }

        html {
            scroll-behavior: smooth;
            scroll-padding-top: 100px;
            font-size: 16px;
        }

        :root {
            /* LIGHT THEME VARIABLES */
            --bg-base: #f8fafc;
            --bg-gradient-1: #eef6ff;
            --bg-gradient-2: #f1f5f9;
            --bg-surface: #ffffff;
            
            --text-primary: #0f172a;
            --text-secondary: #475569;
            --text-muted: #64748b;
            --text-inverse: #ffffff;
            
            --brand-primary: #2563eb;
            --brand-primary-hover: #1d4ed8;
            --brand-primary-light: rgba(37, 99, 235, 0.1);
            --brand-accent: #8b5cf6;
            --brand-success: #059669;
            --brand-warning: #d97706;
            --brand-danger: #e11d48;

            --glass-bg: rgba(255, 255, 255, 0.65);
            --glass-border: rgba(15, 23, 42, 0.1);
            --glass-highlight: rgba(255, 255, 255, 0.8);
            
            --grid-line: rgba(37, 99, 235, 0.05);
            --particle-color: rgba(37, 99, 235, 0.3);
            
            --shadow-sm: 0 2px 4px rgba(0,0,0,0.02);
            --shadow-md: 0 10px 40px rgba(15, 23, 42, 0.06);
            --shadow-lg: 0 20px 60px rgba(37, 99, 235, 0.12);
            --shadow-glow: 0 0 30px rgba(37, 99, 235, 0.3);
            
            --radius-sm: 8px;
            --radius-md: 16px;
            --radius-lg: 24px;
            --radius-full: 9999px;

            --font-sans: 'Plus Jakarta Sans', sans-serif;
            --font-mono: 'JetBrains Mono', monospace;
            
            --transition-fast: 0.2s cubic-bezier(0.4, 0, 0.2, 1);
            --transition-normal: 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            --transition-slow: 0.8s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            
            --z-negative: -1;
            --z-normal: 1;
            --z-sticky: 100;
            --z-drawer: 200;
            --z-modal: 300;
            --z-cursor: 9999;
        }

        [data-theme="dark"] {
            /* DARK THEME VARIABLES (No pure black, using deep slate/blues) */
            --bg-base: #050816;
            --bg-gradient-1: #0f172a;
            --bg-gradient-2: #0a0f1d;
            --bg-surface: #0f172a;
            
            --text-primary: #f8fafc;
            --text-secondary: #cbd5e1;
            --text-muted: #94a3b8;
            --text-inverse: #0f172a;
            
            --brand-primary: #3b82f6;
            --brand-primary-hover: #60a5fa;
            --brand-primary-light: rgba(59, 130, 246, 0.15);
            --brand-accent: #a855f7;
            --brand-success: #10b981;
            
            --glass-bg: rgba(15, 23, 42, 0.55);
            --glass-border: rgba(255, 255, 255, 0.08);
            --glass-highlight: rgba(255, 255, 255, 0.05);
            
            --grid-line: rgba(59, 130, 246, 0.08);
            --particle-color: rgba(96, 165, 250, 0.25);
            
            --shadow-md: 0 10px 40px rgba(0, 0, 0, 0.4);
            --shadow-lg: 0 20px 60px rgba(0, 0, 0, 0.6);
            --shadow-glow: 0 0 30px rgba(59, 130, 246, 0.2);
        }

        /* --------------------------------------------------------------------
           02. BASE TYPOGRAPHY & BODY
           -------------------------------------------------------------------- */
        body {
            font-family: var(--font-sans);
            color: var(--text-primary);
            background-color: var(--bg-base);
            line-height: 1.7;
            overflow-x: hidden;
            position: relative;
            min-height: 100vh;
        }

        ::-webkit-scrollbar { width: 10px; }
        ::-webkit-scrollbar-track { background: var(--bg-base); }
        ::-webkit-scrollbar-thumb { background: var(--glass-border); border-radius: 10px; border: 2px solid var(--bg-base); }
        ::-webkit-scrollbar-thumb:hover { background: var(--brand-primary); }

        h1, h2, h3, h4, h5, h6 { 
            font-weight: 800; 
            line-height: 1.2; 
            color: var(--text-primary); 
            letter-spacing: -0.02em; 
        }
        
        p { margin-bottom: 1.25rem; color: var(--text-secondary); }
        a { color: var(--brand-primary); text-decoration: none; transition: var(--transition-fast); }
        strong { font-weight: 700; color: var(--text-primary); }

        .text-gradient {
            background: linear-gradient(135deg, var(--brand-primary), var(--brand-accent), var(--brand-primary));
            background-size: 200% auto;
            color: transparent;
            -webkit-background-clip: text;
            background-clip: text;
            animation: gradientText 5s linear infinite;
        }

        .mono { font-family: var(--font-mono); }

        /* --------------------------------------------------------------------
           03. ADVANCED BACKGROUND ENGINE
           -------------------------------------------------------------------- */
        .bg-engine {
            position: fixed;
            inset: 0;
            z-index: var(--z-negative);
            pointer-events: none;
            overflow: hidden;
            background: linear-gradient(135deg, var(--bg-base), var(--bg-gradient-1));
        }

        .bg-mesh {
            position: absolute;
            inset: 0;
            background-image: 
                radial-gradient(at 0% 0%, rgba(37,99,235,0.15) 0px, transparent 50%),
                radial-gradient(at 100% 0%, rgba(139,92,246,0.15) 0px, transparent 50%),
                radial-gradient(at 100% 100%, rgba(6,182,212,0.15) 0px, transparent 50%),
                radial-gradient(at 0% 100%, rgba(37,99,235,0.15) 0px, transparent 50%);
            filter: blur(80px);
            opacity: 0.8;
            animation: breatheMesh 20s ease-in-out infinite alternate;
        }

        .bg-grid {
            position: absolute;
            inset: 0;
            background-image: 
                linear-gradient(var(--grid-line) 1px, transparent 1px),
                linear-gradient(90deg, var(--grid-line) 1px, transparent 1px);
            background-size: 40px 40px;
            mask-image: radial-gradient(ellipse 80% 80% at 50% 50%, black 20%, transparent 80%);
            -webkit-mask-image: radial-gradient(ellipse 80% 80% at 50% 50%, black 20%, transparent 80%);
            opacity: 0.5;
        }

        #particle-canvas {
            position: absolute;
            inset: 0;
            width: 100%;
            height: 100%;
        }

        /* --------------------------------------------------------------------
           04. PRELOADER
           -------------------------------------------------------------------- */
        .preloader {
            position: fixed; inset: 0;
            background: var(--bg-base);
            z-index: 99999;
            display: flex; flex-direction: column;
            justify-content: center; align-items: center;
            transition: opacity 0.8s ease, visibility 0.8s;
        }
        .preloader.hidden { opacity: 0; visibility: hidden; }

        .gear-loader {
            width: 80px; height: 80px;
            border: 6px dashed var(--brand-primary);
            border-radius: 50%;
            animation: spinGear 4s linear infinite;
            margin-bottom: 20px;
            position: relative;
        }
        .gear-loader::before {
            content: ''; position: absolute;
            inset: 10px; border: 4px solid var(--brand-accent);
            border-radius: 50%;
            animation: spinGear 2s linear infinite reverse;
        }
        .loading-text {
            font-family: var(--font-mono); font-size: 14px;
            color: var(--brand-primary); letter-spacing: 4px;
            text-transform: uppercase;
            animation: pulse 1.5s ease-in-out infinite;
        }

        /* --------------------------------------------------------------------
           05. UI COMPONENTS (Buttons, Glass Panels, Badges)
           -------------------------------------------------------------------- */
        .glass-panel {
            background: var(--glass-bg);
            backdrop-filter: blur(20px);
            -webkit-backdrop-filter: blur(20px);
            border: 1px solid var(--glass-border);
            border-radius: var(--radius-lg);
            box-shadow: var(--shadow-md);
            position: relative;
            overflow: hidden;
            transition: var(--transition-normal);
        }
        .glass-panel::after {
            content: ''; position: absolute; top: 0; left: 0; right: 0; height: 1px;
            background: linear-gradient(90deg, transparent, var(--glass-highlight), transparent);
        }

        .btn {
            display: inline-flex; align-items: center; justify-content: center;
            gap: 10px; padding: 14px 28px; border-radius: var(--radius-md);
            font-family: var(--font-sans); font-weight: 600; font-size: 1rem;
            cursor: pointer; transition: var(--transition-normal);
            border: 1px solid transparent; text-decoration: none;
            position: relative; overflow: hidden;
            z-index: 1;
        }
        
        .btn-primary {
            background: linear-gradient(135deg, var(--brand-primary), var(--brand-accent));
            color: #ffffff !important;
            box-shadow: 0 4px 15px rgba(37, 99, 235, 0.3);
            border: 1px solid rgba(255,255,255,0.1);
        }
        .btn-primary::before {
            content: ''; position: absolute; inset: 0;
            background: linear-gradient(135deg, var(--brand-accent), var(--brand-primary));
            opacity: 0; transition: var(--transition-normal); z-index: -1;
        }
        .btn-primary:hover::before { opacity: 1; }
        .btn-primary:hover { transform: translateY(-3px) scale(1.02); box-shadow: var(--shadow-lg); }

        .btn-secondary {
            background: var(--glass-bg); color: var(--text-primary);
            border-color: var(--glass-border); backdrop-filter: blur(10px);
        }
        .btn-secondary:hover {
            border-color: var(--brand-primary); color: var(--brand-primary);
            background: var(--brand-primary-light); transform: translateY(-3px);
        }

        .btn-icon {
            width: 45px; height: 45px; padding: 0; border-radius: 50%;
            display: flex; align-items: center; justify-content: center;
            background: var(--glass-bg); border: 1px solid var(--glass-border);
            color: var(--text-primary); font-size: 1.2rem;
            transition: var(--transition-normal); backdrop-filter: blur(10px);
            cursor: pointer;
        }
        .btn-icon:hover {
            background: var(--brand-primary); color: white;
            border-color: var(--brand-primary); transform: translateY(-3px) rotate(10deg);
        }

        .badge {
            display: inline-flex; align-items: center; gap: 8px;
            padding: 8px 16px; border-radius: var(--radius-full);
            font-family: var(--font-mono); font-size: 0.8rem; font-weight: 600;
            background: var(--brand-primary-light); color: var(--brand-primary);
            border: 1px solid rgba(37, 99, 235, 0.2); text-transform: uppercase;
            letter-spacing: 1px;
        }

        /* --------------------------------------------------------------------
           06. LAYOUT & NAVIGATION
           -------------------------------------------------------------------- */
        .container {
            width: 100%; max-width: 1400px; margin: 0 auto;
            padding: 0 5%; position: relative;
        }
        
        section { padding: 120px 0; position: relative; }

        .section-header { text-align: center; max-width: 800px; margin: 0 auto 60px auto; }
        .section-header .badge { margin-bottom: 20px; }
        .section-title { font-size: 3.5rem; margin-bottom: 20px; }
        .section-desc { font-size: 1.15rem; color: var(--text-muted); }

        header {
            position: fixed; top: 0; left: 0; width: 100%; height: 90px;
            display: flex; align-items: center; z-index: var(--z-sticky);
            transition: var(--transition-normal); border-bottom: 1px solid transparent;
        }
        header.scrolled {
            height: 75px; background: var(--glass-bg);
            backdrop-filter: blur(24px); border-bottom: 1px solid var(--glass-border);
            box-shadow: var(--shadow-sm);
        }

        .nav-wrapper { display: flex; justify-content: space-between; align-items: center; width: 100%; }
        
        .logo {
            font-family: var(--font-mono); font-size: 1.5rem; font-weight: 800;
            color: var(--text-primary); text-decoration: none; display: flex; align-items: center; gap: 12px;
        }
        .logo-icon {
            width: 40px; height: 40px; background: var(--brand-primary); color: white;
            border-radius: var(--radius-sm); display: flex; align-items: center; justify-content: center;
            font-size: 1.2rem; transform: rotate(45deg); transition: var(--transition-normal);
        }
        .logo-icon i { transform: rotate(-45deg); }
        .logo:hover .logo-icon { transform: rotate(135deg); border-radius: 50%; }

        .nav-links { display: flex; gap: 2.5rem; list-style: none; margin: 0; padding: 0; }
        .nav-link {
            font-size: 0.95rem; font-weight: 600; color: var(--text-secondary);
            text-decoration: none; transition: var(--transition-fast); position: relative;
        }
        .nav-link::after {
            content: ''; position: absolute; bottom: -5px; left: 0; width: 0; height: 2px;
            background: var(--brand-primary); transition: var(--transition-normal);
        }
        .nav-link:hover, .nav-link.active { color: var(--brand-primary); }
        .nav-link:hover::after, .nav-link.active::after { width: 100%; }

        .nav-actions { display: flex; align-items: center; gap: 15px; }
        
        .mobile-toggle {
            display: none; font-size: 1.5rem; color: var(--text-primary);
            background: none; border: none; cursor: pointer;
        }

        /* --------------------------------------------------------------------
           07. INFINITE SCROLL MARQUEE (Tech Stack)
           -------------------------------------------------------------------- */
        .marquee-wrapper {
            width: 100%; overflow: hidden; padding: 40px 0;
            background: var(--bg-surface); border-top: 1px solid var(--glass-border);
            border-bottom: 1px solid var(--glass-border);
            position: relative;
        }
        .marquee-wrapper::before, .marquee-wrapper::after {
            content: ""; position: absolute; top: 0; width: 250px; height: 100%; z-index: 2;
        }
        .marquee-wrapper::before { left: 0; background: linear-gradient(to right, var(--bg-surface), transparent); }
        .marquee-wrapper::after { right: 0; background: linear-gradient(to left, var(--bg-surface), transparent); }
        
        .marquee-content {
            display: flex; width: max-content;
            animation: marquee 30s linear infinite;
        }
        .marquee-item {
            display: flex; align-items: center; gap: 15px; padding: 0 40px;
            font-family: var(--font-mono); font-weight: 700; font-size: 1.5rem;
            color: var(--text-muted); opacity: 0.6; transition: var(--transition-fast);
        }
        .marquee-item:hover { color: var(--brand-primary); opacity: 1; transform: scale(1.1); }
        .marquee-item i { font-size: 2rem; }

        @keyframes marquee {
            0% { transform: translateX(0); }
            100% { transform: translateX(-50%); }
        }

        /* --------------------------------------------------------------------
           08. HERO SECTION
           -------------------------------------------------------------------- */
        #hero {
            min-height: 100vh; display: flex; align-items: center;
            padding-top: 120px; padding-bottom: 60px;
        }
        
        .hero-grid {
            display: grid; grid-template-columns: 1.2fr 0.8fr;
            gap: 4rem; align-items: center;
        }

        .hero-content .badge { margin-bottom: 30px; animation: slideDown 1s ease forwards; opacity: 0; }
        .hero-title {
            font-size: clamp(3rem, 5vw, 5rem); line-height: 1.1;
            margin-bottom: 25px; opacity: 0; animation: slideUp 1s ease 0.2s forwards;
        }
        
        /* Typewriter specific styling */
        .typewriter-wrapper { height: 1.2em; display: block; overflow: hidden; }
        .typewriter-text { 
            color: var(--brand-primary); 
            border-right: 4px solid var(--brand-primary);
            white-space: nowrap;
            animation: blink-caret 0.75s step-end infinite;
        }

        .hero-desc {
            font-size: 1.25rem; color: var(--text-muted); max-width: 650px;
            margin-bottom: 40px; opacity: 0; animation: slideUp 1s ease 0.4s forwards;
        }

        .hero-metrics {
            display: grid; grid-template-columns: repeat(3, 1fr);
            gap: 20px; margin-bottom: 40px;
            padding-top: 30px; border-top: 1px dashed var(--glass-border);
            opacity: 0; animation: slideUp 1s ease 0.6s forwards;
        }
        .metric { display: flex; flex-direction: column; gap: 5px; }
        .metric-value { font-family: var(--font-mono); font-size: 2.5rem; font-weight: 800; color: var(--text-primary); }
        .metric-label { font-size: 0.9rem; color: var(--text-muted); font-weight: 600; text-transform: uppercase; }

        .hero-btns {
            display: flex; gap: 20px; opacity: 0;
            animation: slideUp 1s ease 0.8s forwards;
        }

        /* 3D Visual Profile */
        .hero-visual { position: relative; opacity: 0; animation: fadeIn 1.5s ease 1s forwards; perspective: 1000px; }
        
        .profile-card {
            padding: 50px; text-align: center; z-index: 2;
            transform-style: preserve-3d;
            transition: transform 0.1s ease;
        }
        .profile-img-wrap {
            width: 300px; height: 300px; margin: 0 auto 30px auto;
            border-radius: 50%; padding: 10px;
            background: linear-gradient(135deg, var(--brand-primary), var(--brand-accent));
            position: relative;
            transform: translateZ(30px);
        }
        .profile-img-wrap::before {
            content: ''; position: absolute; inset: -20px;
            background: radial-gradient(circle, var(--brand-primary) 0%, transparent 70%);
            opacity: 0.4; filter: blur(40px); animation: pulseGlow 4s infinite alternate; z-index: -1;
        }
        .profile-img {
            width: 100%; height: 100%; border-radius: 50%;
            object-fit: cover; border: 4px solid var(--bg-surface);
        }
        
        .profile-card h3 { font-size: 2rem; margin-bottom: 5px; transform: translateZ(20px); }
        .profile-card p { font-family: var(--font-mono); color: var(--brand-primary); margin-bottom: 20px; font-weight: 600; transform: translateZ(15px); }
        
        .float-badge {
            position: absolute; background: var(--glass-bg); backdrop-filter: blur(10px);
            border: 1px solid var(--glass-border); padding: 15px 25px; border-radius: var(--radius-md);
            display: flex; align-items: center; gap: 15px; box-shadow: var(--shadow-md);
            z-index: 3; animation: float 6s ease-in-out infinite;
            transform: translateZ(40px);
        }
        .float-1 { top: 5%; right: -30px; animation-delay: 0s; }
        .float-2 { bottom: 15%; left: -40px; animation-delay: 2s; }
        .float-icon { width: 45px; height: 45px; border-radius: 50%; background: var(--brand-primary-light); color: var(--brand-primary); display: flex; justify-content: center; align-items: center; font-size: 1.3rem; }
        .float-text { font-weight: 700; font-size: 1rem; display: flex; flex-direction: column; }
        .float-text span { font-size: 0.75rem; color: var(--text-muted); font-weight: 500; }

        /* --------------------------------------------------------------------
           09. ABOUT & TABBED INTERFACE
           -------------------------------------------------------------------- */
        .about-grid {
            display: grid; grid-template-columns: 1fr 1.2fr;
            gap: 5rem; align-items: start;
        }
        
        .about-visual { position: relative; }
        .about-image { width: 100%; border-radius: var(--radius-lg); border: 1px solid var(--glass-border); box-shadow: var(--shadow-lg); }
        .location-badge {
            position: absolute; bottom: -20px; left: -20px;
            background: var(--bg-surface); padding: 20px 30px;
            border-radius: var(--radius-lg); border: 1px solid var(--glass-border);
            box-shadow: var(--shadow-md); display: flex; align-items: center; gap: 15px;
        }
        .location-badge i { font-size: 2rem; color: var(--brand-primary); }
        
        /* Custom Tabs System */
        .tabs-header { display: flex; gap: 15px; margin-bottom: 30px; border-bottom: 2px solid var(--glass-border); padding-bottom: 10px; }
        .tab-btn { background: none; border: none; font-family: var(--font-sans); font-size: 1.1rem; font-weight: 700; color: var(--text-muted); cursor: pointer; padding: 10px 20px; position: relative; transition: var(--transition-fast); }
        .tab-btn.active { color: var(--brand-primary); }
        .tab-btn::after { content: ''; position: absolute; bottom: -12px; left: 0; width: 0; height: 3px; background: var(--brand-primary); transition: var(--transition-normal); border-radius: 3px 3px 0 0; }
        .tab-btn.active::after { width: 100%; }
        
        .tab-pane { display: none; animation: fadeIn 0.5s ease forwards; }
        .tab-pane.active { display: block; }
        
        .tab-pane p { font-size: 1.1rem; line-height: 1.8; margin-bottom: 20px; }
        .highlight-box { background: var(--brand-primary-light); border-left: 4px solid var(--brand-primary); padding: 20px; border-radius: 0 var(--radius-sm) var(--radius-sm) 0; margin: 25px 0; }
        .highlight-box h4 { margin-bottom: 10px; color: var(--text-primary); }

        /* --------------------------------------------------------------------
           10. ENGINEERING SKILLS & GEAR CALCULATOR WIDGET
           -------------------------------------------------------------------- */
        .skills-grid {
            display: grid; grid-template-columns: 1fr 1fr; gap: 4rem;
        }

        .skill-bars { display: flex; flex-direction: column; gap: 30px; }
        .skill-item { background: var(--glass-bg); padding: 30px; border-radius: var(--radius-md); border: 1px solid var(--glass-border); }
        .skill-header { display: flex; justify-content: space-between; align-items: center; margin-bottom: 20px; }
        .skill-title { display: flex; align-items: center; gap: 15px; font-weight: 700; font-size: 1.2rem; }
        .skill-icon { width: 50px; height: 50px; border-radius: 12px; background: var(--brand-primary-light); color: var(--brand-primary); display: flex; justify-content: center; align-items: center; font-size: 1.5rem; }
        .skill-pct { font-family: var(--font-mono); font-weight: 800; font-size: 1.2rem; color: var(--brand-primary); }
        
        .progress-track { width: 100%; height: 10px; background: var(--glass-border); border-radius: var(--radius-full); overflow: hidden; position: relative; }
        .progress-fill { position: absolute; top: 0; left: 0; height: 100%; background: linear-gradient(90deg, var(--brand-primary), var(--brand-accent)); border-radius: var(--radius-full); width: 0; transition: width 1.5s cubic-bezier(0.175, 0.885, 0.32, 1.275); }

        /* Interactive Gear Math Widget */
        .calculator-widget {
            background: var(--bg-surface); padding: 40px;
            border-radius: var(--radius-lg); border: 1px solid var(--glass-border);
            box-shadow: var(--shadow-lg);
        }
        .calc-header { margin-bottom: 25px; border-bottom: 1px solid var(--glass-border); padding-bottom: 15px; }
        .calc-title { font-family: var(--font-mono); font-size: 1.2rem; color: var(--brand-primary); display: flex; align-items: center; gap: 10px; }
        
        .calc-form-group { margin-bottom: 20px; }
        .calc-label { display: block; font-size: 0.9rem; font-weight: 600; margin-bottom: 8px; }
        .calc-input { width: 100%; padding: 12px 15px; border-radius: var(--radius-sm); border: 1px solid var(--glass-border); background: var(--bg-base); color: var(--text-primary); font-family: var(--font-mono); transition: var(--transition-fast); }
        .calc-input:focus { outline: none; border-color: var(--brand-primary); box-shadow: 0 0 0 3px var(--brand-primary-light); }
        
        .calc-result-box {
            margin-top: 30px; background: var(--brand-primary-light);
            padding: 20px; border-radius: var(--radius-sm); border: 1px dashed var(--brand-primary);
            text-align: center;
        }
        .calc-result-label { font-size: 0.85rem; text-transform: uppercase; letter-spacing: 1px; font-weight: 700; color: var(--text-secondary); }
        .calc-result-value { font-family: var(--font-mono); font-size: 2.5rem; font-weight: 800; color: var(--brand-primary); margin-top: 5px; }
        .calc-note { font-size: 0.8rem; color: var(--text-muted); margin-top: 10px; font-style: italic; }

        /* --------------------------------------------------------------------
           11. EXPANDED PORTFOLIO SECTION (Grid + Modals)
           -------------------------------------------------------------------- */
        .portfolio-filters { display: flex; justify-content: center; flex-wrap: wrap; gap: 15px; margin-bottom: 50px; }
        .filter-btn {
            background: var(--glass-bg); border: 1px solid var(--glass-border);
            padding: 12px 28px; border-radius: var(--radius-full);
            font-family: var(--font-mono); font-weight: 600; font-size: 0.95rem;
            color: var(--text-secondary); cursor: pointer; transition: var(--transition-normal);
        }
        .filter-btn.active, .filter-btn:hover {
            background: var(--brand-primary); color: white; border-color: var(--brand-primary);
            box-shadow: 0 5px 15px rgba(37, 99, 235, 0.3); transform: translateY(-2px);
        }

        .portfolio-grid {
            display: grid; grid-template-columns: repeat(auto-fill, minmax(400px, 1fr));
            gap: 40px;
        }

        .portfolio-card {
            display: flex; flex-direction: column; overflow: hidden;
            padding: 0; cursor: pointer;
        }
        
        .port-img-wrap {
            width: 100%; height: 280px; overflow: hidden; position: relative;
            background: var(--glass-border);
        }
        .port-img-wrap img {
            width: 100%; height: 100%; object-fit: cover;
            transition: transform 0.8s cubic-bezier(0.175, 0.885, 0.32, 1.275);
        }
        .portfolio-card:hover .port-img-wrap img { transform: scale(1.1) rotate(1deg); }
        
        .port-overlay {
            position: absolute; inset: 0; background: rgba(15, 23, 42, 0.75);
            display: flex; justify-content: center; align-items: center;
            opacity: 0; transition: var(--transition-normal); backdrop-filter: blur(5px);
        }
        .portfolio-card:hover .port-overlay { opacity: 1; }
        .port-view-btn {
            width: 60px; height: 60px; background: var(--brand-primary); color: white;
            border-radius: 50%; display: flex; justify-content: center; align-items: center;
            font-size: 1.5rem; transform: translateY(20px); transition: var(--transition-normal);
        }
        .portfolio-card:hover .port-view-btn { transform: translateY(0); }

        .port-content { padding: 30px; flex-grow: 1; display: flex; flex-direction: column; }
        .port-cat { font-family: var(--font-mono); font-size: 0.8rem; color: var(--brand-primary); font-weight: 700; margin-bottom: 12px; text-transform: uppercase; letter-spacing: 1px; }
        .port-title { font-size: 1.5rem; margin-bottom: 15px; }
        .port-desc { font-size: 1rem; color: var(--text-muted); margin-bottom: 25px; flex-grow: 1; }
        .port-meta { display: flex; justify-content: space-between; align-items: center; border-top: 1px solid var(--glass-border); padding-top: 20px; }
        .port-tool { display: flex; gap: 12px; color: var(--text-secondary); font-size: 1.2rem; }
        .port-meta-link { font-weight: 700; display: flex; align-items: center; gap: 8px; color: var(--text-primary); transition: var(--transition-fast); }
        .portfolio-card:hover .port-meta-link { color: var(--brand-primary); gap: 12px; }

        /* --------------------------------------------------------------------
           12. PUBLICATIONS & INSIGHTS (Blog styling)
           -------------------------------------------------------------------- */
        .insights-grid { display: grid; grid-template-columns: repeat(2, 1fr); gap: 40px; }
        .article-card {
            display: flex; gap: 30px; background: var(--glass-bg); padding: 30px;
            border-radius: var(--radius-lg); border: 1px solid var(--glass-border);
            transition: var(--transition-normal); align-items: center;
        }
        .article-card:hover { border-color: var(--brand-primary); transform: translateX(10px); box-shadow: var(--shadow-lg); }
        .article-date {
            min-width: 100px; text-align: center; padding: 20px;
            background: var(--bg-surface); border-radius: var(--radius-md);
            border: 1px solid var(--glass-border);
        }
        .date-month { display: block; font-weight: 800; font-size: 1.2rem; color: var(--brand-primary); text-transform: uppercase; }
        .date-year { font-family: var(--font-mono); color: var(--text-muted); font-size: 0.9rem; }
        
        .article-content h3 { font-size: 1.4rem; margin-bottom: 10px; }
        .article-content p { margin-bottom: 15px; font-size: 0.95rem; }
        .read-more { font-family: var(--font-mono); font-weight: 700; font-size: 0.9rem; color: var(--brand-primary); display: flex; align-items: center; gap: 5px; }

        /* --------------------------------------------------------------------
           13. CONTACT MODULE & MULTI-STEP FORM
           -------------------------------------------------------------------- */
        .contact-grid { display: grid; grid-template-columns: 1fr 1.5fr; gap: 5rem; }
        .contact-info { display: flex; flex-direction: column; gap: 30px; }
        .contact-card { padding: 30px; display: flex; align-items: flex-start; gap: 20px; background: var(--glass-bg); border-radius: var(--radius-md); border: 1px solid var(--glass-border); }
        .contact-icon { width: 60px; height: 60px; border-radius: var(--radius-md); background: var(--brand-primary-light); color: var(--brand-primary); display: flex; justify-content: center; align-items: center; font-size: 1.5rem; flex-shrink: 0; }
        .contact-details h4 { margin-bottom: 5px; font-size: 1.2rem; }
        .contact-details p, .contact-details a { color: var(--text-secondary); font-size: 1.05rem; }
        
        /* Advanced Form Styling */
        .advanced-form { background: var(--bg-surface); padding: 50px; border-radius: var(--radius-lg); border: 1px solid var(--glass-border); box-shadow: var(--shadow-lg); }
        .form-row { display: grid; grid-template-columns: 1fr 1fr; gap: 25px; margin-bottom: 25px; }
        .input-group { display: flex; flex-direction: column; gap: 10px; position: relative; }
        .input-group label { font-size: 0.95rem; font-weight: 600; color: var(--text-primary); }
        
        .form-control {
            padding: 16px 20px; border-radius: var(--radius-md);
            background: var(--bg-base); border: 1px solid var(--glass-border);
            color: var(--text-primary); font-family: var(--font-sans); font-size: 1.05rem;
            transition: var(--transition-fast); width: 100%;
        }
        .form-control:focus { outline: none; border-color: var(--brand-primary); box-shadow: 0 0 0 4px var(--brand-primary-light); background: var(--bg-surface); }
        textarea.form-control { resize: vertical; min-height: 180px; }
        
        /* Custom Checkbox */
        .custom-checkbox { display: flex; align-items: center; gap: 10px; margin-bottom: 30px; cursor: pointer; }
        .custom-checkbox input { display: none; }
        .checkmark { width: 24px; height: 24px; border: 2px solid var(--glass-border); border-radius: 6px; display: flex; justify-content: center; align-items: center; transition: var(--transition-fast); }
        .custom-checkbox input:checked + .checkmark { background: var(--brand-primary); border-color: var(--brand-primary); }
        .custom-checkbox input:checked + .checkmark::after { content: '\f00c'; font-family: 'Font Awesome 6 Free'; font-weight: 900; color: white; font-size: 0.8rem; }
        .check-label { font-size: 0.95rem; color: var(--text-secondary); }

        /* --------------------------------------------------------------------
           14. MEGA FOOTER
           -------------------------------------------------------------------- */
        footer {
            background: var(--bg-gradient-1); border-top: 1px solid var(--glass-border);
            padding: 100px 0 40px 0; margin-top: 120px; position: relative; overflow: hidden;
        }
        .footer-grid { display: grid; grid-template-columns: 2fr 1fr 1fr 1.5fr; gap: 4rem; margin-bottom: 80px; position: relative; z-index: 2; }
        .footer-brand p { margin-top: 25px; color: var(--text-muted); max-width: 400px; font-size: 1.05rem; }
        
        .footer-title { font-size: 1.3rem; margin-bottom: 30px; color: var(--text-primary); }
        .footer-links { list-style: none; display: flex; flex-direction: column; gap: 15px; }
        .footer-links a { color: var(--text-muted); transition: var(--transition-fast); font-size: 1.05rem; display: inline-flex; align-items: center; gap: 8px; }
        .footer-links a i { font-size: 0.8rem; color: var(--brand-primary); opacity: 0; transition: var(--transition-fast); transform: translateX(-10px); }
        .footer-links a:hover { color: var(--brand-primary); padding-left: 5px; }
        .footer-links a:hover i { opacity: 1; transform: translateX(0); }
        
        .social-circle-links { display: flex; gap: 15px; }
        .social-circle-links a { width: 45px; height: 45px; border-radius: 50%; background: var(--bg-surface); border: 1px solid var(--glass-border); display: flex; justify-content: center; align-items: center; color: var(--text-primary); font-size: 1.2rem; transition: var(--transition-fast); }
        .social-circle-links a:hover { background: var(--brand-primary); color: white; border-color: var(--brand-primary); transform: translateY(-5px); }

        .footer-bottom { display: flex; justify-content: space-between; align-items: center; padding-top: 40px; border-top: 1px solid var(--glass-border); color: var(--text-muted); font-size: 0.95rem; position: relative; z-index: 2; }

        /* --------------------------------------------------------------------
           15. MODAL SYSTEMS
           -------------------------------------------------------------------- */
        .modal { position: fixed; inset: 0; background: rgba(0,0,0,0.85); backdrop-filter: blur(10px); z-index: var(--z-modal); display: flex; justify-content: center; align-items: center; opacity: 0; visibility: hidden; transition: var(--transition-normal); padding: 20px; }
        .modal.active { opacity: 1; visibility: visible; }
        .modal-content { width: 100%; max-width: 900px; max-height: 90vh; overflow-y: auto; background: var(--bg-surface); border: 1px solid var(--glass-border); border-radius: var(--radius-lg); padding: 50px; position: relative; transform: translateY(50px) scale(0.95); transition: var(--transition-normal); }
        .modal.active .modal-content { transform: translateY(0) scale(1); }
        
        .modal-close { position: absolute; top: 25px; right: 25px; width: 45px; height: 45px; border-radius: 50%; background: var(--bg-base); border: 1px solid var(--glass-border); color: var(--text-primary); display: flex; justify-content: center; align-items: center; font-size: 1.5rem; cursor: pointer; transition: var(--transition-fast); }
        .modal-close:hover { background: var(--brand-danger); color: white; border-color: var(--brand-danger); transform: rotate(90deg); }
        
        .modal-header { margin-bottom: 30px; border-bottom: 1px solid var(--glass-border); padding-bottom: 20px; }
        .modal-title { font-size: 2.5rem; margin-bottom: 10px; }
        .modal-body img { width: 100%; border-radius: var(--radius-md); margin-bottom: 30px; border: 1px solid var(--glass-border); }
        
        .spec-table { width: 100%; border-collapse: collapse; margin-top: 30px; }
        .spec-table td { padding: 15px; border-bottom: 1px solid var(--glass-border); }
        .spec-table tr td:first-child { font-weight: 700; color: var(--text-secondary); width: 30%; }
        .spec-table tr td:last-child { font-family: var(--font-mono); color: var(--text-primary); font-weight: 600; }

        /* --------------------------------------------------------------------
           16. ANIMATIONS & RESPONSIVE DESIGN
           -------------------------------------------------------------------- */
        @keyframes slideUp { from { opacity: 0; transform: translateY(40px); } to { opacity: 1; transform: translateY(0); } }
        @keyframes slideDown { from { opacity: 0; transform: translateY(-40px); } to { opacity: 1; transform: translateY(0); } }
        @keyframes fadeIn { from { opacity: 0; } to { opacity: 1; } }
        @keyframes spinGear { 100% { transform: rotate(360deg); } }
        @keyframes pulse { 0%, 100% { opacity: 1; } 50% { opacity: 0.5; } }
        @keyframes pulseGlow { 0% { transform: scale(0.95); opacity: 0.3; } 100% { transform: scale(1.1); opacity: 0.6; } }
        @keyframes float { 0%, 100% { transform: translateY(0); } 50% { transform: translateY(-20px); } }
        @keyframes breatheMesh { 0% { filter: blur(80px) brightness(1); } 100% { filter: blur(100px) brightness(1.2); } }
        @keyframes gradientText { 0% { background-position: 0% center; } 100% { background-position: 200% center; } }
        @keyframes blink-caret { from, to { border-color: transparent } 50% { border-color: var(--brand-primary); } }

        /* Intersection Observer Classes */
        .reveal { opacity: 0; transform: translateY(50px); transition: all 0.8s cubic-bezier(0.175, 0.885, 0.32, 1.275); }
        .reveal.active { opacity: 1; transform: translateY(0); }
        .reveal-left { opacity: 0; transform: translateX(-50px); transition: all 0.8s cubic-bezier(0.175, 0.885, 0.32, 1.275); }
        .reveal-left.active { opacity: 1; transform: translateX(0); }
        .reveal-right { opacity: 0; transform: translateX(50px); transition: all 0.8s cubic-bezier(0.175, 0.885, 0.32, 1.275); }
        .reveal-right.active { opacity: 1; transform: translateX(0); }

        @media (max-width: 1200px) {
            .hero-title { font-size: 3.5rem; }
            .portfolio-grid { grid-template-columns: repeat(2, 1fr); }
            .footer-grid { grid-template-columns: 1fr 1fr; }
        }
        @media (max-width: 992px) {
            .hero-grid, .about-grid, .skills-grid, .contact-grid { grid-template-columns: 1fr; }
            .hero-visual { order: -1; display: flex; justify-content: center; }
            .about-visual { max-width: 600px; margin: 0 auto; }
        }
        @media (max-width: 768px) {
            .nav-links { position: absolute; top: 90px; left: 0; width: 100%; background: var(--bg-surface); flex-direction: column; padding: 30px; gap: 20px; border-bottom: 1px solid var(--glass-border); clip-path: polygon(0 0, 100% 0, 100% 0, 0 0); transition: clip-path 0.4s ease; }
            .nav-links.nav-active { clip-path: polygon(0 0, 100% 0, 100% 100%, 0% 100%); }
            .mobile-toggle { display: block; }
            .hero-metrics { grid-template-columns: 1fr; }
            .portfolio-grid { grid-template-columns: 1fr; }
            .form-row { grid-template-columns: 1fr; }
            .footer-grid { grid-template-columns: 1fr; }
            .footer-bottom { flex-direction: column; gap: 20px; text-align: center; }
        }
    </style>
</head>
<body class="light-mode">

    <!-- PRELOADER -->
    <div class="preloader" id="preloader">
        <div class="gear-loader"></div>
        <div class="loading-text">Loading Assets...</div>
    </div>

    <!-- BACKGROUND ENGINE -->
    <div class="bg-engine">
        <canvas id="particle-canvas"></canvas>
        <div class="bg-mesh"></div>
        <div class="bg-grid"></div>
    </div>

    <!-- HEADER NAVIGATION -->
    <header id="header">
        <div class="container nav-wrapper">
            <a href="#" class="logo">
                <div class="logo-icon"><i class="fas fa-cube"></i></div>
                3D Mech<span>Design</span>
            </a>
            
            <ul class="nav-links">
                <li><a href="#hero" class="nav-link active">Home</a></li>
                <li><a href="#about" class="nav-link">About</a></li>
                <li><a href="#expertise" class="nav-link">Expertise</a></li>
                <li><a href="#portfolio" class="nav-link">Projects</a></li>
                <li><a href="#insights" class="nav-link">Insights</a></li>
                <li><a href="#contact" class="nav-link">Contact</a></li>
            </ul>
            
            <div class="nav-actions">
                <button id="theme-toggle" class="btn-icon" aria-label="Toggle Dark Mode">
                    <i class="fas fa-moon"></i>
                </button>
                <button class="mobile-toggle">
                    <i class="fas fa-bars"></i>
                </button>
            </div>
        </div>
    </header>

    <main>
        <!-- ==================================================================
             SECTION 1: HERO
             ================================================================== -->
        <section id="hero">
            <div class="container hero-grid">
                <div class="hero-content">
                    <div class="badge"><i class="fas fa-rocket"></i> Mechanical Design Consultant</div>
                    <h1 class="hero-title">
                        Precision Engineering <br>
                        <span class="typewriter-wrapper">
                            <span class="typewriter-text" id="typewriter"></span>
                        </span>
                    </h1>
                    <p class="hero-desc">
                        I am Abdur Rafay Yousuf, based in Karachi, Pakistan. I specialize in complex parametric CAD modeling, Computational Fluid Dynamics (CFD), and thermodynamic prototyping for industrial applications.
                    </p>
                    
                    <div class="hero-metrics">
                        <div class="metric">
                            <span class="metric-value" data-target="150">0</span>
                            <span class="metric-label">CAD Models</span>
                        </div>
                        <div class="metric">
                            <span class="metric-value" data-target="4">0</span>
                            <span class="metric-label">Years Exp.</span>
                        </div>
                        <div class="metric">
                            <span class="metric-value">100%</span>
                            <span class="metric-label">Accuracy</span>
                        </div>
                    </div>

                    <div class="hero-btns">
                        <a href="#portfolio" class="btn btn-primary">
                            Explore Portfolio <i class="fas fa-arrow-right"></i>
                        </a>
                        <a href="#contact" class="btn btn-secondary">
                            Contact Me <i class="fas fa-envelope"></i>
                        </a>
                    </div>
                </div>

                <div class="hero-visual" id="heroVisual">
                    <div class="float-badge float-1">
                        <div class="float-icon"><i class="fas fa-wind"></i></div>
                        <div class="float-text">CFD Analysis <span>Advanced Flow Regimes</span></div>
                    </div>
                    <div class="float-badge float-2">
                        <div class="float-icon"><i class="fas fa-cogs"></i></div>
                        <div class="float-text">Gear Engineering <span>Involute Math Profiles</span></div>
                    </div>

                    <div class="glass-panel profile-card">
                        <div class="profile-img-wrap">
                            <img src="https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?fit=crop&w=600&h=600" alt="Abdur Rafay Yousuf" class="profile-img">
                        </div>
                        <h3>Abdur Rafay Yousuf</h3>
                        <p>Founder, 3D Mech Design</p>
                        <div class="badge"><i class="fas fa-university"></i> DHA Suffa University</div>
                    </div>
                </div>
            </div>
        </section>

        <!-- ==================================================================
             INFINITE SCROLL TECH MARQUEE
             ================================================================== -->
        <div class="marquee-wrapper">
            <div class="marquee-content">
                <!-- Set 1 -->
                <div class="marquee-item"><i class="fa-solid fa-code"></i> SolidWorks</div>
                <div class="marquee-item"><i class="fa-brands fa-hubspot"></i> Fusion 360</div>
                <div class="marquee-item"><i class="fa-solid fa-pen-ruler"></i> AutoCAD</div>
                <div class="marquee-item"><i class="fa-solid fa-calculator"></i> MATLAB</div>
                <div class="marquee-item"><i class="fa-solid fa-network-wired"></i> Ansys</div>
                <div class="marquee-item"><i class="fa-brands fa-usb"></i> Arduino Uno</div>
                <div class="marquee-item"><i class="fa-solid fa-wind"></i> CFD Simulation</div>
                <!-- Set 2 (Duplicate for seamless loop) -->
                <div class="marquee-item"><i class="fa-solid fa-code"></i> SolidWorks</div>
                <div class="marquee-item"><i class="fa-brands fa-hubspot"></i> Fusion 360</div>
                <div class="marquee-item"><i class="fa-solid fa-pen-ruler"></i> AutoCAD</div>
                <div class="marquee-item"><i class="fa-solid fa-calculator"></i> MATLAB</div>
                <div class="marquee-item"><i class="fa-solid fa-network-wired"></i> Ansys</div>
                <div class="marquee-item"><i class="fa-brands fa-usb"></i> Arduino Uno</div>
                <div class="marquee-item"><i class="fa-solid fa-wind"></i> CFD Simulation</div>
            </div>
        </div>

        <!-- ==================================================================
             SECTION 2: ABOUT & TABS
             ================================================================== -->
        <section id="about">
            <div class="container">
                <div class="section-header reveal">
                    <div class="badge">Who I Am</div>
                    <h2 class="section-title">Bridging Theory & <span class="text-gradient">Manufacturing</span></h2>
                    <p class="section-desc">Turning abstract physics and thermodynamic concepts into highly precise, manufacturable engineering solutions.</p>
                </div>

                <div class="about-grid">
                    <div class="about-visual reveal-left">
                        <img src="https://images.unsplash.com/photo-1581092160562-40aa08e78837?fit=crop&w=800&h=800" alt="Engineering Workspace" class="about-image">
                        <div class="location-badge">
                            <i class="fas fa-map-marker-alt"></i>
                            <div>
                                <h4 style="margin-bottom: 2px;">Based in</h4>
                                <span class="mono" style="color: var(--text-muted); font-size: 0.9rem;">Karachi, Pakistan</span>
                            </div>
                        </div>
                    </div>
                    
                    <div class="about-content reveal-right">
                        <!-- Custom Tabs -->
                        <div class="tabs-header">
                            <button class="tab-btn active" data-tab="mission">Mission</button>
                            <button class="tab-btn" data-tab="methodology">Methodology</button>
                            <button class="tab-btn" data-tab="mentorship">Mentorship</button>
                        </div>
                        
                        <!-- Tab 1: Mission -->
                        <div class="tab-pane active" id="tab-mission">
                            <h3 style="font-size: 1.8rem; margin-bottom: 20px;">Engineering with Purpose</h3>
                            <p>My core mission is to develop localized, highly efficient mechanical solutions. This drive was heavily inspired by personal family challenges regarding accessibility, which directly motivated the creation of the <strong>Mahfooz Wheelchair Project</strong>—a localized mobility device with stair-lifting capabilities.</p>
                            <div class="highlight-box">
                                <h4>3D Mech Design</h4>
                                <p style="margin: 0; font-size: 0.95rem;">Founded to provide professional mechanical design consultation. We draft technical proposals, flyers, and operate comprehensive parametric modeling projects for industry clients.</p>
                            </div>
                        </div>

                        <!-- Tab 2: Methodology -->
                        <div class="tab-pane" id="tab-methodology">
                            <h3 style="font-size: 1.8rem; margin-bottom: 20px;">The Design Process</h3>
                            <p>I strictly adhere to a mathematically validated design process. Whether it is a thermal sand battery or gear assembly, no dimension is arbitrary.</p>
                            <ul style="list-style: none; display: flex; flex-direction: column; gap: 15px; margin-top: 20px;">
                                <li><i class="fas fa-check-circle" style="color: var(--brand-primary); margin-right: 10px;"></i> <strong>Ideation:</strong> Mathematical formulation & sketches.</li>
                                <li><i class="fas fa-check-circle" style="color: var(--brand-primary); margin-right: 10px;"></i> <strong>CAD Phase:</strong> Parametric design in SolidWorks.</li>
                                <li><i class="fas fa-check-circle" style="color: var(--brand-primary); margin-right: 10px;"></i> <strong>Simulation:</strong> Stress testing & CFD validation.</li>
                                <li><i class="fas fa-check-circle" style="color: var(--brand-primary); margin-right: 10px;"></i> <strong>Production:</strong> Final manufacturing schematics.</li>
                            </ul>
                        </div>

                        <!-- Tab 3: Mentorship -->
                        <div class="tab-pane" id="tab-mentorship">
                            <h3 style="font-size: 1.8rem; margin-bottom: 20px;">Community & Skill Sharing</h3>
                            <p>Knowledge isolation hinders engineering progress. I actively log mentorship and skill-sharing activities with junior students and associates.</p>
                            <div class="glass-panel" style="padding: 20px; margin-top: 20px;">
                                <div style="display: flex; align-items: center; gap: 15px; margin-bottom: 15px;">
                                    <div style="width: 50px; height: 50px; border-radius: 50%; background: var(--brand-primary); color: white; display: flex; align-items: center; justify-content: center; font-weight: bold;">FK</div>
                                    <div>
                                        <h4 style="margin: 0;">Faizan Khan</h4>
                                        <span style="font-size: 0.85rem; color: var(--text-muted);">Junior Associate Mentee</span>
                                    </div>
                                </div>
                                <p style="margin: 0; font-size: 0.95rem; font-style: italic;">"Mentored directly in advanced computer-aided design skills, transferring practical parametric modeling knowledge."</p>
                            </div>
                        </div>

                    </div>
                </div>
            </div>
        </section>

        <!-- ==================================================================
             SECTION 3: EXPERTISE & INTERACTIVE GEAR CALCULATOR
             ================================================================== -->
        <section id="expertise">
            <div class="container">
                <div class="section-header reveal">
                    <div class="badge">Technical Arsenal</div>
                    <h2 class="section-title">Engineering <span class="text-gradient">Capabilities</span></h2>
                </div>

                <div class="skills-grid">
                    <div class="skill-bars reveal-left">
                        <div class="skill-item">
                            <div class="skill-header">
                                <div class="skill-title"><div class="skill-icon"><i class="fas fa-cube"></i></div> 3D CAD & Drafting</div>
                                <div class="skill-pct">95%</div>
                            </div>
                            <div class="progress-track"><div class="progress-fill" style="width: 95%;"></div></div>
                            <p style="margin-top: 15px; font-size: 0.9rem; margin-bottom: 0;">SolidWorks, AutoCAD, Fusion 360. Feature trees & technical drawings.</p>
                        </div>
                        
                        <div class="skill-item">
                            <div class="skill-header">
                                <div class="skill-title"><div class="skill-icon"><i class="fas fa-wind"></i></div> CFD Analysis</div>
                                <div class="skill-pct">88%</div>
                            </div>
                            <div class="progress-track"><div class="progress-fill" style="width: 88%;"></div></div>
                            <p style="margin-top: 15px; font-size: 0.9rem; margin-bottom: 0;">Velocity/pressure distributions across fluid flow regimes.</p>
                        </div>
                        
                        <div class="skill-item">
                            <div class="skill-header">
                                <div class="skill-title"><div class="skill-icon"><i class="fas fa-fire-alt"></i></div> Thermodynamics</div>
                                <div class="skill-pct">85%</div>
                            </div>
                            <div class="progress-track"><div class="progress-fill" style="width: 85%;"></div></div>
                            <p style="margin-top: 15px; font-size: 0.9rem; margin-bottom: 0;">Thermal energy storage, sand batteries, and ICE emissions control.</p>
                        </div>
                    </div>

                    <!-- Interactive Gear Calculator Widget -->
                    <div class="calculator-widget reveal-right">
                        <div class="calc-header">
                            <div class="calc-title"><i class="fas fa-cogs"></i> Involute Gear Toolkit</div>
                            <p style="margin-top: 10px; font-size: 0.9rem; margin-bottom: 0;">Interactive tool demonstrating gear mathematics. <strong>Note:</strong> $\Delta d_r$ calculates Pitch Diameter, not root diameter.</p>
                        </div>
                        
                        <div class="calc-form-group">
                            <label class="calc-label">Number of Teeth (N)</label>
                            <input type="number" id="gearTeeth" class="calc-input" value="24" min="10">
                        </div>
                        <div class="calc-form-group">
                            <label class="calc-label">Module / Diametral Pitch (m)</label>
                            <input type="number" id="gearModule" class="calc-input" value="2.5" step="0.1">
                        </div>
                        
                        <div class="calc-result-box">
                            <div class="calc-result-label">Pitch Diameter ($\Delta d_r$)</div>
                            <div class="calc-result-value" id="gearResult">60.00 <span style="font-size: 1rem;">mm</span></div>
                            <div class="calc-note">Formula: $\Delta d_r = N \times m$</div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- ==================================================================
             SECTION 4: PORTFOLIO
             ================================================================== -->
        <section id="portfolio">
            <div class="container">
                <div class="section-header reveal">
                    <div class="badge">Case Studies</div>
                    <h2 class="section-title">Featured <span class="text-gradient">Projects</span></h2>
                </div>

                <div class="portfolio-filters reveal">
                    <button class="filter-btn active" data-filter="all">All Projects</button>
                    <button class="filter-btn" data-filter="thermo">Thermodynamics</button>
                    <button class="filter-btn" data-filter="mech">Mechanical CAD</button>
                    <button class="filter-btn" data-filter="robotics">Robotics</button>
                </div>

                <div class="portfolio-grid" id="portfolioGrid">
                    
                    <!-- Portfolio Item 1: Wheelchair -->
                    <div class="portfolio-card glass-panel reveal port-item mech">
                        <div class="port-img-wrap">
                            <img src="https://images.unsplash.com/photo-1581092335397-9583eb92d232?fit=crop&w=600&h=400" alt="Mahfooz Wheelchair">
                            <div class="port-overlay">
                                <button class="port-view-btn open-modal" data-target="modal-wheelchair"><i class="fas fa-search-plus"></i></button>
                            </div>
                        </div>
                        <div class="port-content">
                            <span class="port-cat">Product Design</span>
                            <h3 class="port-title">Mahfooz Wheelchair</h3>
                            <p class="port-desc">A locally producible mobility device engineered with advanced stair-lifting capabilities. Recognized by Sindh HEC.</p>
                            <div class="port-meta">
                                <div class="port-tool"><i class="fa-solid fa-code"></i> <i class="fas fa-wheelchair"></i></div>
                                <a href="#" class="port-meta-link open-modal" data-target="modal-wheelchair">Full Specs <i class="fas fa-arrow-right"></i></a>
                            </div>
                        </div>
                    </div>

                    <!-- Portfolio Item 2: Sand Battery -->
                    <div class="portfolio-card glass-panel reveal port-item thermo">
                        <div class="port-img-wrap">
                            <img src="https://images.unsplash.com/photo-1497435334941-8c899ee9e8e9?fit=crop&w=600&h=400" alt="Sand Battery">
                            <div class="port-overlay">
                                <button class="port-view-btn open-modal" data-target="modal-battery"><i class="fas fa-search-plus"></i></button>
                            </div>
                        </div>
                        <div class="port-content">
                            <span class="port-cat">Thermodynamics</span>
                            <h3 class="port-title">Thermal Energy Sand Battery</h3>
                            <p class="port-desc">Final year design prototype. Insulated silica sand tank with internal heat exchanger coils and instrumentation sensors.</p>
                            <div class="port-meta">
                                <div class="port-tool"><i class="fas fa-thermometer-half"></i> <i class="fas fa-cogs"></i></div>
                                <a href="#" class="port-meta-link open-modal" data-target="modal-battery">Full Specs <i class="fas fa-arrow-right"></i></a>
                            </div>
                        </div>
                    </div>

                    <!-- Portfolio Item 3: Autonomous Robot -->
                    <div class="portfolio-card glass-panel reveal port-item robotics">
                        <div class="port-img-wrap">
                            <img src="https://images.unsplash.com/photo-1485827404703-89b55fcc595e?fit=crop&w=600&h=400" alt="Robot">
                            <div class="port-overlay">
                                <button class="port-view-btn open-modal" data-target="modal-robot"><i class="fas fa-search-plus"></i></button>
                            </div>
                        </div>
                        <div class="port-content">
                            <span class="port-cat">Mechatronics</span>
                            <h3 class="port-title">Autonomous Line-Follower</h3>
                            <p class="port-desc">Arduino Uno system featuring complex wiring diagrams, sensor loops, and real-time processing code for the Instrumentation Lab.</p>
                            <div class="port-meta">
                                <div class="port-tool"><i class="fa-brands fa-usb"></i> <i class="fas fa-microchip"></i></div>
                                <a href="#" class="port-meta-link open-modal" data-target="modal-robot">Full Specs <i class="fas fa-arrow-right"></i></a>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- ==================================================================
             SECTION 5: INSIGHTS & PUBLICATIONS
             ================================================================== -->
        <section id="insights">
            <div class="container">
                <div class="section-header reveal">
                    <div class="badge">Research & Academia</div>
                    <h2 class="section-title">Engineering <span class="text-gradient">Insights</span></h2>
                </div>

                <div class="insights-grid">
                    <!-- Article 1 -->
                    <div class="article-card reveal-left">
                        <div class="article-date">
                            <span class="date-month">FALL</span>
                            <span class="date-year">2025</span>
                        </div>
                        <div class="article-content">
                            <h3>Emissions in Internal Combustion Engines</h3>
                            <p>A formal engineering document analyzing pollutant formation mechanisms and evaluating modern emission control technologies for industrial IC Engines.</p>
                            <a href="#" class="read-more">Read Abstract <i class="fas fa-arrow-right"></i></a>
                        </div>
                    </div>

                    <!-- Article 2 -->
                    <div class="article-card reveal-right">
                        <div class="article-date">
                            <span class="date-month">JAN</span>
                            <span class="date-year">2026</span>
                        </div>
                        <div class="article-content">
                            <h3>PSX Portfolio Performance Analysis</h3>
                            <p>Executed a transaction log analysis report for Engineering Economics. Transcribed data from Pakistan Stock Exchange to analyze market value fluctuations.</p>
                            <a href="#" class="read-more">Read Abstract <i class="fas fa-arrow-right"></i></a>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- ==================================================================
             SECTION 6: ADVANCED CONTACT MODULE
             ================================================================== -->
        <section id="contact">
            <div class="container">
                <div class="section-header reveal">
                    <div class="badge">Initiate Collaboration</div>
                    <h2 class="section-title">Let's <span class="text-gradient">Connect</span></h2>
                </div>

                <div class="contact-grid">
                    <div class="contact-info reveal-left">
                        <div class="contact-card">
                            <div class="contact-icon"><i class="fas fa-map-marker-alt"></i></div>
                            <div class="contact-details">
                                <h4>Global & Local Hub</h4>
                                <p>Karachi, Sindh, Pakistan.<br>Available globally via remote consulting.</p>
                            </div>
                        </div>
                        <div class="contact-card">
                            <div class="contact-icon"><i class="fas fa-envelope"></i></div>
                            <div class="contact-details">
                                <h4>Direct Communication</h4>
                                <a href="mailto:contact@example.com">consult@3dmechdesign.com</a>
                                <p style="margin-top: 5px;">Response within 24 hours.</p>
                            </div>
                        </div>
                        
                        <!-- Testimonial Inline -->
                        <div class="glass-panel" style="padding: 30px; margin-top: 20px;">
                            <i class="fas fa-quote-left" style="color: var(--brand-primary); font-size: 2rem; margin-bottom: 15px;"></i>
                            <p style="font-style: italic; font-size: 1.05rem;">"Abdur Rafay demonstrates exceptional diligence... his CFD work sets a high standard for engineering students."</p>
                            <div style="font-weight: 700; color: var(--text-primary);">Dr. Usama</div>
                            <div style="font-family: var(--font-mono); font-size: 0.8rem; color: var(--brand-primary);">DHA Suffa University</div>
                        </div>
                    </div>

                    <div class="advanced-form reveal-right">
                        <h3 style="font-size: 1.8rem; margin-bottom: 30px;">Project Inquiry Application</h3>
                        <form id="contactForm">
                            <div class="form-row">
                                <div class="input-group">
                                    <label>First Name</label>
                                    <input type="text" class="form-control" required placeholder="John">
                                </div>
                                <div class="input-group">
                                    <label>Last Name</label>
                                    <input type="text" class="form-control" required placeholder="Doe">
                                </div>
                            </div>
                            
                            <div class="input-group" style="margin-bottom: 25px;">
                                <label>Corporate Email</label>
                                <input type="email" class="form-control" required placeholder="john@engineering.com">
                            </div>

                            <div class="input-group" style="margin-bottom: 25px;">
                                <label>Engineering Discipline Required</label>
                                <select class="form-control">
                                    <option>Parametric CAD Modeling</option>
                                    <option>Computational Fluid Dynamics (CFD)</option>
                                    <option>Gear Mathematical Profiles</option>
                                    <option>Thermodynamics Prototyping</option>
                                </select>
                            </div>
                            
                            <div class="input-group" style="margin-bottom: 25px;">
                                <label>Project Brief</label>
                                <textarea class="form-control" required placeholder="Describe technical specifications, deliverables, and timelines..."></textarea>
                            </div>

                            <label class="custom-checkbox">
                                <input type="checkbox" required>
                                <span class="checkmark"></span>
                                <span class="check-label">I agree to the processing of technical data for consultation purposes.</span>
                            </label>

                            <button type="submit" class="btn btn-primary" style="width: 100%;">
                                Submit Technical Brief <i class="fas fa-paper-plane"></i>
                            </button>
                        </form>
                    </div>
                </div>
            </div>
        </section>
    </main>

    <!-- ==================================================================
         SECTION 7: MEGA FOOTER
         ================================================================== -->
    <footer>
        <div class="container">
            <div class="footer-grid">
                
                <div class="footer-brand">
                    <a href="#" class="logo">
                        <div class="logo-icon"><i class="fas fa-cube"></i></div>
                        3D Mech<span>Design</span>
                    </a>
                    <p>Providing cutting-edge parametric design, thermodynamics prototyping, and computational fluid dynamics analysis for modern engineering solutions worldwide.</p>
                    <div class="social-circle-links" style="margin-top: 25px;">
                        <a href="#"><i class="fab fa-linkedin-in"></i></a>
                        <a href="#"><i class="fab fa-github"></i></a>
                        <a href="#"><i class="fab fa-instagram"></i></a>
                    </div>
                </div>
                
                <div class="footer-col">
                    <h4 class="footer-title">Disciplines</h4>
                    <ul class="footer-links">
                        <li><a href="#"><i class="fas fa-chevron-right"></i> CAD Consulting</a></li>
                        <li><a href="#"><i class="fas fa-chevron-right"></i> Thermal Simulation</a></li>
                        <li><a href="#"><i class="fas fa-chevron-right"></i> Gear Analysis</a></li>
                        <li><a href="#"><i class="fas fa-chevron-right"></i> Prototyping</a></li>
                    </ul>
                </div>

                <div class="footer-col">
                    <h4 class="footer-title">Navigation</h4>
                    <ul class="footer-links">
                        <li><a href="#hero"><i class="fas fa-chevron-right"></i> Home Base</a></li>
                        <li><a href="#about"><i class="fas fa-chevron-right"></i> Professional Profile</a></li>
                        <li><a href="#portfolio"><i class="fas fa-chevron-right"></i> Case Studies</a></li>
                        <li><a href="#contact"><i class="fas fa-chevron-right"></i> Contact Protocol</a></li>
                    </ul>
                </div>

                <div class="footer-col">
                    <h4 class="footer-title">Academic Affiliation</h4>
                    <p style="color: var(--text-muted); line-height: 1.8;">
                        B.E. Mechanical Engineering<br>
                        <strong>DHA Suffa University</strong><br>
                        Project Collaborators: Ayaan Amir<br>
                        Mentors: Dr. Usama
                    </p>
                </div>

            </div>
            
            <div class="footer-bottom">
                <p>&copy; 2026 Abdur Rafay Yousuf. Engineering Portfolio. All Rights Reserved.</p>
                <p>System Time: PKT 09:05</p>
            </div>
        </div>
    </footer>

    <!-- ==================================================================
         MODALS (HIDDEN BY DEFAULT)
         ================================================================== -->
    
    <!-- Modal: Mahfooz Wheelchair -->
    <div class="modal" id="modal-wheelchair">
        <div class="modal-content">
            <button class="modal-close"><i class="fas fa-times"></i></button>
            <div class="modal-header">
                <div class="badge" style="margin-bottom: 15px;">Product Engineering</div>
                <h2 class="modal-title">Mahfooz Wheelchair Project</h2>
            </div>
            <div class="modal-body">
                <img src="https://images.unsplash.com/photo-1581092335397-9583eb92d232?fit=crop&w=800&h=400" alt="Wheelchair CAD">
                <p><strong>Inspiration & Overview:</strong> Motivated by severe family mobility limitations, this project aimed to develop a highly localized, cost-effective mobility device equipped with functional stair-lifting mechanisms.</p>
                <p><strong>Engineering Process:</strong> Conducted extensive user surveys to determine ergonomic parameters. The mechanical chassis was developed using parametric modeling in SolidWorks, followed by finite element analysis (FEA) on critical load-bearing joints.</p>
                
                <table class="spec-table">
                    <tr>
                        <td>Recognition</td>
                        <td>Sindh Higher Education Commission (Startup)</td>
                    </tr>
                    <tr>
                        <td>Timeline</td>
                        <td>2025 - 2026</td>
                    </tr>
                    <tr>
                        <td>Software Used</td>
                        <td>SolidWorks, Ansys</td>
                    </tr>
                </table>
            </div>
        </div>
    </div>

    <!-- Modal: Sand Battery -->
    <div class="modal" id="modal-battery">
        <div class="modal-content">
            <button class="modal-close"><i class="fas fa-times"></i></button>
            <div class="modal-header">
                <div class="badge" style="margin-bottom: 15px;">Thermodynamics</div>
                <h2 class="modal-title">Thermal Energy Sand Battery</h2>
            </div>
            <div class="modal-body">
                <img src="https://images.unsplash.com/photo-1497435334941-8c899ee9e8e9?fit=crop&w=800&h=400" alt="Sand Battery Spec">
                <p><strong>Overview:</strong> A final year design project exploring high-capacity thermal energy storage for industrial applications utilizing silica sand media.</p>
                
                <table class="spec-table">
                    <tr>
                        <td>Storage Medium</td>
                        <td>High-retention Silica Sand</td>
                    </tr>
                    <tr>
                        <td>Physical Layout</td>
                        <td>Insulated tank, Internal Heat Exchanger Coils</td>
                    </tr>
                    <tr>
                        <td>Data Tracking</td>
                        <td>Instrumentation Sensors</td>
                    </tr>
                </table>
            </div>
        </div>
    </div>

    <!-- Modal: Robot -->
    <div class="modal" id="modal-robot">
        <div class="modal-content">
            <button class="modal-close"><i class="fas fa-times"></i></button>
            <div class="modal-header">
                <div class="badge" style="margin-bottom: 15px;">Mechatronics</div>
                <h2 class="modal-title">Autonomous Line-Following Robot</h2>
            </div>
            <div class="modal-body">
                <img src="https://images.unsplash.com/photo-1485827404703-89b55fcc595e?fit=crop&w=800&h=400" alt="Robot Internals">
                <p><strong>Overview:</strong> A Measurement & Instrumentation Lab project executed in November 2025.</p>
                
                <table class="spec-table">
                    <tr>
                        <td>Core Processor</td>
                        <td>Arduino Uno</td>
                    </tr>
                    <tr>
                        <td>Documentation</td>
                        <td>Technical report, Wiring Diagrams</td>
                    </tr>
                    <tr>
                        <td>Software Logic</td>
                        <td>Real-time C++ processing code</td>
                    </tr>
                </table>
            </div>
        </div>
    </div>

    <!-- ==================================================================
         JAVASCRIPT ENGINE
         ================================================================== -->
    <script>
        document.addEventListener("DOMContentLoaded", () => {
            
            /* --- 1. PRELOADER & INITIALIZATION --- */
            const preloader = document.getElementById('preloader');
            setTimeout(() => {
                preloader.classList.add('hidden');
                setTimeout(() => preloader.style.display = 'none', 800);
            }, 1200);

            /* --- 2. THEME MANAGER --- */
            const themeToggle = document.getElementById("theme-toggle");
            const savedTheme = localStorage.getItem("portfolio_theme");
            
            if (savedTheme) {
                document.documentElement.setAttribute("data-theme", savedTheme);
                themeToggle.innerHTML = savedTheme === "dark" ? '<i class="fas fa-sun"></i>' : '<i class="fas fa-moon"></i>';
            }
            
            themeToggle.addEventListener('click', () => {
                const isDark = document.documentElement.getAttribute("data-theme") === "dark";
                document.documentElement.setAttribute("data-theme", isDark ? "light" : "dark");
                localStorage.setItem("portfolio_theme", isDark ? "light" : "dark");
                themeToggle.innerHTML = isDark ? '<i class="fas fa-moon"></i>' : '<i class="fas fa-sun"></i>';
                initParticles(); // Re-render particles with new theme colors
            });

            /* --- 3. DYNAMIC TYPEWRITER EFFECT --- */
            const typeText = document.getElementById("typewriter");
            if(typeText) {
                const words = ["Parametric Design.", "CFD Simulation.", "Thermodynamics.", "Gear Mathematics."];
                let wordIndex = 0;
                let charIndex = 0;
                let isDeleting = false;
                
                function type() {
                    const currentWord = words[wordIndex];
                    if(isDeleting) {
                        typeText.textContent = currentWord.substring(0, charIndex - 1);
                        charIndex--;
                    } else {
                        typeText.textContent = currentWord.substring(0, charIndex + 1);
                        charIndex++;
                    }
                    
                    let speed = isDeleting ? 50 : 100;
                    
                    if(!isDeleting && charIndex === currentWord.length) {
                        speed = 2000; // Pause at end of word
                        isDeleting = true;
                    } else if (isDeleting && charIndex === 0) {
                        isDeleting = false;
                        wordIndex = (wordIndex + 1) % words.length;
                        speed = 500; // Pause before new word
                    }
                    setTimeout(type, speed);
                }
                setTimeout(type, 1500);
            }

            /* --- 4. NAVBAR SCROLL & MOBILE MENU --- */
            const header = document.getElementById('header');
            const mobileToggle = document.querySelector('.mobile-toggle');
            const navLinks = document.querySelector('.nav-links');
            const navItems = document.querySelectorAll('.nav-link');
            const sections = document.querySelectorAll('section');

            window.addEventListener('scroll', () => {
                // Header minimize
                if(window.scrollY > 50) header.classList.add('scrolled');
                else header.classList.remove('scrolled');

                // Scroll Spy for Nav links
                let current = '';
                sections.forEach(section => {
                    const sectionTop = section.offsetTop;
                    if(pageYOffset >= sectionTop - 200) {
                        current = section.getAttribute('id');
                    }
                });

                navItems.forEach(li => {
                    li.classList.remove('active');
                    if(li.getAttribute('href') === `#${current}`) {
                        li.classList.add('active');
                    }
                });
            });

            mobileToggle.addEventListener('click', () => {
                navLinks.classList.toggle('nav-active');
                const i = mobileToggle.querySelector('i');
                i.classList.toggle('fa-bars');
                i.classList.toggle('fa-times');
            });

            /* --- 5. TABS LOGIC (About Section) --- */
            const tabBtns = document.querySelectorAll('.tab-btn');
            const tabPanes = document.querySelectorAll('.tab-pane');
            
            tabBtns.forEach(btn => {
                btn.addEventListener('click', () => {
                    const target = btn.getAttribute('data-tab');
                    
                    // Reset all
                    tabBtns.forEach(b => b.classList.remove('active'));
                    tabPanes.forEach(p => p.classList.remove('active'));
                    
                    // Activate clicked
                    btn.classList.add('active');
                    document.getElementById(`tab-${target}`).classList.add('active');
                });
            });

            /* --- 6. GEAR CALCULATOR WIDGET LOGIC --- */
            const gearTeethInput = document.getElementById('gearTeeth');
            const gearModuleInput = document.getElementById('gearModule');
            const gearResultDisplay = document.getElementById('gearResult');

            function calculatePitchDiameter() {
                const N = parseFloat(gearTeethInput.value) || 0;
                const m = parseFloat(gearModuleInput.value) || 0;
                // Formula: Pitch Diameter (delta dr) = N * m
                const pitchDiameter = (N * m).toFixed(2);
                gearResultDisplay.innerHTML = `${pitchDiameter} <span style="font-size: 1rem;">mm</span>`;
            }

            if(gearTeethInput && gearModuleInput) {
                gearTeethInput.addEventListener('input', calculatePitchDiameter);
                gearModuleInput.addEventListener('input', calculatePitchDiameter);
            }

            /* --- 7. PORTFOLIO FILTERING --- */
            const filterBtns = document.querySelectorAll('.portfolio-filters .filter-btn');
            const portItems = document.querySelectorAll('.port-item');

            filterBtns.forEach(btn => {
                btn.addEventListener('click', () => {
                    filterBtns.forEach(b => b.classList.remove('active'));
                    btn.classList.add('active');
                    
                    const filter = btn.getAttribute('data-filter');
                    
                    portItems.forEach(item => {
                        item.style.transition = "transform 0.4s ease, opacity 0.4s ease";
                        item.style.opacity = '0';
                        item.style.transform = 'scale(0.9)';
                        
                        setTimeout(() => {
                            if(filter === 'all' || item.classList.contains(filter)) {
                                item.style.display = 'flex';
                                setTimeout(() => {
                                    item.style.opacity = '1';
                                    item.style.transform = 'scale(1)';
                                }, 50);
                            } else {
                                item.style.display = 'none';
                            }
                        }, 400);
                    });
                });
            });

            /* --- 8. MODAL MANAGER --- */
            const modalTriggers = document.querySelectorAll('.open-modal');
            const modals = document.querySelectorAll('.modal');
            const closeBtns = document.querySelectorAll('.modal-close');

            modalTriggers.forEach(trigger => {
                trigger.addEventListener('click', (e) => {
                    e.preventDefault();
                    const targetId = trigger.getAttribute('data-target');
                    if(targetId) document.getElementById(targetId).classList.add('active');
                });
            });

            closeBtns.forEach(btn => {
                btn.addEventListener('click', () => {
                    modals.forEach(m => m.classList.remove('active'));
                });
            });

            window.addEventListener('click', (e) => {
                modals.forEach(m => {
                    if(e.target === m) m.classList.remove('active');
                });
            });

            /* --- 9. METRICS COUNTER ANIMATION --- */
            const metrics = document.querySelectorAll('.metric-value[data-target]');
            let counted = false;

            const runCounters = () => {
                metrics.forEach(metric => {
                    const target = +metric.getAttribute('data-target');
                    const count = +metric.innerText;
                    const inc = target / 100; // Speed control

                    if(count < target) {
                        metric.innerText = Math.ceil(count + inc);
                        setTimeout(runCounters, 20);
                    } else {
                        metric.innerText = target + "+";
                    }
                });
            }

            /* --- 10. SCROLL REVEAL OBSERVER --- */
            const revealElements = document.querySelectorAll('.reveal, .reveal-left, .reveal-right');
            const observerOptions = { root: null, rootMargin: '0px', threshold: 0.15 };

            const observer = new IntersectionObserver((entries, observer) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.classList.add('active');
                        // Trigger counters if hero metrics are visible
                        if(entry.target.classList.contains('hero-metrics') && !counted) {
                            runCounters();
                            counted = true;
                        }
                        observer.unobserve(entry.target);
                    }
                });
            }, observerOptions);

            revealElements.forEach(el => observer.observe(el));

            /* --- 11. FORM SUBMISSION MOCK --- */
            const form = document.getElementById('contactForm');
            if(form) {
                form.addEventListener('submit', (e) => {
                    e.preventDefault();
                    const btn = form.querySelector('button[type="submit"]');
                    const originalText = btn.innerHTML;
                    btn.innerHTML = '<i class="fas fa-circle-notch fa-spin"></i> Processing...';
                    
                    setTimeout(() => {
                        btn.innerHTML = '<i class="fas fa-check"></i> Brief Submitted Successfully';
                        btn.style.background = "var(--brand-success)";
                        btn.style.borderColor = "var(--brand-success)";
                        form.reset();
                        
                        setTimeout(() => {
                            btn.innerHTML = originalText;
                            btn.style.background = "";
                            btn.style.borderColor = "";
                        }, 4000);
                    }, 2000);
                });
            }

            /* --- 12. ADVANCED CANVAS PARTICLE ENGINE (CFD SIM) --- */
            const canvas = document.getElementById('particle-canvas');
            const ctx = canvas.getContext('2d');
            let particlesArray = [];
            
            // Mouse tracking for repulsion effect
            let mouse = { x: null, y: null, radius: 150 };
            
            window.addEventListener('mousemove', (event) => {
                mouse.x = event.x;
                mouse.y = event.y;
            });
            window.addEventListener('mouseout', () => {
                mouse.x = undefined;
                mouse.y = undefined;
            });

            function resizeCanvas() {
                canvas.width = window.innerWidth;
                canvas.height = window.innerHeight;
                initParticles();
            }
            window.addEventListener('resize', resizeCanvas);
            canvas.width = window.innerWidth;
            canvas.height = window.innerHeight;

            class Particle {
                constructor(x, y, directionX, directionY, size, color) {
                    this.x = x;
                    this.y = y;
                    this.baseX = x;
                    this.baseY = y;
                    this.directionX = directionX;
                    this.directionY = directionY;
                    this.size = size;
                    this.color = color;
                    this.density = (Math.random() * 30) + 1;
                }
                
                draw() {
                    ctx.beginPath();
                    ctx.arc(this.x, this.y, this.size, 0, Math.PI * 2, false);
                    ctx.fillStyle = this.color;
                    ctx.fill();
                }
                
                update() {
                    // Collision with borders
                    if (this.x > canvas.width || this.x < 0) this.directionX = -this.directionX;
                    if (this.y > canvas.height || this.y < 0) this.directionY = -this.directionY;
                    
                    // Mouse repulsion physics (Fluid Dynamics feel)
                    let dx = mouse.x - this.x;
                    let dy = mouse.y - this.y;
                    let distance = Math.sqrt(dx * dx + dy * dy);
                    
                    if(distance < mouse.radius) {
                        const forceDirectionX = dx / distance;
                        const forceDirectionY = dy / distance;
                        const force = (mouse.radius - distance) / mouse.radius;
                        const directionX = (forceDirectionX * force * this.density);
                        const directionY = (forceDirectionY * force * this.density);
                        
                        this.x -= directionX;
                        this.y -= directionY;
                    } else {
                        // Slowly return to base direction if untouched
                        if (this.x !== this.baseX) {
                            let dx = this.x - this.baseX;
                            this.x -= dx / 100;
                        }
                        if (this.y !== this.baseY) {
                            let dy = this.y - this.baseY;
                            this.y -= dy / 100;
                        }
                    }
                    
                    // Base movement
                    this.x += this.directionX;
                    this.y += this.directionY;
                    this.draw();
                }
            }

            function initParticles() {
                particlesArray = [];
                const isDark = document.documentElement.getAttribute("data-theme") === "dark";
                const pColor = isDark ? 'rgba(96, 165, 250, 0.4)' : 'rgba(37, 99, 235, 0.2)';
                
                // Scale number of particles based on screen size for performance
                const numberOfParticles = (canvas.height * canvas.width) / 10000;
                
                for (let i = 0; i < numberOfParticles; i++) {
                    let size = (Math.random() * 2) + 1;
                    let x = (Math.random() * ((innerWidth - size * 2) - (size * 2)) + size * 2);
                    let y = (Math.random() * ((innerHeight - size * 2) - (size * 2)) + size * 2);
                    let directionX = (Math.random() * 1.5) - 0.75;
                    let directionY = (Math.random() * 1.5) - 0.75;
                    
                    particlesArray.push(new Particle(x, y, directionX, directionY, size, pColor));
                }
            }

            function animateParticles() {
                requestAnimationFrame(animateParticles);
                ctx.clearRect(0, 0, innerWidth, innerHeight);
                
                for (let i = 0; i < particlesArray.length; i++) {
                    particlesArray[i].update();
                }
                connectParticles();
            }

            function connectParticles() {
                let opacityValue = 1;
                for (let a = 0; a < particlesArray.length; a++) {
                    for (let b = a; b < particlesArray.length; b++) {
                        let distance = ((particlesArray[a].x - particlesArray[b].x) * (particlesArray[a].x - particlesArray[b].x))
                                     + ((particlesArray[a].y - particlesArray[b].y) * (particlesArray[a].y - particlesArray[b].y));
                                     
                        if (distance < (canvas.width / 12) * (canvas.height / 12)) {
                            const isDark = document.documentElement.getAttribute("data-theme") === "dark";
                            opacityValue = 1 - (distance / 20000);
                            ctx.strokeStyle = isDark ? `rgba(96, 165, 250, ${opacityValue * 0.15})` : `rgba(37, 99, 235, ${opacityValue * 0.15})`;
                            ctx.lineWidth = 1;
                            ctx.beginPath();
                            ctx.moveTo(particlesArray[a].x, particlesArray[a].y);
                            ctx.lineTo(particlesArray[b].x, particlesArray[b].y);
                            ctx.stroke();
                        }
                    }
                }
            }

            initParticles();
            animateParticles();

        });
    </script>
</body>
</html>
