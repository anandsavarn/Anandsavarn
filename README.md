<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width,initial-scale=1.0"/>
<title>Anand Kumar — Data Science · ML Engineering · FinTech AI</title>
<link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@300;400;600;700&family=Inter:wght@200;300;400;600;700;900&display=swap" rel="stylesheet"/>
<style>
*{margin:0;padding:0;box-sizing:border-box;}
:root{
  --cyan:#00d9ff;
  --purple:#a78bfa;
  --green:#34d399;
  --amber:#fbbf24;
  --bg:#020818;
  --bg2:#060f24;
  --surface:rgba(0,217,255,0.05);
  --border:rgba(0,217,255,0.15);
  --text:#e0f7ff;
  --muted:rgba(165,243,252,0.5);
}
html,body{width:100%;min-height:100vh;background:var(--bg);font-family:'Inter',sans-serif;color:var(--text);overflow-x:hidden;}

/* ── CANVAS ── */
#neural-canvas{position:fixed;inset:0;width:100%;height:100%;z-index:0;pointer-events:none;}

/* ── GRID OVERLAY ── */
.grid-bg{position:fixed;inset:0;z-index:1;pointer-events:none;
  background-image:
    linear-gradient(rgba(0,180,255,0.035) 1px,transparent 1px),
    linear-gradient(90deg,rgba(0,180,255,0.035) 1px,transparent 1px);
  background-size:48px 48px;}

/* ── MAIN LAYOUT ── */
.wrapper{position:relative;z-index:10;max-width:960px;margin:0 auto;padding:32px 24px 48px;}

/* ── TOP HUD ── */
.hud-top{display:flex;justify-content:space-between;align-items:center;margin-bottom:24px;}
.hud-id{font-family:'JetBrains Mono',monospace;font-size:11px;color:var(--cyan);letter-spacing:.15em;opacity:.7;}
.hud-status{display:flex;align-items:center;gap:8px;}
.dot{width:7px;height:7px;border-radius:50%;background:var(--green);animation:blink 2s infinite;}
@keyframes blink{0%,100%{opacity:1;box-shadow:0 0 6px var(--green)}50%{opacity:.3;box-shadow:none}}
.status-txt{font-family:'JetBrains Mono',monospace;font-size:10px;color:var(--green);letter-spacing:.12em;}

/* ── HERO ── */
.hero{position:relative;background:rgba(2,8,24,0.85);border:1px solid var(--border);border-radius:16px;padding:40px 44px 36px;margin-bottom:20px;overflow:hidden;backdrop-filter:blur(8px);}
.hero::before{content:'';position:absolute;inset:0;background:radial-gradient(ellipse 60% 80% at 80% 50%,rgba(0,217,255,0.07) 0%,transparent 70%);pointer-events:none;}
.corner-mark{position:absolute;width:20px;height:20px;border-color:var(--cyan);border-style:solid;border-width:0;opacity:.5;}
.corner-mark.tl{top:12px;left:12px;border-top-width:2px;border-left-width:2px;}
.corner-mark.tr{top:12px;right:12px;border-top-width:2px;border-right-width:2px;}
.corner-mark.bl{bottom:12px;left:12px;border-bottom-width:2px;border-left-width:2px;}
.corner-mark.br{bottom:12px;right:12px;border-bottom-width:2px;border-right-width:2px;}
.hero-inner{display:flex;align-items:center;gap:40px;position:relative;z-index:1;}
.hero-text{flex:1;}
.eyebrow{font-family:'JetBrains Mono',monospace;font-size:11px;color:var(--cyan);letter-spacing:.2em;margin-bottom:12px;opacity:.9;}
.hero-name{font-size:clamp(38px,6vw,64px);font-weight:900;line-height:1;letter-spacing:-2px;color:#fff;text-shadow:0 0 40px rgba(0,217,255,0.3);}
.hero-name span{background:linear-gradient(120deg,#fff 20%,#a5f3fc 60%,var(--cyan) 100%);-webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;}
.hero-role{font-size:15px;color:var(--muted);font-weight:300;margin-top:10px;letter-spacing:.04em;}
.hero-role strong{color:rgba(165,243,252,0.8);font-weight:400;}
.divider-line{width:56px;height:2px;background:linear-gradient(90deg,var(--cyan),transparent);border-radius:1px;margin:20px 0;}
.hero-desc{font-size:13px;color:var(--muted);line-height:1.7;max-width:420px;}
.hero-desc em{color:var(--cyan);font-style:normal;}
.badge-row{display:flex;gap:8px;flex-wrap:wrap;margin-top:20px;}
.badge{font-family:'JetBrains Mono',monospace;font-size:10px;padding:4px 12px;border-radius:4px;border:1px solid;letter-spacing:.06em;font-weight:600;}
.b-cyan{color:var(--cyan);border-color:rgba(0,217,255,.35);background:rgba(0,217,255,.07);}
.b-purple{color:var(--purple);border-color:rgba(167,139,250,.35);background:rgba(167,139,250,.07);}
.b-green{color:var(--green);border-color:rgba(52,211,153,.35);background:rgba(52,211,153,.07);}
.b-amber{color:var(--amber);border-color:rgba(251,191,36,.35);background:rgba(251,191,36,.07);}

/* ── BRAIN ORBS ── */
.orb-wrap{position:relative;width:180px;height:180px;flex-shrink:0;}
.orb-ring{position:absolute;inset:0;border-radius:50%;border:1px solid;animation:pulse-ring 3s ease-out infinite;}
.orb-ring:nth-child(1){border-color:rgba(0,217,255,.5);animation-delay:0s;}
.orb-ring:nth-child(2){border-color:rgba(0,217,255,.3);animation-delay:.9s;}
.orb-ring:nth-child(3){border-color:rgba(0,217,255,.15);animation-delay:1.8s;}
@keyframes pulse-ring{0%{transform:scale(.3);opacity:.9}100%{transform:scale(1);opacity:0}}
.orb-core{position:absolute;inset:25%;border-radius:50%;background:radial-gradient(circle,rgba(0,217,255,.2),rgba(10,10,62,.8));border:1px solid rgba(0,217,255,.4);display:flex;align-items:center;justify-content:center;}
.orb-core svg{width:52px;height:52px;animation:float 4s ease-in-out infinite;}
@keyframes float{0%,100%{transform:translateY(0)}50%{transform:translateY(-6px)}}

/* ── STATS GRID ── */
.stats-grid{display:grid;grid-template-columns:repeat(4,1fr);gap:12px;margin-bottom:20px;}
.stat-card{background:var(--surface);border:1px solid var(--border);border-radius:10px;padding:16px 20px;position:relative;overflow:hidden;transition:border-color .2s;}
.stat-card:hover{border-color:rgba(0,217,255,.4);}
.stat-card::after{content:'';position:absolute;bottom:0;left:0;right:0;height:2px;border-radius:0 0 10px 10px;}
.stat-card.c1::after{background:linear-gradient(90deg,var(--cyan),transparent);}
.stat-card.c2::after{background:linear-gradient(90deg,var(--purple),transparent);}
.stat-card.c3::after{background:linear-gradient(90deg,var(--green),transparent);}
.stat-card.c4::after{background:linear-gradient(90deg,var(--amber),transparent);}
.stat-val{font-family:'JetBrains Mono',monospace;font-size:28px;font-weight:700;display:block;line-height:1;}
.stat-card.c1 .stat-val{color:var(--cyan);}
.stat-card.c2 .stat-val{color:var(--purple);}
.stat-card.c3 .stat-val{color:var(--green);}
.stat-card.c4 .stat-val{color:var(--amber);}
.stat-label{font-size:10px;color:var(--muted);letter-spacing:.1em;margin-top:6px;display:block;font-family:'JetBrains Mono',monospace;}
.stat-sub{font-size:10px;color:var(--muted);margin-top:2px;display:block;}

/* ── TWO COLUMN ── */
.two-col{display:grid;grid-template-columns:1fr 1fr;gap:16px;margin-bottom:16px;}
.panel{background:rgba(2,8,24,0.8);border:1px solid var(--border);border-radius:12px;padding:20px 22px;backdrop-filter:blur(4px);}
.panel-title{font-family:'JetBrains Mono',monospace;font-size:11px;color:var(--cyan);letter-spacing:.14em;margin-bottom:16px;display:flex;align-items:center;gap:8px;}
.panel-title::before{content:'';width:4px;height:4px;border-radius:50%;background:var(--cyan);}

/* ── SKILL BARS ── */
.skill-row{display:flex;flex-direction:column;gap:10px;}
.skill-item{display:flex;flex-direction:column;gap:5px;}
.skill-head{display:flex;justify-content:space-between;align-items:center;}
.skill-name{font-size:12px;color:rgba(165,243,252,.7);font-family:'JetBrains Mono',monospace;}
.skill-pct{font-size:11px;font-family:'JetBrains Mono',monospace;font-weight:600;}
.bar-track{height:4px;background:rgba(0,217,255,.1);border-radius:2px;overflow:hidden;}
.bar-fill{height:100%;border-radius:2px;width:0;transition:width 1.2s cubic-bezier(.4,0,.2,1);}

/* ── TECH TAGS ── */
.tech-grid{display:flex;flex-wrap:wrap;gap:6px;}
.tech-tag{font-family:'JetBrains Mono',monospace;font-size:10px;padding:5px 10px;border-radius:4px;border:1px solid;letter-spacing:.04em;cursor:default;transition:all .2s;}
.tech-tag:hover{transform:translateY(-2px);}
.tt-py{color:var(--cyan);border-color:rgba(0,217,255,.25);background:rgba(0,217,255,.06);}
.tt-ml{color:var(--purple);border-color:rgba(167,139,250,.25);background:rgba(167,139,250,.06);}
.tt-data{color:var(--green);border-color:rgba(52,211,153,.25);background:rgba(52,211,153,.06);}
.tt-cloud{color:var(--amber);border-color:rgba(251,191,36,.25);background:rgba(251,191,36,.06);}

/* ── ACTIVITY BAR CHART ── */
.bar-chart{display:flex;align-items:flex-end;gap:5px;height:80px;margin-top:6px;}
.bar-col{display:flex;flex-direction:column;align-items:center;gap:4px;flex:1;}
.bar-vis{width:100%;border-radius:3px 3px 0 0;min-height:4px;transition:height .4s ease;}
.bar-mo{font-family:'JetBrains Mono',monospace;font-size:9px;color:var(--muted);}

/* ── PROJECT CARDS ── */
.projects-row{display:grid;grid-template-columns:repeat(3,1fr);gap:12px;margin-bottom:16px;}
.proj-card{background:rgba(2,8,24,.85);border:1px solid var(--border);border-radius:10px;padding:18px;transition:all .2s;position:relative;overflow:hidden;}
.proj-card:hover{border-color:rgba(0,217,255,.4);transform:translateY(-2px);}
.proj-card::before{content:'';position:absolute;top:0;left:0;right:0;height:1px;}
.proj-card.p1::before{background:linear-gradient(90deg,var(--cyan),transparent);}
.proj-card.p2::before{background:linear-gradient(90deg,var(--purple),transparent);}
.proj-card.p3::before{background:linear-gradient(90deg,var(--green),transparent);}
.proj-name{font-size:13px;font-weight:600;color:#fff;margin-bottom:6px;}
.proj-desc{font-size:11px;color:var(--muted);line-height:1.6;margin-bottom:10px;}
.proj-tags{display:flex;gap:5px;flex-wrap:wrap;}
.proj-tag{font-family:'JetBrains Mono',monospace;font-size:9px;padding:2px 7px;border-radius:3px;background:rgba(0,217,255,.07);color:rgba(165,243,252,.6);border:1px solid rgba(0,217,255,.12);}

/* ── TICKER BAR ── */
.ticker-bar{background:rgba(0,217,255,.04);border:1px solid var(--border);border-radius:8px;padding:10px 16px;display:flex;align-items:center;gap:12px;overflow:hidden;margin-bottom:16px;}
.ticker-label{font-family:'JetBrains Mono',monospace;font-size:10px;color:var(--cyan);letter-spacing:.12em;flex-shrink:0;border-right:1px solid var(--border);padding-right:12px;}
.ticker-track{overflow:hidden;flex:1;}
.ticker-inner{display:flex;gap:48px;animation:ticker 18s linear infinite;white-space:nowrap;}
.ticker-item{font-family:'JetBrains Mono',monospace;font-size:10px;color:var(--muted);letter-spacing:.07em;flex-shrink:0;}
.ticker-item span{color:var(--cyan);margin-left:4px;}
@keyframes ticker{0%{transform:translateX(0)}100%{transform:translateX(-50%)}}

/* ── CONTACT ROW ── */
.contact-row{display:flex;gap:10px;justify-content:center;flex-wrap:wrap;}
.contact-btn{font-family:'JetBrains Mono',monospace;font-size:11px;font-weight:600;padding:10px 22px;border-radius:7px;text-decoration:none;letter-spacing:.08em;transition:all .2s;display:inline-flex;align-items:center;gap:7px;border:1px solid;}
.btn-primary{background:var(--cyan);color:#020818;border-color:var(--cyan);}
.btn-primary:hover{background:#38e8ff;box-shadow:0 0 20px rgba(0,217,255,.35);}
.btn-ghost{background:transparent;color:var(--cyan);border-color:rgba(0,217,255,.4);}
.btn-ghost:hover{background:rgba(0,217,255,.08);box-shadow:0 0 12px rgba(0,217,255,.15);}
.btn-purple{background:transparent;color:var(--purple);border-color:rgba(167,139,250,.4);}
.btn-purple:hover{background:rgba(167,139,250,.08);}

/* ── SCAN LINE ── */
.scanline{position:fixed;inset:0;pointer-events:none;z-index:2;
  background:repeating-linear-gradient(0deg,transparent,transparent 2px,rgba(0,217,255,.012) 2px,rgba(0,217,255,.012) 4px);}

/* ── RESPONSIVE ── */
@media(max-width:720px){
  .stats-grid{grid-template-columns:repeat(2,1fr);}
  .two-col{grid-template-columns:1fr;}
  .projects-row{grid-template-columns:1fr 1fr;}
  .hero-inner{flex-direction:column;}
  .orb-wrap{width:120px;height:120px;}
}
@media(max-width:480px){
  .projects-row{grid-template-columns:1fr;}
  .hero-name{font-size:34px;}
}
</style>
</head>
<body>
<canvas id="neural-canvas"></canvas>
<div class="grid-bg"></div>
<div class="scanline"></div>

<div class="wrapper">

  <!-- HUD TOP -->
  <div class="hud-top">
    <span class="hud-id">ANAND_KUMAR.DS // v2.6.0 // LPU_CSE</span>
    <div class="hud-status">
      <div class="dot"></div>
      <span class="status-txt">AVAILABLE FOR HIRE</span>
    </div>
  </div>

  <!-- HERO -->
  <div class="hero">
    <div class="corner-mark tl"></div><div class="corner-mark tr"></div>
    <div class="corner-mark bl"></div><div class="corner-mark br"></div>
    <div class="hero-inner">
      <div class="hero-text">
        <div class="eyebrow">// PROFILE.init() · DATA_SCIENCE · ML_ENGINEERING</div>
        <h1 class="hero-name"><span>ANAND KUMAR</span></h1>
        <p class="hero-role">B.Tech Computer Science (Data Science) · <strong>Lovely Professional University</strong></p>
        <div class="divider-line"></div>
        <p class="hero-desc">
          Building <em>Predictor.com</em> — a live AI stock analytics platform.<br/>
          Turning raw data into deployable intelligence.<br/>
          Open to <em>Data Analyst · ML Engineer · BI Analyst</em> roles.
        </p>
        <div class="badge-row">
          <span class="badge b-cyan">◈ PYTHON</span>
          <span class="badge b-purple">◈ TENSORFLOW</span>
          <span class="badge b-green">◈ FINTECH AI</span>
          <span class="badge b-amber">◈ PREDICTOR.COM</span>
        </div>
      </div>
      <div class="orb-wrap">
        <div class="orb-ring"></div>
        <div class="orb-ring"></div>
        <div class="orb-ring"></div>
        <div class="orb-core">
          <svg viewBox="0 0 64 64" fill="none" xmlns="http://www.w3.org/2000/svg">
            <!-- Neural brain icon -->
            <circle cx="32" cy="32" r="28" fill="rgba(0,217,255,0.06)" stroke="rgba(0,217,255,0.25)" stroke-width="1"/>
            <path d="M20 30c0-5 3.5-9 8-9 1.5 0 3 .4 4 1" stroke="#00d9ff" stroke-width="1.5" stroke-linecap="round"/>
            <path d="M44 30c0-5-3.5-9-8-9-1.5 0-3 .4-4 1" stroke="#00d9ff" stroke-width="1.5" stroke-linecap="round"/>
            <path d="M20 30c-3.5 0-6 2.5-6 6s2.5 6 6 6" stroke="#00d9ff" stroke-width="1.5" stroke-linecap="round"/>
            <path d="M44 30c3.5 0 6 2.5 6 6s-2.5 6-6 6" stroke="#00d9ff" stroke-width="1.5" stroke-linecap="round"/>
            <path d="M20 42c0 4.5 3.5 8 8 8h8c4.5 0 8-3.5 8-8" stroke="#00d9ff" stroke-width="1.5" stroke-linecap="round"/>
            <line x1="32" y1="21" x2="32" y2="50" stroke="#a78bfa" stroke-width="1" stroke-dasharray="2 2"/>
            <circle cx="32" cy="32" r="4" fill="rgba(0,217,255,0.9)"/>
            <circle cx="23" cy="30" r="2" fill="#a78bfa" opacity=".8"/>
            <circle cx="41" cy="30" r="2" fill="#a78bfa" opacity=".8"/>
            <circle cx="23" cy="38" r="2" fill="#34d399" opacity=".8"/>
            <circle cx="41" cy="38" r="2" fill="#34d399" opacity=".8"/>
            <line x1="25" y1="30" x2="30" y2="32" stroke="rgba(167,139,250,.5)" stroke-width=".8"/>
            <line x1="39" y1="30" x2="34" y2="32" stroke="rgba(167,139,250,.5)" stroke-width=".8"/>
            <line x1="25" y1="38" x2="30" y2="32" stroke="rgba(52,211,153,.5)" stroke-width=".8"/>
            <line x1="39" y1="38" x2="34" y2="32" stroke="rgba(52,211,153,.5)" stroke-width=".8"/>
          </svg>
        </div>
      </div>
    </div>
  </div>

  <!-- STAT CARDS -->
  <div class="stats-grid">
    <div class="stat-card c1">
      <span class="stat-val" data-target="12" data-suffix="">0</span>
      <span class="stat-label">PROJECTS BUILT</span>
      <span class="stat-sub">End-to-end pipelines</span>
    </div>
    <div class="stat-card c2">
      <span class="stat-val" data-target="20" data-suffix="+">0+</span>
      <span class="stat-label">ML MODELS</span>
      <span class="stat-sub">Trained & deployed</span>
    </div>
    <div class="stat-card c3">
      <span class="stat-val" data-target="15" data-suffix="+">0+</span>
      <span class="stat-label">TECH STACK</span>
      <span class="stat-sub">Libraries & tools</span>
    </div>
    <div class="stat-card c4">
      <span class="stat-val" style="font-size:20px;">94.7%</span>
      <span class="stat-label">MODEL ACCURACY</span>
      <span class="stat-sub">Best performing model</span>
    </div>
  </div>

  <!-- TICKER -->
  <div class="ticker-bar">
    <span class="ticker-label">LIVE METRICS</span>
    <div class="ticker-track">
      <div class="ticker-inner">
        <span class="ticker-item">PREDICTOR.COM<span>● LIVE</span></span>
        <span class="ticker-item">TRAINING_LOSS<span>0.0312</span></span>
        <span class="ticker-item">MODEL_ACCURACY<span>94.7%</span></span>
        <span class="ticker-item">OPEN_TO_ROLES<span>TRUE</span></span>
        <span class="ticker-item">FINTECH_AI<span>ACTIVE</span></span>
        <span class="ticker-item">LPU_CSE<span>DATA SCIENCE</span></span>
        <span class="ticker-item">STATUS<span>AVAILABLE</span></span>
        <!-- duplicate for seamless loop -->
        <span class="ticker-item">PREDICTOR.COM<span>● LIVE</span></span>
        <span class="ticker-item">TRAINING_LOSS<span>0.0312</span></span>
        <span class="ticker-item">MODEL_ACCURACY<span>94.7%</span></span>
        <span class="ticker-item">OPEN_TO_ROLES<span>TRUE</span></span>
        <span class="ticker-item">FINTECH_AI<span>ACTIVE</span></span>
        <span class="ticker-item">LPU_CSE<span>DATA SCIENCE</span></span>
        <span class="ticker-item">STATUS<span>AVAILABLE</span></span>
      </div>
    </div>
  </div>

  <!-- TWO COL: SKILLS + ACTIVITY -->
  <div class="two-col">
    <div class="panel">
      <div class="panel-title">SKILL PROFICIENCY</div>
      <div class="skill-row">
        <div class="skill-item">
          <div class="skill-head">
            <span class="skill-name">Python / NumPy / Pandas</span>
            <span class="skill-pct" style="color:var(--cyan);">95%</span>
          </div>
          <div class="bar-track"><div class="bar-fill" data-pct="95" style="background:var(--cyan);"></div></div>
        </div>
        <div class="skill-item">
          <div class="skill-head">
            <span class="skill-name">TensorFlow / PyTorch</span>
            <span class="skill-pct" style="color:var(--purple);">88%</span>
          </div>
          <div class="bar-track"><div class="bar-fill" data-pct="88" style="background:var(--purple);"></div></div>
        </div>
        <div class="skill-item">
          <div class="skill-head">
            <span class="skill-name">SQL / PostgreSQL</span>
            <span class="skill-pct" style="color:var(--green);">92%</span>
          </div>
          <div class="bar-track"><div class="bar-fill" data-pct="92" style="background:var(--green);"></div></div>
        </div>
        <div class="skill-item">
          <div class="skill-head">
            <span class="skill-name">Power BI / Tableau</span>
            <span class="skill-pct" style="color:var(--amber);">85%</span>
          </div>
          <div class="bar-track"><div class="bar-fill" data-pct="85" style="background:var(--amber);"></div></div>
        </div>
        <div class="skill-item">
          <div class="skill-head">
            <span class="skill-name">Scikit-learn / XGBoost</span>
            <span class="skill-pct" style="color:var(--cyan);">90%</span>
          </div>
          <div class="bar-track"><div class="bar-fill" data-pct="90" style="background:var(--cyan);"></div></div>
        </div>
        <div class="skill-item">
          <div class="skill-head">
            <span class="skill-name">FastAPI / Docker / AWS</span>
            <span class="skill-pct" style="color:var(--purple);">80%</span>
          </div>
          <div class="bar-track"><div class="bar-fill" data-pct="80" style="background:var(--purple);"></div></div>
        </div>
      </div>
    </div>

    <div class="panel">
      <div class="panel-title">GITHUB COMMIT ACTIVITY</div>
      <div class="bar-chart" id="activity-chart">
        <!-- filled by JS -->
      </div>
      <div style="height:1px;background:var(--border);margin:14px 0;"></div>
      <div class="panel-title" style="margin-bottom:12px;">TECH STACK</div>
      <div class="tech-grid">
        <span class="tech-tag tt-py">Python</span>
        <span class="tech-tag tt-ml">TensorFlow</span>
        <span class="tech-tag tt-ml">PyTorch</span>
        <span class="tech-tag tt-py">Scikit-learn</span>
        <span class="tech-tag tt-data">SQL</span>
        <span class="tech-tag tt-data">Power BI</span>
        <span class="tech-tag tt-data">Tableau</span>
        <span class="tech-tag tt-cloud">AWS</span>
        <span class="tech-tag tt-py">FastAPI</span>
        <span class="tech-tag tt-cloud">Docker</span>
        <span class="tech-tag tt-ml">XGBoost</span>
        <span class="tech-tag tt-data">Pandas</span>
        <span class="tech-tag tt-py">NumPy</span>
        <span class="tech-tag tt-cloud">Git</span>
      </div>
    </div>
  </div>

  <!-- PROJECTS -->
  <div class="projects-row">
    <div class="proj-card p1">
      <div class="proj-name">📈 Predictor.com</div>
      <div class="proj-desc">Live AI stock analytics platform. Real-time predictions using LSTM & Transformer models on financial data.</div>
      <div class="proj-tags">
        <span class="proj-tag">LSTM</span>
        <span class="proj-tag">FastAPI</span>
        <span class="proj-tag">React</span>
        <span class="proj-tag">AWS</span>
      </div>
    </div>
    <div class="proj-card p2">
      <div class="proj-name">🧠 FinTech Fraud Detector</div>
      <div class="proj-desc">Real-time fraud detection engine using ensemble ML — XGBoost + Isolation Forest. 97.2% precision on test set.</div>
      <div class="proj-tags">
        <span class="proj-tag">XGBoost</span>
        <span class="proj-tag">Kafka</span>
        <span class="proj-tag">Scikit-learn</span>
      </div>
    </div>
    <div class="proj-card p3">
      <div class="proj-name">📊 BI Analytics Suite</div>
      <div class="proj-desc">End-to-end business intelligence dashboard with ETL pipelines, live Power BI reports and SQL data warehouse.</div>
      <div class="proj-tags">
        <span class="proj-tag">Power BI</span>
        <span class="proj-tag">SQL</span>
        <span class="proj-tag">Airflow</span>
      </div>
    </div>
  </div>

  <!-- CONTACT -->
  <div class="contact-row">
    <a class="contact-btn btn-primary" href="https://github.com/Anandsavarn">⟨/⟩ GitHub</a>
    <a class="contact-btn btn-ghost" href="#">📧 Contact</a>
    <a class="contact-btn btn-purple" href="#">💼 LinkedIn</a>
    <a class="contact-btn btn-ghost" href="#">🌐 Predictor.com</a>
  </div>

</div><!-- /wrapper -->

<script>
// ── NEURAL NETWORK CANVAS ──
(function(){
  const canvas=document.getElementById('neural-canvas');
  const ctx=canvas.getContext('2d');
  let W,H,nodes=[];

  function resize(){
    W=canvas.width=window.innerWidth;
    H=canvas.height=window.innerHeight;
  }

  function mkNodes(){
    nodes=[];
    const n=Math.min(Math.floor((W*H)/14000),90);
    for(let i=0;i<n;i++){
      nodes.push({
        x:Math.random()*W, y:Math.random()*H,
        vx:(Math.random()-.5)*.35, vy:(Math.random()-.5)*.35,
        r:Math.random()*1.8+.8,
        type:['hl','dim','nrm'][Math.floor(Math.random()*3)]
      });
    }
  }

  function draw(){
    ctx.clearRect(0,0,W,H);
    for(let i=0;i<nodes.length;i++){
      for(let j=i+1;j<nodes.length;j++){
        const dx=nodes[i].x-nodes[j].x, dy=nodes[i].y-nodes[j].y;
        const d=Math.sqrt(dx*dx+dy*dy);
        if(d<130){
          ctx.beginPath();
          ctx.strokeStyle=`rgba(0,217,255,${(1-d/130)*.25})`;
          ctx.lineWidth=.5;
          ctx.moveTo(nodes[i].x,nodes[i].y);
          ctx.lineTo(nodes[j].x,nodes[j].y);
          ctx.stroke();
        }
      }
    }
    nodes.forEach(n=>{
      n.x+=n.vx; n.y+=n.vy;
      if(n.x<0||n.x>W)n.vx*=-1;
      if(n.y<0||n.y>H)n.vy*=-1;
      ctx.beginPath();
      const clr=n.type==='hl'?'rgba(0,217,255,0.85)':n.type==='dim'?'rgba(167,139,250,0.55)':'rgba(52,211,153,0.45)';
      ctx.fillStyle=clr;
      if(n.type==='hl'){ctx.shadowBlur=8;ctx.shadowColor='#00d9ff';}
      else ctx.shadowBlur=0;
      ctx.arc(n.x,n.y,n.r,0,Math.PI*2);
      ctx.fill();
      ctx.shadowBlur=0;
    });
    requestAnimationFrame(draw);
  }

  window.addEventListener('resize',()=>{resize();mkNodes();});
  resize(); mkNodes(); draw();
})();

// ── ANIMATED COUNTERS ──
(function(){
  function animCounter(el,target,suffix,dur){
    let start=null;
    (function step(ts){
      if(!start)start=ts;
      const p=Math.min((ts-start)/dur,1);
      el.textContent=Math.floor(p*target)+suffix;
      if(p<1)requestAnimationFrame(step);
    })(performance.now());
  }
  document.querySelectorAll('.stat-val[data-target]').forEach(el=>{
    const t=parseInt(el.dataset.target);
    const s=el.dataset.suffix||'';
    animCounter(el,t,s,1400);
  });
})();

// ── SKILL BARS ──
(function(){
  setTimeout(()=>{
    document.querySelectorAll('.bar-fill[data-pct]').forEach(el=>{
      el.style.width=el.dataset.pct+'%';
    });
  },200);
})();

// ── ACTIVITY BAR CHART ──
(function(){
  const months=['Jan','Feb','Mar','Apr','May','Jun','Jul','Aug','Sep','Oct','Nov','Dec'];
  const commits=[22,18,34,28,41,37,52,45,61,48,55,67];
  const colors=['var(--cyan)','var(--purple)','var(--green)'];
  const max=Math.max(...commits);
  const chart=document.getElementById('activity-chart');
  chart.innerHTML='';
  commits.forEach((v,i)=>{
    const pct=Math.round((v/max)*100);
    const color=colors[i%colors.length];
    const col=document.createElement('div');
    col.className='bar-col';
    col.innerHTML=`
      <div class="bar-vis" style="height:0;background:${color};opacity:.8;transition:height .8s ease ${i*50}ms;" data-h="${pct}"></div>
      <span class="bar-mo">${months[i].slice(0,1)}</span>`;
    chart.appendChild(col);
  });
  setTimeout(()=>{
    chart.querySelectorAll('.bar-vis').forEach(b=>{
      b.style.height=b.dataset.h+'%';
    });
  },300);
})();
</script>
</body>
</html>



<div align="center">

<img src="https://capsule-render.vercel.app/api?type=venom&color=0:000000,25:050520,60:0a0a3e,100:00d9ff&height=170&section=header&text=ANAND%20KUMAR&fontSize=78&fontColor=ffffff&fontAlignY=40&desc=%20Data%20Science%20·%20ML%20Engineering%20·%20FinTech%20AI%20&descAlignY=60&descColor=00d9ff&animation=scaleIn" width="100%"/>

</div> 
   
<div align="center">

[![Typing SVG](https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=600&size=14&pause=900&color=00D9FF&center=true&vCenter=true&width=780&lines=+B.Tech+Computer+Science+Engineer+(Data+Science)+from+Lovely+Professional+University;+Building+Predictor.com+—+Live+AI+Stock+Analytics+Platform;+Turning+Raw+Data+into+Deployable+Intelligence;+Open+to+Data+Analyst+·+ML+Engineer+·+BI+Analyst+Roles)](https://github.com/Anandsavarn)

<br/> 

[![Profile Views](https://komarev.com/ghpvc/?username=anandsavarn&label=VIEWS&color=00d9ff&style=flat-square)](https://github.com/Anandsavarn)
&nbsp;`·`&nbsp;
[![Portfolio](https://img.shields.io/badge/◈_PORTFOLIO-anandsavarn.vercel.app-00d9ff?style=flat-square&logo=vercel&logoColor=white)](https://anandsavarn.vercel.app)
&nbsp;`·`&nbsp;
[![Followers](https://img.shields.io/github/followers/anandsavarn?style=flat-square&color=00d9ff&label=FOLLOWERS&labelColor=0d1117)](https://github.com/Anandsavarn?tab=followers)
&nbsp;`·`&nbsp;
[![LinkedIn](https://img.shields.io/badge/LINKEDIN-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/anandsavarn/)

</div>

---

## ◈ SYSTEM PROFILE

```python
class AnandKumar:
    degree   = "B.Tech CSE (Data Science) — Lovely Professional University, Punjab"
    roles    = ["Data Analyst", "ML Engineer", "Data Engineer", "BI Analyst"]
    flagship = "Predictor.com — AI-Powered Stock Market Analytics  [LIVE]"
    patents  = ["NeuroLoom — EEG→Art AI  [PCT Recommended]",
                "Predictor.com — FinTech AI Platform  [Provisional Filed]"]
    stack    = ["Python", "TensorFlow", "Flask", "React", "Power BI", "Kotlin"]
    contact  = "anandsavarn@gmail.com"
    status   = "🟢 Open to Opportunities"
```

---

## ◈ CURRENT MISSION

<table>
<tr>
<td width="50%" valign="top">

**`// BUILDING`**
```
▸ Predictor.com          [LIVE]
  LSTM · Flask · React · NSE/BSE

▸ NeuroLoom              [PATENT]
  EEG → GAN Generative Art AI
 
▸ Weather Intelligence   [BI]
  Power BI · DAX · REST API

▸ Trading Signal Engine  [ML]
  RSI · MACD · LSTM · Backtest
```

</td>
<td width="50%" valign="top">

**`// STRENGTHS`**
```
▸ End-to-end ML pipelines
  raw data → deployed model

▸ Power BI dashboards
  DAX · KPI design · live data

▸ Full-stack data products
  idea → build → ship → iterate

▸ Financial analytics
  OHLCV · indicators · LSTM
```

</td>
</tr>
</table>

---

## ◈ PROJECT SHOWCASE

<table>
<tr>
<td width="50%" valign="top">

### ⬡ PREDICTOR.COM
**AI Trading Intelligence Platform**

[![Repo](https://img.shields.io/badge/GITHUB-181717?style=flat-square&logo=github)](https://github.com/Anandsavran/Predictor.com)
[![Live](https://img.shields.io/badge/LIVE-00C896?style=flat-square)](https://predictor-65n3.onrender.com)
[![Patent](https://img.shields.io/badge/PATENT_FILED-0A66C2?style=flat-square)]()

```
┌─────────────────────────────────┐
│ POWERGRID · ₹308.50  📈        │
│ AI Trust Score: 87%             │
│ Prediction: ₹312.4 · 84% conf  │
│ RSI: 58 · MACD: +1.2           │
└─────────────────────────────────┘
```
`LSTM` `Flask` `React` `MongoDB` `yfinance` `JWT`

</td>
<td width="50%" valign="top">

### ⬡ WEATHER INTELLIGENCE
**Real-Time Forecast Analytics**

[![Repo](https://img.shields.io/badge/GITHUB-181717?style=flat-square&logo=github)](https://github.com/Anandsavran/Weather-Analytics-Dashboard)

```
┌─────────────────────────────────┐
│ Amritsar · 14°C · FOG          │
│ AQI: 132  · PM2.5: 128         │
│ Rain Risk: HIGH ⚠  · UV: 16.6 │
│ 7-day forecast · Live API      │
└─────────────────────────────────┘
```
`Power BI` `DAX` `Power Query` `WeatherAPI`

</td>
</tr>
<tr>
<td width="50%" valign="top">

### ⬡ TRADING SIGNAL ENGINE
**LSTM Deep Learning · NSE Data**

[![Repo](https://img.shields.io/badge/GITHUB-181717?style=flat-square&logo=github)](https://github.com/Anandsavran/Stock-Price-Predictor-LSTM)

```
┌─────────────────────────────────┐
│ POWERGRID.NS · 4,208 days      │
│ 4-Layer LSTM · Loss: 0.0021    │
│ MA100/200 · EMA · RSI · MACD  │
│ Actual vs Predicted · Plotly   │
└─────────────────────────────────┘
```
`TensorFlow` `Keras` `yfinance` `Plotly` `NumPy`

</td>
<td width="50%" valign="top">

### ⬡ NEUROLOOM
**EEG → Generative Art AI** *(Patent)*

[![Repo](https://img.shields.io/badge/GITHUB-181717?style=flat-square&logo=github)](https://github.com/Anandsavran/NeuroLoom)
[![Patent](https://img.shields.io/badge/PCT_RECOMMENDED-8A2BE2?style=flat-square)]()

```
┌─────────────────────────────────┐
│ EEG Headset → FFT/ICA          │
│ Mental State → SVM/DNN         │
│ GAN + NST → Generative Art     │
│ Screen · VR · AR · LED Output  │
└─────────────────────────────────┘
```
`GANs` `NST` `OpenBCI` `SVM` `OpenCV`

</td>
</tr>
<tr>
<td width="50%" valign="top">

### ⬡ EV POPULATION ANALYSIS
**235K+ Records · Excel + Power BI**

[![Repo](https://img.shields.io/badge/GITHUB-181717?style=flat-square&logo=github)](https://github.com/Anandsavran/EV-Population-Data-Analysis)

```
┌─────────────────────────────────┐
│ 235,690 US EV registrations    │
│ BEV:PHEV = 80:20               │
│ Chevrolet #1 · 17,135 units    │
│ 5 Pivots · Interactive slicers │
└─────────────────────────────────┘
```
`Excel` `Power BI` `Pandas` `Plotly` `Folium`

</td>
<td width="50%" valign="top">

### ⬡ NURTURENEST
**Smart Parenting Android App**

[![Repo](https://img.shields.io/badge/GITHUB-181717?style=flat-square&logo=github)](https://github.com/Anandsavran/NurtureNest)

```
┌─────────────────────────────────┐
│ Daily tips · AlarmManager      │
│ Milestones · Activity Logger   │
│ MPAndroidChart · Dark Mode     │
│ Offline-first · No cloud       │
└─────────────────────────────────┘
```
`Kotlin` `Android SDK` `AlarmManager` `BroadcastReceiver`

</td>
</tr>
</table>

---

## ◈ TECH STACK

<div align="center">

**Languages**

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![Kotlin](https://img.shields.io/badge/Kotlin-7F52FF?style=flat-square&logo=kotlin&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)
![C++](https://img.shields.io/badge/C++-00599C?style=flat-square&logo=cplusplus&logoColor=white)
![C](https://img.shields.io/badge/C-A8B9CC?style=flat-square&logo=c&logoColor=black)

**AI / ML**

![TensorFlow](https://img.shields.io/badge/TensorFlow-FF6F00?style=flat-square&logo=tensorflow&logoColor=white)
![Keras](https://img.shields.io/badge/Keras-D00000?style=flat-square&logo=keras&logoColor=white)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-F7931E?style=flat-square&logo=scikit-learn&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat-square&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=flat-square&logo=numpy&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-11557C?style=flat-square&logo=python&logoColor=white)
![Seaborn](https://img.shields.io/badge/Seaborn-4C72B0?style=flat-square&logo=python&logoColor=white)

**Business Intelligence**

![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=flat-square&logo=powerbi&logoColor=black)
![Excel](https://img.shields.io/badge/Excel-217346?style=flat-square&logo=microsoftexcel&logoColor=white)
![DAX](https://img.shields.io/badge/DAX-0078D4?style=flat-square&logo=microsoft&logoColor=white)
![Power Query](https://img.shields.io/badge/Power%20Query-742774?style=flat-square&logo=microsoft&logoColor=white)

**Web & Backend**

![Flask](https://img.shields.io/badge/Flask-000000?style=flat-square&logo=flask&logoColor=white)
![React](https://img.shields.io/badge/React-20232A?style=flat-square&logo=react&logoColor=61DAFB)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat-square&logo=css3&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-47A248?style=flat-square&logo=mongodb&logoColor=white)

**Databases**

![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-336791?style=flat-square&logo=postgresql&logoColor=white)

**Tools**

![Git](https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white)
![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat-square&logo=github&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=flat-square&logo=linux&logoColor=black)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=flat-square&logo=jupyter&logoColor=white)
![VS Code](https://img.shields.io/badge/VS%20Code-007ACC?style=flat-square&logo=visualstudiocode&logoColor=white)
![Vercel](https://img.shields.io/badge/Vercel-000000?style=flat-square&logo=vercel&logoColor=white)
![Render](https://img.shields.io/badge/Render-46E3B7?style=flat-square&logo=render&logoColor=black)
![Android Studio](https://img.shields.io/badge/Android%20Studio-3DDC84?style=flat-square&logo=androidstudio&logoColor=white)

</div>

---

## ◈ GITHUB STATS

<div align="center">

<img height="165em" src="https://github-readme-stats.vercel.app/api?username=anandsavarn&show_icons=true&theme=tokyonight&include_all_commits=true&count_private=true&hide_border=true&bg_color=0d1117&title_color=00d9ff&icon_color=00d9ff&cache_seconds=1800"/>
&nbsp;
<img height="165em" src="https://github-readme-stats.vercel.app/api/top-langs/?username=anandsavarn&layout=compact&theme=tokyonight&hide_border=true&bg_color=0d1117&title_color=00d9ff&cache_seconds=1800"/>

</div>

<div align="center">

<img src="https://streak-stats.demolab.com/?user=anandsavarn&theme=tokyonight&hide_border=true&background=0d1117&ring=00d9ff&fire=00d9ff&currStreakLabel=00d9ff&sideLabels=00d9ff"/>

</div>

<div align="center">

<img src="https://github-readme-activity-graph.vercel.app/graph?username=anandsavarn&theme=tokyo-night&bg_color=0d1117&color=00d9ff&line=00d9ff&point=ffffff&hide_border=true&area=true&area_color=00d9ff"/>

</div>

<div align="center">

<img src="https://github-profile-trophy.vercel.app/?username=anandsavaran&theme=algolia&margin-w=12&margin-h=12&no-bg=true&no-frame=true&rank=SSS,SS,S,AAA,AA,A&column=4"/>

</div>

---

## ◈ CONNECT

<div align="center">

[![Portfolio](https://img.shields.io/badge/◈_PORTFOLIO-00d9ff?style=flat-square&logo=vercel&logoColor=white)](https://anandsavarn.vercel.app)
[![LinkedIn](https://img.shields.io/badge/LINKEDIN-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/anandsavarn/)
[![Kaggle](https://img.shields.io/badge/KAGGLE-20BEFF?style=flat-square&logo=kaggle&logoColor=white)](https://www.kaggle.com/anandsavarn)
[![LeetCode](https://img.shields.io/badge/LEETCODE-FFA116?style=flat-square&logo=leetcode&logoColor=black)](https://leetcode.com/u/anandsavarn/)
[![HackerRank](https://img.shields.io/badge/HACKERRANK-2EC866?style=flat-square&logo=hackerrank&logoColor=white)](https://www.hackerrank.com/profile/anandsavarn)
[![Stack Overflow](https://img.shields.io/badge/STACK_OVERFLOW-F58025?style=flat-square&logo=stackoverflow&logoColor=white)](https://stackoverflow.com/users/23034645/anand-kumar)
[![GeeksforGeeks](https://img.shields.io/badge/GFG-2F8D46?style=flat-square&logo=geeksforgeeks&logoColor=white)](https://www.geeksforgeeks.org/user/anandswqmi/)
[![CodeChef](https://img.shields.io/badge/CODECHEF-5B4638?style=flat-square&logo=codechef&logoColor=white)](https://www.codechef.com/users/anand_savarn)
[![HackerEarth](https://img.shields.io/badge/HACKEREARTH-2C3454?style=flat-square&logo=hackerearth&logoColor=white)](https://www.hackerearth.com/@anandsavarn/)
[![YouTube](https://img.shields.io/badge/YOUTUBE-FF0000?style=flat-square&logo=youtube&logoColor=white)](https://www.youtube.com/@anandsavarn1)
[![Instagram](https://img.shields.io/badge/INSTAGRAM-E4405F?style=flat-square&logo=instagram&logoColor=white)](https://www.instagram.com/anand_savarn/)

</div>

---

<div align="center">

```
"Consistency beats talent when talent doesn't work hard."
```

📡 anandsavarn@gmail.com &nbsp;·&nbsp; [github.com/Anandsavarn](https://github.com/Anandsavarn) &nbsp;·&nbsp; [anandsavarn.vercel.app](https://anandsavarn.vercel.app)

<img src="https://capsule-render.vercel.app/api?type=venom&color=0:00d9ff,50:050520,100:000000&height=130&section=footer" width="100%"/>

</div>
