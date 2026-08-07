<!DOCTYPE html>
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
    <link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@300;400;500;600;700;800&family=Plus+Jakarta+Sans:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">

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
            --brand-primary-light: rgba(37, 99, 235, 0.10);
            --brand-accent: #8b5cf6;
            --brand-success: #059669;
            --brand-warning: #d97706;
            --brand-danger: #e11d48;
            --glass-bg: rgba(255, 255, 255, 0.65);
            --glass-border: rgba(15, 23, 42, 0.10);
            --glass-highlight: rgba(255, 255, 255, 0.80);
            --grid-line: rgba(37, 99, 235, 0.05);
            --particle-color: rgba(37, 99, 235, 0.30);
            --shadow-sm: 0 2px 4px rgba(0, 0, 0, 0.02);
            --shadow-md: 0 10px 40px rgba(15, 23, 42, 0.06);
            --shadow-lg: 0 20px 60px rgba(37, 99, 235, 0.12);
            --shadow-glow: 0 0 30px rgba(37, 99, 235, 0.30);
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
            --z-editor: 10000;
        }
        [data-theme="dark"] {
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
            background-image: radial-gradient(at 0% 0%, rgba(37, 99, 235, 0.15) 0px, transparent 50%), radial-gradient(at 100% 0%, rgba(139, 92, 246, 0.15) 0px, transparent 50%), radial-gradient(at 100% 100%, rgba(6, 182, 212, 0.15) 0px, transparent 50%), radial-gradient(at 0% 100%, rgba(37, 99, 235, 0.15) 0px, transparent 50%);
            filter: blur(80px);
            opacity: 0.8;
            animation: breatheMesh 20s ease-in-out infinite alternate;
        }
        .bg-grid {
            position: absolute;
            inset: 0;
            background-image: linear-gradient(var(--grid-line) 1px, transparent 1px), linear-gradient(90deg, var(--grid-line) 1px, transparent 1px);
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
            border: none;
            cursor: pointer;
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
            background: none;
            border: none;
            cursor: pointer;
            font-family: var(--font-sans);
            font-size: 1rem;
        }
        .portfolio-card:hover .port-meta-link {
            color: var(--brand-primary);
            gap: 12px;
        }
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
            background: none;
            border: none;
            cursor: pointer;
            padding: 0;
        }
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
        @keyframes breatheMesh {
            0% {
                filter: blur(80px) brightness(1);
            }
            100% {
                filter: blur(100px) brightness(1.2);
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

        /* ==================================================================
           BACK TO TOP BUTTON
           ================================================================== */
        .back-top {
            position: fixed;
            bottom: 30px;
            right: 30px;
            width: 55px;
            height: 55px;
            border-radius: 50%;
            background: var(--brand-primary);
            color: white;
            border: none;
            font-size: 1.4rem;
            cursor: pointer;
            box-shadow: var(--shadow-lg);
            transition: var(--transition-normal);
            opacity: 0;
            visibility: hidden;
            transform: translateY(20px);
            z-index: var(--z-sticky);
            display: flex;
            align-items: center;
            justify-content: center;
        }
        .back-top.visible {
            opacity: 1;
            visibility: visible;
            transform: translateY(0);
        }
        .back-top:hover {
            transform: translateY(-5px) scale(1.05);
            box-shadow: var(--shadow-glow);
        }

        /* ==================================================================
           EDITOR MODE — HIDDEN DASHBOARD
           ================================================================== */
        .editor-login-overlay {
            position: fixed;
            inset: 0;
            background: rgba(0, 0, 0, 0.85);
            backdrop-filter: blur(14px);
            z-index: var(--z-editor);
            display: none;
            justify-content: center;
            align-items: center;
            padding: 20px;
        }
        .editor-login-overlay.active {
            display: flex;
        }
        .editor-login-box {
            background: var(--bg-surface);
            border-radius: var(--radius-lg);
            padding: 50px;
            max-width: 460px;
            width: 100%;
            border: 1px solid var(--glass-border);
            box-shadow: var(--shadow-lg);
            position: relative;
        }
        .editor-login-box h2 {
            margin-bottom: 10px;
            display: flex;
            align-items: center;
            gap: 12px;
        }
        .editor-login-box p {
            color: var(--text-muted);
            margin-bottom: 30px;
        }
        .editor-login-box .input-group {
            margin-bottom: 20px;
        }
        .editor-login-box .form-control {
            background: var(--bg-base);
        }
        .editor-login-box .btn {
            width: 100%;
        }
        .editor-login-close {
            position: absolute;
            top: 20px;
            right: 20px;
            background: none;
            border: none;
            font-size: 1.5rem;
            color: var(--text-muted);
            cursor: pointer;
            transition: var(--transition-fast);
        }
        .editor-login-close:hover {
            color: var(--brand-danger);
            transform: rotate(90deg);
        }

        /* Editor Dashboard */
        .editor-dashboard {
            position: fixed;
            inset: 0;
            background: var(--bg-base);
            z-index: calc(var(--z-editor) + 1);
            display: none;
            flex-direction: column;
            overflow: hidden;
        }
        .editor-dashboard.active {
            display: flex;
        }
        .editor-dash-header {
            background: var(--bg-surface);
            border-bottom: 1px solid var(--glass-border);
            padding: 18px 40px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-shrink: 0;
        }
        .editor-dash-header h2 {
            font-size: 1.4rem;
            display: flex;
            align-items: center;
            gap: 12px;
        }
        .editor-dash-header h2 i {
            color: var(--brand-primary);
        }
        .editor-dash-actions {
            display: flex;
            gap: 15px;
            align-items: center;
        }
        .editor-dash-actions .btn {
            padding: 10px 22px;
            font-size: 0.9rem;
        }
        .editor-dash-body {
            flex: 1;
            overflow-y: auto;
            padding: 40px;
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 40px;
            align-content: start;
        }
        .editor-card {
            background: var(--bg-surface);
            border-radius: var(--radius-lg);
            border: 1px solid var(--glass-border);
            padding: 30px;
            box-shadow: var(--shadow-sm);
        }
        .editor-card h3 {
            margin-bottom: 20px;
            font-size: 1.2rem;
            display: flex;
            align-items: center;
            gap: 10px;
            border-bottom: 1px solid var(--glass-border);
            padding-bottom: 15px;
        }
        .editor-card .input-group {
            margin-bottom: 18px;
        }
        .editor-card .input-group label {
            font-size: 0.85rem;
            font-weight: 600;
            color: var(--text-secondary);
        }
        .editor-card .form-control {
            font-size: 0.95rem;
            padding: 12px 16px;
        }
        .editor-card .btn {
            margin-top: 5px;
        }
        .editor-card .btn-success {
            background: var(--brand-success);
            color: white;
        }
        .editor-card .btn-success:hover {
            opacity: 0.85;
            transform: translateY(-2px);
        }
        .editor-card .btn-danger {
            background: var(--brand-danger);
            color: white;
        }
        .editor-card .btn-danger:hover {
            opacity: 0.85;
            transform: translateY(-2px);
        }
        .editor-toast {
            position: fixed;
            bottom: 40px;
            right: 40px;
            background: var(--bg-surface);
            border: 1px solid var(--glass-border);
            border-radius: var(--radius-md);
            padding: 18px 30px;
            box-shadow: var(--shadow-lg);
            transform: translateY(100px);
            opacity: 0;
            transition: var(--transition-normal);
            z-index: calc(var(--z-editor) + 2);
            display: flex;
            align-items: center;
            gap: 14px;
            font-weight: 600;
            color: var(--text-primary);
        }
        .editor-toast.show {
            transform: translateY(0);
            opacity: 1;
        }
        .editor-toast i {
            font-size: 1.4rem;
            color: var(--brand-success);
        }
        .editor-toast.error i {
            color: var(--brand-danger);
        }

        /* Editor lock icon on profile */
        .editor-lock-trigger {
            position: fixed;
            bottom: 30px;
            left: 30px;
            width: 50px;
            height: 50px;
            border-radius: 50%;
            background: var(--glass-bg);
            backdrop-filter: blur(12px);
            border: 1px solid var(--glass-border);
            color: var(--text-muted);
            font-size: 1.2rem;
            cursor: pointer;
            transition: var(--transition-normal);
            z-index: var(--z-sticky);
            display: flex;
            align-items: center;
            justify-content: center;
            box-shadow: var(--shadow-sm);
        }
        .editor-lock-trigger:hover {
            background: var(--brand-primary);
            color: white;
            border-color: var(--brand-primary);
            transform: scale(1.1);
            box-shadow: var(--shadow-glow);
        }

        /* ==================================================================
           RESPONSIVE
           ================================================================== */
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
            .editor-dash-body {
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
            .editor-dash-body {
                grid-template-columns: 1fr;
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
            .insights-grid {
                grid-template-columns: 1fr;
            }
            .editor-dash-header {
                flex-direction: column;
                gap: 15px;
                padding: 18px 20px;
                align-items: stretch;
                text-align: center;
            }
            .editor-dash-actions {
                justify-content: center;
                flex-wrap: wrap;
            }
            .editor-dash-body {
                padding: 20px;
            }
            .editor-login-box {
                padding: 30px 20px;
            }
            .modal-content {
                padding: 30px 20px;
            }
            .modal-title {
                font-size: 1.8rem;
            }
            .float-badge {
                display: none;
            }
            .profile-img-wrap {
                width: 220px;
                height: 220px;
            }
        }
        @media (max-width: 480px) {
            section {
                padding: 80px 0;
            }
            .hero-title {
                font-size: 2.4rem;
            }
            .section-title {
                font-size: 2.4rem;
            }
            .profile-img-wrap {
                width: 180px;
                height: 180px;
            }
            .profile-card {
                padding: 30px 20px;
            }
            .hero-btns {
                flex-direction: column;
            }
            .hero-btns .btn {
                width: 100%;
                justify-content: center;
            }
            .editor-dash-header h2 {
                font-size: 1.1rem;
            }
        }
    </style>
</head>
<body>

    <!-- ==================================================================
         PRELOADER
         ================================================================== -->
    <div class="preloader" id="preloader">
        <div class="gear-loader"></div>
        <div class="loading-text">Loading Assets...</div>
    </div>

    <!-- ==================================================================
         BACKGROUND ENGINE
         ================================================================== -->
    <div class="bg-engine">
        <canvas id="particle-canvas"></canvas>
        <div class="bg-mesh"></div>
        <div class="bg-grid"></div>
    </div>

    <!-- ==================================================================
         HEADER NAVIGATION
         ================================================================== -->
    <header id="header">
        <div class="container nav-wrapper">
            <a href="#" class="logo" id="brandLogo">
                <div class="logo-icon"><i class="fas fa-cube"></i></div>
                <span id="brandNameDisplay">3D Mech<span>Design</span></span>
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

    <!-- ==================================================================
         EDITOR LOCK TRIGGER (visible only to the user)
         ================================================================== -->
    <button class="editor-lock-trigger" id="editorLockTrigger" aria-label="Open Editor">
        <i class="fas fa-lock"></i>
    </button>

    <!-- ==================================================================
         EDITOR LOGIN OVERLAY
         ================================================================== -->
    <div class="editor-login-overlay" id="editorLoginOverlay">
        <div class="editor-login-box">
            <button class="editor-login-close" id="editorLoginClose"><i class="fas fa-times"></i></button>
            <h2><i class="fas fa-shield-alt"></i> Editor Access</h2>
            <p>Enter your secure password to modify portfolio content.</p>
            <div class="input-group">
                <label>Password</label>
                <input type="password" class="form-control" id="editorPassword" placeholder="••••••••" autofocus>
            </div>
            <button class="btn btn-primary" id="editorLoginBtn">
                <i class="fas fa-unlock"></i> Unlock Editor
            </button>
            <div style="margin-top: 15px; font-size: 0.85rem; color: var(--text-muted);">
                <i class="fas fa-info-circle"></i> Default: <strong>admin123</strong> (change in settings)
            </div>
        </div>
    </div>

    <!-- ==================================================================
         EDITOR DASHBOARD
         ================================================================== -->
    <div class="editor-dashboard" id="editorDashboard">
        <div class="editor-dash-header">
            <h2><i class="fas fa-edit"></i> <span>Content Editor</span></h2>
            <div class="editor-dash-actions">
                <button class="btn btn-secondary" id="editorSaveAll"><i class="fas fa-save"></i> Save All</button>
                <button class="btn btn-secondary" id="editorPreviewToggle"><i class="fas fa-eye"></i> Preview</button>
                <button class="btn btn-secondary" id="editorCloseDash"><i class="fas fa-times"></i> Close</button>
            </div>
        </div>
        <div class="editor-dash-body" id="editorDashBody">

            <!-- Profile Editor -->
            <div class="editor-card">
                <h3><i class="fas fa-user-circle"></i> Profile</h3>
                <div class="input-group">
                    <label>Full Name</label>
                    <input type="text" class="form-control" id="editName" value="Abdur Rafay Yousuf">
                </div>
                <div class="input-group">
                    <label>Title / Role</label>
                    <input type="text" class="form-control" id="editTitle" value="Founder, 3D Mech Design">
                </div>
                <div class="input-group">
                    <label>Profile Image URL</label>
                    <input type="text" class="form-control" id="editProfileImg" value="https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?fit=crop&w=600&h=600">
                </div>
                <div class="input-group">
                    <label>Bio / Tagline</label>
                    <textarea class="form-control" id="editBio" rows="3">I am Abdur Rafay Yousuf, based in Karachi, Pakistan. I specialize in complex parametric CAD modeling, Computational Fluid Dynamics (CFD), and thermodynamic prototyping for industrial applications.</textarea>
                </div>
            </div>

            <!-- About Section -->
            <div class="editor-card">
                <h3><i class="fas fa-info-circle"></i> About</h3>
                <div class="input-group">
                    <label>Mission Statement</label>
                    <textarea class="form-control" id="editMission" rows="4">My core mission is to develop localized, highly efficient mechanical solutions. This drive was heavily inspired by personal family challenges regarding accessibility, which directly motivated the creation of the Mahfooz Wheelchair Project—a localized mobility device with stair-lifting capabilities.</textarea>
                </div>
                <div class="input-group">
                    <label>Methodology</label>
                    <textarea class="form-control" id="editMethodology" rows="3">I strictly adhere to a mathematically validated design process. Whether it is a thermal sand battery or gear assembly, no dimension is arbitrary.</textarea>
                </div>
                <div class="input-group">
                    <label>Mentorship / Community</label>
                    <textarea class="form-control" id="editMentorship" rows="3">Knowledge isolation hinders engineering progress. I actively log mentorship and skill-sharing activities with junior students and associates.</textarea>
                </div>
            </div>

            <!-- Skills -->
            <div class="editor-card">
                <h3><i class="fas fa-chart-bar"></i> Skills</h3>
                <div class="input-group">
                    <label>Skill 1 Name</label>
                    <input type="text" class="form-control" id="editSkill1Name" value="3D CAD &amp; Drafting">
                </div>
                <div class="input-group">
                    <label>Skill 1 %</label>
                    <input type="number" class="form-control" id="editSkill1Pct" value="95" min="0" max="100">
                </div>
                <div class="input-group">
                    <label>Skill 2 Name</label>
                    <input type="text" class="form-control" id="editSkill2Name" value="CFD Analysis">
                </div>
                <div class="input-group">
                    <label>Skill 2 %</label>
                    <input type="number" class="form-control" id="editSkill2Pct" value="88" min="0" max="100">
                </div>
                <div class="input-group">
                    <label>Skill 3 Name</label>
                    <input type="text" class="form-control" id="editSkill3Name" value="Thermodynamics">
                </div>
                <div class="input-group">
                    <label>Skill 3 %</label>
                    <input type="number" class="form-control" id="editSkill3Pct" value="85" min="0" max="100">
                </div>
            </div>

            <!-- Contact Info -->
            <div class="editor-card">
                <h3><i class="fas fa-address-card"></i> Contact</h3>
                <div class="input-group">
                    <label>Email</label>
                    <input type="email" class="form-control" id="editEmail" value="consult@3dmechdesign.com">
                </div>
                <div class="input-group">
                    <label>Location</label>
                    <input type="text" class="form-control" id="editLocation" value="Karachi, Sindh, Pakistan">
                </div>
                <div class="input-group">
                    <label>Editor Password</label>
                    <input type="text" class="form-control" id="editEditorPassword" value="admin123">
                </div>
                <div style="margin-top: 15px; font-size: 0.85rem; color: var(--text-muted);">
                    <i class="fas fa-shield-alt"></i> Change password to lock editor.
                </div>
            </div>

            <!-- Portfolio Management -->
            <div class="editor-card" style="grid-column: 1 / -1;">
                <h3><i class="fas fa-project-diagram"></i> Portfolio Projects</h3>
                <div id="editorProjectList" style="margin-bottom: 20px;"></div>
                <button class="btn btn-primary" id="editorAddProject"><i class="fas fa-plus"></i> Add Project</button>
            </div>

        </div>
    </div>

    <!-- ==================================================================
         EDITOR TOAST
         ================================================================== -->
    <div class="editor-toast" id="editorToast">
        <i class="fas fa-check-circle"></i>
        <span id="editorToastMsg">Changes saved!</span>
    </div>

    <!-- ==================================================================
         MAIN CONTENT
         ================================================================== -->
    <main>

        <!-- ==================================================================
             SECTION 1: HERO
             ================================================================== -->
        <section id="hero">
            <div class="container hero-grid">
                <div class="hero-content">
                    <div class="badge"><i class="fas fa-rocket"></i> <span id="heroBadgeText">Mechanical Design Consultant</span></div>
                    <h1 class="hero-title">
                        Precision Engineering <br>
                        <span class="typewriter-wrapper">
                            <span class="typewriter-text" id="typewriter"></span>
                        </span>
                    </h1>
                    <p class="hero-desc" id="heroBioText">
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
                            <img src="https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?fit=crop&w=600&h=600" alt="Abdur Rafay Yousuf" class="profile-img" id="profileImage">
                        </div>
                        <h3 id="profileNameDisplay">Abdur Rafay Yousuf</h3>
                        <p id="profileTitleDisplay">Founder, 3D Mech Design</p>
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
                <div class="marquee-item"><i class="fa-solid fa-code"></i> SolidWorks</div>
                <div class="marquee-item"><i class="fa-brands fa-hubspot"></i> Fusion 360</div>
                <div class="marquee-item"><i class="fa-solid fa-pen-ruler"></i> AutoCAD</div>
                <div class="marquee-item"><i class="fa-solid fa-calculator"></i> MATLAB</div>
                <div class="marquee-item"><i class="fa-solid fa-network-wired"></i> Ansys</div>
                <div class="marquee-item"><i class="fa-brands fa-usb"></i> Arduino Uno</div>
                <div class="marquee-item"><i class="fa-solid fa-wind"></i> CFD Simulation</div>
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
                                <span class="mono" style="color: var(--text-muted); font-size: 0.9rem;" id="aboutLocationText">Karachi, Pakistan</span>
                            </div>
                        </div>
                    </div>
                    <div class="about-content reveal-right">
                        <div class="tabs-header">
                            <button class="tab-btn active" data-tab="mission">Mission</button>
                            <button class="tab-btn" data-tab="methodology">Methodology</button>
                            <button class="tab-btn" data-tab="mentorship">Mentorship</button>
                        </div>
                        <div class="tab-pane active" id="tab-mission">
                            <h3 style="font-size: 1.8rem; margin-bottom: 20px;">Engineering with Purpose</h3>
                            <p id="aboutMissionText">My core mission is to develop localized, highly efficient mechanical solutions. This drive was heavily inspired by personal family challenges regarding accessibility, which directly motivated the creation of the <strong>Mahfooz Wheelchair Project</strong>—a localized mobility device with stair-lifting capabilities.</p>
                            <div class="highlight-box">
                                <h4>3D Mech Design</h4>
                                <p style="margin: 0; font-size: 0.95rem;">Founded to provide professional mechanical design consultation. We draft technical proposals, flyers, and operate comprehensive parametric modeling projects for industry clients.</p>
                            </div>
                        </div>
                        <div class="tab-pane" id="tab-methodology">
                            <h3 style="font-size: 1.8rem; margin-bottom: 20px;">The Design Process</h3>
                            <p id="aboutMethodologyText">I strictly adhere to a mathematically validated design process. Whether it is a thermal sand battery or gear assembly, no dimension is arbitrary.</p>
                            <ul style="list-style: none; display: flex; flex-direction: column; gap: 15px; margin-top: 20px;">
                                <li><i class="fas fa-check-circle" style="color: var(--brand-primary); margin-right: 10px;"></i> <strong>Ideation:</strong> Mathematical formulation & sketches.</li>
                                <li><i class="fas fa-check-circle" style="color: var(--brand-primary); margin-right: 10px;"></i> <strong>CAD Phase:</strong> Parametric design in SolidWorks.</li>
                                <li><i class="fas fa-check-circle" style="color: var(--brand-primary); margin-right: 10px;"></i> <strong>Simulation:</strong> Stress testing & CFD validation.</li>
                                <li><i class="fas fa-check-circle" style="color: var(--brand-primary); margin-right: 10px;"></i> <strong>Production:</strong> Final manufacturing schematics.</li>
                            </ul>
                        </div>
                        <div class="tab-pane" id="tab-mentorship">
                            <h3 style="font-size: 1.8rem; margin-bottom: 20px;">Community & Skill Sharing</h3>
                            <p id="aboutMentorshipText">Knowledge isolation hinders engineering progress. I actively log mentorship and skill-sharing activities with junior students and associates.</p>
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
             SECTION 3: EXPERTISE & GEAR CALCULATOR
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
                                <div class="skill-title"><div class="skill-icon"><i class="fas fa-cube"></i></div> <span id="skill1Name">3D CAD &amp; Drafting</span></div>
                                <div class="skill-pct" id="skill1PctDisplay">95%</div>
                            </div>
                            <div class="progress-track"><div class="progress-fill" id="skill1Fill" style="width: 95%;"></div></div>
                            <p style="margin-top: 15px; font-size: 0.9rem; margin-bottom: 0;">SolidWorks, AutoCAD, Fusion 360. Feature trees & technical drawings.</p>
                        </div>
                        <div class="skill-item">
                            <div class="skill-header">
                                <div class="skill-title"><div class="skill-icon"><i class="fas fa-wind"></i></div> <span id="skill2Name">CFD Analysis</span></div>
                                <div class="skill-pct" id="skill2PctDisplay">88%</div>
                            </div>
                            <div class="progress-track"><div class="progress-fill" id="skill2Fill" style="width: 88%;"></div></div>
                            <p style="margin-top: 15px; font-size: 0.9rem; margin-bottom: 0;">Velocity/pressure distributions across fluid flow regimes.</p>
                        </div>
                        <div class="skill-item">
                            <div class="skill-header">
                                <div class="skill-title"><div class="skill-icon"><i class="fas fa-fire-alt"></i></div> <span id="skill3Name">Thermodynamics</span></div>
                                <div class="skill-pct" id="skill3PctDisplay">85%</div>
                            </div>
                            <div class="progress-track"><div class="progress-fill" id="skill3Fill" style="width: 85%;"></div></div>
                            <p style="margin-top: 15px; font-size: 0.9rem; margin-bottom: 0;">Thermal energy storage, sand batteries, and ICE emissions control.</p>
                        </div>
                    </div>
                    <div class="calculator-widget reveal-right">
                        <div class="calc-header">
                            <div class="calc-title"><i class="fas fa-cogs"></i> Involute Gear Toolkit</div>
                            <p style="margin-top: 10px; font-size: 0.9rem; margin-bottom: 0;">Interactive tool demonstrating gear mathematics. <strong>Note:</strong> Δd<sub>r</sub> calculates Pitch Diameter, not root diameter.</p>
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
                            <div class="calc-result-label">Pitch Diameter (Δd<sub>r</sub>)</div>
                            <div class="calc-result-value" id="gearResult">60.00 <span style="font-size: 1rem;">mm</span></div>
                            <div class="calc-note">Formula: Δd<sub>r</sub> = N × m</div>
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
                    <!-- Projects are rendered by JavaScript -->
                </div>
            </div>
        </section>

        <!-- ==================================================================
             SECTION 5: INSIGHTS
             ================================================================== -->
        <section id="insights">
            <div class="container">
                <div class="section-header reveal">
                    <div class="badge">Research & Academia</div>
                    <h2 class="section-title">Engineering <span class="text-gradient">Insights</span></h2>
                </div>
                <div class="insights-grid" id="insightsGrid">
                    <!-- Rendered by JavaScript -->
                </div>
            </div>
        </section>

        <!-- ==================================================================
             SECTION 6: CONTACT
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
                                <p id="contactLocationText">Karachi, Sindh, Pakistan.<br>Available globally via remote consulting.</p>
                            </div>
                        </div>
                        <div class="contact-card">
                            <div class="contact-icon"><i class="fas fa-envelope"></i></div>
                            <div class="contact-details">
                                <h4>Direct Communication</h4>
                                <a href="mailto:consult@3dmechdesign.com" id="contactEmailLink">consult@3dmechdesign.com</a>
                                <p style="margin-top: 5px;">Response within 24 hours.</p>
                            </div>
                        </div>
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
         FOOTER
         ================================================================== -->
    <footer>
        <div class="container">
            <div class="footer-grid">
                <div class="footer-brand">
                    <a href="#" class="logo">
                        <div class="logo-icon"><i class="fas fa-cube"></i></div>
                        <span id="footerBrandName">3D Mech<span>Design</span></span>
                    </a>
                    <p id="footerBioText">Providing cutting-edge parametric design, thermodynamics prototyping, and computational fluid dynamics analysis for modern engineering solutions worldwide.</p>
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
                <p>System Time: PKT <span id="clockDisplay">09:05</span></p>
            </div>
        </div>
    </footer>

    <!-- ==================================================================
         BACK TO TOP BUTTON
         ================================================================== -->
    <button class="back-top" id="backTopBtn" aria-label="Back to top">
        <i class="fas fa-chevron-up"></i>
    </button>

    <!-- ==================================================================
         MODALS (HIDDEN BY DEFAULT)
         ================================================================== -->
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
                    <tr><td>Recognition</td><td>Sindh Higher Education Commission (Startup)</td></tr>
                    <tr><td>Timeline</td><td>2025 - 2026</td></tr>
                    <tr><td>Software Used</td><td>SolidWorks, Ansys</td></tr>
                </table>
            </div>
        </div>
    </div>

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
                    <tr><td>Storage Medium</td><td>High-retention Silica Sand</td></tr>
                    <tr><td>Physical Layout</td><td>Insulated tank, Internal Heat Exchanger Coils</td></tr>
                    <tr><td>Data Tracking</td><td>Instrumentation Sensors</td></tr>
                </table>
            </div>
        </div>
    </div>

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
                    <tr><td>Core Processor</td><td>Arduino Uno</td></tr>
                    <tr><td>Documentation</td><td>Technical report, Wiring Diagrams</td></tr>
                    <tr><td>Software Logic</td><td>Real-time C++ processing code</td></tr>
                </table>
            </div>
        </div>
    </div>

    <!-- ==================================================================
         JAVASCRIPT ENGINE
         ================================================================== -->
    <script>
        document.addEventListener("DOMContentLoaded", () => {

            // ==================================================================
            // 1. DATA STORE (persisted via localStorage)
            // ==================================================================
            const DEFAULT_DATA = {
                profile: {
                    name: "Abdur Rafay Yousuf",
                    title: "Founder, 3D Mech Design",
                    img: "https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?fit=crop&w=600&h=600",
                    bio: "I am Abdur Rafay Yousuf, based in Karachi, Pakistan. I specialize in complex parametric CAD modeling, Computational Fluid Dynamics (CFD), and thermodynamic prototyping for industrial applications.",
                    badge: "Mechanical Design Consultant"
                },
                about: {
                    mission: "My core mission is to develop localized, highly efficient mechanical solutions. This drive was heavily inspired by personal family challenges regarding accessibility, which directly motivated the creation of the Mahfooz Wheelchair Project—a localized mobility device with stair-lifting capabilities.",
                    methodology: "I strictly adhere to a mathematically validated design process. Whether it is a thermal sand battery or gear assembly, no dimension is arbitrary.",
                    mentorship: "Knowledge isolation hinders engineering progress. I actively log mentorship and skill-sharing activities with junior students and associates.",
                    location: "Karachi, Pakistan"
                },
                skills: [
                    { name: "3D CAD & Drafting", pct: 95 },
                    { name: "CFD Analysis", pct: 88 },
                    { name: "Thermodynamics", pct: 85 }
                ],
                contact: {
                    email: "consult@3dmechdesign.com",
                    location: "Karachi, Sindh, Pakistan.\nAvailable globally via remote consulting."
                },
                editorPassword: "admin123",
                projects: [{
                    id: "p1",
                    title: "Mahfooz Wheelchair",
                    category: "mech",
                    catLabel: "Product Design",
                    desc: "A locally producible mobility device engineered with advanced stair-lifting capabilities. Recognized by Sindh HEC.",
                    img: "https://images.unsplash.com/photo-1581092335397-9583eb92d232?fit=crop&w=600&h=400",
                    modalId: "modal-wheelchair",
                    tools: ['fa-solid fa-code', 'fas fa-wheelchair'],
                    specs: [
                        ["Recognition", "Sindh Higher Education Commission (Startup)"],
                        ["Timeline", "2025 - 2026"],
                        ["Software Used", "SolidWorks, Ansys"]
                    ],
                    modalImg: "https://images.unsplash.com/photo-1581092335397-9583eb92d232?fit=crop&w=800&h=400",
                    modalBody: "<p><strong>Inspiration & Overview:</strong> Motivated by severe family mobility limitations, this project aimed to develop a highly localized, cost-effective mobility device equipped with functional stair-lifting mechanisms.</p><p><strong>Engineering Process:</strong> Conducted extensive user surveys to determine ergonomic parameters. The mechanical chassis was developed using parametric modeling in SolidWorks, followed by finite element analysis (FEA) on critical load-bearing joints.</p>"
                }, {
                    id: "p2",
                    title: "Thermal Energy Sand Battery",
                    category: "thermo",
                    catLabel: "Thermodynamics",
                    desc: "Final year design prototype. Insulated silica sand tank with internal heat exchanger coils and instrumentation sensors.",
                    img: "https://images.unsplash.com/photo-1497435334941-8c899ee9e8e9?fit=crop&w=600&h=400",
                    modalId: "modal-battery",
                    tools: ['fas fa-thermometer-half', 'fas fa-cogs'],
                    specs: [
                        ["Storage Medium", "High-retention Silica Sand"],
                        ["Physical Layout", "Insulated tank, Internal Heat Exchanger Coils"],
                        ["Data Tracking", "Instrumentation Sensors"]
                    ],
                    modalImg: "https://images.unsplash.com/photo-1497435334941-8c899ee9e8e9?fit=crop&w=800&h=400",
                    modalBody: "<p><strong>Overview:</strong> A final year design project exploring high-capacity thermal energy storage for industrial applications utilizing silica sand media.</p>"
                }, {
                    id: "p3",
                    title: "Autonomous Line-Follower",
                    category: "robotics",
                    catLabel: "Mechatronics",
                    desc: "Arduino Uno system featuring complex wiring diagrams, sensor loops, and real-time processing code for the Instrumentation Lab.",
                    img: "https://images.unsplash.com/photo-1485827404703-89b55fcc595e?fit=crop&w=600&h=400",
                    modalId: "modal-robot",
                    tools: ['fa-brands fa-usb', 'fas fa-microchip'],
                    specs: [
                        ["Core Processor", "Arduino Uno"],
                        ["Documentation", "Technical report, Wiring Diagrams"],
                        ["Software Logic", "Real-time C++ processing code"]
                    ],
                    modalImg: "https://images.unsplash.com/photo-1485827404703-89b55fcc595e?fit=crop&w=800&h=400",
                    modalBody: "<p><strong>Overview:</strong> A Measurement & Instrumentation Lab project executed in November 2025.</p>"
                }],
                insights: [{
                    title: "Emissions in Internal Combustion Engines",
                    month: "FALL",
                    year: "2025",
                    desc: "A formal engineering document analyzing pollutant formation mechanisms and evaluating modern emission control technologies for industrial IC Engines."
                }, {
                    title: "PSX Portfolio Performance Analysis",
                    month: "JAN",
                    year: "2026",
                    desc: "Executed a transaction log analysis report for Engineering Economics. Transcribed data from Pakistan Stock Exchange to analyze market value fluctuations."
                }]
            };

            // Load data from localStorage or use defaults
            let siteData = {};
            try {
                const stored = localStorage.getItem('portfolio_editor_data');
                if (stored) {
                    const parsed = JSON.parse(stored);
                    // Merge with defaults to ensure all keys exist
                    siteData = JSON.parse(JSON.stringify(DEFAULT_DATA));
                    for (let key in parsed) {
                        if (parsed[key] && typeof parsed[key] === 'object' && !Array.isArray(parsed[key])) {
                            for (let subKey in parsed[key]) {
                                if (parsed[key][subKey] !== undefined) siteData[key][subKey] = parsed[key][subKey];
                            }
                        } else if (Array.isArray(parsed[key])) {
                            siteData[key] = parsed[key];
                        } else {
                            siteData[key] = parsed[key];
                        }
                    }
                } else {
                    siteData = JSON.parse(JSON.stringify(DEFAULT_DATA));
                }
            } catch (e) {
                siteData = JSON.parse(JSON.stringify(DEFAULT_DATA));
            }

            // Helper to persist
            function saveData() {
                localStorage.setItem('portfolio_editor_data', JSON.stringify(siteData));
            }

            // ==================================================================
            // 2. RENDER FUNCTIONS
            // ==================================================================
            function renderProfile() {
                const p = siteData.profile;
                document.getElementById('profileNameDisplay').textContent = p.name;
                document.getElementById('profileTitleDisplay').textContent = p.title;
                document.getElementById('profileImage').src = p.img;
                document.getElementById('heroBioText').textContent = p.bio;
                document.getElementById('heroBadgeText').textContent = p.badge;
                document.getElementById('footerBioText').textContent = p.bio;
                document.getElementById('brandNameDisplay').innerHTML = p.name.split(' ').slice(0, -1).join(' ') + ' <span>' + p
                    .name.split(' ').pop() + '</span>';
                document.getElementById('footerBrandName').innerHTML = p.name.split(' ').slice(0, -1).join(' ') + ' <span>' + p
                    .name.split(' ').pop() + '</span>';
                // Editor fields
                document.getElementById('editName').value = p.name;
                document.getElementById('editTitle').value = p.title;
                document.getElementById('editProfileImg').value = p.img;
                document.getElementById('editBio').value = p.bio;
            }

            function renderAbout() {
                const a = siteData.about;
                document.getElementById('aboutMissionText').innerHTML = a.mission;
                document.getElementById('aboutMethodologyText').textContent = a.methodology;
                document.getElementById('aboutMentorshipText').textContent = a.mentorship;
                document.getElementById('aboutLocationText').textContent = a.location;
                document.getElementById('contactLocationText').innerHTML = siteData.contact.location.replace(/\n/g, '<br>');
                document.getElementById('editMission').value = a.mission;
                document.getElementById('editMethodology').value = a.methodology;
                document.getElementById('editMentorship').value = a.mentorship;
            }

            function renderSkills() {
                const skills = siteData.skills;
                const names = ['skill1Name', 'skill2Name', 'skill3Name'];
                const pcts = ['skill1PctDisplay', 'skill2PctDisplay', 'skill3PctDisplay'];
                const fills = ['skill1Fill', 'skill2Fill', 'skill3Fill'];
                skills.forEach((s, i) => {
                    if (i < 3) {
                        document.getElementById(names[i]).textContent = s.name;
                        document.getElementById(pcts[i]).textContent = s.pct + '%';
                        document.getElementById(fills[i]).style.width = s.pct + '%';
                    }
                });
                // Editor fields
                document.getElementById('editSkill1Name').value = skills[0]?.name || '';
                document.getElementById('editSkill1Pct').value = skills[0]?.pct || 0;
                document.getElementById('editSkill2Name').value = skills[1]?.name || '';
                document.getElementById('editSkill2Pct').value = skills[1]?.pct || 0;
                document.getElementById('editSkill3Name').value = skills[2]?.name || '';
                document.getElementById('editSkill3Pct').value = skills[2]?.pct || 0;
            }

            function renderContact() {
                const c = siteData.contact;
                document.getElementById('contactEmailLink').textContent = c.email;
                document.getElementById('contactEmailLink').href = 'mailto:' + c.email;
                document.getElementById('contactLocationText').innerHTML = c.location.replace(/\n/g, '<br>');
                document.getElementById('editEmail').value = c.email;
                document.getElementById('editLocation').value = c.location;
                document.getElementById('editEditorPassword').value = siteData.editorPassword || 'admin123';
            }

            function renderPortfolio() {
                const grid = document.getElementById('portfolioGrid');
                grid.innerHTML = '';
                siteData.projects.forEach((proj, idx) => {
                    const card = document.createElement('div');
                    card.className = 'portfolio-card glass-panel reveal port-item ' + proj.category;
                    card.dataset.category = proj.category;
                    card.innerHTML = `
                        <div class="port-img-wrap">
                            <img src="${proj.img}" alt="${proj.title}" loading="lazy">
                            <div class="port-overlay">
                                <button class="port-view-btn open-modal" data-target="${proj.modalId}"><i class="fas fa-search-plus"></i></button>
                            </div>
                        </div>
                        <div class="port-content">
                            <span class="port-cat">${proj.catLabel}</span>
                            <h3 class="port-title">${proj.title}</h3>
                            <p class="port-desc">${proj.desc}</p>
                            <div class="port-meta">
                                <div class="port-tool">${proj.tools.map(t => `<i class="${t}"></i>`).join(' ')}</div>
                                <button class="port-meta-link open-modal" data-target="${proj.modalId}">Full Specs <i class="fas fa-arrow-right"></i></button>
                            </div>
                        </div>
                    `;
                    grid.appendChild(card);
                });
                // Reattach modal triggers
                document.querySelectorAll('.open-modal').forEach(el => {
                    el.addEventListener('click', function(e) {
                        e.preventDefault();
                        const target = this.dataset.target;
                        if (target) document.getElementById(target).classList.add('active');
                    });
                });
                // Rebuild modal content from data
                siteData.projects.forEach(proj => {
                    const modal = document.getElementById(proj.modalId);
                    if (modal) {
                        const body = modal.querySelector('.modal-body');
                        if (body) {
                            body.innerHTML = `
                                <img src="${proj.modalImg || proj.img}" alt="${proj.title}" style="width:100%;border-radius:var(--radius-md);margin-bottom:30px;border:1px solid var(--glass-border);">
                                ${proj.modalBody || ''}
                                <table class="spec-table">
                                    ${proj.specs.map(row => `<tr><td>${row[0]}</td><td>${row[1]}</td></tr>`).join('')}
                                </table>
                            `;
                        }
                        const header = modal.querySelector('.modal-header .badge');
                        if (header) header.textContent = proj.catLabel;
                        const title = modal.querySelector('.modal-title');
                        if (title) title.textContent = proj.title;
                    }
                });
            }

            function renderInsights() {
                const grid = document.getElementById('insightsGrid');
                grid.innerHTML = '';
                siteData.insights.forEach(ins => {
                    const card = document.createElement('div');
                    card.className = 'article-card reveal-left';
                    card.innerHTML = `
                        <div class="article-date">
                            <span class="date-month">${ins.month}</span>
                            <span class="date-year">${ins.year}</span>
                        </div>
                        <div class="article-content">
                            <h3>${ins.title}</h3>
                            <p>${ins.desc}</p>
                            <button class="read-more">Read Abstract <i class="fas fa-arrow-right"></i></button>
                        </div>
                    `;
                    grid.appendChild(card);
                });
            }

            function renderAll() {
                renderProfile();
                renderAbout();
                renderSkills();
                renderContact();
                renderPortfolio();
                renderInsights();
                // Update editor project list
                renderEditorProjectList();
            }

            // ==================================================================
            // 3. EDITOR PROJECT LIST
            // ==================================================================
            function renderEditorProjectList() {
                const container = document.getElementById('editorProjectList');
                if (!container) return;
                container.innerHTML = '';
                siteData.projects.forEach((proj, idx) => {
                    const div = document.createElement('div');
                    div.style.cssText =
                        'display:flex;justify-content:space-between;align-items:center;padding:12px 16px;background:var(--bg-base);border-radius:var(--radius-sm);margin-bottom:10px;border:1px solid var(--glass-border);';
                    div.innerHTML = `
                        <span><strong>${proj.title}</strong> <span style="color:var(--text-muted);font-size:0.85rem;">(${proj.catLabel})</span></span>
                        <div style="display:flex;gap:10px;">
                            <button class="btn btn-secondary btn-sm editor-edit-project" data-idx="${idx}" style="padding:6px 14px;font-size:0.8rem;"><i class="fas fa-edit"></i></button>
                            <button class="btn btn-danger btn-sm editor-delete-project" data-idx="${idx}" style="padding:6px 14px;font-size:0.8rem;"><i class="fas fa-trash"></i></button>
                        </div>
                    `;
                    container.appendChild(div);
                });
                // Attach events
                container.querySelectorAll('.editor-edit-project').forEach(btn => {
                    btn.addEventListener('click', function() {
                        const idx = parseInt(this.dataset.idx);
                        editProject(idx);
                    });
                });
                container.querySelectorAll('.editor-delete-project').forEach(btn => {
                    btn.addEventListener('click', function() {
                        const idx = parseInt(this.dataset.idx);
                        if (confirm('Delete project "' + siteData.projects[idx].title + '"?')) {
                            siteData.projects.splice(idx, 1);
                            saveData();
                            renderAll();
                            showToast('Project deleted.', false);
                        }
                    });
                });
            }

            // ==================================================================
            // 4. EDIT PROJECT MODAL (inline prompt)
            // ==================================================================
            function editProject(idx) {
                const proj = siteData.projects[idx];
                if (!proj) return;
                // Simple prompt-based editing (could be expanded)
                const newTitle = prompt('Project Title:', proj.title);
                if (newTitle !== null) proj.title = newTitle || proj.title;
                const newCat = prompt('Category Label (e.g. Product Design):', proj.catLabel);
                if (newCat !== null) proj.catLabel = newCat || proj.catLabel;
                const newDesc = prompt('Description:', proj.desc);
                if (newDesc !== null) proj.desc = newDesc || proj.desc;
                const newImg = prompt('Image URL:', proj.img);
                if (newImg !== null) proj.img = newImg || proj.img;
                saveData();
                renderAll();
                showToast('Project updated!', false);
            }

            // ==================================================================
            // 5. ADD PROJECT
            // ==================================================================
            document.getElementById('editorAddProject')?.addEventListener('click', function() {
                const newProj = {
                    id: 'p' + Date.now(),
                    title: 'New Project',
                    category: 'mech',
                    catLabel: 'Mechanical CAD',
                    desc: 'Describe your project here.',
                    img: 'https://images.unsplash.com/photo-1581092335397-9583eb92d232?fit=crop&w=600&h=400',
                    modalId: 'modal-' + Date.now(),
                    tools: ['fas fa-cube'],
                    specs: [
                        ['Key Feature', 'Description']
                    ],
                    modalImg: 'https://images.unsplash.com/photo-1581092335397-9583eb92d232?fit=crop&w=800&h=400',
                    modalBody: '<p>Project details go here.</p>'
                };
                siteData.projects.push(newProj);
                // Create a new modal element
                const modalDiv = document.createElement('div');
                modalDiv.className = 'modal';
                modalDiv.id = newProj.modalId;
                modalDiv.innerHTML = `
                    <div class="modal-content">
                        <button class="modal-close"><i class="fas fa-times"></i></button>
                        <div class="modal-header">
                            <div class="badge" style="margin-bottom:15px;">${newProj.catLabel}</div>
                            <h2 class="modal-title">${newProj.title}</h2>
                        </div>
                        <div class="modal-body">
                            <img src="${newProj.modalImg}" alt="${newProj.title}" style="width:100%;border-radius:var(--radius-md);margin-bottom:30px;border:1px solid var(--glass-border);">
                            ${newProj.modalBody}
                            <table class="spec-table">
                                ${newProj.specs.map(row => `<tr><td>${row[0]}</td><td>${row[1]}</td></tr>`).join('')}
                            </table>
                        </div>
                    </div>
                `;
                document.body.appendChild(modalDiv);
                // Close button for new modal
                modalDiv.querySelector('.modal-close').addEventListener('click', function() {
                    modalDiv.classList.remove('active');
                });
                saveData();
                renderAll();
                showToast('New project added! Edit it using the editor.', false);
            });

            // ==================================================================
            // 6. TOAST NOTIFICATION
            // ==================================================================
            function showToast(msg, isError = false) {
                const toast = document.getElementById('editorToast');
                const toastMsg = document.getElementById('editorToastMsg');
                toastMsg.textContent = msg;
                toast.className = 'editor-toast' + (isError ? ' error' : '');
                toast.classList.add('show');
                clearTimeout(toast._timeout);
                toast._timeout = setTimeout(() => toast.classList.remove('show'), 3000);
            }

            // ==================================================================
            // 7. EDITOR LOGIN / DASHBOARD
            // ==================================================================
            const lockTrigger = document.getElementById('editorLockTrigger');
            const loginOverlay = document.getElementById('editorLoginOverlay');
            const loginClose = document.getElementById('editorLoginClose');
            const loginBtn = document.getElementById('editorLoginBtn');
            const passwordInput = document.getElementById('editorPassword');
            const dashboard = document.getElementById('editorDashboard');
            const closeDash = document.getElementById('editorCloseDash');

            let editorUnlocked = false;

            function openLogin() {
                loginOverlay.classList.add('active');
                passwordInput.value = '';
                passwordInput.focus();
            }

            function closeLogin() {
                loginOverlay.classList.remove('active');
            }

            function unlockEditor() {
                const entered = passwordInput.value.trim();
                const correct = siteData.editorPassword || 'admin123';
                if (entered === correct) {
                    closeLogin();
                    dashboard.classList.add('active');
                    editorUnlocked = true;
                    // Populate editor fields with current data
                    document.getElementById('editName').value = siteData.profile.name;
                    document.getElementById('editTitle').value = siteData.profile.title;
                    document.getElementById('editProfileImg').value = siteData.profile.img;
                    document.getElementById('editBio').value = siteData.profile.bio;
                    document.getElementById('editMission').value = siteData.about.mission;
                    document.getElementById('editMethodology').value = siteData.about.methodology;
                    document.getElementById('editMentorship').value = siteData.about.mentorship;
                    document.getElementById('editEmail').value = siteData.contact.email;
                    document.getElementById('editLocation').value = siteData.contact.location;
                    document.getElementById('editEditorPassword').value = siteData.editorPassword || 'admin123';
                    if (siteData.skills.length >= 3) {
                        document.getElementById('editSkill1Name').value = siteData.skills[0].name;
                        document.getElementById('editSkill1Pct').value = siteData.skills[0].pct;
                        document.getElementById('editSkill2Name').value = siteData.skills[1].name;
                        document.getElementById('editSkill2Pct').value = siteData.skills[1].pct;
                        document.getElementById('editSkill3Name').value = siteData.skills[2].name;
                        document.getElementById('editSkill3Pct').value = siteData.skills[2].pct;
                    }
                    renderEditorProjectList();
                    showToast('Editor unlocked!', false);
                } else {
                    showToast('Incorrect password.', true);
                    passwordInput.value = '';
                    passwordInput.focus();
                }
            }

            lockTrigger.addEventListener('click', openLogin);
            loginClose.addEventListener('click', closeLogin);
            loginBtn.addEventListener('click', unlockEditor);
            passwordInput.addEventListener('keydown', (e) => {
                if (e.key === 'Enter') unlockEditor();
            });
            loginOverlay.addEventListener('click', (e) => {
                if (e.target === loginOverlay) closeLogin();
            });

            closeDash.addEventListener('click', function() {
                dashboard.classList.remove('active');
                editorUnlocked = false;
                // Re-render to reflect any changes made in editor
                renderAll();
                showToast('Editor closed. Changes applied.', false);
            });

            // ==================================================================
            // 8. SAVE ALL FROM EDITOR
            // ==================================================================
            document.getElementById('editorSaveAll').addEventListener('click', function() {
                // Gather all editor fields
                const name = document.getElementById('editName').value.trim() || siteData.profile.name;
                const title = document.getElementById('editTitle').value.trim() || siteData.profile.title;
                const img = document.getElementById('editProfileImg').value.trim() || siteData.profile.img;
                const bio = document.getElementById('editBio').value.trim() || siteData.profile.bio;

                const mission = document.getElementById('editMission').value.trim() || siteData.about.mission;
                const methodology = document.getElementById('editMethodology').value.trim() || siteData.about
                .methodology;
                const mentorship = document.getElementById('editMentorship').value.trim() || siteData.about
                .mentorship;

                const email = document.getElementById('editEmail').value.trim() || siteData.contact.email;
                const location = document.getElementById('editLocation').value.trim() || siteData.contact.location;
                const editorPass = document.getElementById('editEditorPassword').value.trim() || 'admin123';

                const s1n = document.getElementById('editSkill1Name').value.trim() || '3D CAD & Drafting';
                const s1p = parseInt(document.getElementById('editSkill1Pct').value) || 95;
                const s2n = document.getElementById('editSkill2Name').value.trim() || 'CFD Analysis';
                const s2p = parseInt(document.getElementById('editSkill2Pct').value) || 88;
                const s3n = document.getElementById('editSkill3Name').value.trim() || 'Thermodynamics';
                const s3p = parseInt(document.getElementById('editSkill3Pct').value) || 85;

                // Update data
                siteData.profile.name = name;
                siteData.profile.title = title;
                siteData.profile.img = img;
                siteData.profile.bio = bio;

                siteData.about.mission = mission;
                siteData.about.methodology = methodology;
                siteData.about.mentorship = mentorship;

                siteData.contact.email = email;
                siteData.contact.location = location;
                siteData.editorPassword = editorPass;

                siteData.skills = [
                    { name: s1n, pct: s1p },
                    { name: s2n, pct: s2p },
                    { name: s3n, pct: s3p }
                ];

                saveData();
                renderAll();
                showToast('All changes saved successfully!', false);
            });

            // ==================================================================
            // 9. PREVIEW TOGGLE (close editor to see site)
            // ==================================================================
            document.getElementById('editorPreviewToggle').addEventListener('click', function() {
                dashboard.classList.remove('active');
                editorUnlocked = false;
                renderAll();
                showToast('Preview mode. Click lock icon to re-enter editor.', false);
                // Re-open login overlay as a gate
                setTimeout(() => {
                    // If user wants back in, they click the lock
                }, 100);
            });

            // ==================================================================
            // 10. THEME TOGGLE
            // ==================================================================
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
                initParticles();
            });

            // ==================================================================
            // 11. TYPEWRITER
            // ==================================================================
            const typeText = document.getElementById("typewriter");
            if (typeText) {
                const words = ["Parametric Design.", "CFD Simulation.", "Thermodynamics.", "Gear Mathematics."];
                let wordIndex = 0,
                    charIndex = 0,
                    isDeleting = false;

                function type() {
                    const currentWord = words[wordIndex];
                    if (isDeleting) {
                        typeText.textContent = currentWord.substring(0, charIndex - 1);
                        charIndex--;
                    } else {
                        typeText.textContent = currentWord.substring(0, charIndex + 1);
                        charIndex++;
                    }
                    let speed = isDeleting ? 50 : 100;
                    if (!isDeleting && charIndex === currentWord.length) {
                        speed = 2000;
                        isDeleting = true;
                    } else if (isDeleting && charIndex === 0) {
                        isDeleting = false;
                        wordIndex = (wordIndex + 1) % words.length;
                        speed = 500;
                    }
                    setTimeout(type, speed);
                }
                setTimeout(type, 1500);
            }

            // ==================================================================
            // 12. NAVBAR
            // ==================================================================
            const header = document.getElementById('header');
            const mobileToggle = document.querySelector('.mobile-toggle');
            const navLinks = document.querySelector('.nav-links');
            const navItems = document.querySelectorAll('.nav-link');
            const sections = document.querySelectorAll('section');

            window.addEventListener('scroll', () => {
                if (window.scrollY > 50) header.classList.add('scrolled');
                else header.classList.remove('scrolled');
                let current = '';
                sections.forEach(section => {
                    const sectionTop = section.offsetTop;
                    if (pageYOffset >= sectionTop - 200) current = section.getAttribute('id');
                });
                navItems.forEach(li => {
                    li.classList.remove('active');
                    if (li.getAttribute('href') === `#${current}`) li.classList.add('active');
                });
                // Back to top
                const backBtn = document.getElementById('backTopBtn');
                if (window.scrollY > 400) backBtn.classList.add('visible');
                else backBtn.classList.remove('visible');
            });

            mobileToggle.addEventListener('click', () => {
                navLinks.classList.toggle('nav-active');
                const i = mobileToggle.querySelector('i');
                i.classList.toggle('fa-bars');
                i.classList.toggle('fa-times');
            });

            // ==================================================================
            // 13. TABS
            // ==================================================================
            const tabBtns = document.querySelectorAll('.tab-btn');
            const tabPanes = document.querySelectorAll('.tab-pane');
            tabBtns.forEach(btn => {
                btn.addEventListener('click', () => {
                    const target = btn.getAttribute('data-tab');
                    tabBtns.forEach(b => b.classList.remove('active'));
                    tabPanes.forEach(p => p.classList.remove('active'));
                    btn.classList.add('active');
                    document.getElementById(`tab-${target}`).classList.add('active');
                });
            });

            // ==================================================================
            // 14. GEAR CALCULATOR
            // ==================================================================
            const gearTeethInput = document.getElementById('gearTeeth');
            const gearModuleInput = document.getElementById('gearModule');
            const gearResultDisplay = document.getElementById('gearResult');

            function calculatePitchDiameter() {
                const N = parseFloat(gearTeethInput.value) || 0;
                const m = parseFloat(gearModuleInput.value) || 0;
                const pitchDiameter = (N * m).toFixed(2);
                gearResultDisplay.innerHTML = `${pitchDiameter} <span style="font-size:1rem;">mm</span>`;
            }
            if (gearTeethInput && gearModuleInput) {
                gearTeethInput.addEventListener('input', calculatePitchDiameter);
                gearModuleInput.addEventListener('input', calculatePitchDiameter);
            }

            // ==================================================================
            // 15. PORTFOLIO FILTERS
            // ==================================================================
            const filterBtns = document.querySelectorAll('.portfolio-filters .filter-btn');
            const portItems = () => document.querySelectorAll('.port-item');

            filterBtns.forEach(btn => {
                btn.addEventListener('click', () => {
                    filterBtns.forEach(b => b.classList.remove('active'));
                    btn.classList.add('active');
                    const filter = btn.getAttribute('data-filter');
                    portItems().forEach(item => {
                        item.style.transition = "transform 0.4s ease, opacity 0.4s ease";
                        item.style.opacity = '0';
                        item.style.transform = 'scale(0.9)';
                        setTimeout(() => {
                            if (filter === 'all' || item.dataset.category === filter) {
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

            // ==================================================================
            // 16. MODALS
            // ==================================================================
            document.querySelectorAll('.modal-close').forEach(btn => {
                btn.addEventListener('click', function() {
                    this.closest('.modal').classList.remove('active');
                });
            });
            window.addEventListener('click', (e) => {
                document.querySelectorAll('.modal').forEach(m => {
                    if (e.target === m) m.classList.remove('active');
                });
            });

            // ==================================================================
            // 17. METRICS COUNTER
            // ==================================================================
            const metrics = document.querySelectorAll('.metric-value[data-target]');
            let counted = false;

            function runCounters() {
                metrics.forEach(metric => {
                    const target = +metric.getAttribute('data-target');
                    const count = +metric.innerText.replace(/[^0-9.]/g, '');
                    const inc = target / 80;
                    if (count < target) {
                        metric.innerText = Math.ceil(count + inc);
                        setTimeout(runCounters, 20);
                    } else {
                        metric.innerText = target + '+';
                    }
                });
            }

            // ==================================================================
            // 18. SCROLL REVEAL
            // ==================================================================
            const revealElements = document.querySelectorAll('.reveal, .reveal-left, .reveal-right');
            const observerOptions = { root: null, rootMargin: '0px', threshold: 0.15 };
            const observer = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.classList.add('active');
                        if (entry.target.classList.contains('hero-metrics') && !counted) {
                            runCounters();
                            counted = true;
                        }
                        observer.unobserve(entry.target);
                    }
                });
            }, observerOptions);
            revealElements.forEach(el => observer.observe(el));

            // ==================================================================
            // 19. FORM SUBMISSION
            // ==================================================================
            const form = document.getElementById('contactForm');
            if (form) {
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

            // ==================================================================
            // 20. BACK TO TOP
            // ==================================================================
            document.getElementById('backTopBtn').addEventListener('click', () => {
                window.scrollTo({ top: 0, behavior: 'smooth' });
            });

            // ==================================================================
            // 21. CLOCK
            // ==================================================================
            function updateClock() {
                const now = new Date();
                const h = String(now.getHours()).padStart(2, '0');
                const m = String(now.getMinutes()).padStart(2, '0');
                document.getElementById('clockDisplay').textContent = h + ':' + m;
            }
            updateClock();
            setInterval(updateClock, 30000);

            // ==================================================================
            // 22. PARTICLES
            // ==================================================================
            const canvas = document.getElementById('particle-canvas');
            const ctx = canvas.getContext('2d');
            let particlesArray = [];
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
                    if (this.x > canvas.width || this.x < 0) this.directionX = -this.directionX;
                    if (this.y > canvas.height || this.y < 0) this.directionY = -this.directionY;
                    let dx = mouse.x - this.x;
                    let dy = mouse.y - this.y;
                    let distance = Math.sqrt(dx * dx + dy * dy);
                    if (distance < mouse.radius) {
                        const forceDirectionX = dx / distance;
                        const forceDirectionY = dy / distance;
                        const force = (mouse.radius - distance) / mouse.radius;
                        const directionX = (forceDirectionX * force * this.density);
                        const directionY = (forceDirectionY * force * this.density);
                        this.x -= directionX;
                        this.y -= directionY;
                    } else {
                        if (this.x !== this.baseX) { let dx = this.x - this.baseX;
                            this.x -= dx / 100; }
                        if (this.y !== this.baseY) { let dy = this.y - this.baseY;
                            this.y -= dy / 100; }
                    }
                    this.x += this.directionX;
                    this.y += this.directionY;
                    this.draw();
                }
            }

            function initParticles() {
                particlesArray = [];
                const isDark = document.documentElement.getAttribute("data-theme") === "dark";
                const pColor = isDark ? 'rgba(96, 165, 250, 0.4)' : 'rgba(37, 99, 235, 0.2)';
                const numberOfParticles = Math.min(200, Math.floor((canvas.height * canvas.width) / 12000));
                for (let i = 0; i < numberOfParticles; i++) {
                    let size = (Math.random() * 2) + 1;
                    let x = (Math.random() * ((canvas.width - size * 2) - (size * 2)) + size * 2);
                    let y = (Math.random() * ((canvas.height - size * 2) - (size * 2)) + size * 2);
                    let directionX = (Math.random() * 1.5) - 0.75;
                    let directionY = (Math.random() * 1.5) - 0.75;
                    particlesArray.push(new Particle(x, y, directionX, directionY, size, pColor));
                }
            }

            function animateParticles() {
                requestAnimationFrame(animateParticles);
                ctx.clearRect(0, 0, canvas.width, canvas.height);
                for (let i = 0; i < particlesArray.length; i++) {
                    particlesArray[i].update();
                }
                connectParticles();
            }

            function connectParticles() {
                let opacityValue = 1;
                const maxDist = Math.min(canvas.width, canvas.height) / 6;
                for (let a = 0; a < particlesArray.length; a++) {
                    for (let b = a; b < particlesArray.length; b++) {
                        let distance = ((particlesArray[a].x - particlesArray[b].x) * (particlesArray[a].x - particlesArray[b]
                            .x)) +
                            ((particlesArray[a].y - particlesArray[b].y) * (particlesArray[a].y - particlesArray[b].y));
                        if (distance < maxDist * maxDist) {
                            const isDark = document.documentElement.getAttribute("data-theme") === "dark";
                            opacityValue = 1 - (distance / (maxDist * maxDist));
                            ctx.strokeStyle = isDark ? `rgba(96, 165, 250, ${opacityValue * 0.15})` :
                                `rgba(37, 99, 235, ${opacityValue * 0.15})`;
                            ctx.lineWidth = 1;
                            ctx.beginPath();
                            ctx.moveTo(particlesArray[a].x, particlesArray[a].y);
                            ctx.lineTo(particlesArray[b].x, particlesArray[b].y);
                            ctx.stroke();
                        }
                    }
                }
            }

            resizeCanvas();
            animateParticles();

            // ==================================================================
            // 23. PRELOADER
            // ==================================================================
            const preloader = document.getElementById('preloader');
            setTimeout(() => {
                preloader.classList.add('hidden');
                setTimeout(() => preloader.style.display = 'none', 800);
            }, 1200);

            // ==================================================================
            // 24. INITIAL RENDER
            // ==================================================================
            renderAll();

            // ==================================================================
            // 25. KEYBOARD SHORTCUT: Ctrl+Shift+E to open editor
            // ==================================================================
            document.addEventListener('keydown', (e) => {
                if (e.ctrlKey && e.shiftKey && (e.key === 'E' || e.key === 'e')) {
                    e.preventDefault();
                    if (dashboard.classList.contains('active')) {
                        dashboard.classList.remove('active');
                        editorUnlocked = false;
                        renderAll();
                    } else {
                        openLogin();
                    }
                }
                // Escape to close dashboard
                if (e.key === 'Escape' && dashboard.classList.contains('active')) {
                    dashboard.classList.remove('active');
                    editorUnlocked = false;
                    renderAll();
                }
            });

            console.log('%c🔧 Portfolio Editor Active', 'font-size:16px;font-weight:bold;color:#2563eb;');
            console.log('%cPress Ctrl+Shift+E to open editor.', 'font-size:12px;color:#64748b;');

        }); // end DOMContentLoaded
    </script>

</body>
</html>
