<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Abdur Rafay Yousuf | Mechanical Engineer &amp; CAD Consultant</title>

    <!-- Font Awesome 6 & Google Fonts -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css" />
    <link rel="preconnect" href="https://fonts.googleapis.com" />
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
    <link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;500;600;700&family=Plus+Jakarta+Sans:wght@300;400;500;600;700;800&display=swap" rel="stylesheet" />

    <style>
        /* ==========================================================================
           1.  DESIGN SYSTEM & VARIABLES (LIGHT / DARK)
           ========================================================================== */
        :root {
            --bg: #f8fafc;
            --bg2: #eef6ff;
            --text: #0f172a;
            --primary: #2563eb;
            --card: rgba(255, 255, 255, 0.65);
            --primary-hover: #1d4ed8;
            --primary-light: rgba(37, 99, 235, 0.10);
            --secondary: #0f172a;
            --text-muted: #64748b;
            --accent-green: #059669;
            --border-color: rgba(15, 23, 42, 0.10);
            --border-accent: rgba(37, 99, 235, 0.30);
            --grid-line: rgba(37, 99, 235, 0.06);
            --shadow-sm: 0 1px 3px rgba(0, 0, 0, 0.05);
            --shadow-md: 0 10px 40px rgba(0, 0, 0, 0.08);
            --shadow-hover: 0 20px 60px rgba(37, 99, 235, 0.15);
            --transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            --radius: 20px;
            --radius-sm: 12px;
            --font-main: 'Plus Jakarta Sans', sans-serif;
            --font-mono: 'JetBrains Mono', monospace;
        }
        [data-theme="dark"] {
            --bg: #050816;
            --bg2: #0f172a;
            --text: #ffffff;
            --primary: #4f9bff;
            --card: rgba(15, 23, 42, 0.55);
            --primary-hover: #60a5fa;
            --primary-light: rgba(79, 155, 255, 0.15);
            --secondary: #f8fafc;
            --text-muted: #94a3b8;
            --accent-green: #10b981;
            --border-color: rgba(255, 255, 255, 0.12);
            --border-accent: rgba(79, 155, 255, 0.30);
            --grid-line: rgba(79, 155, 255, 0.08);
            --shadow-md: 0 10px 40px rgba(0, 0, 0, 0.30);
            --shadow-hover: 0 20px 60px rgba(79, 155, 255, 0.25);
        }
        /* Scrollbar */
        ::-webkit-scrollbar {
            width: 10px;
        }
        ::-webkit-scrollbar-track {
            background: var(--bg);
        }
        ::-webkit-scrollbar-thumb {
            background: var(--border-accent);
            border-radius: 10px;
        }
        ::-webkit-scrollbar-thumb:hover {
            background: var(--primary);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        html {
            scroll-behavior: smooth;
        }

        /* ==========================================================================
           2.  PREMIUM BACKGROUND + AURORA
           ========================================================================== */
        body {
            color: var(--text);
            background:
                radial-gradient(circle at 10% 20%, rgba(37, 99, 235, 0.15), transparent 35%),
                radial-gradient(circle at 90% 20%, rgba(0, 212, 255, 0.12), transparent 30%),
                radial-gradient(circle at 50% 90%, rgba(139, 92, 246, 0.15), transparent 35%),
                linear-gradient(135deg, var(--bg), var(--bg2));
            background-size: cover;
            background-attachment: fixed;
            min-height: 100vh;
            font-family: var(--font-main);
            line-height: 1.6;
            overflow-x: hidden;
            position: relative;
        }
        body::before {
            content: "";
            position: fixed;
            inset: -20%;
            background:
                radial-gradient(circle, rgba(37, 99, 235, 0.15) 0%, transparent 40%),
                radial-gradient(circle, rgba(6, 182, 212, 0.15) 0%, transparent 35%),
                radial-gradient(circle, rgba(139, 92, 246, 0.15) 0%, transparent 40%);
            filter: blur(120px);
            animation: aurora 30s linear infinite alternate;
            z-index: -2;
            pointer-events: none;
        }
        @keyframes aurora {
            0% {
                transform: translate(-10%, -5%) rotate(0deg);
            }
            100% {
                transform: translate(10%, 8%) rotate(20deg);
            }
        }
        .spotlight {
            position: fixed;
            inset: 0;
            pointer-events: none;
            z-index: 9998;
            background: radial-gradient(600px circle at var(--x, 50%) var(--y, 50%), rgba(255, 255, 255, 0.06), transparent 40%);
        }

        /* ==========================================================================
           3.  GLASSMORPHISM & CARDS
           ========================================================================== */
        .card,
        .project-card,
        .skill-card,
        .testimonial-card,
        .drawing-item,
        .modal-container,
        .service-card,
        .faq-item,
        .blog-card,
        .cert-card,
        .edu-card {
            background: var(--card);
            backdrop-filter: blur(18px);
            -webkit-backdrop-filter: blur(18px);
            border: 1px solid var(--border-color);
            border-radius: var(--radius);
            box-shadow: var(--shadow-md);
            transition: var(--transition);
            transform: perspective(1000px) rotateX(0) rotateY(0) scale3d(1, 1, 1);
        }
        .card:hover,
        .project-card:hover,
        .skill-card:hover,
        .testimonial-card:hover,
        .drawing-item:hover,
        .service-card:hover,
        .blog-card:hover,
        .cert-card:hover,
        .edu-card:hover {
            transform: perspective(1000px) translateY(-8px) rotateX(2deg) rotateY(-2deg) scale3d(1.02, 1.02, 1.02);
            box-shadow: var(--shadow-hover);
            border-color: var(--border-accent);
        }

        /* ==========================================================================
           4.  LAYOUT & TYPOGRAPHY
           ========================================================================== */
        section {
            padding: 90px 8%;
            max-width: 1320px;
            margin: 0 auto;
            position: relative;
        }
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
            border-radius: 6px;
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
        .text-gradient {
            background: linear-gradient(to right, var(--primary), #8b5cf6, var(--primary));
            background-size: 200% auto;
            color: transparent;
            -webkit-background-clip: text;
            background-clip: text;
            animation: textShine 4s linear infinite;
        }
        @keyframes textShine {
            to {
                background-position: 200% center;
            }
        }

        /* ==========================================================================
           5.  BUTTONS & TOGGLES
           ========================================================================== */
        .btn {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            gap: 0.6rem;
            padding: 0.85rem 1.6rem;
            border-radius: var(--radius-sm);
            font-weight: 600;
            font-size: 0.95rem;
            text-decoration: none;
            cursor: pointer;
            transition: var(--transition);
            border: 1px solid transparent;
        }
        .btn-primary {
            background: linear-gradient(45deg, var(--primary), #8b5cf6, var(--primary));
            background-size: 200% 100%;
            animation: btnGradient 4s ease infinite;
            color: #ffffff;
            box-shadow: 0 4px 14px rgba(37, 99, 235, 0.25);
            border: 1px solid rgba(255, 255, 255, 0.10);
        }
        @keyframes btnGradient {
            0% {
                background-position: 0% 50%;
            }
            50% {
                background-position: 100% 50%;
            }
            100% {
                background-position: 0% 50%;
            }
        }
        .btn-primary:hover {
            transform: translateY(-3px) scale(1.02);
            box-shadow: 0 8px 25px rgba(139, 92, 246, 0.40);
        }
        .btn-secondary {
            background: var(--card);
            color: var(--secondary);
            border-color: var(--border-color);
            backdrop-filter: blur(10px);
        }
        .btn-secondary:hover {
            border-color: var(--primary);
            color: var(--primary);
            background: var(--primary-light);
            transform: translateY(-3px);
        }
        #theme-toggle {
            position: fixed;
            top: 25px;
            right: 25px;
            width: 50px;
            height: 50px;
            border: 1px solid var(--border-color);
            border-radius: 50%;
            cursor: pointer;
            font-size: 20px;
            background: var(--card);
            backdrop-filter: blur(12px);
            color: var(--text);
            z-index: 1001;
            box-shadow: var(--shadow-md);
            transition: var(--transition);
        }
        #theme-toggle:hover {
            transform: scale(1.10) rotate(15deg);
            border-color: var(--primary);
        }
        /* Editor Toggle Button */
        #editor-toggle {
            position: fixed;
            bottom: 95px;
            right: 25px;
            width: 54px;
            height: 54px;
            border: 1px solid var(--border-accent);
            border-radius: 50%;
            cursor: pointer;
            font-size: 22px;
            background: var(--card);
            backdrop-filter: blur(12px);
            color: var(--primary);
            z-index: 1001;
            box-shadow: var(--shadow-md);
            transition: var(--transition);
            display: flex;
            align-items: center;
            justify-content: center;
        }
        #editor-toggle:hover {
            transform: scale(1.10) rotate(10deg);
            border-color: var(--primary);
            background: var(--primary-light);
        }
        #editor-toggle.active {
            background: var(--primary);
            color: #fff;
            border-color: var(--primary);
        }

        .whatsapp-btn {
            position: fixed;
            right: 25px;
            bottom: 25px;
            width: 60px;
            height: 60px;
            background: #25D366;
            color: #fff;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 32px;
            box-shadow: 0 8px 25px rgba(37, 211, 102, 0.35);
            z-index: 1000;
            text-decoration: none;
            transition: var(--transition);
            border: 2px solid rgba(255, 255, 255, 0.20);
        }
        .whatsapp-btn:hover {
            transform: scale(1.15) rotate(-5deg);
            background: #128C7E;
            box-shadow: 0 12px 35px rgba(37, 211, 102, 0.50);
            color: #fff;
        }

        /* ==========================================================================
           6.  HEADER – Glass Navigation
           ========================================================================== */
        header {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            padding: 0 8%;
            height: 80px;
            display: flex;
            justify-content: center;
            align-items: center;
            background: var(--card);
            backdrop-filter: blur(24px);
            -webkit-backdrop-filter: blur(24px);
            z-index: 1000;
            border-bottom: 1px solid var(--border-color);
        }
        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
            width: 100%;
            max-width: 1320px;
            padding-right: 60px;
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
        .menu-toggle {
            display: none;
            font-size: 1.4rem;
            cursor: pointer;
            color: var(--secondary);
        }

        /* ==========================================================================
           7.  HERO
           ========================================================================== */
        #hero {
            min-height: 100vh;
            padding-top: 140px;
            padding-bottom: 60px;
            display: grid;
            grid-template-columns: 1.2fr 0.8fr;
            gap: 4rem;
            align-items: center;
            position: relative;
        }
        #hero::before {
            content: "";
            position: absolute;
            top: 0;
            left: 50%;
            transform: translateX(-50%);
            width: 100vw;
            height: 100%;
            background-image:
                linear-gradient(var(--grid-line) 1px, transparent 1px),
                linear-gradient(90deg, var(--grid-line) 1px, transparent 1px);
            background-size: 32px 32px;
            -webkit-mask-image: radial-gradient(ellipse at center, black 10%, transparent 70%);
            mask-image: radial-gradient(ellipse at center, black 10%, transparent 70%);
            z-index: -1;
            pointer-events: none;
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
        .profile-card {
            padding: 1.5rem;
            text-align: center;
            width: 100%;
            max-width: 380px;
            position: relative;
            z-index: 1;
        }
        .profile-img-container {
            width: 220px;
            height: 220px;
            margin: 0 auto 1.5rem auto;
            border-radius: 50%;
            position: relative;
            z-index: 2;
            border: 4px solid rgba(255, 255, 255, 0.10);
            background: var(--bg);
            overflow: hidden;
        }
        .profile-img-container::before {
            content: '';
            position: absolute;
            inset: -15px;
            background: linear-gradient(135deg, var(--primary), #8b5cf6, #06b6d4);
            filter: blur(25px);
            z-index: -1;
            opacity: 0.5;
            border-radius: 50%;
            animation: pulseGlow 5s infinite alternate;
        }
        @keyframes pulseGlow {
            0% {
                opacity: 0.3;
                transform: scale(0.95);
            }
            100% {
                opacity: 0.7;
                transform: scale(1.05);
            }
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

        /* ==========================================================================
           8.  SKILLS
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
            border-radius: var(--radius-sm);
            background: var(--primary-light);
            border: 1px solid var(--border-accent);
            color: var(--primary);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.25rem;
            flex-shrink: 0;
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
            background: var(--border-color);
            border-radius: 10px;
            overflow: hidden;
        }
        .progress-fill {
            height: 100%;
            background: linear-gradient(90deg, var(--primary), #8b5cf6);
            border-radius: 10px;
            transition: width 1.2s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            width: 0%;
        }
        .skill-card.active .progress-fill {
            width: var(--skill-width);
        }

        /* ==========================================================================
           9.  EXPERIENCE TIMELINE
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
            background: var(--card);
            backdrop-filter: blur(10px);
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
            border-radius: 6px;
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
            padding: 3px 8px;
            background: var(--primary-light);
            color: var(--primary);
            border-radius: 6px;
            border: 1px solid var(--border-accent);
            font-weight: 600;
        }

        /* ==========================================================================
           10.  PROJECTS PORTFOLIO
           ========================================================================== */
        .filter-menu {
            display: flex;
            gap: 10px;
            margin-bottom: 2.5rem;
            flex-wrap: wrap;
            justify-content: center;
        }
        .filter-btn {
            padding: 8px 18px;
            background: var(--card);
            border: 1px solid var(--border-color);
            color: var(--secondary);
            border-radius: 30px;
            cursor: pointer;
            font-size: 0.875rem;
            font-weight: 600;
            font-family: var(--font-mono);
            transition: var(--transition);
            backdrop-filter: blur(10px);
        }
        .filter-btn.active,
        .filter-btn:hover {
            background: var(--primary);
            color: #ffffff;
            border-color: var(--primary);
            box-shadow: 0 4px 12px rgba(37, 99, 235, 0.25);
            transform: translateY(-2px);
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
            padding: 0;
        }
        .project-img {
            width: 100%;
            height: 220px;
            background-color: var(--border-color);
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
            transform: scale(1.08);
        }
        .project-content {
            padding: 1.5rem;
            flex-grow: 1;
            display: flex;
            flex-direction: column;
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
            margin-right: 6px;
            margin-bottom: 10px;
            display: inline-block;
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
            transition: var(--transition);
        }
        .project-link:hover {
            color: #8b5cf6;
            gap: 12px;
        }

        .drawings-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 1.25rem;
            margin-top: 2rem;
        }
        .drawing-item {
            position: relative;
            height: 220px;
            overflow: hidden;
            cursor: pointer;
            padding: 0;
        }
        .drawing-item img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: var(--transition);
        }
        .drawing-overlay {
            position: absolute;
            inset: 0;
            background: rgba(15, 23, 42, 0.85);
            backdrop-filter: blur(4px);
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            opacity: 0;
            transition: var(--transition);
            color: #ffffff;
            text-align: center;
            padding: 1rem;
            border-radius: inherit;
        }
        .drawing-item:hover .drawing-overlay {
            opacity: 1;
        }
        .drawing-item:hover img {
            transform: scale(1.10);
        }
        .drawing-overlay h4 {
            font-size: 1.1rem;
            font-weight: 700;
            margin-bottom: 5px;
            color: #fff;
        }

        /* ==========================================================================
           11.  TESTIMONIALS
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
            font-size: 0.95rem;
            font-weight: 700;
            color: var(--secondary);
        }
        .author-details span {
            font-size: 0.8rem;
            color: var(--text-muted);
        }

        /* ==========================================================================
           12.  SERVICES
           ========================================================================== */
        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
            gap: 1.5rem;
        }
        .service-card {
            padding: 2rem;
            text-align: center;
        }
        .service-icon {
            font-size: 2.5rem;
            color: var(--primary);
            margin-bottom: 1rem;
        }
        .service-card h3 {
            font-size: 1.1rem;
            font-weight: 700;
            color: var(--secondary);
            margin-bottom: 0.5rem;
        }
        .service-card p {
            color: var(--text-muted);
            font-size: 0.9rem;
        }

        /* ==========================================================================
           13.  EDUCATION / CERTIFICATIONS
           ========================================================================== */
        .edu-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 1.5rem;
        }
        .edu-card {
            padding: 1.75rem;
        }
        .edu-card h3 {
            font-size: 1.1rem;
            font-weight: 700;
            color: var(--secondary);
        }
        .edu-card .meta {
            color: var(--primary);
            font-weight: 600;
            font-size: 0.9rem;
            margin: 4px 0 8px;
        }
        .edu-card p {
            color: var(--text-muted);
            font-size: 0.9rem;
        }
        .cert-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
            gap: 1rem;
            margin-top: 2rem;
        }
        .cert-card {
            padding: 1.25rem;
            text-align: center;
        }
        .cert-card i {
            font-size: 2rem;
            color: var(--primary);
            margin-bottom: 0.5rem;
        }
        .cert-card h4 {
            font-size: 1rem;
            color: var(--secondary);
            font-weight: 700;
        }
        .cert-card span {
            font-size: 0.8rem;
            color: var(--text-muted);
        }

        /* ==========================================================================
           14.  FAQ
           ========================================================================== */
        .faq-grid {
            max-width: 860px;
            margin: 0 auto;
            display: flex;
            flex-direction: column;
            gap: 0.75rem;
        }
        .faq-item {
            padding: 1.25rem 1.5rem;
            cursor: pointer;
            transition: var(--transition);
        }
        .faq-item .faq-q {
            display: flex;
            justify-content: space-between;
            align-items: center;
            font-weight: 700;
            color: var(--secondary);
            font-size: 1rem;
        }
        .faq-item .faq-q i {
            transition: var(--transition);
            color: var(--primary);
        }
        .faq-item .faq-a {
            max-height: 0;
            overflow: hidden;
            transition: max-height 0.5s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            color: var(--text-muted);
            font-size: 0.95rem;
            padding-top: 0;
        }
        .faq-item.open .faq-a {
            max-height: 300px;
            padding-top: 1rem;
        }
        .faq-item.open .faq-q i {
            transform: rotate(180deg);
        }

        /* ==========================================================================
           15.  CONTACT
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
            gap: 1.5rem;
        }
        .info-item {
            display: flex;
            align-items: center;
            gap: 1rem;
        }
        .info-icon {
            width: 48px;
            height: 48px;
            border-radius: var(--radius-sm);
            background: var(--primary-light);
            color: var(--primary);
            border: 1px solid var(--border-accent);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.2rem;
            flex-shrink: 0;
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
        .form-group input,
        .form-group textarea {
            padding: 0.85rem 1rem;
            background: var(--bg);
            border: 1px solid var(--border-color);
            border-radius: var(--radius-sm);
            color: var(--text);
            font-family: inherit;
            transition: var(--transition);
            font-size: 0.95rem;
            width: 100%;
        }
        .form-group input:focus,
        .form-group textarea:focus {
            outline: none;
            border-color: var(--primary);
            background: var(--bg2);
            box-shadow: 0 0 0 3px rgba(37, 99, 235, 0.15);
        }
        .alert-success {
            background: rgba(16, 185, 129, 0.10);
            color: var(--accent-green);
            border: 1px solid rgba(16, 185, 129, 0.30);
            padding: 1rem;
            border-radius: 8px;
            font-size: 0.95rem;
            font-weight: 600;
            display: none;
            align-items: center;
            gap: 10px;
            margin-top: 1rem;
            opacity: 0;
            transform: translateY(10px);
            transition: all 0.4s ease;
            backdrop-filter: blur(10px);
        }
        .alert-success.show {
            display: flex;
            opacity: 1;
            transform: translateY(0);
        }

        /* ==========================================================================
           16.  FOOTER
           ========================================================================== */
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
            margin-top: 2rem;
            flex-wrap: wrap;
            gap: 1rem;
        }
        .social-links {
            display: flex;
            gap: 1rem;
        }
        .social-links a {
            width: 38px;
            height: 38px;
            border-radius: 50%;
            background: var(--card);
            border: 1px solid var(--border-color);
            color: var(--text-muted);
            display: flex;
            align-items: center;
            justify-content: center;
            transition: var(--transition);
            text-decoration: none;
            backdrop-filter: blur(10px);
        }
        .social-links a:hover {
            color: var(--primary);
            border-color: var(--primary);
            background: var(--primary-light);
            transform: translateY(-3px) scale(1.10);
        }

        /* ==========================================================================
           17.  MODAL
           ========================================================================== */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(15, 23, 42, 0.70);
            backdrop-filter: blur(8px);
            z-index: 2000;
            justify-content: center;
            align-items: center;
            padding: 20px;
            opacity: 0;
            transition: opacity 0.3s ease;
        }
        .modal.show {
            display: flex;
            opacity: 1;
        }
        .modal-container {
            max-width: 700px;
            width: 100%;
            padding: 2.25rem;
            position: relative;
            transform: translateY(20px);
            transition: transform 0.3s ease;
        }
        .modal.show .modal-container {
            transform: translateY(0);
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
            color: var(--text);
        }
        .spec-table td:first-child {
            color: var(--text-muted);
            font-weight: 500;
            width: 40%;
        }
        .spec-table td:last-child {
            font-weight: 700;
        }
        .close-modal {
            position: absolute;
            top: 20px;
            right: 25px;
            color: var(--text-muted);
            font-size: 1.75rem;
            cursor: pointer;
            transition: var(--transition);
        }
        .close-modal:hover {
            color: var(--primary);
            transform: rotate(90deg);
        }

        /* ==========================================================================
           18.  EDITOR PANEL (SLIDE-OUT)
           ========================================================================== */
        #editor-panel {
            position: fixed;
            top: 0;
            right: -480px;
            width: 480px;
            max-width: 94vw;
            height: 100vh;
            background: var(--card);
            backdrop-filter: blur(28px);
            -webkit-backdrop-filter: blur(28px);
            border-left: 1px solid var(--border-color);
            box-shadow: -10px 0 60px rgba(0, 0, 0, 0.15);
            z-index: 3000;
            transition: right 0.45s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            padding: 2rem 1.5rem;
            overflow-y: auto;
            display: flex;
            flex-direction: column;
            gap: 1.25rem;
        }
        #editor-panel.open {
            right: 0;
        }
        #editor-panel .panel-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            border-bottom: 1px solid var(--border-color);
            padding-bottom: 1rem;
        }
        #editor-panel .panel-header h2 {
            font-size: 1.3rem;
            font-weight: 800;
            color: var(--secondary);
        }
        #editor-panel .panel-header .close-editor {
            font-size: 1.5rem;
            cursor: pointer;
            color: var(--text-muted);
            transition: var(--transition);
        }
        #editor-panel .panel-header .close-editor:hover {
            color: var(--primary);
            transform: rotate(90deg);
        }
        #editor-panel .editor-section {
            border-bottom: 1px solid var(--border-color);
            padding-bottom: 1.25rem;
        }
        #editor-panel .editor-section:last-child {
            border-bottom: none;
        }
        #editor-panel .editor-section h3 {
            font-size: 0.9rem;
            font-weight: 700;
            color: var(--secondary);
            margin-bottom: 0.75rem;
            text-transform: uppercase;
            letter-spacing: 1px;
            font-family: var(--font-mono);
            color: var(--primary);
        }
        #editor-panel label {
            font-size: 0.825rem;
            font-weight: 600;
            color: var(--secondary);
            display: block;
            margin-top: 0.5rem;
        }
        #editor-panel input,
        #editor-panel textarea {
            width: 100%;
            padding: 0.6rem 0.8rem;
            background: var(--bg);
            border: 1px solid var(--border-color);
            border-radius: var(--radius-sm);
            color: var(--text);
            font-family: inherit;
            font-size: 0.9rem;
            transition: var(--transition);
            margin-top: 4px;
        }
        #editor-panel input:focus,
        #editor-panel textarea:focus {
            outline: none;
            border-color: var(--primary);
            box-shadow: 0 0 0 3px rgba(37, 99, 235, 0.12);
        }
        #editor-panel textarea {
            resize: vertical;
            min-height: 60px;
        }
        #editor-panel .editor-row {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 0.75rem;
        }
        #editor-panel .btn-sm {
            padding: 0.5rem 1.2rem;
            font-size: 0.8rem;
            border-radius: 8px;
            border: none;
            font-weight: 600;
            cursor: pointer;
            transition: var(--transition);
            background: var(--primary);
            color: #fff;
            width: 100%;
            margin-top: 0.5rem;
        }
        #editor-panel .btn-sm:hover {
            opacity: 0.85;
            transform: translateY(-2px);
        }
        #editor-panel .btn-sm.danger {
            background: #ef4444;
        }
        #editor-panel .btn-sm.danger:hover {
            background: #dc2626;
        }
        #editor-panel .btn-sm.outline {
            background: transparent;
            border: 1px solid var(--border-color);
            color: var(--secondary);
        }
        #editor-panel .btn-sm.outline:hover {
            border-color: var(--primary);
            color: var(--primary);
            background: var(--primary-light);
        }
        #editor-panel .file-upload-wrap {
            position: relative;
            overflow: hidden;
            margin-top: 6px;
        }
        #editor-panel .file-upload-wrap input[type="file"] {
            position: absolute;
            left: 0;
            top: 0;
            opacity: 0;
            width: 100%;
            height: 100%;
            cursor: pointer;
        }
        #editor-panel .file-upload-wrap .fake-btn {
            display: inline-block;
            padding: 0.5rem 1.2rem;
            background: var(--primary-light);
            border: 1px solid var(--border-accent);
            border-radius: 8px;
            color: var(--primary);
            font-weight: 600;
            font-size: 0.8rem;
            cursor: pointer;
            transition: var(--transition);
            width: 100%;
            text-align: center;
        }
        #editor-panel .file-upload-wrap .fake-btn:hover {
            background: var(--primary);
            color: #fff;
        }
        #editor-panel .editor-status {
            font-size: 0.8rem;
            color: var(--accent-green);
            padding: 0.4rem 0.8rem;
            background: rgba(16, 185, 129, 0.10);
            border-radius: 6px;
            display: none;
            align-items: center;
            gap: 8px;
        }
        #editor-panel .editor-status.show {
            display: flex;
        }
        #editor-panel .editor-password {
            display: flex;
            gap: 0.5rem;
            align-items: center;
        }
        #editor-panel .editor-password input {
            flex: 1;
        }
        #editor-panel .editor-password .btn-sm {
            width: auto;
            padding: 0.5rem 1.2rem;
            margin-top: 0;
        }

        /* ==========================================================================
           19.  REVEAL ANIMATIONS
           ========================================================================== */
        .reveal {
            opacity: 0;
            transform: translateY(40px);
            transition: all 0.8s cubic-bezier(0.175, 0.885, 0.32, 1.275);
        }
        .reveal.active {
            opacity: 1;
            transform: translateY(0);
        }

        /* ==========================================================================
           20.  STATS COUNTER
           ========================================================================== */
        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            gap: 1.5rem;
            text-align: center;
            margin-top: 2rem;
        }
        .stat-item .stat-number {
            font-size: 2.8rem;
            font-weight: 800;
            font-family: var(--font-mono);
            color: var(--secondary);
            line-height: 1.2;
        }
        .stat-item .stat-label {
            font-size: 0.85rem;
            color: var(--text-muted);
            font-weight: 500;
        }

        /* ==========================================================================
           21.  RESPONSIVE
           ========================================================================== */
        @media (max-width: 992px) {
            #hero,
            .contact-container {
                grid-template-columns: 1fr;
            }
            .hero-image-wrapper {
                order: -1;
            }
            .hero-title {
                font-size: 2.75rem;
            }
        }
        @media (max-width: 768px) {
            .header-content {
                padding-right: 0;
            }
            .nav-links {
                display: none;
                position: absolute;
                top: 80px;
                left: 0;
                width: 100%;
                background: var(--card);
                backdrop-filter: blur(24px);
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
            section {
                padding: 70px 6%;
            }
            .hero-highlights {
                grid-template-columns: 1fr;
            }
            .whatsapp-btn {
                right: 16px;
                bottom: 16px;
                width: 52px;
                height: 52px;
                font-size: 26px;
            }
            #theme-toggle {
                top: 15px;
                right: 70px;
                width: 40px;
                height: 40px;
                font-size: 16px;
            }
            #editor-toggle {
                bottom: 82px;
                right: 16px;
                width: 46px;
                height: 46px;
                font-size: 18px;
            }
            #editor-panel {
                width: 100%;
                right: -100%;
                padding: 1.5rem 1rem;
            }
            .projects-grid {
                grid-template-columns: 1fr;
            }
            .drawings-grid {
                grid-template-columns: 1fr 1fr;
            }
            .hero-title {
                font-size: 2.2rem;
            }
            .section-title {
                font-size: 1.8rem;
            }
            footer {
                flex-direction: column;
                text-align: center;
            }
            .profile-card {
                max-width: 100%;
            }
            .profile-img-container {
                width: 160px;
                height: 160px;
            }
            .services-grid {
                grid-template-columns: 1fr 1fr;
            }
            .edu-grid {
                grid-template-columns: 1fr;
            }
            .cert-grid {
                grid-template-columns: 1fr 1fr;
            }
            .contact-container {
                gap: 2rem;
            }
            .contact-form {
                padding: 1.5rem;
            }
        }
        @media (max-width: 480px) {
            .services-grid {
                grid-template-columns: 1fr;
            }
            .cert-grid {
                grid-template-columns: 1fr;
            }
            .drawings-grid {
                grid-template-columns: 1fr;
            }
            .hero-title {
                font-size: 1.8rem;
            }
            .stats-grid {
                grid-template-columns: 1fr 1fr;
            }
            #editor-panel .editor-row {
                grid-template-columns: 1fr;
            }
        }

        /* ==========================================================================
           22.  LOADING SPINNER (hidden by default, instant load)
           ========================================================================== */
        #loader {
            display: none;
        }
    </style>
</head>
<body>

    <!-- ============================================================
    THEME TOGGLE
    ============================================================ -->
    <button id="theme-toggle" aria-label="Toggle theme">🌙</button>

    <!-- ============================================================
    EDITOR TOGGLE (slide-out panel)
    ============================================================ -->
    <button id="editor-toggle" aria-label="Open Editor" title="Open Editor (admin)">
        <i class="fas fa-pen-fancy"></i>
    </button>

    <!-- ============================================================
    WHATSAPP FLOATING BUTTON
    ============================================================ -->
    <a href="https://wa.me/920000000000" class="whatsapp-btn" target="_blank" rel="noopener noreferrer" aria-label="Contact on WhatsApp">
        <i class="fab fa-whatsapp"></i>
    </a>

    <!-- ============================================================
    SPOTLIGHT
    ============================================================ -->
    <div class="spotlight"></div>

    <!-- ============================================================
    HEADER
    ============================================================ -->
    <header>
        <div class="header-content">
            <a href="#" class="logo" id="brandLogo">3D Mech<span>Design</span></a>
            <ul class="nav-links" id="navLinks">
                <li><a href="#hero">Home</a></li>
                <li><a href="#skills">Skills</a></li>
                <li><a href="#experience">Experience</a></li>
                <li><a href="#projects">Projects</a></li>
                <li><a href="#services">Services</a></li>
                <li><a href="#testimonials">Testimonials</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
            <div class="menu-toggle" id="menuToggle"><i class="fas fa-bars"></i></div>
        </div>
    </header>

    <!-- ============================================================
    HERO
    ============================================================ -->
    <section id="hero">
        <div>
            <p class="hero-greeting" id="heroGreeting"><i class="fas fa-compass"></i> Welcome to my engineering portfolio</p>
            <h1 class="hero-title">Hi, I'm <span class="text-gradient" id="heroName">Abdur Rafay Yousuf</span></h1>
            <h2 class="hero-subtitle" id="heroSubtitle">Mechanical Engineer &amp; CAD Consultant</h2>
            <p class="hero-bio" id="heroBio">Specializing in parametric product design, complex geometric modeling, gear engineering, and computational fluid dynamics (CFD). Founder of 3D Mech Design based in Karachi, Pakistan.</p>

            <div class="hero-highlights reveal" id="heroMetrics">
                <div class="metric-item">
                    <strong id="metric1Val">100+</strong>
                    <span id="metric1Label">CAD Models</span>
                </div>
                <div class="metric-item">
                    <strong id="metric2Val">4+</strong>
                    <span id="metric2Label">Years Exp.</span>
                </div>
                <div class="metric-item">
                    <strong id="metric3Val">100%</strong>
                    <span id="metric3Label">Precision</span>
                </div>
            </div>

            <div class="hero-btns">
                <a href="#projects" class="btn btn-primary"><i class="fas fa-rocket"></i> View Projects</a>
                <a href="#contact" class="btn btn-secondary"><i class="fas fa-envelope"></i> Contact Me</a>
            </div>
        </div>

        <div class="hero-image-wrapper">
            <div class="profile-card card reveal" id="profileCard">
                <div class="profile-img-container" id="profileImgContainer">
                    <img src="https://via.placeholder.com/220" alt="Profile" id="profileImg" />
                </div>
                <div class="profile-info">
                    <h3 id="profileName">Abdur Rafay Yousuf</h3>
                    <p id="profileTitle">Founder @ 3D Mech Design</p>
                    <div style="margin-top: 10px;">
                        <span class="tag-sm"><i class="fas fa-university"></i> <span id="profileUni">DHA Suffa University</span></span>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- ============================================================
    SKILLS
    ============================================================ -->
    <section id="skills">
        <div class="section-header">
            <span class="section-tag">Core Competencies</span>
            <h2 class="section-title" id="skillsTitle">Technical Expertise</h2>
            <p class="section-subtitle" id="skillsSub">Specialized engineering skills developed through rigorous academic research and professional consulting.</p>
        </div>
        <div class="skills-grid" id="skillsGrid">
            <!-- Skill cards injected by JS -->
        </div>
    </section>

    <!-- ============================================================
    STATS COUNTER
    ============================================================ -->
    <section id="stats" style="padding-top:0;">
        <div class="stats-grid" id="statsGrid">
            <div class="stat-item reveal">
                <div class="stat-number" data-count="128">0</div>
                <div class="stat-label">CAD Projects</div>
            </div>
            <div class="stat-item reveal">
                <div class="stat-number" data-count="24">0</div>
                <div class="stat-label">Happy Clients</div>
            </div>
            <div class="stat-item reveal">
                <div class="stat-number" data-count="15">0</div>
                <div class="stat-label">Research Papers</div>
            </div>
            <div class="stat-item reveal">
                <div class="stat-number" data-count="8">0</div>
                <div class="stat-label">Industry Awards</div>
            </div>
        </div>
    </section>

    <!-- ============================================================
    EXPERIENCE
    ============================================================ -->
    <section id="experience">
        <div class="section-header">
            <span class="section-tag">Professional Timeline</span>
            <h2 class="section-title" id="expTitle">Work &amp; Projects Experience</h2>
        </div>
        <div class="timeline" id="timelineContainer">
            <!-- Injected by JS -->
        </div>
    </section>

    <!-- ============================================================
    PROJECTS
    ============================================================ -->
    <section id="projects">
        <div class="section-header">
            <span class="section-tag">Portfolio</span>
            <h2 class="section-title" id="projectsTitle">Featured Projects</h2>
            <p class="section-subtitle" id="projectsSub">A showcase of advanced engineering applications, thermodynamic research, and robotic integrations.</p>
        </div>

        <div class="filter-menu reveal" id="filterMenu">
            <button class="filter-btn active" data-filter="all">All Projects</button>
            <button class="filter-btn" data-filter="cad">CAD / Mechanical</button>
            <button class="filter-btn" data-filter="thermo">Thermodynamics</button>
            <button class="filter-btn" data-filter="robotics">Robotics</button>
        </div>

        <div class="projects-grid" id="projectsGrid">
            <!-- Injected by JS -->
        </div>

        <h3 class="section-title reveal" style="margin-top:5rem; font-size:1.8rem;">Technical Drawings &amp; Renders</h3>
        <div class="drawings-grid" id="drawingsGrid">
            <!-- Injected by JS -->
        </div>
    </section>

    <!-- ============================================================
    SERVICES
    ============================================================ -->
    <section id="services">
        <div class="section-header">
            <span class="section-tag">What I Offer</span>
            <h2 class="section-title" id="servicesTitle">Consulting Services</h2>
            <p class="section-subtitle" id="servicesSub">Professional mechanical engineering and CAD consulting tailored to your project needs.</p>
        </div>
        <div class="services-grid" id="servicesGrid">
            <!-- Injected by JS -->
        </div>
    </section>

    <!-- ============================================================
    EDUCATION & CERTIFICATIONS
    ============================================================ -->
    <section id="education">
        <div class="section-header">
            <span class="section-tag">Academic</span>
            <h2 class="section-title" id="eduTitle">Education &amp; Certifications</h2>
        </div>
        <div class="edu-grid" id="eduGrid">
            <!-- Injected by JS -->
        </div>
        <div class="cert-grid" id="certGrid">
            <!-- Injected by JS -->
        </div>
    </section>

    <!-- ============================================================
    TESTIMONIALS
    ============================================================ -->
    <section id="testimonials">
        <div class="section-header">
            <span class="section-tag">References</span>
            <h2 class="section-title" id="testTitle">Academic &amp; Professional Feedback</h2>
        </div>
        <div class="testimonials-grid" id="testimonialsGrid">
            <!-- Injected by JS -->
        </div>
    </section>

    <!-- ============================================================
    FAQ
    ============================================================ -->
    <section id="faq">
        <div class="section-header">
            <span class="section-tag">FAQ</span>
            <h2 class="section-title" id="faqTitle">Frequently Asked Questions</h2>
        </div>
        <div class="faq-grid" id="faqGrid">
            <!-- Injected by JS -->
        </div>
    </section>

    <!-- ============================================================
    CONTACT
    ============================================================ -->
    <section id="contact">
        <div class="section-header">
            <span class="section-tag">Get in Touch</span>
            <h2 class="section-title" id="contactTitle">Let's Work Together</h2>
            <p class="section-subtitle" id="contactSub">Available for mechanical design consultation, parametric modeling contracts, and CFD analysis projects.</p>
        </div>

        <div class="contact-container">
            <div class="contact-info reveal">
                <p id="contactIntro">Operating primarily out of Karachi, Pakistan, providing high-quality engineering deliverables globally through <strong>3D Mech Design</strong>.</p>
                <div class="info-list">
                    <div class="info-item">
                        <div class="info-icon"><i class="fas fa-map-marker-alt"></i></div>
                        <div>
                            <strong style="color:var(--secondary);">Location</strong>
                            <p style="margin:0; font-size:0.9rem; color:var(--text-muted);" id="contactLocation">Karachi, Pakistan</p>
                        </div>
                    </div>
                    <div class="info-item">
                        <div class="info-icon"><i class="fas fa-building"></i></div>
                        <div>
                            <strong style="color:var(--secondary);">Consultancy</strong>
                            <p style="margin:0; font-size:0.9rem; color:var(--text-muted);" id="contactConsultancy">3D Mech Design</p>
                        </div>
                    </div>
                    <div class="info-item">
                        <div class="info-icon"><i class="fas fa-envelope"></i></div>
                        <div>
                            <strong style="color:var(--secondary);">Email</strong>
                            <p style="margin:0; font-size:0.9rem; color:var(--text-muted);" id="contactEmail">contact@example.com</p>
                        </div>
                    </div>
                    <div class="info-item">
                        <div class="info-icon"><i class="fas fa-phone"></i></div>
                        <div>
                            <strong style="color:var(--secondary);">Phone</strong>
                            <p style="margin:0; font-size:0.9rem; color:var(--text-muted);" id="contactPhone">+92 300 1234567</p>
                        </div>
                    </div>
                </div>
            </div>

            <div class="contact-form card reveal">
                <form id="contactForm">
                    <div class="form-group">
                        <label>Full Name</label>
                        <input type="text" required placeholder="John Doe" id="formName" />
                    </div>
                    <div class="form-group">
                        <label>Email Address</label>
                        <input type="email" required placeholder="john@example.com" id="formEmail" />
                    </div>
                    <div class="form-group">
                        <label>Project Details</label>
                        <textarea rows="5" required placeholder="Please provide details about your CAD or Engineering requirements..." id="formMessage"></textarea>
                    </div>
                    <button type="submit" class="btn btn-primary" style="width:100%;">Submit Inquiry</button>
                    <div class="alert-success" id="successMsg">
                        <i class="fas fa-check-circle"></i> Message sent successfully! I will reply shortly.
                    </div>
                </form>
            </div>
        </div>
    </section>

    <!-- ============================================================
    FOOTER
    ============================================================ -->
    <footer>
        <div id="footerText">&copy; 2026 Abdur Rafay Yousuf. All rights reserved.</div>
        <div class="social-links" id="socialLinks">
            <a href="#" id="socialLinkedin"><i class="fab fa-linkedin-in"></i></a>
            <a href="#" id="socialGithub"><i class="fab fa-github"></i></a>
            <a href="#" id="socialInstagram"><i class="fab fa-instagram"></i></a>
            <a href="#" id="socialTwitter"><i class="fab fa-x-twitter"></i></a>
        </div>
    </footer>

    <!-- ============================================================
    MODALS
    ============================================================ -->
    <div class="modal" id="modal-battery">
        <div class="modal-container">
            <span class="close-modal">&times;</span>
            <h3 class="modal-title">Thermal Energy Sand Battery</h3>
            <p style="color:var(--text-muted); margin-bottom:1rem;">Technical specifications for the final year thermal energy storage project.</p>
            <table class="spec-table">
                <tr><td>Storage Medium</td><td>Silica Sand</td></tr>
                <tr><td>Core Components</td><td>Insulated Tank, Heat Exchanger Coils</td></tr>
                <tr><td>Application</td><td>Industrial Scale Thermal Storage</td></tr>
                <tr><td>Key Focus</td><td>Thermodynamics &amp; Heat Transfer</td></tr>
            </table>
        </div>
    </div>

    <div class="modal" id="modal-robot">
        <div class="modal-container">
            <span class="close-modal">&times;</span>
            <h3 class="modal-title">Autonomous Line-Following Robot</h3>
            <p style="color:var(--text-muted); margin-bottom:1rem;">Measurement &amp; Instrumentation Lab Project Details.</p>
            <table class="spec-table">
                <tr><td>Microcontroller</td><td>Arduino Uno</td></tr>
                <tr><td>Function</td><td>Real-Time Line Tracking</td></tr>
                <tr><td>Components</td><td>IR Sensors, Motor Drivers</td></tr>
                <tr><td>Focus Area</td><td>Wiring diagrams, Signal Processing</td></tr>
            </table>
        </div>
    </div>

    <div class="modal" id="modal-ice">
        <div class="modal-container">
            <span class="close-modal">&times;</span>
            <h3 class="modal-title">ICE Emissions Research</h3>
            <p style="color:var(--text-muted); margin-bottom:1rem;">Fall 2025 Technical Research Report Data.</p>
            <table class="spec-table">
                <tr><td>Subject</td><td>Internal Combustion Engines</td></tr>
                <tr><td>Primary Focus</td><td>Pollutant Formation Mechanisms</td></tr>
                <tr><td>Output</td><td>Technical Research Document</td></tr>
                <tr><td>Key Findings</td><td>Modern Emission Control Technologies</td></tr>
            </table>
        </div>
    </div>

    <!-- ============================================================
    EDITOR PANEL (SLIDE-OUT)
    ============================================================ -->
    <div id="editor-panel">
        <div class="panel-header">
            <h2><i class="fas fa-pen-fancy" style="color:var(--primary);"></i> Editor Mode</h2>
            <span class="close-editor" id="closeEditor">&times;</span>
        </div>

        <!-- Password lock -->
        <div class="editor-section">
            <h3>🔐 Unlock Editor</h3>
            <div class="editor-password">
                <input type="password" id="editorPassword" placeholder="Enter password" />
                <button class="btn-sm" id="unlockEditorBtn">Unlock</button>
            </div>
            <div id="editorLockStatus" style="font-size:0.8rem; color:var(--text-muted); margin-top:4px;">🔒 Locked</div>
        </div>

        <!-- Profile -->
        <div class="editor-section" id="editorProfileSection">
            <h3>👤 Profile</h3>
            <label>Profile Picture</label>
            <div class="file-upload-wrap">
                <div class="fake-btn"><i class="fas fa-upload"></i> Upload Image</div>
                <input type="file" id="profileUpload" accept="image/*" />
            </div>
            <label>Full Name</label>
            <input type="text" id="editProfileName" value="Abdur Rafay Yousuf" />
            <label>Title</label>
            <input type="text" id="editProfileTitle" value="Founder @ 3D Mech Design" />
            <label>University / Affiliation</label>
            <input type="text" id="editProfileUni" value="DHA Suffa University" />
            <label>Hero Greeting</label>
            <input type="text" id="editHeroGreeting" value="Welcome to my engineering portfolio" />
            <label>Hero Subtitle</label>
            <input type="text" id="editHeroSubtitle" value="Mechanical Engineer &amp; CAD Consultant" />
            <label>Hero Bio</label>
            <textarea id="editHeroBio" rows="2">Specializing in parametric product design, complex geometric modeling, gear engineering, and computational fluid dynamics (CFD). Founder of 3D Mech Design based in Karachi, Pakistan.</textarea>
        </div>

        <!-- Contact -->
        <div class="editor-section">
            <h3>📬 Contact Info</h3>
            <label>Email</label>
            <input type="text" id="editContactEmail" value="contact@example.com" />
            <label>Phone</label>
            <input type="text" id="editContactPhone" value="+92 300 1234567" />
            <label>Location</label>
            <input type="text" id="editContactLocation" value="Karachi, Pakistan" />
            <label>Consultancy Name</label>
            <input type="text" id="editContactConsultancy" value="3D Mech Design" />
        </div>

        <!-- Social -->
        <div class="editor-section">
            <h3>🔗 Social Links</h3>
            <label>LinkedIn URL</label>
            <input type="text" id="editSocialLinkedin" value="#" />
            <label>GitHub URL</label>
            <input type="text" id="editSocialGithub" value="#" />
            <label>Instagram URL</label>
            <input type="text" id="editSocialInstagram" value="#" />
            <label>Twitter / X URL</label>
            <input type="text" id="editSocialTwitter" value="#" />
        </div>

        <!-- Brand -->
        <div class="editor-section">
            <h3>🏷️ Brand</h3>
            <label>Brand Logo Text</label>
            <input type="text" id="editBrandLogo" value="3D MechDesign" />
            <label>Brand Highlight</label>
            <input type="text" id="editBrandHighlight" value="Design" />
            <label>Footer Text</label>
            <input type="text" id="editFooterText" value="&copy; 2026 Abdur Rafay Yousuf. All rights reserved." />
        </div>

        <!-- Actions -->
        <div class="editor-section">
            <h3>⚙️ Actions</h3>
            <div style="display:flex; gap:0.5rem; flex-wrap:wrap;">
                <button class="btn-sm" id="saveEditorBtn"><i class="fas fa-save"></i> Save Changes</button>
                <button class="btn-sm outline" id="resetEditorBtn"><i class="fas fa-undo"></i> Reset Defaults</button>
                <button class="btn-sm danger" id="exportEditorBtn"><i class="fas fa-download"></i> Export Data</button>
            </div>
            <div class="editor-status" id="editorStatus"><i class="fas fa-check-circle"></i> Changes saved!</div>
        </div>
    </div>

    <!-- ============================================================
    JAVASCRIPT — ALL LOGIC, DATA, EDITOR, ANIMATIONS
    ============================================================ -->
    <script>
        /**
         * =====================================================================
         *  DATA STORE — All content is stored here for easy editing.
         *  The editor modifies this data and persists to localStorage.
         * =====================================================================
         */
        const DEFAULT_DATA = {
            profile: {
                name: 'Abdur Rafay Yousuf',
                title: 'Founder @ 3D Mech Design',
                uni: 'DHA Suffa University',
                img: 'https://via.placeholder.com/220',
                heroGreeting: 'Welcome to my engineering portfolio',
                heroSubtitle: 'Mechanical Engineer &amp; CAD Consultant',
                heroBio: 'Specializing in parametric product design, complex geometric modeling, gear engineering, and computational fluid dynamics (CFD). Founder of 3D Mech Design based in Karachi, Pakistan.'
            },
            contact: {
                email: 'contact@example.com',
                phone: '+92 300 1234567',
                location: 'Karachi, Pakistan',
                consultancy: '3D Mech Design'
            },
            social: {
                linkedin: '#',
                github: '#',
                instagram: '#',
                twitter: '#'
            },
            brand: {
                logo: '3D Mech',
                highlight: 'Design',
                footer: '&copy; 2026 Abdur Rafay Yousuf. All rights reserved.'
            },
            metrics: [
                { val: '100+', label: 'CAD Models' },
                { val: '4+', label: 'Years Exp.' },
                { val: '100%', label: 'Precision' }
            ],
            skills: [
                { icon: 'fa-cube', title: '3D CAD Modeling', sub: 'SolidWorks, AutoCAD, Fusion 360',
                    desc: 'Expertise in complex parametric geometric modeling, design tables, feature trees, and generating technical manufacturing drawings.',
                    width: 95 },
                { icon: 'fa-wind', title: 'CFD Analysis', sub: 'Flow Regimes, Velocity &amp; Pressure',
                    desc: 'Performing computational fluid dynamics analysis and generating accurate graphical representations of pressure and velocity distributions.',
                    width: 88 },
                { icon: 'fa-cogs', title: 'Gear Engineering', sub: 'MATLAB &amp; Custom Equations',
                    desc: 'Calculating mathematically accurate involute tooth profiles, diametral pitch, and designing specialized hobbing and inspection arbors.',
                    width: 92 },
                { icon: 'fa-fire-alt', title: 'Thermodynamics', sub: 'Thermal Energy Storage',
                    desc: 'Engaged in advanced thermal energy storage solutions, including sand battery technologies and internal combustion engine emissions control.',
                    width: 85 }
            ],
            experiences: [{
                role: 'Founder &amp; Design Consultant',
                company: '3D Mech Design',
                date: '2025 – Present',
                desc: 'Providing professional mechanical design consultation. Drafting technical proposals, flyers, and operating comprehensive parametric modeling projects for industry clients. Leading design architecture and modeling processes.',
                tags: ['Consulting', 'CAD', 'Parametric Design']
            }, {
                role: 'Lead Engineer',
                company: 'Mahfooz Wheelchair Project',
                date: '2025 – 2026',
                desc: 'Developed a locally producible mobility device featuring stair-lifting capabilities inspired by personal family challenges. Conducted user surveys and received official startup recognition from the Sindh Higher Education Commission.',
                tags: ['Prototyping', 'Accessibility', 'Innovation']
            }, {
                role: 'CAD Mentor &amp; Supervisor',
                company: 'Community Skill-Sharing',
                date: '2026',
                desc: 'Mentored junior engineering associates (including Faizan Khan) directly in advanced computer-aided design skills, logging community engagement records and fostering practical design logic among upcoming engineers.',
                tags: ['Mentorship', 'SolidWorks', 'Leadership']
            }],
            projects: [{
                title: 'Thermal Energy Sand Battery',
                desc: 'Final year design project featuring a physical layout consisting of an insulated silica sand tank, internal heat exchanger coils, and precision instrumentation sensors for industrial energy storage applications.',
                category: 'thermo',
                tags: ['Energy Storage', 'Thermodynamics'],
                img: 'https://via.placeholder.com/400x250',
                modal: 'modal-battery'
            }, {
                title: 'Autonomous Line-Following Robot',
                desc: 'Developed for Measurement and Instrumentation Lab. System features real-time processing code, complex wiring diagrams, and integrated sensor feedback mechanisms.',
                category: 'robotics',
                tags: ['Robotics', 'Arduino Uno'],
                img: 'https://via.placeholder.com/400x250',
                modal: 'modal-robot'
            }, {
                title: 'ICE Emissions Research Report',
                desc: 'A formal engineering document analyzing pollutant formation mechanisms and modern emission control technologies in Internal Combustion Engines.',
                category: 'thermo',
                tags: ['Research', 'IC Engines'],
                img: 'https://via.placeholder.com/400x250',
                modal: 'modal-ice'
            }],
            drawings: [
                { title: 'Gear Arbor Profile', sub: 'Involute Tooth / Pitch Dia Calc' },
                { title: 'CFD Analysis Plot', sub: 'Pressure &amp; Velocity Distribution' },
                { title: 'Wheelchair Mechanism', sub: 'Mahfooz Project Stair-Lift' },
                { title: 'Engineering Economics', sub: 'PSX Transaction Log Analysis' }
            ],
            services: [
                { icon: 'fa-cube', title: '3D Parametric Modeling',
                desc: 'High-precision CAD models for manufacturing and prototyping.' },
                { icon: 'fa-chart-line', title: 'CFD &amp; Thermal Analysis',
                    desc: 'Simulation of fluid dynamics and heat transfer for design optimization.' },
                { icon: 'fa-cogs', title: 'Gear &amp; Mechanical Systems',
                    desc: 'Custom gear design, mechanical system analysis, and hobbing solutions.' },
                { icon: 'fa-file-alt', title: 'Technical Documentation',
                    desc: 'Comprehensive reports, proposals, and manufacturing drawings.' }
            ],
            education: [
                { title: 'B.E. Mechanical Engineering', meta: 'DHA Suffa University, Karachi',
                desc: 'Specialization in Thermodynamics, Fluid Mechanics, and Machine Design.' },
                { title: 'CAD Professional Certification', meta: 'SolidWorks &amp; AutoCAD',
                    desc: 'Advanced training in parametric modeling and 2D/3D drafting.' }
            ],
            certifications: [
                { icon: 'fa-certificate', title: 'SolidWorks Professional', date: '2025' },
                { icon: 'fa-certificate', title: 'CFD Fundamentals', date: '2025' },
                { icon: 'fa-certificate', title: 'Gear Design Specialist', date: '2026' }
            ],
            testimonials: [{
                text: '"Abdur Rafay demonstrates exceptional diligence in complex design architecture. His work on the Thermal Sand Battery and computational fluid dynamics sets a high standard for mechanical engineering students."',
                author: 'Dr. Usama',
                role: 'University Professor, DHA Suffa University'
            }, {
                text: '"Collaborating with Rafay on lab projects has been incredible. His precision in SolidWorks and ability to translate mathematical gear equations into working CAD models is unmatched."',
                author: 'Ayaan Amir',
                role: 'Classmate &amp; Project Collaborator'
            }, {
                text: '"The mentorship provided by Rafay in computer-aided design has been invaluable to my growth. He breaks down complex geometric modeling into understandable, practical logic."',
                author: 'Faizan Khan',
                role: 'Junior Associate &amp; Mentee'
            }],
            faq: [
                { q: 'What CAD software do you specialize in?',
                    a: 'I work primarily with SolidWorks, AutoCAD, and Fusion 360 for 3D parametric modeling and technical drafting.' },
                { q: 'Do you offer CFD analysis services?',
                    a: 'Yes, I perform computational fluid dynamics analysis for a variety of applications including pressure and velocity distribution studies.' },
                { q: 'Can you help with gear design and manufacturing?',
                    a: 'Absolutely. I specialize in involute tooth geometry, diametral pitch calculations, and custom hobbing arbor design.' },
                { q: 'What is your typical project turnaround time?',
                    a: 'Turnaround time depends on complexity, but most projects are delivered within 5–15 business days.' }
            ]
        };

        // =====================================================================
        //  STATE
        // =====================================================================
        let appData = {};
        let editorUnlocked = false;
        const EDITOR_PASSWORD = 'admin123'; // change this to your own password

        // =====================================================================
        //  HELPERS
        // =====================================================================
        function deepClone(obj) { return JSON.parse(JSON.stringify(obj)); }

        function loadData() {
            const stored = localStorage.getItem('cad_portfolio_data');
            if (stored) {
                try {
                    const parsed = JSON.parse(stored);
                    appData = deepMerge(DEFAULT_DATA, parsed);
                    return;
                } catch (_) { /* fall through */ }
            }
            appData = deepClone(DEFAULT_DATA);
        }

        function deepMerge(target, source) {
            const result = deepClone(target);
            for (const key in source) {
                if (source.hasOwnProperty(key)) {
                    if (typeof source[key] === 'object' && source[key] !== null && !Array.isArray(source[key])) {
                        result[key] = deepMerge(result[key] || {}, source[key]);
                    } else {
                        result[key] = source[key];
                    }
                }
            }
            return result;
        }

        function saveData() {
            localStorage.setItem('cad_portfolio_data', JSON.stringify(appData));
        }

        function getProfileImg() {
            return appData.profile.img || 'https://via.placeholder.com/220';
        }

        // =====================================================================
        //  RENDER FUNCTIONS
        // =====================================================================
        function renderProfile() {
            const p = appData.profile;
            document.getElementById('profileImg').src = getProfileImg();
            document.getElementById('profileName').textContent = p.name;
            document.getElementById('profileTitle').textContent = p.title;
            document.getElementById('profileUni').textContent = p.uni;
            document.getElementById('heroGreeting').innerHTML = '<i class="fas fa-compass"></i> ' + p.heroGreeting;
            document.getElementById('heroName').textContent = p.name;
            document.getElementById('heroSubtitle').textContent = p.heroSubtitle;
            document.getElementById('heroBio').textContent = p.heroBio;

            // Metrics
            const m = appData.metrics;
            if (m.length >= 3) {
                document.getElementById('metric1Val').textContent = m[0].val;
                document.getElementById('metric1Label').textContent = m[0].label;
                document.getElementById('metric2Val').textContent = m[1].val;
                document.getElementById('metric2Label').textContent = m[1].label;
                document.getElementById('metric3Val').textContent = m[2].val;
                document.getElementById('metric3Label').textContent = m[2].label;
            }
        }

        function renderSkills() {
            const container = document.getElementById('skillsGrid');
            container.innerHTML = '';
            appData.skills.forEach((sk, idx) => {
                const div = document.createElement('div');
                div.className = 'skill-card reveal';
                div.setAttribute('data-skill-idx', idx);
                div.innerHTML = `
              <div class="skill-icon-header">
                <div class="skill-icon"><i class="fas ${sk.icon}"></i></div>
                <div class="skill-title-group">
                  <h3>${sk.title}</h3>
                  <span>${sk.sub}</span>
                </div>
              </div>
              <p class="skill-desc">${sk.desc}</p>
              <div class="progress-bar"><div class="progress-fill" style="--skill-width:${sk.width}%;"></div></div>
            `;
                container.appendChild(div);
            });
            // Re-run reveal observer for new cards
            setTimeout(() => {
                document.querySelectorAll('.skill-card.reveal').forEach(el => {
                    if (el.getBoundingClientRect().top < window.innerHeight * 0.85) {
                        el.classList.add('active');
                    }
                });
            }, 100);
        }

        function renderExperience() {
            const container = document.getElementById('timelineContainer');
            container.innerHTML = '';
            const icons = ['fa-briefcase', 'fa-wheelchair', 'fa-chalkboard-teacher'];
            appData.experiences.forEach((exp, idx) => {
                const item = document.createElement('div');
                item.className = 'timeline-item reveal';
                item.innerHTML = `
              <div class="timeline-icon"><i class="fas ${icons[idx % icons.length]}"></i></div>
              <div class="timeline-content card">
                <div class="timeline-header" style="display:flex; justify-content:space-between; flex-wrap:wrap; gap:0.5rem;">
                  <div>
                    <h3 class="timeline-role">${exp.role}</h3>
                    <span class="timeline-company">${exp.company}</span>
                  </div>
                  <span class="timeline-date">${exp.date}</span>
                </div>
                <div class="timeline-body">
                  <p>${exp.desc}</p>
                  <div class="timeline-tags">${exp.tags.map(t => `<span class="tag-sm">${t}</span>`).join('')}</div>
                </div>
              </div>
            `;
                container.appendChild(item);
            });
        }

        function renderProjects() {
            const container = document.getElementById('projectsGrid');
            container.innerHTML = '';
            appData.projects.forEach((proj, idx) => {
                const card = document.createElement('div');
                card.className = 'project-card card reveal';
                card.setAttribute('data-category', proj.category);
                card.innerHTML = `
              <div class="project-img"><img src="${proj.img}" alt="${proj.title}" loading="lazy" /></div>
              <div class="project-content">
                <div>${proj.tags.map(t => `<span class="tag">${t}</span>`).join('')}</div>
                <h3 class="project-title">${proj.title}</h3>
                <p class="project-desc">${proj.desc}</p>
                <button class="project-link open-modal" data-target="${proj.modal}">View Specs <i class="fas fa-arrow-right"></i></button>
              </div>
            `;
                container.appendChild(card);
            });
            // Re-bind modal triggers
            document.querySelectorAll('.open-modal').forEach(btn => {
                btn.addEventListener('click', function(e) {
                    e.preventDefault();
                    const target = this.getAttribute('data-target');
                    document.getElementById(target).classList.add('show');
                });
            });
        }

        function renderDrawings() {
            const container = document.getElementById('drawingsGrid');
            container.innerHTML = '';
            appData.drawings.forEach(d => {
                const div = document.createElement('div');
                div.className = 'drawing-item reveal';
                // Use a placeholder image with a subtle gradient
                const color = '#' + Math.floor(Math.random() * 16777215).toString(16).padStart(6, '0');
                div.innerHTML = `
              <img src="https://via.placeholder.com/400x300/${color.replace('#','')}/ffffff?text=${encodeURIComponent(d.title)}" alt="${d.title}" loading="lazy" />
              <div class="drawing-overlay">
                <h4>${d.title}</h4>
                <p style="font-size:0.8rem; margin-top:5px;">${d.sub}</p>
              </div>
            `;
                container.appendChild(div);
            });
        }

        function renderServices() {
            const container = document.getElementById('servicesGrid');
            container.innerHTML = '';
            appData.services.forEach(s => {
                const div = document.createElement('div');
                div.className = 'service-card card reveal';
                div.innerHTML = `
              <div class="service-icon"><i class="fas ${s.icon}"></i></div>
              <h3>${s.title}</h3>
              <p>${s.desc}</p>
            `;
                container.appendChild(div);
            });
        }

        function renderEducation() {
            const container = document.getElementById('eduGrid');
            container.innerHTML = '';
            appData.education.forEach(e => {
                const div = document.createElement('div');
                div.className = 'edu-card card reveal';
                div.innerHTML = `
              <h3>${e.title}</h3>
              <div class="meta">${e.meta}</div>
              <p>${e.desc}</p>
            `;
                container.appendChild(div);
            });
            const certContainer = document.getElementById('certGrid');
            certContainer.innerHTML = '';
            appData.certifications.forEach(c => {
                const div = document.createElement('div');
                div.className = 'cert-card card reveal';
                div.innerHTML = `
              <i class="fas ${c.icon}"></i>
              <h4>${c.title}</h4>
              <span>${c.date}</span>
            `;
                certContainer.appendChild(div);
            });
        }

        function renderTestimonials() {
            const container = document.getElementById('testimonialsGrid');
            container.innerHTML = '';
            appData.testimonials.forEach(t => {
                const div = document.createElement('div');
                div.className = 'testimonial-card card reveal';
                const initial = t.author.charAt(0).toUpperCase();
                div.innerHTML = `
              <i class="fas fa-quote-left quote-icon"></i>
              <p class="testimonial-text">${t.text}</p>
              <div class="author-group">
                <div class="author-avatar">${initial}</div>
                <div class="author-details">
                  <h4>${t.author}</h4>
                  <span>${t.role}</span>
                </div>
              </div>
            `;
                container.appendChild(div);
            });
        }

        function renderFAQ() {
            const container = document.getElementById('faqGrid');
            container.innerHTML = '';
            appData.faq.forEach((item, idx) => {
                const div = document.createElement('div');
                div.className = 'faq-item card reveal';
                div.innerHTML = `
              <div class="faq-q">
                <span>${item.q}</span>
                <i class="fas fa-chevron-down"></i>
              </div>
              <div class="faq-a">${item.a}</div>
            `;
                div.addEventListener('click', function() {
                    this.classList.toggle('open');
                });
                container.appendChild(div);
            });
        }

        function renderContact() {
            const c = appData.contact;
            document.getElementById('contactLocation').textContent = c.location;
            document.getElementById('contactConsultancy').textContent = c.consultancy;
            document.getElementById('contactEmail').textContent = c.email;
            document.getElementById('contactPhone').textContent = c.phone;
            document.getElementById('contactIntro').innerHTML =
                'Operating primarily out of ' + c.location +
                ', providing high-quality engineering deliverables globally through <strong>' + c.consultancy +
                '</strong>.';
        }

        function renderSocial() {
            const s = appData.social;
            document.getElementById('socialLinkedin').href = s.linkedin;
            document.getElementById('socialGithub').href = s.github;
            document.getElementById('socialInstagram').href = s.instagram;
            document.getElementById('socialTwitter').href = s.twitter;
        }

        function renderBrand() {
            const b = appData.brand;
            document.getElementById('brandLogo').innerHTML = b.logo + ' <span>' + b.highlight + '</span>';
            document.getElementById('footerText').innerHTML = b.footer;
        }

        function renderAll() {
            renderProfile();
            renderSkills();
            renderExperience();
            renderProjects();
            renderDrawings();
            renderServices();
            renderEducation();
            renderTestimonials();
            renderFAQ();
            renderContact();
            renderSocial();
            renderBrand();
            // Re-run reveal after render
            setTimeout(() => {
                document.querySelectorAll('.reveal').forEach(el => {
                    if (el.getBoundingClientRect().top < window.innerHeight * 0.85) {
                        el.classList.add('active');
                    }
                });
            }, 200);
            // Trigger skill bar animation
            setTimeout(() => {
                document.querySelectorAll('.skill-card').forEach(card => {
                    card.classList.add('active');
                });
            }, 400);
        }

        // =====================================================================
        //  EDITOR — Populate fields from data
        // =====================================================================
        function populateEditorFields() {
            const p = appData.profile;
            document.getElementById('editProfileName').value = p.name;
            document.getElementById('editProfileTitle').value = p.title;
            document.getElementById('editProfileUni').value = p.uni;
            document.getElementById('editHeroGreeting').value = p.heroGreeting;
            document.getElementById('editHeroSubtitle').value = p.heroSubtitle;
            document.getElementById('editHeroBio').value = p.heroBio;

            const c = appData.contact;
            document.getElementById('editContactEmail').value = c.email;
            document.getElementById('editContactPhone').value = c.phone;
            document.getElementById('editContactLocation').value = c.location;
            document.getElementById('editContactConsultancy').value = c.consultancy;

            const s = appData.social;
            document.getElementById('editSocialLinkedin').value = s.linkedin;
            document.getElementById('editSocialGithub').value = s.github;
            document.getElementById('editSocialInstagram').value = s.instagram;
            document.getElementById('editSocialTwitter').value = s.twitter;

            const b = appData.brand;
            document.getElementById('editBrandLogo').value = b.logo;
            document.getElementById('editBrandHighlight').value = b.highlight;
            document.getElementById('editFooterText').value = b.footer;
        }

        function applyEditorChanges() {
            const p = appData.profile;
            p.name = document.getElementById('editProfileName').value.trim() || p.name;
            p.title = document.getElementById('editProfileTitle').value.trim() || p.title;
            p.uni = document.getElementById('editProfileUni').value.trim() || p.uni;
            p.heroGreeting = document.getElementById('editHeroGreeting').value.trim() || p.heroGreeting;
            p.heroSubtitle = document.getElementById('editHeroSubtitle').value.trim() || p.heroSubtitle;
            p.heroBio = document.getElementById('editHeroBio').value.trim() || p.heroBio;

            const c = appData.contact;
            c.email = document.getElementById('editContactEmail').value.trim() || c.email;
            c.phone = document.getElementById('editContactPhone').value.trim() || c.phone;
            c.location = document.getElementById('editContactLocation').value.trim() || c.location;
            c.consultancy = document.getElementById('editContactConsultancy').value.trim() || c.consultancy;

            const s = appData.social;
            s.linkedin = document.getElementById('editSocialLinkedin').value.trim() || s.linkedin;
            s.github = document.getElementById('editSocialGithub').value.trim() || s.github;
            s.instagram = document.getElementById('editSocialInstagram').value.trim() || s.instagram;
            s.twitter = document.getElementById('editSocialTwitter').value.trim() || s.twitter;

            const b = appData.brand;
            b.logo = document.getElementById('editBrandLogo').value.trim() || b.logo;
            b.highlight = document.getElementById('editBrandHighlight').value.trim() || b.highlight;
            b.footer = document.getElementById('editFooterText').value.trim() || b.footer;

            saveData();
            renderAll();
            // Show status
            const status = document.getElementById('editorStatus');
            status.classList.add('show');
            setTimeout(() => status.classList.remove('show'), 3000);
        }

        function resetToDefaults() {
            if (confirm('Reset all content to default values? This cannot be undone.')) {
                appData = deepClone(DEFAULT_DATA);
                saveData();
                renderAll();
                populateEditorFields();
                const status = document.getElementById('editorStatus');
                status.textContent = '✓ Reset to defaults';
                status.classList.add('show');
                setTimeout(() => status.classList.remove('show'), 3000);
            }
        }

        function exportData() {
            const blob = new Blob([JSON.stringify(appData, null, 2)], { type: 'application/json' });
            const url = URL.createObjectURL(blob);
            const a = document.createElement('a');
            a.href = url;
            a.download = 'cad_portfolio_backup.json';
            a.click();
            URL.revokeObjectURL(url);
        }

        // =====================================================================
        //  IMAGE UPLOAD (base64)
        // =====================================================================
        function handleImageUpload(file) {
            const reader = new FileReader();
            reader.onload = function(e) {
                const base64 = e.target.result;
                appData.profile.img = base64;
                saveData();
                renderProfile();
                const status = document.getElementById('editorStatus');
                status.textContent = '✓ Profile picture updated!';
                status.classList.add('show');
                setTimeout(() => status.classList.remove('show'), 3000);
            };
            reader.readAsDataURL(file);
        }

        // =====================================================================
        //  STATS COUNTER ANIMATION
        // =====================================================================
        function animateCounters() {
            const counters = document.querySelectorAll('.stat-number');
            const observer = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        const el = entry.target;
                        const target = parseInt(el.getAttribute('data-count'));
                        let current = 0;
                        const increment = Math.ceil(target / 60);
                        const timer = setInterval(() => {
                            current += increment;
                            if (current >= target) {
                                el.textContent = target;
                                clearInterval(timer);
                            } else {
                                el.textContent = current;
                            }
                        }, 25);
                        observer.unobserve(el);
                    }
                });
            }, { threshold: 0.5 });
            counters.forEach(c => observer.observe(c));
        }

        // =====================================================================
        //  INIT
        // =====================================================================
        function init() {
            loadData();
            renderAll();
            populateEditorFields();
            animateCounters();

            // --- Theme toggle ---
            const themeToggle = document.getElementById('theme-toggle');
            const savedTheme = localStorage.getItem('theme');
            if (savedTheme) {
                document.documentElement.setAttribute('data-theme', savedTheme);
                themeToggle.innerHTML = savedTheme === 'dark' ? '☀️' : '🌙';
            }
            themeToggle.addEventListener('click', function() {
                const isDark = document.documentElement.getAttribute('data-theme') === 'dark';
                const newTheme = isDark ? 'light' : 'dark';
                document.documentElement.setAttribute('data-theme', newTheme);
                localStorage.setItem('theme', newTheme);
                this.innerHTML = newTheme === 'dark' ? '☀️' : '🌙';
            });

            // --- Mobile menu ---
            document.getElementById('menuToggle').addEventListener('click', function() {
                const nav = document.getElementById('navLinks');
                nav.classList.toggle('active');
                const icon = this.querySelector('i');
                icon.classList.toggle('fa-bars');
                icon.classList.toggle('fa-times');
            });

            // --- Editor panel ---
            const editorPanel = document.getElementById('editor-panel');
            const editorToggle = document.getElementById('editor-toggle');
            const closeEditor = document.getElementById('closeEditor');

            function openEditor() {
                editorPanel.classList.add('open');
                editorToggle.classList.add('active');
                populateEditorFields();
            }

            function closeEditorPanel() {
                editorPanel.classList.remove('open');
                editorToggle.classList.remove('active');
            }

            editorToggle.addEventListener('click', function() {
                if (editorPanel.classList.contains('open')) {
                    closeEditorPanel();
                } else {
                    openEditor();
                }
            });
            closeEditor.addEventListener('click', closeEditorPanel);

            // --- Editor unlock ---
            const unlockBtn = document.getElementById('unlockEditorBtn');
            const pwInput = document.getElementById('editorPassword');
            const lockStatus = document.getElementById('editorLockStatus');

            function checkUnlock() {
                if (pwInput.value === EDITOR_PASSWORD) {
                    editorUnlocked = true;
                    lockStatus.textContent = '✅ Unlocked — editing enabled';
                    lockStatus.style.color = 'var(--accent-green)';
                    document.querySelectorAll('#editor-panel input, #editor-panel textarea, #editor-panel .file-upload-wrap')
                        .forEach(el => el.disabled = false);
                    document.querySelectorAll('#editor-panel input, #editor-panel textarea').forEach(el => el.style
                        .opacity = '1');
                    document.querySelectorAll('#editor-panel .btn-sm:not(#unlockEditorBtn)').forEach(el => el.style
                        .opacity = '1');
                    pwInput.value = '';
                } else {
                    editorUnlocked = false;
                    lockStatus.textContent = '🔒 Locked — incorrect password';
                    lockStatus.style.color = '#ef4444';
                    document.querySelectorAll('#editor-panel input, #editor-panel textarea, #editor-panel .file-upload-wrap')
                        .forEach(el => el.disabled = true);
                    document.querySelectorAll('#editor-panel input, #editor-panel textarea').forEach(el => el.style
                        .opacity = '0.5');
                    document.querySelectorAll('#editor-panel .btn-sm:not(#unlockEditorBtn)').forEach(el => el.style
                        .opacity = '0.5');
                }
            }

            // Initially lock all editor fields
            document.querySelectorAll('#editor-panel input, #editor-panel textarea, #editor-panel .file-upload-wrap')
                .forEach(el => el.disabled = true);
            document.querySelectorAll('#editor-panel input, #editor-panel textarea').forEach(el => el.style.opacity =
            '0.5');
            document.querySelectorAll('#editor-panel .btn-sm:not(#unlockEditorBtn)').forEach(el => el.style.opacity =
                '0.5');

            unlockBtn.addEventListener('click', checkUnlock);
            pwInput.addEventListener('keydown', function(e) { if (e.key === 'Enter') checkUnlock(); });

            // --- Editor save ---
            document.getElementById('saveEditorBtn').addEventListener('click', function() {
                if (!editorUnlocked) { alert('Please unlock the editor first.'); return; }
                applyEditorChanges();
            });

            // --- Reset ---
            document.getElementById('resetEditorBtn').addEventListener('click', function() {
                if (!editorUnlocked) { alert('Please unlock the editor first.'); return; }
                resetToDefaults();
            });

            // --- Export ---
            document.getElementById('exportEditorBtn').addEventListener('click', function() {
                if (!editorUnlocked) { alert('Please unlock the editor first.'); return; }
                exportData();
            });

            // --- Profile image upload ---
            document.getElementById('profileUpload').addEventListener('change', function(e) {
                if (!editorUnlocked) { alert('Please unlock the editor first.'); return; }
                const file = e.target.files[0];
                if (file) handleImageUpload(file);
                this.value = '';
            });

            // --- Form submission ---
            document.getElementById('contactForm').addEventListener('submit', function(e) {
                e.preventDefault();
                const btn = this.querySelector('button');
                const original = btn.innerHTML;
                btn.innerHTML = '<i class="fas fa-circle-notch fa-spin"></i> Sending...';
                setTimeout(() => {
                    btn.innerHTML = original;
                    const msg = document.getElementById('successMsg');
                    msg.classList.add('show');
                    this.reset();
                    setTimeout(() => msg.classList.remove('show'), 5000);
                }, 1500);
            });

            // --- Modal close ---
            document.querySelectorAll('.close-modal').forEach(btn => {
                btn.addEventListener('click', function() {
                    document.querySelectorAll('.modal').forEach(m => m.classList.remove('show'));
                });
            });
            window.addEventListener('click', function(e) {
                document.querySelectorAll('.modal').forEach(m => {
                    if (e.target === m) m.classList.remove('show');
                });
            });

            // --- Spotlight ---
            const spotlight = document.querySelector('.spotlight');
            document.addEventListener('mousemove', function(e) {
                if (spotlight) {
                    spotlight.style.setProperty('--x', e.clientX + 'px');
                    spotlight.style.setProperty('--y', e.clientY + 'px');
                }
            });

            // --- Reveal observer ---
            const revealObs = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.classList.add('active');
                    }
                });
            }, { threshold: 0.15 });
            document.querySelectorAll('.reveal').forEach(el => revealObs.observe(el));

            // --- Filter buttons ---
            document.querySelectorAll('.filter-btn').forEach(btn => {
                btn.addEventListener('click', function() {
                    document.querySelectorAll('.filter-btn').forEach(b => b.classList.remove('active'));
                    this.classList.add('active');
                    const filter = this.getAttribute('data-filter');
                    document.querySelectorAll('.project-card').forEach(card => {
                        if (filter === 'all' || card.getAttribute('data-category') === filter) {
                            card.style.display = 'flex';
                            setTimeout(() => card.classList.add('active'), 50);
                        } else {
                            card.style.display = 'none';
                            card.classList.remove('active');
                        }
                    });
                });
            });
        }

        // Run on DOM ready
        if (document.readyState === 'loading') {
            document.addEventListener('DOMContentLoaded', init);
        } else {
            init();
        }
    </script>

</body>
</html>
