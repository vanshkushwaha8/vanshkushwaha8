<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Vansh Kushwaha · Software Developer</title>

    <!-- Google Fonts -->
    <link rel="preconnect" href="https://fonts.googleapis.com" />
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
    <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,300;14..32,400;14..32,500;14..32,600;14..32,700;14..32,800&display=swap" rel="stylesheet" />

    <!-- Font Awesome -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css" />

    <style>
        /* ===== CSS Variables ===== */
        :root {
            --bg-primary: #0b0d10;
            --bg-secondary: #13161c;
            --bg-card: #1a1f28;
            --bg-card-hover: #222a36;
            --text-primary: #eaeef3;
            --text-secondary: #a8b5c9;
            --text-muted: #6b7a93;
            --accent: #6c8cff;
            --accent-glow: rgba(108, 140, 255, 0.15);
            --accent-dark: #5a7aee;
            --border: #2a3442;
            --shadow: 0 12px 40px rgba(0, 0, 0, 0.5);
            --radius: 16px;
            --radius-sm: 10px;
            --transition: 0.3s cubic-bezier(0.25, 0.46, 0.45, 0.94);
            --font: 'Inter', sans-serif;
            --max-width: 1200px;
            --toast-success: #4ade80;
            --toast-error: #f87171;
            --toast-warning: #fbbf24;
        }

        /* ===== Reset & Base ===== */
        *,
        *::before,
        *::after {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        html {
            scroll-behavior: smooth;
            scroll-padding-top: 80px;
        }

        body {
            font-family: var(--font);
            background: var(--bg-primary);
            color: var(--text-primary);
            line-height: 1.6;
            overflow-x: hidden;
        }

        a {
            text-decoration: none;
            color: inherit;
        }

        ul {
            list-style: none;
        }

        img {
            max-width: 100%;
            display: block;
        }

        .container {
            max-width: var(--max-width);
            margin: 0 auto;
            padding: 0 24px;
        }

        /* ===== Scrollbar ===== */
        ::-webkit-scrollbar {
            width: 8px;
        }
        ::-webkit-scrollbar-track {
            background: var(--bg-secondary);
        }
        ::-webkit-scrollbar-thumb {
            background: var(--accent);
            border-radius: 10px;
        }

        /* ===== Typography ===== */
        .section-label {
            display: inline-block;
            font-size: 0.75rem;
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 0.12em;
            color: var(--accent);
            background: rgba(108, 140, 255, 0.1);
            padding: 4px 14px;
            border-radius: 100px;
            margin-bottom: 12px;
            border: 1px solid rgba(108, 140, 255, 0.15);
        }

        .section-title {
            font-size: 2.2rem;
            font-weight: 700;
            letter-spacing: -0.02em;
            margin-bottom: 8px;
        }
        .section-title .highlight {
            color: var(--accent);
        }

        .section-subtitle {
            font-size: 1.05rem;
            color: var(--text-secondary);
            max-width: 560px;
        }

        .section-header {
            margin-bottom: 48px;
        }
        .section-header.centered {
            text-align: center;
        }
        .section-header.centered .section-subtitle {
            margin: 0 auto;
        }

        /* ===== Buttons ===== */
        .btn {
            display: inline-flex;
            align-items: center;
            gap: 10px;
            padding: 12px 28px;
            font-family: var(--font);
            font-weight: 600;
            font-size: 0.95rem;
            border-radius: 100px;
            border: none;
            cursor: pointer;
            transition: var(--transition);
            background: transparent;
            color: var(--text-primary);
        }

        .btn-primary {
            background: var(--accent);
            color: #fff;
            box-shadow: 0 4px 20px rgba(108, 140, 255, 0.3);
        }
        .btn-primary:hover {
            background: var(--accent-dark);
            transform: translateY(-2px);
            box-shadow: 0 8px 30px rgba(108, 140, 255, 0.4);
        }

        .btn-outline {
            border: 1.5px solid var(--border);
            color: var(--text-primary);
        }
        .btn-outline:hover {
            border-color: var(--accent);
            color: var(--accent);
            background: rgba(108, 140, 255, 0.05);
            transform: translateY(-2px);
        }

        .btn-sm {
            padding: 8px 20px;
            font-size: 0.85rem;
        }

        /* ===== Navbar ===== */
        .navbar {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            z-index: 1000;
            padding: 16px 0;
            background: rgba(11, 13, 16, 0.7);
            backdrop-filter: blur(16px) saturate(1.2);
            border-bottom: 1px solid rgba(42, 52, 66, 0.4);
            transition: var(--transition);
        }
        .navbar.scrolled {
            background: rgba(11, 13, 16, 0.92);
            box-shadow: 0 4px 30px rgba(0, 0, 0, 0.5);
        }

        .navbar .container {
            display: flex;
            align-items: center;
            justify-content: space-between;
        }

        .nav-logo {
            font-size: 1.3rem;
            font-weight: 700;
            letter-spacing: -0.02em;
            color: var(--text-primary);
        }
        .nav-logo .accent {
            color: var(--accent);
        }

        .nav-links {
            display: flex;
            align-items: center;
            gap: 32px;
        }
        .nav-links a {
            font-size: 0.9rem;
            font-weight: 500;
            color: var(--text-secondary);
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
            background: var(--accent);
            transition: var(--transition);
            border-radius: 10px;
        }
        .nav-links a:hover {
            color: var(--text-primary);
        }
        .nav-links a:hover::after {
            width: 100%;
        }
        .nav-links a.active::after {
            width: 100%;
        }

        .nav-cta {
            display: none;
        }

        .hamburger {
            display: none;
            flex-direction: column;
            gap: 5px;
            cursor: pointer;
            padding: 4px;
            background: transparent;
            border: none;
        }
        .hamburger span {
            display: block;
            width: 26px;
            height: 2.5px;
            background: var(--text-primary);
            border-radius: 10px;
            transition: var(--transition);
        }
        .hamburger.active span:nth-child(1) {
            transform: rotate(45deg) translate(5px, 5px);
        }
        .hamburger.active span:nth-child(2) {
            opacity: 0;
        }
        .hamburger.active span:nth-child(3) {
            transform: rotate(-45deg) translate(5px, -5px);
        }

        /* ===== Hero ===== */
        .hero {
            min-height: 100vh;
            display: flex;
            align-items: center;
            padding: 120px 0 80px;
            position: relative;
            overflow: hidden;
        }
        .hero::before {
            content: '';
            position: absolute;
            top: -30%;
            right: -10%;
            width: 600px;
            height: 600px;
            background: radial-gradient(circle, rgba(108, 140, 255, 0.08), transparent 70%);
            border-radius: 50%;
            pointer-events: none;
        }
        .hero::after {
            content: '';
            position: absolute;
            bottom: -20%;
            left: -10%;
            width: 500px;
            height: 500px;
            background: radial-gradient(circle, rgba(108, 140, 255, 0.05), transparent 70%);
            border-radius: 50%;
            pointer-events: none;
        }

        .hero .container {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 60px;
            align-items: center;
            position: relative;
            z-index: 2;
        }

        .hero-content .badge {
            display: inline-flex;
            align-items: center;
            gap: 8px;
            font-size: 0.85rem;
            font-weight: 500;
            color: var(--accent);
            background: rgba(108, 140, 255, 0.1);
            padding: 6px 16px;
            border-radius: 100px;
            border: 1px solid rgba(108, 140, 255, 0.15);
            margin-bottom: 20px;
        }
        .hero-content .badge .dot {
            display: inline-block;
            width: 8px;
            height: 8px;
            border-radius: 50%;
            background: #4ade80;
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
                transform: scale(0.8);
            }
        }

        .hero-content h1 {
            font-size: 3.4rem;
            font-weight: 800;
            letter-spacing: -0.03em;
            line-height: 1.1;
            margin-bottom: 16px;
        }
        .hero-content h1 .highlight {
            color: var(--accent);
        }

        .hero-content .tagline {
            font-size: 1.2rem;
            color: var(--text-secondary);
            max-width: 500px;
            margin-bottom: 28px;
        }

        .hero-actions {
            display: flex;
            flex-wrap: wrap;
            gap: 14px;
            margin-bottom: 36px;
        }

        .hero-social {
            display: flex;
            gap: 16px;
        }
        .hero-social a {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 44px;
            height: 44px;
            border-radius: 50%;
            background: var(--bg-card);
            border: 1px solid var(--border);
            color: var(--text-secondary);
            font-size: 1.1rem;
            transition: var(--transition);
        }
        .hero-social a:hover {
            background: var(--accent);
            color: #fff;
            border-color: var(--accent);
            transform: translateY(-3px);
            box-shadow: 0 8px 24px rgba(108, 140, 255, 0.3);
        }

        .hero-visual {
            display: flex;
            justify-content: center;
            align-items: center;
        }

        .hero-avatar {
            width: 340px;
            height: 340px;
            border-radius: 50%;
            background: linear-gradient(135deg, var(--bg-card), var(--bg-secondary));
            border: 2px solid var(--border);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 8rem;
            font-weight: 700;
            color: var(--accent);
            position: relative;
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.5);
            user-select: none;
            opacity: 0;
            transform: scale(0.9);
            transition: opacity 0.6s ease, transform 0.6s ease;
        }
        .hero-avatar::after {
            content: '';
            position: absolute;
            inset: -4px;
            border-radius: 50%;
            padding: 2px;
            background: linear-gradient(135deg, var(--accent), transparent 50%, var(--accent));
            -webkit-mask: linear-gradient(#fff 0 0) content-box, linear-gradient(#fff 0 0);
            -webkit-mask-composite: xor;
            mask-composite: exclude;
            opacity: 0.4;
        }
        .hero-avatar .status-ring {
            position: absolute;
            bottom: 16px;
            right: 16px;
            width: 20px;
            height: 20px;
            border-radius: 50%;
            background: #4ade80;
            border: 3px solid var(--bg-primary);
            box-shadow: 0 0 20px rgba(74, 222, 128, 0.3);
        }

        /* floating badges */
        .floating-badge {
            position: absolute;
            background: var(--bg-card);
            border: 1px solid var(--border);
            border-radius: var(--radius-sm);
            padding: 10px 16px;
            font-size: 0.8rem;
            font-weight: 500;
            display: flex;
            align-items: center;
            gap: 8px;
            box-shadow: var(--shadow);
            animation: float 6s ease-in-out infinite;
            backdrop-filter: blur(8px);
            background: rgba(26, 31, 40, 0.85);
        }
        .floating-badge i {
            color: var(--accent);
            font-size: 1rem;
        }
        .floating-badge:nth-child(1) {
            top: 10%;
            right: -10%;
            animation-delay: 0s;
        }
        .floating-badge:nth-child(2) {
            bottom: 20%;
            left: -8%;
            animation-delay: 2s;
        }
        .floating-badge:nth-child(3) {
            top: 50%;
            right: -12%;
            animation-delay: 4s;
        }

        @keyframes float {
            0%,
            100% {
                transform: translateY(0px);
            }
            50% {
                transform: translateY(-12px);
            }
        }

        /* ===== Sections ===== */
        section {
            padding: 80px 0;
        }

        section:nth-child(even) {
            background: var(--bg-secondary);
        }

        /* ===== About ===== */
        .about-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 48px;
            align-items: start;
        }

        .about-text p {
            color: var(--text-secondary);
            margin-bottom: 16px;
            font-size: 1.05rem;
            max-width: 560px;
        }

        .about-stats {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 20px;
            margin-top: 24px;
        }
        .stat-item {
            background: var(--bg-card);
            padding: 20px 16px;
            border-radius: var(--radius-sm);
            border: 1px solid var(--border);
            text-align: center;
            transition: var(--transition);
        }
        .stat-item:hover {
            border-color: var(--accent);
            transform: translateY(-4px);
        }
        .stat-item .number {
            font-size: 1.8rem;
            font-weight: 700;
            color: var(--accent);
            display: block;
        }
        .stat-item .label {
            font-size: 0.85rem;
            color: var(--text-muted);
            font-weight: 500;
        }

        .about-interests {
            background: var(--bg-card);
            border-radius: var(--radius);
            padding: 32px;
            border: 1px solid var(--border);
        }
        .about-interests h3 {
            font-size: 1.1rem;
            font-weight: 600;
            margin-bottom: 16px;
        }
        .interest-tags {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
        }
        .interest-tags span {
            background: var(--bg-secondary);
            padding: 6px 16px;
            border-radius: 100px;
            font-size: 0.85rem;
            color: var(--text-secondary);
            border: 1px solid var(--border);
            transition: var(--transition);
        }
        .interest-tags span:hover {
            border-color: var(--accent);
            color: var(--accent);
            background: rgba(108, 140, 255, 0.05);
        }

        /* ===== Skills ===== */
        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
            gap: 24px;
        }

        .skill-category {
            background: var(--bg-card);
            border-radius: var(--radius);
            padding: 28px 24px;
            border: 1px solid var(--border);
            transition: var(--transition);
        }
        .skill-category:hover {
            border-color: var(--accent);
            transform: translateY(-4px);
            box-shadow: 0 8px 30px rgba(0, 0, 0, 0.3);
        }
        .skill-category .cat-icon {
            font-size: 1.6rem;
            color: var(--accent);
            margin-bottom: 12px;
        }
        .skill-category h4 {
            font-size: 1.05rem;
            font-weight: 600;
            margin-bottom: 14px;
        }
        .skill-tags {
            display: flex;
            flex-wrap: wrap;
            gap: 8px;
        }
        .skill-tags span {
            background: var(--bg-secondary);
            padding: 4px 14px;
            border-radius: 100px;
            font-size: 0.8rem;
            color: var(--text-secondary);
            border: 1px solid var(--border);
            transition: var(--transition);
        }
        .skill-tags span:hover {
            border-color: var(--accent);
            color: var(--text-primary);
        }

        /* ===== Education ===== */
        .edu-timeline {
            display: flex;
            flex-direction: column;
            gap: 20px;
            max-width: 700px;
            margin: 0 auto;
        }

        .edu-item {
            background: var(--bg-card);
            border-radius: var(--radius);
            padding: 28px 32px;
            border: 1px solid var(--border);
            border-left: 4px solid var(--accent);
            transition: var(--transition);
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            gap: 12px;
        }
        .edu-item:hover {
            border-color: var(--accent);
            transform: translateX(6px);
        }
        .edu-item .left h4 {
            font-size: 1.1rem;
            font-weight: 600;
        }
        .edu-item .left .institute {
            color: var(--text-secondary);
            font-size: 0.95rem;
        }
        .edu-item .right {
            text-align: right;
            color: var(--text-muted);
            font-size: 0.9rem;
            font-weight: 500;
        }
        .edu-item .right .cgpa {
            color: var(--accent);
            font-weight: 700;
        }

        /* ===== Experience ===== */
        .exp-timeline {
            display: flex;
            flex-direction: column;
            gap: 28px;
        }

        .exp-item {
            background: var(--bg-card);
            border-radius: var(--radius);
            padding: 32px;
            border: 1px solid var(--border);
            transition: var(--transition);
        }
        .exp-item:hover {
            border-color: var(--accent);
            transform: translateY(-4px);
            box-shadow: 0 8px 30px rgba(0, 0, 0, 0.3);
        }

        .exp-header {
            display: flex;
            justify-content: space-between;
            align-items: flex-start;
            flex-wrap: wrap;
            gap: 12px;
            margin-bottom: 14px;
        }
        .exp-header h3 {
            font-size: 1.2rem;
            font-weight: 600;
        }
        .exp-header .company {
            color: var(--accent);
            font-weight: 500;
        }
        .exp-header .date {
            color: var(--text-muted);
            font-size: 0.9rem;
            font-weight: 500;
            white-space: nowrap;
        }

        .exp-desc {
            color: var(--text-secondary);
            font-size: 0.95rem;
        }
        .exp-desc ul {
            list-style: disc;
            padding-left: 20px;
            margin-top: 8px;
        }
        .exp-desc ul li {
            margin-bottom: 6px;
        }
        .exp-desc ul li::marker {
            color: var(--accent);
        }

        /* ===== Projects ===== */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(340px, 1fr));
            gap: 28px;
        }

        .project-card {
            background: var(--bg-card);
            border-radius: var(--radius);
            padding: 28px 28px 32px;
            border: 1px solid var(--border);
            transition: var(--transition);
            display: flex;
            flex-direction: column;
        }
        .project-card:hover {
            border-color: var(--accent);
            transform: translateY(-6px);
            box-shadow: 0 12px 40px rgba(0, 0, 0, 0.4);
        }

        .project-card .p-icon {
            font-size: 1.8rem;
            color: var(--accent);
            margin-bottom: 12px;
        }
        .project-card h4 {
            font-size: 1.15rem;
            font-weight: 600;
            margin-bottom: 4px;
        }
        .project-card .p-tech {
            font-size: 0.8rem;
            color: var(--text-muted);
            font-weight: 500;
            margin-bottom: 12px;
        }
        .project-card .p-desc {
            color: var(--text-secondary);
            font-size: 0.95rem;
            flex: 1;
            margin-bottom: 16px;
        }
        .project-card .p-tags {
            display: flex;
            flex-wrap: wrap;
            gap: 6px;
            margin-bottom: 16px;
        }
        .project-card .p-tags span {
            background: var(--bg-secondary);
            padding: 2px 12px;
            border-radius: 100px;
            font-size: 0.7rem;
            font-weight: 500;
            color: var(--text-muted);
            border: 1px solid var(--border);
        }
        .project-card .p-link {
            color: var(--accent);
            font-weight: 500;
            font-size: 0.9rem;
            display: inline-flex;
            align-items: center;
            gap: 6px;
            transition: var(--transition);
            align-self: flex-start;
        }
        .project-card .p-link:hover {
            gap: 12px;
        }

        /* ===== Certifications ===== */
        .certs-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
            gap: 20px;
        }

        .cert-item {
            background: var(--bg-card);
            border-radius: var(--radius-sm);
            padding: 24px 20px;
            border: 1px solid var(--border);
            text-align: center;
            transition: var(--transition);
        }
        .cert-item:hover {
            border-color: var(--accent);
            transform: translateY(-4px);
        }
        .cert-item i {
            font-size: 2rem;
            color: var(--accent);
            margin-bottom: 10px;
        }
        .cert-item h5 {
            font-weight: 600;
            font-size: 0.95rem;
        }
        .cert-item p {
            color: var(--text-muted);
            font-size: 0.85rem;
        }

        /* ===== Resume ===== */
        .resume-box {
            background: var(--bg-card);
            border-radius: var(--radius);
            padding: 48px 40px;
            border: 1px solid var(--border);
            text-align: center;
            max-width: 640px;
            margin: 0 auto;
            transition: var(--transition);
        }
        .resume-box:hover {
            border-color: var(--accent);
        }
        .resume-box i {
            font-size: 3rem;
            color: var(--accent);
            margin-bottom: 16px;
        }
        .resume-box h3 {
            font-size: 1.4rem;
            font-weight: 600;
            margin-bottom: 8px;
        }
        .resume-box p {
            color: var(--text-secondary);
            margin-bottom: 24px;
        }

        /* ===== Contact ===== */
        .contact-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 48px;
            align-items: start;
        }

        .contact-info h3 {
            font-size: 1.4rem;
            font-weight: 600;
            margin-bottom: 8px;
        }
        .contact-info p {
            color: var(--text-secondary);
            margin-bottom: 28px;
        }

        .contact-item {
            display: flex;
            align-items: center;
            gap: 16px;
            margin-bottom: 16px;
            padding: 16px 20px;
            background: var(--bg-card);
            border-radius: var(--radius-sm);
            border: 1px solid var(--border);
            transition: var(--transition);
        }
        .contact-item:hover {
            border-color: var(--accent);
            transform: translateX(6px);
        }
        .contact-item i {
            font-size: 1.2rem;
            color: var(--accent);
            width: 28px;
            text-align: center;
        }
        .contact-item .info {
            font-size: 0.95rem;
        }
        .contact-item .info .label {
            display: block;
            font-size: 0.75rem;
            color: var(--text-muted);
            font-weight: 500;
            text-transform: uppercase;
            letter-spacing: 0.06em;
        }
        .contact-item .info a {
            color: var(--text-secondary);
            transition: var(--transition);
        }
        .contact-item .info a:hover {
            color: var(--accent);
        }

        .contact-form {
            background: var(--bg-card);
            border-radius: var(--radius);
            padding: 32px;
            border: 1px solid var(--border);
        }
        .contact-form .form-group {
            margin-bottom: 18px;
        }
        .contact-form label {
            display: block;
            font-size: 0.85rem;
            font-weight: 500;
            margin-bottom: 4px;
            color: var(--text-secondary);
        }
        .contact-form input,
        .contact-form textarea {
            width: 100%;
            padding: 12px 16px;
            background: var(--bg-secondary);
            border: 1px solid var(--border);
            border-radius: var(--radius-sm);
            color: var(--text-primary);
            font-family: var(--font);
            font-size: 0.95rem;
            transition: var(--transition);
            outline: none;
        }
        .contact-form input:focus,
        .contact-form textarea:focus {
            border-color: var(--accent);
            box-shadow: 0 0 0 3px rgba(108, 140, 255, 0.15);
        }
        .contact-form textarea {
            min-height: 130px;
            resize: vertical;
        }
        .contact-form .btn {
            width: 100%;
            justify-content: center;
        }

        /* ===== Footer ===== */
        footer {
            background: var(--bg-secondary);
            border-top: 1px solid var(--border);
            padding: 32px 0;
        }
        footer .container {
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            gap: 16px;
        }
        footer p {
            color: var(--text-muted);
            font-size: 0.9rem;
        }
        footer .social {
            display: flex;
            gap: 14px;
        }
        footer .social a {
            color: var(--text-muted);
            transition: var(--transition);
            font-size: 1.1rem;
        }
        footer .social a:hover {
            color: var(--accent);
        }

        /* ===== Toast / Custom Notification ===== */
        .toast-container {
            position: fixed;
            top: 90px;
            right: 24px;
            z-index: 9999;
            display: flex;
            flex-direction: column;
            gap: 12px;
            max-width: 400px;
            width: 100%;
            pointer-events: none;
        }

        .toast {
            pointer-events: auto;
            background: var(--bg-card);
            border: 1px solid var(--border);
            border-radius: var(--radius-sm);
            padding: 18px 22px;
            box-shadow: 0 12px 48px rgba(0, 0, 0, 0.6);
            display: flex;
            align-items: flex-start;
            gap: 14px;
            transform: translateX(120%);
            opacity: 0;
            transition: transform 0.5s cubic-bezier(0.22, 1, 0.36, 1), opacity 0.4s ease;
            backdrop-filter: blur(12px);
            background: rgba(26, 31, 40, 0.92);
            border-left: 4px solid var(--accent);
        }

        .toast.show {
            transform: translateX(0);
            opacity: 1;
        }

        .toast.hide {
            transform: translateX(120%);
            opacity: 0;
        }

        .toast .toast-icon {
            flex-shrink: 0;
            width: 36px;
            height: 36px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1rem;
            background: rgba(108, 140, 255, 0.15);
            color: var(--accent);
            margin-top: 2px;
        }

        .toast.success .toast-icon {
            background: rgba(74, 222, 128, 0.15);
            color: var(--toast-success);
        }
        .toast.success {
            border-left-color: var(--toast-success);
        }

        .toast.error .toast-icon {
            background: rgba(248, 113, 113, 0.15);
            color: var(--toast-error);
        }
        .toast.error {
            border-left-color: var(--toast-error);
        }

        .toast .toast-content {
            flex: 1;
        }
        .toast .toast-content .toast-title {
            font-weight: 600;
            font-size: 0.95rem;
            color: var(--text-primary);
            margin-bottom: 2px;
        }
        .toast .toast-content .toast-message {
            font-size: 0.9rem;
            color: var(--text-secondary);
            line-height: 1.4;
        }

        .toast .toast-close {
            flex-shrink: 0;
            background: transparent;
            border: none;
            color: var(--text-muted);
            font-size: 1.1rem;
            cursor: pointer;
            padding: 4px;
            transition: var(--transition);
            border-radius: 50%;
            line-height: 1;
            margin-top: -2px;
        }
        .toast .toast-close:hover {
            color: var(--text-primary);
            background: rgba(255, 255, 255, 0.05);
        }

        /* ===== Responsive ===== */
        @media (max-width: 1024px) {
            .hero .container {
                grid-template-columns: 1fr;
                text-align: center;
            }
            .hero-content .tagline {
                margin: 0 auto 28px;
            }
            .hero-actions {
                justify-content: center;
            }
            .hero-social {
                justify-content: center;
            }
            .hero-avatar {
                width: 260px;
                height: 260px;
                font-size: 6rem;
            }
            .floating-badge {
                display: none;
            }
            .about-grid {
                grid-template-columns: 1fr;
            }
            .about-text p {
                max-width: 100%;
            }
            .contact-grid {
                grid-template-columns: 1fr;
            }
            .section-title {
                font-size: 1.9rem;
            }
            .toast-container {
                top: 80px;
                right: 16px;
                left: 16px;
                max-width: none;
            }
        }

        @media (max-width: 768px) {
            .nav-links {
                position: fixed;
                top: 0;
                right: -100%;
                width: 280px;
                height: 100vh;
                background: var(--bg-secondary);
                flex-direction: column;
                justify-content: center;
                gap: 24px;
                padding: 40px;
                border-left: 1px solid var(--border);
                transition: var(--transition);
                box-shadow: -10px 0 40px rgba(0, 0, 0, 0.5);
            }
            .nav-links.open {
                right: 0;
            }
            .nav-links a {
                font-size: 1.1rem;
            }
            .hamburger {
                display: flex;
                z-index: 1001;
            }
            .hero-content h1 {
                font-size: 2.4rem;
            }
            .hero-avatar {
                width: 200px;
                height: 200px;
                font-size: 4.5rem;
            }
            .hero {
                padding: 100px 0 60px;
            }
            section {
                padding: 56px 0;
            }
            .section-title {
                font-size: 1.7rem;
            }
            .exp-header {
                flex-direction: column;
            }
            .exp-header .date {
                white-space: normal;
            }
            .projects-grid {
                grid-template-columns: 1fr;
            }
            .edu-item {
                flex-direction: column;
                align-items: flex-start;
                text-align: left;
            }
            .edu-item .right {
                text-align: left;
            }
            .about-stats {
                grid-template-columns: 1fr 1fr;
            }
            .resume-box {
                padding: 32px 24px;
            }
            .contact-form {
                padding: 24px;
            }
            footer .container {
                flex-direction: column;
                text-align: center;
            }
            .toast-container {
                top: 76px;
                right: 12px;
                left: 12px;
            }
            .toast {
                padding: 14px 18px;
            }
        }

        @media (max-width: 480px) {
            .hero-content h1 {
                font-size: 1.9rem;
            }
            .hero-avatar {
                width: 160px;
                height: 160px;
                font-size: 3.5rem;
            }
            .hero-avatar .status-ring {
                width: 16px;
                height: 16px;
                bottom: 10px;
                right: 10px;
            }
            .about-stats {
                grid-template-columns: 1fr;
            }
            .stat-item {
                padding: 14px;
            }
            .skills-grid {
                grid-template-columns: 1fr;
            }
            .certs-grid {
                grid-template-columns: 1fr 1fr;
            }
            .section-title {
                font-size: 1.5rem;
            }
            .container {
                padding: 0 16px;
            }
            .toast-container {
                top: 72px;
                right: 8px;
                left: 8px;
            }
            .toast {
                padding: 12px 14px;
                border-radius: var(--radius-sm);
            }
            .toast .toast-content .toast-title {
                font-size: 0.85rem;
            }
            .toast .toast-content .toast-message {
                font-size: 0.8rem;
            }
        }

        /* ===== Animations ===== */
        .reveal {
            opacity: 0;
            transform: translateY(30px);
            transition: opacity 0.7s ease, transform 0.7s ease;
        }
        .reveal.visible {
            opacity: 1;
            transform: translateY(0);
        }

        .reveal-left {
            opacity: 0;
            transform: translateX(-30px);
            transition: opacity 0.7s ease, transform 0.7s ease;
        }
        .reveal-left.visible {
            opacity: 1;
            transform: translateX(0);
        }

        .reveal-right {
            opacity: 0;
            transform: translateX(30px);
            transition: opacity 0.7s ease, transform 0.7s ease;
        }
        .reveal-right.visible {
            opacity: 1;
            transform: translateX(0);
        }

        .reveal-scale {
            opacity: 0;
            transform: scale(0.95);
            transition: opacity 0.7s ease, transform 0.7s ease;
        }
        .reveal-scale.visible {
            opacity: 1;
            transform: scale(1);
        }

        /* stagger children */
        .stagger>* {
            opacity: 0;
            transform: translateY(20px);
            transition: opacity 0.5s ease, transform 0.5s ease;
        }
        .stagger.visible>*:nth-child(1) {
            transition-delay: 0.05s;
        }
        .stagger.visible>*:nth-child(2) {
            transition-delay: 0.1s;
        }
        .stagger.visible>*:nth-child(3) {
            transition-delay: 0.15s;
        }
        .stagger.visible>*:nth-child(4) {
            transition-delay: 0.2s;
        }
        .stagger.visible>*:nth-child(5) {
            transition-delay: 0.25s;
        }
        .stagger.visible>*:nth-child(6) {
            transition-delay: 0.3s;
        }
        .stagger.visible>* {
            opacity: 1;
            transform: translateY(0);
        }
    </style>
</head>

<body>

    <!-- ===== TOAST CONTAINER ===== -->
    <div class="toast-container" id="toastContainer"></div>

    <!-- ===== NAVBAR ===== -->
    <nav class="navbar" id="navbar" role="navigation" aria-label="Main navigation">
        <div class="container">
            <a href="#home" class="nav-logo">V<span class="accent">.</span>Kushwaha</a>

            <ul class="nav-links" id="navLinks" role="menubar">
                <li role="none"><a href="#home" role="menuitem" class="active">Home</a></li>
                <li role="none"><a href="#about" role="menuitem">About</a></li>
                <li role="none"><a href="#skills" role="menuitem">Skills</a></li>
                <li role="none"><a href="#education" role="menuitem">Education</a></li>
                <li role="none"><a href="#experience" role="menuitem">Experience</a></li>
                <li role="none"><a href="#projects" role="menuitem">Projects</a></li>
                <li role="none"><a href="#certifications" role="menuitem">Certifications</a></li>
                <li role="none"><a href="#resume" role="menuitem">Resume</a></li>
                <li role="none"><a href="#contact" role="menuitem">Contact</a></li>
            </ul>

            <button class="hamburger" id="hamburger" aria-label="Toggle navigation menu" aria-expanded="false">
                <span></span>
                <span></span>
                <span></span>
            </button>
        </div>
    </nav>

    <!-- ===== HERO ===== -->
    <section class="hero" id="home">
        <div class="container">
            <div class="hero-content">
                <div class="badge">
                    <span class="dot"></span>
                    Open to opportunities
                </div>
                <h1>Hi, I'm <span class="highlight">Vansh Kushwaha</span></h1>
                <p class="tagline">Frontend Developer · React · React Native · MERN</p>
                <div class="hero-actions">
                    <a href="#projects" class="btn btn-primary">
                        <i class="fas fa-code"></i> View Projects
                    </a>
                    <a href="#contact" class="btn btn-outline">
                        <i class="fas fa-paper-plane"></i> Contact
                    </a>
                </div>
                <div class="hero-social">
                    <a href="https://github.com/vanshkushwaha8" target="_blank" aria-label="GitHub"><i class="fab fa-github"></i></a>
                    <a href="https://www.linkedin.com/in/vansh-kushwaha-71640a25b/" target="_blank" aria-label="LinkedIn"><i class="fab fa-linkedin-in"></i></a>
                    <a href="https://www.instagram.com/vansh_kushwaha__/" target="_blank" aria-label="Instagram"><i class="fab fa-instagram"></i></a>
                    <a href="mailto:vanshkushwaha34@gmail.com" aria-label="Email"><i class="fas fa-envelope"></i></a>
                    <a href="https://www.leetcode.com/tlgmdjrmqq" target="_blank" aria-label="LeetCode"><i class="fas fa-code"></i></a>
                </div>
            </div>

            <div class="hero-visual">
                <div class="hero-avatar" id="heroAvatar">
                    VK
                    <span class="status-ring"></span>
                    <div class="floating-badge" style="top: 8%; right: -6%;">
                        <i class="fas fa-database"></i> MongoDB
                    </div>
                    <div class="floating-badge" style="bottom: 18%; left: -4%;">
                        <i class="fab fa-react"></i> React
                    </div>
                    <div class="floating-badge" style="top: 48%; right: -8%;">
                        <i class="fab fa-node-js"></i> Node.js
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- ===== ABOUT ===== -->
    <section id="about">
        <div class="container">
            <div class="section-header">
                <span class="section-label">About Me</span>
                <h2 class="section-title">Building <span class="highlight">impactful</span> experiences</h2>
                <p class="section-subtitle">Passionate frontend developer from India, currently exploring Vue.js and building mobile apps with React Native.</p>
            </div>

            <div class="about-grid">
                <div class="about-text">
                    <p>
                        I'm a frontend developer with a B.Tech in Computer Science, deeply passionate about crafting intuitive user interfaces and seamless experiences. I have experience with React, React Native, and the MERN stack, and I'm currently learning Vue.js to broaden my skill set.
                    </p>
                    <p>
                        Beyond coding, I enjoy organizing hackathons and tech workshops — I've led events with 250+ participants. I believe in the power of community and continuous learning.
                    </p>
                    <div class="about-stats">
                        <div class="stat-item">
                            <span class="number">1+</span>
                            <span class="label">Years Experience</span>
                        </div>
                        <div class="stat-item">
                            <span class="number">10+</span>
                            <span class="label">Projects Delivered</span>
                        </div>
                        <div class="stat-item">
                            <span class="number">8.48</span>
                            <span class="label">CGPA</span>
                        </div>
                    </div>
                </div>

                <div class="about-interests">
                    <h3><i class="fas fa-heart" style="color:var(--accent);margin-right:8px;"></i> What I'm Into</h3>
                    <div class="interest-tags">
                        <span>🚀 React</span>
                        <span>📱 React Native</span>
                        <span>⚛️ Vue.js</span>
                        <span>☁️ Firebase</span>
                        <span>🎨 UI/UX</span>
                        <span>🧠 AI/ML</span>
                        <span>📊 Data Viz</span>
                        <span>🎯 Hackathons</span>
                    </div>
                    <br />
                    <p style="color:var(--text-secondary);font-size:0.95rem;margin-top:8px;">
                        <i class="fas fa-quote-left" style="color:var(--accent);margin-right:6px;opacity:0.6;"></i>
                        Currently working on <strong>MASTYA JEEVAN</strong> — a React Native app, and always exploring new tools to build better products.
                    </p>
                </div>
            </div>
        </div>
    </section>

    <!-- ===== SKILLS ===== -->
    <section id="skills">
        <div class="container">
            <div class="section-header centered">
                <span class="section-label">Technical Skills</span>
                <h2 class="section-title">My <span class="highlight">tech stack</span></h2>
                <p class="section-subtitle">Languages, frameworks, tools, and practices I work with daily.</p>
            </div>

            <div class="skills-grid stagger" id="skillsGrid">
                <div class="skill-category">
                    <div class="cat-icon"><i class="fas fa-code"></i></div>
                    <h4>Languages</h4>
                    <div class="skill-tags">
                        <span>JavaScript</span>
                        <span>TypeScript</span>
                        <span>Java</span>
                        <span>Python</span>
                        <span>MATLAB</span>
                    </div>
                </div>

                <div class="skill-category">
                    <div class="cat-icon"><i class="fas fa-laptop-code"></i></div>
                    <h4>Frontend</h4>
                    <div class="skill-tags">
                        <span>React.js</span>
                        <span>Next.js</span>
                        <span>React Native</span>
                        <span>Vue.js</span>
                        <span>HTML5</span>
                        <span>CSS3</span>
                        <span>Tailwind CSS</span>
                        <span>Redux</span>
                    </div>
                </div>

                <div class="skill-category">
                    <div class="cat-icon"><i class="fas fa-server"></i></div>
                    <h4>Backend</h4>
                    <div class="skill-tags">
                        <span>Node.js</span>
                        <span>Express.js</span>
                        <span>REST API</span>
                        <span>Auth &amp; AuthZ</span>
                    </div>
                </div>

                <div class="skill-category">
                    <div class="cat-icon"><i class="fas fa-database"></i></div>
                    <h4>Database</h4>
                    <div class="skill-tags">
                        <span>MongoDB</span>
                        <span>PostgreSQL</span>
                        <span>Prisma ORM</span>
                        <span>Firebase</span>
                    </div>
                </div>

                <div class="skill-category">
                    <div class="cat-icon"><i class="fas fa-tools"></i></div>
                    <h4>Design &amp; Tools</h4>
                    <div class="skill-tags">
                        <span>Figma</span>
                        <span>Adobe Illustrator</span>
                        <span>Photoshop</span>
                        <span>Git</span>
                        <span>Postman</span>
                        <span>VS Code</span>
                    </div>
                </div>

                <div class="skill-category">
                    <div class="cat-icon"><i class="fas fa-brain"></i></div>
                    <h4>Currently Learning</h4>
                    <div class="skill-tags">
                        <span>Vue.js</span>
                        <span>AI/ML Fundamentals</span>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- ===== EDUCATION ===== -->
    <section id="education">
        <div class="container">
            <div class="section-header centered">
                <span class="section-label">Education</span>
                <h2 class="section-title">Academic <span class="highlight">background</span></h2>
            </div>

            <div class="edu-timeline">
                <div class="edu-item">
                    <div class="left">
                        <h4>B.Tech in Computer Science &amp; Engineering</h4>
                        <span class="institute">Centurion University of Technology and Management, Odisha</span>
                    </div>
                    <div class="right">
                        <span>2021 – 2025</span><br />
                        <span class="cgpa">CGPA: 8.48</span>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- ===== EXPERIENCE ===== -->
    <section id="experience">
        <div class="container">
            <div class="section-header">
                <span class="section-label">Work Experience</span>
                <h2 class="section-title">Where I've <span class="highlight">built impact</span></h2>
                <p class="section-subtitle">Professional experience and key contributions.</p>
            </div>

            <div class="exp-timeline">
                <div class="exp-item">
                    <div class="exp-header">
                        <div>
                            <h3>Software Developer</h3>
                            <span class="company">Brain Technosys Pvt. Ltd.</span>
                        </div>
                        <span class="date">Feb 2025 – Aug 2026</span>
                    </div>
                    <div class="exp-desc">
                        <ul>
                            <li>Architected and deployed 50+ production REST APIs across Opalus, Shift Work, Hirra, and HomiiConnect using Express.js, MongoDB, PostgreSQL, and Prisma ORM.</li>
                            <li>Engineered an 8-step KYC onboarding flow with Sumsub WebSDK covering residency verification, tax profiling, investor categorization, and knowledge assessments.</li>
                            <li>Designed and implemented Epic E15, a money operations and financial crime compliance module using a provider-agnostic adapter pattern and environment toggles.</li>
                            <li>Built a project publication state machine covering submitted, under review, approval, and live stages with conditional field mutability, role-based transitions, and automated admin review.</li>
                            <li>Optimized investor pagination using a dual-pipeline Promise.all approach and resolved state-machine desynchronization across 100+ active projects.</li>
                            <li>Developed Shift Work backend infrastructure including soft-delete mechanisms, cron-based invoice generation with PDF rendering, Australian tax-compliant formatting, OTP-based account deletion, and public compliance pages.</li>
                        </ul>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- ===== PROJECTS ===== -->
    <section id="projects">
        <div class="container">
            <div class="section-header">
                <span class="section-label">Projects</span>
                <h2 class="section-title">Featured <span class="highlight">work</span></h2>
                <p class="section-subtitle">Real-world platforms I've contributed to as a full-stack engineer, plus personal projects.</p>
            </div>

            <div class="projects-grid">
                <!-- Opalus -->
                <div class="project-card">
                    <div class="p-icon"><i class="fas fa-building"></i></div>
                    <h4>Opalus</h4>
                    <div class="p-tech">Real Estate Crowdfunding Investment Platform</div>
                    <div class="p-desc">
                        Full-stack contribution on an ECSP-regulated investment platform supporting 100+ concurrent investors.
                        Architected 50+ REST APIs for project lifecycle, investor onboarding, transactions, and compliance.
                        Implemented 8-step KYC/AML with Sumsub identity verification and a provider-agnostic payment adapter.
                    </div>
                    <div class="p-tags">
                        <span>Node.js</span>
                        <span>Express</span>
                        <span>MongoDB</span>
                        <span>PostgreSQL</span>
                        <span>React</span>
                        <span>Sumsub</span>
                    </div>
                    <a href="https://opalusdev.etrueconcept.com/" target="_blank" class="p-link">Live Demo <i class="fas fa-arrow-right"></i></a>
                </div>

                <!-- Shift Work -->
                <div class="project-card">
                    <div class="p-icon"><i class="fas fa-clock"></i></div>
                    <h4>Shift Work</h4>
                    <div class="p-tech">Workforce &amp; Shift Management Platform</div>
                    <div class="p-desc">
                        Architected backend infrastructure serving 1000+ concurrent mobile and web users.
                        Implemented 30+ REST APIs for scheduling, timers, payments, and reporting.
                        Engineered cron-based invoice generation with PDF rendering, Australian tax-compliant formatting,
                        and automated overdue transitions — 500+ monthly invoices at 99.8% accuracy.
                    </div>
                    <div class="p-tags">
                        <span>Node.js</span>
                        <span>Express</span>
                        <span>TypeScript</span>
                        <span>MongoDB</span>
                        <span>Prisma</span>
                        <span>React Native</span>
                        <span>PostgreSQL</span>
                    </div>
                    <a href="https://shiftwork.au/" target="_blank" class="p-link">Live Demo <i class="fas fa-arrow-right"></i></a>
                </div>

                <!-- Hirra -->
                <div class="project-card">
                    <div class="p-icon"><i class="fas fa-users"></i></div>
                    <h4>Hirra</h4>
                    <div class="p-tech">Workforce Hiring Platform</div>
                    <div class="p-desc">
                        Developed backend hiring workflows and CRUD APIs for subcontractor and tradesperson management,
                        applicant tracking, and job matching. Built React admin dashboard with RBAC and multi-role
                        authentication for admin, recruiter, and applicant personas.
                    </div>
                    <div class="p-tags">
                        <span>Node.js</span>
                        <span>Express</span>
                        <span>MongoDB</span>
                        <span>React</span>
                        <span>Material UI</span>
                    </div>
                    <a href="https://hira.etrueconcept.com/" target="_blank" class="p-link">Live Demo <i class="fas fa-arrow-right"></i></a>
                </div>

                <!-- HomiiConnect -->
                <div class="project-card">
                    <div class="p-icon"><i class="fas fa-share-alt"></i></div>
                    <h4>HomiiConnect</h4>
                    <div class="p-tech">Social Media &amp; Marketplace Platform</div>
                    <div class="p-desc">
                        Developed backend architecture and scalable APIs for posts, videos, stories, communities, polls,
                        and marketplace functionality. Optimized PostgreSQL schemas and backend performance using Prisma ORM
                        and production-grade API architecture.
                    </div>
                    <div class="p-tags">
                        <span>Next.js</span>
                        <span>Prisma</span>
                        <span>PostgreSQL</span>
                    </div>
                    <a href="https://homii.etrueconcept.com/" target="_blank" class="p-link">Live Demo <i class="fas fa-arrow-right"></i></a>
                </div>

                <!-- vanshTastic (new from README) -->
                <div class="project-card">
                    <div class="p-icon"><i class="fas fa-shopping-cart"></i></div>
                    <h4>vanshTastic</h4>
                    <div class="p-tech">E-Commerce Website (React.js)</div>
                    <div class="p-desc">
                        A fully functional e-commerce store built with React.js, featuring product listings, cart management, and a seamless checkout experience. Deployed on Netlify.
                    </div>
                    <div class="p-tags">
                        <span>React</span>
                        <span>Redux</span>
                        <span>CSS</span>
                        <span>Netlify</span>
                    </div>
                    <a href="https://vanshtastic.netlify.app/" target="_blank" class="p-link">Live Demo <i class="fas fa-arrow-right"></i></a>
                </div>

                <!-- MASTYA JEEVAN (currently working) -->
                <div class="project-card">
                    <div class="p-icon"><i class="fas fa-mobile-alt"></i></div>
                    <h4>MASTYA JEEVAN</h4>
                    <div class="p-tech">Mobile App (React Native)</div>
                    <div class="p-desc">
                        Currently developing a React Native app — a lifestyle and wellness platform. Focused on delivering a smooth user experience with modern UI components and real-time data.
                    </div>
                    <div class="p-tags">
                        <span>React Native</span>
                        <span>Firebase</span>
                        <span>Expo</span>
                    </div>
                    <span class="p-link" style="color:var(--text-muted);">In Progress</span>
                </div>
            </div>
        </div>
    </section>

    <!-- ===== CERTIFICATIONS ===== -->
    <section id="certifications">
        <div class="container">
            <div class="section-header centered">
                <span class="section-label">Certifications &amp; Achievements</span>
                <h2 class="section-title">Recognitions &amp; <span class="highlight">impact</span></h2>
            </div>

            <div class="certs-grid">
                <div class="cert-item">
                    <i class="fas fa-certificate"></i>
                    <h5>MERN Stack Web Development</h5>
                    <p>CodeHelp</p>
                </div>
                <div class="cert-item">
                    <i class="fas fa-brain"></i>
                    <h5>Problem Solving &amp; Algorithms</h5>
                    <p>TCAC</p>
                </div>
                <div class="cert-item">
                    <i class="fas fa-users"></i>
                    <h5>Hackathon Organizer</h5>
                    <p>250+ participants · Technology workshops</p>
                </div>
                <div class="cert-item">
                    <i class="fas fa-trophy"></i>
                    <h5>Tech Workshop Lead</h5>
                    <p>Hands-on sessions &amp; mentoring</p>
                </div>
            </div>
        </div>
    </section>

    <!-- ===== RESUME ===== -->
    <section id="resume">
        <div class="container">
            <div class="resume-box reveal-scale">
                <i class="fas fa-file-pdf"></i>
                <h3>Download my Resume</h3>
                <p>Get a complete overview of my experience, skills, and education in one document.</p>
                <a href="https://drive.google.com/file/d/1p8Aiw24e75HX1wEpNbWv_n2Zu_6fTBen/view?usp=sharing" target="_blank" class="btn btn-primary">
                    <i class="fas fa-download"></i> View on Google Drive
                </a>
            </div>
        </div>
    </section>

    <!-- ===== CONTACT ===== -->
    <section id="contact">
        <div class="container">
            <div class="section-header centered">
                <span class="section-label">Contact</span>
                <h2 class="section-title">Let's <span class="highlight">connect</span></h2>
                <p class="section-subtitle">Have a question or want to work together? Reach out anytime.</p>
            </div>

            <div class="contact-grid">
                <div class="contact-info">
                    <h3>Get in touch</h3>
                    <p>I'm always open to interesting conversations, collaboration opportunities, and new challenges.</p>

                    <div class="contact-item">
                        <i class="fas fa-envelope"></i>
                        <div class="info">
                            <span class="label">Email</span>
                            <a href="mailto:vanshkushwaha34@gmail.com">vanshkushwaha34@gmail.com</a>
                        </div>
                    </div>
                    <div class="contact-item">
                        <i class="fas fa-map-marker-alt"></i>
                        <div class="info">
                            <span class="label">Location</span>
                            Odisha, India
                        </div>
                    </div>
                    <div class="contact-item">
                        <i class="fab fa-github"></i>
                        <div class="info">
                            <span class="label">GitHub</span>
                            <a href="https://github.com/vanshkushwaha8" target="_blank">github.com/vanshkushwaha8</a>
                        </div>
                    </div>
                    <div class="contact-item">
                        <i class="fab fa-linkedin-in"></i>
                        <div class="info">
                            <span class="label">LinkedIn</span>
                            <a href="https://www.linkedin.com/in/vansh-kushwaha-71640a25b/" target="_blank">linkedin.com/in/vansh-kushwaha</a>
                        </div>
                    </div>
                    <div class="contact-item">
                        <i class="fab fa-instagram"></i>
                        <div class="info">
                            <span class="label">Instagram</span>
                            <a href="https://www.instagram.com/vansh_kushwaha__/" target="_blank">@vansh_kushwaha__</a>
                        </div>
                    </div>
                </div>

                <form class="contact-form" id="contactForm">
                    <div class="form-group">
                        <label for="name">Your Name</label>
                        <input type="text" id="name" placeholder="John Doe" required />
                    </div>
                    <div class="form-group">
                        <label for="email">Email Address</label>
                        <input type="email" id="email" placeholder="john@example.com" required />
                    </div>
                    <div class="form-group">
                        <label for="message">Message</label>
                        <textarea id="message" placeholder="Tell me about your project or opportunity..." required></textarea>
                    </div>
                    <button type="submit" class="btn btn-primary">
                        <i class="fas fa-paper-plane"></i> Send Message
                    </button>
                </form>
            </div>
        </div>
    </section>

    <!-- ===== FOOTER ===== -->
    <footer>
        <div class="container">
            <p>&copy; 2026 Vansh Kushwaha. Crafted with <i class="fas fa-heart" style="color:var(--accent);"></i></p>
            <div class="social">
                <a href="https://github.com/vanshkushwaha8" target="_blank" aria-label="GitHub"><i class="fab fa-github"></i></a>
                <a href="https://www.linkedin.com/in/vansh-kushwaha-71640a25b/" target="_blank" aria-label="LinkedIn"><i class="fab fa-linkedin-in"></i></a>
                <a href="https://www.instagram.com/vansh_kushwaha__/" target="_blank" aria-label="Instagram"><i class="fab fa-instagram"></i></a>
                <a href="mailto:vanshkushwaha34@gmail.com" aria-label="Email"><i class="fas fa-envelope"></i></a>
                <a href="https://www.leetcode.com/tlgmdjrmqq" target="_blank" aria-label="LeetCode"><i class="fas fa-code"></i></a>
            </div>
        </div>
    </footer>

    <!-- ===== JAVASCRIPT ===== -->
    <script>
        document.addEventListener('DOMContentLoaded', () => {

            // ===== Toast System =====
            const toastContainer = document.getElementById('toastContainer');

            function showToast(title, message, type = 'success', duration = 4000) {
                const toast = document.createElement('div');
                toast.className = `toast ${type}`;

                const iconMap = {
                    success: 'fa-check-circle',
                    error: 'fa-exclamation-circle',
                    warning: 'fa-exclamation-triangle'
                };
                const icon = iconMap[type] || iconMap.success;

                toast.innerHTML = `
                        <div class="toast-icon">
                            <i class="fas ${icon}"></i>
                        </div>
                        <div class="toast-content">
                            <div class="toast-title">${title}</div>
                            <div class="toast-message">${message}</div>
                        </div>
                        <button class="toast-close" aria-label="Close notification">
                            <i class="fas fa-times"></i>
                        </button>
                    `;

                toastContainer.appendChild(toast);

                requestAnimationFrame(() => {
                    toast.classList.add('show');
                });

                const closeBtn = toast.querySelector('.toast-close');
                closeBtn.addEventListener('click', () => {
                    dismissToast(toast);
                });

                let timeout = setTimeout(() => {
                    dismissToast(toast);
                }, duration);

                toast.addEventListener('mouseenter', () => {
                    clearTimeout(timeout);
                });
                toast.addEventListener('mouseleave', () => {
                    timeout = setTimeout(() => {
                        dismissToast(toast);
                    }, 1500);
                });

                return toast;
            }

            function dismissToast(toast) {
                if (toast.classList.contains('hide')) return;
                toast.classList.remove('show');
                toast.classList.add('hide');
                setTimeout(() => {
                    if (toast.parentNode) {
                        toast.remove();
                    }
                }, 400);
            }

            // ===== Mobile Nav Toggle =====
            const hamburger = document.getElementById('hamburger');
            const navLinks = document.getElementById('navLinks');

            hamburger.addEventListener('click', () => {
                const isOpen = navLinks.classList.toggle('open');
                hamburger.classList.toggle('active');
                hamburger.setAttribute('aria-expanded', isOpen);
            });

            document.querySelectorAll('.nav-links a').forEach(link => {
                link.addEventListener('click', () => {
                    navLinks.classList.remove('open');
                    hamburger.classList.remove('active');
                    hamburger.setAttribute('aria-expanded', 'false');
                });
            });

            // ===== Navbar scroll effect =====
            const navbar = document.getElementById('navbar');

            window.addEventListener('scroll', () => {
                const currentScroll = window.pageYOffset || document.documentElement.scrollTop;
                if (currentScroll > 50) {
                    navbar.classList.add('scrolled');
                } else {
                    navbar.classList.remove('scrolled');
                }

                const sections = document.querySelectorAll('section[id]');
                let currentSection = '';
                sections.forEach(section => {
                    const top = section.offsetTop - 120;
                    const height = section.offsetHeight;
                    if (currentScroll >= top && currentScroll < top + height) {
                        currentSection = section.getAttribute('id');
                    }
                });

                document.querySelectorAll('.nav-links a').forEach(link => {
                    link.classList.remove('active');
                    if (link.getAttribute('href') === `#${currentSection}`) {
                        link.classList.add('active');
                    }
                });
            });

            // ===== Reveal on scroll =====
            const revealElements = document.querySelectorAll('.reveal, .reveal-left, .reveal-right, .reveal-scale, .stagger');
            const observer = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.classList.add('visible');
                        if (entry.target.classList.contains('stagger')) {
                            entry.target.classList.add('visible');
                        }
                    }
                });
            }, {
                threshold: 0.1,
                rootMargin: '0px 0px -40px 0px'
            });
            revealElements.forEach(el => observer.observe(el));
            document.querySelectorAll('.stagger').forEach(el => observer.observe(el));

            // ===== Contact form =====
            const contactForm = document.getElementById('contactForm');
            contactForm.addEventListener('submit', (e) => {
                e.preventDefault();
                const name = document.getElementById('name').value.trim();
                const email = document.getElementById('email').value.trim();
                const message = document.getElementById('message').value.trim();

                if (!name || !email || !message) {
                    showToast('Missing Fields', 'Please fill in all fields before sending.', 'error', 3500);
                    return;
                }
                if (!email.includes('@') || !email.includes('.')) {
                    showToast('Invalid Email', 'Please enter a valid email address.', 'error', 3500);
                    return;
                }

                showToast(
                    'Message Sent! 🎉',
                    `Thanks, ${name}! I'll get back to you soon.`,
                    'success',
                    4500
                );
                contactForm.reset();
            });

            // ===== Hero avatar reveal =====
            const avatar = document.getElementById('heroAvatar');
            setTimeout(() => {
                avatar.style.opacity = '1';
                avatar.style.transform = 'scale(1)';
            }, 300);

            // ===== Update footer year =====
            document.querySelector('footer p').innerHTML =
                `&copy; ${new Date().getFullYear()} Vansh Kushwaha. Crafted with <i class="fas fa-heart" style="color:var(--accent);"></i>`;

        });
    </script>

</body>
</html>
