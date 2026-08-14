<!DOCTYPE html>
<html lang="th">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>YellowGreenRed - Roblox Studio Developer Group</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Kanit:wght@300;400;600;700;800&family=Orbitron:wght@600;800;900&display=swap" rel="stylesheet">
    <style>
        :root {
            --yellow: #f1c40f;
            --green: #2ecc71;
            --red: #e74c3c;
            --dark-bg: #0b0c10;
            --card-bg: #1f2833;
            --card-hover: #25303e;
            --text-main: #ffffff;
            --text-muted: #c5c6c7;
            --accent-glow: rgba(241, 196, 15, 0.2);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Kanit', sans-serif;
            background-color: var(--dark-bg);
            color: var(--text-main);
            line-height: 1.6;
            overflow-x: hidden;
        }

        /* Header / Navbar */
        header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 1.2rem 8%;
            background: rgba(11, 12, 16, 0.85);
            backdrop-filter: blur(12px);
            position: fixed;
            top: 0;
            width: 100%;
            z-index: 1000;
            border-bottom: 1px solid rgba(255, 255, 255, 0.08);
        }

        .logo-container {
            display: flex;
            align-items: center;
            gap: 12px;
            text-decoration: none;
        }

        .logo-container img {
            width: 42px;
            height: 42px;
            border-radius: 50%;
            object-fit: cover;
            box-shadow: 0 0 10px rgba(255, 255, 255, 0.15);
        }

        .brand-name {
            font-family: 'Orbitron', sans-serif;
            font-size: 1.3rem;
            font-weight: 800;
            letter-spacing: 1px;
            background: linear-gradient(90deg, var(--yellow), var(--green), var(--red));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        nav ul {
            display: flex;
            list-style: none;
            gap: 2rem;
        }

        nav a {
            color: var(--text-muted);
            text-decoration: none;
            font-weight: 500;
            transition: all 0.3s ease;
            position: relative;
        }

        nav a:hover {
            color: #fff;
        }

        nav a::after {
            content: '';
            position: absolute;
            width: 0%;
            height: 2px;
            bottom: -4px;
            left: 0;
            background: linear-gradient(90deg, var(--yellow), var(--green), var(--red));
            transition: width 0.3s ease;
        }

        nav a:hover::after {
            width: 100%;
        }

        .cta-btn {
            background: linear-gradient(135deg, #e74c3c, #c0392b);
            color: #fff;
            padding: 0.6rem 1.4rem;
            border-radius: 30px;
            text-decoration: none;
            font-weight: 600;
            transition: transform 0.3s, box-shadow 0.3s;
            box-shadow: 0 4px 15px rgba(231, 76, 60, 0.4);
            display: inline-block;
        }

        .cta-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 6px 20px rgba(231, 76, 60, 0.6);
        }

        /* Hero Section */
        .hero {
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            padding: 120px 8% 60px;
            position: relative;
            background: radial-gradient(circle at 50% 30%, rgba(241, 196, 15, 0.08) 0%, rgba(46, 204, 113, 0.05) 30%, rgba(231, 76, 60, 0.05) 60%, rgba(11, 12, 16, 1) 100%);
        }

        .hero-content {
            max-width: 1200px;
            display: flex;
            align-items: center;
            gap: 4rem;
            width: 100%;
        }

        .hero-text {
            flex: 1;
        }

        .hero-tag {
            display: inline-block;
            background: rgba(255, 255, 255, 0.08);
            padding: 6px 16px;
            border-radius: 20px;
            font-size: 0.9rem;
            color: var(--yellow);
            border: 1px solid rgba(241, 196, 15, 0.3);
            margin-bottom: 1.5rem;
            font-weight: 500;
        }

        .hero-title {
            font-size: 3.5rem;
            font-weight: 800;
            line-height: 1.2;
            margin-bottom: 1.2rem;
        }

        .hero-title span.y { color: var(--yellow); }
        .hero-title span.g { color: var(--green); }
        .hero-title span.r { color: var(--red); }

        .hero-desc {
            font-size: 1.15rem;
            color: var(--text-muted);
            margin-bottom: 2rem;
            font-weight: 300;
        }

        .hero-buttons {
            display: flex;
            gap: 1rem;
        }

        .btn-secondary {
            border: 1px solid rgba(255,255,255,0.2);
            background: rgba(255,255,255,0.05);
            color: #fff;
            padding: 0.6rem 1.4rem;
            border-radius: 30px;
            text-decoration: none;
            font-weight: 600;
            transition: all 0.3s;
        }

        .btn-secondary:hover {
            background: rgba(255,255,255,0.15);
            border-color: rgba(255,255,255,0.4);
        }

        .hero-logo-display {
            flex: 1;
            display: flex;
            justify-content: center;
            align-items: center;
            position: relative;
        }

        .hero-logo-img {
            width: 320px;
            max-width: 100%;
            filter: drop-shadow(0 0 35px rgba(241, 196, 15, 0.25));
            animation: float 4s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-15px); }
        }

        /* Section Title */
        .section-title {
            text-align: center;
            margin-bottom: 3rem;
        }

        .section-title h2 {
            font-size: 2.2rem;
            font-weight: 700;
            letter-spacing: 0.5px;
        }

        .section-title p {
            color: var(--text-muted);
            font-size: 1rem;
            margin-top: 0.4rem;
        }

        /* Games Section */
        .games-section {
            padding: 80px 8%;
            background: #08090c;
        }

        .games-grid {
            display: flex;
            justify-content: center;
            gap: 2.5rem;
            max-width: 1100px;
            margin: 0 auto;
        }

        .game-card {
            background: var(--card-bg);
            border-radius: 20px;
            overflow: hidden;
            border: 1px solid rgba(255,255,255,0.08);
            transition: all 0.3s cubic-bezier(0.25, 0.8, 0.25, 1);
            max-width: 500px;
            width: 100%;
            position: relative;
        }

        .game-card:hover {
            transform: translateY(-8px);
            border-color: rgba(241, 196, 15, 0.4);
            box-shadow: 0 15px 30px rgba(0,0,0,0.5), 0 0 20px rgba(241, 196, 15, 0.15);
        }

        .game-banner {
            height: 220px;
            background: linear-gradient(135deg, #11141a, #1a2332);
            display: flex;
            align-items: center;
            justify-content: center;
            position: relative;
            overflow: hidden;
        }

        .game-banner-icon {
            font-size: 3.5rem;
            background: linear-gradient(45deg, var(--yellow), var(--red));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            font-weight: 900;
            font-family: 'Orbitron', sans-serif;
            text-shadow: 0 0 20px rgba(231, 76, 60, 0.3);
        }

        .badge-live {
            position: absolute;
            top: 15px;
            right: 15px;
            background: rgba(46, 204, 113, 0.2);
            color: var(--green);
            border: 1px solid var(--green);
            padding: 4px 12px;
            border-radius: 20px;
            font-size: 0.8rem;
            font-weight: 600;
            display: flex;
            align-items: center;
            gap: 6px;
        }

        .badge-live::before {
            content: '';
            width: 8px;
            height: 8px;
            background-color: var(--green);
            border-radius: 50%;
            display: inline-block;
            box-shadow: 0 0 8px var(--green);
        }

        .game-info {
            padding: 2rem;
        }

        .game-title {
            font-size: 1.8rem;
            font-weight: 700;
            margin-bottom: 0.8rem;
            color: #fff;
        }

        .game-desc {
            color: var(--text-muted);
            font-size: 0.98rem;
            margin-bottom: 1.5rem;
            font-weight: 300;
        }

        .game-stats {
            display: flex;
            gap: 1.5rem;
            margin-bottom: 1.8rem;
            padding-top: 1rem;
            border-top: 1px solid rgba(255, 255, 255, 0.08);
        }

        .stat-item {
            display: flex;
            flex-direction: column;
        }

        .stat-value {
            font-weight: 700;
            font-size: 1.1rem;
            color: #fff;
        }

        .stat-label {
            font-size: 0.8rem;
            color: var(--text-muted);
        }

        .play-btn {
            display: block;
            width: 100%;
            text-align: center;
            background: linear-gradient(90deg, var(--yellow), #f39c12);
            color: #000;
            font-weight: 700;
            padding: 0.8rem;
            border-radius: 12px;
            text-decoration: none;
            transition: all 0.3s ease;
        }

        .play-btn:hover {
            opacity: 0.9;
            box-shadow: 0 0 15px rgba(241, 196, 15, 0.4);
        }

        /* About Section */
        .about-section {
            padding: 80px 8%;
            max-width: 1100px;
            margin: 0 auto;
        }

        .about-cards {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 2rem;
            margin-top: 2rem;
        }

        .about-card {
            background: var(--card-bg);
            padding: 2rem;
            border-radius: 16px;
            border: 1px solid rgba(255,255,255,0.05);
            transition: transform 0.3s;
        }

        .about-card:hover {
            transform: translateY(-5px);
        }

        .about-icon {
            font-size: 2rem;
            margin-bottom: 1rem;
            display: inline-block;
        }

        .about-card.yellow .about-icon { color: var(--yellow); }
        .about-card.green .about-icon { color: var(--green); }
        .about-card.red .about-icon { color: var(--red); }

        .about-card h3 {
            font-size: 1.25rem;
            margin-bottom: 0.6rem;
        }

        .about-card p {
            color: var(--text-muted);
            font-size: 0.95rem;
            font-weight: 300;
        }

        /* Footer */
        footer {
            background: #050507;
            padding: 40px 8% 20px;
            text-align: center;
            border-top: 1px solid rgba(255,255,255,0.05);
        }

        .footer-logo {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
            margin-bottom: 1rem;
        }

        .footer-logo img {
            width: 30px;
            height: 30px;
            border-radius: 50%;
        }

        .footer-text {
            color: var(--text-muted);
            font-size: 0.9rem;
            margin-bottom: 1.5rem;
        }

        .copyright {
            color: rgba(255,255,255,0.3);
            font-size: 0.8rem;
            border-top: 1px solid rgba(255,255,255,0.05);
            padding-top: 1.5rem;
        }

        /* Responsive */
        @media (max-width: 900px) {
            .hero-content {
                flex-direction: column-reverse;
                text-align: center;
                gap: 2rem;
            }

            .hero-buttons {
                justify-content: center;
            }

            .hero-title {
                font-size: 2.5rem;
            }

            nav ul {
                display: none;
            }
        }
    </style>
</head>
<body>

    <!-- Header Navigation -->
    <header>
        <a href="#" class="logo-container">
            <img src="data:image/png;base64,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
