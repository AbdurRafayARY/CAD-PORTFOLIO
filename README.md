<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Abdur Rafay Yousuf | Mechanical CAD Engineer & Product Designer</title>

    <!-- Font Awesome 6 -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css" />
    <!-- Google Fonts -->
    <link rel="preconnect" href="https://fonts.googleapis.com" />
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
    <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,300;14..32,400;14..32,500;14..32,600;14..32,700;14..32,800;14..32,900&family=JetBrains+Mono:wght@400;500;600;700&display=swap" rel="stylesheet" />

    <style>
        /* ============================================================
                   ROOT VARIABLES & RESET
                   ============================================================ */
        :root {
            --primary: #2563EB;
            --primary-dark: #1D4ED8;
            --primary-light: #EFF6FF;
            --primary-glow: rgba(37, 99, 235, 0.20);
            --bg-main: #F8FAFC;
            --bg-card: #FFFFFF;
            --bg-alt: #F1F5F9;
            --border-color: #E2E8F0;
            --border-accent: rgba(37, 99, 235, 0.25);
            --text-main: #0F172A;
            --text-muted: #64748B;
            --text-light: #94A3B8;
            --shadow-sm: 0 1px 3px rgba(0, 0, 0, 0.04);
            --shadow-md: 0 4px 24px -6px rgba(15, 23, 42, 0.08);
            --shadow-lg: 0 16px 48px -12px rgba(37, 99, 235, 0.15);
            --shadow-hover: 0 12px 40px -8px rgba(37, 99, 235, 0.18);
            --radius-sm: 8px;
            --radius-md: 16px;
            --radius-lg: 24px;
            --radius-xl: 32px;
            --transition: all 0.30s cubic-bezier(0.4, 0, 0.2, 1);
            --font-main: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
            --font-mono: 'JetBrains Mono', monospace;
            --max-width: 1200px;
            --section-padding: 80px 5%;
        }

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
        }

        /* Subtle Blueprint Grid Background */
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
        }

        /* CAD Wireframe decoration — floating subtle lines */
        .cad-decoration {
            position: fixed;
            pointer-events: none;
            z-index: 0;
            opacity: 0.06;
            color: var(--primary);
            font-size: 14rem;
            right: -4%;
            bottom: -8%;
            font-family: var(--font-mono);
            font-weight: 700;
            letter-spacing: -0.08em;
            user-select: none;
            line-height: 1;
        }

        .cad-decoration-top {
            position: fixed;
            pointer-events: none;
            z-index: 0;
            opacity: 0.04;
            color: var(--primary);
            font-size: 10rem;
            left: -2%;
            top: 12%;
            font-family: var(--font-mono);
            font-weight: 700;
            letter-spacing: -0.06em;
            user-select: none;
            line-height: 1;
            transform: rotate(-6deg);
        }

        @media (max-width: 768px) {
            .cad-decoration,
            .cad-decoration-top {
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
            border-radius: 20px;
            border: 1px solid var(--border-accent);
            margin-bottom: 0.75rem;
        }

        .section-title {
            font-size: 2.4rem;
            font-weight: 800;
            color: var(--text-main);
            letter-spacing: -0.03em;
            line-height: 1.15;
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
            transform: translateY(-2px);
            box-shadow: 0 8px 28px rgba(37, 99, 235, 0.35);
        }

        .btn-secondary {
            background: #fff;
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
            background: rgba(255, 255, 255, 0.85);
            backdrop-filter: blur(16px);
            -webkit-backdrop-filter: blur(16px);
            z-index: 1000;
            border-bottom: 1px solid var(--border-color);
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
            font-size: 0.875rem;
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

        /* ============================================================
                   HERO
                   ============================================================ */
        #hero {
            min-height: 100vh;
            padding-top: 100px;
            display: grid;
            grid-template-columns: 1.2fr 0.8fr;
            gap: 4rem;
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
        }

        .hero-title {
            font-size: 3.2rem;
            font-weight: 900;
            line-height: 1.1;
            color: var(--text-main);
            letter-spacing: -0.04em;
            margin-bottom: 0.5rem;
        }
        .hero-title .highlight {
            color: var(--primary);
        }

        .hero-subtitle {
            font-size: 1.25rem;
            font-weight: 600;
            color: var(--primary);
            margin-bottom: 0.75rem;
        }

        .hero-bio {
            color: var(--text-muted);
            font-size: 1.05rem;
            max-width: 540px;
            margin-bottom: 2rem;
            line-height: 1.7;
        }

        .hero-metrics {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 1.25rem;
            margin-bottom: 2.5rem;
            padding-top: 1.5rem;
            border-top: 1px solid var(--border-color);
            max-width: 480px;
        }
        .metric-item strong {
            display: block;
            font-size: 1.5rem;
            font-weight: 800;
            color: var(--text-main);
            font-family: var(--font-mono);
        }
        .metric-item span {
            font-size: 0.8rem;
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
            display: flex;
            justify-content: center;
            align-items: center;
        }

        .profile-card {
            position: relative;
            padding: 1.5rem;
            background: #fff;
            border: 1px solid var(--border-color);
            border-radius: var(--radius-lg);
            box-shadow: var(--shadow-lg);
            text-align: center;
            width: 100%;
            max-width: 360px;
            transition: var(--transition);
        }
        .profile-card:hover {
            transform: translateY(-4px);
            box-shadow: var(--shadow-hover);
        }

        .profile-img-wrap {
            width: 200px;
            height: 200px;
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
            font-size: 1.2rem;
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

        /* ============================================================
                   ABOUT
                   ============================================================ */
        #about {
            background: #fff;
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
            gap: 1.5rem;
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
        }
        .stat-box .number {
            font-size: 2.2rem;
            font-weight: 800;
            color: var(--primary);
            font-family: var(--font-mono);
        }
        .stat-box .label {
            font-size: 0.85rem;
            color: var(--text-muted);
            font-weight: 500;
        }

        /* ============================================================
                   SKILLS
                   ============================================================ */
        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
            gap: 1.5rem;
        }

        .skill-card {
            padding: 1.75rem;
            display: flex;
            flex-direction: column;
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
            background: var(--primary);
            border-radius: 10px;
            transition: width 0.8s ease;
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
            background: #fff;
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
            background: #fff;
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
            box-shadow: 0 4px 12px rgba(37, 99, 235, 0.25);
        }

        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(320px, 1fr));
            gap: 2rem;
        }

        .project-card {
            display: flex;
            flex-direction: column;
            overflow: hidden;
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
            transition: var(--transition);
        }
        .project-card:hover .project-img img {
            transform: scale(1.04);
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
            margin-bottom: 1.25rem;
            flex-grow: 1;
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
        }
        .project-link:hover {
            gap: 12px;
            color: var(--primary-dark);
        }

        /* Drawings Gallery */
        .drawings-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(260px, 1fr));
            gap: 1.25rem;
            margin-top: 2rem;
        }

        .drawing-item {
            position: relative;
            border-radius: var(--radius-md);
            overflow: hidden;
            height: 190px;
            cursor: pointer;
            border: 1px solid var(--border-color);
            background: #fff;
            transition: var(--transition);
        }
        .drawing-item:hover {
            border-color: var(--border-accent);
            box-shadow: var(--shadow-hover);
        }
        .drawing-item img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: var(--transition);
        }
        .drawing-item:hover img {
            transform: scale(1.06);
        }

        .drawing-overlay {
            position: absolute;
            inset: 0;
            background: rgba(15, 23, 42, 0.80);
            backdrop-filter: blur(4px);
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            opacity: 0;
            transition: var(--transition);
            padding: 1rem;
            text-align: center;
            color: #fff;
        }
        .drawing-item:hover .drawing-overlay {
            opacity: 1;
        }
        .drawing-overlay i {
            font-size: 1.8rem;
            margin-bottom: 6px;
        }
        .drawing-overlay strong {
            font-size: 0.95rem;
        }
        .drawing-overlay small {
            font-size: 0.7rem;
            opacity: 0.7;
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
        }
        .quote-icon {
            font-size: 1.6rem;
            color: var(--primary);
            opacity: 0.4;
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
            flex-shrink: 0;
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
            background: #fff;
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
            background: #fff;
            box-shadow: 0 0 0 3px rgba(37, 99, 235, 0.12);
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

        .social-links {
            display: flex;
            gap: 0.75rem;
        }
        .social-links a {
            width: 38px;
            height: 38px;
            border-radius: 50%;
            background: #fff;
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
            backdrop-filter: blur(6px);
            -webkit-backdrop-filter: blur(6px);
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
            background: #fff;
            border-radius: var(--radius-lg);
            box-shadow: var(--shadow-lg);
            animation: modalIn 0.3s ease;
        }
        @keyframes modalIn {
            from {
                opacity: 0;
                transform: scale(0.95) translateY(20px);
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
        }

        @media (max-width: 768px) {
            .nav-links {
                display: none;
                position: absolute;
                top: 72px;
                left: 0;
                width: 100%;
                background: #fff;
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
            }
            .hero-btns {
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
            .drawings-grid {
                grid-template-columns: 1fr 1fr;
            }
            .skills-grid {
                grid-template-columns: 1fr;
            }
            .hero-metrics {
                grid-template-columns: 1fr 1fr;
            }

            .profile-card {
                max-width: 300px;
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

            .status-badge {
                display: none;
            }
        }

        @media (max-width: 480px) {
            .hero-title {
                font-size: 1.8rem;
            }
            .hero-metrics {
                grid-template-columns: 1fr;
                gap: 0.75rem;
            }
            .drawings-grid {
                grid-template-columns: 1fr;
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
        }

        /* ============================================================
                   SCROLL ANIMATIONS (simple reveal)
                   ============================================================ */
        .reveal {
            opacity: 0;
            transform: translateY(30px);
            transition: opacity 0.7s ease, transform 0.7s ease;
        }
        .reveal.visible {
            opacity: 1;
            transform: translateY(0);
        }
    </style>
</head>

<body>

    <!-- ============================================================
    CAD WIREFRAME DECORATIONS
    ============================================================ -->
    <div class="cad-decoration" aria-hidden="true">&lt;/&gt;</div>
    <div class="cad-decoration-top" aria-hidden="true">◈</div>

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

        <button class="menu-toggle" id="menuToggle" aria-label="Toggle navigation">
            <i class="fa-solid fa-bars"></i>
        </button>

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
            <div class="hero-greeting">👋 Hi, I'm Abdur Rafay Yousuf</div>
            <h1 class="hero-title">
                Mechanical <br /><span class="highlight">CAD Engineer</span> &amp; Product Designer
            </h1>
            <p class="hero-subtitle">
                I transform complex engineering problems into production-ready 3D assemblies &amp; DFM drawings.
            </p>
            <p class="hero-bio">
                Founder of <strong>3D Mech Design</strong> &amp; Mechanical Engineering Specialist. I craft mathematically
                accurate involute gears, fluid/thermal CFD simulations, and lightweight structural assemblies optimized for
                modern manufacturing.
            </p>

            <div class="hero-metrics">
                <div class="metric-item">
                    <strong>3+ Years</strong>
                    <span>Parametric CAD Modeling</span>
                </div>
                <div class="metric-item">
                    <strong>±0.01 mm</strong>
                    <span>Precision GD&amp;T</span>
                </div>
                <div class="metric-item">
                    <strong>100% DFM</strong>
                    <span>Manufacturing Ready</span>
                </div>
            </div>

            <div class="hero-btns">
                <a href="#projects" class="btn btn-primary">
                    <i class="fa-solid fa-layer-group"></i> View Portfolio
                </a>
                <a href="#" class="btn btn-secondary" onclick="alert('Resume download coming soon!')">
                    <i class="fa-solid fa-file-pdf"></i> Resume
                </a>
            </div>
        </div>

        <!-- Profile Photo -->
        <div class="hero-image-wrapper">
            <div class="profile-card">
                <div class="profile-img-wrap">
                    <!-- Replace with your actual professional photo -->
                    <img src="https://images.unsplash.com/photo-1534528741775-53994a69daeb?auto=format&fit=crop&w=600&q=80"
                    alt="Abdur Rafay Yousuf - Mechanical CAD Engineer" />
                </div>
                <h3>Abdur Rafay Yousuf</h3>
                <div class="role-tag">Mechanical Design Consultant</div>
                <div class="profile-badge">
                    <i class="fa-solid fa-certificate"></i> SolidWorks &amp; CFD Certified
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
                    <p style="margin-top: 1rem;">
                        <span style="display:inline-flex; align-items:center; gap:0.5rem; background:var(--primary-light); padding:0.3rem 1rem; border-radius:50px; font-size:0.85rem; font-weight:600; color:var(--primary); border:1px solid var(--border-accent);">
                            <i class="fa-regular fa-clock"></i> Available for freelance &amp; consulting work
                        </span>
                    </p>
                </div>

                <div class="about-stats">
                    <div class="stat-box">
                        <div class="number">12+</div>
                        <div class="label">CAD Projects Delivered</div>
                    </div>
                    <div class="stat-box">
                        <div class="number">5</div>
                        <div class="label">Industry Collaborations</div>
                    </div>
                    <div class="stat-box">
                        <div class="number">100%</div>
                        <div class="label">DFM Compliance Rate</div>
                    </div>
                    <div class="stat-box">
                        <div class="number">4.9★</div>
                        <div class="label">Client Satisfaction</div>
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
                <div class="skill-card card">
                    <div class="skill-icon-header">
                        <div class="skill-icon-box"><i class="fa-solid fa-cube"></i></div>
                        <div class="skill-title-group">
                            <h4>SolidWorks &amp; 3D CAD</h4>
                            <span>Parametric Modeling</span>
                        </div>
                    </div>
                    <p class="skill-desc">Complex assembly design, motion simulation, parametric feature trees, and sheet metal design.</p>
                    <div class="progress-track"><div class="progress-fill" style="width:95%;"></div></div>
                </div>

                <!-- Skill 2 -->
                <div class="skill-card card">
                    <div class="skill-icon-header">
                        <div class="skill-icon-box"><i class="fa-solid fa-wind"></i></div>
                        <div class="skill-title-group">
                            <h4>CFD &amp; Thermal Analysis</h4>
                            <span>ANSYS / Flow Simulation</span>
                        </div>
                    </div>
                    <p class="skill-desc">Internal flow distribution, thermal energy storage modeling, forced convection, and turbulence estimation.</p>
                    <div class="progress-track"><div class="progress-fill" style="width:88%;"></div></div>
                </div>

                <!-- Skill 3 -->
                <div class="skill-card card">
                    <div class="skill-icon-header">
                        <div class="skill-icon-box"><i class="fa-solid fa-gear"></i></div>
                        <div class="skill-title-group">
                            <h4>Involute Gear Engineering</h4>
                            <span>MATLAB &amp; Custom Arbors</span>
                        </div>
                    </div>
                    <p class="skill-desc">Mathematical involute tooth profile calculations, diametral pitch analysis, hobbing &amp; inspection arbors.</p>
                    <div class="progress-track"><div class="progress-fill" style="width:92%;"></div></div>
                </div>

                <!-- Skill 4 -->
                <div class="skill-card card">
                    <div class="skill-icon-header">
                        <div class="skill-icon-box"><i class="fa-solid fa-compass-drafting"></i></div>
                        <div class="skill-title-group">
                            <h4>AutoCAD &amp; GD&amp;T Drafting</h4>
                            <span>ASME Y14.5 Standards</span>
                        </div>
                    </div>
                    <p class="skill-desc">Production drawings with geometric dimensioning and tolerancing, datum reference frames, and BOMs.</p>
                    <div class="progress-track"><div class="progress-fill" style="width:90%;"></div></div>
                </div>

                <!-- Skill 5 -->
                <div class="skill-card card">
                    <div class="skill-icon-header">
                        <div class="skill-icon-box"><i class="fa-solid fa-microchip"></i></div>
                        <div class="skill-title-group">
                            <h4>FEA &amp; Structural Analysis</h4>
                            <span>ANSYS / SolidWorks Simulation</span>
                        </div>
                    </div>
                    <p class="skill-desc">Linear static, fatigue, and modal analysis for structural integrity validation under loading conditions.</p>
                    <div class="progress-track"><div class="progress-fill" style="width:85%;"></div></div>
                </div>

                <!-- Skill 6 -->
                <div class="skill-card card">
                    <div class="skill-icon-header">
                        <div class="skill-icon-box"><i class="fa-solid fa-code"></i></div>
                        <div class="skill-title-group">
                            <h4>Engineering Automation</h4>
                            <span>Python / MATLAB Scripting</span>
                        </div>
                    </div>
                    <p class="skill-desc">Custom scripts for gear geometry generation, data post-processing, and parametric design automation.</p>
                    <div class="progress-track"><div class="progress-fill" style="width:78%;"></div></div>
                </div>
            </div>
        </div>
    </section>

    <!-- ============================================================
    EXPERIENCE
    ============================================================ -->
    <section id="experience" style="background:#fff; border-top:1px solid var(--border-color); border-bottom:1px solid var(--border-color);">
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
                    <div class="timeline-content card">
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
                    <div class="timeline-content card">
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
                    <div class="timeline-content card">
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
    <section id="projects">
        <div class="container">
            <div class="section-header">
                <div class="section-tag"><i class="fa-solid fa-folder-open"></i> Portfolio</div>
                <h2 class="section-title">Featured CAD &amp; Engineering Projects</h2>
                <p class="section-subtitle">Explore selected mechanical assemblies, thermal CFD models, and manufacturing drawings.</p>
            </div>

            <!-- Filter -->
            <div class="filter-bar">
                <button class="filter-btn active" data-filter="all">All Work</button>
                <button class="filter-btn" data-filter="mobility">Mobility Systems</button>
                <button class="filter-btn" data-filter="thermal">Thermal &amp; CFD</button>
                <button class="filter-btn" data-filter="gears">Precision Gears</button>
            </div>

            <!-- Projects Grid -->
            <div class="projects-grid" id="projectsGrid">
                <!-- Project 1 -->
                <div class="project-card card" data-category="mobility">
                    <div class="project-img">
                        <img src="https://images.unsplash.com/photo-1581092160607-ee22621dd758?auto=format&fit=crop&w=600&q=80" alt="Stair-Lifting Assistive Mechanism" loading="lazy" />
                    </div>
                    <div class="project-content">
                        <div class="project-tags">
                            <span class="tag">SolidWorks</span>
                            <span class="tag">Kinematics</span>
                            <span class="tag">FEA</span>
                        </div>
                        <h3 class="project-title">Stair-Ascending Mobility Chassis</h3>
                        <p class="project-desc">Locally manufacturable stair-lifting mechanism with custom high-torque gearing and FEA load factor validation.</p>
                        <button class="project-link" onclick="openSpecModal('Stair-Ascending Mobility Chassis', 'AL 6061-T6 Frame', '3.2 FEA Safety Factor', 'SolidWorks / Motion Study', '±0.05 mm')">
                            View Specs <i class="fa-solid fa-arrow-right"></i>
                        </button>
                    </div>
                </div>

                <!-- Project 2 -->
                <div class="project-card card" data-category="thermal">
                    <div class="project-img">
                        <img src="https://images.unsplash.com/photo-1531403009284-440f080d1e12?auto=format&fit=crop&w=600&q=80" alt="Sand Battery Thermal Vessel" loading="lazy" />
                    </div>
                    <div class="project-content">
                        <div class="project-tags">
                            <span class="tag">CFD</span>
                            <span class="tag">Heat Transfer</span>
                            <span class="tag">Thermal Storage</span>
                        </div>
                        <h3 class="project-title">Sand Thermal Energy Battery</h3>
                        <p class="project-desc">High-temperature silica sand energy storage unit equipped with internal heat exchanger coil flow contours.</p>
                        <button class="project-link" onclick="openSpecModal('Sand Thermal Energy Battery', 'Insulated Mild Steel + Silica Sand', 'Flow &amp; Heat Transfer Simulation', 'CFD / ANSYS', 'Sealed Thermal Fit')">
                            View Specs <i class="fa-solid fa-arrow-right"></i>
                        </button>
                    </div>
                </div>

                <!-- Project 3 -->
                <div class="project-card card" data-category="gears">
                    <div class="project-img">
                        <img src="https://images.unsplash.com/photo-1581092580497-e0d23cbdf1dc?auto=format&fit=crop&w=600&q=80" alt="Involute Inspection Arbor" loading="lazy" />
                    </div>
                    <div class="project-content">
                        <div class="project-tags">
                            <span class="tag">Involute Gear</span>
                            <span class="tag">MATLAB</span>
                            <span class="tag">GD&amp;T</span>
                        </div>
                        <h3 class="project-title">Involute Gear Hobbing Arbor</h3>
                        <p class="project-desc">Custom arbor engineered with exact mathematical pitch diameter scripts and tight tolerance GD&amp;T callouts.</p>
                        <button class="project-link" onclick="openSpecModal('Involute Gear Hobbing Arbor', 'Tool Steel (HRC 58-60)', 'Pitch Dia Profile Scripts', 'MATLAB / AutoCAD', '±0.01 mm')">
                            View Specs <i class="fa-solid fa-arrow-right"></i>
                        </button>
                    </div>
                </div>
            </div>

            <!-- Drawings Gallery -->
            <div style="margin-top:4rem;">
                <h3 style="font-size:1.3rem; font-weight:800; color:var(--text-main); margin-bottom:1rem; display:flex; align-items:center; gap:0.75rem;">
                    <i class="fa-regular fa-image" style="color:var(--primary);"></i>
                    2D GD&amp;T Drawings &amp; Renders
                </h3>
                <div class="drawings-grid">
                    <div class="drawing-item">
                        <img src="https://images.unsplash.com/photo-1581092335397-9583fe92d232?auto=format&fit=crop&w=500&q=80" alt="GD&T Drawing Sheet" loading="lazy" />
                        <div class="drawing-overlay">
                            <i class="fa-solid fa-magnifying-glass-plus"></i>
                            <strong>GD&amp;T Assembly Drawing</strong>
                            <small>ASME Y14.5 Compliant</small>
                        </div>
                    </div>
                    <div class="drawing-item">
                        <img src="https://images.unsplash.com/photo-1581091226825-a6a2a5aee158?auto=format&fit=crop&w=500&q=80" alt="3D Render" loading="lazy" />
                        <div class="drawing-overlay">
                            <i class="fa-solid fa-magnifying-glass-plus"></i>
                            <strong>Photorealistic 3D Render</strong>
                            <small>KeyShot / SolidWorks Visualize</small>
                        </div>
                    </div>
                    <div class="drawing-item">
                        <img src="https://images.unsplash.com/photo-1581092580497-e0d23cbdf1dc?auto=format&fit=crop&w=500&q=80" alt="Gear Profile" loading="lazy" />
                        <div class="drawing-overlay">
                            <i class="fa-solid fa-magnifying-glass-plus"></i>
                            <strong>Involute Profile Geometry</strong>
                            <small>Pitch Diameter Blueprint</small>
                        </div>
                    </div>
                    <div class="drawing-item">
                        <img src="https://images.unsplash.com/photo-1581092335397-9583fe92d232?auto=format&fit=crop&w=500&q=80" alt="Exploded View" loading="lazy" />
                        <div class="drawing-overlay">
                            <i class="fa-solid fa-magnifying-glass-plus"></i>
                            <strong>Exploded Assembly View</strong>
                            <small>BOM &amp; Part Callouts</small>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- ============================================================
    TESTIMONIALS
    ============================================================ -->
    <section id="testimonials" style="background:#fff; border-top:1px solid var(--border-color); border-bottom:1px solid var(--border-color);">
        <div class="container">
            <div class="section-header">
                <div class="section-tag"><i class="fa-solid fa-comment-dots"></i> Endorsements</div>
                <h2 class="section-title">Client &amp; Academic Feedback</h2>
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
                        and full 3D assembly modeling projects. I respond within 24 hours.
                    </p>

                    <div class="info-list">
                        <div class="info-item">
                            <div class="info-icon"><i class="fa-solid fa-briefcase"></i></div>
                            <div>
                                <small>Consultancy Brand</small>
                                <div><strong>3D Mech Design</strong></div>
                            </div>
                        </div>
                        <div class="info-item">
                            <div class="info-icon"><i class="fa-solid fa-location-dot"></i></div>
                            <div>
                                <small>Location</small>
                                <div><strong>Karachi, Pakistan / Remote Worldwide</strong></div>
                            </div>
                        </div>
                        <div class="info-item">
                            <div class="info-icon"><i class="fa-solid fa-envelope"></i></div>
                            <div>
                                <small>Email Address</small>
                                <div><strong>rafay.yousuf.mech@gmail.com</strong></div>
                            </div>
                        </div>
                    </div>
                </div>

                <form class="contact-form card" onsubmit="event.preventDefault(); alert('✅ Thank you! Your message has been sent successfully. I\'ll get back to you within 24 hours.');">
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
    FOOTER
    ============================================================ -->
    <footer>
        <div>&copy; 2026 Abdur Rafay Yousuf • 3D Mech Design. All rights reserved.</div>
        <div class="social-links">
            <a href="https://github.com" target="_blank" title="GitHub"><i class="fa-brands fa-github"></i></a>
            <a href="https://linkedin.com" target="_blank" title="LinkedIn"><i class="fa-brands fa-linkedin-in"></i></a>
            <a href="mailto:rafay.yousuf.mech@gmail.com" title="Email"><i class="fa-solid fa-envelope"></i></a>
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
        // === Mobile Menu Toggle ===
        const menuToggle = document.getElementById('menuToggle');
        const navLinks = document.getElementById('navLinks');

        menuToggle.addEventListener('click', () => {
            navLinks.classList.toggle('active');
        });

        document.querySelectorAll('.nav-links a').forEach(link => {
            link.addEventListener('click', () => navLinks.classList.remove('active'));
        });

        // === Project Filter ===
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

        // === Spec Modal ===
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

        // === Scroll Reveal ===
        const revealElements = document.querySelectorAll('.reveal');

        const revealObserver = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('visible');
                }
            });
        }, { threshold: 0.12, rootMargin: '0px 0px -30px 0px' });

        document.querySelectorAll(
            '.skill-card, .timeline-item, .project-card, .testimonial-card, .stat-box, .drawing-item'
        ).forEach(el => {
            el.classList.add('reveal');
            revealObserver.observe(el);
        });

        // Also reveal section headers
        document.querySelectorAll('.section-header').forEach(el => {
            el.classList.add('reveal');
            revealObserver.observe(el);
        });

        // === Smooth anchor scroll (no-jump) ===
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

        console.log('🚀 Abdur Rafay Yousuf — Mechanical CAD Engineer Portfolio');
        console.log('📐 Built with precision, just like my CAD models.');
    </script>
</body>
</html>
