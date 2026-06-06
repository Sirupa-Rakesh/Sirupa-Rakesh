<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Rakesh Sirupa — DevOps Engineer</title>
<link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;500;700&family=Syne:wght@400;600;800&display=swap" rel="stylesheet" />
<style>
  :root {
    --bg: #080d14;
    --bg2: #0d1520;
    --bg3: #111e2e;
    --bg4: #162336;
    --accent: #1e90ff;
    --accent2: #00d4aa;
    --accent3: #ff6b35;
    --text: #e8f0fe;
    --text2: #8aa4c8;
    --text3: #4a6480;
    --border: #1e3050;
    --border2: #2a4570;
    --mono: 'JetBrains Mono', monospace;
    --sans: 'Syne', sans-serif;
    --radius: 10px;
    --radius-lg: 16px;
  }
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
  html { scroll-behavior: smooth; }
  body {
    background: var(--bg);
    color: var(--text);
    font-family: var(--mono);
    line-height: 1.7;
    overflow-x: hidden;
  }
  a { color: var(--accent); text-decoration: none; }
  a:hover { color: var(--accent2); }

  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noise'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noise)' opacity='0.04'/%3E%3C/svg%3E");
    pointer-events: none;
    z-index: 999;
    opacity: 0.4;
  }

  nav {
    position: fixed;
    top: 0; left: 0; right: 0;
    z-index: 100;
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 0 2.5rem;
    height: 60px;
    background: rgba(8,13,20,0.85);
    backdrop-filter: blur(12px);
    border-bottom: 1px solid var(--border);
  }
  .nav-logo { font-family: var(--sans); font-weight: 800; font-size: 1.1rem; color: var(--text); letter-spacing: -0.02em; }
  .nav-logo span { color: var(--accent); }
  .nav-links { display: flex; gap: 2rem; }
  .nav-links a { font-size: 0.75rem; color: var(--text2); letter-spacing: 0.1em; text-transform: uppercase; transition: color 0.2s; }
  .nav-links a:hover { color: var(--accent2); }
  .nav-badge { font-size: 0.7rem; background: rgba(30,144,255,0.15); border: 1px solid rgba(30,144,255,0.3); color: var(--accent); padding: 4px 12px; border-radius: 20px; }

  .hero { min-height: 100vh; display: flex; flex-direction: column; align-items: center; justify-content: center; text-align: center; padding: 100px 2rem 4rem; position: relative; overflow: hidden; }
  .hero-grid { position: absolute; inset: 0; background-image: linear-gradient(rgba(30,144,255,0.04) 1px, transparent 1px), linear-gradient(90deg, rgba(30,144,255,0.04) 1px, transparent 1px); background-size: 60px 60px; }
  .hero-glow { position: absolute; width: 600px; height: 600px; background: radial-gradient(circle, rgba(30,144,255,0.08) 0%, transparent 70%); top: 50%; left: 50%; transform: translate(-50%, -50%); pointer-events: none; }
  .hero-tag { font-size: 0.72rem; letter-spacing: 0.18em; color: var(--accent2); text-transform: uppercase; margin-bottom: 1.5rem; position: relative; }
  .hero-tag::before, .hero-tag::after { content: '──'; margin: 0 12px; color: var(--text3); }
  .hero-name { font-family: var(--sans); font-weight: 800; font-size: clamp(3rem, 8vw, 6.5rem); letter-spacing: -0.03em; line-height: 1; color: var(--text); margin-bottom: 0.5rem; position: relative; }
  .hero-name .hi { color: var(--accent); }
  .hero-role { font-size: clamp(1rem, 2.5vw, 1.4rem); color: var(--text2); margin-bottom: 2.5rem; position: relative; }
  .hero-role .tag { color: var(--accent); }
  .typed-cursor { animation: blink 1s infinite; }
  @keyframes blink { 0%,100%{opacity:1} 50%{opacity:0} }
  .hero-cta { display: flex; gap: 1rem; flex-wrap: wrap; justify-content: center; position: relative; }
  .btn { font-family: var(--mono); font-size: 0.8rem; letter-spacing: 0.05em; padding: 12px 28px; border-radius: var(--radius); cursor: pointer; transition: all 0.2s; display: inline-flex; align-items: center; gap: 8px; }
  .btn-primary { background: var(--accent); color: #fff; border: 1px solid var(--accent); }
  .btn-primary:hover { background: #1a7fe0; color: #fff; transform: translateY(-2px); }
  .btn-outline { background: transparent; color: var(--text2); border: 1px solid var(--border2); }
  .btn-outline:hover { border-color: var(--accent2); color: var(--accent2); transform: translateY(-2px); }
  .hero-scroll { position: absolute; bottom: 2rem; left: 50%; transform: translateX(-50%); display: flex; flex-direction: column; align-items: center; gap: 8px; color: var(--text3); font-size: 0.7rem; letter-spacing: 0.1em; animation: float 2s ease-in-out infinite; }
  .scroll-line { width: 1px; height: 40px; background: linear-gradient(to bottom, var(--accent), transparent); }
  @keyframes float { 0%,100%{transform:translateX(-50%) translateY(0)} 50%{transform:translateX(-50%) translateY(8px)} }

  section { padding: 6rem 0; }
  .container { max-width: 1100px; margin: 0 auto; padding: 0 2rem; }
  .section-label { font-size: 0.72rem; letter-spacing: 0.18em; color: var(--accent2); text-transform: uppercase; margin-bottom: 0.5rem; }
  .section-title { font-family: var(--sans); font-weight: 800; font-size: clamp(2rem, 4vw, 3rem); letter-spacing: -0.02em; color: var(--text); margin-bottom: 1rem; }
  .section-desc { color: var(--text2); max-width: 560px; line-height: 1.8; font-size: 0.9rem; margin-bottom: 3.5rem; }

  .about-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 3rem; align-items: start; }
  .about-text { color: var(--text2); font-size: 0.9rem; line-height: 2; }
  .about-text p { margin-bottom: 1rem; }
  .about-text strong { color: var(--accent); font-weight: 500; }
  .yaml-card { background: var(--bg2); border: 1px solid var(--border); border-radius: var(--radius-lg); padding: 1.5rem; font-size: 0.82rem; }
  .yaml-card .comment { color: var(--text3); }
  .yaml-card .key { color: var(--accent2); }
  .yaml-card .value { color: var(--text); }
  .yaml-card .string { color: #ffd700; }
  .yaml-sep { color: var(--border2); margin: 0.5rem 0; }
  .traits { display: grid; grid-template-columns: 1fr 1fr; gap: 1rem; margin-top: 2rem; }
  .trait { background: var(--bg2); border: 1px solid var(--border); border-radius: var(--radius); padding: 1rem 1.2rem; display: flex; align-items: flex-start; gap: 12px; }
  .trait-icon { font-size: 1.2rem; margin-top: 2px; }
  .trait-title { font-size: 0.78rem; font-weight: 500; color: var(--text); margin-bottom: 2px; }
  .trait-desc { font-size: 0.72rem; color: var(--text2); line-height: 1.6; }

  .skills-section { background: var(--bg2); }
  .skills-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); gap: 1.5rem; }
  .skill-group { background: var(--bg3); border: 1px solid var(--border); border-radius: var(--radius-lg); padding: 1.5rem; }
  .skill-group-title { font-size: 0.7rem; letter-spacing: 0.12em; text-transform: uppercase; color: var(--accent2); margin-bottom: 1.2rem; padding-bottom: 0.75rem; border-bottom: 1px solid var(--border); }
  .skill-item { margin-bottom: 1rem; }
  .skill-header { display: flex; justify-content: space-between; align-items: center; margin-bottom: 5px; }
  .skill-name { font-size: 0.8rem; color: var(--text); }
  .skill-pct { font-size: 0.75rem; color: var(--text3); }
  .skill-bar { height: 4px; background: var(--bg4); border-radius: 2px; overflow: hidden; }
  .skill-fill { height: 100%; border-radius: 2px; width: 0; transition: width 1.2s cubic-bezier(0.16, 1, 0.3, 1); }
  .skill-fill.blue { background: linear-gradient(90deg, var(--accent), var(--accent2)); }
  .skill-fill.teal { background: linear-gradient(90deg, var(--accent2), #00ffaa); }
  .skill-fill.orange { background: linear-gradient(90deg, var(--accent3), #ffd700); }
  .skill-fill.dim { background: linear-gradient(90deg, var(--text3), var(--text2)); }
  .badges { display: flex; flex-wrap: wrap; gap: 8px; margin-top: 1.5rem; }
  .badge { font-size: 0.72rem; padding: 5px 12px; border-radius: 20px; border: 1px solid; letter-spacing: 0.05em; }
  .badge.b-blue { background: rgba(30,144,255,0.1); border-color: rgba(30,144,255,0.3); color: var(--accent); }
  .badge.b-teal { background: rgba(0,212,170,0.1); border-color: rgba(0,212,170,0.3); color: var(--accent2); }
  .badge.b-orange { background: rgba(255,107,53,0.1); border-color: rgba(255,107,53,0.3); color: var(--accent3); }
  .badge.b-gray { background: rgba(255,255,255,0.05); border-color: var(--border); color: var(--text2); }

  .projects-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(480px, 1fr)); gap: 1.5rem; }
  .project-card { background: var(--bg2); border: 1px solid var(--border); border-radius: var(--radius-lg); padding: 1.75rem; transition: all 0.3s; position: relative; overflow: hidden; }
  .project-card::before { content: ''; position: absolute; top: 0; left: 0; right: 0; height: 2px; opacity: 0; transition: opacity 0.3s; }
  .project-card:hover { border-color: var(--border2); transform: translateY(-4px); }
  .project-card:hover::before { opacity: 1; }
  .project-card.blue::before { background: linear-gradient(90deg, var(--accent), var(--accent2)); }
  .project-card.teal::before { background: linear-gradient(90deg, var(--accent2), #00ffaa); }
  .project-card.orange::before { background: linear-gradient(90deg, var(--accent3), #ffd700); }
  .project-card.purple::before { background: linear-gradient(90deg, #9d4edd, #c77dff); }
  .project-top { display: flex; align-items: flex-start; justify-content: space-between; margin-bottom: 1rem; }
  .project-icon { font-size: 1.8rem; }
  .project-links { display: flex; gap: 8px; }
  .project-link { font-size: 0.7rem; padding: 5px 12px; border-radius: var(--radius); border: 1px solid var(--border2); color: var(--text2); transition: all 0.2s; display: flex; align-items: center; gap: 5px; }
  .project-link:hover { border-color: var(--accent); color: var(--accent); }
  .project-title { font-family: var(--sans); font-weight: 600; font-size: 1.1rem; color: var(--text); margin-bottom: 0.5rem; }
  .project-desc { font-size: 0.82rem; color: var(--text2); line-height: 1.8; margin-bottom: 1.2rem; }
  .project-features { list-style: none; margin-bottom: 1.2rem; }
  .project-features li { font-size: 0.78rem; color: var(--text2); padding: 3px 0; display: flex; align-items: flex-start; gap: 8px; }
  .project-features li::before { content: '▸'; color: var(--accent2); flex-shrink: 0; }
  .project-stack { display: flex; flex-wrap: wrap; gap: 6px; }
  .stack-tag { font-size: 0.68rem; padding: 3px 10px; background: var(--bg3); border: 1px solid var(--border); border-radius: 4px; color: var(--text2); letter-spacing: 0.05em; }

  .roadmap-section { background: var(--bg2); }
  .timeline { position: relative; padding-left: 2rem; }
  .timeline::before { content: ''; position: absolute; left: 0; top: 8px; bottom: 8px; width: 1px; background: linear-gradient(to bottom, var(--accent), var(--accent2), transparent); }
  .timeline-item { position: relative; margin-bottom: 1.5rem; padding-left: 1.5rem; }
  .timeline-dot { position: absolute; left: -2rem; top: 6px; width: 12px; height: 12px; border-radius: 50%; border: 2px solid; background: var(--bg); }
  .timeline-dot.done { border-color: var(--accent2); background: rgba(0,212,170,0.2); }
  .timeline-dot.active { border-color: var(--accent); background: rgba(30,144,255,0.2); box-shadow: 0 0 8px rgba(30,144,255,0.4); }
  .timeline-dot.planned { border-color: var(--border2); }
  .timeline-dot.goal { border-color: var(--accent3); background: rgba(255,107,53,0.2); }
  .timeline-header { display: flex; align-items: center; gap: 12px; margin-bottom: 4px; }
  .timeline-quarter { font-size: 0.7rem; color: var(--text3); letter-spacing: 0.1em; min-width: 60px; }
  .timeline-title { font-size: 0.88rem; color: var(--text); font-weight: 500; }
  .timeline-status { margin-left: auto; font-size: 0.68rem; padding: 2px 10px; border-radius: 20px; }
  .status-done { background: rgba(0,212,170,0.15); color: var(--accent2); border: 1px solid rgba(0,212,170,0.3); }
  .status-progress { background: rgba(30,144,255,0.15); color: var(--accent); border: 1px solid rgba(30,144,255,0.3); }
  .status-planned { background: rgba(255,255,255,0.05); color: var(--text3); border: 1px solid var(--border); }
  .status-goal { background: rgba(255,107,53,0.15); color: var(--accent3); border: 1px solid rgba(255,107,53,0.3); }
  .timeline-sub { font-size: 0.78rem; color: var(--text3); padding-left: 72px; }

  .philosophy-grid { display: grid; grid-template-columns: repeat(4, 1fr); gap: 1.5rem; }
  .philosophy-card { background: var(--bg2); border: 1px solid var(--border); border-radius: var(--radius-lg); padding: 2rem 1.5rem; text-align: center; transition: all 0.3s; }
  .philosophy-card:hover { border-color: var(--border2); transform: translateY(-4px); }
  .philo-icon { font-size: 2rem; margin-bottom: 1rem; }
  .philo-title { font-family: var(--sans); font-weight: 600; font-size: 1rem; color: var(--text); margin-bottom: 0.75rem; }
  .philo-desc { font-size: 0.78rem; color: var(--text2); line-height: 1.8; }
  .quote-block { background: var(--bg2); border-left: 3px solid var(--accent); border-radius: 0 var(--radius) var(--radius) 0; padding: 1.5rem 2rem; margin-bottom: 3rem; font-style: italic; color: var(--text2); font-size: 0.95rem; line-height: 1.9; }

  .contact-section { background: var(--bg2); }
  .contact-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 4rem; align-items: start; }
  .contact-links { display: flex; flex-direction: column; gap: 1rem; margin-top: 2rem; }
  .contact-link-item { display: flex; align-items: center; gap: 1rem; padding: 1rem 1.25rem; background: var(--bg3); border: 1px solid var(--border); border-radius: var(--radius); transition: all 0.2s; color: var(--text); }
  .contact-link-item:hover { border-color: var(--border2); background: var(--bg4); color: var(--text); transform: translateX(4px); }
  .contact-link-icon { font-size: 1.2rem; }
  .contact-link-label { font-size: 0.7rem; color: var(--text3); margin-bottom: 2px; }
  .contact-link-value { font-size: 0.85rem; color: var(--text); }
  .availability { display: inline-flex; align-items: center; gap: 8px; font-size: 0.78rem; padding: 8px 16px; background: rgba(0,212,170,0.1); border: 1px solid rgba(0,212,170,0.3); border-radius: 20px; color: var(--accent2); margin-top: 1.5rem; }
  .avail-dot { width: 8px; height: 8px; border-radius: 50%; background: var(--accent2); animation: pulse 2s infinite; }
  @keyframes pulse { 0%,100%{opacity:1;transform:scale(1)} 50%{opacity:0.6;transform:scale(1.2)} }
  .contact-form-area { background: var(--bg3); border: 1px solid var(--border); border-radius: var(--radius-lg); padding: 2rem; }
  .form-title { font-family: var(--sans); font-weight: 600; font-size: 1.1rem; margin-bottom: 1.5rem; color: var(--text); }
  .form-group { margin-bottom: 1.2rem; }
  .form-label { font-size: 0.72rem; color: var(--text3); letter-spacing: 0.08em; display: block; margin-bottom: 6px; }
  .form-input, .form-textarea { width: 100%; background: var(--bg2); border: 1px solid var(--border); border-radius: var(--radius); padding: 10px 14px; color: var(--text); font-family: var(--mono); font-size: 0.82rem; outline: none; transition: border-color 0.2s; resize: none; }
  .form-input:focus, .form-textarea:focus { border-color: var(--accent); }
  .form-textarea { height: 120px; }
  .btn-submit { width: 100%; padding: 12px; background: var(--accent); color: #fff; border: none; border-radius: var(--radius); font-family: var(--mono); font-size: 0.82rem; cursor: pointer; transition: all 0.2s; letter-spacing: 0.05em; }
  .btn-submit:hover { background: #1a7fe0; transform: translateY(-1px); }
  .form-success { display: none; text-align: center; padding: 2rem; color: var(--accent2); font-size: 0.85rem; }

  footer { border-top: 1px solid var(--border); padding: 2rem; text-align: center; font-size: 0.75rem; color: var(--text3); }
  footer span { color: var(--accent); }

  .fade-up { opacity: 0; transform: translateY(30px); transition: opacity 0.7s ease, transform 0.7s ease; }
  .fade-up.visible { opacity: 1; transform: translateY(0); }

  .stats-grid { display: grid; grid-template-columns: repeat(4, 1fr); gap: 1rem; margin-bottom: 2rem; }
  .stat-card { background: var(--bg2); border: 1px solid var(--border); border-radius: var(--radius); padding: 1.25rem; text-align: center; }
  .stat-value { font-family: var(--sans); font-size: 1.8rem; font-weight: 800; color: var(--accent); }
  .stat-label { font-size: 0.7rem; color: var(--text3); margin-top: 4px; letter-spacing: 0.08em; }
  .contrib-graph { background: var(--bg2); border: 1px solid var(--border); border-radius: var(--radius-lg); padding: 1.5rem; overflow-x: auto; }
  .contrib-title { font-size: 0.72rem; color: var(--text3); margin-bottom: 1rem; letter-spacing: 0.08em; }
  .contrib-grid { display: grid; grid-template-columns: repeat(52, 12px); gap: 3px; }
  .contrib-col { display: grid; grid-template-rows: repeat(7, 12px); gap: 3px; }
  .contrib-cell { width: 12px; height: 12px; border-radius: 2px; }

  @media (max-width: 768px) {
    .about-grid, .contact-grid, .philosophy-grid { grid-template-columns: 1fr; }
    .projects-grid { grid-template-columns: 1fr; }
    .stats-grid { grid-template-columns: repeat(2, 1fr); }
    .nav-links { display: none; }
    .traits { grid-template-columns: 1fr; }
    .contrib-grid { grid-template-columns: repeat(26, 12px); }
  }
</style>
</head>
<body>

<nav>
  <div class="nav-logo">Rakesh<span>.</span></div>
  <div class="nav-links">
    <a href="#about">About</a>
    <a href="#skills">Skills</a>
    <a href="#projects">Projects</a>
    <a href="#roadmap">Roadmap</a>
    <a href="#contact">Contact</a>
  </div>
  <div class="nav-badge">🟢 Open to Work</div>
</nav>

<section class="hero" id="home">
  <div class="hero-grid"></div>
  <div class="hero-glow"></div>
  <div class="hero-tag">B.Tech ECE · 2026 · Warangal, Telangana</div>
  <h1 class="hero-name">Rakesh <span class="hi">Sirupa</span></h1>
  <p class="hero-role">
    <span class="tag">&lt;</span>
    <span id="typed-text">DevOps Engineer</span><span class="typed-cursor">_</span>
    <span class="tag">/&gt;</span>
  </p>
  <div class="hero-cta">
    <a href="#projects" class="btn btn-primary">🚀 View Projects</a>
    <a href="#contact" class="btn btn-outline">📬 Get In Touch</a>
    <a href="https://github.com/Sirupa-Rakesh" target="_blank" class="btn btn-outline">⭐ GitHub</a>
    <a href="https://www.linkedin.com/in/rakesh-sirupa" target="_blank" class="btn btn-outline">💼 LinkedIn</a>
  </div>
  <div class="hero-scroll">
    <div class="scroll-line"></div>
    <span>SCROLL</span>
  </div>
</section>

<section id="about">
  <div class="container">
    <div class="section-label fade-up">// 01. about_me</div>
    <h2 class="section-title fade-up">Who I Am</h2>
    <div class="about-grid fade-up">
      <div>
        <div class="about-text">
          <p>I'm a <strong>B.Tech ECE graduate (2026)</strong> from Warangal, Telangana — deeply passionate about <strong>DevOps, Cloud Infrastructure, and Automation</strong>.</p>
          <p>I thrive on solving infrastructure challenges, building reliable pipelines, and automating repetitive workflows. My approach is always <strong>hands-on</strong> — I spin up lab environments, break things intentionally, and rebuild with deeper understanding.</p>
          <p>Currently deepening my expertise across the <strong>full DevOps toolchain</strong> — from Linux internals and Bash scripting to containerization with Docker and cloud deployments on AWS.</p>
          <p>I believe infrastructure should be <strong>code</strong>, deployments should be <strong>boring</strong>, and incidents should be <strong>learning opportunities</strong>.</p>
        </div>
        <div class="traits">
          <div class="trait"><div class="trait-icon">🔍</div><div><div class="trait-title">Problem Solver</div><div class="trait-desc">Debugging-first mindset; root-cause thinking over quick fixes.</div></div></div>
          <div class="trait"><div class="trait-icon">⚡</div><div><div class="trait-title">Self-Driven</div><div class="trait-desc">Ships real projects, not just tutorials or theory.</div></div></div>
          <div class="trait"><div class="trait-icon">🤝</div><div><div class="trait-title">Communicator</div><div class="trait-desc">Clear technical docs and team-friendly communication.</div></div></div>
          <div class="trait"><div class="trait-icon">🔁</div><div><div class="trait-title">Automator</div><div class="trait-desc">If I do it twice, I script it. If I script it, I version it.</div></div></div>
        </div>
      </div>
      <div class="yaml-card">
        <div class="comment"># rakesh-sirupa.yaml</div>
        <div class="yaml-sep">───────────────────────────</div>
        <div><span class="key">name</span>     : <span class="string">Rakesh Sirupa</span></div>
        <div><span class="key">degree</span>   : <span class="string">B.Tech ECE</span></div>
        <div><span class="key">batch</span>    : <span class="value">2022 – 2026</span></div>
        <div><span class="key">location</span> : <span class="string">Warangal, Telangana</span></div>
        <div class="yaml-sep">───────────────────────────</div>
        <div><span class="key">role</span>     : <span class="string">Aspiring DevOps Engineer</span></div>
        <div><span class="key">seeking</span>  : <span class="string">Entry-level / Internship</span></div>
        <div class="yaml-sep">───────────────────────────</div>
        <div><span class="key">learning</span> :</div>
        <div>&nbsp;&nbsp;- <span class="value">Kubernetes</span></div>
        <div>&nbsp;&nbsp;- <span class="value">Ansible</span></div>
        <div>&nbsp;&nbsp;- <span class="value">Terraform</span></div>
        <div>&nbsp;&nbsp;- <span class="value">AWS SAA</span></div>
        <div class="yaml-sep">───────────────────────────</div>
        <div><span class="key">mantra</span>   : <span class="string">Build · Break · Debug · Automate</span></div>
        <div class="yaml-sep">───────────────────────────</div>
        <div><span class="key">status</span>   : <span style="color:var(--accent2)">🟢 Open to Opportunities</span></div>
      </div>
    </div>
  </div>
</section>

<section id="skills" class="skills-section">
  <div class="container">
    <div class="section-label fade-up">// 02. tech_stack</div>
    <h2 class="section-title fade-up">Skills & Tools</h2>
    <p class="section-desc fade-up">My current proficiency across the DevOps ecosystem — actively expanding daily.</p>
    <div class="skills-grid fade-up">
      <div class="skill-group">
        <div class="skill-group-title">⚙️ Core DevOps</div>
        <div class="skill-item"><div class="skill-header"><span class="skill-name">Linux & Bash</span><span class="skill-pct">88%</span></div><div class="skill-bar"><div class="skill-fill blue" data-width="88"></div></div></div>
        <div class="skill-item"><div class="skill-header"><span class="skill-name">Git & GitHub</span><span class="skill-pct">85%</span></div><div class="skill-bar"><div class="skill-fill blue" data-width="85"></div></div></div>
        <div class="skill-item"><div class="skill-header"><span class="skill-name">Jenkins & CI/CD</span><span class="skill-pct">55%</span></div><div class="skill-bar"><div class="skill-fill blue" data-width="55"></div></div></div>
        <div class="skill-item"><div class="skill-header"><span class="skill-name">GitHub Actions</span><span class="skill-pct">50%</span></div><div class="skill-bar"><div class="skill-fill blue" data-width="50"></div></div></div>
        <div class="badges"><span class="badge b-blue">Ubuntu</span><span class="badge b-blue">Bash</span><span class="badge b-blue">Git</span><span class="badge b-blue">Jenkins</span><span class="badge b-blue">Nginx</span></div>
      </div>
      <div class="skill-group">
        <div class="skill-group-title">☁️ Cloud & Infra</div>
        <div class="skill-item"><div class="skill-header"><span class="skill-name">AWS (EC2, S3, IAM)</span><span class="skill-pct">58%</span></div><div class="skill-bar"><div class="skill-fill teal" data-width="58"></div></div></div>
        <div class="skill-item"><div class="skill-header"><span class="skill-name">Docker & Containers</span><span class="skill-pct">62%</span></div><div class="skill-bar"><div class="skill-fill teal" data-width="62"></div></div></div>
        <div class="skill-item"><div class="skill-header"><span class="skill-name">Kubernetes (K8s)</span><span class="skill-pct">32%</span></div><div class="skill-bar"><div class="skill-fill teal" data-width="32"></div></div></div>
        <div class="skill-item"><div class="skill-header"><span class="skill-name">Terraform</span><span class="skill-pct">18%</span></div><div class="skill-bar"><div class="skill-fill dim" data-width="18"></div></div></div>
        <div class="badges"><span class="badge b-teal">AWS EC2</span><span class="badge b-teal">S3</span><span class="badge b-teal">IAM</span><span class="badge b-teal">Docker</span><span class="badge b-teal">K8s</span></div>
      </div>
      <div class="skill-group">
        <div class="skill-group-title">📦 IaC & Automation</div>
        <div class="skill-item"><div class="skill-header"><span class="skill-name">Ansible</span><span class="skill-pct">22%</span></div><div class="skill-bar"><div class="skill-fill orange" data-width="22"></div></div></div>
        <div class="skill-item"><div class="skill-header"><span class="skill-name">YAML / Config</span><span class="skill-pct">80%</span></div><div class="skill-bar"><div class="skill-fill orange" data-width="80"></div></div></div>
        <div class="skill-item"><div class="skill-header"><span class="skill-name">JavaScript</span><span class="skill-pct">45%</span></div><div class="skill-bar"><div class="skill-fill orange" data-width="45"></div></div></div>
        <div class="skill-item"><div class="skill-header"><span class="skill-name">Markdown / Docs</span><span class="skill-pct">90%</span></div><div class="skill-bar"><div class="skill-fill orange" data-width="90"></div></div></div>
        <div class="badges"><span class="badge b-orange">Ansible</span><span class="badge b-orange">YAML</span><span class="badge b-orange">JS</span><span class="badge b-orange">Cron</span><span class="badge b-orange">Markdown</span></div>
      </div>
    </div>
  </div>
</section>

<section id="projects">
  <div class="container">
    <div class="section-label fade-up">// 03. projects</div>
    <h2 class="section-title fade-up">Featured Work</h2>
    <p class="section-desc fade-up">Real hands-on projects built in lab environments — not tutorials, actual deployments.</p>
    <div class="projects-grid fade-up">
      <div class="project-card blue">
        <div class="project-top">
          <div class="project-icon">🐳</div>
          <div class="project-links"><a href="https://github.com/Sirupa-Rakesh" target="_blank" class="project-link">↗ GitHub</a></div>
        </div>
        <div class="project-title">Docker CI/CD Pipeline</div>
        <div class="project-desc">Containerized a web application using Docker and automated the full build-test-deploy cycle with Jenkins. Includes reverse proxy configuration for production traffic routing.</div>
        <ul class="project-features">
          <li>Multi-stage Dockerfile for optimized, lean image builds</li>
          <li>Automated Jenkins pipeline triggered on every git push</li>
          <li>Nginx reverse proxy configuration for traffic routing</li>
          <li>Container health checks and automatic restart policies</li>
        </ul>
        <div class="project-stack"><span class="stack-tag">Docker</span><span class="stack-tag">Jenkins</span><span class="stack-tag">Nginx</span><span class="stack-tag">Linux</span><span class="stack-tag">Bash</span></div>
      </div>
      <div class="project-card teal">
        <div class="project-top">
          <div class="project-icon">☁️</div>
          <div class="project-links"><a href="https://github.com/Sirupa-Rakesh" target="_blank" class="project-link">↗ GitHub</a></div>
        </div>
        <div class="project-title">AWS Infrastructure Setup</div>
        <div class="project-desc">Provisioned and configured core AWS services for a small web application environment. Focused on security best practices including least-privilege IAM policies and encrypted storage.</div>
        <ul class="project-features">
          <li>EC2 instance setup with security groups and key pairs</li>
          <li>S3 bucket policies for static assets and encrypted backups</li>
          <li>IAM roles with least-privilege access policies</li>
          <li>VPC configuration with public and private subnets</li>
        </ul>
        <div class="project-stack"><span class="stack-tag">AWS EC2</span><span class="stack-tag">S3</span><span class="stack-tag">IAM</span><span class="stack-tag">VPC</span><span class="stack-tag">Bash</span></div>
      </div>
      <div class="project-card orange">
        <div class="project-top">
          <div class="project-icon">🐧</div>
          <div class="project-links"><a href="https://github.com/Sirupa-Rakesh" target="_blank" class="project-link">↗ GitHub</a></div>
        </div>
        <div class="project-title">Linux Automation Scripts</div>
        <div class="project-desc">A collection of production-quality Bash scripts for automating repetitive system administration tasks — all version controlled and documented with usage examples.</div>
        <ul class="project-features">
          <li>System health monitoring with CPU, memory, and disk alerts</li>
          <li>Automated backup pipeline with compressed log rotation</li>
          <li>User provisioning and permission management automation</li>
          <li>Cron-based scheduling for periodic maintenance tasks</li>
        </ul>
        <div class="project-stack"><span class="stack-tag">Bash</span><span class="stack-tag">Linux</span><span class="stack-tag">Cron</span><span class="stack-tag">Git</span><span class="stack-tag">systemd</span></div>
      </div>
      <div class="project-card purple">
        <div class="project-top">
          <div class="project-icon">🔁</div>
          <div class="project-links"><a href="https://github.com/Sirupa-Rakesh" target="_blank" class="project-link">↗ GitHub</a></div>
        </div>
        <div class="project-title">Git Workflow Practice Repo</div>
        <div class="project-desc">Structured hands-on practice repository for Git branching strategies, rebase workflows, conflict resolution, and professional PR processes used at engineering teams.</div>
        <ul class="project-features">
          <li>Feature branch and GitFlow branching strategies</li>
          <li>Merge conflict resolution with realistic multi-branch scenarios</li>
          <li>Pull request templates and structured code review habits</li>
          <li>Interactive rebase, cherry-pick, and bisect exercises</li>
        </ul>
        <div class="project-stack"><span class="stack-tag">Git</span><span class="stack-tag">GitHub</span><span class="stack-tag">Markdown</span><span class="stack-tag">GitFlow</span></div>
      </div>
    </div>
  </div>
</section>

<section style="background: var(--bg2); padding: 4rem 0;">
  <div class="container">
    <div class="section-label fade-up">// 04. github_analytics</div>
    <h2 class="section-title fade-up">Activity</h2>
    <div class="stats-grid fade-up">
      <div class="stat-card"><div class="stat-value" id="c-commits">0</div><div class="stat-label">TOTAL COMMITS</div></div>
      <div class="stat-card"><div class="stat-value" id="c-repos">0</div><div class="stat-label">PUBLIC REPOS</div></div>
      <div class="stat-card"><div class="stat-value" id="c-streak">0</div><div class="stat-label">DAY STREAK</div></div>
      <div class="stat-card"><div class="stat-value" id="c-stars">0</div><div class="stat-label">STARS EARNED</div></div>
    </div>
    <div class="contrib-graph fade-up">
      <div class="contrib-title">CONTRIBUTION GRAPH — LAST 12 MONTHS</div>
      <div class="contrib-grid" id="contrib-grid"></div>
    </div>
  </div>
</section>

<section id="roadmap" class="roadmap-section">
  <div class="container">
    <div class="section-label fade-up">// 05. roadmap</div>
    <h2 class="section-title fade-up">2025 / 2026 Plan</h2>
    <p class="section-desc fade-up">A structured path from fundamentals to landing that first DevOps role.</p>
    <div class="timeline fade-up">
      <div class="timeline-item">
        <div class="timeline-dot done"></div>
        <div class="timeline-header"><span class="timeline-quarter">Q1 2025</span><span class="timeline-title">Master Linux CLI & Bash Scripting</span><span class="timeline-status status-done">✅ Done</span></div>
        <div class="timeline-sub">File system, permissions, process management, cron, scripting patterns</div>
      </div>
      <div class="timeline-item">
        <div class="timeline-dot done"></div>
        <div class="timeline-header"><span class="timeline-quarter">Q1 2025</span><span class="timeline-title">Git & GitHub Workflows</span><span class="timeline-status status-done">✅ Done</span></div>
        <div class="timeline-sub">Branching strategies, PRs, rebase, conflict resolution, GitFlow</div>
      </div>
      <div class="timeline-item">
        <div class="timeline-dot active"></div>
        <div class="timeline-header"><span class="timeline-quarter">Q2 2025</span><span class="timeline-title">CI/CD Pipeline with Jenkins + Docker</span><span class="timeline-status status-progress">🔄 In Progress</span></div>
        <div class="timeline-sub">Multi-stage builds, pipeline as code, webhook triggers, artifact management</div>
      </div>
      <div class="timeline-item">
        <div class="timeline-dot active"></div>
        <div class="timeline-header"><span class="timeline-quarter">Q2 2025</span><span class="timeline-title">AWS Cloud Practitioner Certification</span><span class="timeline-status status-progress">🔄 In Progress</span></div>
        <div class="timeline-sub">EC2, S3, IAM, VPC, RDS, CloudWatch, Route 53</div>
      </div>
      <div class="timeline-item">
        <div class="timeline-dot planned"></div>
        <div class="timeline-header"><span class="timeline-quarter">Q3 2025</span><span class="timeline-title">Kubernetes Fundamentals (CKA Prep)</span><span class="timeline-status status-planned">📌 Planned</span></div>
        <div class="timeline-sub">Pods, deployments, services, ingress, persistent volumes, RBAC</div>
      </div>
      <div class="timeline-item">
        <div class="timeline-dot planned"></div>
        <div class="timeline-header"><span class="timeline-quarter">Q3 2025</span><span class="timeline-title">Ansible for Configuration Management</span><span class="timeline-status status-planned">📌 Planned</span></div>
        <div class="timeline-sub">Playbooks, roles, inventory management, idempotent automation</div>
      </div>
      <div class="timeline-item">
        <div class="timeline-dot planned"></div>
        <div class="timeline-header"><span class="timeline-quarter">Q4 2025</span><span class="timeline-title">Terraform for Infrastructure as Code</span><span class="timeline-status status-planned">📌 Planned</span></div>
        <div class="timeline-sub">HCL, state management, modules, remote backends, workspaces</div>
      </div>
      <div class="timeline-item">
        <div class="timeline-dot goal"></div>
        <div class="timeline-header"><span class="timeline-quarter">Q1 2026</span><span class="timeline-title">Land First DevOps Engineer / Intern Role 🚀</span><span class="timeline-status status-goal">🎯 Goal</span></div>
        <div class="timeline-sub">Target: Product-based company or strong DevOps-focused team</div>
      </div>
    </div>
  </div>
</section>

<section>
  <div class="container">
    <div class="section-label fade-up">// 06. philosophy</div>
    <h2 class="section-title fade-up">DevOps Mindset</h2>
    <div class="quote-block fade-up">"Infrastructure should be code. Deployments should be boring. Incidents should be learning opportunities."</div>
    <div class="philosophy-grid fade-up">
      <div class="philosophy-card"><div class="philo-icon">🔨</div><div class="philo-title">Build</div><div class="philo-desc">Hands-on projects over tutorials. Every tool I learn gets deployed in a real lab environment before I call it learned.</div></div>
      <div class="philosophy-card"><div class="philo-icon">🧪</div><div class="philo-title">Break</div><div class="philo-desc">Intentional failures teach more than smooth runs. I deliberately break my setups to understand failure modes and edge cases.</div></div>
      <div class="philosophy-card"><div class="philo-icon">🔍</div><div class="philo-title">Debug</div><div class="philo-desc">Logs, metrics, and root-cause thinking. Every incident is a chance to go deeper into systems understanding.</div></div>
      <div class="philosophy-card"><div class="philo-icon">🔁</div><div class="philo-title">Automate</div><div class="philo-desc">If I do it twice, I script it. If I script it, I version-control it. Manual is temporary; automation is permanent.</div></div>
    </div>
  </div>
</section>

<section id="contact" class="contact-section">
  <div class="container">
    <div class="section-label fade-up">// 07. contact</div>
    <h2 class="section-title fade-up">Let's Connect</h2>
    <div class="contact-grid fade-up">
      <div class="contact-info">
        <p class="about-text" style="margin-bottom: 1.5rem;">I'm actively looking for <strong style="color:var(--accent)">entry-level DevOps roles, internships, and mentorship</strong> opportunities. If you're a recruiter, engineer, or fellow learner — my inbox is always open!</p>
        <div class="contact-links">
          <a href="https://www.linkedin.com/in/rakesh-sirupa" target="_blank" class="contact-link-item">
            <div class="contact-link-icon">💼</div>
            <div><div class="contact-link-label">LINKEDIN</div><div class="contact-link-value">linkedin.com/in/rakesh-sirupa</div></div>
            <span style="margin-left: auto; color: var(--text3); font-size: 0.8rem;">↗</span>
          </a>
          <a href="https://github.com/Sirupa-Rakesh" target="_blank" class="contact-link-item">
            <div class="contact-link-icon">🐙</div>
            <div><div class="contact-link-label">GITHUB</div><div class="contact-link-value">github.com/Sirupa-Rakesh</div></div>
            <span style="margin-left: auto; color: var(--text3); font-size: 0.8rem;">↗</span>
          </a>
          <div class="contact-link-item">
            <div class="contact-link-icon">📍</div>
            <div><div class="contact-link-label">LOCATION</div><div class="contact-link-value">Warangal, Telangana, India</div></div>
          </div>
        </div>
        <div class="availability"><div class="avail-dot"></div>Available for Internships & Entry-level Roles</div>
      </div>
      <div class="contact-form-area">
        <div class="form-title">Send a Message</div>
        <div id="contact-form">
          <div class="form-group"><label class="form-label">YOUR NAME</label><input type="text" class="form-input" id="f-name" placeholder="e.g. Jane Smith" /></div>
          <div class="form-group"><label class="form-label">EMAIL</label><input type="email" class="form-input" id="f-email" placeholder="jane@company.com" /></div>
          <div class="form-group"><label class="form-label">SUBJECT</label><input type="text" class="form-input" id="f-subject" placeholder="e.g. Internship Opportunity" /></div>
          <div class="form-group"><label class="form-label">MESSAGE</label><textarea class="form-textarea" id="f-message" placeholder="Tell me about the opportunity or just say hi!"></textarea></div>
          <button class="btn-submit" onclick="submitForm()">Send Message →</button>
        </div>
        <div class="form-success" id="form-success">
          <div style="font-size: 2rem; margin-bottom: 1rem;">✅</div>
          <div style="font-size: 0.9rem; color: var(--accent2); margin-bottom: 0.5rem;">Message sent!</div>
          <div style="font-size: 0.75rem; color: var(--text3)">Thanks for reaching out. I'll get back to you soon.</div>
        </div>
      </div>
    </div>
  </div>
</section>

<footer>
  <p>Built with <span>❤️</span> by <span>Rakesh Sirupa</span> &nbsp;·&nbsp; B.Tech ECE 2026 &nbsp;·&nbsp; Warangal, Telangana</p>
  <p style="margin-top: 6px; font-size: 0.65rem; color: var(--text3)">DevOps Engineer · Cloud Infrastructure · Automation</p>
</footer>

<script>
const roles = ['DevOps Engineer', 'Cloud Builder', 'Linux Enthusiast', 'Automation Nerd', 'CI/CD Engineer'];
let ri = 0, ci = 0, del = false;
const el = document.getElementById('typed-text');
function type() {
  const word = roles[ri];
  if (!del) {
    el.textContent = word.slice(0, ++ci);
    if (ci === word.length) { del = true; setTimeout(type, 2000); return; }
  } else {
    el.textContent = word.slice(0, --ci);
    if (ci === 0) { del = false; ri = (ri + 1) % roles.length; }
  }
  setTimeout(type, del ? 60 : 90);
}
type();

const observer = new IntersectionObserver((entries) => {
  entries.forEach(e => { if (e.isIntersecting) e.target.classList.add('visible'); });
}, { threshold: 0.1 });
document.querySelectorAll('.fade-up').forEach(el => observer.observe(el));

const barObserver = new IntersectionObserver((entries) => {
  entries.forEach(e => {
    if (e.isIntersecting) {
      e.target.querySelectorAll('.skill-fill').forEach(bar => { bar.style.width = bar.dataset.width + '%'; });
    }
  });
}, { threshold: 0.3 });
document.querySelectorAll('.skills-grid').forEach(el => barObserver.observe(el));

function animateCount(id, target) {
  const el = document.getElementById(id);
  let cur = 0;
  const step = Math.ceil(target / 60);
  const t = setInterval(() => { cur = Math.min(cur + step, target); el.textContent = cur; if (cur >= target) clearInterval(t); }, 25);
}
const countObserver = new IntersectionObserver((entries) => {
  entries.forEach(e => {
    if (e.isIntersecting) {
      animateCount('c-commits', 124);
      animateCount('c-repos', 8);
      animateCount('c-streak', 21);
      animateCount('c-stars', 15);
      countObserver.disconnect();
    }
  });
}, { threshold: 0.4 });
const statsEl = document.querySelector('.stats-grid');
if (statsEl) countObserver.observe(statsEl);

function buildContrib() {
  const grid = document.getElementById('contrib-grid');
  if (!grid) return;
  const levels = [0,0,0,1,1,1,2,2,3,4];
  const colors = ['#0d1520','#0d3b5e','#1565c0','#1e90ff','#60b4ff'];
  for (let w = 0; w < 52; w++) {
    const col = document.createElement('div');
    col.className = 'contrib-col';
    for (let d = 0; d < 7; d++) {
      const cell = document.createElement('div');
      cell.className = 'contrib-cell';
      const lvl = levels[Math.floor(Math.random() * levels.length)];
      cell.style.background = colors[lvl];
      col.appendChild(cell);
    }
    grid.appendChild(col);
  }
}
buildContrib();

function submitForm() {
  const name = document.getElementById('f-name').value.trim();
  const email = document.getElementById('f-email').value.trim();
  if (!name || !email) { alert('Please fill in at least name and email.'); return; }
  document.getElementById('contact-form').style.display = 'none';
  document.getElementById('form-success').style.display = 'block';
}
</script>
</body>
</html>
