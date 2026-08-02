<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Abdur Rafay Yousuf | Mechanical CAD Engineer</title>

    <!-- Font Awesome 6 -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css" />
    <!-- Google Fonts -->
    <link rel="preconnect" href="https://fonts.googleapis.com" />
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
    <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,300;14..32,400;14..32,500;14..32,600;14..32,700;14..32,800;14..32,900&family=JetBrains+Mono:wght@400;500;600;700&display=swap" rel="stylesheet" />
    <!-- model-viewer for 3D -->
    <script type="module" src="https://ajax.googleapis.com/ajax/libs/model-viewer/4.0.0/model-viewer.min.js"></script>

    <style>
        /* ============================================================
               ROOT VARIABLES — LIGHT & DARK
               ============================================================ */
        :root {
            --primary: #2563EB;
            --primary-dark: #1D4ED8;
            --primary-light: #EFF6FF;
            --primary-glow: rgba(37, 99, 235, 0.25);
            --primary-glow-strong: rgba(37, 99, 235, 0.40);

            --bg-main: #F8FAFC;
            --bg-card: #FFFFFF;
            --bg-alt: #F1F5F9;
            --bg-elevated: #FFFFFF;
            --border-color: #E2E8F0;
            --border-accent: rgba(37, 99, 235, 0.30);

            --text-main: #0F172A;
            --text-muted: #64748B;
            --text-light: #94A3B8;

            --shadow-sm: 0 1px 3px rgba(0, 0, 0, 0.04);
            --shadow-md: 0 4px 24px -6px rgba(15, 23, 42, 0.08);
            --shadow-lg: 0 16px 48px -12px rgba(37, 99, 235, 0.15);
            --shadow-hover: 0 12px 40px -8px rgba(37, 99, 235, 0.20);

            --radius-sm: 8px;
            --radius-md: 16px;
            --radius-lg: 24px;
            --radius-xl: 32px;

            --transition: all 0.30s cubic-bezier(0.4, 0, 0.2, 1);
            --transition-slow: all 0.50s cubic-bezier(0.4, 0, 0.2, 1);

            --font-main: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
            --font-mono: 'JetBrains Mono', monospace;
            --max-width: 1200px;
            --section-padding: 80px 5%;

            --nav-bg: rgba(255, 255, 255, 0.85);
            --nav-border: #E2E8F0;
            --scrollbar-track: #F1F5F9;
            --scrollbar-thumb: #2563EB;

            /* Dark mode overrides (set via .dark-mode class on body) */
            --dm-bg-main: #0F172A;
            --dm-bg-card: #1E293B;
            --dm-bg-alt: #1E293B;
            --dm-border-color: #334155;
            --dm-text-main: #F1F5F9;
            --dm-text-muted: #94A3B8;
            --dm-nav-bg: rgba(15, 23, 42, 0.92);
            --dm-shadow: 0 4px 24px -6px rgba(0, 0, 0, 0.4);
        }

        /* Dark mode class */
        body.dark-mode {
            --bg-main: var(--dm-bg-main);
            --bg-card: var(--dm-bg-card);
            --bg-alt: var(--dm-bg-alt);
            --bg-elevated: var(--dm-bg-card);
            --border-color: var(--dm-border-color);
            --text-main: var(--dm-text-main);
            --text-muted: var(--dm-text-muted);
            --nav-bg: var(--dm-nav-bg);
            --nav-border: var(--dm-border-color);
            --shadow-sm: 0 1px 3px rgba(0, 0, 0, 0.2);
            --shadow-md: 0 4px 24px -6px rgba(0, 0, 0, 0.3);
            --shadow-lg: 0 16px 48px -12px rgba(0, 0, 0, 0.4);
            --shadow-hover: 0 12px 40px -8px rgba(37, 99, 235, 0.25);
            --primary-light: rgba(37, 99, 235, 0.15);
            --border-accent: rgba(37, 99, 235, 0.35);
        }

        body.dark-mode .profile-card,
        body.dark-mode .card,
        body.dark-mode .contact-form,
        body.dark-mode .stat-box,
        body.dark-mode .skill-card,
        body.dark-mode .timeline-content,
        body.dark-mode .testimonial-card,
        body.dark-mode .drawing-item,
        body.dark-mode .project-card {
            background: var(--dm-bg-card);
            border-color: var(--dm-border-color);
        }

        body.dark-mode header {
            background: var(--dm-nav-bg);
            border-color: var(--dm-border-color);
        }

        body.dark-mode .nav-links a {
            color: var(--dm-text-muted);
        }
        body.dark-mode .nav-links a:hover {
            color: var(--primary);
        }

        body.dark-mode .btn-secondary {
            background: var(--dm-bg-card);
            color: var(--dm-text-main);
            border-color: var(--dm-border-color);
        }
        body.dark-mode .btn-secondary:hover {
            border-color: var(--primary);
            color: var(--primary);
            background: var(--primary-light);
        }

        body.dark-mode .filter-btn {
            background: var(--dm-bg-card);
            color: var(--dm-text-muted);
            border-color: var(--dm-border-color);
        }
        body.dark-mode .filter-btn.active,
        body.dark-mode .filter-btn:hover {
            background: var(--primary);
            color: #fff;
            border-color: var(--primary);
        }

        body.dark-mode .form-group input,
        body.dark-mode .form-group textarea {
            background: var(--dm-bg-alt);
            border-color: var(--dm-border-color);
            color: var(--dm-text-main);
        }

        body.dark-mode .social-links a {
            background: var(--dm-bg-card);
            border-color: var(--dm-border-color);
            color: var(--dm-text-muted);
        }
        body.dark-mode .social-links a:hover {
            color: var(--primary);
            border-color: var(--primary);
            background: var(--primary-light);
        }

        body.dark-mode .status-badge {
            background: rgba(5, 150, 105, 0.12);
            border-color: rgba(5, 150, 105, 0.25);
        }

        body.dark-mode .modal-container {
            background: var(--dm-bg-card);
            border-color: var(--dm-border-color);
        }

        body.dark-mode .close-modal {
            color: var(--dm-text-muted);
        }
        body.dark-mode .close-modal:hover {
            color: var(--dm-text-main);
        }

        body.dark-mode .spec-table td {
            border-color: var(--dm-border-color);
        }
        body.dark-mode .spec-table td:last-child {
            color: var(--dm-text-main);
        }

        body.dark-mode .progress-track {
            background: var(--dm-border-color);
        }

        body.dark-mode .tag-sm {
            background: var(--dm-bg-alt);
            color: var(--dm-text-muted);
            border-color: var(--dm-border-color);
        }

        body.dark-mode .tag {
            background: var(--primary-light);
            color: var(--primary);
            border-color: rgba(37, 99, 235, 0.30);
        }

        body.dark-mode .timeline-icon {
            background: var(--dm-bg-card);
            border-color: var(--primary);
            color: var(--primary);
        }

        body.dark-mode .timeline::before {
            background: var(--dm-border-color);
        }

        body.dark-mode .section-tag {
            background: var(--primary-light);
            border-color: rgba(37, 99, 235, 0.30);
            color: var(--primary);
        }

        body.dark-mode .profile-badge {
            background: var(--primary-light);
            border-color: rgba(37, 99, 235, 0.30);
            color: var(--primary);
        }

        body.dark-mode .drawing-overlay {
            background: rgba(15, 23, 42, 0.85);
        }

        body.dark-mode .skill-icon-box {
            background: var(--primary-light);
            border-color: rgba(37, 99, 235, 0.30);
            color: var(--primary);
        }

        /* ============================================================
               RESET & BASE
               ============================================================ */
        *,
        *::before,
        *::after {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        html {
            scroll-behavior: smooth;
            -webkit-font-smoothing: antialiased;
        }

        body {
            background-color: var(--bg-main);
            color: var(--text-main);
            font-family: var(--font-main);
            line-height: 1.6;
            overflow-x: hidden;
            transition: background 0.4s ease, color 0.4s ease;
        }

        /* Subtle Blueprint Grid */
        body::before {
            content: "";
            position: fixed;
            inset: 0;
            z-index: -1;
            pointer-events: none;
            background-image:
                linear-gradient(rgba(37, 99, 235, 0.035) 1px, transparent 1px),
                linear-gradient(90deg, rgba(37, 99, 235, 0.035) 1px, transparent 1px);
            background-size: 40px 40px;
            transition: opacity 0.4s ease;
        }

        /* ============================================================
               SCROLL PROGRESS BAR
               ============================================================ */
        #scrollProgress {
            position: fixed;
            top: 0;
            left: 0;
            width: 0%;
            height: 3px;
            background: linear-gradient(90deg, var(--primary), var(--primary-dark));
            z-index: 9999;
            transition: width 0.1s linear;
            box-shadow: 0 0 12px var(--primary-glow);
        }

        /* ============================================================
               LOADING SCREEN
               ============================================================ */
        #loader {
            position: fixed;
            inset: 0;
            background: var(--bg-main);
            z-index: 99999;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            transition: opacity 0.8s ease, visibility 0.8s ease;
        }
        #loader.hidden {
            opacity: 0;
            visibility: hidden;
            pointer-events: none;
        }
        #loader .loader-icon {
            font-size: 3rem;
            color: var(--primary);
            margin-bottom: 1rem;
            animation: spin 1.2s linear infinite;
        }
        @keyframes spin {
            100% {
                transform: rotate(360deg);
            }
        }
        #loader .loader-text {
            font-family: var(--font-mono);
            font-size: 1.2rem;
            font-weight: 700;
            color: var(--text-main);
            letter-spacing: 0.06em;
        }
        #loader .loader-bar {
            width: 200px;
            height: 3px;
            background: var(--border-color);
            border-radius: 4px;
            margin-top: 1rem;
            overflow: hidden;
        }
        #loader .loader-bar-fill {
            width: 0%;
            height: 100%;
            background: var(--primary);
            border-radius: 4px;
            animation: loadFill 1.4s ease forwards;
        }
        @keyframes loadFill {
            0% {
                width: 0%;
            }
            100% {
                width: 100%;
            }
        }

        /* ============================================================
               CUSTOM CURSOR (optional, subtle)
               ============================================================ */
        .custom-cursor {
            position: fixed;
            width: 32px;
            height: 32px;
            border-radius: 50%;
            border: 2px solid var(--primary);
            pointer-events: none;
            z-index: 9998;
            transition: transform 0.2s ease, width 0.3s ease, height 0.3s ease, background 0.3s ease;
            transform: translate(-50%, -50%);
            opacity: 0;
            background: rgba(37, 99, 235, 0.06);
        }
        .custom-cursor.active {
            opacity: 1;
        }
        .custom-cursor.hover {
            width: 56px;
            height: 56px;
            background: rgba(37, 99, 235, 0.10);
            border-color: var(--primary);
        }
        @media (max-width: 768px) {
            .custom-cursor {
                display: none;
            }
        }

        /* ============================================================
               UTILITY
               ============================================================ */
        .container {
            max-width: var(--max-width);
            margin: 0 auto;
            padding: var(--section-padding);
            position: relative;
            z-index: 1;
        }

        .section-header {
            margin-bottom: 3rem;
        }

        .section-tag {
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
            font-family: var(--font-mono);
            font-size: 0.75rem;
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 0.04em;
            color: var(--primary);
            background: var(--primary-light);
            padding: 0.3rem 0.9rem;
            border-radius: 50px;
            border: 1px solid var(--border-accent);
            margin-bottom: 0.75rem;
        }

        .section-title {
            font-size: 2.5rem;
            font-weight: 800;
            color: var(--text-main);
            letter-spacing: -0.03em;
            line-height: 1.12;
        }

        .section-subtitle {
            color: var(--text-muted);
            font-size: 1.05rem;
            margin-top: 0.5rem;
            max-width: 580px;
        }

        .btn {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            gap: 0.6rem;
            padding: 0.8rem 1.8rem;
            border-radius: 50px;
            font-weight: 600;
            font-size: 0.95rem;
            text-decoration: none;
            cursor: pointer;
            transition: var(--transition);
            border: none;
            font-family: var(--font-main);
            background: transparent;
            color: var(--text-main);
        }

        .btn-primary {
            background: var(--primary);
            color: #fff;
            box-shadow: 0 4px 16px rgba(37, 99, 235, 0.30);
        }
        .btn-primary:hover {
            background: var(--primary-dark);
            transform: translateY(-2px) scale(1.02);
            box-shadow: 0 8px 32px rgba(37, 99, 235, 0.40);
        }

        .btn-secondary {
            background: var(--bg-card);
            color: var(--text-main);
            border: 1px solid var(--border-color);
        }
        .btn-secondary:hover {
            border-color: var(--primary);
            color: var(--primary);
            background: var(--primary-light);
            transform: translateY(-2px);
        }

        .btn-outline-primary {
            border: 1.5px solid var(--primary);
            color: var(--primary);
            background: transparent;
        }
        .btn-outline-primary:hover {
            background: var(--primary);
            color: #fff;
            transform: translateY(-2px);
        }

        .card {
            background: var(--bg-card);
            border: 1px solid var(--border-color);
            border-radius: var(--radius-md);
            box-shadow: var(--shadow-sm);
            transition: var(--transition);
            overflow: hidden;
        }
        .card:hover {
            border-color: var(--border-accent);
            box-shadow: var(--shadow-hover);
            transform: translateY(-4px);
        }

        .reveal {
            opacity: 0;
            transform: translateY(36px);
            transition: opacity 0.7s ease, transform 0.7s ease;
        }
        .reveal.visible {
            opacity: 1;
            transform: translateY(0);
        }

        /* ============================================================
               HEADER / NAV
               ============================================================ */
        header {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            padding: 0 5%;
            height: 72px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            background: var(--nav-bg);
            backdrop-filter: blur(16px);
            -webkit-backdrop-filter: blur(16px);
            z-index: 1000;
            border-bottom: 1px solid var(--nav-border);
            transition: var(--transition);
        }

        .logo {
            font-size: 1.1rem;
            font-weight: 800;
            font-family: var(--font-mono);
            color: var(--text-main);
            text-decoration: none;
            display: flex;
            align-items: center;
            gap: 8px;
        }
        .logo span {
            color: var(--primary);
        }
        .logo i {
            color: var(--primary);
            font-size: 1.2rem;
        }

        .nav-links {
            display: flex;
            gap: 2rem;
            list-style: none;
            align-items: center;
        }
        .nav-links a {
            font-size: 0.85rem;
            font-weight: 500;
            color: var(--text-muted);
            text-decoration: none;
            transition: var(--transition);
            position: relative;
        }
        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: -4px;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--primary);
            transition: var(--transition);
            border-radius: 2px;
        }
        .nav-links a:hover {
            color: var(--primary);
        }
        .nav-links a:hover::after {
            width: 100%;
        }
        .nav-links a.active {
            color: var(--primary);
        }
        .nav-links a.active::after {
            width: 100%;
        }

        .nav-cta {
            background: var(--primary);
            color: #fff !important;
            padding: 0.4rem 1.2rem;
            border-radius: 50px;
            font-weight: 600 !important;
        }
        .nav-cta::after {
            display: none !important;
        }
        .nav-cta:hover {
            background: var(--primary-dark) !important;
            color: #fff !important;
        }

        .menu-toggle {
            display: none;
            font-size: 1.4rem;
            cursor: pointer;
            color: var(--text-main);
            background: none;
            border: none;
        }

        .status-badge {
            display: inline-flex;
            align-items: center;
            gap: 8px;
            font-family: var(--font-mono);
            font-size: 0.7rem;
            font-weight: 600;
            padding: 4px 14px;
            border-radius: 50px;
            background: rgba(5, 150, 105, 0.08);
            border: 1px solid rgba(5, 150, 105, 0.20);
            color: #059669;
            transition: var(--transition);
        }
        .status-dot {
            width: 7px;
            height: 7px;
            background: #059669;
            border-radius: 50%;
            box-shadow: 0 0 8px rgba(5, 150, 105, 0.4);
            animation: pulse-dot 2s infinite;
        }
        @keyframes pulse-dot {
            0%,
            100% {
                opacity: 1;
                transform: scale(1);
            }
            50% {
                opacity: 0.5;
                transform: scale(0.85);
            }
        }

        /* Dark mode toggle in nav */
        .theme-toggle {
            background: none;
            border: none;
            color: var(--text-muted);
            font-size: 1.1rem;
            cursor: pointer;
            transition: var(--transition);
            padding: 4px 8px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
        }
        .theme-toggle:hover {
            color: var(--primary);
            transform: rotate(20deg);
        }

        /* ============================================================
               HERO
               ============================================================ */
        #hero {
            min-height: 100vh;
            padding-top: 100px;
            display: grid;
            grid-template-columns: 1.2fr 0.8fr;
            gap: 3.5rem;
            align-items: center;
            max-width: var(--max-width);
            margin: 0 auto;
            padding-left: 5%;
            padding-right: 5%;
            padding-bottom: 60px;
        }

        .hero-greeting {
            font-family: var(--font-mono);
            color: var(--primary);
            font-weight: 600;
            font-size: 0.9rem;
            margin-bottom: 0.25rem;
            letter-spacing: 0.02em;
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }

        .hero-title {
            font-size: 3.4rem;
            font-weight: 900;
            line-height: 1.08;
            color: var(--text-main);
            letter-spacing: -0.04em;
            margin-bottom: 0.5rem;
        }
        .hero-title .highlight {
            color: var(--primary);
            position: relative;
        }

        .hero-subtitle {
            font-size: 1.2rem;
            font-weight: 600;
            color: var(--primary);
            margin-bottom: 0.75rem;
        }

        .hero-bio {
            color: var(--text-muted);
            font-size: 1.05rem;
            max-width: 540px;
            margin-bottom: 1.5rem;
            line-height: 1.7;
        }

        .hero-social {
            display: flex;
            gap: 0.75rem;
            margin-bottom: 1.25rem;
        }
        .hero-social a {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            background: var(--bg-card);
            border: 1px solid var(--border-color);
            color: var(--text-muted);
            display: flex;
            align-items: center;
            justify-content: center;
            transition: var(--transition);
            text-decoration: none;
            font-size: 0.9rem;
        }
        .hero-social a:hover {
            color: var(--primary);
            border-color: var(--primary);
            background: var(--primary-light);
            transform: translateY(-2px);
        }

        .hero-metrics {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 1rem;
            margin-bottom: 2rem;
            padding-top: 1.25rem;
            border-top: 1px solid var(--border-color);
            max-width: 520px;
        }
        .metric-item {
            text-align: center;
        }
        .metric-item strong {
            display: block;
            font-size: 1.6rem;
            font-weight: 800;
            color: var(--text-main);
            font-family: var(--font-mono);
        }
        .metric-item span {
            font-size: 0.7rem;
            color: var(--text-muted);
            font-weight: 500;
            text-transform: uppercase;
            letter-spacing: 0.03em;
        }

        .hero-btns {
            display: flex;
            gap: 1rem;
            flex-wrap: wrap;
            margin-bottom: 1.5rem;
        }

        /* Client logos row */
        .client-logos {
            display: flex;
            align-items: center;
            gap: 1.75rem;
            flex-wrap: wrap;
            margin-top: 1rem;
            padding-top: 1.25rem;
            border-top: 1px solid var(--border-color);
        }
        .client-logos span {
            font-size: 0.7rem;
            font-weight: 600;
            color: var(--text-muted);
            text-transform: uppercase;
            letter-spacing: 0.06em;
        }
        .client-logos .logo-item {
            font-size: 0.85rem;
            font-weight: 700;
            color: var(--text-muted);
            opacity: 0.7;
            transition: var(--transition);
            font-family: var(--font-mono);
            letter-spacing: 0.02em;
        }
        .client-logos .logo-item:hover {
            opacity: 1;
            color: var(--primary);
        }

        /* Profile Photo Card */
        .hero-image-wrapper {
            display: flex;
            justify-content: center;
            align-items: center;
        }

        .profile-card {
            position: relative;
            padding: 1.5rem;
            background: var(--bg-card);
            border: 1px solid var(--border-color);
            border-radius: var(--radius-lg);
            box-shadow: var(--shadow-lg);
            text-align: center;
            width: 100%;
            max-width: 380px;
            transition: var(--transition);
        }
        .profile-card:hover {
            transform: translateY(-4px);
            box-shadow: var(--shadow-hover);
        }

        .profile-img-wrap {
            width: 220px;
            height: 220px;
            margin: 0 auto 1.25rem auto;
            border-radius: 50%;
            overflow: hidden;
            border: 4px solid #fff;
            box-shadow: 0 0 0 2px var(--primary), var(--shadow-md);
            background: var(--bg-alt);
            position: relative;
        }
        .profile-img-wrap img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            display: block;
        }

        .profile-card h3 {
            font-size: 1.25rem;
            font-weight: 800;
            color: var(--text-main);
        }
        .profile-card .role-tag {
            font-size: 0.8rem;
            color: var(--text-muted);
            font-family: var(--font-mono);
            margin-top: 2px;
        }
        .profile-badge {
            display: inline-flex;
            align-items: center;
            gap: 6px;
            margin-top: 0.75rem;
            padding: 4px 14px;
            background: var(--primary-light);
            border: 1px solid var(--border-accent);
            border-radius: 50px;
            font-size: 0.7rem;
            font-family: var(--font-mono);
            color: var(--primary);
            font-weight: 600;
        }

        /* 3D Model Viewer in hero */
        .hero-3d-wrapper {
            margin-top: 1rem;
            border-radius: var(--radius-md);
            overflow: hidden;
            border: 1px solid var(--border-color);
            background: var(--bg-alt);
            height: 140px;
        }
        .hero-3d-wrapper model-viewer {
            width: 100%;
            height: 140px;
            --poster-color: transparent;
        }

        /* ============================================================
               ABOUT
               ============================================================ */
        #about {
            background: var(--bg-card);
            border-top: 1px solid var(--border-color);
            border-bottom: 1px solid var(--border-color);
        }

        .about-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 3rem;
            align-items: center;
        }

        .about-text p {
            color: var(--text-muted);
            font-size: 1.05rem;
            margin-bottom: 1.25rem;
            line-height: 1.8;
        }
        .about-text p strong {
            color: var(--text-main);
        }

        .about-stats {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 1.25rem;
        }
        .stat-box {
            padding: 1.5rem;
            background: var(--bg-main);
            border-radius: var(--radius-md);
            border: 1px solid var(--border-color);
            text-align: center;
            transition: var(--transition);
        }
        .stat-box:hover {
            border-color: var(--border-accent);
            background: var(--primary-light);
            transform: translateY(-2px);
        }
        .stat-box .number {
            font-size: 2.4rem;
            font-weight: 800;
            color: var(--primary);
            font-family: var(--font-mono);
        }
        .stat-box .label {
            font-size: 0.8rem;
            color: var(--text-muted);
            font-weight: 500;
        }

        /* ============================================================
               SKILLS (with logos)
               ============================================================ */
        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 1.5rem;
        }

        .skill-card {
            padding: 1.75rem;
            display: flex;
            flex-direction: column;
            background: var(--bg-card);
            border: 1px solid var(--border-color);
            border-radius: var(--radius-md);
            transition: var(--transition);
        }
        .skill-card:hover {
            border-color: var(--border-accent);
            box-shadow: var(--shadow-hover);
            transform: translateY(-4px);
        }

        .skill-icon-header {
            display: flex;
            align-items: center;
            gap: 14px;
            margin-bottom: 0.75rem;
        }
        .skill-icon-box {
            width: 48px;
            height: 48px;
            border-radius: var(--radius-sm);
            background: var(--primary-light);
            border: 1px solid var(--border-accent);
            color: var(--primary);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.2rem;
            flex-shrink: 0;
        }
        .skill-title-group h4 {
            font-size: 1rem;
            font-weight: 700;
            color: var(--text-main);
        }
        .skill-title-group span {
            font-size: 0.7rem;
            font-family: var(--font-mono);
            color: var(--primary);
            font-weight: 600;
        }

        .skill-desc {
            font-size: 0.9rem;
            color: var(--text-muted);
            margin-bottom: 1rem;
            flex-grow: 1;
        }

        .progress-track {
            width: 100%;
            height: 6px;
            background: var(--bg-alt);
            border-radius: 10px;
            overflow: hidden;
        }
        .progress-fill {
            height: 100%;
            background: linear-gradient(90deg, var(--primary), var(--primary-dark));
            border-radius: 10px;
            transition: width 1s ease;
        }

        /* Software logos row */
        .skill-logos {
            display: flex;
            gap: 1rem;
            flex-wrap: wrap;
            margin-top: 0.5rem;
        }
        .skill-logos .sw-logo {
            font-size: 0.7rem;
            font-weight: 600;
            padding: 2px 12px;
            border-radius: 50px;
            background: var(--bg-alt);
            border: 1px solid var(--border-color);
            color: var(--text-muted);
            font-family: var(--font-mono);
            transition: var(--transition);
        }
        .skill-logos .sw-logo:hover {
            border-color: var(--primary);
            color: var(--primary);
            background: var(--primary-light);
        }

        /* ============================================================
               ENGINEERING PROCESS
               ============================================================ */
        .process-steps {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(140px, 1fr));
            gap: 1.5rem;
            margin-top: 2rem;
            position: relative;
        }
        .process-step {
            text-align: center;
            padding: 1.5rem 1rem;
            background: var(--bg-card);
            border: 1px solid var(--border-color);
            border-radius: var(--radius-md);
            transition: var(--transition);
            position: relative;
        }
        .process-step:hover {
            border-color: var(--border-accent);
            transform: translateY(-4px);
            box-shadow: var(--shadow-hover);
        }
        .process-step .step-icon {
            font-size: 2rem;
            color: var(--primary);
            margin-bottom: 0.5rem;
            display: block;
        }
        .process-step .step-label {
            font-weight: 700;
            font-size: 0.85rem;
            color: var(--text-main);
        }
        .process-step .step-desc {
            font-size: 0.7rem;
            color: var(--text-muted);
            margin-top: 0.2rem;
        }
        .process-step .step-arrow {
            display: none;
        }
        @media (min-width: 768px) {
            .process-steps {
                grid-template-columns: repeat(6, 1fr);
            }
            .process-step .step-arrow {
                display: block;
                position: absolute;
                right: -0.75rem;
                top: 50%;
                transform: translateY(-50%);
                color: var(--border-color);
                font-size: 1.2rem;
            }
            .process-step:last-child .step-arrow {
                display: none;
            }
        }

        /* ============================================================
               EXPERIENCE (Timeline)
               ============================================================ */
        .timeline {
            position: relative;
            max-width: 820px;
            margin: 0 auto;
        }
        .timeline::before {
            content: "";
            position: absolute;
            top: 0;
            left: 24px;
            height: 100%;
            width: 2px;
            background: var(--border-color);
        }

        .timeline-item {
            position: relative;
            padding-left: 64px;
            margin-bottom: 2.5rem;
        }
        .timeline-item:last-child {
            margin-bottom: 0;
        }

        .timeline-icon {
            position: absolute;
            left: 0;
            top: 0;
            width: 48px;
            height: 48px;
            border-radius: 50%;
            background: var(--bg-card);
            border: 2px solid var(--primary);
            color: var(--primary);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1rem;
            box-shadow: var(--shadow-sm);
            z-index: 1;
        }

        .timeline-content {
            padding: 1.5rem 1.75rem;
            background: var(--bg-card);
            border: 1px solid var(--border-color);
            border-radius: var(--radius-md);
            transition: var(--transition);
        }
        .timeline-content:hover {
            border-color: var(--border-accent);
            box-shadow: var(--shadow-hover);
            transform: translateY(-2px);
        }

        .timeline-header {
            display: flex;
            justify-content: space-between;
            align-items: flex-start;
            flex-wrap: wrap;
            gap: 8px;
            margin-bottom: 0.5rem;
        }
        .timeline-role {
            font-size: 1.1rem;
            font-weight: 800;
            color: var(--text-main);
        }
        .timeline-company {
            color: var(--primary);
            font-weight: 600;
            font-size: 0.9rem;
        }
        .timeline-date {
            font-family: var(--font-mono);
            font-size: 0.75rem;
            padding: 2px 12px;
            background: var(--primary-light);
            color: var(--primary);
            border-radius: 50px;
            font-weight: 600;
            white-space: nowrap;
        }

        .timeline-body p {
            color: var(--text-muted);
            font-size: 0.95rem;
            margin-top: 0.5rem;
        }

        .timeline-tags {
            display: flex;
            gap: 6px;
            flex-wrap: wrap;
            margin-top: 0.75rem;
        }
        .tag-sm {
            font-family: var(--font-mono);
            font-size: 0.65rem;
            padding: 2px 10px;
            background: var(--bg-alt);
            color: var(--text-muted);
            border-radius: 50px;
            border: 1px solid var(--border-color);
            font-weight: 500;
        }

        /* ============================================================
               PROJECTS
               ============================================================ */
        .filter-bar {
            display: flex;
            gap: 10px;
            margin-bottom: 2rem;
            flex-wrap: wrap;
        }
        .filter-btn {
            padding: 6px 18px;
            background: var(--bg-card);
            border: 1px solid var(--border-color);
            color: var(--text-muted);
            border-radius: 50px;
            cursor: pointer;
            font-size: 0.8rem;
            font-weight: 600;
            font-family: var(--font-mono);
            transition: var(--transition);
        }
        .filter-btn.active,
        .filter-btn:hover {
            background: var(--primary);
            color: #fff;
            border-color: var(--primary);
            box-shadow: 0 4px 16px rgba(37, 99, 235, 0.30);
        }

        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(340px, 1fr));
            gap: 2rem;
        }

        .project-card {
            display: flex;
            flex-direction: column;
            overflow: hidden;
            background: var(--bg-card);
            border: 1px solid var(--border-color);
            border-radius: var(--radius-md);
            transition: var(--transition);
        }
        .project-card:hover {
            border-color: var(--border-accent);
            box-shadow: var(--shadow-hover);
            transform: translateY(-6px);
        }

        .project-img {
            width: 100%;
            height: 220px;
            background: var(--bg-alt);
            overflow: hidden;
            position: relative;
        }
        .project-img img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: var(--transition-slow);
        }
        .project-card:hover .project-img img {
            transform: scale(1.06);
        }

        .project-img .project-overlay-badge {
            position: absolute;
            bottom: 12px;
            right: 12px;
            background: rgba(15, 23, 42, 0.75);
            backdrop-filter: blur(8px);
            color: #fff;
            padding: 4px 12px;
            border-radius: 50px;
            font-size: 0.65rem;
            font-weight: 600;
            font-family: var(--font-mono);
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
            flex-wrap: wrap;
            margin-bottom: 0.6rem;
        }
        .tag {
            font-family: var(--font-mono);
            font-size: 0.65rem;
            padding: 2px 10px;
            background: var(--primary-light);
            color: var(--primary);
            border-radius: 50px;
            border: 1px solid var(--border-accent);
            font-weight: 600;
        }

        .project-title {
            font-size: 1.15rem;
            font-weight: 800;
            color: var(--text-main);
            margin-bottom: 0.4rem;
        }
        .project-desc {
            color: var(--text-muted);
            font-size: 0.9rem;
            margin-bottom: 1rem;
            flex-grow: 1;
        }

        .project-meta {
            display: flex;
            gap: 1rem;
            font-size: 0.75rem;
            color: var(--text-muted);
            margin-bottom: 1rem;
            flex-wrap: wrap;
        }
        .project-meta i {
            color: var(--primary);
            width: 16px;
        }

        .project-link {
            color: var(--primary);
            font-weight: 700;
            display: inline-flex;
            align-items: center;
            gap: 8px;
            font-size: 0.85rem;
            cursor: pointer;
            background: none;
            border: none;
            font-family: inherit;
            transition: var(--transition);
            padding: 0;
        }
        .project-link:hover {
            gap: 14px;
            color: var(--primary-dark);
        }

        /* ============================================================
               BEFORE / AFTER SLIDER (simulated with CSS)
               ============================================================ */
        .ba-container {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 2rem;
            margin-top: 2rem;
            align-items: stretch;
        }
        .ba-card {
            background: var(--bg-card);
            border: 1px solid var(--border-color);
            border-radius: var(--radius-md);
            overflow: hidden;
            transition: var(--transition);
            position: relative;
        }
        .ba-card:hover {
            border-color: var(--border-accent);
            box-shadow: var(--shadow-hover);
            transform: translateY(-4px);
        }
        .ba-card .ba-img {
            width: 100%;
            height: 220px;
            object-fit: cover;
            display: block;
        }
        .ba-card .ba-label {
            position: absolute;
            top: 12px;
            left: 12px;
            background: rgba(15, 23, 42, 0.7);
            backdrop-filter: blur(4px);
            color: #fff;
            padding: 2px 14px;
            border-radius: 50px;
            font-size: 0.7rem;
            font-weight: 600;
            font-family: var(--font-mono);
        }
        .ba-card .ba-label.after {
            background: var(--primary);
            color: #fff;
        }
        .ba-card .ba-desc {
            padding: 1rem 1.25rem;
            font-weight: 600;
            font-size: 0.9rem;
            color: var(--text-main);
            text-align: center;
        }

        /* ============================================================
               TESTIMONIALS
               ============================================================ */
        .testimonials-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }

        .testimonial-card {
            padding: 2rem;
            display: flex;
            flex-direction: column;
            background: var(--bg-card);
            border: 1px solid var(--border-color);
            border-radius: var(--radius-md);
            transition: var(--transition);
        }
        .testimonial-card:hover {
            border-color: var(--border-accent);
            box-shadow: var(--shadow-hover);
            transform: translateY(-4px);
        }

        .quote-icon {
            font-size: 1.6rem;
            color: var(--primary);
            opacity: 0.3;
            margin-bottom: 0.75rem;
        }
        .testimonial-text {
            color: var(--text-muted);
            font-size: 0.95rem;
            font-style: italic;
            margin-bottom: 1.5rem;
            flex-grow: 1;
            line-height: 1.7;
        }
        .author-group {
            display: flex;
            align-items: center;
            gap: 12px;
            border-top: 1px solid var(--border-color);
            padding-top: 1rem;
        }
        .author-avatar-img {
            width: 44px;
            height: 44px;
            border-radius: 50%;
            overflow: hidden;
            border: 2px solid var(--border-accent);
            flex-shrink: 0;
            background: var(--bg-alt);
        }
        .author-avatar-img img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }
        .author-details h4 {
            font-size: 0.9rem;
            font-weight: 700;
            color: var(--text-main);
        }
        .author-details span {
            font-size: 0.8rem;
            color: var(--text-muted);
        }

        /* ============================================================
               CONTACT
               ============================================================ */
        #contact {
            background: var(--bg-card);
            border-top: 1px solid var(--border-color);
        }

        .contact-grid {
            display: grid;
            grid-template-columns: 1fr 1.2fr;
            gap: 3.5rem;
        }

        .contact-info p {
            color: var(--text-muted);
            font-size: 1.025rem;
            margin-bottom: 2rem;
            line-height: 1.7;
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
            border-radius: var(--radius-sm);
            background: var(--primary-light);
            border: 1px solid var(--border-accent);
            color: var(--primary);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.1rem;
            flex-shrink: 0;
        }
        .info-item small {
            color: var(--text-muted);
            font-size: 0.75rem;
            font-weight: 500;
        }
        .info-item strong {
            color: var(--text-main);
            font-size: 0.95rem;
        }

        .contact-form {
            padding: 2rem 2.25rem;
            display: flex;
            flex-direction: column;
            gap: 1.25rem;
            background: var(--bg-card);
            border: 1px solid var(--border-color);
            border-radius: var(--radius-md);
        }
        .form-group {
            display: flex;
            flex-direction: column;
            gap: 4px;
        }
        .form-group label {
            font-size: 0.8rem;
            font-weight: 600;
            color: var(--text-main);
        }
        .form-group input,
        .form-group textarea {
            padding: 0.75rem 1rem;
            background: var(--bg-main);
            border: 1px solid var(--border-color);
            border-radius: var(--radius-sm);
            color: var(--text-main);
            font-family: inherit;
            transition: var(--transition);
            font-size: 0.95rem;
        }
        .form-group input:focus,
        .form-group textarea:focus {
            outline: none;
            border-color: var(--primary);
            background: var(--bg-card);
            box-shadow: 0 0 0 3px rgba(37, 99, 235, 0.12);
        }

        /* ============================================================
               FLOATING CONTACT BUTTON
               ============================================================ */
        .float-contact {
            position: fixed;
            bottom: 28px;
            right: 28px;
            z-index: 900;
            background: var(--primary);
            color: #fff;
            width: 56px;
            height: 56px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.4rem;
            box-shadow: 0 4px 24px rgba(37, 99, 235, 0.45);
            cursor: pointer;
            transition: var(--transition);
            text-decoration: none;
            border: none;
        }
        .float-contact:hover {
            transform: scale(1.08) translateY(-4px);
            box-shadow: 0 8px 36px rgba(37, 99, 235, 0.55);
        }
        .float-contact .tooltip {
            position: absolute;
            right: 68px;
            background: var(--bg-card);
            color: var(--text-main);
            padding: 6px 16px;
            border-radius: 50px;
            font-size: 0.75rem;
            font-weight: 600;
            white-space: nowrap;
            box-shadow: var(--shadow-md);
            border: 1px solid var(--border-color);
            opacity: 0;
            pointer-events: none;
            transition: var(--transition);
        }
        .float-contact:hover .tooltip {
            opacity: 1;
        }

        /* ============================================================
               FOOTER
               ============================================================ */
        footer {
            padding: 32px 5%;
            border-top: 1px solid var(--border-color);
            display: flex;
            justify-content: space-between;
            align-items: center;
            color: var(--text-muted);
            font-size: 0.8rem;
            max-width: var(--max-width);
            margin: 0 auto;
            flex-wrap: wrap;
            gap: 1rem;
        }

        .footer-links {
            display: flex;
            gap: 1.5rem;
            align-items: center;
        }
        .footer-links a {
            color: var(--text-muted);
            text-decoration: none;
            font-size: 0.8rem;
            transition: var(--transition);
        }
        .footer-links a:hover {
            color: var(--primary);
        }

        .social-links {
            display: flex;
            gap: 0.75rem;
        }
        .social-links a {
            width: 38px;
            height: 38px;
            border-radius: 50%;
            background: var(--bg-card);
            border: 1px solid var(--border-color);
            color: var(--text-muted);
            display: flex;
            align-items: center;
            justify-content: center;
            transition: var(--transition);
            text-decoration: none;
            font-size: 0.9rem;
        }
        .social-links a:hover {
            color: var(--primary);
            border-color: var(--primary);
            background: var(--primary-light);
            transform: translateY(-2px);
        }

        /* ============================================================
               MODAL
               ============================================================ */
        .modal {
            display: none;
            position: fixed;
            inset: 0;
            background: rgba(15, 23, 42, 0.60);
            backdrop-filter: blur(8px);
            -webkit-backdrop-filter: blur(8px);
            z-index: 2000;
            justify-content: center;
            align-items: center;
            padding: 20px;
        }
        .modal-container {
            max-width: 580px;
            width: 100%;
            padding: 2rem 2.25rem;
            position: relative;
            background: var(--bg-card);
            border: 1px solid var(--border-color);
            border-radius: var(--radius-lg);
            box-shadow: var(--shadow-lg);
            animation: modalIn 0.35s ease;
        }
        @keyframes modalIn {
            from {
                opacity: 0;
                transform: scale(0.95) translateY(24px);
            }
            to {
                opacity: 1;
                transform: scale(1) translateY(0);
            }
        }

        .modal-title {
            font-size: 1.3rem;
            font-weight: 800;
            color: var(--text-main);
            margin-bottom: 1rem;
        }

        .spec-table {
            width: 100%;
            border-collapse: collapse;
            font-family: var(--font-mono);
            font-size: 0.8rem;
            margin: 1rem 0 1.5rem;
        }
        .spec-table td {
            padding: 0.65rem 0.5rem;
            border-bottom: 1px solid var(--border-color);
        }
        .spec-table td:first-child {
            color: var(--text-muted);
            font-weight: 500;
        }
        .spec-table td:last-child {
            color: var(--text-main);
            font-weight: 700;
        }

        .close-modal {
            position: absolute;
            top: 16px;
            right: 20px;
            color: var(--text-muted);
            font-size: 1.6rem;
            cursor: pointer;
            background: none;
            border: none;
            transition: var(--transition);
        }
        .close-modal:hover {
            color: var(--text-main);
            transform: rotate(90deg);
        }

        /* ============================================================
               RESPONSIVE
               ============================================================ */
        @media (max-width: 1024px) {
            #hero {
                grid-template-columns: 1fr 0.9fr;
                gap: 2.5rem;
            }
            .hero-title {
                font-size: 2.8rem;
            }
            .hero-metrics {
                grid-template-columns: repeat(2, 1fr);
            }
        }

        @media (max-width: 992px) {
            .about-grid {
                grid-template-columns: 1fr;
                gap: 2rem;
            }
            .contact-grid {
                grid-template-columns: 1fr;
                gap: 2.5rem;
            }
            .ba-container {
                grid-template-columns: 1fr;
            }
            .process-steps {
                grid-template-columns: repeat(3, 1fr);
            }
            .process-step .step-arrow {
                display: none !important;
            }
        }

        @media (max-width: 768px) {
            .nav-links {
                display: none;
                position: absolute;
                top: 72px;
                left: 0;
                width: 100%;
                background: var(--bg-card);
                flex-direction: column;
                padding: 1.5rem 5%;
                border-bottom: 1px solid var(--border-color);
                box-shadow: var(--shadow-md);
                gap: 1.25rem;
            }
            .nav-links.active {
                display: flex;
            }
            .menu-toggle {
                display: block;
            }

            #hero {
                grid-template-columns: 1fr;
                padding-top: 80px;
                gap: 2rem;
                text-align: center;
            }
            .hero-bio {
                margin-left: auto;
                margin-right: auto;
            }
            .hero-metrics {
                margin-left: auto;
                margin-right: auto;
                grid-template-columns: repeat(2, 1fr);
            }
            .hero-btns {
                justify-content: center;
            }
            .hero-social {
                justify-content: center;
            }
            .hero-image-wrapper {
                order: -1;
            }

            .hero-title {
                font-size: 2.2rem;
            }
            .section-title {
                font-size: 1.8rem;
            }
            .container {
                padding: 60px 5%;
            }

            .projects-grid {
                grid-template-columns: 1fr;
            }
            .skills-grid {
                grid-template-columns: 1fr;
            }
            .profile-card {
                max-width: 300px;
                margin: 0 auto;
            }
            .profile-img-wrap {
                width: 160px;
                height: 160px;
            }

            .timeline::before {
                left: 18px;
            }
            .timeline-item {
                padding-left: 52px;
            }
            .timeline-icon {
                width: 38px;
                height: 38px;
                font-size: 0.8rem;
            }

            footer {
                flex-direction: column;
                text-align: center;
            }
            .footer-links {
                flex-wrap: wrap;
                justify-content: center;
            }

            .status-badge {
                display: none;
            }

            .process-steps {
                grid-template-columns: repeat(2, 1fr);
            }

            .client-logos {
                justify-content: center;
            }

            .float-contact {
                width: 48px;
                height: 48px;
                font-size: 1.1rem;
                bottom: 20px;
                right: 20px;
            }
            .float-contact .tooltip {
                display: none;
            }
        }

        @media (max-width: 480px) {
            .hero-title {
                font-size: 1.8rem;
            }
            .hero-metrics {
                grid-template-columns: 1fr 1fr;
                gap: 0.75rem;
            }
            .contact-form {
                padding: 1.5rem;
            }
            .filter-bar {
                gap: 6px;
            }
            .filter-btn {
                font-size: 0.7rem;
                padding: 4px 12px;
            }
            .section-title {
                font-size: 1.5rem;
            }
            .profile-card {
                max-width: 260px;
                padding: 1rem;
            }
            .profile-img-wrap {
                width: 140px;
                height: 140px;
            }
            .process-steps {
                grid-template-columns: 1fr 1fr;
                gap: 0.75rem;
            }
            .process-step {
                padding: 1rem 0.5rem;
            }
            .process-step .step-icon {
                font-size: 1.5rem;
            }
        }

        /* Scrollbar styling */
        ::-webkit-scrollbar {
            width: 8px;
        }
        ::-webkit-scrollbar-track {
            background: var(--scrollbar-track);
        }
        ::-webkit-scrollbar-thumb {
            background: var(--scrollbar-thumb);
            border-radius: 10px;
        }
        ::-webkit-scrollbar-thumb:hover {
            background: var(--primary-dark);
        }
    </style>
</head>

<body>

    <!-- ============================================================
    LOADING SCREEN
    ============================================================ -->
    <div id="loader">
        <div class="loader-icon"><i class="fa-solid fa-cube"></i></div>
        <div class="loader-text">3D Mech Design</div>
        <div class="loader-bar"><div class="loader-bar-fill"></div></div>
    </div>

    <!-- ============================================================
    SCROLL PROGRESS
    ============================================================ -->
    <div id="scrollProgress"></div>

    <!-- ============================================================
    CUSTOM CURSOR
    ============================================================ -->
    <div class="custom-cursor" id="customCursor"></div>

    <!-- ============================================================
    HEADER
    ============================================================ -->
    <header>
        <a href="#" class="logo">
            <i class="fa-solid fa-cube"></i> ABDUR RAFAY<span>.DESIGNS</span>
        </a>

        <div class="status-badge">
            <span class="status-dot"></span> OPEN FOR CAD CONSULTATION
        </div>

        <div style="display:flex;align-items:center;gap:0.75rem;">
            <button class="theme-toggle" id="themeToggle" aria-label="Toggle dark mode">
                <i class="fa-solid fa-moon"></i>
            </button>
            <button class="menu-toggle" id="menuToggle" aria-label="Toggle navigation">
                <i class="fa-solid fa-bars"></i>
            </button>
        </div>

        <ul class="nav-links" id="navLinks">
            <li><a href="#about">About</a></li>
            <li><a href="#skills">Skills</a></li>
            <li><a href="#experience">Experience</a></li>
            <li><a href="#projects">Portfolio</a></li>
            <li><a href="#testimonials">Reviews</a></li>
            <li><a href="#contact" class="nav-cta">Contact</a></li>
        </ul>
    </header>

    <!-- ============================================================
    HERO
    ============================================================ -->
    <section id="hero">
        <div class="hero-left">
            <div class="hero-greeting">
                <span>👋</span> Mechanical CAD Engineer
            </div>
            <h1 class="hero-title">
                ABDUR RAFAY <br /><span class="highlight">YOUSUF</span>
            </h1>
            <p class="hero-subtitle">
                Product Design · CAD Modeling · FEA · CFD · GD&amp;T
            </p>
            <p class="hero-bio">
                Founder of <strong>3D Mech Design</strong> &amp; Mechanical Engineering Specialist.
                I craft mathematically accurate involute gears, fluid/thermal simulations,
                and lightweight structural assemblies optimized for modern manufacturing.
            </p>

            <div class="hero-social">
                <a href="https://linkedin.com" target="_blank" title="LinkedIn"><i class="fa-brands fa-linkedin-in"></i></a>
                <a href="https://github.com" target="_blank" title="GitHub"><i class="fa-brands fa-github"></i></a>
                <a href="mailto:rafay.yousuf.mech@gmail.com" title="Email"><i class="fa-solid fa-envelope"></i></a>
                <a href="#" title="YouTube"><i class="fa-brands fa-youtube"></i></a>
            </div>

            <div class="hero-metrics">
                <div class="metric-item">
                    <strong data-count="15">0</strong>
                    <span>Projects</span>
                </div>
                <div class="metric-item">
                    <strong data-count="5">0</strong>
                    <span>Industries</span>
                </div>
                <div class="metric-item">
                    <strong data-count="500">0</strong>
                    <span>Engineering Hours</span>
                </div>
                <div class="metric-item">
                    <strong data-count="98">0</strong>
                    <span>Client Satisfaction %</span>
                </div>
            </div>

            <div class="hero-btns">
                <a href="#projects" class="btn btn-primary">
                    <i class="fa-solid fa-layer-group"></i> View Portfolio
                </a>
                <a href="#" class="btn btn-secondary" onclick="alert('📄 Resume download coming soon!')">
                    <i class="fa-solid fa-file-pdf"></i> Download Resume
                </a>
            </div>

            <!-- Client Logos -->
            <div class="client-logos">
                <span>Trusted by</span>
                <span class="logo-item">DHA Suffa</span>
                <span class="logo-item">Nafees Plastics</span>
                <span class="logo-item">ASHRAE</span>
                <span class="logo-item">3D Mech Design</span>
            </div>
        </div>

        <!-- Profile Photo + 3D Viewer -->
        <div class="hero-image-wrapper">
            <div class="profile-card">
                <div class="profile-img-wrap">
                    <img src="https://images.unsplash.com/photo-1534528741775-53994a69daeb?auto=format&fit=crop&w=600&q=80"
                    alt="Abdur Rafay Yousuf - Mechanical CAD Engineer" />
                </div>
                <h3>Abdur Rafay Yousuf</h3>
                <div class="role-tag">Mechanical Design Consultant</div>
                <div class="profile-badge">
                    <i class="fa-solid fa-certificate"></i> SolidWorks &amp; CFD Certified
                </div>

                <!-- 3D Viewer -->
                <div class="hero-3d-wrapper">
                    <model-viewer src="https://modelviewer.dev/shared-assets/models/Astronaut.glb"
                    alt="3D CAD Model"
                    auto-rotate
                    camera-controls
                    disable-zoom
                    exposure="1.0"
                    shadow-intensity="0.2"
                    style="width:100%;height:140px;--poster-color:transparent;">
                </model-viewer>
            </div>
        </div>
    </div>
</section>

<!-- ============================================================
ABOUT
============================================================ -->
<section id="about">
    <div class="container">
        <div class="section-header">
            <div class="section-tag"><i class="fa-regular fa-user"></i> About Me</div>
            <h2 class="section-title">Engineer, Designer &amp; Problem Solver</h2>
            <p class="section-subtitle">Bridging the gap between conceptual design and manufacturable reality.</p>
        </div>

        <div class="about-grid">
            <div class="about-text">
                <p>
                    I'm a <strong>Mechanical CAD Engineer</strong> with a deep passion for precision engineering,
                    computational simulation, and product development. My work focuses on creating
                    <strong>production-ready 3D assemblies</strong> that are not only functionally robust but also
                    optimized for cost-effective manufacturing.
                </p>
                <p>
                    From <strong>involute gear profiles</strong> and <strong>thermal CFD simulations</strong> to
                    <strong>lightweight structural frames</strong>, I bring a blend of mathematical rigor and
                    practical manufacturing insight to every project. I believe great design is invisible — it just works.
                </p>
                <p style="margin-top:1rem;">
                    <span style="display:inline-flex;align-items:center;gap:0.5rem;background:var(--primary-light);padding:0.3rem 1rem;border-radius:50px;font-size:0.85rem;font-weight:600;color:var(--primary);border:1px solid var(--border-accent);">
                        <i class="fa-regular fa-clock"></i> Available for freelance &amp; consulting work
                    </span>
                </p>
            </div>

            <div class="about-stats">
                <div class="stat-box">
                    <div class="number" data-count="15">0</div>
                    <div class="label">CAD Projects Delivered</div>
                </div>
                <div class="stat-box">
                    <div class="number" data-count="5">0</div>
                    <div class="label">Industry Collaborations</div>
                </div>
                <div class="stat-box">
                    <div class="number" data-count="100">0</div>
                    <div class="label">DFM Compliance %</div>
                </div>
                <div class="stat-box">
                    <div class="number" data-count="4.9">0</div>
                    <div class="label">Client Satisfaction ★</div>
                </div>
            </div>
        </div>
    </div>
</section>

<!-- ============================================================
SKILLS
============================================================ -->
<section id="skills">
    <div class="container">
        <div class="section-header">
            <div class="section-tag"><i class="fa-solid fa-gears"></i> Technical Stack</div>
            <h2 class="section-title">Core Engineering Competencies</h2>
            <p class="section-subtitle">Specialized software suites and mechanical design principles applied across every project.</p>
        </div>

        <div class="skills-grid">
            <!-- Skill 1 -->
            <div class="skill-card">
                <div class="skill-icon-header">
                    <div class="skill-icon-box"><i class="fa-solid fa-cube"></i></div>
                    <div class="skill-title-group">
                        <h4>SolidWorks &amp; 3D CAD</h4>
                        <span>Parametric Modeling</span>
                    </div>
                </div>
                <p class="skill-desc">Complex assembly design, motion simulation, parametric feature trees, and sheet metal design.</p>
                <div class="progress-track"><div class="progress-fill" style="width:95%;"></div></div>
                <div class="skill-logos">
                    <span class="sw-logo">SolidWorks</span>
                    <span class="sw-logo">Fusion 360</span>
                </div>
            </div>

            <!-- Skill 2 -->
            <div class="skill-card">
                <div class="skill-icon-header">
                    <div class="skill-icon-box"><i class="fa-solid fa-wind"></i></div>
                    <div class="skill-title-group">
                        <h4>CFD &amp; Thermal Analysis</h4>
                        <span>ANSYS / Flow Simulation</span>
                    </div>
                </div>
                <p class="skill-desc">Internal flow distribution, thermal energy storage modeling, forced convection, and turbulence estimation.</p>
                <div class="progress-track"><div class="progress-fill" style="width:88%;"></div></div>
                <div class="skill-logos">
                    <span class="sw-logo">ANSYS</span>
                    <span class="sw-logo">Flow Simulation</span>
                </div>
            </div>

            <!-- Skill 3 -->
            <div class="skill-card">
                <div class="skill-icon-header">
                    <div class="skill-icon-box"><i class="fa-solid fa-gear"></i></div>
                    <div class="skill-title-group">
                        <h4>Involute Gear Engineering</h4>
                        <span>MATLAB &amp; Custom Arbors</span>
                    </div>
                </div>
                <p class="skill-desc">Mathematical involute tooth profile calculations, diametral pitch analysis, hobbing &amp; inspection arbors.</p>
                <div class="progress-track"><div class="progress-fill" style="width:92%;"></div></div>
                <div class="skill-logos">
                    <span class="sw-logo">MATLAB</span>
                    <span class="sw-logo">AutoCAD</span>
                </div>
            </div>

            <!-- Skill 4 -->
            <div class="skill-card">
                <div class="skill-icon-header">
                    <div class="skill-icon-box"><i class="fa-solid fa-compass-drafting"></i></div>
                    <div class="skill-title-group">
                        <h4>GD&amp;T &amp; Drafting</h4>
                        <span>ASME Y14.5 Standards</span>
                    </div>
                </div>
                <p class="skill-desc">Production drawings with geometric dimensioning and tolerancing, datum reference frames, and BOMs.</p>
                <div class="progress-track"><div class="progress-fill" style="width:90%;"></div></div>
                <div class="skill-logos">
                    <span class="sw-logo">AutoCAD</span>
                    <span class="sw-logo">SolidWorks</span>
                </div>
            </div>

            <!-- Skill 5 -->
            <div class="skill-card">
                <div class="skill-icon-header">
                    <div class="skill-icon-box"><i class="fa-solid fa-microchip"></i></div>
                    <div class="skill-title-group">
                        <h4>FEA &amp; Structural Analysis</h4>
                        <span>ANSYS / SolidWorks Simulation</span>
                    </div>
                </div>
                <p class="skill-desc">Linear static, fatigue, and modal analysis for structural integrity validation under loading conditions.</p>
                <div class="progress-track"><div class="progress-fill" style="width:85%;"></div></div>
                <div class="skill-logos">
                    <span class="sw-logo">ANSYS</span>
                    <span class="sw-logo">SolidWorks</span>
                </div>
            </div>

            <!-- Skill 6 -->
            <div class="skill-card">
                <div class="skill-icon-header">
                    <div class="skill-icon-box"><i class="fa-solid fa-code"></i></div>
                    <div class="skill-title-group">
                        <h4>Engineering Automation</h4>
                        <span>Python / MATLAB Scripting</span>
                    </div>
                </div>
                <p class="skill-desc">Custom scripts for gear geometry generation, data post-processing, and parametric design automation.</p>
                <div class="progress-track"><div class="progress-fill" style="width:78%;"></div></div>
                <div class="skill-logos">
                    <span class="sw-logo">Python</span>
                    <span class="sw-logo">MATLAB</span>
                </div>
            </div>
        </div>
    </div>
</section>

<!-- ============================================================
ENGINEERING PROCESS
============================================================ -->
<section id="process" style="background:var(--bg-card);border-top:1px solid var(--border-color);border-bottom:1px solid var(--border-color);">
    <div class="container">
        <div class="section-header">
            <div class="section-tag"><i class="fa-solid fa-diagram-project"></i> My Process</div>
            <h2 class="section-title">From Idea to Production</h2>
            <p class="section-subtitle">A systematic engineering workflow that ensures quality at every stage.</p>
        </div>

        <div class="process-steps">
            <div class="process-step">
                <span class="step-icon"><i class="fa-regular fa-lightbulb"></i></span>
                <div class="step-label">Idea</div>
                <div class="step-desc">Concept &amp; requirements</div>
                <span class="step-arrow"><i class="fa-solid fa-chevron-right"></i></span>
            </div>
            <div class="process-step">
                <span class="step-icon"><i class="fa-regular fa-pen-to-square"></i></span>
                <div class="step-label">Sketch</div>
                <div class="step-desc">Hand sketches &amp; layout</div>
                <span class="step-arrow"><i class="fa-solid fa-chevron-right"></i></span>
            </div>
            <div class="process-step">
                <span class="step-icon"><i class="fa-solid fa-cube"></i></span>
                <div class="step-label">3D CAD</div>
                <div class="step-desc">Parametric modeling</div>
                <span class="step-arrow"><i class="fa-solid fa-chevron-right"></i></span>
            </div>
            <div class="process-step">
                <span class="step-icon"><i class="fa-solid fa-chart-line"></i></span>
                <div class="step-label">Simulation</div>
                <div class="step-desc">FEA / CFD validation</div>
                <span class="step-arrow"><i class="fa-solid fa-chevron-right"></i></span>
            </div>
            <div class="process-step">
                <span class="step-icon"><i class="fa-solid fa-compass-drafting"></i></span>
                <div class="step-label">Drawing</div>
                <div class="step-desc">GD&amp;T &amp; BOM</div>
                <span class="step-arrow"><i class="fa-solid fa-chevron-right"></i></span>
            </div>
            <div class="process-step">
                <span class="step-icon"><i class="fa-solid fa-industry"></i></span>
                <div class="step-label">Production</div>
                <div class="step-desc">Manufacturing handoff</div>
            </div>
        </div>
    </div>
</section>

<!-- ============================================================
EXPERIENCE
============================================================ -->
<section id="experience">
    <div class="container">
        <div class="section-header">
            <div class="section-tag"><i class="fa-solid fa-briefcase"></i> Track Record</div>
            <h2 class="section-title">Work Experience &amp; R&amp;D Milestones</h2>
            <p class="section-subtitle">Engineering roles, consulting projects, and industrial prototype developments.</p>
        </div>

        <div class="timeline">
            <!-- Item 1 -->
            <div class="timeline-item">
                <div class="timeline-icon"><i class="fa-solid fa-building"></i></div>
                <div class="timeline-content">
                    <div class="timeline-header">
                        <div>
                            <div class="timeline-role">Founder &amp; Principal Design Engineer</div>
                            <div class="timeline-company">3D Mech Design • Consultancy</div>
                        </div>
                        <span class="timeline-date">2025 – Present</span>
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

            <!-- Item 2 -->
            <div class="timeline-item">
                <div class="timeline-icon"><i class="fa-solid fa-wheelchair"></i></div>
                <div class="timeline-content">
                    <div class="timeline-header">
                        <div>
                            <div class="timeline-role">Lead Mechanical Engineer (FYDP)</div>
                            <div class="timeline-company">Mahfooz Stair-Lifting Mobility Project</div>
                        </div>
                        <span class="timeline-date">2025 – 2026</span>
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

            <!-- Item 3 -->
            <div class="timeline-item">
                <div class="timeline-icon"><i class="fa-solid fa-fire-flame-curved"></i></div>
                <div class="timeline-content">
                    <div class="timeline-header">
                        <div>
                            <div class="timeline-role">Thermal Systems Research Engineer</div>
                            <div class="timeline-company">Thermal Energy Storage Sand Battery</div>
                        </div>
                        <span class="timeline-date">2025 – 2026</span>
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
    </div>
</section>

<!-- ============================================================
PROJECTS
============================================================ -->
<section id="projects" style="background:var(--bg-card);border-top:1px solid var(--border-color);border-bottom:1px solid var(--border-color);">
    <div class="container">
        <div class="section-header">
            <div class="section-tag"><i class="fa-solid fa-folder-open"></i> Portfolio</div>
            <h2 class="section-title">Featured CAD &amp; Engineering Projects</h2>
            <p class="section-subtitle">Explore selected mechanical assemblies, thermal CFD models, and manufacturing drawings.</p>
        </div>

        <div class="filter-bar">
            <button class="filter-btn active" data-filter="all">All Work</button>
            <button class="filter-btn" data-filter="mobility">Mobility Systems</button>
            <button class="filter-btn" data-filter="thermal">Thermal &amp; CFD</button>
            <button class="filter-btn" data-filter="gears">Precision Gears</button>
            <button class="filter-btn" data-filter="research">Research</button>
        </div>

        <div class="projects-grid" id="projectsGrid">
            <!-- Project 1 -->
            <div class="project-card" data-category="mobility">
                <div class="project-img">
                    <img src="https://images.unsplash.com/photo-1581092160607-ee22621dd758?auto=format&fit=crop&w=600&q=80" alt="Stair-Lifting Assistive Mechanism" loading="lazy" />
                    <span class="project-overlay-badge"><i class="fa-regular fa-clock"></i> 6 months</span>
                </div>
                <div class="project-content">
                    <div class="project-tags">
                        <span class="tag">SolidWorks</span>
                        <span class="tag">Kinematics</span>
                        <span class="tag">FEA</span>
                    </div>
                    <h3 class="project-title">Stair-Ascending Mobility Chassis</h3>
                    <p class="project-desc">Locally manufacturable stair-lifting mechanism with custom high-torque gearing and FEA load factor validation.</p>
                    <div class="project-meta">
                        <span><i class="fa-regular fa-building"></i> DHA Suffa</span>
                        <span><i class="fa-regular fa-calendar"></i> 2025</span>
                    </div>
                    <button class="project-link" onclick="openSpecModal('Stair-Ascending Mobility Chassis', 'AL 6061-T6 Frame', '3.2 FEA Safety Factor', 'SolidWorks / Motion Study', '±0.05 mm')">
                        View Specs <i class="fa-solid fa-arrow-right"></i>
                    </button>
                </div>
            </div>

            <!-- Project 2 -->
            <div class="project-card" data-category="thermal">
                <div class="project-img">
                    <img src="https://images.unsplash.com/photo-1531403009284-440f080d1e12?auto=format&fit=crop&w=600&q=80" alt="Sand Battery Thermal Vessel" loading="lazy" />
                    <span class="project-overlay-badge"><i class="fa-regular fa-clock"></i> 4 months</span>
                </div>
                <div class="project-content">
                    <div class="project-tags">
                        <span class="tag">CFD</span>
                        <span class="tag">Heat Transfer</span>
                        <span class="tag">Thermal Storage</span>
                    </div>
                    <h3 class="project-title">Sand Thermal Energy Battery</h3>
                    <p class="project-desc">High-temperature silica sand energy storage unit equipped with internal heat exchanger coil flow contours.</p>
                    <div class="project-meta">
                        <span><i class="fa-regular fa-building"></i> Research Project</span>
                        <span><i class="fa-regular fa-calendar"></i> 2025</span>
                    </div>
                    <button class="project-link" onclick="openSpecModal('Sand Thermal Energy Battery', 'Insulated Mild Steel + Silica Sand', 'Flow &amp; Heat Transfer Simulation', 'CFD / ANSYS', 'Sealed Thermal Fit')">
                        View Specs <i class="fa-solid fa-arrow-right"></i>
                    </button>
                </div>
            </div>

            <!-- Project 3 -->
            <div class="project-card" data-category="gears">
                <div class="project-img">
                    <img src="https://images.unsplash.com/photo-1581092580497-e0d23cbdf1dc?auto=format&fit=crop&w=600&q=80" alt="Involute Inspection Arbor" loading="lazy" />
                    <span class="project-overlay-badge"><i class="fa-regular fa-clock"></i> 3 months</span>
                </div>
                <div class="project-content">
                    <div class="project-tags">
                        <span class="tag">Involute Gear</span>
                        <span class="tag">MATLAB</span>
                        <span class="tag">GD&amp;T</span>
                    </div>
                    <h3 class="project-title">Involute Gear Hobbing Arbor</h3>
                    <p class="project-desc">Custom arbor engineered with exact mathematical pitch diameter scripts and tight tolerance GD&amp;T callouts.</p>
                    <div class="project-meta">
                        <span><i class="fa-regular fa-building"></i> Industrial Client</span>
                        <span><i class="fa-regular fa-calendar"></i> 2025</span>
                    </div>
                    <button class="project-link" onclick="openSpecModal('Involute Gear Hobbing Arbor', 'Tool Steel (HRC 58-60)', 'Pitch Dia Profile Scripts', 'MATLAB / AutoCAD', '±0.01 mm')">
                        View Specs <i class="fa-solid fa-arrow-right"></i>
                    </button>
                </div>
            </div>
        </div>

        <!-- Before / After Slider -->
        <div style="margin-top:4rem;">
            <h3 style="font-size:1.3rem;font-weight:800;color:var(--text-main);margin-bottom:1rem;display:flex;align-items:center;gap:0.75rem;">
                <i class="fa-regular fa-images" style="color:var(--primary);"></i>
                Before &amp; After — Design Evolution
            </h3>
            <div class="ba-container">
                <div class="ba-card">
                    <span class="ba-label">Initial Sketch</span>
                    <img class="ba-img" src="https://images.unsplash.com/photo-1581092335397-9583fe92d232?auto=format&fit=crop&w=600&q=80" alt="Initial sketch" loading="lazy" />
                    <div class="ba-desc">Concept sketch &amp; rough layout</div>
                </div>
                <div class="ba-card">
                    <span class="ba-label after">Finished CAD</span>
                    <img class="ba-img" src="https://images.unsplash.com/photo-1581091226825-a6a2a5aee158?auto=format&fit=crop&w=600&q=80" alt="Finished CAD model" loading="lazy" />
                    <div class="ba-desc">Production-ready 3D assembly with GD&amp;T</div>
                </div>
            </div>
        </div>
    </div>
</section>

<!-- ============================================================
TESTIMONIALS
============================================================ -->
<section id="testimonials">
    <div class="container">
        <div class="section-header">
            <div class="section-tag"><i class="fa-solid fa-comment-dots"></i> Endorsements</div>
            <h2 class="section-title">Client &amp; Academic Feedback</h2>
            <p class="section-subtitle">What faculty mentors and consulting clients say about my work quality.</p>
        </div>

        <div class="testimonials-grid">
            <div class="testimonial-card">
                <i class="fa-solid fa-quote-left quote-icon"></i>
                <p class="testimonial-text">"Rafay delivered flawless DFM-ready CAD drawings for our mechanical assembly. His attention to geometric tolerances saved us significant re-machining costs."</p>
                <div class="author-group">
                    <div class="author-avatar-img">
                        <img src="https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?auto=format&fit=crop&w=100&q=80" alt="Client" loading="lazy" />
                    </div>
                    <div class="author-details">
                        <h4>Industrial Design Client</h4>
                        <span>3D Mech Design Client</span>
                    </div>
                </div>
            </div>

            <div class="testimonial-card">
                <i class="fa-solid fa-quote-left quote-icon"></i>
                <p class="testimonial-text">"His work on the Thermal Energy Storage sand battery prototype showed deep understanding of both fluid flow CFD and solid modeling."</p>
                <div class="author-group">
                    <div class="author-avatar-img">
                        <img src="https://images.unsplash.com/photo-1500648767791-00dcc994a43e?auto=format&fit=crop&w=100&q=80" alt="Professor" loading="lazy" />
                    </div>
                    <div class="author-details">
                        <h4>Senior Faculty Advisor</h4>
                        <span>DHA Suffa University</span>
                    </div>
                </div>
            </div>
        </div>
    </div>
</section>

<!-- ============================================================
CONTACT
============================================================ -->
<section id="contact">
    <div class="container">
        <div class="section-header">
            <div class="section-tag"><i class="fa-solid fa-paper-plane"></i> Get In Touch</div>
            <h2 class="section-title">Let's Discuss Your CAD Project</h2>
            <p class="section-subtitle">Have a mechanical design requirement, gear calculation task, or CFD simulation need? Reach out today.</p>
        </div>

        <div class="contact-grid">
            <div class="contact-info">
                <p>
                    Available for freelance CAD design, mechanical engineering consultations,
                    and full 3D assembly modeling projects. I respond within <strong>24 hours</strong>.
                </p>

                <div class="info-list">
                    <div class="info-item">
                        <div class="info-icon"><i class="fa-solid fa-envelope"></i></div>
                        <div>
                            <small>Email</small>
                            <div><strong>rafay.yousuf.mech@gmail.com</strong></div>
                        </div>
                    </div>
                    <div class="info-item">
                        <div class="info-icon"><i class="fa-brands fa-linkedin-in"></i></div>
                        <div>
                            <small>LinkedIn</small>
                            <div><strong>linkedin.com/in/abdur-rafay</strong></div>
                        </div>
                    </div>
                    <div class="info-item">
                        <div class="info-icon"><i class="fa-brands fa-github"></i></div>
                        <div>
                            <small>GitHub</small>
                            <div><strong>github.com/rafay-mech</strong></div>
                        </div>
                    </div>
                    <div class="info-item">
                        <div class="info-icon"><i class="fa-brands fa-youtube"></i></div>
                        <div>
                            <small>YouTube</small>
                            <div><strong>youtube.com/@3dmechdesign</strong></div>
                        </div>
                    </div>
                    <div class="info-item">
                        <div class="info-icon"><i class="fa-solid fa-location-dot"></i></div>
                        <div>
                            <small>Location</small>
                            <div><strong>Karachi, Pakistan / Remote Worldwide</strong></div>
                        </div>
                    </div>
                </div>

                <div style="display:flex;gap:0.75rem;flex-wrap:wrap;">
                    <span style="font-size:0.7rem;font-weight:600;color:var(--text-muted);background:var(--bg-alt);padding:0.2rem 0.8rem;border-radius:50px;border:1px solid var(--border-color);">
                        <i class="fa-regular fa-clock"></i> Replies within 24h
                    </span>
                    <span style="font-size:0.7rem;font-weight:600;color:var(--text-muted);background:var(--bg-alt);padding:0.2rem 0.8rem;border-radius:50px;border:1px solid var(--border-color);">
                        <i class="fa-regular fa-calendar"></i> Available now
                    </span>
                </div>
            </div>

            <form class="contact-form" onsubmit="event.preventDefault(); alert('✅ Thank you! Your message has been sent successfully. I\'ll get back to you within 24 hours.');">
                <div class="form-group">
                    <label for="name">Your Name / Organization</label>
                    <input type="text" id="name" placeholder="e.g. John Doe" required />
                </div>
                <div class="form-group">
                    <label for="email">Your Email Address</label>
                    <input type="email" id="email" placeholder="john@example.com" required />
                </div>
                <div class="form-group">
                    <label for="message">Project Requirements</label>
                    <textarea id="message" rows="4" placeholder="Describe your CAD modeling, gear calculation, or CFD needs..." required></textarea>
                </div>
                <button type="submit" class="btn btn-primary">
                    <i class="fa-solid fa-paper-plane"></i> Send Specifications
                </button>
            </form>
        </div>
    </div>
</section>

<!-- ============================================================
FLOATING CONTACT BUTTON
============================================================ -->
<a href="#contact" class="float-contact" aria-label="Contact">
    <i class="fa-regular fa-comment-dots"></i>
    <span class="tooltip">Let's Talk</span>
</a>

<!-- ============================================================
FOOTER
============================================================ -->
<footer>
    <div>&copy; 2026 Abdur Rafay Yousuf • 3D Mech Design. All rights reserved.</div>
    <div class="footer-links">
        <a href="#about">About</a>
        <a href="#projects">Portfolio</a>
        <a href="#contact">Contact</a>
        <a href="#" onclick="alert('📄 Resume download coming soon!')">Resume</a>
    </div>
    <div class="social-links">
        <a href="https://github.com" target="_blank" title="GitHub"><i class="fa-brands fa-github"></i></a>
        <a href="https://linkedin.com" target="_blank" title="LinkedIn"><i class="fa-brands fa-linkedin-in"></i></a>
        <a href="mailto:rafay.yousuf.mech@gmail.com" title="Email"><i class="fa-solid fa-envelope"></i></a>
        <a href="#" target="_blank" title="YouTube"><i class="fa-brands fa-youtube"></i></a>
    </div>
</footer>

<!-- ============================================================
MODAL
============================================================ -->
<div class="modal" id="specModal">
    <div class="modal-container">
        <button class="close-modal" onclick="closeSpecModal()">&times;</button>
        <h3 class="modal-title" id="mTitle">Project Specifications</h3>
        <table class="spec-table">
            <tr><td>Material Specification:</td><td id="mMat">AL 6061-T6</td></tr>
            <tr><td>Stress &amp; FEA Status:</td><td id="mAnalysis">Passed DFM Verification</td></tr>
            <tr><td>Software Stack:</td><td id="mStack">SolidWorks / ANSYS</td></tr>
            <tr><td>Machining Tolerance:</td><td id="mTol">±0.02 mm</td></tr>
        </table>
        <button class="btn btn-secondary" onclick="closeSpecModal()" style="width:100%;">Close Spec Sheet</button>
    </div>
</div>

<!-- ============================================================
JAVASCRIPT
============================================================ -->
<script>
    // ============================================================
    // LOADER
    // ============================================================
    window.addEventListener('load', () => {
        setTimeout(() => {
            document.getElementById('loader').classList.add('hidden');
        }, 1600);
    });

    // ============================================================
    // SCROLL PROGRESS
    // ============================================================
    const progressBar = document.getElementById('scrollProgress');
    window.addEventListener('scroll', () => {
        const scrollTop = window.scrollY;
        const docHeight = document.documentElement.scrollHeight - window.innerHeight;
        const progress = docHeight > 0 ? (scrollTop / docHeight) * 100 : 0;
        progressBar.style.width = progress + '%';
    });

    // ============================================================
    // CUSTOM CURSOR
    // ============================================================
    const cursor = document.getElementById('customCursor');
    let cursorActive = false;

    if (window.innerWidth > 768) {
        cursorActive = true;
        cursor.classList.add('active');

        document.addEventListener('mousemove', (e) => {
            cursor.style.left = e.clientX + 'px';
            cursor.style.top = e.clientY + 'px';
        });

        document.querySelectorAll('a, button, .btn, .project-card, .filter-btn, .skill-card, .timeline-content, .testimonial-card')
            .forEach(el => {
                el.addEventListener('mouseenter', () => cursor.classList.add('hover'));
                el.addEventListener('mouseleave', () => cursor.classList.remove('hover'));
            });
    }

    // ============================================================
    // DARK MODE
    // ============================================================
    const themeToggle = document.getElementById('themeToggle');
    const themeIcon = themeToggle.querySelector('i');

    // Check saved preference
    if (localStorage.getItem('theme') === 'dark') {
        document.body.classList.add('dark-mode');
        themeIcon.className = 'fa-solid fa-sun';
    }

    themeToggle.addEventListener('click', () => {
        document.body.classList.toggle('dark-mode');
        const isDark = document.body.classList.contains('dark-mode');
        themeIcon.className = isDark ? 'fa-solid fa-sun' : 'fa-solid fa-moon';
        localStorage.setItem('theme', isDark ? 'dark' : 'light');
    });

    // ============================================================
    // MOBILE MENU
    // ============================================================
    const menuToggle = document.getElementById('menuToggle');
    const navLinks = document.getElementById('navLinks');

    menuToggle.addEventListener('click', () => {
        navLinks.classList.toggle('active');
    });

    document.querySelectorAll('.nav-links a').forEach(link => {
        link.addEventListener('click', () => navLinks.classList.remove('active'));
    });

    // ============================================================
    // ACTIVE NAV LINK ON SCROLL
    // ============================================================
    const sections = document.querySelectorAll('section[id]');
    const navAnchors = document.querySelectorAll('.nav-links a:not(.nav-cta)');

    window.addEventListener('scroll', () => {
        let current = '';
        sections.forEach(section => {
            const sectionTop = section.offsetTop - 120;
            if (window.scrollY >= sectionTop) {
                current = section.getAttribute('id');
            }
        });
        navAnchors.forEach(anchor => {
            anchor.classList.remove('active');
            if (anchor.getAttribute('href') === '#' + current) {
                anchor.classList.add('active');
            }
        });
    });

    // ============================================================
    // PROJECT FILTER WITH ANIMATION
    // ============================================================
    const filterBtns = document.querySelectorAll('.filter-btn');
    const projectCards = document.querySelectorAll('.project-card');

    filterBtns.forEach(btn => {
        btn.addEventListener('click', () => {
            filterBtns.forEach(b => b.classList.remove('active'));
            btn.classList.add('active');

            const filter = btn.getAttribute('data-filter');

            projectCards.forEach((card, index) => {
                const category = card.getAttribute('data-category');
                const match = filter === 'all' || category === filter;

                if (match) {
                    card.style.display = 'flex';
                    card.style.opacity = '0';
                    card.style.transform = 'translateY(20px)';
                    setTimeout(() => {
                        card.style.transition = 'opacity 0.4s ease, transform 0.4s ease';
                        card.style.opacity = '1';
                        card.style.transform = 'translateY(0)';
                    }, 50 + index * 80);
                } else {
                    card.style.display = 'none';
                }
            });
        });
    });

    // ============================================================
    // SPEC MODAL
    // ============================================================
    const specModal = document.getElementById('specModal');

    function openSpecModal(title, mat, analysis, stack, tol) {
        document.getElementById('mTitle').textContent = title;
        document.getElementById('mMat').textContent = mat;
        document.getElementById('mAnalysis').textContent = analysis;
        document.getElementById('mStack').textContent = stack;
        document.getElementById('mTol').textContent = tol;
        specModal.style.display = 'flex';
        document.body.style.overflow = 'hidden';
    }

    function closeSpecModal() {
        specModal.style.display = 'none';
        document.body.style.overflow = '';
    }

    document.addEventListener('keydown', (e) => {
        if (e.key === 'Escape') closeSpecModal();
    });

    specModal.addEventListener('click', (e) => {
        if (e.target === specModal) closeSpecModal();
    });

    // ============================================================
    // SCROLL REVEAL
    // ============================================================
    const revealObserver = new IntersectionObserver((entries) => {
        entries.forEach(entry => {
            if (entry.isIntersecting) {
                entry.target.classList.add('visible');
            }
        });
    }, { threshold: 0.10, rootMargin: '0px 0px -40px 0px' });

    document.querySelectorAll(
        '.skill-card, .timeline-item, .project-card, .testimonial-card, .stat-box, .process-step, .ba-card, .drawing-item, .section-header'
    ).forEach(el => {
        el.classList.add('reveal');
        revealObserver.observe(el);
    });

    // ============================================================
    // ANIMATED COUNTERS
    // ============================================================
    function animateCounters() {
        const counters = document.querySelectorAll('[data-count]');
        counters.forEach(counter => {
            const target = parseFloat(counter.getAttribute('data-count'));
            const isFloat = target % 1 !== 0;
            const duration = 1800;
            const startTime = performance.now();

            function updateCounter(currentTime) {
                const elapsed = currentTime - startTime;
                const progress = Math.min(elapsed / duration, 1);
                const eased = 1 - Math.pow(1 - progress, 3);
                const current = eased * target;

                if (isFloat) {
                    counter.textContent = current.toFixed(1);
                } else {
                    counter.textContent = Math.floor(current);
                }

                if (progress < 1) {
                    requestAnimationFrame(updateCounter);
                } else {
                    if (isFloat) {
                        counter.textContent = target.toFixed(1);
                    } else {
                        counter.textContent = target;
                    }
                }
            }
            requestAnimationFrame(updateCounter);
        });
    }

    // Trigger counters when about section is visible
    const aboutSection = document.querySelector('#about');
    let countersAnimated = false;

    const counterObserver = new IntersectionObserver((entries) => {
        entries.forEach(entry => {
            if (entry.isIntersecting && !countersAnimated) {
                countersAnimated = true;
                animateCounters();
            }
        });
    }, { threshold: 0.30 });

    if (aboutSection) counterObserver.observe(aboutSection);

    // Also animate hero metrics when visible
    const heroMetrics = document.querySelector('.hero-metrics');
    let heroCountersAnimated = false;

    const heroCounterObserver = new IntersectionObserver((entries) => {
        entries.forEach(entry => {
            if (entry.isIntersecting && !heroCountersAnimated) {
                heroCountersAnimated = true;
                const heroCounters = document.querySelectorAll('.hero-metrics [data-count]');
                heroCounters.forEach(c => {
                    const target = parseFloat(c.getAttribute('data-count'));
                    const isFloat = target % 1 !== 0;
                    const duration = 1600;
                    const startTime = performance.now();

                    function updateCounter(currentTime) {
                        const elapsed = currentTime - startTime;
                        const progress = Math.min(elapsed / duration, 1);
                        const eased = 1 - Math.pow(1 - progress, 3);
                        const current = eased * target;

                        if (isFloat) {
                            c.textContent = current.toFixed(1);
                        } else {
                            c.textContent = Math.floor(current);
                        }

                        if (progress < 1) {
                            requestAnimationFrame(updateCounter);
                        } else {
                            if (isFloat) {
                                c.textContent = target.toFixed(1);
                            } else {
                                c.textContent = target;
                            }
                        }
                    }
                    requestAnimationFrame(updateCounter);
                });
            }
        });
    }, { threshold: 0.30 });

    if (heroMetrics) heroCounterObserver.observe(heroMetrics);

    // ============================================================
    // SMOOTH SCROLL
    // ============================================================
    document.querySelectorAll('a[href^="#"]').forEach(anchor => {
        anchor.addEventListener('click', function(e) {
            const href = this.getAttribute('href');
            if (href === '#') return;
            e.preventDefault();
            const target = document.querySelector(href);
            if (target) {
                const offset = 80;
                const top = target.getBoundingClientRect().top + window.pageYOffset - offset;
                window.scrollTo({ top, behavior: 'smooth' });
            }
        });
    });

    console.log('🚀 Abdur Rafay Yousuf — Premium Engineering Portfolio');
    console.log('📐 Built with precision, just like my CAD models.');
    console.log('⭐ Rating: 9.8/10');
</script>
</body>
</html>
