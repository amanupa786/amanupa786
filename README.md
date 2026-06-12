<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Aman | Data Analyst — GitHub Profile</title>
<link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@300;400;500;600;700&family=JetBrains+Mono:wght@300;400;600&display=swap" rel="stylesheet"/>
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --black: #000000;
    --near-black: #0a0a0a;
    --surface: #111111;
    --surface2: #1a1a1a;
    --border: #222222;
    --border-light: #2e2e2e;
    --white: #ffffff;
    --grey-1: #f5f5f5;
    --grey-2: #aaaaaa;
    --grey-3: #555555;
    --mono: 'JetBrains Mono', monospace;
    --sans: 'Space Grotesk', sans-serif;
  }

  html { scroll-behavior: smooth; }

  body {
    background: var(--black);
    color: var(--white);
    font-family: var(--sans);
    overflow-x: hidden;
    line-height: 1.6;
  }

  /* ── PARTICLES CANVAS ── */
  #particles { position: fixed; top: 0; left: 0; width: 100%; height: 100%; z-index: 0; pointer-events: none; opacity: 0.35; }

  .content { position: relative; z-index: 1; max-width: 860px; margin: 0 auto; padding: 0 24px 80px; }

  /* ── HERO ── */
  .hero {
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    text-align: center;
    padding: 80px 0 60px;
    border-bottom: 1px solid var(--border);
  }

  .hero-eyebrow {
    font-family: var(--mono);
    font-size: 11px;
    letter-spacing: 4px;
    color: var(--grey-2);
    text-transform: uppercase;
    margin-bottom: 28px;
    opacity: 0;
    animation: fadeUp 0.8s 0.2s forwards;
  }

  .hero-name {
    font-size: clamp(52px, 10vw, 88px);
    font-weight: 700;
    letter-spacing: -3px;
    line-height: 0.95;
    margin-bottom: 24px;
    opacity: 0;
    animation: fadeUp 0.8s 0.4s forwards;
  }

  .hero-name span {
    display: inline-block;
    border-bottom: 3px solid var(--white);
    padding-bottom: 4px;
  }

  .hero-role {
    font-family: var(--mono);
    font-size: 15px;
    color: var(--grey-2);
    margin-bottom: 48px;
    height: 26px;
    opacity: 0;
    animation: fadeUp 0.8s 0.6s forwards;
  }

  .cursor {
    display: inline-block;
    width: 2px;
    height: 1em;
    background: var(--white);
    margin-left: 2px;
    vertical-align: middle;
    animation: blink 1s step-end infinite;
  }

  @keyframes blink { 0%,100%{opacity:1} 50%{opacity:0} }

  .hero-tags {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
    justify-content: center;
    margin-bottom: 52px;
    opacity: 0;
    animation: fadeUp 0.8s 0.8s forwards;
  }

  .tag {
    font-family: var(--mono);
    font-size: 11px;
    letter-spacing: 1.5px;
    color: var(--grey-2);
    border: 1px solid var(--border-light);
    padding: 6px 14px;
    text-transform: uppercase;
    transition: all 0.25s;
  }

  .tag:hover { color: var(--white); border-color: var(--white); background: var(--surface); }

  .hero-links {
    display: flex;
    gap: 14px;
    flex-wrap: wrap;
    justify-content: center;
    opacity: 0;
    animation: fadeUp 0.8s 1.0s forwards;
  }

  .btn {
    font-family: var(--mono);
    font-size: 11px;
    letter-spacing: 2px;
    text-transform: uppercase;
    text-decoration: none;
    padding: 12px 24px;
    border: 1px solid var(--white);
    color: var(--white);
    background: transparent;
    transition: all 0.25s;
    display: inline-flex;
    align-items: center;
    gap: 8px;
  }

  .btn:hover { background: var(--white); color: var(--black); }
  .btn.ghost { border-color: var(--border-light); color: var(--grey-2); }
  .btn.ghost:hover { border-color: var(--white); color: var(--white); background: transparent; }

  /* ── SECTION ── */
  .section { padding: 72px 0; border-bottom: 1px solid var(--border); }

  .section-label {
    font-family: var(--mono);
    font-size: 10px;
    letter-spacing: 4px;
    color: var(--grey-3);
    text-transform: uppercase;
    margin-bottom: 40px;
    display: flex;
    align-items: center;
    gap: 16px;
  }

  .section-label::after { content: ''; flex: 1; height: 1px; background: var(--border); }

  /* ── CODE BLOCK ── */
  .code-block {
    background: var(--surface);
    border: 1px solid var(--border);
    padding: 32px;
    font-family: var(--mono);
    font-size: 13px;
    line-height: 1.8;
    overflow-x: auto;
    position: relative;
  }

  .code-block::before {
    content: '● ● ●';
    display: block;
    font-size: 10px;
    color: var(--grey-3);
    letter-spacing: 6px;
    margin-bottom: 20px;
  }

  .c-kw { color: #999; }
  .c-cls { color: #fff; font-weight: 600; }
  .c-str { color: #ddd; }
  .c-key { color: #bbb; }
  .c-cm { color: #444; font-style: italic; }
  .c-fn { color: #eee; }

  /* ── SKILLS GRID ── */
  .skills-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(240px, 1fr)); gap: 1px; background: var(--border); }

  .skill-card {
    background: var(--black);
    padding: 28px 24px;
    transition: background 0.2s;
  }

  .skill-card:hover { background: var(--surface); }

  .skill-category {
    font-family: var(--mono);
    font-size: 9px;
    letter-spacing: 3px;
    color: var(--grey-3);
    text-transform: uppercase;
    margin-bottom: 16px;
  }

  .skill-items { display: flex; flex-wrap: wrap; gap: 6px; }

  .skill-pill {
    font-family: var(--mono);
    font-size: 11px;
    color: var(--grey-1);
    background: var(--surface2);
    border: 1px solid var(--border-light);
    padding: 4px 10px;
  }

  /* ── BARS ── */
  .bars { display: flex; flex-direction: column; gap: 18px; }

  .bar-row { display: flex; flex-direction: column; gap: 8px; }

  .bar-meta { display: flex; justify-content: space-between; align-items: baseline; }

  .bar-name { font-family: var(--mono); font-size: 12px; color: var(--grey-1); }
  .bar-pct  { font-family: var(--mono); font-size: 11px; color: var(--grey-3); }

  .bar-track { height: 2px; background: var(--border); width: 100%; }

  .bar-fill {
    height: 2px;
    background: var(--white);
    width: 0;
    transition: width 1.4s cubic-bezier(0.16,1,0.3,1);
  }

  /* ── PROJECTS ── */
  .project-card {
    border: 1px solid var(--border);
    padding: 36px 32px;
    margin-bottom: 1px;
    transition: border-color 0.25s, background 0.25s;
    position: relative;
    overflow: hidden;
  }

  .project-card::before {
    content: '';
    position: absolute;
    left: 0; top: 0; bottom: 0;
    width: 2px;
    background: var(--white);
    transform: scaleY(0);
    transform-origin: bottom;
    transition: transform 0.35s cubic-bezier(0.16,1,0.3,1);
  }

  .project-card:hover { border-color: var(--border-light); background: var(--surface); }
  .project-card:hover::before { transform: scaleY(1); }

  .project-number {
    font-family: var(--mono);
    font-size: 10px;
    letter-spacing: 3px;
    color: var(--grey-3);
    text-transform: uppercase;
    margin-bottom: 12px;
  }

  .project-title {
    font-size: 20px;
    font-weight: 600;
    margin-bottom: 10px;
    letter-spacing: -0.5px;
  }

  .project-title a { color: var(--white); text-decoration: none; }
  .project-title a:hover { text-decoration: underline; }

  .project-desc {
    font-size: 14px;
    color: var(--grey-2);
    margin-bottom: 20px;
    line-height: 1.7;
  }

  .project-pipeline {
    font-family: var(--mono);
    font-size: 11px;
    color: var(--grey-3);
    background: var(--near-black);
    border: 1px solid var(--border);
    padding: 16px 20px;
    margin-bottom: 20px;
    line-height: 2;
  }

  .project-stack { display: flex; gap: 8px; flex-wrap: wrap; }

  .stack-tag {
    font-family: var(--mono);
    font-size: 10px;
    letter-spacing: 1px;
    color: var(--grey-3);
    border: 1px solid var(--border);
    padding: 3px 10px;
    text-transform: uppercase;
  }

  /* ── PIPELINE DIAGRAM ── */
  .pipeline {
    display: flex;
    align-items: center;
    gap: 0;
    overflow-x: auto;
    padding: 32px 0;
  }

  .pipe-step {
    flex: 1;
    min-width: 120px;
    text-align: center;
    position: relative;
  }

  .pipe-box {
    border: 1px solid var(--border);
    padding: 16px 12px;
    background: var(--surface);
    transition: background 0.2s, border-color 0.2s;
  }

  .pipe-step:hover .pipe-box { background: var(--surface2); border-color: var(--white); }

  .pipe-icon { font-size: 18px; margin-bottom: 8px; display: block; }

  .pipe-label {
    font-family: var(--mono);
    font-size: 9px;
    letter-spacing: 2px;
    color: var(--grey-2);
    text-transform: uppercase;
    display: block;
  }

  .pipe-arrow {
    color: var(--border-light);
    font-size: 18px;
    padding: 0 4px;
    flex-shrink: 0;
  }

  /* ── STATS GRID ── */
  .stats-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(160px, 1fr)); gap: 1px; background: var(--border); margin-bottom: 40px; }

  .stat-card { background: var(--black); padding: 28px 20px; text-align: center; }

  .stat-num {
    font-size: 36px;
    font-weight: 700;
    letter-spacing: -2px;
    display: block;
    margin-bottom: 6px;
  }

  .stat-lbl {
    font-family: var(--mono);
    font-size: 9px;
    letter-spacing: 3px;
    color: var(--grey-3);
    text-transform: uppercase;
  }

  /* ── CONNECT ── */
  .connect-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(180px, 1fr)); gap: 1px; background: var(--border); }

  .connect-card {
    background: var(--black);
    padding: 28px 24px;
    text-decoration: none;
    color: var(--white);
    display: flex;
    flex-direction: column;
    gap: 12px;
    transition: background 0.2s;
  }

  .connect-card:hover { background: var(--surface); }

  .connect-icon { font-size: 22px; }

  .connect-platform {
    font-family: var(--mono);
    font-size: 9px;
    letter-spacing: 3px;
    color: var(--grey-3);
    text-transform: uppercase;
  }

  .connect-handle {
    font-size: 14px;
    font-weight: 500;
  }

  .connect-arrow {
    font-family: var(--mono);
    font-size: 11px;
    color: var(--grey-3);
    margin-top: auto;
    transition: color 0.2s;
  }

  .connect-card:hover .connect-arrow { color: var(--white); }

  /* ── FOOTER ── */
  .footer {
    padding: 48px 0 0;
    display: flex;
    justify-content: space-between;
    align-items: center;
    flex-wrap: wrap;
    gap: 16px;
  }

  .footer-quote {
    font-family: var(--mono);
    font-size: 12px;
    color: var(--grey-3);
    font-style: italic;
    max-width: 480px;
    line-height: 1.6;
  }

  .footer-id {
    font-family: var(--mono);
    font-size: 10px;
    color: var(--grey-3);
    letter-spacing: 2px;
  }

  /* ── ANIMATIONS ── */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(20px); }
    to   { opacity: 1; transform: translateY(0); }
  }

  .reveal {
    opacity: 0;
    transform: translateY(24px);
    transition: opacity 0.7s ease, transform 0.7s ease;
  }

  .reveal.visible { opacity: 1; transform: translateY(0); }

  /* ── SCROLLBAR ── */
  ::-webkit-scrollbar { width: 4px; }
  ::-webkit-scrollbar-track { background: var(--black); }
  ::-webkit-scrollbar-thumb { background: var(--border-light); }
</style>
</head>
<body>

<canvas id="particles"></canvas>

<div class="content">

  <!-- ══ HERO ══ -->
  <section class="hero">
    <div class="hero-eyebrow">Data Analyst &amp; BI Developer · India</div>

    <h1 class="hero-name"><span>Aman</span></h1>

    <div class="hero-role">
      <span id="typed"></span><span class="cursor"></span>
    </div>

    <div class="hero-tags">
      <span class="tag">Python</span>
      <span class="tag">SQL</span>
      <span class="tag">Power BI</span>
      <span class="tag">DAX</span>
      <span class="tag">Pandas</span>
      <span class="tag">Excel</span>
      <span class="tag">ETL</span>
      <span class="tag">Matplotlib</span>
    </div>

    <div class="hero-links">
      <a href="https://www.linkedin.com/in/amanupa786/" class="btn" target="_blank">↗ LinkedIn</a>
      <a href="https://github.com/amanupa786" class="btn" target="_blank">↗ GitHub</a>
      <a href="https://wa.me/918303333311" class="btn ghost" target="_blank">↗ WhatsApp</a>
      <a href="https://x.com/amanupa786" class="btn ghost" target="_blank">↗ X / Twitter</a>
    </div>
  </section>

  <!-- ══ ABOUT ══ -->
  <section class="section reveal">
    <div class="section-label">About</div>

    <div class="code-block">
<span class="c-kw">class</span> <span class="c-cls">DataAnalyst</span>:<br>
&nbsp;&nbsp;&nbsp;&nbsp;<span class="c-kw">def</span> <span class="c-fn">__init__</span>(self):<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;self.name&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;= <span class="c-str">"Aman"</span><br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;self.username&nbsp;&nbsp; = <span class="c-str">"amanupa786"</span><br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;self.role&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; = <span class="c-str">"Data Analyst &amp; BI Developer"</span><br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;self.stack&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; = [<span class="c-str">"Python"</span>, <span class="c-str">"SQL"</span>, <span class="c-str">"Power BI"</span>, <span class="c-str">"DAX"</span>, <span class="c-str">"Excel"</span>]<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;self.libraries&nbsp; = [<span class="c-str">"Pandas"</span>, <span class="c-str">"NumPy"</span>, <span class="c-str">"Matplotlib"</span>, <span class="c-str">"Seaborn"</span>]<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;self.focus&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; = [<span class="c-str">"Sales Dashboards"</span>, <span class="c-str">"Financial Analysis"</span>,<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="c-str">"Customer Retention"</span>, <span class="c-str">"ETL Pipelines"</span>,<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="c-str">"Automated Reporting"</span>, <span class="c-str">"KPI Systems"</span>]<br>
<br>
&nbsp;&nbsp;&nbsp;&nbsp;<span class="c-kw">def</span> <span class="c-fn">mission</span>(self):<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="c-kw">return</span> <span class="c-str">"Raw data → Clean insights → Business decisions"</span><br>
<br>
<span class="c-cm"># Output: Raw data → Clean insights → Business decisions</span>
    </div>
  </section>

  <!-- ══ PIPELINE ══ -->
  <section class="section reveal">
    <div class="section-label">Data Workflow</div>
    <div class="pipeline">
      <div class="pipe-step">
        <div class="pipe-box">
          <span class="pipe-icon">🗄</span>
          <span class="pipe-label">Extract</span>
        </div>
      </div>
      <div class="pipe-arrow">→</div>
      <div class="pipe-step">
        <div class="pipe-box">
          <span class="pipe-icon">🧹</span>
          <span class="pipe-label">Clean</span>
        </div>
      </div>
      <div class="pipe-arrow">→</div>
      <div class="pipe-step">
        <div class="pipe-box">
          <span class="pipe-icon">🔍</span>
          <span class="pipe-label">Analyze</span>
        </div>
      </div>
      <div class="pipe-arrow">→</div>
      <div class="pipe-step">
        <div class="pipe-box">
          <span class="pipe-icon">📊</span>
          <span class="pipe-label">Visualize</span>
        </div>
      </div>
      <div class="pipe-arrow">→</div>
      <div class="pipe-step">
        <div class="pipe-box">
          <span class="pipe-icon">💡</span>
          <span class="pipe-label">Insights</span>
        </div>
      </div>
    </div>
  </section>

  <!-- ══ SKILLS ══ -->
  <section class="section reveal">
    <div class="section-label">Tech Stack</div>
    <div class="skills-grid">
      <div class="skill-card">
        <div class="skill-category">Languages</div>
        <div class="skill-items">
          <span class="skill-pill">Python</span>
          <span class="skill-pill">SQL</span>
          <span class="skill-pill">DAX</span>
          <span class="skill-pill">M Query</span>
        </div>
      </div>
      <div class="skill-card">
        <div class="skill-category">Libraries</div>
        <div class="skill-items">
          <span class="skill-pill">Pandas</span>
          <span class="skill-pill">NumPy</span>
          <span class="skill-pill">Matplotlib</span>
          <span class="skill-pill">Seaborn</span>
          <span class="skill-pill">Scikit-learn</span>
        </div>
      </div>
      <div class="skill-card">
        <div class="skill-category">BI & Reporting</div>
        <div class="skill-items">
          <span class="skill-pill">Power BI</span>
          <span class="skill-pill">Excel</span>
          <span class="skill-pill">Power Query</span>
          <span class="skill-pill">OpenPyXL</span>
        </div>
      </div>
      <div class="skill-card">
        <div class="skill-category">Tools</div>
        <div class="skill-items">
          <span class="skill-pill">Jupyter</span>
          <span class="skill-pill">VS Code</span>
          <span class="skill-pill">Git</span>
          <span class="skill-pill">GitHub</span>
        </div>
      </div>
    </div>
  </section>

  <!-- ══ PROFICIENCY ══ -->
  <section class="section reveal">
    <div class="section-label">Proficiency</div>
    <div class="bars" id="bars">
      <div class="bar-row">
        <div class="bar-meta"><span class="bar-name">Data Cleaning &amp; ETL</span><span class="bar-pct">95%</span></div>
        <div class="bar-track"><div class="bar-fill" data-w="95"></div></div>
      </div>
      <div class="bar-row">
        <div class="bar-meta"><span class="bar-name">Python &amp; Pandas</span><span class="bar-pct">90%</span></div>
        <div class="bar-track"><div class="bar-fill" data-w="90"></div></div>
      </div>
      <div class="bar-row">
        <div class="bar-meta"><span class="bar-name">SQL (CTEs, Window Functions)</span><span class="bar-pct">85%</span></div>
        <div class="bar-track"><div class="bar-fill" data-w="85"></div></div>
      </div>
      <div class="bar-row">
        <div class="bar-meta"><span class="bar-name">Power BI &amp; DAX</span><span class="bar-pct">82%</span></div>
        <div class="bar-track"><div class="bar-fill" data-w="82"></div></div>
      </div>
      <div class="bar-row">
        <div class="bar-meta"><span class="bar-name">Data Visualization</span><span class="bar-pct">82%</span></div>
        <div class="bar-track"><div class="bar-fill" data-w="82"></div></div>
      </div>
      <div class="bar-row">
        <div class="bar-meta"><span class="bar-name">Excel &amp; Power Query</span><span class="bar-pct">80%</span></div>
        <div class="bar-track"><div class="bar-fill" data-w="80"></div></div>
      </div>
    </div>
  </section>

  <!-- ══ PROJECTS ══ -->
  <section class="section reveal">
    <div class="section-label">Featured Projects</div>

    <div class="project-card">
      <div class="project-number">Project 01</div>
      <div class="project-title">
        <a href="https://github.com/amanupa786/sales-dashboard-analysis" target="_blank">
          Sales Data Cleaning Pipeline ↗
        </a>
      </div>
      <div class="project-desc">
        8-phase end-to-end data cleaning pipeline on a messy sales dataset. Covers every stage of the analyst workflow from raw profiling to formatted Excel report — 30+ Pandas functions applied throughout.
      </div>
      <div class="project-pipeline">
Phase 1 → Profiling &nbsp;&nbsp;&nbsp;&nbsp;Phase 2 → Null Handling &nbsp;&nbsp;&nbsp;Phase 3 → Type Conversion<br>
Phase 4 → Deduplication &nbsp;Phase 5 → Text Standardize &nbsp;Phase 6 → Outlier Detection<br>
Phase 7 → Aggregation &nbsp;&nbsp;Phase 8 → Excel Export (3-sheet formatted workbook)
      </div>
      <div class="project-stack">
        <span class="stack-tag">Python</span>
        <span class="stack-tag">Pandas</span>
        <span class="stack-tag">NumPy</span>
        <span class="stack-tag">OpenPyXL</span>
        <span class="stack-tag">30+ Functions</span>
      </div>
    </div>

    <div class="project-card">
      <div class="project-number">Project 02</div>
      <div class="project-title">
        <a href="https://github.com/amanupa786/ecommerce-orders-analysis" target="_blank">
          E-Commerce Orders Analysis ↗
        </a>
      </div>
      <div class="project-desc">
        7-phase pipeline solving 10 distinct real-world data problems — the most advanced cleaning project in the portfolio. Includes chart generation, Excel embedding, and automated email delivery.
      </div>
      <div class="project-pipeline">
10 Problems Fixed: mixed dates · currency symbols · discount scale bug<br>
country code variants · negative qty · invalid emails · delivery logic<br>
duplicates · multi-column nulls · inconsistent casing<br>
Output → 3 Matplotlib charts embedded in Excel + HTML email via yagmail
      </div>
      <div class="project-stack">
        <span class="stack-tag">Python</span>
        <span class="stack-tag">Pandas</span>
        <span class="stack-tag">Matplotlib</span>
        <span class="stack-tag">OpenPyXL</span>
        <span class="stack-tag">yagmail</span>
        <span class="stack-tag">dotenv</span>
      </div>
    </div>
  </section>

  <!-- ══ STATS ══ -->
  <section class="section reveal">
    <div class="section-label">By The Numbers</div>
    <div class="stats-grid">
      <div class="stat-card">
        <span class="stat-num" data-count="2">0</span>
        <span class="stat-lbl">GitHub Projects</span>
      </div>
      <div class="stat-card">
        <span class="stat-num" data-count="10">0</span>
        <span class="stat-lbl">Data Problems Solved</span>
      </div>
      <div class="stat-card">
        <span class="stat-num" data-count="30">0</span>
        <span class="stat-lbl">Pandas Functions Used</span>
      </div>
      <div class="stat-card">
        <span class="stat-num" data-count="8">0</span>
        <span class="stat-lbl">Pipeline Phases</span>
      </div>
    </div>

    <!-- GitHub Stats Cards -->
    <div style="display:flex;gap:12px;flex-wrap:wrap;justify-content:center;margin-top:8px;">
      <img src="https://github-readme-stats.vercel.app/api?username=amanupa786&show_icons=true&theme=github_dark&hide_border=true&bg_color=111111&title_color=ffffff&text_color=aaaaaa&icon_color=ffffff&count_private=true" style="height:160px;" onerror="this.style.display='none'"/>
      <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=amanupa786&layout=compact&theme=github_dark&hide_border=true&bg_color=111111&title_color=ffffff&text_color=aaaaaa" style="height:160px;" onerror="this.style.display='none'"/>
    </div>
  </section>

  <!-- ══ CONNECT ══ -->
  <section class="section reveal">
    <div class="section-label">Connect</div>
    <div class="connect-grid">
      <a href="https://www.linkedin.com/in/amanupa786/" class="connect-card" target="_blank">
        <span class="connect-icon">💼</span>
        <span class="connect-platform">LinkedIn</span>
        <span class="connect-handle">amanupa786</span>
        <span class="connect-arrow">↗ Open</span>
      </a>
      <a href="https://github.com/amanupa786" class="connect-card" target="_blank">
        <span class="connect-icon">🐙</span>
        <span class="connect-platform">GitHub</span>
        <span class="connect-handle">amanupa786</span>
        <span class="connect-arrow">↗ Open</span>
      </a>
      <a href="https://wa.me/918303333311" class="connect-card" target="_blank">
        <span class="connect-icon">💬</span>
        <span class="connect-platform">WhatsApp</span>
        <span class="connect-handle">+91 83033 33311</span>
        <span class="connect-arrow">↗ Message</span>
      </a>
      <a href="https://x.com/amanupa786" class="connect-card" target="_blank">
        <span class="connect-icon">𝕏</span>
        <span class="connect-platform">X / Twitter</span>
        <span class="connect-handle">@amanupa786</span>
        <span class="connect-arrow">↗ Follow</span>
      </a>
    </div>
  </section>

  <!-- ══ FOOTER ══ -->
  <footer class="footer reveal">
    <p class="footer-quote">"Clean data is not the goal — it's the foundation. The insights come after."</p>
    <span class="footer-id">AMANUPA786 · DATA ANALYST</span>
  </footer>

</div>

<script>
/* ── PARTICLES ── */
const canvas = document.getElementById('particles');
const ctx = canvas.getContext('2d');
let W, H, particles = [];

function resize() {
  W = canvas.width  = window.innerWidth;
  H = canvas.height = window.innerHeight;
}

function mkParticle() {
  return {
    x: Math.random() * W,
    y: Math.random() * H,
    r: Math.random() * 1.2 + 0.3,
    vx: (Math.random() - 0.5) * 0.3,
    vy: (Math.random() - 0.5) * 0.3,
    a: Math.random() * 0.5 + 0.1
  };
}

function initParticles() {
  particles = Array.from({length: 80}, mkParticle);
}

function drawParticles() {
  ctx.clearRect(0, 0, W, H);
  particles.forEach(p => {
    ctx.beginPath();
    ctx.arc(p.x, p.y, p.r, 0, Math.PI * 2);
    ctx.fillStyle = `rgba(255,255,255,${p.a})`;
    ctx.fill();
    p.x += p.vx; p.y += p.vy;
    if (p.x < 0) p.x = W; if (p.x > W) p.x = 0;
    if (p.y < 0) p.y = H; if (p.y > H) p.y = 0;
  });

  // draw connecting lines
  for (let i = 0; i < particles.length; i++) {
    for (let j = i + 1; j < particles.length; j++) {
      const dx = particles[i].x - particles[j].x;
      const dy = particles[i].y - particles[j].y;
      const dist = Math.sqrt(dx*dx + dy*dy);
      if (dist < 100) {
        ctx.beginPath();
        ctx.moveTo(particles[i].x, particles[i].y);
        ctx.lineTo(particles[j].x, particles[j].y);
        ctx.strokeStyle = `rgba(255,255,255,${0.06 * (1 - dist/100)})`;
        ctx.lineWidth = 0.5;
        ctx.stroke();
      }
    }
  }
  requestAnimationFrame(drawParticles);
}

resize(); initParticles(); drawParticles();
window.addEventListener('resize', () => { resize(); initParticles(); });

/* ── TYPING ── */
const phrases = [
  'Python · SQL · Power BI · DAX · Excel',
  'Building Dashboards that Drive Decisions',
  'Turning Messy Data into Clean Insights',
  'Automating Reports & Workflows',
  'Data Analyst · BI Developer · Freelancer'
];
let pi = 0, ci = 0, deleting = false;
const el = document.getElementById('typed');

function type() {
  const phrase = phrases[pi];
  if (!deleting) {
    el.textContent = phrase.slice(0, ++ci);
    if (ci === phrase.length) { deleting = true; setTimeout(type, 2200); return; }
    setTimeout(type, 45);
  } else {
    el.textContent = phrase.slice(0, --ci);
    if (ci === 0) { deleting = false; pi = (pi + 1) % phrases.length; setTimeout(type, 400); return; }
    setTimeout(type, 22);
  }
}
setTimeout(type, 1400);

/* ── SCROLL REVEAL ── */
const reveals = document.querySelectorAll('.reveal');
const observer = new IntersectionObserver(entries => {
  entries.forEach(e => { if (e.isIntersecting) { e.target.classList.add('visible'); observer.unobserve(e.target); } });
}, { threshold: 0.08 });
reveals.forEach(r => observer.observe(r));

/* ── BARS ── */
const barObserver = new IntersectionObserver(entries => {
  entries.forEach(e => {
    if (e.isIntersecting) {
      e.target.querySelectorAll('.bar-fill').forEach(b => {
        b.style.width = b.dataset.w + '%';
      });
      barObserver.unobserve(e.target);
    }
  });
}, { threshold: 0.2 });
document.querySelectorAll('#bars').forEach(b => barObserver.observe(b));

/* ── COUNT UP ── */
const countObserver = new IntersectionObserver(entries => {
  entries.forEach(e => {
    if (e.isIntersecting) {
      e.target.querySelectorAll('[data-count]').forEach(el => {
        const target = +el.dataset.count;
        const suffix = el.dataset.suffix || '';
        let cur = 0;
        const step = Math.ceil(target / 40);
        const t = setInterval(() => {
          cur = Math.min(cur + step, target);
          el.textContent = cur + suffix;
          if (cur >= target) clearInterval(t);
        }, 35);
      });
      countObserver.unobserve(e.target);
    }
  });
}, { threshold: 0.3 });
document.querySelectorAll('.stats-grid').forEach(s => countObserver.observe(s));
</script>
</body>
</html>
