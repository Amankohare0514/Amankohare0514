<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Aman Kohare — README</title>
<link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;600;700;800&family=Space+Mono:wght@400;700&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #080c14;
    --surface: #0d1421;
    --card: #111827;
    --border: #1f2d45;
    --accent: #00d4ff;
    --accent2: #7c3aed;
    --accent3: #f59e0b;
    --text: #e2e8f0;
    --muted: #64748b;
    --green: #10b981;
  }
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
  
  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'Syne', sans-serif;
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* Animated background grid */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image: 
      linear-gradient(rgba(0,212,255,0.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(0,212,255,0.03) 1px, transparent 1px);
    background-size: 60px 60px;
    pointer-events: none;
    z-index: 0;
  }

  .container {
    max-width: 860px;
    margin: 0 auto;
    padding: 60px 24px 100px;
    position: relative;
    z-index: 1;
  }

  /* ── HERO ── */
  .hero {
    display: grid;
    grid-template-columns: 1fr auto;
    gap: 40px;
    align-items: start;
    margin-bottom: 72px;
    padding-bottom: 72px;
    border-bottom: 1px solid var(--border);
    position: relative;
  }

  .hero::after {
    content: '';
    position: absolute;
    bottom: -1px;
    left: 0;
    width: 120px;
    height: 1px;
    background: linear-gradient(90deg, var(--accent), transparent);
  }

  .status-pill {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    background: rgba(16,185,129,0.1);
    border: 1px solid rgba(16,185,129,0.25);
    color: var(--green);
    font-family: 'Space Mono', monospace;
    font-size: 11px;
    letter-spacing: 0.1em;
    padding: 5px 12px;
    border-radius: 20px;
    margin-bottom: 20px;
    text-transform: uppercase;
  }

  .status-dot {
    width: 7px; height: 7px;
    background: var(--green);
    border-radius: 50%;
    animation: pulse 2s ease-in-out infinite;
  }

  @keyframes pulse {
    0%, 100% { opacity: 1; box-shadow: 0 0 0 0 rgba(16,185,129,0.4); }
    50% { opacity: 0.7; box-shadow: 0 0 0 6px rgba(16,185,129,0); }
  }

  .hero-name {
    font-size: clamp(36px, 6vw, 58px);
    font-weight: 800;
    line-height: 1.05;
    letter-spacing: -0.03em;
    margin-bottom: 6px;
  }

  .hero-name span {
    background: linear-gradient(135deg, #fff 30%, var(--accent));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }

  .hero-role {
    font-family: 'Space Mono', monospace;
    font-size: 13px;
    color: var(--accent);
    letter-spacing: 0.15em;
    text-transform: uppercase;
    margin-bottom: 20px;
  }

  .hero-bio {
    color: var(--muted);
    font-size: 15px;
    line-height: 1.7;
    max-width: 480px;
  }

  .hero-links {
    display: flex;
    gap: 12px;
    margin-top: 28px;
    flex-wrap: wrap;
  }

  .btn {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    padding: 10px 20px;
    border-radius: 8px;
    font-size: 13px;
    font-weight: 600;
    text-decoration: none;
    transition: all 0.2s;
    letter-spacing: 0.02em;
  }

  .btn-primary {
    background: var(--accent);
    color: #000;
  }
  .btn-primary:hover { background: #fff; transform: translateY(-2px); }

  .btn-ghost {
    background: transparent;
    color: var(--text);
    border: 1px solid var(--border);
  }
  .btn-ghost:hover { border-color: var(--accent); color: var(--accent); transform: translateY(-2px); }

  /* Avatar area */
  .hero-avatar {
    position: relative;
    flex-shrink: 0;
  }

  .avatar-frame {
    width: 130px;
    height: 130px;
    border-radius: 24px;
    background: linear-gradient(135deg, var(--accent2), var(--accent));
    padding: 2px;
    position: relative;
  }

  .avatar-inner {
    width: 100%;
    height: 100%;
    border-radius: 22px;
    background: var(--card);
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 52px;
    font-weight: 800;
    color: var(--accent);
    letter-spacing: -0.05em;
  }

  .avatar-badge {
    position: absolute;
    bottom: -8px;
    right: -8px;
    width: 36px;
    height: 36px;
    background: var(--accent3);
    border-radius: 10px;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 18px;
    border: 2px solid var(--bg);
  }

  /* ── SECTION HEADERS ── */
  .section {
    margin-bottom: 56px;
  }

  .section-label {
    display: flex;
    align-items: center;
    gap: 14px;
    margin-bottom: 28px;
  }

  .section-label h2 {
    font-size: 11px;
    font-family: 'Space Mono', monospace;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    color: var(--muted);
  }

  .section-line {
    flex: 1;
    height: 1px;
    background: var(--border);
  }

  /* ── SKILL GRID ── */
  .skill-category {
    margin-bottom: 32px;
  }

  .skill-category-title {
    font-size: 12px;
    font-family: 'Space Mono', monospace;
    color: var(--accent);
    letter-spacing: 0.12em;
    text-transform: uppercase;
    margin-bottom: 14px;
    padding-left: 12px;
    border-left: 2px solid var(--accent);
  }

  .skill-tags {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
  }

  .skill-tag {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    background: var(--card);
    border: 1px solid var(--border);
    padding: 8px 14px;
    border-radius: 10px;
    font-size: 13px;
    font-weight: 600;
    transition: all 0.2s;
    cursor: default;
    position: relative;
    overflow: hidden;
  }

  .skill-tag::before {
    content: '';
    position: absolute;
    inset: 0;
    background: linear-gradient(135deg, var(--accent), var(--accent2));
    opacity: 0;
    transition: opacity 0.2s;
  }

  .skill-tag:hover { border-color: var(--accent); transform: translateY(-2px); box-shadow: 0 8px 24px rgba(0,212,255,0.15); }
  .skill-tag:hover::before { opacity: 0.07; }

  .skill-icon { font-size: 16px; position: relative; z-index: 1; }
  .skill-name { position: relative; z-index: 1; }

  /* ── WHAT I BUILD ── */
  .build-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    gap: 16px;
  }

  .build-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 16px;
    padding: 24px 20px;
    transition: all 0.25s;
    position: relative;
    overflow: hidden;
  }

  .build-card::after {
    content: '';
    position: absolute;
    bottom: 0; left: 0;
    width: 100%; height: 2px;
    background: linear-gradient(90deg, var(--accent), var(--accent2));
    transform: scaleX(0);
    transform-origin: left;
    transition: transform 0.3s;
  }

  .build-card:hover { border-color: rgba(0,212,255,0.3); transform: translateY(-3px); box-shadow: 0 16px 40px rgba(0,0,0,0.3); }
  .build-card:hover::after { transform: scaleX(1); }

  .build-icon { font-size: 28px; margin-bottom: 14px; }
  .build-title { font-size: 15px; font-weight: 700; margin-bottom: 6px; }
  .build-desc { font-size: 12px; color: var(--muted); line-height: 1.6; }

  /* ── CONNECT ── */
  .connect-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(160px, 1fr));
    gap: 12px;
  }

  .connect-card {
    display: flex;
    align-items: center;
    gap: 12px;
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 16px 18px;
    text-decoration: none;
    color: var(--text);
    font-size: 13px;
    font-weight: 600;
    transition: all 0.2s;
  }

  .connect-card:hover { border-color: var(--accent); color: var(--accent); transform: translateX(4px); }
  .connect-icon { font-size: 20px; }
  .connect-label { flex: 1; }
  .connect-arrow { color: var(--muted); font-size: 16px; transition: transform 0.2s; }
  .connect-card:hover .connect-arrow { transform: translateX(3px); color: var(--accent); }

  /* ── STATS ROW ── */
  .stats-row {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 16px;
    margin-bottom: 56px;
  }

  .stat-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 16px;
    padding: 24px;
    text-align: center;
  }

  .stat-number {
    font-size: 32px;
    font-weight: 800;
    background: linear-gradient(135deg, var(--accent), var(--accent2));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    display: block;
    margin-bottom: 4px;
  }

  .stat-label {
    font-size: 11px;
    font-family: 'Space Mono', monospace;
    color: var(--muted);
    letter-spacing: 0.1em;
    text-transform: uppercase;
  }

  /* ── FOOTER ── */
  .footer {
    text-align: center;
    padding-top: 56px;
    border-top: 1px solid var(--border);
    color: var(--muted);
    font-family: 'Space Mono', monospace;
    font-size: 11px;
    letter-spacing: 0.1em;
  }

  .footer span { color: var(--accent); }

  /* Animations */
  @keyframes fadeSlideUp {
    from { opacity: 0; transform: translateY(20px); }
    to { opacity: 1; transform: translateY(0); }
  }

  .hero { animation: fadeSlideUp 0.6s ease both; }
  .section { animation: fadeSlideUp 0.6s ease both; }
  .section:nth-child(2) { animation-delay: 0.1s; }
  .section:nth-child(3) { animation-delay: 0.2s; }
  .section:nth-child(4) { animation-delay: 0.3s; }

  /* README wrapper look */
  .readme-wrapper {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 16px;
    padding: 48px;
    position: relative;
  }

  .readme-topbar {
    display: flex;
    align-items: center;
    gap: 8px;
    margin-bottom: 40px;
    padding-bottom: 20px;
    border-bottom: 1px solid var(--border);
  }

  .dot { width: 12px; height: 12px; border-radius: 50%; }
  .dot-red { background: #ff5f57; }
  .dot-yellow { background: #ffbd2e; }
  .dot-green { background: #28c840; }

  .readme-filename {
    font-family: 'Space Mono', monospace;
    font-size: 12px;
    color: var(--muted);
    margin-left: 12px;
    letter-spacing: 0.05em;
  }

  @media (max-width: 600px) {
    .readme-wrapper { padding: 24px 18px; }
    .hero { grid-template-columns: 1fr; }
    .hero-avatar { display: none; }
    .stats-row { grid-template-columns: 1fr; }
  }
</style>
</head>
<body>
<div class="container">
  <div class="readme-wrapper">

    <!-- Top bar like a code editor / GitHub -->
    <div class="readme-topbar">
      <div class="dot dot-red"></div>
      <div class="dot dot-yellow"></div>
      <div class="dot dot-green"></div>
      <span class="readme-filename">README.md — amankohare</span>
    </div>

    <!-- HERO -->
    <div class="hero">
      <div>
        <div class="status-pill">
          <div class="status-dot"></div>
          Open to opportunities
        </div>
        <h1 class="hero-name"><span>Aman Kohare</span></h1>
        <p class="hero-role">// Full-Stack Web Developer</p>
        <p class="hero-bio">
          I craft modern web experiences — from pixel-perfect UIs to robust APIs.
          Passionate about performance, clean code, and turning ideas into polished products.
          Based in India, building for the world.
        </p>
        <div class="hero-links">
          <a href="https://amankohare.live" class="btn btn-primary" target="_blank">
            🌐 Portfolio
          </a>
          <a href="https://www.linkedin.com/in/aman-kohare-3a0678235/" class="btn btn-ghost" target="_blank">
            💼 LinkedIn
          </a>
          <a href="https://x.com/Aman__0514" class="btn btn-ghost" target="_blank">
            𝕏 Twitter
          </a>
        </div>
      </div>
      <div class="hero-avatar">
        <div class="avatar-frame">
          <div class="avatar-inner">AK</div>
        </div>
        <div class="avatar-badge">⚡</div>
      </div>
    </div>

    <!-- STATS -->
    <div class="stats-row">
      <div class="stat-card">
        <span class="stat-number">3+</span>
        <span class="stat-label">Years Coding</span>
      </div>
      <div class="stat-card">
        <span class="stat-number">20+</span>
        <span class="stat-label">Projects Shipped</span>
      </div>
      <div class="stat-card">
        <span class="stat-number">15+</span>
        <span class="stat-label">Technologies</span>
      </div>
    </div>

    <!-- SKILLS -->
    <div class="section">
      <div class="section-label">
        <h2>Tech Stack</h2>
        <div class="section-line"></div>
      </div>

      <div class="skill-category">
        <div class="skill-category-title">Languages & Core</div>
        <div class="skill-tags">
          <span class="skill-tag"><span class="skill-icon">🌐</span><span class="skill-name">HTML5</span></span>
          <span class="skill-tag"><span class="skill-icon">🎨</span><span class="skill-name">CSS3</span></span>
          <span class="skill-tag"><span class="skill-icon">⚡</span><span class="skill-name">JavaScript</span></span>
          <span class="skill-tag"><span class="skill-icon">🔷</span><span class="skill-name">TypeScript</span></span>
        </div>
      </div>

      <div class="skill-category">
        <div class="skill-category-title">Frontend</div>
        <div class="skill-tags">
          <span class="skill-tag"><span class="skill-icon">⚛️</span><span class="skill-name">React.js</span></span>
          <span class="skill-tag"><span class="skill-icon">▲</span><span class="skill-name">Next.js</span></span>
          <span class="skill-tag"><span class="skill-icon">📱</span><span class="skill-name">React Native</span></span>
          <span class="skill-tag"><span class="skill-icon">🌊</span><span class="skill-name">Tailwind CSS</span></span>
          <span class="skill-tag"><span class="skill-icon">🅱️</span><span class="skill-name">Bootstrap</span></span>
          <span class="skill-tag"><span class="skill-icon">🔴</span><span class="skill-name">Redux</span></span>
        </div>
      </div>

      <div class="skill-category">
        <div class="skill-category-title">Backend</div>
        <div class="skill-tags">
          <span class="skill-tag"><span class="skill-icon">🟢</span><span class="skill-name">Node.js</span></span>
          <span class="skill-tag"><span class="skill-icon">🚂</span><span class="skill-name">Express.js</span></span>
          <span class="skill-tag"><span class="skill-icon">🍃</span><span class="skill-name">MongoDB</span></span>
          <span class="skill-tag"><span class="skill-icon">🔥</span><span class="skill-name">Firebase</span></span>
          <span class="skill-tag"><span class="skill-icon">🟦</span><span class="skill-name">Sanity.io</span></span>
        </div>
      </div>

      <div class="skill-category">
        <div class="skill-category-title">Tools & Platforms</div>
        <div class="skill-tags">
          <span class="skill-tag"><span class="skill-icon">▲</span><span class="skill-name">Vercel</span></span>
          <span class="skill-tag"><span class="skill-icon">🌍</span><span class="skill-name">Netlify</span></span>
          <span class="skill-tag"><span class="skill-icon">📦</span><span class="skill-name">Expo</span></span>
          <span class="skill-tag"><span class="skill-icon">🐙</span><span class="skill-name">GitHub</span></span>
          <span class="skill-tag"><span class="skill-icon">🐧</span><span class="skill-name">Linux</span></span>
          <span class="skill-tag"><span class="skill-icon">🎨</span><span class="skill-name">Figma</span></span>
          <span class="skill-tag"><span class="skill-icon">✏️</span><span class="skill-name">Canva</span></span>
        </div>
      </div>
    </div>

    <!-- WHAT I BUILD -->
    <div class="section">
      <div class="section-label">
        <h2>What I Build</h2>
        <div class="section-line"></div>
      </div>
      <div class="build-grid">
        <div class="build-card">
          <div class="build-icon">🖥️</div>
          <div class="build-title">Web Apps</div>
          <div class="build-desc">Full-stack applications with great UX and solid architecture</div>
        </div>
        <div class="build-card">
          <div class="build-icon">📱</div>
          <div class="build-title">Mobile Apps</div>
          <div class="build-desc">Cross-platform apps using React Native & Expo</div>
        </div>
        <div class="build-card">
          <div class="build-icon">🚀</div>
          <div class="build-title">APIs & Backends</div>
          <div class="build-desc">RESTful APIs and database architecture with Node.js</div>
        </div>
        <div class="build-card">
          <div class="build-icon">🎯</div>
          <div class="build-title">UI/UX Design</div>
          <div class="build-desc">Pixel-perfect interfaces designed in Figma first</div>
        </div>
      </div>
    </div>

    <!-- CONNECT -->
    <div class="section">
      <div class="section-label">
        <h2>Let's Connect</h2>
        <div class="section-line"></div>
      </div>
      <div class="connect-grid">
        <a href="https://amankohare.live" class="connect-card" target="_blank">
          <span class="connect-icon">🌐</span>
          <span class="connect-label">Portfolio</span>
          <span class="connect-arrow">→</span>
        </a>
        <a href="https://www.linkedin.com/in/aman-kohare-3a0678235/" class="connect-card" target="_blank">
          <span class="connect-icon">💼</span>
          <span class="connect-label">LinkedIn</span>
          <span class="connect-arrow">→</span>
        </a>
        <a href="https://x.com/Aman__0514" class="connect-card" target="_blank">
          <span class="connect-icon">𝕏</span>
          <span class="connect-label">Twitter</span>
          <span class="connect-arrow">→</span>
        </a>
        <a href="https://github.com/Amankohare0514" class="connect-card" target="_blank">
          <span class="connect-icon">🐙</span>
          <span class="connect-label">GitHub</span>
          <span class="connect-arrow">→</span>
        </a>
      </div>
    </div>

    <!-- FOOTER -->
    <div class="footer">
      <p>Made with <span>♥</span> by Aman Kohare &nbsp;·&nbsp; <span>amankohare.live</span></p>
    </div>

  </div>
</div>
</body>
</html>
