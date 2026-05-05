# my_protfolio
<!DOCTYPE html>
<html lang="en" data-theme="dark">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>M. Delfina Masarallo — Web Developer</title>
  <meta name="description" content="M. Delfina Masarallo — Aspiring Web Developer skilled in React.js, JavaScript, HTML5, CSS3. Building responsive, scalable web applications." />
  <meta name="keywords" content="Web Developer, React, JavaScript, Frontend, Portfolio, Tamil Nadu" />
  <meta name="author" content="M. Delfina Masarallo" />
  <meta property="og:title" content="M. Delfina Masarallo — Web Developer" />
  <meta property="og:description" content="Frontend Developer crafting responsive, scalable web experiences." />
  <meta property="og:type" content="website" />
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,700;0,900;1,400&family=DM+Sans:wght@300;400;500;600&family=DM+Mono:wght@400;500&display=swap" rel="stylesheet" />
 <style>
   /* ─── TOKENS ─────────────────────────────────────────── */
    :root {
      --bg: #0a0a0f;
      --bg2: #111118;
      --bg3: #18181f;
      --border: rgba(255,255,255,0.07);
      --text: #e8e8f0;
      --muted: #888899;
      --accent: #c8a96e;
      --accent2: #e8c98e;
      --accent-glow: rgba(200,169,110,0.15);
      --card: rgba(255,255,255,0.03);
      --card-hover: rgba(255,255,255,0.06);
      --radius: 16px;
      --nav-h: 72px;
      --transition: 0.3s cubic-bezier(0.4,0,0.2,1);
    }
    [data-theme="light"] {
      --bg: #faf9f6;
      --bg2: #f2f0eb;
      --bg3: #e8e5de;
      --border: rgba(0,0,0,0.08);
      --text: #1a1a2e;
      --muted: #666677;
      --accent: #9a6f3a;
      --accent2: #b88040;
      --accent-glow: rgba(154,111,58,0.1);
      --card: rgba(0,0,0,0.02);
      --card-hover: rgba(0,0,0,0.05);
    }
/* ─── RESET ──────────────────────────────────────────── */
   *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
html { scroll-behavior: smooth; font-size: 16px; }
 body {
   font-family: 'DM Sans', sans-serif;
      background: var(--bg);
      color: var(--text);
      line-height: 1.7;
      overflow-x: hidden;
      transition: background var(--transition), color var(--transition);
    }
    a { color: inherit; text-decoration: none; }
    img { max-width: 100%; }
    ::selection { background: var(--accent); color: #000; }
 /* ─── SCROLLBAR ──────────────────────────────────────── */
    ::-webkit-scrollbar { width: 4px; }
    ::-webkit-scrollbar-track { background: var(--bg); }
    ::-webkit-scrollbar-thumb { background: var(--accent); border-radius: 2px; }
/* ─── NOISE TEXTURE ──────────────────────────────────── */
    body::before {
      content: '';
      position: fixed; inset: 0;
      background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noise'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noise)' opacity='0.03'/%3E%3C/svg%3E");
      pointer-events: none; z-index: 9999; opacity: 0.4;
    }
 /* ─── NAV ────────────────────────────────────────────── */
    nav {
      position: fixed; top: 0; left: 0; right: 0; z-index: 100;
      height: var(--nav-h);
      display: flex; align-items: center; justify-content: space-between;
      padding: 0 clamp(20px, 5vw, 80px);
      background: rgba(10,10,15,0.7);
      backdrop-filter: blur(20px) saturate(1.5);
      border-bottom: 1px solid var(--border);
      transition: background var(--transition);
    }
    [data-theme="light"] nav { background: rgba(250,249,246,0.75); }
    .nav-logo {
      font-family: 'Playfair Display', serif;
      font-size: 1.4rem; font-weight: 700;
      letter-spacing: -0.02em; color: var(--text);
    }
    .nav-logo span { color: var(--accent); }
    .nav-links {
      display: flex; align-items: center; gap: 8px;
      list-style: none;
    }
    .nav-links a {
      font-size: 0.82rem; font-weight: 500;
      color: var(--muted); letter-spacing: 0.04em; text-transform: uppercase;
      padding: 6px 14px; border-radius: 999px;
      transition: color var(--transition), background var(--transition);
    }
    .nav-links a:hover { color: var(--text); background: var(--card-hover); }
    .nav-right { display: flex; align-items: center; gap: 12px; }
    .theme-toggle {
      width: 40px; height: 40px; border-radius: 50%;
      border: 1px solid var(--border); background: var(--card);
      cursor: pointer; display: flex; align-items: center; justify-content: center;
      font-size: 1rem; transition: all var(--transition); color: var(--text);
    }
    .theme-toggle:hover { border-color: var(--accent); background: var(--accent-glow); }
    .hamburger { display: none; flex-direction: column; gap: 5px; cursor: pointer; padding: 8px; }
    .hamburger span { display: block; width: 22px; height: 2px; background: var(--text); border-radius: 1px; transition: all var(--transition); }
 /* ─── MOBILE NAV ─────────────────────────────────────── */
    @media (max-width: 768px) {
      .nav-links { display: none; position: absolute; top: var(--nav-h); left: 0; right: 0; background: var(--bg2); border-bottom: 1px solid var(--border); flex-direction: column; padding: 20px; gap: 4px; }
      .nav-links.open { display: flex; }
      .hamburger { display: flex; }
    }
  /* ─── HERO ───────────────────────────────────────────── */
    #hero {
      min-height: 100vh; padding-top: var(--nav-h);
      display: flex; align-items: center; justify-content: center;
      position: relative; overflow: hidden;
      padding-left: clamp(20px, 5vw, 80px);
      padding-right: clamp(20px, 5vw, 80px);
    }
    .hero-orb {
      position: absolute; border-radius: 50%;
      filter: blur(80px); pointer-events: none;
    }
    .hero-orb-1 {
      width: 600px; height: 600px;
      background: radial-gradient(circle, rgba(200,169,110,0.12) 0%, transparent 70%);
      top: -100px; right: -100px;
      animation: float 8s ease-in-out infinite;
    }
    .hero-orb-2 {
      width: 400px; height: 400px;
      background: radial-gradient(circle, rgba(100,100,200,0.08) 0%, transparent 70%);
      bottom: 0; left: -50px;
      animation: float 10s ease-in-out infinite reverse;
    }
    @keyframes float {
      0%,100% { transform: translateY(0) scale(1); }
      50% { transform: translateY(-30px) scale(1.05); }
    }
    .hero-content { max-width: 900px; position: relative; z-index: 1; }
    .hero-badge {
      display: inline-flex; align-items: center; gap: 8px;
      padding: 6px 16px; border-radius: 999px;
      border: 1px solid var(--accent); background: var(--accent-glow);
      font-size: 0.78rem; font-weight: 500; color: var(--accent);
      letter-spacing: 0.06em; text-transform: uppercase;
      margin-bottom: 28px;
      opacity: 0; animation: fadeUp 0.6s ease forwards;
    }
    .hero-badge::before { content: '●'; font-size: 0.5rem; animation: pulse 2s infinite; }
    @keyframes pulse { 0%,100% { opacity: 1; } 50% { opacity: 0.3; } }
    .hero-name {
      font-family: 'Playfair Display', serif;
      font-size: clamp(3rem, 8vw, 6.5rem);
      font-weight: 900; line-height: 0.95;
      letter-spacing: -0.03em;
      opacity: 0; animation: fadeUp 0.6s 0.1s ease forwards;
    }
    .hero-name .line2 { display: block; color: var(--accent); font-style: italic; }
    .hero-title {
      font-family: 'DM Mono', monospace;
      font-size: clamp(0.85rem, 2vw, 1rem);
      color: var(--muted); letter-spacing: 0.12em; text-transform: uppercase;
      margin-top: 20px;
      opacity: 0; animation: fadeUp 0.6s 0.2s ease forwards;
    }
    .hero-tagline {
      font-size: clamp(1rem, 2.5vw, 1.2rem);
      color: var(--muted); max-width: 560px; line-height: 1.8;
      margin-top: 20px;
      opacity: 0; animation: fadeUp 0.6s 0.3s ease forwards;
    }
    .hero-cta {
      display: flex; flex-wrap: wrap; gap: 12px; margin-top: 40px;
      opacity: 0; animation: fadeUp 0.6s 0.4s ease forwards;
    }
    .btn {
      display: inline-flex; align-items: center; gap: 8px;
      padding: 12px 28px; border-radius: 999px; font-size: 0.9rem; font-weight: 600;
      cursor: pointer; transition: all var(--transition); border: none; font-family: 'DM Sans', sans-serif;
    }
    .btn-primary { background: var(--accent); color: #000; }
    .btn-primary:hover { background: var(--accent2); transform: translateY(-2px); box-shadow: 0 12px 30px rgba(200,169,110,0.3); }
    .btn-outline { background: transparent; color: var(--text); border: 1px solid var(--border); }
    .btn-outline:hover { border-color: var(--accent); color: var(--accent); background: var(--accent-glow); transform: translateY(-2px); }
    .hero-scroll {
      position: absolute; bottom: 40px; left: 50%; transform: translateX(-50%);
      display: flex; flex-direction: column; align-items: center; gap: 8px;
      color: var(--muted); font-size: 0.75rem; letter-spacing: 0.1em;
      text-transform: uppercase; animation: fadeUp 1s 0.8s ease forwards; opacity: 0;
    }
    .scroll-line {
      width: 1px; height: 50px;
      background: linear-gradient(to bottom, var(--accent), transparent);
      animation: scrollLine 2s ease-in-out infinite;
    }
    @keyframes scrollLine { 0%,100% { transform: scaleY(1); } 50% { transform: scaleY(0.5); } }
    @keyframes fadeUp { from { opacity: 0; transform: translateY(20px); } to { opacity: 1; transform: translateY(0); } }
 /* ─── SECTIONS ───────────────────────────────────────── */
    section { padding: clamp(60px, 10vw, 120px) clamp(20px, 5vw, 80px); }
    .section-label {
      font-family: 'DM Mono', monospace;
      font-size: 0.75rem; color: var(--accent);
      letter-spacing: 0.15em; text-transform: uppercase;
      margin-bottom: 12px;
    }
    .section-title {
      font-family: 'Playfair Display', serif;
      font-size: clamp(2rem, 5vw, 3.2rem);
      font-weight: 700; line-height: 1.1; letter-spacing: -0.02em;
    }
    .section-header { margin-bottom: 60px; }
    .divider {
      width: 60px; height: 2px;
      background: linear-gradient(to right, var(--accent), transparent);
      margin-top: 16px;
    }
/* ─── ABOUT ──────────────────────────────────────────── */
    #about { background: var(--bg2); }
    .about-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 60px; align-items: start; }
    @media (max-width: 768px) { .about-grid { grid-template-columns: 1fr; } }
    .about-text p { color: var(--muted); margin-bottom: 20px; font-size: 1.05rem; line-height: 1.9; }
    .about-text p strong { color: var(--text); font-weight: 600; }
    .about-stats { display: grid; grid-template-columns: 1fr 1fr; gap: 20px; }
    .stat-card {
      padding: 28px; border-radius: var(--radius);
      background: var(--card); border: 1px solid var(--border);
      transition: all var(--transition);
    }
    .stat-card:hover { border-color: var(--accent); background: var(--accent-glow); transform: translateY(-4px); }
    .stat-num {
      font-family: 'Playfair Display', serif;
      font-size: 2.4rem; font-weight: 900; color: var(--accent);
      line-height: 1;
    }
    .stat-label { font-size: 0.82rem; color: var(--muted); margin-top: 6px; letter-spacing: 0.04em; }
 /* ─── SKILLS ─────────────────────────────────────────── */
    .skills-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: 24px; }
    .skill-category {
      padding: 32px; border-radius: var(--radius);
      background: var(--card); border: 1px solid var(--border);
      transition: all var(--transition);
    }
    .skill-category:hover { border-color: var(--accent); transform: translateY(-4px); box-shadow: 0 20px 40px rgba(0,0,0,0.2); }
    .skill-cat-icon { font-size: 1.8rem; margin-bottom: 16px; }
    .skill-cat-name {
      font-family: 'Playfair Display', serif;
      font-size: 1.1rem; font-weight: 700; margin-bottom: 20px;
    }
    .skill-tags { display: flex; flex-wrap: wrap; gap: 8px; }
    .skill-tag {
      padding: 5px 12px; border-radius: 999px;
      font-size: 0.8rem; font-family: 'DM Mono', monospace;
      background: var(--bg3); border: 1px solid var(--border);
      color: var(--muted); transition: all var(--transition);
    }
    .skill-tag:hover { border-color: var(--accent); color: var(--accent); background: var(--accent-glow); }
/* ─── PROJECTS ───────────────────────────────────────── */
    #projects { background: var(--bg2); }
    .projects-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(340px, 1fr)); gap: 28px; }
    .project-card {
      padding: 36px; border-radius: var(--radius);
      background: var(--card); border: 1px solid var(--border);
      transition: all var(--transition); position: relative; overflow: hidden;
    }
    .project-card::before {
      content: ''; position: absolute; top: 0; left: 0; right: 0; height: 2px;
      background: linear-gradient(to right, var(--accent), transparent);
      transform: scaleX(0); transition: transform var(--transition); transform-origin: left;
    }
    .project-card:hover::before { transform: scaleX(1); }
    .project-card:hover { border-color: rgba(200,169,110,0.3); transform: translateY(-6px); box-shadow: 0 30px 60px rgba(0,0,0,0.3); }
    .project-num {
      font-family: 'DM Mono', monospace; font-size: 0.75rem;
      color: var(--accent); letter-spacing: 0.1em; margin-bottom: 12px;
    }
    .project-title {
      font-family: 'Playfair Display', serif;
      font-size: 1.4rem; font-weight: 700; margin-bottom: 12px; line-height: 1.3;
    }
    .project-desc { color: var(--muted); font-size: 0.92rem; line-height: 1.8; margin-bottom: 20px; }
    .project-tech { display: flex; flex-wrap: wrap; gap: 8px; margin-bottom: 24px; }
    .tech-chip {
      padding: 3px 10px; border-radius: 4px;
      font-size: 0.75rem; font-family: 'DM Mono', monospace;
      background: var(--accent-glow); color: var(--accent); border: 1px solid rgba(200,169,110,0.2);
    }
    .project-links { display: flex; gap: 12px; }
    .project-link {
      display: inline-flex; align-items: center; gap: 6px;
      font-size: 0.82rem; font-weight: 500; color: var(--muted);
      transition: color var(--transition); padding: 6px 0;
    }
    .project-link:hover { color: var(--accent); }
 /* ─── EDUCATION ──────────────────────────────────────── */
    .edu-card {
      display: grid; grid-template-columns: auto 1fr; gap: 32px; align-items: start;
      padding: 40px; border-radius: var(--radius);
      background: var(--card); border: 1px solid var(--border);
      transition: all var(--transition); max-width: 800px;
    }
    .edu-card:hover { border-color: var(--accent); transform: translateY(-4px); }
    .edu-icon {
      width: 56px; height: 56px; border-radius: 16px;
      background: var(--accent-glow); border: 1px solid rgba(200,169,110,0.3);
      display: flex; align-items: center; justify-content: center; font-size: 1.6rem;
    }
    .edu-degree {
      font-family: 'Playfair Display', serif;
      font-size: 1.3rem; font-weight: 700; margin-bottom: 6px;
    }
    .edu-school { color: var(--accent); font-weight: 500; margin-bottom: 4px; }
    .edu-meta { color: var(--muted); font-size: 0.85rem; font-family: 'DM Mono', monospace; }
 /* ─── CERTIFICATIONS ─────────────────────────────────── */
    #certifications { background: var(--bg2); }
    .cert-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(260px, 1fr)); gap: 20px; }
    .cert-card {
      padding: 28px; border-radius: var(--radius);
      background: var(--card); border: 1px solid var(--border);
      transition: all var(--transition); display: flex; align-items: flex-start; gap: 16px;
    }
    .cert-card:hover { border-color: var(--accent); background: var(--accent-glow); transform: translateY(-4px); }
    .cert-icon {
      width: 42px; height: 42px; border-radius: 10px; flex-shrink: 0;
      background: var(--accent-glow); border: 1px solid rgba(200,169,110,0.3);
      display: flex; align-items: center; justify-content: center; font-size: 1.2rem;
    }
    .cert-name { font-weight: 600; margin-bottom: 4px; }
    .cert-issuer { color: var(--muted); font-size: 0.82rem; }
/* ─── STRENGTHS ──────────────────────────────────────── */
    .strengths-row { display: flex; flex-wrap: wrap; gap: 16px; }
    .strength-pill {
      padding: 12px 24px; border-radius: 999px;
      border: 1px solid var(--border); background: var(--card);
      font-size: 0.9rem; font-weight: 500; color: var(--muted);
      transition: all var(--transition); display: flex; align-items: center; gap: 10px;
    }
    .strength-pill span { font-size: 1rem; }
    .strength-pill:hover { border-color: var(--accent); color: var(--text); background: var(--accent-glow); transform: translateY(-3px); }
  /* ─── CONTACT ────────────────────────────────────────── */
    #contact {
      text-align: center;
      background: linear-gradient(to bottom, var(--bg), var(--bg2));
    }
    .contact-wrapper { max-width: 680px; margin: 0 auto; }
    .contact-email {
      font-family: 'Playfair Display', serif;
      font-size: clamp(1.4rem, 4vw, 2.2rem); font-style: italic;
      color: var(--accent); margin: 32px 0;
    }
    .contact-links { display: flex; flex-wrap: wrap; justify-content: center; gap: 16px; margin-top: 40px; }
    .contact-link {
      display: flex; align-items: center; gap: 10px;
      padding: 14px 28px; border-radius: 999px;
      border: 1px solid var(--border); background: var(--card);
      font-weight: 500; color: var(--muted); transition: all var(--transition);
    }
    .contact-link:hover { border-color: var(--accent); color: var(--accent); background: var(--accent-glow); transform: translateY(-3px); }
/* ─── FOOTER ─────────────────────────────────────────── */
    footer {
      text-align: center; padding: 32px 20px;
      border-top: 1px solid var(--border);
      color: var(--muted); font-size: 0.82rem;
    }
    footer span { color: var(--accent); }
/* ─── SCROLL TO TOP ──────────────────────────────────── */
    #scrollTop {
      position: fixed; bottom: 32px; right: 32px; z-index: 50;
      width: 48px; height: 48px; border-radius: 50%;
      background: var(--accent); color: #000; border: none; cursor: pointer;
      display: flex; align-items: center; justify-content: center; font-size: 1.1rem;
      opacity: 0; transform: translateY(20px);
      transition: all var(--transition); box-shadow: 0 8px 20px rgba(200,169,110,0.4);
    }
    #scrollTop.visible { opacity: 1; transform: translateY(0); }
    #scrollTop:hover { transform: translateY(-4px); box-shadow: 0 12px 28px rgba(200,169,110,0.5); }
/* ─── REVEAL ANIMATIONS ──────────────────────────────── */
    .reveal { opacity: 0; transform: translateY(30px); transition: opacity 0.7s ease, transform 0.7s ease; }
    .reveal.visible { opacity: 1; transform: translateY(0); }
/* ─── EXPERIENCE TIMELINE ────────────────────────────── */
    .timeline { position: relative; padding-left: 32px; }
    .timeline::before {
      content: ''; position: absolute; left: 0; top: 8px; bottom: 8px;
      width: 1px; background: linear-gradient(to bottom, var(--accent), transparent);
    }
    .timeline-item { position: relative; margin-bottom: 48px; }
    .timeline-dot {
      position: absolute; left: -38px; top: 6px;
      width: 12px; height: 12px; border-radius: 50%;
      background: var(--accent); border: 2px solid var(--bg);
      box-shadow: 0 0 12px var(--accent);
    }
    .timeline-title { font-family: 'Playfair Display', serif; font-size: 1.2rem; font-weight: 700; margin-bottom: 4px; }
    .timeline-company { color: var(--accent); font-weight: 500; margin-bottom: 4px; }
    .timeline-date { color: var(--muted); font-size: 0.82rem; font-family: 'DM Mono', monospace; margin-bottom: 12px; }
    .timeline-desc { color: var(--muted); font-size: 0.92rem; line-height: 1.8; }
 </style>
</head>
<body>
  <!-- NAV -->
<nav id="navbar">
  <a href="#hero" class="nav-logo">M.<span>D</span></a>
  <ul class="nav-links" id="navLinks">
    <li><a href="#about">About</a></li>
    <li><a href="#skills">Skills</a></li>
    <li><a href="#projects">Projects</a></li>
    <li><a href="#education">Education</a></li>
    <li><a href="#certifications">Certifications</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
  <div class="nav-right">
    <button class="theme-toggle" id="themeToggle" aria-label="Toggle theme">🌙</button>
    <button class="hamburger" id="hamburger" aria-label="Menu">
      <span></span><span></span><span></span>
    </button>
  </div>
</nav>
<!-- HERO -->
<section id="hero">
  <div class="hero-orb hero-orb-1"></div>
  <div class="hero-orb hero-orb-2"></div>
  <div class="hero-content">
    <div class="hero-badge">Available for Opportunities</div>
    <h1 class="hero-name">
      M. Delfina
      <span class="line2">Masarallo</span>
    </h1>
    <p class="hero-title">Frontend Developer &amp; React Specialist</p>
    <p class="hero-tagline">
      Crafting responsive, scalable web experiences with clean code and thoughtful design.
      Based in Kancheepuram, Tamil Nadu.
    </p>
    <div class="hero-cta">
      <a href="#projects" class="btn btn-primary">View Projects ↓</a>
      <a href="#contact" class="btn btn-outline">Contact Me</a>
      <a href="https://github.com/delfinam1306-cmd" target="_blank" class="btn btn-outline">GitHub ↗</a>
    </div>
  </div>
  <div class="hero-scroll">
    <div class="scroll-line"></div>
    Scroll
  </div>
</section>
<!-- ABOUT -->
<section id="about">
  <div class="section-header reveal">
    <p class="section-label">01 / About</p>
    <h2 class="section-title">Driven by curiosity,<br>built on code.</h2>
    <div class="divider"></div>
  </div>
  <div class="about-grid">
    <div class="about-text reveal">
   <p>I'm an <strong>aspiring web developer</strong> with a solid foundation in HTML5, CSS3, JavaScript, and React.js — with a genuine passion for building products that are both functional and beautiful.</p>
      <p>My expertise spans <strong>REST API integration</strong>, DOM manipulation, component-based architecture, and responsive design. I believe great software is built at the intersection of technical excellence and user empathy.</p>
      <p>Currently pursuing my B.E. in Computer Science, I'm actively seeking opportunities to contribute to innovative teams where I can grow, ship meaningful work, and continue learning every day.</p>
    </div>
    <div class="about-stats reveal">
      <div class="stat-card">
        <div class="stat-num">3+</div>
        <div class="stat-label">Live Projects Deployed</div>
      </div>
      <div class="stat-card">
        <div class="stat-num">3</div>
        <div class="stat-label">Certifications Earned</div>
      </div>
      <div class="stat-card">
        <div class="stat-num">10+</div>
        <div class="stat-label">Technologies Mastered</div>
      </div>
      <div class="stat-card">
        <div class="stat-num">2028</div>
        <div class="stat-label">Expected Graduation</div>
      </div>
    </div>
  </div>
</section>
<!-- SKILLS -->
<section id="skills">
  <div class="section-header reveal">
    <p class="section-label">02 / Skills</p>
    <h2 class="section-title">Technologies &amp;<br>Capabilities</h2>
    <div class="divider"></div>
  </div>
  <div class="skills-grid">
    <div class="skill-category reveal">
      <div class="skill-cat-icon">⌨️</div>
      <div class="skill-cat-name">Languages</div>
      <div class="skill-tags">
        <span class="skill-tag">HTML5</span>
        <span class="skill-tag">CSS3</span>
        <span class="skill-tag">JavaScript</span>
      </div>
    </div>
    <div class="skill-category reveal">
      <div class="skill-cat-icon">⚛️</div>
      <div class="skill-cat-name">Frameworks &amp; Libraries</div>
      <div class="skill-tags">
        <span class="skill-tag">React.js</span>
        <span class="skill-tag">REST API</span>
        <span class="skill-tag">DOM Manipulation</span>
        <span class="skill-tag">Component Architecture</span>
      </div>
    </div>
    <div class="skill-category reveal">
      <div class="skill-cat-icon">🛠️</div>
      <div class="skill-cat-name">Tools &amp; Platforms</div>
      <div class="skill-tags">
        <span class="skill-tag">Git</span>
        <span class="skill-tag">GitHub</span>
        <span class="skill-tag">VS Code</span>
        <span class="skill-tag">Netlify</span>
        <span class="skill-tag">Vercel</span>
      </div>
    </div>
    <div class="skill-category reveal">
      <div class="skill-cat-icon">🧠</div>
      <div class="skill-cat-name">Concepts</div>
      <div class="skill-tags">
        <span class="skill-tag">Responsive Design</span>
        <span class="skill-tag">Performance Optimization</span>
        <span class="skill-tag">Semantic HTML</span>
        <span class="skill-tag">Basic Data Structures</span>
      </div>
    </div>
  </div>
</section>
  !-- PROJECTS -->
<section id="projects">
  <div class="section-header reveal">
    <p class="section-label">03 / Projects</p>
    <h2 class="section-title">Things I've<br>Built &amp; Shipped</h2>
    <div class="divider"></div>
  </div>
  <div class="projects-grid">

  <div class="project-card reveal">
      <div class="project-num">PROJECT — 01</div>
      <h3 class="project-title">E-Commerce Web Application</h3>
      <p class="project-desc">A fully responsive React.js storefront featuring product listing, category filtering, and a dynamic shopping cart. Integrated live product data via REST APIs with performance-tuned rendering for a seamless user experience.</p>
      <div class="project-tech">
        <span class="tech-chip">React.js</span>
        <span class="tech-chip">REST API</span>
        <span class="tech-chip">CSS3</span>
        <span class="tech-chip">Netlify</span>
      </div>
      <div class="project-links">
        <a href="#" target="_blank" class="project-link">↗ Coming Soon</a>
      </div>
    </div>

  <div class="project-card reveal">
      <div class="project-num">PROJECT — 02</div>
      <h3 class="project-title">Personal Portfolio Website</h3>
      <p class="project-desc">A modern, fully responsive portfolio built with semantic HTML and CSS — showcasing projects, skills, and a contact form. Optimized for performance with accessibility-first markup and smooth interactions.</p>
      <div class="project-tech">
        <span class="tech-chip">HTML5</span>
        <span class="tech-chip">CSS3</span>
        <span class="tech-chip">JavaScript</span>
        <span class="tech-chip">Netlify</span>
      </div>
      <div class="project-links">
        <a href="#" target="_blank" class="project-link">↗ Coming Soon</a>
      </div>
    </div>

  <div class="project-card reveal">
      <div class="project-num">PROJECT — 03</div>
      <h3 class="project-title">To-Do List Web Application</h3>
      <p class="project-desc">A feature-rich task manager built in vanilla JavaScript with add, delete, and mark-complete functionality. Uses localStorage for persistent data across sessions — zero dependencies, pure performance.</p>
      <div class="project-tech">
        <span class="tech-chip">JavaScript</span>
        <span class="tech-chip">localStorage</span>
        <span class="tech-chip">HTML5</span>
        <span class="tech-chip">Vercel</span>
      </div>
      <div class="project-links">
        <a href="#" target="_blank" class="project-link">↗ Coming Soon</a>
      </div>
    </div>

  </div>
</section>

<!-- EDUCATION -->
<section id="education">
  <div class="section-header reveal">
    <p class="section-label">04 / Education</p>
    <h2 class="section-title">Academic<br>Foundation</h2>
    <div class="divider"></div>
  </div>
  <div class="edu-card reveal">
    <div class="edu-icon">🎓</div>
    <div>
      <div class="edu-degree">Bachelor of Engineering — Computer Science &amp; Engineering</div>
      <div class="edu-school">Karpaga Vinayaga College of Engineering and Technology</div>
      <div class="edu-meta">Anna University &nbsp;·&nbsp; 2024 – 2028</div>
    </div>
  </div>
</section>

<!-- CERTIFICATIONS -->
<section id="certifications">
  <div class="section-header reveal">
    <p class="section-label">05 / Certifications</p>
    <h2 class="section-title">Credentials &amp;<br>Achievements</h2>
    <div class="divider"></div>
  </div>
  <div class="cert-grid">
    <div class="cert-card reveal">
      <div class="cert-icon">🏅</div>
      <div>
        <div class="cert-name">Web Development Basics</div>
        <div class="cert-issuer">Novi Tech Private Limited</div>
      </div>
    </div>
    <div class="cert-card reveal">
      <div class="cert-icon">🏅</div>
      <div>
        <div class="cert-name">Web Developer Certification</div>
        <div class="cert-issuer">Simplilearn</div>
      </div>
    </div>
    <div class="cert-card reveal">
      <div class="cert-icon">🏅</div>
      <div>
        <div class="cert-name">Full Stack Web Development</div>
        <div class="cert-issuer">LearnVern</div>
      </div>
    </div>
  </div>

  <!-- Additional Strengths -->
  <div style="margin-top: 60px;">
    <p class="section-label" style="margin-bottom: 24px;">Additional Strengths</p>
    <div class="strengths-row">
      <div class="strength-pill"><span>🧩</span> Strong Problem-Solving</div>
      <div class="strength-pill"><span>⚡</span> Quick Learner</div>
      <div class="strength-pill"><span>🔄</span> Adaptable</div>
      <div class="strength-pill"><span>💬</span> Effective Communication</div>
      <div class="strength-pill"><span>🤝</span> Team Player</div>
      <div class="strength-pill"><span>🎯</span> Self-Motivated</div>
    </div>
  </div>
</section>

<!-- CONTACT -->
<section id="contact">
  <div class="contact-wrapper">
    <div class="reveal">
      <p class="section-label" style="justify-content:center;display:flex">06 / Contact</p>
      <h2 class="section-title" style="text-align:center">Let's Build<br>Something Great</h2>
      <div class="divider" style="margin: 16px auto 0;"></div>
    </div>
    <p class="contact-email reveal">delfinam1306@gmail.com</p>
    <p style="color:var(--muted); margin-bottom: 8px;" class="reveal">+91 8940737966 &nbsp;·&nbsp; Kancheepuram, Tamil Nadu, India</p>
    <div class="contact-links reveal">
      <a href="mailto:delfinam1306@gmail.com" class="contact-link">✉️ Email Me</a>
      <a href="tel:+918940737966" class="contact-link">📞 Call</a>
      <a href="https://github.com/delfinam1306-cmd" target="_blank" class="contact-link">🐙 GitHub</a>
      <a href="https://your-portfolio-link.netlify.app" target="_blank" class="contact-link">🌐 Portfolio</a>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <p>Designed &amp; built with <span>♥</span> by M. Delfina Masarallo &nbsp;·&nbsp; <span>2025</span></p>
</footer>

<!-- SCROLL TOP -->
<button id="scrollTop" aria-label="Scroll to top">↑</button>

<script>
  // Theme toggle
  const toggle = document.getElementById('themeToggle');
  const html = document.documentElement;
  toggle.addEventListener('click', () => {
    const isDark = html.getAttribute('data-theme') === 'dark';
    html.setAttribute('data-theme', isDark ? 'light' : 'dark');
    toggle.textContent = isDark ? '🌙' : '☀️';
  });

  // Hamburger menu
  const hamburger = document.getElementById('hamburger');
  const navLinks = document.getElementById('navLinks');
  hamburger.addEventListener('click', () => navLinks.classList.toggle('open'));
  navLinks.querySelectorAll('a').forEach(a => a.addEventListener('click', () => navLinks.classList.remove('open')));

  // Scroll to top
  const scrollBtn = document.getElementById('scrollTop');
  window.addEventListener('scroll', () => {
    scrollBtn.classList.toggle('visible', window.scrollY > 400);
  });
  scrollBtn.addEventListener('click', () => window.scrollTo({ top: 0, behavior: 'smooth' }));

  // Reveal on scroll
  const reveals = document.querySelectorAll('.reveal');
  const observer = new IntersectionObserver((entries) => {
    entries.forEach((entry, i) => {
      if (entry.isIntersecting) {
        setTimeout(() => entry.target.classList.add('visible'), i * 80);
        observer.unobserve(entry.target);
      }
    });
  }, { threshold: 0.1, rootMargin: '0px 0px -40px 0px' });
  reveals.forEach(el => observer.observe(el));

  // Active nav highlighting
  const sections = document.querySelectorAll('section[id]');
  const navAnchors = document.querySelectorAll('.nav-links a');
  window.addEventListener('scroll', () => {
    let current = '';
    sections.forEach(s => {
      if (window.scrollY >= s.offsetTop - 100) current = s.getAttribute('id');
    });
    navAnchors.forEach(a => {
      a.style.color = a.getAttribute('href') === '#' + current ? 'var(--accent)' : '';
    });
  });
</script>
</body>
</html>

  
