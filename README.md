<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Anandha Krishnan PS – Portfolio</title>
<link href="https://fonts.googleapis.com/css2?family=Space+Mono:wght@400;700&family=Syne:wght@400;700;800&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #0a0a0f;
    --card: #111118;
    --border: #1e1e2e;
    --accent: #7c3aed;
    --accent2: #06b6d4;
    --accent3: #f59e0b;
    --text: #e2e8f0;
    --muted: #64748b;
    --glow: rgba(124, 58, 237, 0.35);
  }
  * { margin: 0; padding: 0; box-sizing: border-box; }
  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'DM Sans', sans-serif;
    min-height: 100vh;
    overflow-x: hidden;
  }
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      linear-gradient(rgba(124,58,237,0.04) 1px, transparent 1px),
      linear-gradient(90deg, rgba(124,58,237,0.04) 1px, transparent 1px);
    background-size: 60px 60px;
    pointer-events: none;
    z-index: 0;
  }
  .container {
    max-width: 960px;
    margin: 0 auto;
    padding: 60px 24px;
    position: relative;
    z-index: 1;
  }

  /* HERO */
  .hero {
    display: grid;
    grid-template-columns: 1fr 370px;
    gap: 48px;
    align-items: center;
    margin-bottom: 72px;
  }
  .hero-tag {
    font-family: 'Space Mono', monospace;
    font-size: 11px;
    color: var(--accent2);
    letter-spacing: 3px;
    text-transform: uppercase;
    margin-bottom: 16px;
    display: flex;
    align-items: center;
    gap: 8px;
    animation: fadeUp 0.6s ease both;
  }
  .hero-tag::before { content: ''; width: 24px; height: 1px; background: var(--accent2); }
  .hero-name {
    font-family: 'Syne', sans-serif;
    font-size: clamp(36px, 5vw, 56px);
    font-weight: 800;
    line-height: 1.05;
    letter-spacing: -1px;
    margin-bottom: 8px;
    animation: fadeUp 0.6s 0.1s ease both;
  }
  .hero-name .highlight {
    background: linear-gradient(135deg, var(--accent), var(--accent2));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }
  .hero-role {
    font-size: 15px;
    color: var(--muted);
    margin-bottom: 28px;
    font-weight: 300;
    animation: fadeUp 0.6s 0.2s ease both;
  }
  .hero-role span { color: var(--accent3); font-weight: 500; }
  .hero-badges {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
    margin-bottom: 32px;
    animation: fadeUp 0.6s 0.3s ease both;
  }
  .badge {
    font-family: 'Space Mono', monospace;
    font-size: 10px;
    padding: 5px 12px;
    border-radius: 2px;
    border: 1px solid var(--border);
    background: var(--card);
    color: var(--muted);
    letter-spacing: 1px;
    transition: all 0.25s;
    cursor: default;
  }
  .badge:hover { border-color: var(--accent); color: var(--accent); box-shadow: 0 0 12px var(--glow); }
  .badge.learning { border-color: rgba(124,58,237,0.4); color: #a78bfa; }
  .hero-links {
    display: flex;
    gap: 12px;
    animation: fadeUp 0.6s 0.4s ease both;
  }
  .btn {
    font-family: 'Space Mono', monospace;
    font-size: 11px;
    padding: 12px 22px;
    text-decoration: none;
    letter-spacing: 1px;
    border-radius: 2px;
    transition: all 0.25s;
    display: inline-flex;
    align-items: center;
    gap: 8px;
  }
  .btn-primary { background: var(--accent); color: #fff; box-shadow: 0 0 20px var(--glow); }
  .btn-primary:hover { background: #6d28d9; transform: translateY(-2px); box-shadow: 0 4px 30px var(--glow); }
  .btn-outline { border: 1px solid var(--border); color: var(--muted); background: transparent; }
  .btn-outline:hover { border-color: var(--accent2); color: var(--accent2); transform: translateY(-2px); }

  /* GIF FRAME */
  .gif-frame {
    position: relative;
    animation: fadeUp 0.6s 0.2s ease both;
  }
  .gif-frame::before {
    content: '';
    position: absolute;
    inset: -2px;
    background: linear-gradient(135deg, var(--accent), var(--accent2), transparent 60%);
    border-radius: 6px;
    z-index: -1;
  }
  .gif-frame::after {
    content: '';
    position: absolute;
    inset: 0;
    background: linear-gradient(to bottom, transparent 60%, var(--bg));
    border-radius: 4px;
    pointer-events: none;
  }
  .gif-frame img { width: 100%; border-radius: 4px; display: block; filter: saturate(1.1); }
  .gif-corner {
    position: absolute;
    font-family: 'Space Mono', monospace;
    font-size: 9px;
    color: var(--accent2);
    letter-spacing: 2px;
    z-index: 2;
  }
  .gif-corner.tl { top: 10px; left: 12px; }
  .gif-corner.br { bottom: 14px; right: 12px; }

  /* SECTION HEADER */
  .section-header { display: flex; align-items: center; gap: 16px; margin-bottom: 28px; }
  .section-label { font-family: 'Space Mono', monospace; font-size: 11px; color: var(--accent); letter-spacing: 3px; text-transform: uppercase; white-space: nowrap; }
  .section-line { flex: 1; height: 1px; background: linear-gradient(to right, var(--border), transparent); }

  /* ABOUT CARDS */
  .about-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 14px; margin-bottom: 64px; }
  .about-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 4px;
    padding: 22px 20px;
    transition: all 0.3s;
    position: relative;
    overflow: hidden;
    animation: fadeUp 0.5s ease both;
  }
  .about-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 2px;
    background: linear-gradient(to right, var(--accent), transparent);
    opacity: 0;
    transition: opacity 0.3s;
  }
  .about-card:hover { border-color: rgba(124,58,237,0.4); transform: translateY(-4px); box-shadow: 0 12px 40px rgba(0,0,0,0.4); }
  .about-card:hover::before { opacity: 1; }
  .about-icon { font-size: 22px; margin-bottom: 12px; display: block; }
  .about-card h4 { font-family: 'Syne', sans-serif; font-size: 12px; font-weight: 700; margin-bottom: 6px; color: var(--text); letter-spacing: 1px; }
  .about-card p { font-size: 13px; color: var(--muted); line-height: 1.6; }
  .about-card a { color: var(--accent2); text-decoration: none; }
  .about-card a:hover { text-decoration: underline; }

  /* TECH STACK */
  .tech-section { margin-bottom: 64px; }
  .tech-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(78px, 1fr)); gap: 10px; }
  .tech-item {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 4px;
    padding: 16px 8px;
    text-align: center;
    transition: all 0.3s;
    cursor: default;
    animation: fadeUp 0.4s ease both;
  }
  .tech-item:hover { border-color: var(--accent); transform: translateY(-3px); box-shadow: 0 8px 24px rgba(124,58,237,0.2); }
  .tech-item img { width: 30px; height: 30px; object-fit: contain; margin-bottom: 8px; filter: brightness(0.85) saturate(0.8); transition: filter 0.3s; display: block; margin-left: auto; margin-right: auto; }
  .tech-item:hover img { filter: brightness(1) saturate(1.2); }
  .tech-item span { display: block; font-family: 'Space Mono', monospace; font-size: 9px; color: var(--muted); letter-spacing: 0.5px; }

  /* STATS */
  .stats-section { margin-bottom: 64px; }
  .stats-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 14px; }
  .stat-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 4px;
    overflow: hidden;
    transition: all 0.3s;
  }
  .stat-card:hover { border-color: rgba(124,58,237,0.4); transform: translateY(-3px); box-shadow: 0 8px 32px rgba(0,0,0,0.3); }
  .stat-card img { width: 100%; display: block; padding: 10px; }

  /* CONNECT */
  .connect-section { margin-bottom: 48px; }
  .connect-row { display: flex; gap: 12px; flex-wrap: wrap; }
  .social-link {
    display: flex;
    align-items: center;
    gap: 10px;
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 4px;
    padding: 13px 18px;
    text-decoration: none;
    color: var(--muted);
    font-size: 12px;
    font-family: 'Space Mono', monospace;
    letter-spacing: 0.5px;
    transition: all 0.25s;
  }
  .social-link:hover { transform: translateY(-3px); box-shadow: 0 8px 24px rgba(0,0,0,0.3); }
  .social-link.linkedin:hover { border-color: #0077b5; color: #0077b5; }
  .social-link.instagram:hover { border-color: #e1306c; color: #e1306c; }
  .social-link.email:hover { border-color: var(--accent3); color: var(--accent3); }
  .social-link.portfolio:hover { border-color: var(--accent2); color: var(--accent2); }
  .social-link svg { width: 16px; height: 16px; flex-shrink: 0; }

  /* VIEWS BADGE */
  .views-badge {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 2px;
    padding: 5px 12px;
    font-family: 'Space Mono', monospace;
    font-size: 10px;
    color: var(--muted);
    margin-bottom: 20px;
    letter-spacing: 1px;
    animation: fadeUp 0.6s ease both;
  }
  .views-badge .dot { width: 5px; height: 5px; border-radius: 50%; background: var(--accent2); box-shadow: 0 0 6px var(--accent2); animation: pulse 2s infinite; }

  /* FOOTER */
  .footer { text-align: center; padding-top: 40px; border-top: 1px solid var(--border); font-family: 'Space Mono', monospace; font-size: 11px; color: var(--muted); letter-spacing: 1px; }
  .footer span { color: var(--accent); }

  /* ANIMATIONS */
  @keyframes fadeUp { from { opacity: 0; transform: translateY(18px); } to { opacity: 1; transform: translateY(0); } }
  @keyframes pulse { 0%, 100% { opacity: 1; transform: scale(1); } 50% { opacity: 0.5; transform: scale(1.6); } }

  @media (max-width: 720px) {
    .hero { grid-template-columns: 1fr; }
    .gif-frame { order: -1; max-width: 280px; }
    .about-grid { grid-template-columns: 1fr; }
    .stats-grid { grid-template-columns: 1fr; }
  }
</style>
</head>
<body>
<div class="container">

  <!-- HERO -->
  <section class="hero">
    <div class="hero-left">
      <div class="views-badge"><span class="dot"></span>OPEN TO WORK &nbsp;·&nbsp; INDIA 🇮🇳</div>
      <div class="hero-tag">Full-Stack Developer</div>
      <h1 class="hero-name">Anandha<br><span class="highlight">Krishnan PS</span></h1>
      <p class="hero-role">Building with <span>Django</span> · <span>React</span> · <span>Python</span></p>
      <div class="hero-badges">
        <span class="badge learning">▸ Currently learning: Python · Django · React</span>
        <span class="badge">Django</span>
        <span class="badge">React</span>
        <span class="badge">PostgreSQL</span>
        <span class="badge">Node.js</span>
      </div>
      <div class="hero-links">
        <a href="https://anandhakrishnanps.vercel.app/" class="btn btn-primary" target="_blank">
          <svg width="13" height="13" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M18 13v6a2 2 0 01-2 2H5a2 2 0 01-2-2V8a2 2 0 012-2h6"/><polyline points="15 3 21 3 21 9"/><line x1="10" y1="14" x2="21" y2="3"/></svg>
          View Portfolio
        </a>
        <a href="mailto:kanandha808@gmail.com" class="btn btn-outline">
          <svg width="13" height="13" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"/><polyline points="22,6 12,12 2,6"/></svg>
          Contact
        </a>
      </div>
    </div>

    <!-- GIF stays in the perfect spot on the right -->
    <div class="gif-frame">
      <span class="gif-corner tl">// ANANDHA.DEV</span>
      <img src="https://static.wixstatic.com/media/b313a9_89ebec0c5f384c65a9551f0c1ec18ca9~mv2.gif" alt="coding gif">
      <span class="gif-corner br">FULLSTACK ▸</span>
    </div>
  </section>

  <!-- ABOUT -->
  <section>
    <div class="section-header">
      <span class="section-label">// about</span>
      <div class="section-line"></div>
    </div>
    <div class="about-grid">
      <div class="about-card" style="animation-delay:0.05s">
        <span class="about-icon">🌱</span>
        <h4>CURRENTLY LEARNING</h4>
        <p>Deep-diving into the Python · Django · React stack, building full-stack apps end-to-end.</p>
      </div>
      <div class="about-card" style="animation-delay:0.1s">
        <span class="about-icon">💬</span>
        <h4>ASK ME ABOUT</h4>
        <p>Django REST Framework, React hooks, database design, or anything fullstack.</p>
      </div>
      <div class="about-card" style="animation-delay:0.15s">
        <span class="about-icon">📫</span>
        <h4>REACH ME</h4>
        <p><a href="mailto:kanandha808@gmail.com">kanandha808@gmail.com</a></p>
      </div>
    </div>
  </section>

  <!-- TECH STACK -->
  <section class="tech-section">
    <div class="section-header">
      <span class="section-label">// tech stack</span>
      <div class="section-line"></div>
    </div>
    <div class="tech-grid">
      <div class="tech-item" style="animation-delay:0.04s"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/html5/html5-original-wordmark.svg" alt="HTML5"><span>HTML5</span></div>
      <div class="tech-item" style="animation-delay:0.06s"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/css3/css3-original-wordmark.svg" alt="CSS3"><span>CSS3</span></div>
      <div class="tech-item" style="animation-delay:0.08s"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/javascript/javascript-original.svg" alt="JavaScript"><span>JS</span></div>
      <div class="tech-item" style="animation-delay:0.10s"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/react/react-original-wordmark.svg" alt="React"><span>React</span></div>
      <div class="tech-item" style="animation-delay:0.12s"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/bootstrap/bootstrap-plain-wordmark.svg" alt="Bootstrap"><span>Bootstrap</span></div>
      <div class="tech-item" style="animation-delay:0.14s"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/python/python-original.svg" alt="Python"><span>Python</span></div>
      <div class="tech-item" style="animation-delay:0.16s"><img src="https://cdn.worldvectorlogo.com/logos/django.svg" alt="Django"><span>Django</span></div>
      <div class="tech-item" style="animation-delay:0.18s"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/nodejs/nodejs-original-wordmark.svg" alt="Node.js"><span>Node.js</span></div>
      <div class="tech-item" style="animation-delay:0.20s"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/java/java-original.svg" alt="Java"><span>Java</span></div>
      <div class="tech-item" style="animation-delay:0.22s"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/c/c-original.svg" alt="C"><span>C</span></div>
      <div class="tech-item" style="animation-delay:0.24s"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/cplusplus/cplusplus-original.svg" alt="C++"><span>C++</span></div>
      <div class="tech-item" style="animation-delay:0.26s"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/postgresql/postgresql-original-wordmark.svg" alt="PostgreSQL"><span>Postgres</span></div>
      <div class="tech-item" style="animation-delay:0.28s"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/mysql/mysql-original-wordmark.svg" alt="MySQL"><span>MySQL</span></div>
      <div class="tech-item" style="animation-delay:0.30s"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/mongodb/mongodb-original-wordmark.svg" alt="MongoDB"><span>MongoDB</span></div>
      <div class="tech-item" style="animation-delay:0.32s"><img src="https://www.vectorlogo.zone/logos/git-scm/git-scm-icon.svg" alt="Git"><span>Git</span></div>
    </div>
  </section>

  <!-- GITHUB STATS -->
  <section class="stats-section">
    <div class="section-header">
      <span class="section-label">// github stats</span>
      <div class="section-line"></div>
    </div>
    <div class="stats-grid">
      <div class="stat-card">
        <img src="https://github-readme-stats.vercel.app/api?username=anandakrishnann&show_icons=true&theme=transparent&hide_border=true&title_color=7c3aed&icon_color=06b6d4&text_color=94a3b8&bg_color=00000000" alt="GitHub Stats">
      </div>
      <div class="stat-card">
        <img src="https://github-readme-stats.vercel.app/api/top-langs?username=anandakrishnann&show_icons=true&theme=transparent&hide_border=true&layout=compact&title_color=7c3aed&text_color=94a3b8&bg_color=00000000" alt="Top Languages">
      </div>
      <div class="stat-card">
        <img src="https://github-readme-streak-stats.herokuapp.com/?user=anandakrishnann&theme=transparent&hide_border=true&background=00000000&ring=7c3aed&fire=f59e0b&currStreakLabel=06b6d4&sideLabels=94a3b8&dates=64748b" alt="Streak Stats">
      </div>
    </div>
  </section>

  <!-- CONNECT -->
  <section class="connect-section">
    <div class="section-header">
      <span class="section-label">// connect</span>
      <div class="section-line"></div>
    </div>
    <div class="connect-row">
      <a href="https://linkedin.com/in/anandha-krishnan" class="social-link linkedin" target="_blank">
        <svg viewBox="0 0 24 24" fill="currentColor"><path d="M16 8a6 6 0 016 6v7h-4v-7a2 2 0 00-2-2 2 2 0 00-2 2v7h-4v-7a6 6 0 016-6zM2 9h4v12H2z"/><circle cx="4" cy="4" r="2"/></svg>
        LinkedIn
      </a>
      <a href="https://instagram.com/ananda.krishnnn" class="social-link instagram" target="_blank">
        <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><rect x="2" y="2" width="20" height="20" rx="5"/><path d="M16 11.37A4 4 0 1112.63 8 4 4 0 0116 11.37z"/><line x1="17.5" y1="6.5" x2="17.51" y2="6.5"/></svg>
        Instagram
      </a>
      <a href="mailto:kanandha808@gmail.com" class="social-link email">
        <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"/><polyline points="22,6 12,12 2,6"/></svg>
        kanandha808@gmail.com
      </a>
      <a href="https://anandhakrishnanps.vercel.app/" class="social-link portfolio" target="_blank">
        <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="12" cy="12" r="10"/><line x1="2" y1="12" x2="22" y2="12"/><path d="M12 2a15.3 15.3 0 014 10 15.3 15.3 0 01-4 10 15.3 15.3 0 01-4-10 15.3 15.3 0 014-10z"/></svg>
        Portfolio
      </a>
    </div>
  </section>

  <!-- FOOTER -->
  <footer class="footer">
    <p>Made with <span>♥</span> by Anandha Krishnan PS &nbsp;·&nbsp; India 🇮🇳</p>
  </footer>

</div>
</body>
</html>
