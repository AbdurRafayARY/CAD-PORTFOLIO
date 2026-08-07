<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Abdur Rafay Yousuf | Mechanical Engineer & CAD Consultant</title>
    
    <!-- Font Awesome 6 & Google Fonts -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;500;600;700&family=Plus+Jakarta+Sans:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">

    <style>
        /* ==========================================================================
           1. PREMIUM DESIGN SYSTEM & VARIABLES (LIGHT/DARK MODE)
           ========================================================================== */
        :root {
            --bg: #f8fafc;
            --bg2: #eef6ff;
            --text: #0f172a;
            --primary: #2563eb;
            --card: rgba(255, 255, 255, 0.65);
            
            --primary-hover: #1d4ed8;
            --primary-light: rgba(37, 99, 235, 0.1);
            --secondary: #0f172a;
            --text-muted: #64748b;
            --accent-green: #059669;
            --border-color: rgba(15, 23, 42, 0.1);
            --border-accent: rgba(37, 99, 235, 0.3);
            --grid-line: rgba(37, 99, 235, 0.06);

            --font-main: 'Plus Jakarta Sans', sans-serif;
            --font-mono: 'JetBrains Mono', monospace;
            --shadow-sm: 0 1px 3px rgba(0, 0, 0, 0.05);
            --shadow-md: 0 10px 40px rgba(0, 0, 0, 0.08);
            --shadow-hover: 0 20px 60px rgba(37, 99, 235, 0.15);
            --transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
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
            --border-accent: rgba(79, 155, 255, 0.3);
            --grid-line: rgba(79, 155, 255, 0.08);
            
            --shadow-md: 0 10px 40px rgba(0, 0, 0, 0.3);
            --shadow-hover: 0 20px 60px rgba(79, 155, 255, 0.25);
        }

        /* Scrollbar */
        ::-webkit-scrollbar { width: 10px; }
        ::-webkit-scrollbar-track { background: var(--bg); }
        ::-webkit-scrollbar-thumb { background: var(--border-accent); border-radius: 10px; }
        ::-webkit-scrollbar-thumb:hover { background: var(--primary); }

        * { margin: 0; padding: 0; box-sizing: border-box; }
        html { scroll-behavior: smooth; }

        /* ==========================================================================
           2. PREMIUM BACKGROUND: MESH + AURORA
           ========================================================================== */
        body {
            color: var(--text);
            background: 
                radial-gradient(circle at 10% 20%, rgba(37,99,235,0.15), transparent 35%),
                radial-gradient(circle at 90% 20%, rgba(0,212,255,0.12), transparent 30%),
                radial-gradient(circle at 50% 90%, rgba(139,92,246,0.15), transparent 35%),
                linear-gradient(135deg, var(--bg), var(--bg2));
            background-size: cover;
            background-attachment: fixed;
            min-height: 100vh;
            font-family: var(--font-main);
            line-height: 1.6;
            overflow-x: hidden;
            position: relative;
        }

        /* Animated Aurora */
        body::before {
            content: "";
            position: fixed;
            inset: -20%;
            background: 
                radial-gradient(circle, rgba(37,99,235,0.15) 0%, transparent 40%),
                radial-gradient(circle, rgba(6,182,212,0.15) 0%, transparent 35%),
                radial-gradient(circle, rgba(139,92,246,0.15) 0%, transparent 40%);
            filter: blur(120px);
            animation: aurora 30s linear infinite alternate;
            z-index: -2;
            pointer-events: none;
        }

        @keyframes aurora {
            0% { transform: translate(-10%, -5%) rotate(0deg); }
            100% { transform: translate(10%, 8%) rotate(20deg); }
        }

        /* Mouse-Following Spotlight */
        .spotlight {
            position: fixed;
            inset: 0;
            pointer-events: none;
            z-index: 9998;
            background: radial-gradient(600px circle at var(--x, 50%) var(--y, 50%), rgba(255,255,255,0.06), transparent 40%);
        }

        /* ==========================================================================
           3. GLASSMORPHISM & 3D CARDS
           ========================================================================== */
        .card, .project-card, .skill-card, .testimonial-card, .drawing-item, .modal-container {
            background: var(--card);
            backdrop-filter: blur(18px);
            -webkit-backdrop-filter: blur(18px);
            border: 1px solid var(--border-color);
            border-radius: 20px;
            box-shadow: var(--shadow-md);
            transition: var(--transition);
            transform: perspective(1000px) rotateX(0) rotateY(0) scale3d(1, 1, 1);
        }

        .card:hover, .project-card:hover, .skill-card:hover, .testimonial-card:hover, .drawing-item:hover {
            transform: perspective(1000px) translateY(-8px) rotateX(2deg) rotateY(-2deg) scale3d(1.02, 1.02, 1.02);
            box-shadow: var(--shadow-hover);
            border-color: var(--border-accent);
        }

        /* ==========================================================================
           4. LAYOUT & TYPOGRAPHY
           ========================================================================== */
        section { padding: 90px 8%; max-width: 1320px; margin: 0 auto; position: relative; }

        .section-header { margin-bottom: 3.5rem; }
        .section-tag {
            display: inline-flex; align-items: center; gap: 0.5rem;
            font-family: var(--font-mono); color: var(--primary); font-size: 0.85rem;
            font-weight: 600; text-transform: uppercase; letter-spacing: 1px;
            margin-bottom: 0.5rem; background: var(--primary-light);
            padding: 0.25rem 0.75rem; border-radius: 6px; border: 1px solid var(--border-accent);
        }
        .section-title { font-size: 2.25rem; font-weight: 800; color: var(--secondary); letter-spacing: -0.02em; }
        .section-subtitle { color: var(--text-muted); margin-top: 0.5rem; font-size: 1.05rem; max-width: 620px; }

        /* Gradient Text Effect */
        .text-gradient {
            background: linear-gradient(to right, var(--primary), #8b5cf6, var(--primary));
            background-size: 200% auto;
            color: transparent;
            -webkit-background-clip: text;
            background-clip: text;
            animation: textShine 4s linear infinite;
        }
        @keyframes textShine { to { background-position: 200% center; } }

        /* ==========================================================================
           5. BUTTONS & TOGGLES
           ========================================================================== */
        .btn {
            display: inline-flex; align-items: center; justify-content: center;
            gap: 0.6rem; padding: 0.85rem 1.6rem; border-radius: 12px;
            font-weight: 600; font-size: 0.95rem; text-decoration: none;
            cursor: pointer; transition: var(--transition); border: 1px solid transparent;
        }
        .btn-primary {
            background: linear-gradient(45deg, var(--primary), #8b5cf6, var(--primary));
            background-size: 200% 100%;
            animation: btnGradient 4s ease infinite;
            color: #ffffff;
            box-shadow: 0 4px 14px rgba(37, 99, 235, 0.25);
            border: 1px solid rgba(255,255,255,0.1);
        }
        @keyframes btnGradient {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }
        .btn-primary:hover { transform: translateY(-3px) scale(1.02); box-shadow: 0 8px 25px rgba(139, 92, 246, 0.4); }
        .btn-secondary { background: var(--card); color: var(--secondary); border-color: var(--border-color); backdrop-filter: blur(10px); }
        .btn-secondary:hover { border-color: var(--primary); color: var(--primary); background: var(--primary-light); transform: translateY(-3px); }

        #theme-toggle {
            position: fixed; top: 25px; right: 25px; width: 50px; height: 50px;
            border: 1px solid var(--border-color); border-radius: 50%; cursor: pointer;
            font-size: 20px; background: var(--card); backdrop-filter: blur(12px);
            color: var(--text); z-index: 1001; box-shadow: var(--shadow-md); transition: var(--transition);
        }
        #theme-toggle:hover { transform: scale(1.1) rotate(15deg); border-color: var(--primary); }

        .whatsapp-btn {
            position: fixed; right: 25px; bottom: 25px; width: 60px; height: 60px;
            background: #25D366; color: white; border-radius: 50%; display: flex;
            align-items: center; justify-content: center; font-size: 32px;
            box-shadow: 0 8px 25px rgba(37, 211, 102, 0.35); z-index: 1000;
            text-decoration: none; transition: var(--transition); border: 2px solid rgba(255,255,255,0.2);
        }
        .whatsapp-btn:hover { transform: scale(1.15) rotate(-5deg); background: #128C7E; box-shadow: 0 12px 35px rgba(37, 211, 102, 0.5); color: white; }

        /* ==========================================================================
           6. HEADER (Glass Navigation)
           ========================================================================== */
        header {
            position: fixed; top: 0; left: 0; width: 100%; padding: 0 8%; height: 80px;
            display: flex; justify-content: center; align-items: center;
            background: var(--card); backdrop-filter: blur(24px); -webkit-backdrop-filter: blur(24px);
            z-index: 1000; border-bottom: 1px solid var(--border-color);
        }
        .header-content { display: flex; justify-content: space-between; align-items: center; width: 100%; max-width: 1320px; padding-right: 60px; }
        .logo { font-size: 1.25rem; font-weight: 800; font-family: var(--font-mono); color: var(--secondary); text-decoration: none; display: flex; align-items: center; gap: 10px; }
        .logo span { color: var(--primary); }
        .nav-links { display: flex; gap: 2rem; list-style: none; align-items: center; }
        .nav-links a { font-size: 0.925rem; font-weight: 600; color: var(--text-muted); text-decoration: none; transition: var(--transition); }
        .nav-links a:hover { color: var(--primary); }
        .menu-toggle { display: none; font-size: 1.4rem; cursor: pointer; color: var(--secondary); }

        /* ==========================================================================
           7. HERO SECTION (Subtle Grid + Soft Profile Glow)
           ========================================================================== */
        #hero {
            min-height: 100vh; padding-top: 140px; padding-bottom: 60px;
            display: grid; grid-template-columns: 1.2fr 0.8fr; gap: 4rem; align-items: center;
            position: relative;
        }

        /* Subtle Hero-Only Blueprint Grid */
        #hero::before {
            content: ""; position: absolute; top: 0; left: 50%; transform: translateX(-50%);
            width: 100vw; height: 100%;
            background-image: 
                linear-gradient(var(--grid-line) 1px, transparent 1px),
                linear-gradient(90deg, var(--grid-line) 1px, transparent 1px);
            background-size: 32px 32px;
            -webkit-mask-image: radial-gradient(ellipse at center, black 10%, transparent 70%);
            mask-image: radial-gradient(ellipse at center, black 10%, transparent 70%);
            z-index: -1; pointer-events: none;
        }

        .hero-greeting { font-family: var(--font-mono); color: var(--primary); font-weight: 600; font-size: 1rem; margin-bottom: 0.5rem; }
        .hero-title { font-size: 3.25rem; font-weight: 800; line-height: 1.15; color: var(--secondary); margin-bottom: 1.25rem; letter-spacing: -0.03em; }
        .hero-subtitle { font-size: 1.2rem; color: var(--primary); margin-bottom: 1rem; font-weight: 700; }
        .hero-bio { color: var(--text-muted); margin-bottom: 2.25rem; font-size: 1.05rem; max-width: 580px; }
        .hero-highlights { display: grid; grid-template-columns: repeat(3, 1fr); gap: 1rem; margin-bottom: 2.5rem; padding-top: 1.5rem; border-top: 1px dashed var(--border-color); }
        .metric-item strong { display: block; font-size: 1.5rem; font-weight: 800; color: var(--secondary); font-family: var(--font-mono); }
        .metric-item span { font-size: 0.825rem; color: var(--text-muted); font-weight: 500; }
        .hero-btns { display: flex; gap: 1rem; flex-wrap: wrap; }

        /* Profile Card & Glow */
        .profile-card { padding: 1.5rem; text-align: center; width: 100%; max-width: 380px; position: relative; z-index: 1; }
        .profile-img-container {
            width: 220px; height: 220px; margin: 0 auto 1.5rem auto; border-radius: 50%;
            position: relative; z-index: 2;
            border: 4px solid rgba(255,255,255,0.1); background: var(--bg);
        }
        .profile-img-container::before {
            content: ''; position: absolute; inset: -15px;
            background: linear-gradient(135deg, var(--primary), #8b5cf6, #06b6d4);
            filter: blur(25px); z-index: -1; opacity: 0.5; border-radius: 50%;
            animation: pulseGlow 5s infinite alternate;
        }
        @keyframes pulseGlow {
            0% { opacity: 0.3; transform: scale(0.95); }
            100% { opacity: 0.7; transform: scale(1.05); }
        }
        .profile-img-container img { width: 100%; height: 100%; object-fit: cover; border-radius: 50%; }
        .profile-info h3 { font-size: 1.25rem; font-weight: 800; color: var(--secondary); }
        .profile-info p { font-size: 0.875rem; color: var(--text-muted); font-family: var(--font-mono); margin-top: 2px; }

        /* ==========================================================================
           8. SKILLS SECTION
           ========================================================================== */
        .skills-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: 1.5rem; }
        .skill-card { padding: 1.75rem; }
        .skill-icon-header { display: flex; align-items: center; gap: 14px; margin-bottom: 1rem; }
        .skill-icon { width: 48px; height: 48px; border-radius: 12px; background: var(--primary-light); border: 1px solid var(--border-accent); color: var(--primary); display: flex; align-items: center; justify-content: center; font-size: 1.25rem; }
        .skill-title-group h3 { font-size: 1.05rem; font-weight: 700; color: var(--secondary); }
        .skill-title-group span { font-size: 0.75rem; font-family: var(--font-mono); color: var(--primary); font-weight: 600; }
        .skill-desc { font-size: 0.9rem; color: var(--text-muted); margin-bottom: 1.25rem; }
        .progress-bar { width: 100%; height: 7px; background: var(--border-color); border-radius: 10px; overflow: hidden; }
        .progress-fill { height: 100%; background: linear-gradient(90deg, var(--primary), #8b5cf6); border-radius: 10px; }

        /* ==========================================================================
           9. EXPERIENCE TIMELINE
           ========================================================================== */
        .timeline { position: relative; max-width: 900px; margin: 0 auto; }
        .timeline::before { content: ""; position: absolute; top: 0; left: 20px; height: 100%; width: 2px; background: var(--border-color); }
        .timeline-item { position: relative; padding-left: 60px; margin-bottom: 2.5rem; }
        .timeline-icon { position: absolute; left: 0; top: 0; width: 42px; height: 42px; border-radius: 50%; background: var(--card); backdrop-filter: blur(10px); border: 2px solid var(--primary); color: var(--primary); display: flex; align-items: center; justify-content: center; font-size: 1rem; box-shadow: var(--shadow-sm); }
        .timeline-content { padding: 1.75rem; }
        .timeline-role { font-size: 1.2rem; font-weight: 800; color: var(--secondary); }
        .timeline-company { color: var(--primary); font-weight: 600; font-size: 0.95rem; }
        .timeline-date { font-family: var(--font-mono); font-size: 0.8rem; padding: 3px 10px; background: var(--primary-light); color: var(--primary); border-radius: 6px; font-weight: 600; }
        .timeline-body p { color: var(--text-muted); font-size: 0.95rem; margin-top: 0.75rem; }
        .timeline-tags { display: flex; gap: 6px; flex-wrap: wrap; margin-top: 1rem; }
        .tag-sm { font-family: var(--font-mono); font-size: 0.725rem; padding: 3px 8px; background: var(--primary-light); color: var(--primary); border-radius: 6px; border: 1px solid var(--border-accent); font-weight: 600;}

        /* ==========================================================================
           10. PROJECTS & DRAWINGS PORTFOLIO
           ========================================================================== */
        .filter-menu { display: flex; gap: 10px; margin-bottom: 2.5rem; flex-wrap: wrap; justify-content: center; }
        .filter-btn { padding: 8px 18px; background: var(--card); border: 1px solid var(--border-color); color: var(--secondary); border-radius: 30px; cursor: pointer; font-size: 0.875rem; font-weight: 600; font-family: var(--font-mono); transition: var(--transition); backdrop-filter: blur(10px); }
        .filter-btn.active, .filter-btn:hover { background: var(--primary); color: #ffffff; border-color: var(--primary); box-shadow: 0 4px 12px rgba(37, 99, 235, 0.25); transform: translateY(-2px); }

        .projects-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(340px, 1fr)); gap: 2rem; }
        .project-card { display: flex; flex-direction: column; overflow: hidden; padding: 0; }
        .project-img { width: 100%; height: 220px; background-color: var(--border-color); overflow: hidden; position: relative; }
        .project-img img { width: 100%; height: 100%; object-fit: cover; transition: var(--transition); }
        .project-card:hover .project-img img { transform: scale(1.08); }
        .project-content { padding: 1.5rem; flex-grow: 1; display: flex; flex-direction: column; }
        .tag { font-family: var(--font-mono); font-size: 0.7rem; padding: 3px 8px; background: var(--primary-light); color: var(--primary); border-radius: 4px; border: 1px solid var(--border-accent); font-weight: 600; margin-right: 6px; margin-bottom: 10px; display: inline-block; }
        .project-title { font-size: 1.2rem; font-weight: 800; color: var(--secondary); margin-bottom: 0.5rem; }
        .project-desc { color: var(--text-muted); font-size: 0.925rem; margin-bottom: 1.5rem; flex-grow: 1; }
        .project-link { color: var(--primary); font-weight: 700; display: inline-flex; align-items: center; gap: 8px; font-size: 0.9rem; cursor: pointer; background: none; border: none; font-family: inherit; transition: var(--transition); }
        .project-link:hover { color: #8b5cf6; gap: 12px; }

        .drawings-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(280px, 1fr)); gap: 1.25rem; margin-top: 2rem; }
        .drawing-item { position: relative; height: 220px; overflow: hidden; cursor: pointer; padding: 0; }
        .drawing-item img { width: 100%; height: 100%; object-fit: cover; transition: var(--transition); }
        .drawing-overlay { position: absolute; inset: 0; background: rgba(15, 23, 42, 0.85); backdrop-filter: blur(4px); display: flex; flex-direction: column; justify-content: center; align-items: center; opacity: 0; transition: var(--transition); color: #ffffff; text-align: center; padding: 1rem; border-radius: inherit; }
        .drawing-item:hover .drawing-overlay { opacity: 1; }
        .drawing-item:hover img { transform: scale(1.1); }
        .drawing-overlay h4 { font-size: 1.1rem; font-weight: 700; margin-bottom: 5px; color: #fff; }

        /* ==========================================================================
           11. TESTIMONIALS SECTION
           ========================================================================== */
        .testimonials-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(320px, 1fr)); gap: 2rem; }
        .testimonial-card { padding: 2rem; display: flex; flex-direction: column; justify-content: space-between; }
        .quote-icon { font-size: 1.75rem; color: var(--primary); margin-bottom: 1rem; opacity: 0.6; }
        .testimonial-text { color: var(--text-muted); font-size: 0.975rem; font-style: italic; margin-bottom: 1.5rem; line-height: 1.7; }
        .author-group { display: flex; align-items: center; gap: 12px; border-top: 1px solid var(--border-color); padding-top: 1rem; }
        .author-avatar { width: 44px; height: 44px; border-radius: 50%; background: var(--primary-light); color: var(--primary); display: flex; align-items: center; justify-content: center; font-weight: 700; font-family: var(--font-mono); border: 1px solid var(--border-accent); }
        .author-details h4 { font-size: 0.95rem; font-weight: 700; color: var(--secondary); }
        .author-details span { font-size: 0.8rem; color: var(--text-muted); }

        /* ==========================================================================
           12. CONTACT SECTION & FOOTER
           ========================================================================== */
        .contact-container { display: grid; grid-template-columns: 1fr 1.2fr; gap: 3.5rem; }
        .contact-info p { color: var(--text-muted); margin-bottom: 2rem; font-size: 1.025rem; }
        .info-list { display: flex; flex-direction: column; gap: 1.5rem; }
        .info-item { display: flex; align-items: center; gap: 1rem; }
        .info-icon { width: 48px; height: 48px; border-radius: 12px; background: var(--primary-light); color: var(--primary); border: 1px solid var(--border-accent); display: flex; align-items: center; justify-content: center; font-size: 1.2rem; }
        
        .contact-form { padding: 2.25rem; display: flex; flex-direction: column; gap: 1.25rem; }
        .form-group { display: flex; flex-direction: column; gap: 6px; }
        .form-group label { font-size: 0.875rem; font-weight: 600; color: var(--secondary); }
        .form-group input, .form-group textarea { padding: 0.85rem 1rem; background: var(--bg); border: 1px solid var(--border-color); border-radius: 12px; color: var(--text); font-family: inherit; transition: var(--transition); font-size: 0.95rem; width: 100%; }
        .form-group input:focus, .form-group textarea:focus { outline: none; border-color: var(--primary); background: var(--bg2); box-shadow: 0 0 0 3px rgba(37, 99, 235, 0.15); }
        
        .alert-success { background: rgba(16, 185, 129, 0.1); color: var(--accent-green); border: 1px solid rgba(16, 185, 129, 0.3); padding: 1rem; border-radius: 8px; font-size: 0.95rem; font-weight: 600; display: none; align-items: center; gap: 10px; margin-top: 1rem; opacity: 0; transform: translateY(10px); transition: all 0.4s ease; backdrop-filter: blur(10px); }
        .alert-success.show { display: flex; opacity: 1; transform: translateY(0); }

        footer { padding: 40px 8%; border-top: 1px solid var(--border-color); display: flex; justify-content: space-between; align-items: center; color: var(--text-muted); font-size: 0.875rem; max-width: 1320px; margin: 0 auto; margin-top: 2rem; }
        .social-links { display: flex; gap: 1rem; }
        .social-links a { width: 38px; height: 38px; border-radius: 50%; background: var(--card); border: 1px solid var(--border-color); color: var(--text-muted); display: flex; align-items: center; justify-content: center; transition: var(--transition); text-decoration: none; backdrop-filter: blur(10px); }
        .social-links a:hover { color: var(--primary); border-color: var(--primary); background: var(--primary-light); transform: translateY(-3px) scale(1.1); }

        /* ==========================================================================
           13. MODAL (Project Specs)
           ========================================================================== */
        .modal { display: none; position: fixed; top: 0; left: 0; width: 100%; height: 100%; background: rgba(15, 23, 42, 0.7); backdrop-filter: blur(8px); z-index: 2000; justify-content: center; align-items: center; padding: 20px; opacity: 0; transition: opacity 0.3s ease; }
        .modal.show { display: flex; opacity: 1; }
        .modal-container { max-width: 700px; width: 100%; padding: 2.25rem; position: relative; transform: translateY(20px); transition: transform 0.3s ease; }
        .modal.show .modal-container { transform: translateY(0); }
        .modal-title { font-size: 1.5rem; color: var(--secondary); margin-bottom: 1rem; font-weight: 800; }
        .spec-table { width: 100%; border-collapse: collapse; margin: 1.25rem 0; font-family: var(--font-mono); font-size: 0.875rem; }
        .spec-table td { padding: 0.75rem 1rem; border-bottom: 1px solid var(--border-color); color: var(--text); }
        .spec-table td:first-child { color: var(--text-muted); font-weight: 500; width: 40%; }
        .spec-table td:last-child { font-weight: 700; }
        .close-modal { position: absolute; top: 20px; right: 25px; color: var(--text-muted); font-size: 1.75rem; cursor: pointer; transition: var(--transition); }
        .close-modal:hover { color: var(--primary); transform: rotate(90deg); }

        /* ==========================================================================
           14. ANIMATIONS & RESPONSIVE
           ========================================================================== */
        .reveal { opacity: 0; transform: translateY(40px); transition: all 0.8s cubic-bezier(0.175, 0.885, 0.32, 1.275); }
        .reveal.active { opacity: 1; transform: translateY(0); }

        @media (max-width: 992px) {
            #hero, .contact-container { grid-template-columns: 1fr; }
            .hero-image-wrapper { order: -1; }
            .hero-title { font-size: 2.75rem; }
        }
        @media (max-width: 768px) {
            .header-content { padding-right: 0; }
            .nav-links { display: none; position: absolute; top: 80px; left: 0; width: 100%; background: var(--card); backdrop-filter: blur(24px); flex-direction: column; padding: 20px 8%; border-bottom: 1px solid var(--border-color); box-shadow: var(--shadow-md); }
            .nav-links.active { display: flex; }
            .menu-toggle { display: block; }
            section { padding: 70px 6%; }
            .hero-highlights { grid-template-columns: 1fr; }
            .whatsapp-btn { right: 16px; bottom: 16px; width: 52px; height: 52px; font-size: 26px; }
            #theme-toggle { top: 15px; right: 70px; width: 40px; height: 40px; font-size: 16px; }
        }
    </style>
</head>
<body>

    <!-- Theme Toggle Button -->
    <button id="theme-toggle">🌙</button>

    <!-- Floating WhatsApp Button -->
    <a href="https://wa.me/920000000000" class="whatsapp-btn" target="_blank" rel="noopener noreferrer" aria-label="Contact on WhatsApp">
        <i class="fab fa-whatsapp"></i>
    </a>

    <!-- Mouse-Following Spotlight -->
    <div class="spotlight"></div>

    <!-- Navigation Header -->
    <header>
        <div class="header-content">
            <a href="#" class="logo">3D Mech<span>Design</span></a>
            <ul class="nav-links">
                <li><a href="#hero">Home</a></li>
                <li><a href="#skills">Skills</a></li>
                <li><a href="#experience">Experience</a></li>
                <li><a href="#projects">Projects</a></li>
                <li><a href="#testimonials">Testimonials</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
            <div class="menu-toggle"><i class="fas fa-bars"></i></div>
        </div>
    </header>

    <!-- Hero Section -->
    <section id="hero">
        <div>
            <p class="hero-greeting"><i class="fas fa-compass"></i> Welcome to my engineering portfolio</p>
            <h1 class="hero-title">Hi, I'm <span class="text-gradient">Abdur Rafay Yousuf</span></h1>
            <h2 class="hero-subtitle">Mechanical Engineer & CAD Consultant</h2>
            <p class="hero-bio">Specializing in parametric product design, complex geometric modeling, gear engineering, and computational fluid dynamics (CFD). Founder of 3D Mech Design based in Karachi, Pakistan.</p>
            
            <div class="hero-highlights reveal">
                <div class="metric-item">
                    <strong>100+</strong>
                    <span>CAD Models</span>
                </div>
                <div class="metric-item">
                    <strong>4+</strong>
                    <span>Years Exp.</span>
                </div>
                <div class="metric-item">
                    <strong>100%</strong>
                    <span>Precision</span>
                </div>
            </div>

            <div class="hero-btns">
                <a href="#projects" class="btn btn-primary"><i class="fas fa-rocket"></i> View Projects</a>
                <a href="#contact" class="btn btn-secondary"><i class="fas fa-envelope"></i> Contact Me</a>
            </div>
        </div>
        
        <div class="hero-image-wrapper">
            <div class="profile-card card reveal">
                <div class="profile-img-container">
                    <!-- Replace with your actual photo -->
                    <img src="https://via.placeholder.com/220" alt="Abdur Rafay Yousuf Profile">
                </div>
                <div class="profile-info">
                    <h3>Abdur Rafay Yousuf</h3>
                    <p>Founder @ 3D Mech Design</p>
                    <div style="margin-top: 10px;">
                        <span class="tag-sm"><i class="fas fa-university"></i> DHA Suffa University</span>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Skills Section -->
    <section id="skills">
        <div class="section-header">
            <span class="section-tag">Core Competencies</span>
            <h2 class="section-title">Technical Expertise</h2>
            <p class="section-subtitle">Specialized engineering skills developed through rigorous academic research and professional consulting.</p>
        </div>

        <div class="skills-grid">
            <div class="skill-card reveal">
                <div class="skill-icon-header">
                    <div class="skill-icon"><i class="fas fa-cube"></i></div>
                    <div class="skill-title-group">
                        <h3>3D CAD Modeling</h3>
                        <span>SolidWorks, AutoCAD, Fusion 360</span>
                    </div>
                </div>
                <p class="skill-desc">Expertise in complex parametric geometric modeling, design tables, feature trees, and generating technical manufacturing drawings.</p>
                <div class="progress-bar"><div class="progress-fill" style="width: 95%;"></div></div>
            </div>

            <div class="skill-card reveal">
                <div class="skill-icon-header">
                    <div class="skill-icon"><i class="fas fa-wind"></i></div>
                    <div class="skill-title-group">
                        <h3>CFD Analysis</h3>
                        <span>Flow Regimes, Velocity & Pressure</span>
                    </div>
                </div>
                <p class="skill-desc">Performing computational fluid dynamics analysis and generating accurate graphical representations of pressure and velocity distributions.</p>
                <div class="progress-bar"><div class="progress-fill" style="width: 88%;"></div></div>
            </div>

            <div class="skill-card reveal">
                <div class="skill-icon-header">
                    <div class="skill-icon"><i class="fas fa-cogs"></i></div>
                    <div class="skill-title-group">
                        <h3>Gear Engineering</h3>
                        <span>MATLAB & Custom Equations</span>
                    </div>
                </div>
                <p class="skill-desc">Calculating mathematically accurate involute tooth profiles, diametral pitch, and designing specialized hobbing and inspection arbors.</p>
                <div class="progress-bar"><div class="progress-fill" style="width: 92%;"></div></div>
            </div>
            
            <div class="skill-card reveal">
                <div class="skill-icon-header">
                    <div class="skill-icon"><i class="fas fa-fire-alt"></i></div>
                    <div class="skill-title-group">
                        <h3>Thermodynamics</h3>
                        <span>Thermal Energy Storage</span>
                    </div>
                </div>
                <p class="skill-desc">Engaged in advanced thermal energy storage solutions, including sand battery technologies and internal combustion engine emissions control.</p>
                <div class="progress-bar"><div class="progress-fill" style="width: 85%;"></div></div>
            </div>
        </div>
    </section>

    <!-- Experience Timeline -->
    <section id="experience">
        <div class="section-header">
            <span class="section-tag">Professional Timeline</span>
            <h2 class="section-title">Work & Projects Experience</h2>
        </div>

        <div class="timeline">
            <div class="timeline-item reveal">
                <div class="timeline-icon"><i class="fas fa-briefcase"></i></div>
                <div class="timeline-content card">
                    <div class="timeline-header">
                        <div>
                            <h3 class="timeline-role">Founder & Design Consultant</h3>
                            <span class="timeline-company">3D Mech Design</span>
                        </div>
                        <span class="timeline-date">2025 - Present</span>
                    </div>
                    <div class="timeline-body">
                        <p>Providing professional mechanical design consultation. Drafting technical proposals, flyers, and operating comprehensive parametric modeling projects for industry clients. Leading design architecture and modeling processes.</p>
                        <div class="timeline-tags">
                            <span class="tag-sm">Consulting</span>
                            <span class="tag-sm">CAD</span>
                            <span class="tag-sm">Parametric Design</span>
                        </div>
                    </div>
                </div>
            </div>

            <div class="timeline-item reveal">
                <div class="timeline-icon"><i class="fas fa-wheelchair"></i></div>
                <div class="timeline-content card">
                    <div class="timeline-header">
                        <div>
                            <h3 class="timeline-role">Lead Engineer</h3>
                            <span class="timeline-company">Mahfooz Wheelchair Project</span>
                        </div>
                        <span class="timeline-date">2025 - 2026</span>
                    </div>
                    <div class="timeline-body">
                        <p>Developed a locally producible mobility device featuring stair-lifting capabilities inspired by personal family challenges. Conducted user surveys and received official startup recognition from the Sindh Higher Education Commission.</p>
                        <div class="timeline-tags">
                            <span class="tag-sm">Prototyping</span>
                            <span class="tag-sm">Accessibility</span>
                            <span class="tag-sm">Innovation</span>
                        </div>
                    </div>
                </div>
            </div>

            <div class="timeline-item reveal">
                <div class="timeline-icon"><i class="fas fa-chalkboard-teacher"></i></div>
                <div class="timeline-content card">
                    <div class="timeline-header">
                        <div>
                            <h3 class="timeline-role">CAD Mentor & Supervisor</h3>
                            <span class="timeline-company">Community Skill-Sharing</span>
                        </div>
                        <span class="timeline-date">2026</span>
                    </div>
                    <div class="timeline-body">
                        <p>Mentored junior engineering associates (including Faizan Khan) directly in advanced computer-aided design skills, logging community engagement records and fostering practical design logic among upcoming engineers.</p>
                        <div class="timeline-tags">
                            <span class="tag-sm">Mentorship</span>
                            <span class="tag-sm">SolidWorks</span>
                            <span class="tag-sm">Leadership</span>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Projects Portfolio -->
    <section id="projects">
        <div class="section-header">
            <span class="section-tag">Portfolio</span>
            <h2 class="section-title">Featured Projects</h2>
            <p class="section-subtitle">A showcase of advanced engineering applications, thermodynamic research, and robotic integrations.</p>
        </div>

        <div class="filter-menu reveal">
            <button class="filter-btn active" data-filter="all">All Projects</button>
            <button class="filter-btn" data-filter="cad">CAD / Mechanical</button>
            <button class="filter-btn" data-filter="thermo">Thermodynamics</button>
            <button class="filter-btn" data-filter="robotics">Robotics</button>
        </div>

        <div class="projects-grid">
            <!-- Project 1 -->
            <div class="project-card card reveal" data-category="thermo">
                <div class="project-img">
                    <img src="https://via.placeholder.com/400x250" alt="Sand Battery Prototype">
                </div>
                <div class="project-content">
                    <div>
                        <span class="tag">Energy Storage</span>
                        <span class="tag">Thermodynamics</span>
                    </div>
                    <h3 class="project-title">Thermal Energy Sand Battery</h3>
                    <p class="project-desc">Final year design project featuring a physical layout consisting of an insulated silica sand tank, internal heat exchanger coils, and precision instrumentation sensors for industrial energy storage applications.</p>
                    <button class="project-link open-modal" data-target="modal-battery">View Specs <i class="fas fa-arrow-right"></i></button>
                </div>
            </div>

            <!-- Project 2 -->
            <div class="project-card card reveal" data-category="robotics">
                <div class="project-img">
                    <img src="https://via.placeholder.com/400x250" alt="Autonomous Robot">
                </div>
                <div class="project-content">
                    <div>
                        <span class="tag">Robotics</span>
                        <span class="tag">Arduino Uno</span>
                    </div>
                    <h3 class="project-title">Autonomous Line-Following Robot</h3>
                    <p class="project-desc">Developed for Measurement and Instrumentation Lab. System features real-time processing code, complex wiring diagrams, and integrated sensor feedback mechanisms.</p>
                    <button class="project-link open-modal" data-target="modal-robot">View Specs <i class="fas fa-arrow-right"></i></button>
                </div>
            </div>

            <!-- Project 3 -->
            <div class="project-card card reveal" data-category="thermo">
                <div class="project-img">
                    <img src="https://via.placeholder.com/400x250" alt="ICE Emissions">
                </div>
                <div class="project-content">
                    <div>
                        <span class="tag">Research</span>
                        <span class="tag">IC Engines</span>
                    </div>
                    <h3 class="project-title">ICE Emissions Research Report</h3>
                    <p class="project-desc">A formal engineering document analyzing pollutant formation mechanisms and modern emission control technologies in Internal Combustion Engines.</p>
                    <button class="project-link open-modal" data-target="modal-ice">View Specs <i class="fas fa-arrow-right"></i></button>
                </div>
            </div>
        </div>

        <h3 class="section-title reveal" style="margin-top: 5rem; font-size: 1.8rem;">Technical Drawings & Renders</h3>
        <div class="drawings-grid">
            <div class="drawing-item reveal">
                <img src="https://via.placeholder.com/300" alt="Gear Arbor Profile">
                <div class="drawing-overlay">
                    <h4>Gear Arbor Profile</h4>
                    <p style="font-size: 0.8rem; margin-top: 5px;">Involute Tooth / Pitch Dia Calc</p>
                </div>
            </div>
            <div class="drawing-item reveal">
                <img src="https://via.placeholder.com/300" alt="CFD Analysis Plot">
                <div class="drawing-overlay">
                    <h4>CFD Analysis Plot</h4>
                    <p style="font-size: 0.8rem; margin-top: 5px;">Pressure & Velocity Distribution</p>
                </div>
            </div>
            <div class="drawing-item reveal">
                <img src="https://via.placeholder.com/300" alt="Wheelchair Mechanism">
                <div class="drawing-overlay">
                    <h4>Wheelchair Mechanism</h4>
                    <p style="font-size: 0.8rem; margin-top: 5px;">Mahfooz Project Stair-Lift</p>
                </div>
            </div>
            <div class="drawing-item reveal">
                <img src="https://via.placeholder.com/300" alt="Portfolio Economics">
                <div class="drawing-overlay">
                    <h4>Engineering Economics</h4>
                    <p style="font-size: 0.8rem; margin-top: 5px;">PSX Transaction Log Analysis</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Testimonials Section -->
    <section id="testimonials">
        <div class="section-header">
            <span class="section-tag">References</span>
            <h2 class="section-title">Academic & Professional Feedback</h2>
        </div>

        <div class="testimonials-grid">
            <div class="testimonial-card card reveal">
                <i class="fas fa-quote-left quote-icon"></i>
                <p class="testimonial-text">"Abdur Rafay demonstrates exceptional diligence in complex design architecture. His work on the Thermal Sand Battery and computational fluid dynamics sets a high standard for mechanical engineering students."</p>
                <div class="author-group">
                    <div class="author-avatar">U</div>
                    <div class="author-details">
                        <h4>Dr. Usama</h4>
                        <span>University Professor, DHA Suffa University</span>
                    </div>
                </div>
            </div>

            <div class="testimonial-card card reveal">
                <i class="fas fa-quote-left quote-icon"></i>
                <p class="testimonial-text">"Collaborating with Rafay on lab projects has been incredible. His precision in SolidWorks and ability to translate mathematical gear equations into working CAD models is unmatched."</p>
                <div class="author-group">
                    <div class="author-avatar">A</div>
                    <div class="author-details">
                        <h4>Ayaan Amir</h4>
                        <span>Classmate & Project Collaborator</span>
                    </div>
                </div>
            </div>

            <div class="testimonial-card card reveal">
                <i class="fas fa-quote-left quote-icon"></i>
                <p class="testimonial-text">"The mentorship provided by Rafay in computer-aided design has been invaluable to my growth. He breaks down complex geometric modeling into understandable, practical logic."</p>
                <div class="author-group">
                    <div class="author-avatar">F</div>
                    <div class="author-details">
                        <h4>Faizan Khan</h4>
                        <span>Junior Associate & Mentee</span>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact">
        <div class="section-header">
            <span class="section-tag">Get in Touch</span>
            <h2 class="section-title">Let's Work Together</h2>
            <p class="section-subtitle">Available for mechanical design consultation, parametric modeling contracts, and CFD analysis projects.</p>
        </div>

        <div class="contact-container">
            <div class="contact-info reveal">
                <p>Operating primarily out of Karachi, Pakistan, providing high-quality engineering deliverables globally through <strong>3D Mech Design</strong>.</p>
                <div class="info-list">
                    <div class="info-item">
                        <div class="info-icon"><i class="fas fa-map-marker-alt"></i></div>
                        <div>
                            <strong style="color: var(--secondary);">Location</strong>
                            <p style="margin:0; font-size: 0.9rem; color: var(--text-muted);">Karachi, Pakistan</p>
                        </div>
                    </div>
                    <div class="info-item">
                        <div class="info-icon"><i class="fas fa-building"></i></div>
                        <div>
                            <strong style="color: var(--secondary);">Consultancy</strong>
                            <p style="margin:0; font-size: 0.9rem; color: var(--text-muted);">3D Mech Design</p>
                        </div>
                    </div>
                    <div class="info-item">
                        <div class="info-icon"><i class="fas fa-envelope"></i></div>
                        <div>
                            <strong style="color: var(--secondary);">Email</strong>
                            <p style="margin:0; font-size: 0.9rem; color: var(--text-muted);">contact@example.com</p>
                        </div>
                    </div>
                </div>
            </div>

            <div class="contact-form card reveal">
                <form id="contactForm">
                    <div class="form-group" style="margin-bottom: 1rem;">
                        <label>Full Name</label>
                        <input type="text" required placeholder="John Doe">
                    </div>
                    <div class="form-group" style="margin-bottom: 1rem;">
                        <label>Email Address</label>
                        <input type="email" required placeholder="john@example.com">
                    </div>
                    <div class="form-group" style="margin-bottom: 1.5rem;">
                        <label>Project Details</label>
                        <textarea rows="5" required placeholder="Please provide details about your CAD or Engineering requirements..."></textarea>
                    </div>
                    <button type="submit" class="btn btn-primary" style="width: 100%;">Submit Inquiry</button>
                    
                    <div class="alert-success" id="successMsg">
                        <i class="fas fa-check-circle"></i> Message sent successfully! I will reply shortly.
                    </div>
                </form>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div>&copy; 2026 Abdur Rafay Yousuf. All rights reserved.</div>
        <div class="social-links">
            <a href="#"><i class="fab fa-linkedin-in"></i></a>
            <a href="#"><i class="fab fa-github"></i></a>
            <a href="#"><i class="fab fa-instagram"></i></a>
        </div>
    </footer>

    <!-- Modals for Projects -->
    <!-- Modal 1: Battery -->
    <div class="modal" id="modal-battery">
        <div class="modal-container">
            <span class="close-modal">&times;</span>
            <h3 class="modal-title">Thermal Energy Sand Battery</h3>
            <p style="color: var(--text-muted); margin-bottom: 1rem;">Technical specifications for the final year thermal energy storage project.</p>
            <table class="spec-table">
                <tr>
                    <td>Storage Medium</td>
                    <td>Silica Sand</td>
                </tr>
                <tr>
                    <td>Core Components</td>
                    <td>Insulated Tank, Heat Exchanger Coils</td>
                </tr>
                <tr>
                    <td>Application</td>
                    <td>Industrial Scale Thermal Storage</td>
                </tr>
                <tr>
                    <td>Key Focus</td>
                    <td>Thermodynamics & Heat Transfer</td>
                </tr>
            </table>
        </div>
    </div>

    <!-- Modal 2: Robot -->
    <div class="modal" id="modal-robot">
        <div class="modal-container">
            <span class="close-modal">&times;</span>
            <h3 class="modal-title">Autonomous Line-Following Robot</h3>
            <p style="color: var(--text-muted); margin-bottom: 1rem;">Measurement & Instrumentation Lab Project Details.</p>
            <table class="spec-table">
                <tr>
                    <td>Microcontroller</td>
                    <td>Arduino Uno</td>
                </tr>
                <tr>
                    <td>Function</td>
                    <td>Real-Time Line Tracking</td>
                </tr>
                <tr>
                    <td>Components</td>
                    <td>IR Sensors, Motor Drivers</td>
                </tr>
                <tr>
                    <td>Focus Area</td>
                    <td>Wiring diagrams, Signal Processing</td>
                </tr>
            </table>
        </div>
    </div>

    <!-- Modal 3: ICE -->
    <div class="modal" id="modal-ice">
        <div class="modal-container">
            <span class="close-modal">&times;</span>
            <h3 class="modal-title">ICE Emissions Research</h3>
            <p style="color: var(--text-muted); margin-bottom: 1rem;">Fall 2025 Technical Research Report Data.</p>
            <table class="spec-table">
                <tr>
                    <td>Subject</td>
                    <td>Internal Combustion Engines</td>
                </tr>
                <tr>
                    <td>Primary Focus</td>
                    <td>Pollutant Formation Mechanisms</td>
                </tr>
                <tr>
                    <td>Output</td>
                    <td>Technical Research Document</td>
                </tr>
                <tr>
                    <td>Key Findings</td>
                    <td>Modern Emission Control Technologies</td>
                </tr>
            </table>
        </div>
    </div>

    <!-- JavaScript Interactions -->
    <script>
        // 1. Dark / Light Toggle
        const toggle = document.getElementById("theme-toggle");
        const saved = localStorage.getItem("theme");
        
        if (saved) {
            document.documentElement.setAttribute("data-theme", saved);
            toggle.innerHTML = saved === "dark" ? "☀️" : "🌙";
        }
        
        toggle.onclick = () => {
            const isDark = document.documentElement.getAttribute("data-theme") === "dark";
            document.documentElement.setAttribute("data-theme", isDark ? "light" : "dark");
            localStorage.setItem("theme", isDark ? "light" : "dark");
            toggle.innerHTML = isDark ? "🌙" : "☀️";
        };

        // 2. Mouse-Following Spotlight
        const spotlight = document.querySelector('.spotlight');
        document.addEventListener('mousemove', (e) => {
            if(spotlight) {
                spotlight.style.setProperty('--x', `${e.clientX}px`);
                spotlight.style.setProperty('--y', `${e.clientY}px`);
            }
        });

        // 3. Smooth Fade-in While Scrolling
        const revealElements = document.querySelectorAll('.card, .project-card, .skill-card, .timeline-item, .drawing-item, .section-title, .hero-highlights, .contact-info');
        revealElements.forEach(el => el.classList.add('reveal'));

        const observerOptions = {
            root: null,
            rootMargin: '0px',
            threshold: 0.15
        };

        const observer = new IntersectionObserver((entries, observer) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('active');
                    observer.unobserve(entry.target);
                }
            });
        }, observerOptions);

        revealElements.forEach(el => observer.observe(el));

        // 4. Mobile Menu Toggle
        const menuToggle = document.querySelector('.menu-toggle');
        const navLinks = document.querySelector('.nav-links');
        
        menuToggle.addEventListener('click', () => {
            navLinks.classList.toggle('active');
            const icon = menuToggle.querySelector('i');
            icon.classList.toggle('fa-bars');
            icon.classList.toggle('fa-times');
        });

        // 5. Project Filtering
        const filterBtns = document.querySelectorAll('.filter-btn');
        const projectCards = document.querySelectorAll('.project-card');

        filterBtns.forEach(btn => {
            btn.addEventListener('click', () => {
                // Remove active class from all buttons
                filterBtns.forEach(b => b.classList.remove('active'));
                // Add active class to clicked button
                btn.classList.add('active');
                
                const filterValue = btn.getAttribute('data-filter');
                
                projectCards.forEach(card => {
                    if(filterValue === 'all' || card.getAttribute('data-category') === filterValue) {
                        card.style.display = 'flex';
                        // Re-trigger animation
                        setTimeout(() => { card.classList.add('active'); }, 50);
                    } else {
                        card.style.display = 'none';
                        card.classList.remove('active');
                    }
                });
            });
        });

        // 6. Modal Logic
        const modalTriggers = document.querySelectorAll('.open-modal');
        const closeBtns = document.querySelectorAll('.close-modal');
        const modals = document.querySelectorAll('.modal');

        modalTriggers.forEach(trigger => {
            trigger.addEventListener('click', (e) => {
                e.preventDefault();
                const targetId = trigger.getAttribute('data-target');
                document.getElementById(targetId).classList.add('show');
            });
        });

        closeBtns.forEach(btn => {
            btn.addEventListener('click', () => {
                modals.forEach(modal => modal.classList.remove('show'));
            });
        });

        window.addEventListener('click', (e) => {
            modals.forEach(modal => {
                if (e.target === modal) {
                    modal.classList.remove('show');
                }
            });
        });

        // 7. Form Submission Fake Delay
        document.getElementById('contactForm').addEventListener('submit', (e) => {
            e.preventDefault();
            const btn = e.target.querySelector('button');
            const originalText = btn.innerHTML;
            btn.innerHTML = '<i class="fas fa-circle-notch fa-spin"></i> Sending...';
            
            setTimeout(() => {
                btn.innerHTML = originalText;
                document.getElementById('successMsg').classList.add('show');
                e.target.reset();
                
                setTimeout(() => {
                    document.getElementById('successMsg').classList.remove('show');
                }, 5000);
            }, 1500);
        });
    </script>
</body>
</html>
