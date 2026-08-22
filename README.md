<!DOCTYPE html>
<html lang="en" data-theme="dark">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>3D Mech Design - Engineering Excellence</title>
    
    <!-- ======================================================================
         EXTERNAL ASSETS & FONTS
         ====================================================================== -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <!-- Plus Jakarta Sans for UI, JetBrains Mono for Technical Data -->
    <link
        href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@300;400;500;600;700;800&family=Plus+Jakarta+Sans:wght@300;400;500;600;700;800&display=swap"
        rel="stylesheet">

    <!-- ======================================================================
         MASTER CSS STYLESHEET
         ====================================================================== -->
    <style>
        /* --------------------------------------------------------------------
           01. CSS RESET & CUSTOM PROPERTIES
           -------------------------------------------------------------------- */
        *,
        *::before,
        *::after {
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

            --shadow-sm: 0 2px 4px rgba(0, 0, 0, 0.02);
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
            --bg-base: #05050c;
            --bg-gradient-1: #0a0a1a;
            --bg-gradient-2: #020208;
            --bg-surface: #0c0c1e;
            --text-primary: #f0f4ff;
            --text-secondary: #aab4d4;
            --text-muted: #6a7a9e;
            --text-inverse: #0f172a;
            --brand-primary: #00b4ff;
            --brand-primary-hover: #66d0ff;
            --brand-primary-light: rgba(0, 180, 255, 0.12);
            --brand-accent: #7c5cfc;
            --brand-success: #10b981;
            --glass-bg: rgba(10, 10, 30, 0.55);
            --glass-border: rgba(0, 180, 255, 0.08);
            --glass-highlight: rgba(0, 180, 255, 0.06);
            --grid-line: rgba(0, 180, 255, 0.06);
            --particle-color: rgba(0, 180, 255, 0.25);
            --shadow-md: 0 10px 40px rgba(0, 0, 0, 0.6);
            --shadow-lg: 0 20px 60px rgba(0, 100, 255, 0.1);
            --shadow-glow: 0 0 80px rgba(0, 150, 255, 0.10);
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

        ::-webkit-scrollbar {
            width: 10px;
        }

        ::-webkit-scrollbar-track {
            background: var(--bg-base);
        }

        ::-webkit-scrollbar-thumb {
            background: var(--glass-border);
            border-radius: 10px;
            border: 2px solid var(--bg-base);
        }

        ::-webkit-scrollbar-thumb:hover {
            background: var(--brand-primary);
        }

        h1,
        h2,
        h3,
        h4,
        h5,
        h6 {
            font-weight: 800;
            line-height: 1.2;
            color: var(--text-primary);
            letter-spacing: -0.02em;
        }

        p {
            margin-bottom: 1.25rem;
            color: var(--text-secondary);
        }

        a {
            color: var(--brand-primary);
            text-decoration: none;
            transition: var(--transition-fast);
        }

        strong {
            font-weight: 700;
            color: var(--text-primary);
        }

        .text-gradient {
            background: linear-gradient(135deg, var(--brand-primary), var(--brand-accent), var(--brand-primary));
            background-size: 200% auto;
            color: transparent;
            -webkit-background-clip: text;
            background-clip: text;
            animation: gradientText 5s linear infinite;
        }

        .mono {
            font-family: var(--font-mono);
        }

        /* --------------------------------------------------------------------
           03. ADVANCED BACKGROUND ENGINE
           -------------------------------------------------------------------- */
        .bg-engine {
            position: fixed;
            inset: 0;
            z-index: var(--z-negative);
            pointer-events: none;
            overflow: hidden;
            background: var(--bg-base);
        }

        .bg-orb {
            position: absolute;
            top: 10%;
            left: 50%;
            transform: translateX(-50%);
            width: 600px;
            height: 600px;
            background: radial-gradient(circle, rgba(0, 180, 255, 0.08) 0%, transparent 70%);
            border-radius: 50%;
            filter: blur(80px);
            animation: pulseOrb 6s ease-in-out infinite alternate;
        }

        @keyframes pulseOrb {
            0% { transform: translateX(-50%) scale(0.9); opacity: 0.6; }
            100% { transform: translateX(-50%) scale(1.2); opacity: 1; }
        }

        .bg-mesh {
            position: absolute;
            inset: 0;
            background:
                radial-gradient(ellipse at 50% 30%, rgba(0, 180, 255, 0.12) 0%, transparent 60%),
                radial-gradient(ellipse at 80% 80%, rgba(124, 92, 252, 0.06) 0%, transparent 50%),
                radial-gradient(ellipse at 20% 70%, rgba(0, 180, 255, 0.04) 0%, transparent 40%);
            filter: blur(60px);
            animation: breatheGlow 8s ease-in-out infinite alternate;
        }

        @keyframes breatheGlow {
            0% { transform: scale(1) translateY(0); opacity: 0.8; }
            100% { transform: scale(1.1) translateY(-20px); opacity: 1; }
        }

        .bg-grid {
            position: absolute;
            inset: 0;
            background-image:
                linear-gradient(var(--grid-line) 1px, transparent 1px),
                linear-gradient(90deg, var(--grid-line) 1px, transparent 1px);
            background-size: 60px 60px;
            mask-image: radial-gradient(ellipse 70% 70% at 50% 50%, black 30%, transparent 80%);
            -webkit-mask-image: radial-gradient(ellipse 70% 70% at 50% 50%, black 30%, transparent 80%);
            opacity: 0.6;
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
            position: fixed;
            inset: 0;
            background: var(--bg-base);
            z-index: 99999;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            transition: opacity 0.8s ease, visibility 0.8s;
        }

        .preloader.hidden {
            opacity: 0;
            visibility: hidden;
        }

        .gear-loader {
            width: 80px;
            height: 80px;
            border: 6px dashed var(--brand-primary);
            border-radius: 50%;
            animation: spinGear 4s linear infinite;
            margin-bottom: 20px;
            position: relative;
        }

        .gear-loader::before {
            content: '';
            position: absolute;
            inset: 10px;
            border: 4px solid var(--brand-accent);
            border-radius: 50%;
            animation: spinGear 2s linear infinite reverse;
        }

        .loading-text {
            font-family: var(--font-mono);
            font-size: 14px;
            color: var(--brand-primary);
            letter-spacing: 4px;
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
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 1px;
            background: linear-gradient(90deg, transparent, var(--glass-highlight), transparent);
        }

        .btn {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
            padding: 14px 28px;
            border-radius: var(--radius-md);
            font-family: var(--font-sans);
            font-weight: 600;
            font-size: 1rem;
            cursor: pointer;
            transition: var(--transition-normal);
            border: 1px solid transparent;
            text-decoration: none;
            position: relative;
            overflow: hidden;
            z-index: 1;
        }

        .btn-primary {
            background: linear-gradient(135deg, var(--brand-primary), var(--brand-accent));
            color: #ffffff !important;
            box-shadow: 0 4px 15px rgba(37, 99, 235, 0.3);
            border: 1px solid rgba(255, 255, 255, 0.1);
        }

        .btn-primary::before {
            content: '';
            position: absolute;
            inset: 0;
            background: linear-gradient(135deg, var(--brand-accent), var(--brand-primary));
            opacity: 0;
            transition: var(--transition-normal);
            z-index: -1;
        }

        .btn-primary:hover::before {
            opacity: 1;
        }

        .btn-primary:hover {
            transform: translateY(-3px) scale(1.02);
            box-shadow: var(--shadow-lg);
        }

        .btn-secondary {
            background: var(--glass-bg);
            color: var(--text-primary);
            border-color: var(--glass-border);
            backdrop-filter: blur(10px);
        }

        .btn-secondary:hover {
            border-color: var(--brand-primary);
            color: var(--brand-primary);
            background: var(--brand-primary-light);
            transform: translateY(-3px);
        }

        .btn-icon {
            width: 45px;
            height: 45px;
            padding: 0;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            background: var(--glass-bg);
            border: 1px solid var(--glass-border);
            color: var(--text-primary);
            font-size: 1.2rem;
            transition: var(--transition-normal);
            backdrop-filter: blur(10px);
            cursor: pointer;
        }

        .btn-icon:hover {
            background: var(--brand-primary);
            color: white;
            border-color: var(--brand-primary);
            transform: translateY(-3px) rotate(10deg);
        }

        .badge {
            display: inline-flex;
            align-items: center;
            gap: 8px;
            padding: 8px 16px;
            border-radius: var(--radius-full);
            font-family: var(--font-mono);
            font-size: 0.8rem;
            font-weight: 600;
            background: var(--brand-primary-light);
            color: var(--brand-primary);
            border: 1px solid rgba(37, 99, 235, 0.2);
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        /* --------------------------------------------------------------------
           06. LAYOUT & NAVIGATION
           -------------------------------------------------------------------- */
        .container {
            width: 100%;
            max-width: 1400px;
            margin: 0 auto;
            padding: 0 5%;
            position: relative;
        }

        section {
            padding: 120px 0;
            position: relative;
        }

        .section-header {
            text-align: center;
            max-width: 800px;
            margin: 0 auto 60px auto;
        }

        .section-header .badge {
            margin-bottom: 20px;
        }

        .section-title {
            font-size: 3.5rem;
            margin-bottom: 20px;
        }

        .section-desc {
            font-size: 1.15rem;
            color: var(--text-muted);
        }

        header {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 90px;
            display: flex;
            align-items: center;
            z-index: var(--z-sticky);
            transition: var(--transition-normal);
            border-bottom: 1px solid transparent;
        }

        header.scrolled {
            height: 75px;
            background: var(--glass-bg);
            backdrop-filter: blur(24px);
            border-bottom: 1px solid var(--glass-border);
            box-shadow: var(--shadow-sm);
        }

        .nav-wrapper {
            display: flex;
            justify-content: space-between;
            align-items: center;
            width: 100%;
        }

        .logo {
            font-family: var(--font-mono);
            font-size: 1.5rem;
            font-weight: 800;
            color: var(--text-primary);
            text-decoration: none;
            display: flex;
            align-items: center;
            gap: 12px;
        }

        .logo-icon {
            width: 40px;
            height: 40px;
            background: var(--brand-primary);
            color: white;
            border-radius: var(--radius-sm);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.2rem;
            transform: rotate(45deg);
            transition: var(--transition-normal);
        }

        .logo-icon i {
            transform: rotate(-45deg);
        }

        .logo:hover .logo-icon {
            transform: rotate(135deg);
            border-radius: 50%;
        }

        .nav-links {
            display: flex;
            gap: 2.5rem;
            list-style: none;
            margin: 0;
            padding: 0;
        }

        .nav-link {
            font-size: 0.95rem;
            font-weight: 600;
            color: var(--text-secondary);
            text-decoration: none;
            transition: var(--transition-fast);
            position: relative;
        }

        .nav-link::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--brand-primary);
            transition: var(--transition-normal);
        }

        .nav-link:hover,
        .nav-link.active {
            color: var(--brand-primary);
        }

        .nav-link:hover::after,
        .nav-link.active::after {
            width: 100%;
        }

        .nav-actions {
            display: flex;
            align-items: center;
            gap: 15px;
        }

        .mobile-toggle {
            display: none;
            font-size: 1.5rem;
            color: var(--text-primary);
            background: none;
            border: none;
            cursor: pointer;
        }

        /* --------------------------------------------------------------------
           07. INFINITE SCROLL MARQUEE (Tech Stack)
           -------------------------------------------------------------------- */
        .marquee-wrapper {
            width: 100%;
            overflow: hidden;
            padding: 40px 0;
            background: var(--bg-surface);
            border-top: 1px solid var(--glass-border);
            border-bottom: 1px solid var(--glass-border);
            position: relative;
        }

        .marquee-wrapper::before,
        .marquee-wrapper::after {
            content: "";
            position: absolute;
            top: 0;
            width: 250px;
            height: 100%;
            z-index: 2;
        }

        .marquee-wrapper::before {
            left: 0;
            background: linear-gradient(to right, var(--bg-surface), transparent);
        }

        .marquee-wrapper::after {
            right: 0;
            background: linear-gradient(to left, var(--bg-surface), transparent);
        }

        .marquee-content {
            display: flex;
            width: max-content;
            animation: marquee 30s linear infinite;
        }

        .marquee-item {
            display: flex;
            align-items: center;
            gap: 15px;
            padding: 0 40px;
            font-family: var(--font-mono);
            font-weight: 700;
            font-size: 1.5rem;
            color: var(--text-muted);
            opacity: 0.6;
            transition: var(--transition-fast);
        }

        .marquee-item:hover {
            color: var(--brand-primary);
            opacity: 1;
            transform: scale(1.1);
        }

        .marquee-item i {
            font-size: 2rem;
        }

        @keyframes marquee {
            0% {
                transform: translateX(0);
            }

            100% {
                transform: translateX(-50%);
            }
        }

        /* --------------------------------------------------------------------
           08. HERO SECTION
           -------------------------------------------------------------------- */
        #hero {
            min-height: 100vh;
            display: flex;
            align-items: center;
            padding-top: 120px;
            padding-bottom: 60px;
        }

        .hero-grid {
            display: grid;
            grid-template-columns: 1.2fr 0.8fr;
            gap: 4rem;
            align-items: center;
        }

        .hero-content .badge {
            margin-bottom: 30px;
            animation: slideDown 1s ease forwards;
            opacity: 0;
        }

        .hero-title {
            font-size: clamp(3rem, 5vw, 5rem);
            line-height: 1.1;
            margin-bottom: 25px;
            opacity: 0;
            animation: slideUp 1s ease 0.2s forwards;
        }

        /* Typewriter specific styling */
        .typewriter-wrapper {
            height: 1.2em;
            display: block;
            overflow: hidden;
        }

        .typewriter-text {
            color: var(--brand-primary);
            border-right: 4px solid var(--brand-primary);
            white-space: nowrap;
            animation: blink-caret 0.75s step-end infinite;
        }

        .hero-desc {
            font-size: 1.25rem;
            color: var(--text-muted);
            max-width: 650px;
            margin-bottom: 40px;
            opacity: 0;
            animation: slideUp 1s ease 0.4s forwards;
        }

        .hero-metrics {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 20px;
            margin-bottom: 40px;
            padding-top: 30px;
            border-top: 1px dashed var(--glass-border);
            opacity: 0;
            animation: slideUp 1s ease 0.6s forwards;
        }

        .metric {
            display: flex;
            flex-direction: column;
            gap: 5px;
        }

        .metric-value {
            font-family: var(--font-mono);
            font-size: 2.5rem;
            font-weight: 800;
            color: var(--text-primary);
        }

        .metric-label {
            font-size: 0.9rem;
            color: var(--text-muted);
            font-weight: 600;
            text-transform: uppercase;
        }

        .hero-btns {
            display: flex;
            gap: 20px;
            opacity: 0;
            animation: slideUp 1s ease 0.8s forwards;
        }

        /* 3D Visual Profile */
        .hero-visual {
            position: relative;
            opacity: 0;
            animation: fadeIn 1.5s ease 1s forwards;
            perspective: 1000px;
        }

        .profile-card {
            padding: 50px;
            text-align: center;
            z-index: 2;
            transform-style: preserve-3d;
            transition: transform 0.1s ease;
        }

        .profile-img-wrap {
            width: 300px;
            height: 300px;
            margin: 0 auto 30px auto;
            border-radius: 50%;
            padding: 10px;
            background: linear-gradient(135deg, var(--brand-primary), var(--brand-accent));
            position: relative;
            transform: translateZ(30px);
        }

        .profile-img-wrap::before {
            content: '';
            position: absolute;
            inset: -20px;
            background: radial-gradient(circle, var(--brand-primary) 0%, transparent 70%);
            opacity: 0.4;
            filter: blur(40px);
            animation: pulseGlow 4s infinite alternate;
            z-index: -1;
        }

        .profile-img {
            width: 100%;
            height: 100%;
            border-radius: 50%;
            object-fit: cover;
            border: 4px solid var(--bg-surface);
        }

        .profile-card h3 {
            font-size: 2rem;
            margin-bottom: 5px;
            transform: translateZ(20px);
        }

        .profile-card p {
            font-family: var(--font-mono);
            color: var(--brand-primary);
            margin-bottom: 20px;
            font-weight: 600;
            transform: translateZ(15px);
        }

        .float-badge {
            position: absolute;
            background: var(--glass-bg);
            backdrop-filter: blur(10px);
            border: 1px solid var(--glass-border);
            padding: 15px 25px;
            border-radius: var(--radius-md);
            display: flex;
            align-items: center;
            gap: 15px;
            box-shadow: var(--shadow-md);
            z-index: 3;
            animation: float 6s ease-in-out infinite;
            transform: translateZ(40px);
        }

        .float-1 {
            top: 5%;
            right: -30px;
            animation-delay: 0s;
        }

        .float-2 {
            bottom: 15%;
            left: -40px;
            animation-delay: 2s;
        }

        .float-icon {
            width: 45px;
            height: 45px;
            border-radius: 50%;
            background: var(--brand-primary-light);
            color: var(--brand-primary);
            display: flex;
            justify-content: center;
            align-items: center;
            font-size: 1.3rem;
        }

        .float-text {
            font-weight: 700;
            font-size: 1rem;
            display: flex;
            flex-direction: column;
        }

        .float-text span {
            font-size: 0.75rem;
            color: var(--text-muted);
            font-weight: 500;
        }

        /* --------------------------------------------------------------------
           09. ABOUT & TABBED INTERFACE
           -------------------------------------------------------------------- */
        .about-grid {
            display: grid;
            grid-template-columns: 1fr 1.2fr;
            gap: 5rem;
            align-items: start;
        }

        .about-visual {
            position: relative;
        }

        .about-image {
            width: 100%;
            border-radius: var(--radius-lg);
            border: 1px solid var(--glass-border);
            box-shadow: var(--shadow-lg);
        }

        .location-badge {
            position: absolute;
            bottom: -20px;
            left: -20px;
            background: var(--bg-surface);
            padding: 20px 30px;
            border-radius: var(--radius-lg);
            border: 1px solid var(--glass-border);
            box-shadow: var(--shadow-md);
            display: flex;
            align-items: center;
            gap: 15px;
        }

        .location-badge i {
            font-size: 2rem;
            color: var(--brand-primary);
        }

        /* Custom Tabs System */
        .tabs-header {
            display: flex;
            gap: 15px;
            margin-bottom: 30px;
            border-bottom: 2px solid var(--glass-border);
            padding-bottom: 10px;
        }

        .tab-btn {
            background: none;
            border: none;
            font-family: var(--font-sans);
            font-size: 1.1rem;
            font-weight: 700;
            color: var(--text-muted);
            cursor: pointer;
            padding: 10px 20px;
            position: relative;
            transition: var(--transition-fast);
        }

        .tab-btn.active {
            color: var(--brand-primary);
        }

        .tab-btn::after {
            content: '';
            position: absolute;
            bottom: -12px;
            left: 0;
            width: 0;
            height: 3px;
            background: var(--brand-primary);
            transition: var(--transition-normal);
            border-radius: 3px 3px 0 0;
        }

        .tab-btn.active::after {
            width: 100%;
        }

        .tab-pane {
            display: none;
            animation: fadeIn 0.5s ease forwards;
        }

        .tab-pane.active {
            display: block;
        }

        .tab-pane p {
            font-size: 1.1rem;
            line-height: 1.8;
            margin-bottom: 20px;
        }

        .highlight-box {
            background: var(--brand-primary-light);
            border-left: 4px solid var(--brand-primary);
            padding: 20px;
            border-radius: 0 var(--radius-sm) var(--radius-sm) 0;
            margin: 25px 0;
        }

        .highlight-box h4 {
            margin-bottom: 10px;
            color: var(--text-primary);
        }

        /* --------------------------------------------------------------------
           10. ENGINEERING SKILLS & GEAR CALCULATOR WIDGET
           -------------------------------------------------------------------- */
        .skills-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 4rem;
        }

        .skill-bars {
            display: flex;
            flex-direction: column;
            gap: 30px;
        }

        .skill-item {
            background: var(--glass-bg);
            padding: 30px;
            border-radius: var(--radius-md);
            border: 1px solid var(--glass-border);
        }

        .skill-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 20px;
        }

        .skill-title {
            display: flex;
            align-items: center;
            gap: 15px;
            font-weight: 700;
            font-size: 1.2rem;
        }

        .skill-icon {
            width: 50px;
            height: 50px;
            border-radius: 12px;
            background: var(--brand-primary-light);
            color: var(--brand-primary);
            display: flex;
            justify-content: center;
            align-items: center;
            font-size: 1.5rem;
        }

        .skill-pct {
            font-family: var(--font-mono);
            font-weight: 800;
            font-size: 1.2rem;
            color: var(--brand-primary);
        }

        .progress-track {
            width: 100%;
            height: 10px;
            background: var(--glass-border);
            border-radius: var(--radius-full);
            overflow: hidden;
            position: relative;
        }

        .progress-fill {
            position: absolute;
            top: 0;
            left: 0;
            height: 100%;
            background: linear-gradient(90deg, var(--brand-primary), var(--brand-accent));
            border-radius: var(--radius-full);
            width: 0;
            transition: width 1.5s cubic-bezier(0.175, 0.885, 0.32, 1.275);
        }

        /* Interactive Gear Math Widget */
        .calculator-widget {
            background: var(--bg-surface);
            padding: 40px;
            border-radius: var(--radius-lg);
            border: 1px solid var(--glass-border);
            box-shadow: var(--shadow-lg);
        }

        .calc-header {
            margin-bottom: 25px;
            border-bottom: 1px solid var(--glass-border);
            padding-bottom: 15px;
        }

        .calc-title {
            font-family: var(--font-mono);
            font-size: 1.2rem;
            color: var(--brand-primary);
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .calc-form-group {
            margin-bottom: 20px;
        }

        .calc-label {
            display: block;
            font-size: 0.9rem;
            font-weight: 600;
            margin-bottom: 8px;
        }

        .calc-input {
            width: 100%;
            padding: 12px 15px;
            border-radius: var(--radius-sm);
            border: 1px solid var(--glass-border);
            background: var(--bg-base);
            color: var(--text-primary);
            font-family: var(--font-mono);
            transition: var(--transition-fast);
        }

        .calc-input:focus {
            outline: none;
            border-color: var(--brand-primary);
            box-shadow: 0 0 0 3px var(--brand-primary-light);
        }

        .calc-result-box {
            margin-top: 30px;
            background: var(--brand-primary-light);
            padding: 20px;
            border-radius: var(--radius-sm);
            border: 1px dashed var(--brand-primary);
            text-align: center;
        }

        .calc-result-label {
            font-size: 0.85rem;
            text-transform: uppercase;
            letter-spacing: 1px;
            font-weight: 700;
            color: var(--text-secondary);
        }

        .calc-result-value {
            font-family: var(--font-mono);
            font-size: 2.5rem;
            font-weight: 800;
            color: var(--brand-primary);
            margin-top: 5px;
        }

        .calc-note {
            font-size: 0.8rem;
            color: var(--text-muted);
            margin-top: 10px;
            font-style: italic;
        }

        /* --------------------------------------------------------------------
           11. EXPANDED PORTFOLIO SECTION (Grid + Modals)
           -------------------------------------------------------------------- */
        .portfolio-filters {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 15px;
            margin-bottom: 50px;
        }

        .filter-btn {
            background: var(--glass-bg);
            border: 1px solid var(--glass-border);
            padding: 12px 28px;
            border-radius: var(--radius-full);
            font-family: var(--font-mono);
            font-weight: 600;
            font-size: 0.95rem;
            color: var(--text-secondary);
            cursor: pointer;
            transition: var(--transition-normal);
        }

        .filter-btn.active,
        .filter-btn:hover {
            background: var(--brand-primary);
            color: white;
            border-color: var(--brand-primary);
            box-shadow: 0 5px 15px rgba(37, 99, 235, 0.3);
            transform: translateY(-2px);
        }

        .portfolio-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(400px, 1fr));
            gap: 40px;
        }

        .portfolio-card {
            display: flex;
            flex-direction: column;
            overflow: hidden;
            padding: 0;
            cursor: pointer;
        }

        .port-img-wrap {
            width: 100%;
            height: 280px;
            overflow: hidden;
            position: relative;
            background: var(--glass-border);
        }

        .port-img-wrap img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.8s cubic-bezier(0.175, 0.885, 0.32, 1.275);
        }

        .portfolio-card:hover .port-img-wrap img {
            transform: scale(1.1) rotate(1deg);
        }

        .port-overlay {
            position: absolute;
            inset: 0;
            background: rgba(15, 23, 42, 0.75);
            display: flex;
            justify-content: center;
            align-items: center;
            opacity: 0;
            transition: var(--transition-normal);
            backdrop-filter: blur(5px);
        }

        .portfolio-card:hover .port-overlay {
            opacity: 1;
        }

        .port-view-btn {
            width: 60px;
            height: 60px;
            background: var(--brand-primary);
            color: white;
            border-radius: 50%;
            display: flex;
            justify-content: center;
            align-items: center;
            font-size: 1.5rem;
            transform: translateY(20px);
            transition: var(--transition-normal);
        }

        .portfolio-card:hover .port-view-btn {
            transform: translateY(0);
        }

        .port-content {
            padding: 30px;
            flex-grow: 1;
            display: flex;
            flex-direction: column;
        }

        .port-cat {
            font-family: var(--font-mono);
            font-size: 0.8rem;
            color: var(--brand-primary);
            font-weight: 700;
            margin-bottom: 12px;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .port-title {
            font-size: 1.5rem;
            margin-bottom: 15px;
        }

        .port-desc {
            font-size: 1rem;
            color: var(--text-muted);
            margin-bottom: 25px;
            flex-grow: 1;
        }

        .port-meta {
            display: flex;
            justify-content: space-between;
            align-items: center;
            border-top: 1px solid var(--glass-border);
            padding-top: 20px;
        }

        .port-tool {
            display: flex;
            gap: 12px;
            color: var(--text-secondary);
            font-size: 1.2rem;
        }

        .port-meta-link {
            font-weight: 700;
            display: flex;
            align-items: center;
            gap: 8px;
            color: var(--text-primary);
            transition: var(--transition-fast);
        }

        .portfolio-card:hover .port-meta-link {
            color: var(--brand-primary);
            gap: 12px;
        }

        /* --------------------------------------------------------------------
           12. PUBLICATIONS & INSIGHTS (Blog styling)
           -------------------------------------------------------------------- */
        .insights-grid {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 40px;
        }

        .article-card {
            display: flex;
            gap: 30px;
            background: var(--glass-bg);
            padding: 30px;
            border-radius: var(--radius-lg);
            border: 1px solid var(--glass-border);
            transition: var(--transition-normal);
            align-items: center;
        }

        .article-card:hover {
            border-color: var(--brand-primary);
            transform: translateX(10px);
            box-shadow: var(--shadow-lg);
        }

        .article-date {
            min-width: 100px;
            text-align: center;
            padding: 20px;
            background: var(--bg-surface);
            border-radius: var(--radius-md);
            border: 1px solid var(--glass-border);
        }

        .date-month {
            display: block;
            font-weight: 800;
            font-size: 1.2rem;
            color: var(--brand-primary);
            text-transform: uppercase;
        }

        .date-year {
            font-family: var(--font-mono);
            color: var(--text-muted);
            font-size: 0.9rem;
        }

        .article-content h3 {
            font-size: 1.4rem;
            margin-bottom: 10px;
        }

        .article-content p {
            margin-bottom: 15px;
            font-size: 0.95rem;
        }

        .read-more {
            font-family: var(--font-mono);
            font-weight: 700;
            font-size: 0.9rem;
            color: var(--brand-primary);
            display: flex;
            align-items: center;
            gap: 5px;
        }

        /* --------------------------------------------------------------------
           13. CONTACT MODULE & MULTI-STEP FORM
           -------------------------------------------------------------------- */
        .contact-grid {
            display: grid;
            grid-template-columns: 1fr 1.5fr;
            gap: 5rem;
        }

        .contact-info {
            display: flex;
            flex-direction: column;
            gap: 30px;
        }

        .contact-card {
            padding: 30px;
            display: flex;
            align-items: flex-start;
            gap: 20px;
            background: var(--glass-bg);
            border-radius: var(--radius-md);
            border: 1px solid var(--glass-border);
        }

        .contact-icon {
            width: 60px;
            height: 60px;
            border-radius: var(--radius-md);
            background: var(--brand-primary-light);
            color: var(--brand-primary);
            display: flex;
            justify-content: center;
            align-items: center;
            font-size: 1.5rem;
            flex-shrink: 0;
        }

        .contact-details h4 {
            margin-bottom: 5px;
            font-size: 1.2rem;
        }

        .contact-details p,
        .contact-details a {
            color: var(--text-secondary);
            font-size: 1.05rem;
        }

        /* Advanced Form Styling */
        .advanced-form {
            background: var(--bg-surface);
            padding: 50px;
            border-radius: var(--radius-lg);
            border: 1px solid var(--glass-border);
            box-shadow: var(--shadow-lg);
        }

        .form-row {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 25px;
            margin-bottom: 25px;
        }

        .input-group {
            display: flex;
            flex-direction: column;
            gap: 10px;
            position: relative;
        }

        .input-group label {
            font-size: 0.95rem;
            font-weight: 600;
            color: var(--text-primary);
        }

        .form-control {
            padding: 16px 20px;
            border-radius: var(--radius-md);
            background: var(--bg-base);
            border: 1px solid var(--glass-border);
            color: var(--text-primary);
            font-family: var(--font-sans);
            font-size: 1.05rem;
            transition: var(--transition-fast);
            width: 100%;
        }

        .form-control:focus {
            outline: none;
            border-color: var(--brand-primary);
            box-shadow: 0 0 0 4px var(--brand-primary-light);
            background: var(--bg-surface);
        }

        textarea.form-control {
            resize: vertical;
            min-height: 180px;
        }

        /* Custom Checkbox */
        .custom-checkbox {
            display: flex;
            align-items: center;
            gap: 10px;
            margin-bottom: 30px;
            cursor: pointer;
        }

        .custom-checkbox input {
            display: none;
        }

        .checkmark {
            width: 24px;
            height: 24px;
            border: 2px solid var(--glass-border);
            border-radius: 6px;
            display: flex;
            justify-content: center;
            align-items: center;
            transition: var(--transition-fast);
        }

        .custom-checkbox input:checked+.checkmark {
            background: var(--brand-primary);
            border-color: var(--brand-primary);
        }

        .custom-checkbox input:checked+.checkmark::after {
            content: '\f00c';
            font-family: 'Font Awesome 6 Free';
            font-weight: 900;
            color: white;
            font-size: 0.8rem;
        }

        .check-label {
            font-size: 0.95rem;
            color: var(--text-secondary);
        }

        /* --------------------------------------------------------------------
           14. MEGA FOOTER
           -------------------------------------------------------------------- */
        footer {
            background: var(--bg-gradient-1);
            border-top: 1px solid var(--glass-border);
            padding: 100px 0 40px 0;
            margin-top: 120px;
            position: relative;
            overflow: hidden;
        }

        .footer-grid {
            display: grid;
            grid-template-columns: 2fr 1fr 1fr 1.5fr;
            gap: 4rem;
            margin-bottom: 80px;
            position: relative;
            z-index: 2;
        }

        .footer-brand p {
            margin-top: 25px;
            color: var(--text-muted);
            max-width: 400px;
            font-size: 1.05rem;
        }

        .footer-title {
            font-size: 1.3rem;
            margin-bottom: 30px;
            color: var(--text-primary);
        }

        .footer-links {
            list-style: none;
            display: flex;
            flex-direction: column;
            gap: 15px;
        }

        .footer-links a {
            color: var(--text-muted);
            transition: var(--transition-fast);
            font-size: 1.05rem;
            display: inline-flex;
            align-items: center;
            gap: 8px;
        }

        .footer-links a i {
            font-size: 0.8rem;
            color: var(--brand-primary);
            opacity: 0;
            transition: var(--transition-fast);
            transform: translateX(-10px);
        }

        .footer-links a:hover {
            color: var(--brand-primary);
            padding-left: 5px;
        }

        .footer-links a:hover i {
            opacity: 1;
            transform: translateX(0);
        }

        .social-circle-links {
            display: flex;
            gap: 15px;
        }

        .social-circle-links a {
            width: 45px;
            height: 45px;
            border-radius: 50%;
            background: var(--bg-surface);
            border: 1px solid var(--glass-border);
            display: flex;
            justify-content: center;
            align-items: center;
            color: var(--text-primary);
            font-size: 1.2rem;
            transition: var(--transition-fast);
        }

        .social-circle-links a:hover {
            background: var(--brand-primary);
            color: white;
            border-color: var(--brand-primary);
            transform: translateY(-5px);
        }

        .footer-bottom {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding-top: 40px;
            border-top: 1px solid var(--glass-border);
            color: var(--text-muted);
            font-size: 0.95rem;
            position: relative;
            z-index: 2;
        }

        /* --------------------------------------------------------------------
           15. MODAL SYSTEMS
           -------------------------------------------------------------------- */
        .modal {
            position: fixed;
            inset: 0;
            background: rgba(0, 0, 0, 0.85);
            backdrop-filter: blur(10px);
            z-index: var(--z-modal);
            display: flex;
            justify-content: center;
            align-items: center;
            opacity: 0;
            visibility: hidden;
            transition: var(--transition-normal);
            padding: 20px;
        }

        .modal.active {
            opacity: 1;
            visibility: visible;
        }

        .modal-content {
            width: 100%;
            max-width: 900px;
            max-height: 90vh;
            overflow-y: auto;
            background: var(--bg-surface);
            border: 1px solid var(--glass-border);
            border-radius: var(--radius-lg);
            padding: 50px;
            position: relative;
            transform: translateY(50px) scale(0.95);
            transition: var(--transition-normal);
        }

        .modal.active .modal-content {
            transform: translateY(0) scale(1);
        }

        .modal-close {
            position: absolute;
            top: 25px;
            right: 25px;
            width: 45px;
            height: 45px;
            border-radius: 50%;
            background: var(--bg-base);
            border: 1px solid var(--glass-border);
            color: var(--text-primary);
            display: flex;
            justify-content: center;
            align-items: center;
            font-size: 1.5rem;
            cursor: pointer;
            transition: var(--transition-fast);
        }

        .modal-close:hover {
            background: var(--brand-danger);
            color: white;
            border-color: var(--brand-danger);
            transform: rotate(90deg);
        }

        .modal-header {
            margin-bottom: 30px;
            border-bottom: 1px solid var(--glass-border);
            padding-bottom: 20px;
        }

        .modal-title {
            font-size: 2.5rem;
            margin-bottom: 10px;
        }

        .modal-body img {
            width: 100%;
            border-radius: var(--radius-md);
            margin-bottom: 30px;
            border: 1px solid var(--glass-border);
        }

        .spec-table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 30px;
        }

        .spec-table td {
            padding: 15px;
            border-bottom: 1px solid var(--glass-border);
        }

        .spec-table tr td:first-child {
            font-weight: 700;
            color: var(--text-secondary);
            width: 30%;
        }

        .spec-table tr td:last-child {
            font-family: var(--font-mono);
            color: var(--text-primary);
            font-weight: 600;
        }

        /* --------------------------------------------------------------------
           16. ANIMATIONS & RESPONSIVE DESIGN
           -------------------------------------------------------------------- */
        @keyframes slideUp {
            from {
                opacity: 0;
                transform: translateY(40px);
            }

            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes slideDown {
            from {
                opacity: 0;
                transform: translateY(-40px);
            }

            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes fadeIn {
            from {
                opacity: 0;
            }

            to {
                opacity: 1;
            }
        }

        @keyframes spinGear {
            100% {
                transform: rotate(360deg);
            }
        }

        @keyframes pulse {

            0%,
            100% {
                opacity: 1;
            }

            50% {
                opacity: 0.5;
            }
        }

        @keyframes pulseGlow {
            0% {
                transform: scale(0.95);
                opacity: 0.3;
            }

            100% {
                transform: scale(1.1);
                opacity: 0.6;
            }
        }

        @keyframes float {

            0%,
            100% {
                transform: translateY(0);
            }

            50% {
                transform: translateY(-20px);
            }
        }

        @keyframes gradientText {
            0% {
                background-position: 0% center;
            }

            100% {
                background-position: 200% center;
            }
        }

        @keyframes blink-caret {

            from,
            to {
                border-color: transparent
            }

            50% {
                border-color: var(--brand-primary);
            }
        }

        /* Intersection Observer Classes */
        .reveal {
            opacity: 0;
            transform: translateY(50px);
            transition: all 0.8s cubic-bezier(0.175, 0.885, 0.32, 1.275);
        }

        .reveal.active {
            opacity: 1;
            transform: translateY(0);
        }

        .reveal-left {
            opacity: 0;
            transform: translateX(-50px);
            transition: all 0.8s cubic-bezier(0.175, 0.885, 0.32, 1.275);
        }

        .reveal-left.active {
            opacity: 1;
            transform: translateX(0);
        }

        .reveal-right {
            opacity: 0;
            transform: translateX(50px);
            transition: all 0.8s cubic-bezier(0.175, 0.885, 0.32, 1.275);
        }

        .reveal-right.active {
            opacity: 1;
            transform: translateX(0);
        }

        @media (max-width: 1200px) {
            .hero-title {
                font-size: 3.5rem;
            }

            .portfolio-grid {
                grid-template-columns: repeat(2, 1fr);
            }

            .footer-grid {
                grid-template-columns: 1fr 1fr;
            }
        }

        @media (max-width: 992px) {

            .hero-grid,
            .about-grid,
            .skills-grid,
            .contact-grid {
                grid-template-columns: 1fr;
            }

            .hero-visual {
                order: -1;
                display: flex;
                justify-content: center;
            }

            .about-visual {
                max-width: 600px;
                margin: 0 auto;
            }
        }

        @media (max-width: 768px) {
            .nav-links {
                position: absolute;
                top: 90px;
                left: 0;
                width: 100%;
                background: var(--bg-surface);
                flex-direction: column;
                padding: 30px;
                gap: 20px;
                border-bottom: 1px solid var(--glass-border);
                clip-path: polygon(0 0, 100% 0, 100% 0, 0 0);
                transition: clip-path 0.4s ease;
            }

            .nav-links.nav-active {
                clip-path: polygon(0 0, 100% 0, 100% 100%, 0% 100%);
            }

            .mobile-toggle {
                display: block;
            }

            .hero-metrics {
                grid-template-columns: 1fr;
            }

            .portfolio-grid {
                grid-template-columns: 1fr;
            }

            .form-row {
                grid-template-columns: 1fr;
            }

            .footer-grid {
                grid-template-columns: 1fr;
            }

            .footer-bottom {
                flex-direction: column;
                gap: 20px;
                text-align: center;
            }
        }
    </style>
</head>
<!-- Add data-theme="dark" to body to enable dark mode if preferred -->
<body>

    <!-- ======================================================================
         ADVANCED BACKGROUND ENGINE
         ====================================================================== -->
    <div class="bg-engine">
        <div class="bg-orb"></div>
        <div class="bg-mesh"></div>
        <div class="bg-grid"></div>
        <canvas id="particle-canvas"></canvas>
    </div>

    <!-- ======================================================================
         PRELOADER
         ====================================================================== -->
    <div class="preloader" id="preloader">
        <div class="gear-loader"></div>
        <div class="loading-text">Initializing Systems</div>
    </div>

    <!-- ======================================================================
         HEADER & NAVIGATION
         ====================================================================== -->
    <header id="header">
        <div class="container">
            <div class="nav-wrapper">
                <a href="#hero" class="logo">
                    <div class="logo-icon"><i class="fa-solid fa-cube"></i></div>
                    3D Mech Design
                </a>
                <ul class="nav-links">
                    <li><a href="#hero" class="nav-link active">Home</a></li>
                    <li><a href="#about" class="nav-link">About</a></li>
                    <li><a href="#skills" class="nav-link">Expertise</a></li>
                    <li><a href="#portfolio" class="nav-link">Portfolio</a></li>
                    <li><a href="#insights" class="nav-link">Insights</a></li>
                </ul>
                <div class="nav-actions">
                    <a href="#contact" class="btn btn-primary">Hire Us</a>
                    <button class="mobile-toggle"><i class="fa-solid fa-bars"></i></button>
                </div>
            </div>
        </div>
    </header>

    <!-- ======================================================================
         HERO SECTION
         ====================================================================== -->
    <section id="hero">
        <div class="container">
            <div class="hero-grid">
                <div class="hero-content">
                    <div class="badge"><i class="fa-solid fa-rocket"></i> Design Beyond Boundaries</div>
                    <h1 class="hero-title">
                        Precision Engineering <br>
                        <span class="text-gradient">For The Future</span>
                    </h1>
                    <p class="hero-desc">Founded by Abdur Rafay Yousuf in Karachi, Pakistan, we deliver high-precision CAD modeling, 2D manufacturing drawings, gear design, and computational fluid dynamics (CFD) for domestic and international clients.</p>
                    
                    <div class="hero-metrics">
                        <div class="metric">
                            <span class="metric-value mono">100+</span>
                            <span class="metric-label">Projects Completed</span>
                        </div>
                        <div class="metric">
                            <span class="metric-value mono">ASME</span>
                            <span class="metric-label">Y14.5 Standards</span>
                        </div>
                        <div class="metric">
                            <span class="metric-value mono">24/7</span>
                            <span class="metric-label">Client Support</span>
                        </div>
                    </div>

                    <div class="hero-btns">
                        <a href="#portfolio" class="btn btn-primary"><i class="fa-solid fa-folder-open"></i> View Portfolio</a>
                        <a href="#contact" class="btn btn-secondary">Contact Us</a>
                    </div>
                </div>
                
                <div class="hero-visual">
                    <div class="profile-card glass-panel">
                        <div class="float-badge float-1">
                            <div class="float-icon"><i class="fa-solid fa-gear"></i></div>
                            <div class="float-text">Precision<span>Gear Design</span></div>
                        </div>
                        <div class="float-badge float-2">
                            <div class="float-icon"><i class="fa-solid fa-cube"></i></div>
                            <div class="float-text">Parametric<span>3D Modeling</span></div>
                        </div>
                        <div class="profile-img-wrap">
                            <img src="https://via.placeholder.com/300" alt="Abdur Rafay Yousuf - 3D Mech Design" class="profile-img">
                        </div>
                        <h3>Abdur Rafay Yousuf</h3>
                        <p>Mechanical Design Engineer</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- ======================================================================
         INFINITE SCROLL MARQUEE (TECH STACK)
         ====================================================================== -->
    <div class="marquee-wrapper">
        <div class="marquee-content">
            <div class="marquee-item"><i class="fa-solid fa-cube"></i> SolidWorks</div>
            <div class="marquee-item"><i class="fa-solid fa-calculator"></i> MATLAB</div>
            <div class="marquee-item"><i class="fa-solid fa-pen-ruler"></i> AutoCAD</div>
            <div class="marquee-item"><i class="fa-solid fa-arrows-spin"></i> Fusion 360</div>
            <div class="marquee-item"><i class="fa-solid fa-microchip"></i> LabVIEW</div>
            <div class="marquee-item"><i class="fa-solid fa-robot"></i> Arduino</div>
            <!-- Duplicate for infinite loop -->
            <div class="marquee-item"><i class="fa-solid fa-cube"></i> SolidWorks</div>
            <div class="marquee-item"><i class="fa-solid fa-calculator"></i> MATLAB</div>
            <div class="marquee-item"><i class="fa-solid fa-pen-ruler"></i> AutoCAD</div>
            <div class="marquee-item"><i class="fa-solid fa-arrows-spin"></i> Fusion 360</div>
            <div class="marquee-item"><i class="fa-solid fa-microchip"></i> LabVIEW</div>
            <div class="marquee-item"><i class="fa-solid fa-robot"></i> Arduino</div>
        </div>
    </div>

    <!-- ======================================================================
         ABOUT SECTION
         ====================================================================== -->
    <section id="about">
        <div class="container">
            <div class="section-header reveal">
                <div class="badge">Who We Are</div>
                <h2 class="section-title">The Mind Behind The Models</h2>
                <p class="section-desc">Self-taught CAD expertise transforming into a full-fledged mechanical design consultancy.</p>
            </div>
            
            <div class="about-grid reveal">
                <div class="about-visual">
                    <img src="https://via.placeholder.com/600x800" alt="Karachi HQ" class="about-image">
                    <div class="location-badge">
                        <i class="fa-solid fa-location-dot"></i>
                        <div>
                            <h4 style="margin:0;">Headquarters</h4>
                            <span style="color:var(--text-muted); font-size:0.9rem;">Karachi, Pakistan</span>
                        </div>
                    </div>
                </div>
                
                <div class="about-content">
                    <div class="tabs-header">
                        <button class="tab-btn active" data-target="tab-story">Our Story</button>
                        <button class="tab-btn" data-target="tab-edu">Education</button>
                        <button class="tab-btn" data-target="tab-dha">Leadership</button>
                    </div>
                    
                    <!-- UPDATED "OUR STORY" TAB AS REQUESTED -->
                    <div class="tab-pane active" id="tab-story">
                        <h3 style="margin-bottom: 5px; color: var(--text-primary);">Abdur Rafay Yousuf</h3>
                        <h4 style="margin-bottom: 20px; color: var(--brand-primary); font-family: var(--font-mono); font-size: 1rem;">Founder & Mechanical Design Engineer</h4>
                        
                        <p>Abdur Rafay Yousuf is the Founder of 3D Mech Design, a mechanical design and engineering consultancy established in 2023. His work focuses on transforming engineering concepts into precise, manufacturable, and performance-driven mechanical solutions.</p>
                        
                        <p>With hands-on experience in 3D CAD, mechanical component design, precision gear engineering, engineering drawings, GD&T, product development, and manufacturing support, Abdur Rafay combines engineering fundamentals with practical manufacturing knowledge.</p>
                        
                        <p>Through 3D Mech Design, he has worked on projects ranging from precision gear systems and mechanical components to prototypes and industrial products, supporting clients across Pakistan, the United States, and Germany.</p>
                        
                        <div class="highlight-box">
                            <h4>Vision</h4>
                            <p style="margin:0; font-size:1rem;">His vision is to build an engineering company that bridges the gap between CAD design and real-world manufacturing—creating designs that do not simply look correct on a screen, but are engineered to function, manufacture, and perform.<br><br><strong>Design Beyond Boundaries.</strong></p>
                        </div>
                    </div>
                    
                    <div class="tab-pane" id="tab-edu">
                        <p>Currently pursuing a Bachelor's degree in Mechanical Engineering at <strong>DHA Suffa University</strong> in Karachi, Pakistan, with an expected graduation in 2026. My foundational secondary education in pre-engineering was completed under the Sindh Board.</p>
                        <p>Looking ahead, I am actively exploring graduate degree programs and scholarship opportunities (such as the McCall MacBain Scholarship) in aerospace, mechatronics, and robotics for 2027 admission across Canada, Germany, Australia, and Italy.</p>
                    </div>

                    <div class="tab-pane" id="tab-dha">
                        <p>Beyond technical engineering, I've held organizational roles within university student groups. I currently serve as the treasurer for the Management Sciences Society at DHA Suffa University, organizing campus-wide events and managing budgets.</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- ======================================================================
         SKILLS & GEAR CALCULATOR SECTION
         ====================================================================== -->
    <section id="skills" style="background: var(--bg-surface);">
        <div class="container">
            <div class="skills-grid">
                <div class="skill-bars reveal-left">
                    <h2 class="section-title" style="font-size:2.5rem;">Technical Expertise</h2>
                    <p style="margin-bottom: 30px;">Mastery in the tools required to bring industrial designs from concept to reality.</p>
                    
                    <div class="skill-item">
                        <div class="skill-header">
                            <div class="skill-title">
                                <div class="skill-icon"><i class="fa-solid fa-cube"></i></div>
                                SolidWorks (Parametric & Surfaces)
                            </div>
                            <div class="skill-pct">95%</div>
                        </div>
                        <div class="progress-track">
                            <div class="progress-fill" style="width: 95%;"></div>
                        </div>
                    </div>
                    
                    <div class="skill-item">
                        <div class="skill-header">
                            <div class="skill-title">
                                <div class="skill-icon"><i class="fa-solid fa-gear"></i></div>
                                True Involute Gear Engineering
                            </div>
                            <div class="skill-pct">90%</div>
                        </div>
                        <div class="progress-track">
                            <div class="progress-fill" style="width: 90%;"></div>
                        </div>
                    </div>

                    <div class="skill-item">
                        <div class="skill-header">
                            <div class="skill-title">
                                <div class="skill-icon"><i class="fa-solid fa-calculator"></i></div>
                                MATLAB Numerical Analysis
                            </div>
                            <div class="skill-pct">85%</div>
                        </div>
                        <div class="progress-track">
                            <div class="progress-fill" style="width: 85%;"></div>
                        </div>
                    </div>
                </div>
                
                <div class="calculator-widget reveal-right">
                    <div class="calc-header">
                        <h3 class="calc-title"><i class="fa-solid fa-gear"></i> Quick Gear Pitch Calculator</h3>
                        <p style="font-size: 0.9rem; margin-top:5px;">Calculate Diametral Pitch (DP)</p>
                    </div>
                    
                    <div class="calc-form-group">
                        <label class="calc-label">Number of Teeth (N)</label>
                        <input type="number" class="calc-input" value="120" placeholder="e.g. 120">
                    </div>
                    
                    <div class="calc-form-group">
                        <label class="calc-label">Pitch Diameter (inches)</label>
                        <input type="number" class="calc-input" value="1.0" placeholder="e.g. 1.0">
                    </div>
                    
                    <div class="calc-result-box">
                        <div class="calc-result-label">Calculated Diametral Pitch</div>
                        <div class="calc-result-value">120 DP</div>
                    </div>
                    <p class="calc-note">*We specialize in fine-pitch 120 DP systems for optical and scientific instruments.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- ======================================================================
         PORTFOLIO SECTION
         ====================================================================== -->
    <section id="portfolio">
        <div class="container">
            <div class="section-header reveal">
                <div class="badge">Our Work</div>
                <h2 class="section-title">Selected Engineering Projects</h2>
                <p class="section-desc">Explore our custom prototypes, thermal systems, and precision tooling.</p>
            </div>
            
            <div class="portfolio-filters reveal">
                <button class="filter-btn active">All</button>
                <button class="filter-btn">Mechanical Design</button>
                <button class="filter-btn">Thermal Engineering</button>
                <button class="filter-btn">Robotics & Controls</button>
            </div>
            
            <div class="portfolio-grid reveal">
                <!-- Portfolio Card 1 -->
                <div class="portfolio-card glass-panel">
                    <div class="port-img-wrap">
                        <img src="https://via.placeholder.com/600x400" alt="Mahfooz Wheelchair">
                        <div class="port-overlay">
                            <div class="port-view-btn"><i class="fa-solid fa-eye"></i></div>
                        </div>
                    </div>
                    <div class="port-content">
                        <div class="port-cat">Mechanical Design</div>
                        <h3 class="port-title">Mahfooz Wheelchair Prototype</h3>
                        <p class="port-desc">A custom mobility device designed with stair-lifting capabilities and adjustable angles for seamless multi-story building access.</p>
                        <div class="port-meta">
                            <div class="port-tool">
                                <i class="fa-solid fa-cube" title="SolidWorks"></i>
                            </div>
                            <a href="#" class="port-meta-link">View Pitch Deck <i class="fa-solid fa-arrow-right"></i></a>
                        </div>
                    </div>
                </div>

                <!-- Portfolio Card 2 -->
                <div class="portfolio-card glass-panel">
                    <div class="port-img-wrap">
                        <img src="https://via.placeholder.com/600x400" alt="Sand Battery">
                        <div class="port-overlay">
                            <div class="port-view-btn"><i class="fa-solid fa-eye"></i></div>
                        </div>
                    </div>
                    <div class="port-content">
                        <div class="port-cat">Thermal Engineering</div>
                        <h3 class="port-title">Thermal Energy Sand Battery</h3>
                        <p class="port-desc">A lab-scale 3x3x3 foot prototype utilizing silica sand, aluminum chips, and heat exchanger coils for industrial heat recovery.</p>
                        <div class="port-meta">
                            <div class="port-tool">
                                <i class="fa-solid fa-fire" title="CFD"></i>
                                <i class="fa-solid fa-calculator" title="MATLAB"></i>
                            </div>
                            <a href="#" class="port-meta-link">View Analysis <i class="fa-solid fa-arrow-right"></i></a>
                        </div>
                    </div>
                </div>

                <!-- Portfolio Card 3 -->
                <div class="portfolio-card glass-panel">
                    <div class="port-img-wrap">
                        <img src="https://via.placeholder.com/600x400" alt="Gear System">
                        <div class="port-overlay">
                            <div class="port-view-btn"><i class="fa-solid fa-eye"></i></div>
                        </div>
                    </div>
                    <div class="port-content">
                        <div class="port-cat">Precision Tooling</div>
                        <h3 class="port-title">120 DP Fine-Pitch Gear System</h3>
                        <p class="port-desc">Mathematically accurate involute spur gear system alongside custom hobbing, shaping, and inspection arbors for scientific instruments.</p>
                        <div class="port-meta">
                            <div class="port-tool">
                                <i class="fa-solid fa-gear" title="Gear Design"></i>
                            </div>
                            <a href="#" class="port-meta-link">View Drawings <i class="fa-solid fa-arrow-right"></i></a>
                        </div>
                    </div>
                </div>

                <!-- Portfolio Card 4 -->
                <div class="portfolio-card glass-panel">
                    <div class="port-img-wrap">
                        <img src="https://via.placeholder.com/600x400" alt="Arduino Robot">
                        <div class="port-overlay">
                            <div class="port-view-btn"><i class="fa-solid fa-eye"></i></div>
                        </div>
                    </div>
                    <div class="port-content">
                        <div class="port-cat">Robotics & Controls</div>
                        <h3 class="port-title">Arduino PID Control Platform</h3>
                        <p class="port-desc">Open-source instrumentation platform and line-following robot to measure and validate real-time Proportional-Integral-Derivative (PID) control algorithms.</p>
                        <div class="port-meta">
                            <div class="port-tool">
                                <i class="fa-solid fa-microchip" title="Arduino"></i>
                                <i class="fa-solid fa-code" title="C/C++"></i>
                            </div>
                            <a href="#" class="port-meta-link">View Firmware <i class="fa-solid fa-arrow-right"></i></a>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- ======================================================================
         INSIGHTS / BLOG SECTION
         ====================================================================== -->
    <section id="insights" style="background: var(--bg-surface);">
        <div class="container">
            <div class="section-header reveal">
                <div class="badge">Publications</div>
                <h2 class="section-title">Engineering Insights</h2>
                <p class="section-desc">Technical deep-dives and computational reports authored by Abdur Rafay Yousuf.</p>
            </div>
            
            <div class="insights-grid reveal">
                <div class="article-card">
                    <div class="article-date">
                        <span class="date-month">Nov</span>
                        <span class="date-year">2025</span>
                    </div>
                    <div class="article-content">
                        <h3>Optimizing PID Control with Arduino</h3>
                        <p>A technical review on breadboard circuitry, ultrasonic sensors, and firmware code development for proximity alert systems.</p>
                        <a href="#" class="read-more">Read Full Paper <i class="fa-solid fa-arrow-right"></i></a>
                    </div>
                </div>

                <div class="article-card">
                    <div class="article-date">
                        <span class="date-month">Mar</span>
                        <span class="date-year">2026</span>
                    </div>
                    <div class="article-content">
                        <h3>CFD Analysis in Heat Recovery</h3>
                        <p>Analytical studies and visualization tasks regarding computational fluid dynamics velocity and pressure distributions in sand batteries.</p>
                        <a href="#" class="read-more">Read Full Paper <i class="fa-solid fa-arrow-right"></i></a>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- ======================================================================
         CONTACT SECTION & FORM
         ====================================================================== -->
    <section id="contact">
        <div class="container">
            <div class="section-header reveal">
                <div class="badge">Get In Touch</div>
                <h2 class="section-title">Let's Build Something Precise</h2>
                <p class="section-desc">Whether you need custom gear arbors or full CFD analysis, 3D Mech Design is ready.</p>
            </div>
            
            <div class="contact-grid reveal">
                <div class="contact-info">
                    <div class="contact-card">
                        <div class="contact-icon"><i class="fa-solid fa-envelope"></i></div>
                        <div class="contact-details">
                            <h4>Email Address</h4>
                            <a href="mailto:info@3dmechdesign.com">info@3dmechdesign.com</a>
                        </div>
                    </div>
                    <div class="contact-card">
                        <div class="contact-icon"><i class="fa-solid fa-map-location-dot"></i></div>
                        <div class="contact-details">
                            <h4>Location</h4>
                            <p>Karachi, Sindh, Pakistan</p>
                        </div>
                    </div>
                    <div class="contact-card">
                        <div class="contact-icon"><i class="fa-solid fa-handshake"></i></div>
                        <div class="contact-details">
                            <h4>Partnerships</h4>
                            <p>Open for Master Service & NDA Agreements.</p>
                        </div>
                    </div>
                </div>
                
                <div class="advanced-form">
                    <form action="#" method="POST">
                        <div class="form-row">
                            <div class="input-group">
                                <label for="name">Full Name</label>
                                <input type="text" id="name" class="form-control" placeholder="John Doe">
                            </div>
                            <div class="input-group">
                                <label for="email">Email Address</label>
                                <input type="email" id="email" class="form-control" placeholder="john@company.com">
                            </div>
                        </div>
                        <div class="input-group" style="margin-bottom: 25px;">
                            <label for="service">Service Required</label>
                            <select id="service" class="form-control">
                                <option>Parametric 3D Modeling</option>
                                <option>2D Manufacturing Drawings (GD&T)</option>
                                <option>Gear Design (Hobbing/Shaping)</option>
                                <option>CFD Analysis</option>
                            </select>
                        </div>
                        <div class="input-group" style="margin-bottom: 25px;">
                            <label for="message">Project Details</label>
                            <textarea id="message" class="form-control" placeholder="Tell us about your technical requirements..."></textarea>
                        </div>
                        <label class="custom-checkbox">
                            <input type="checkbox" required>
                            <span class="checkmark"></span>
                            <span class="check-label">I agree to standard Non-Disclosure Agreement (NDA) terms prior to sharing proprietary designs.</span>
                        </label>
                        <button type="submit" class="btn btn-primary" style="width: 100%;">Submit Inquiry</button>
                    </form>
                </div>
            </div>
        </div>
    </section>

    <!-- ======================================================================
         MEGA FOOTER WITH LINKED SOCIALS
         ====================================================================== -->
    <footer>
        <div class="container">
            <div class="footer-grid">
                <div class="footer-brand">
                    <a href="#hero" class="logo">
                        <div class="logo-icon"><i class="fa-solid fa-cube"></i></div>
                        3D Mech Design
                    </a>
                    <p>Headquartered in Karachi, Pakistan, we provide top-tier mechanical engineering and CAD consulting services worldwide.</p>
                    
                    <h3 class="footer-title" style="margin-top: 30px;">Connect with us</h3>
                    
                    <!-- ==========================================================
                         HERE ARE YOUR REQUESTED SOCIAL LINKS (LinkedIn & Insta)
                         ========================================================== -->
                    <div class="social-circle-links">
                        <!-- LinkedIn Button targeting the Admin Dashboard URL -->
                        <a href="https://www.linkedin.com/company/107649824/admin/dashboard/" target="_blank" rel="noopener noreferrer" title="LinkedIn Admin Dashboard">
                            <i class="fa-brands fa-linkedin"></i>
                        </a>
                        
                        <!-- Instagram Button targeting your requested IG URL -->
                        <a href="https://www.instagram.com/3d_mechdesign/" target="_blank" rel="noopener noreferrer" title="Instagram">
                            <i class="fa-brands fa-instagram"></i>
                        </a>
                    </div>
                    <!-- ========================================================== -->
                    
                </div>
                
                <div>
                    <h3 class="footer-title">Services</h3>
                    <ul class="footer-links">
                        <li><a href="#"><i class="fa-solid fa-chevron-right"></i> CAD Modeling</a></li>
                        <li><a href="#"><i class="fa-solid fa-chevron-right"></i> 2D Technical Drawings</a></li>
                        <li><a href="#"><i class="fa-solid fa-chevron-right"></i> Gear Engineering</a></li>
                        <li><a href="#"><i class="fa-solid fa-chevron-right"></i> CFD Analysis</a></li>
                    </ul>
                </div>

                <div>
                    <h3 class="footer-title">Company</h3>
                    <ul class="footer-links">
                        <li><a href="#about"><i class="fa-solid fa-chevron-right"></i> About Founder</a></li>
                        <li><a href="#portfolio"><i class="fa-solid fa-chevron-right"></i> Projects</a></li>
                        <li><a href="#insights"><i class="fa-solid fa-chevron-right"></i> Publications</a></li>
                    </ul>
                </div>
                
                <div>
                    <h3 class="footer-title">Contact</h3>
                    <ul class="footer-links">
                        <li><a href="mailto:info@3dmechdesign.com"><i class="fa-solid fa-envelope"></i> Email Us</a></li>
                        <li><a href="#"><i class="fa-solid fa-location-dot"></i> Karachi, Pakistan</a></li>
                    </ul>
                </div>
            </div>
            
            <div class="footer-bottom">
                <p>&copy; 2026 3D Mech Design. Founded by Abdur Rafay Yousuf. All rights reserved.</p>
                <p>Designed with precision.</p>
            </div>
        </div>
    </footer>

    <!-- ======================================================================
         JAVASCRIPT FOR INTERACTIONS (Tabs, Modals, Navbar Scroll)
         ====================================================================== -->
    <script>
        document.addEventListener('DOMContentLoaded', () => {
            // Preloader removal
            const preloader = document.getElementById('preloader');
            setTimeout(() => {
                preloader.classList.add('hidden');
            }, 800);

            // Navbar Scroll Effect
            const header = document.getElementById('header');
            window.addEventListener('scroll', () => {
                if(window.scrollY > 50) {
                    header.classList.add('scrolled');
                } else {
                    header.classList.remove('scrolled');
                }
            });

            // Tabs Logic
            const tabBtns = document.querySelectorAll('.tab-btn');
            const tabPanes = document.querySelectorAll('.tab-pane');
            
            tabBtns.forEach(btn => {
                btn.addEventListener('click', () => {
                    tabBtns.forEach(b => b.classList.remove('active'));
                    tabPanes.forEach(p => p.classList.remove('active'));
                    
                    btn.classList.add('active');
                    const target = document.getElementById(btn.getAttribute('data-target'));
                    if(target) target.classList.add('active');
                });
            });

            // Simple Intersection Observer for Animations
            const revealElements = document.querySelectorAll('.reveal, .reveal-left, .reveal-right');
            const revealOptions = { threshold: 0.15, rootMargin: "0px 0px -50px 0px" };
            
            const revealObserver = new IntersectionObserver((entries, observer) => {
                entries.forEach(entry => {
                    if(!entry.isIntersecting) return;
                    entry.target.classList.add('active');
                    observer.unobserve(entry.target);
                });
            }, revealOptions);

            revealElements.forEach(el => revealObserver.observe(el));
        });
    </script>
</body>
</html>
