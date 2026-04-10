<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<style>
  @import url('https://fonts.googleapis.com/css2?family=Space+Mono:ital,wght@0,400;0,700;1,400&family=DM+Sans:wght@300;400;500;600&display=swap');

  * { margin: 0; padding: 0; box-sizing: border-box; }

  :root {
    --bg: #0a0a0f;
    --surface: #111118;
    --card: #16161f;
    --border: rgba(255,255,255,0.07);
    --border-bright: rgba(255,255,255,0.14);
    --text: #e8e6f0;
    --muted: #6b6880;
    --accent: #7c6af5;
    --accent2: #3ecfb0;
    --accent3: #f06292;
    --mono: 'Space Mono', monospace;
    --sans: 'DM Sans', sans-serif;
    --glow: 0 0 30px rgba(124,106,245,0.15);
  }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: var(--sans);
    min-height: 100vh;
    padding: 0;
    overflow-x: hidden;
  }

  /* HERO */
  .hero {
    position: relative;
    padding: 52px 40px 40px;
    border-bottom: 1px solid var(--border);
    overflow: hidden;
  }
  .hero::before {
    content: '';
    position: absolute;
    top: -80px; right: -80px;
    width: 340px; height: 340px;
    background: radial-gradient(circle, rgba(124,106,245,0.18) 0%, transparent 70%);
    pointer-events: none;
  }
  .hero::after {
    content: '';
    position: absolute;
    bottom: -60px; left: 20%;
    width: 260px; height: 260px;
    background: radial-gradient(circle, rgba(62,207,176,0.1) 0%, transparent 70%);
    pointer-events: none;
  }
  .hero-tag {
    font-family: var(--mono);
    font-size: 11px;
    color: var(--accent2);
    letter-spacing: 0.12em;
    text-transform: uppercase;
    margin-bottom: 14px;
    display: flex;
    align-items: center;
    gap: 8px;
  }
  .hero-tag::before {
    content: '';
    display: inline-block;
    width: 24px; height: 1px;
    background: var(--accent2);
  }
  .hero-name {
    font-family: var(--mono);
    font-size: 42px;
    font-weight: 700;
    line-height: 1.1;
    margin-bottom: 8px;
    background: linear-gradient(135deg, #e8e6f0 30%, var(--accent) 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }
  .hero-sub {
    font-size: 15px;
    color: var(--muted);
    font-weight: 300;
    margin-bottom: 28px;
    max-width: 480px;
    line-height: 1.6;
  }
  .hero-pills {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
  }
  .pill {
    font-family: var(--mono);
    font-size: 11px;
    padding: 5px 12px;
    border-radius: 2px;
    border: 1px solid;
    letter-spacing: 0.05em;
  }
  .pill-v { color: var(--accent); border-color: rgba(124,106,245,0.35); background: rgba(124,106,245,0.08); }
  .pill-g { color: var(--accent2); border-color: rgba(62,207,176,0.35); background: rgba(62,207,176,0.08); }
  .pill-r { color: var(--accent3); border-color: rgba(240,98,146,0.35); background: rgba(240,98,146,0.08); }

  /* GRID LAYOUT */
  .grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 1px;
    background: var(--border);
  }
  .grid-3 { grid-template-columns: 1fr 1fr 1fr; }

  .cell {
    background: var(--bg);
    padding: 28px 32px;
  }
  .cell-dark { background: var(--surface); }

  .section-label {
    font-family: var(--mono);
    font-size: 10px;
    letter-spacing: 0.14em;
    text-transform: uppercase;
    color: var(--muted);
    margin-bottom: 20px;
    display: flex;
    align-items: center;
    gap: 8px;
  }
  .section-label::after {
    content: '';
    flex: 1;
    height: 1px;
    background: var(--border);
  }

  /* TECH STACK */
  .tech-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 6px;
  }
  .tech-item {
    padding: 10px 12px;
    border: 1px solid var(--border);
    border-radius: 3px;
    font-family: var(--mono);
    font-size: 11px;
    color: var(--text);
    display: flex;
    align-items: center;
    gap: 8px;
    transition: border-color 0.2s, background 0.2s;
    cursor: default;
  }
  .tech-item:hover {
    border-color: var(--border-bright);
    background: var(--card);
  }
  .tech-dot {
    width: 6px; height: 6px;
    border-radius: 50%;
    flex-shrink: 0;
  }
  .d-purple { background: var(--accent); }
  .d-teal { background: var(--accent2); }
  .d-pink { background: var(--accent3); }
  .d-amber { background: #f0a830; }
  .d-blue { background: #5ab0f5; }
  .d-gray { background: var(--muted); }

  /* STATS */
  .stat-block {
    text-align: center;
  }
  .stat-num {
    font-family: var(--mono);
    font-size: 32px;
    font-weight: 700;
    color: var(--accent);
    line-height: 1;
    margin-bottom: 6px;
    counter-reset: none;
  }
  .stat-label {
    font-size: 11px;
    color: var(--muted);
    text-transform: uppercase;
    letter-spacing: 0.1em;
    font-family: var(--mono);
  }

  /* FOCUS */
  .focus-item {
    display: flex;
    align-items: flex-start;
    gap: 14px;
    padding: 10px 0;
    border-bottom: 1px solid var(--border);
    font-size: 13px;
    line-height: 1.5;
  }
  .focus-item:last-child { border-bottom: none; }
  .focus-key {
    font-family: var(--mono);
    font-size: 10px;
    color: var(--muted);
    letter-spacing: 0.08em;
    min-width: 52px;
    padding-top: 2px;
    text-transform: uppercase;
  }

  /* CONNECT */
  .connect-row {
    display: flex;
    flex-direction: column;
    gap: 8px;
  }
  .connect-link {
    display: flex;
    align-items: center;
    gap: 12px;
    padding: 10px 14px;
    border: 1px solid var(--border);
    border-radius: 3px;
    text-decoration: none;
    color: var(--text);
    font-size: 13px;
    font-family: var(--mono);
    transition: border-color 0.2s, background 0.2s;
    cursor: pointer;
  }
  .connect-link:hover {
    border-color: var(--border-bright);
    background: var(--card);
    color: var(--accent);
  }
  .connect-icon {
    width: 20px; height: 20px;
    border-radius: 3px;
    display: flex; align-items: center; justify-content: center;
    font-size: 11px;
    font-family: var(--mono);
    font-weight: 700;
    flex-shrink: 0;
  }
  .ci-li { background: rgba(0,119,181,0.2); color: #5ab0f5; }
  .ci-tw { background: rgba(29,161,242,0.2); color: #5ab0f5; }
  .ci-po { background: rgba(240,98,146,0.2); color: var(--accent3); }
  .ci-em { background: rgba(62,207,176,0.2); color: var(--accent2); }
  .arrow-out { margin-left: auto; color: var(--muted); font-size: 12px; }

  /* TERMINAL */
  .terminal {
    background: #0d0d14;
    border: 1px solid var(--border);
    border-radius: 4px;
    overflow: hidden;
  }
  .term-bar {
    background: var(--surface);
    padding: 8px 14px;
    display: flex;
    gap: 6px;
    align-items: center;
    border-bottom: 1px solid var(--border);
  }
  .dot { width: 10px; height: 10px; border-radius: 50%; }
  .d1 { background: #ff5f57; } .d2 { background: #febc2e; } .d3 { background: #28c840; }
  .term-body {
    padding: 16px 18px;
    font-family: var(--mono);
    font-size: 12px;
    line-height: 2;
  }
  .t-prompt { color: var(--accent2); }
  .t-cmd { color: var(--text); }
  .t-out { color: var(--muted); }
  .t-hi { color: var(--accent); }
  .t-hi2 { color: var(--accent3); }
  .cursor {
    display: inline-block;
    width: 8px; height: 14px;
    background: var(--accent);
    vertical-align: middle;
    animation: blink 1.1s step-end infinite;
  }
  @keyframes blink { 50% { opacity: 0; } }

  /* CONTRIB BAR */
  .contrib-bar {
    display: flex;
    gap: 3px;
    flex-wrap: wrap;
    margin-top: 12px;
  }
  .cb-week {
    display: flex;
    flex-direction: column;
    gap: 3px;
  }
  .cb-day {
    width: 11px; height: 11px;
    border-radius: 2px;
    background: var(--border);
    transition: background 0.15s;
  }
  .cb-day:hover { opacity: 0.8; }
  .lv1 { background: rgba(124,106,245,0.25); }
  .lv2 { background: rgba(124,106,245,0.5); }
  .lv3 { background: rgba(124,106,245,0.75); }
  .lv4 { background: rgba(124,106,245,1); }

  /* FOOTER */
  .footer {
    padding: 20px 32px;
    border-top: 1px solid var(--border);
    display: flex;
    align-items: center;
    justify-content: space-between;
    font-family: var(--mono);
    font-size: 11px;
    color: var(--muted);
    background: var(--surface);
  }
  .footer-status {
    display: flex;
    align-items: center;
    gap: 7px;
  }
  .status-dot {
    width: 6px; height: 6px;
    border-radius: 50%;
    background: var(--accent2);
    box-shadow: 0 0 6px var(--accent2);
    animation: pulse 2s ease-in-out infinite;
  }
  @keyframes pulse { 0%,100% { opacity: 1; } 50% { opacity: 0.4; } }

  .full-width { grid-column: 1 / -1; }

  /* SKILL BARS */
  .skill-row {
    margin-bottom: 12px;
  }
  .skill-header {
    display: flex;
    justify-content: space-between;
    font-size: 12px;
    color: var(--muted);
    font-family: var(--mono);
    margin-bottom: 6px;
  }
  .skill-bar {
    height: 2px;
    background: var(--border);
    border-radius: 1px;
    overflow: hidden;
  }
  .skill-fill {
    height: 100%;
    border-radius: 1px;
    animation: fillbar 1.2s ease-out forwards;
  }
  @keyframes fillbar { from { width: 0; } }
</style>
</head>
<body>

<div class="hero">
  <div class="hero-tag">@Ye-Thihaa — github profile</div>
  <div class="hero-name">Frontend<br>Developer.</div>
  <p class="hero-sub">Building full-stack web applications. Currently deep in advanced React patterns, system design, and open source collaboration.</p>
  <div class="hero-pills">
    <span class="pill pill-v">Available for collab</span>
    <span class="pill pill-g">Open source</span>
    <span class="pill pill-r">console.log enthusiast</span>
  </div>
</div>

<div class="grid" style="border-top:1px solid var(--border)">

  <!-- TECH STACK -->
  <div class="cell full-width">
    <div class="section-label">Tech stack</div>
    <div class="tech-grid">
      <div class="tech-item"><span class="tech-dot d-purple"></span>TypeScript</div>
      <div class="tech-item"><span class="tech-dot d-teal"></span>React</div>
      <div class="tech-item"><span class="tech-dot d-teal"></span>Next.js</div>
      <div class="tech-item"><span class="tech-dot d-blue"></span>Python</div>
      <div class="tech-item"><span class="tech-dot d-blue"></span>Node.js</div>
      <div class="tech-item"><span class="tech-dot d-blue"></span>Express</div>
      <div class="tech-item"><span class="tech-dot d-amber"></span>Java</div>
      <div class="tech-item"><span class="tech-dot d-amber"></span>C++</div>
      <div class="tech-item"><span class="tech-dot d-gray"></span>JavaScript</div>
      <div class="tech-item"><span class="tech-dot d-pink"></span>Laravel</div>
      <div class="tech-item"><span class="tech-dot d-pink"></span>Flask</div>
      <div class="tech-item"><span class="tech-dot d-purple"></span>Astro</div>
      <div class="tech-item"><span class="tech-dot d-teal"></span>Tailwind CSS</div>
      <div class="tech-item"><span class="tech-dot d-gray"></span>Three.js</div>
      <div class="tech-item"><span class="tech-dot d-amber"></span>Docker</div>
      <div class="tech-item"><span class="tech-dot d-blue"></span>PostgreSQL</div>
      <div class="tech-item"><span class="tech-dot d-teal"></span>Supabase</div>
      <div class="tech-item"><span class="tech-dot d-amber"></span>MongoDB</div>
    </div>
  </div>

  <!-- TERMINAL -->
  <div class="cell cell-dark">
    <div class="section-label">Terminal</div>
    <div class="terminal">
      <div class="term-bar">
        <div class="dot d1"></div><div class="dot d2"></div><div class="dot d3"></div>
      </div>
      <div class="term-body">
        <div><span class="t-prompt">~/dev</span> <span class="t-cmd">whoami</span></div>
        <div class="t-out">→ <span class="t-hi">frontend developer</span> & open source contributor</div>
        <div><span class="t-prompt">~/dev</span> <span class="t-cmd">cat focus.txt</span></div>
        <div class="t-out">→ full-stack apps · <span class="t-hi2">react patterns</span> · system design</div>
        <div><span class="t-prompt">~/dev</span> <span class="t-cmd">git status</span></div>
        <div class="t-out">→ always <span class="t-hi">learning</span>, always <span class="t-hi2">building</span></div>
        <div><span class="t-prompt">~/dev</span> <span class="cursor"></span></div>
      </div>
    </div>
  </div>

  <!-- SKILL BARS -->
  <div class="cell">
    <div class="section-label">Proficiency</div>
    <div class="skill-row">
      <div class="skill-header"><span>Frontend</span><span>90%</span></div>
      <div class="skill-bar"><div class="skill-fill" style="width:90%;background:var(--accent)"></div></div>
    </div>
    <div class="skill-row">
      <div class="skill-header"><span>Backend</span><span>75%</span></div>
      <div class="skill-bar"><div class="skill-fill" style="width:75%;background:var(--accent2)"></div></div>
    </div>
    <div class="skill-row">
      <div class="skill-header"><span>Databases</span><span>70%</span></div>
      <div class="skill-bar"><div class="skill-fill" style="width:70%;background:var(--accent3)"></div></div>
    </div>
    <div class="skill-row">
      <div class="skill-header"><span>DevOps / Cloud</span><span>55%</span></div>
      <div class="skill-bar"><div class="skill-fill" style="width:55%;background:#f0a830"></div></div>
    </div>
    <div class="skill-row">
      <div class="skill-header"><span>System Design</span><span>65%</span></div>
      <div class="skill-bar"><div class="skill-fill" style="width:65%;background:#5ab0f5"></div></div>
    </div>
  </div>

  <!-- GITHUB STATS -->
  <div class="cell cell-dark">
    <div class="section-label">GitHub stats</div>
    <div style="display:grid;grid-template-columns:1fr 1fr 1fr;gap:16px;margin-bottom:24px">
      <div class="stat-block">
        <div class="stat-num">847</div>
        <div class="stat-label">Commits</div>
      </div>
      <div class="stat-block">
        <div class="stat-num" style="color:var(--accent2)">23</div>
        <div class="stat-label">Repos</div>
      </div>
      <div class="stat-block">
        <div class="stat-num" style="color:var(--accent3)">142</div>
        <div class="stat-label">Stars</div>
      </div>
    </div>
    <div class="section-label" style="font-size:9px">Contributions</div>
    <div class="contrib-bar" id="contribs"></div>
    <script>
      const cb = document.getElementById('contribs');
      const levels = [0,0,1,1,2,2,3,4,3,2,1,0,1,2,3,2,1,0,0,1,2,1,3,4,3,2,1,0,0,1,2,3,2,1,0,1,2,3,4,3,2,1,0,0,1,2,3,2,1,0];
      const cls = ['','lv1','lv2','lv3','lv4'];
      for (let w = 0; w < 50; w++) {
        const week = document.createElement('div');
        week.className = 'cb-week';
        for (let d = 0; d < 7; d++) {
          const day = document.createElement('div');
          const lv = Math.floor(Math.random() * 5) * (levels[w] > 0 ? 1 : 0.3) | 0;
          day.className = 'cb-day ' + (cls[Math.min(lv, 4)] || '');
          week.appendChild(day);
        }
        cb.appendChild(week);
      }
    </script>
  </div>

  <!-- CURRENT FOCUS -->
  <div class="cell">
    <div class="section-label">Current focus</div>
    <div class="focus-item">
      <span class="focus-key">Build</span>
      <span>Full-stack web applications with modern tooling</span>
    </div>
    <div class="focus-item">
      <span class="focus-key">Learn</span>
      <span>Advanced React patterns & system design</span>
    </div>
    <div class="focus-item">
      <span class="focus-key">Collab</span>
      <span>Open source projects — reach out anytime</span>
    </div>
    <div class="focus-item">
      <span class="focus-key">Ask me</span>
      <span>Web dev, APIs, and database design</span>
    </div>
    <div class="focus-item">
      <span class="focus-key">Deploy</span>
      <span>Vercel · Render · AWS · Netlify · Docker</span>
    </div>
  </div>

  <!-- CONNECT -->
  <div class="cell cell-dark">
    <div class="section-label">Let's connect</div>
    <div class="connect-row">
      <div class="connect-link">
        <div class="connect-icon ci-li">in</div>
        <span>LinkedIn</span>
        <span class="arrow-out">↗</span>
      </div>
      <div class="connect-link">
        <div class="connect-icon ci-tw">𝕏</div>
        <span>Twitter / X</span>
        <span class="arrow-out">↗</span>
      </div>
      <div class="connect-link">
        <div class="connect-icon ci-po">◈</div>
        <span>Portfolio</span>
        <span class="arrow-out">↗</span>
      </div>
      <div class="connect-link">
        <div class="connect-icon ci-em">@</div>
        <span>Email me</span>
        <span class="arrow-out">↗</span>
      </div>
    </div>
  </div>

</div>

<div class="footer">
  <div class="footer-status">
    <div class="status-dot"></div>
    <span>Open to collaboration</span>
  </div>
  <span>Ye-Thihaa · github readme</span>
</div>

</body>
</html>
