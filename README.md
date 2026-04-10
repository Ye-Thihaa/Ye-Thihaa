
<style>
  @import url('https://fonts.googleapis.com/css2?family=DM+Mono:ital,wght@0,300;0,400;0,500;1,300&family=DM+Serif+Display:ital@0;1&display=swap');

  *{box-sizing:border-box;margin:0;padding:0}

  :root{
    --ink:#0a0a0a;
    --ink2:#444;
    --ink3:#888;
    --rule:rgba(0,0,0,0.1);
    --bg:#fafafa;
    --card:#fff;
    --accent:#0a0a0a;
  }

  @media(prefers-color-scheme:dark){
    :root{
      --ink:#f0f0ee;
      --ink2:#aaa;
      --ink3:#666;
      --rule:rgba(255,255,255,0.1);
      --bg:#0f0f0f;
      --card:#1a1a1a;
      --accent:#f0f0ee;
    }
  }

  body{font-family:'DM Mono',monospace;background:var(--bg);color:var(--ink);padding:0}

  .wrap{max-width:780px;margin:0 auto;padding:2.5rem 2rem}

  .header-rule{height:1px;background:var(--ink);margin-bottom:2rem}

  .masthead{display:grid;grid-template-columns:1fr auto;align-items:end;gap:1rem;margin-bottom:2.5rem}

  .name{font-family:'DM Serif Display',serif;font-size:clamp(2.2rem,6vw,3.8rem);line-height:1;letter-spacing:-0.02em;color:var(--ink)}
  .name em{font-style:italic;color:var(--ink2)}

  .role-tag{font-size:11px;letter-spacing:0.12em;text-transform:uppercase;color:var(--ink3);border:1px solid var(--rule);padding:6px 10px;white-space:nowrap;align-self:flex-start}

  .bio{font-size:13px;color:var(--ink2);line-height:1.8;max-width:480px;margin-bottom:2.5rem;border-left:2px solid var(--ink);padding-left:1rem}

  .section-label{font-size:10px;letter-spacing:0.18em;text-transform:uppercase;color:var(--ink3);margin-bottom:1rem}

  .rule{height:1px;background:var(--rule);margin:2rem 0}

  .stack-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(0,1fr));gap:0}

  .stack-col{border-right:1px solid var(--rule);padding:1.2rem}
  .stack-col:last-child{border-right:none}

  .stack-col-title{font-size:10px;letter-spacing:0.14em;text-transform:uppercase;color:var(--ink3);margin-bottom:0.8rem}

  .tag-list{display:flex;flex-wrap:wrap;gap:6px}

  .tag{font-size:11px;color:var(--ink2);border:1px solid var(--rule);padding:3px 8px;cursor:default;transition:all 0.15s}
  .tag:hover{background:var(--ink);color:var(--bg);border-color:var(--ink)}

  .focus-grid{display:grid;grid-template-columns:1fr 1fr;gap:1px;background:var(--rule);border:1px solid var(--rule);margin-bottom:2rem}

  .focus-item{background:var(--card);padding:1rem 1.2rem}

  .focus-num{font-size:10px;color:var(--ink3);letter-spacing:0.1em;margin-bottom:4px}
  .focus-text{font-size:12px;color:var(--ink2);line-height:1.5}

  .links-row{display:flex;gap:1.5rem;flex-wrap:wrap;align-items:center}

  .link-item{font-size:12px;color:var(--ink);letter-spacing:0.06em;text-decoration:none;display:flex;align-items:center;gap:6px;border-bottom:1px solid var(--ink);padding-bottom:2px;transition:opacity 0.15s}
  .link-item:hover{opacity:0.5}

  .footer-rule{height:1px;background:var(--ink);margin-top:2rem}
  .footer-note{font-size:10px;color:var(--ink3);margin-top:0.8rem;letter-spacing:0.08em}

  .stat-strip{display:flex;gap:0;border:1px solid var(--rule);margin-bottom:2rem}
  .stat-cell{flex:1;padding:1rem 1.2rem;border-right:1px solid var(--rule)}
  .stat-cell:last-child{border-right:none}
  .stat-num{font-family:'DM Serif Display',serif;font-size:1.8rem;color:var(--ink);line-height:1}
  .stat-label{font-size:10px;color:var(--ink3);letter-spacing:0.1em;text-transform:uppercase;margin-top:4px}

  .ticker{overflow:hidden;border:1px solid var(--rule);padding:0.6rem 1rem;margin-bottom:2rem}
  .ticker-inner{display:flex;gap:3rem;animation:scroll 18s linear infinite;white-space:nowrap}
  .ticker-inner:hover{animation-play-state:paused}
  @keyframes scroll{0%{transform:translateX(0)}100%{transform:translateX(-50%)}}
  .ticker-item{font-size:11px;color:var(--ink3);letter-spacing:0.1em;text-transform:uppercase}
  .ticker-item span{color:var(--ink);margin-right:1rem}

  .blink{animation:blink 1.2s step-end infinite}
  @keyframes blink{0%,100%{opacity:1}50%{opacity:0}}
</style>

<div class="wrap">
  <div class="header-rule"></div>

  <div class="masthead">
    <div>
      <div style="font-size:11px;letter-spacing:0.16em;text-transform:uppercase;color:var(--ink3);margin-bottom:0.6rem">Ye-Thihaa / readme.md</div>
      <div class="name">Frontend<br><em>Developer</em></div>
    </div>
    <div class="role-tag">Open to collab</div>
  </div>

  <p class="bio">
    Building full-stack web applications. Interested in advanced React patterns, system design, and open source collaboration. Debugs with <code style="font-family:inherit;background:var(--rule);padding:1px 4px">console.log</code> — no apologies.<span class="blink" style="margin-left:2px">_</span>
  </p>

  <div class="ticker">
    <div class="ticker-inner">
      <span class="ticker-item"><span>React</span>Next.js &nbsp;·&nbsp;</span>
      <span class="ticker-item"><span>TypeScript</span>JavaScript &nbsp;·&nbsp;</span>
      <span class="ticker-item"><span>Node.js</span>Express &nbsp;·&nbsp;</span>
      <span class="ticker-item"><span>PostgreSQL</span>MongoDB &nbsp;·&nbsp;</span>
      <span class="ticker-item"><span>Docker</span>AWS &nbsp;·&nbsp;</span>
      <span class="ticker-item"><span>Tailwind</span>Three.js &nbsp;·&nbsp;</span>
      <span class="ticker-item"><span>React</span>Next.js &nbsp;·&nbsp;</span>
      <span class="ticker-item"><span>TypeScript</span>JavaScript &nbsp;·&nbsp;</span>
      <span class="ticker-item"><span>Node.js</span>Express &nbsp;·&nbsp;</span>
      <span class="ticker-item"><span>PostgreSQL</span>MongoDB &nbsp;·&nbsp;</span>
      <span class="ticker-item"><span>Docker</span>AWS &nbsp;·&nbsp;</span>
      <span class="ticker-item"><span>Tailwind</span>Three.js &nbsp;·&nbsp;</span>
    </div>
  </div>

  <div class="rule"></div>
  <div class="section-label">Stack</div>

  <div style="display:grid;grid-template-columns:repeat(5,minmax(0,1fr));border:1px solid var(--rule);margin-bottom:2rem">
    <div class="stack-col">
      <div class="stack-col-title">Languages</div>
      <div class="tag-list">
        <span class="tag">JS</span>
        <span class="tag">TS</span>
        <span class="tag">Python</span>
        <span class="tag">Java</span>
        <span class="tag">C++</span>
      </div>
    </div>
    <div class="stack-col">
      <div class="stack-col-title">Frontend</div>
      <div class="tag-list">
        <span class="tag">React</span>
        <span class="tag">Next.js</span>
        <span class="tag">Astro</span>
        <span class="tag">Tailwind</span>
        <span class="tag">Three.js</span>
      </div>
    </div>
    <div class="stack-col">
      <div class="stack-col-title">Backend</div>
      <div class="tag-list">
        <span class="tag">Node.js</span>
        <span class="tag">Express</span>
        <span class="tag">Laravel</span>
        <span class="tag">Flask</span>
      </div>
    </div>
    <div class="stack-col">
      <div class="stack-col-title">Database</div>
      <div class="tag-list">
        <span class="tag">PostgreSQL</span>
        <span class="tag">MySQL</span>
        <span class="tag">MongoDB</span>
        <span class="tag">Supabase</span>
        <span class="tag">Firebase</span>
      </div>
    </div>
    <div class="stack-col">
      <div class="stack-col-title">Deploy</div>
      <div class="tag-list">
        <span class="tag">Vercel</span>
        <span class="tag">Docker</span>
        <span class="tag">AWS</span>
        <span class="tag">Render</span>
        <span class="tag">Netlify</span>
      </div>
    </div>
  </div>

  <div class="rule"></div>
  <div class="section-label">Current focus</div>

  <div class="focus-grid">
    <div class="focus-item">
      <div class="focus-num">01</div>
      <div class="focus-text">Full-stack web applications</div>
    </div>
    <div class="focus-item">
      <div class="focus-num">02</div>
      <div class="focus-text">Advanced React patterns</div>
    </div>
    <div class="focus-item">
      <div class="focus-num">03</div>
      <div class="focus-text">System design</div>
    </div>
    <div class="focus-item">
      <div class="focus-num">04</div>
      <div class="focus-text">Open source collaboration</div>
    </div>
  </div>

  <div class="rule"></div>
  <div class="section-label">GitHub activity</div>

  <div style="border:1px solid var(--rule);padding:1rem 1.2rem;margin-bottom:2rem">
    <img
      src="https://github-readme-activity-graph.vercel.app/graph?username=Ye-Thihaa&bg_color=transparent&color=888888&line=0a0a0a&point=0a0a0a&area=false&hide_border=true&custom_title=contribution+graph"
      style="width:100%;display:block;opacity:0.85"
      alt="GitHub contribution graph"
    />
  </div>

  <div style="display:grid;grid-template-columns:1fr 1fr;gap:1rem;margin-bottom:2rem">
    <div style="border:1px solid var(--rule);padding:1rem">
      <img
        src="https://github-readme-stats.vercel.app/api?username=Ye-Thihaa&show_icons=true&theme=graywhite&include_all_commits=true&count_private=true&hide_border=true&title_color=0a0a0a&text_color=888888&icon_color=0a0a0a&bg_color=00000000"
        style="width:100%;display:block"
        alt="GitHub stats"
      />
    </div>
    <div style="border:1px solid var(--rule);padding:1rem">
      <img
        src="https://github-readme-stats.vercel.app/api/top-langs/?username=Ye-Thihaa&layout=compact&langs_count=6&theme=graywhite&hide_border=true&title_color=0a0a0a&text_color=888888&bg_color=00000000"
        style="width:100%;display:block"
        alt="Top languages"
      />
    </div>
  </div>

  <div class="rule"></div>
  <div class="section-label">Connect</div>

  <div class="links-row">
    <a href="https://linkedin.com/in/your-profile" class="link-item">
      <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2 2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6z"/><rect x="2" y="9" width="4" height="12"/><circle cx="4" cy="4" r="2"/></svg>
      LinkedIn
    </a>
    <a href="https://twitter.com/your-handle" class="link-item">
      <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M23 3a10.9 10.9 0 0 1-3.14 1.53 4.48 4.48 0 0 0-7.86 3v1A10.66 10.66 0 0 1 3 4s-4 9 5 13a11.64 11.64 0 0 1-7 2c9 5 20 0 20-11.5a4.5 4.5 0 0 0-.08-.83A7.72 7.72 0 0 0 23 3z"/></svg>
      Twitter
    </a>
    <a href="https://your-portfolio.com" class="link-item">
      <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="12" cy="12" r="10"/><line x1="2" y1="12" x2="22" y2="12"/><path d="M12 2a15.3 15.3 0 0 1 4 10 15.3 15.3 0 0 1-4 10 15.3 15.3 0 0 1-4-10 15.3 15.3 0 0 1 4-10z"/></svg>
      Portfolio
    </a>
    <a href="mailto:your.email@gmail.com" class="link-item">
      <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"/><polyline points="22,6 12,13 2,6"/></svg>
      Email
    </a>
  </div>

  <div class="footer-rule"></div>
  <div class="footer-note" style="margin-top:0.8rem">Ye-Thihaa &nbsp;·&nbsp; Frontend Developer &nbsp;·&nbsp; <span id="yr"></span></div>
</div>

<script>document.getElementById('yr').textContent = new Date().getFullYear();</script>
