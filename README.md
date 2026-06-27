<div align="center">

<!-- ANIMATED NAME BACKGROUND using capsule-render + SVG animation -->

![header](https://capsule-render.vercel.app/api?type=venom&color=0:000000,25:050520,60:0a0a3e,100:00d9ff&height=200&section=header&text=ANAND%20KUMAR&fontSize=80&fontColor=ffffff&fontAlignY=45&desc=Data%20Science%20·%20ML%20Engineering%20·%20FinTech%20AI&descAlignY=65&descColor=00d9ff&animation=scaleIn)

</div>

---

<!-- OPTION 2: Pure SVG animated name (works on GitHub) -->
<!-- Replace the capsule-render above with this SVG block if you want a custom look -->

<!--
<div align="center">
<svg width="860" height="200" viewBox="0 0 860 200" xmlns="http://www.w3.org/2000/svg">
  <defs>
    <linearGradient id="bg" x1="0%" y1="0%" x2="100%" y2="100%">
      <stop offset="0%" style="stop-color:#000000"/>
      <stop offset="40%" style="stop-color:#050520"/>
      <stop offset="100%" style="stop-color:#0a0a3e"/>
    </linearGradient>
    <filter id="glow">
      <feGaussianBlur stdDeviation="4" result="coloredBlur"/>
      <feMerge><feMergeNode in="coloredBlur"/><feMergeNode in="SourceGraphic"/></feMerge>
    </filter>
    <style>
      .name { font-family: 'Segoe UI', Arial, sans-serif; font-size: 64px; font-weight: 800; fill: #ffffff; letter-spacing: 6px; }
      .sub  { font-family: 'Segoe UI', Arial, sans-serif; font-size: 15px; font-weight: 400; fill: #00d9ff; letter-spacing: 3px; }
      .dot  { fill: #00d9ff; }
      .ring { fill: none; stroke: #00d9ff; stroke-width: 1; opacity: 0.4; }
      @keyframes pulse { 0%,100%{opacity:0.2;r:4} 50%{opacity:1;r:7} }
      @keyframes spin  { from{transform:rotate(0deg)} to{transform:rotate(360deg)} }
      @keyframes fade  { 0%,100%{opacity:0.1} 50%{opacity:0.6} }
      .n1 { animation: pulse 2.0s ease-in-out infinite; }
      .n2 { animation: pulse 2.4s ease-in-out infinite 0.3s; }
      .n3 { animation: pulse 1.8s ease-in-out infinite 0.7s; }
      .n4 { animation: pulse 2.2s ease-in-out infinite 1.1s; }
      .n5 { animation: pulse 2.6s ease-in-out infinite 0.5s; }
      .n6 { animation: pulse 1.9s ease-in-out infinite 1.4s; }
      .orb { transform-origin: 430px 100px; animation: spin 12s linear infinite; }
      .orb2{ transform-origin: 430px 100px; animation: spin 20s linear infinite reverse; }
      .ln  { stroke: #00d9ff; stroke-width: 0.5; opacity: 0; animation: fade 3s ease-in-out infinite; }
      .ln2 { animation: fade 4s ease-in-out infinite 1s; }
      .ln3 { animation: fade 3.5s ease-in-out infinite 2s; }
    </style>
  </defs>

  <!-- Background -->
  <rect width="860" height="200" fill="url(#bg)" rx="12"/>

  <!-- Grid lines -->
  <line x1="0" y1="40"  x2="860" y2="40"  stroke="#00d9ff" stroke-width="0.3" opacity="0.07"/>
  <line x1="0" y1="80"  x2="860" y2="80"  stroke="#00d9ff" stroke-width="0.3" opacity="0.07"/>
  <line x1="0" y1="120" x2="860" y2="120" stroke="#00d9ff" stroke-width="0.3" opacity="0.07"/>
  <line x1="0" y1="160" x2="860" y2="160" stroke="#00d9ff" stroke-width="0.3" opacity="0.07"/>
  <line x1="172" y1="0" x2="172" y2="200" stroke="#00d9ff" stroke-width="0.3" opacity="0.07"/>
  <line x1="344" y1="0" x2="344" y2="200" stroke="#00d9ff" stroke-width="0.3" opacity="0.07"/>
  <line x1="516" y1="0" x2="516" y2="200" stroke="#00d9ff" stroke-width="0.3" opacity="0.07"/>
  <line x1="688" y1="0" x2="688" y2="200" stroke="#00d9ff" stroke-width="0.3" opacity="0.07"/>

  <!-- Neural network edges -->
  <line x1="60"  y1="30"  x2="160" y2="80"  class="ln"  stroke="#00d9ff" stroke-width="0.5"/>
  <line x1="160" y1="80"  x2="280" y2="50"  class="ln2" stroke="#7c3aed" stroke-width="0.5"/>
  <line x1="280" y1="50"  x2="380" y2="120" class="ln3" stroke="#00d9ff" stroke-width="0.5"/>
  <line x1="800" y1="30"  x2="700" y2="90"  class="ln"  stroke="#7c3aed" stroke-width="0.5"/>
  <line x1="700" y1="90"  x2="600" y2="50"  class="ln2" stroke="#00d9ff" stroke-width="0.5"/>
  <line x1="600" y1="50"  x2="480" y2="120" class="ln3" stroke="#7c3aed" stroke-width="0.5"/>
  <line x1="60"  y1="170" x2="160" y2="130" class="ln2" stroke="#7c3aed" stroke-width="0.5"/>
  <line x1="800" y1="170" x2="700" y2="130" class="ln3" stroke="#00d9ff" stroke-width="0.5"/>

  <!-- Neural nodes left side -->
  <circle cx="60"  cy="30"  class="n1 dot" r="4"/>
  <circle cx="160" cy="80"  class="n2 dot" r="4"/>
  <circle cx="280" cy="50"  class="n3 dot" r="4"/>
  <circle cx="60"  cy="170" class="n4 dot" r="4"/>
  <circle cx="160" cy="130" class="n5 dot" r="4"/>

  <!-- Neural nodes right side -->
  <circle cx="800" cy="30"  class="n2 dot" r="4"/>
  <circle cx="700" cy="90"  class="n3 dot" r="4"/>
  <circle cx="600" cy="50"  class="n1 dot" r="4"/>
  <circle cx="800" cy="170" class="n5 dot" r="4"/>
  <circle cx="700" cy="130" class="n6 dot" r="4"/>

  <!-- Orbiting rings around center -->
  <g class="orb">
    <ellipse cx="430" cy="100" rx="320" ry="30" class="ring"/>
  </g>
  <g class="orb2">
    <ellipse cx="430" cy="100" rx="260" ry="18" class="ring" opacity="0.2"/>
  </g>

  <!-- Main name text with glow -->
  <text x="430" y="112" text-anchor="middle" class="name" filter="url(#glow)">ANAND KUMAR</text>

  <!-- Subtitle -->
  <text x="430" y="148" text-anchor="middle" class="sub">DATA SCIENCE · ML ENGINEERING · FINTECH AI</text>
</svg>
</div>
-->

---

<div align="center">

[![Typing SVG](https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=600&size=14&pause=900&color=00D9FF&center=true&vCenter=true&width=780&lines=B.Tech+Computer+Science+Engineer+(Data+Science)+from+Lovely+Professional+University;Building+Predictor.com+%E2%80%94+Live+AI+Stock+Analytics+Platform;Turning+Raw+Data+into+Deployable+Intelligence;Open+to+Data+Analyst+%C2%B7+ML+Engineer+%C2%B7+BI+Analyst+Roles)](https://github.com/Anandsavarn)

<br/>

[![Profile Views](https://komarev.com/ghpvc/?username=anandsavarn&label=VIEWS&color=00d9ff&style=flat-square)](https://github.com/Anandsavarn)
&nbsp;`·`&nbsp;
[![Portfolio](https://img.shields.io/badge/◈_PORTFOLIO-anandsavarn.vercel.app-00d9ff?style=flat-square&logo=vercel&logoColor=white)](https://anandsavarn.vercel.app)
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
</table>

---

## ◈ TECH STACK

<div align="center">

**Languages**

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![Kotlin](https://img.shields.io/badge/Kotlin-7F52FF?style=flat-square&logo=kotlin&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)
![C++](https://img.shields.io/badge/C++-00599C?style=flat-square&logo=cplusplus&logoColor=white)

**AI / ML**

![TensorFlow](https://img.shields.io/badge/TensorFlow-FF6F00?style=flat-square&logo=tensorflow&logoColor=white)
![Keras](https://img.shields.io/badge/Keras-D00000?style=flat-square&logo=keras&logoColor=white)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-F7931E?style=flat-square&logo=scikit-learn&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat-square&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=flat-square&logo=numpy&logoColor=white)

**Business Intelligence**

![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=flat-square&logo=powerbi&logoColor=black)
![Excel](https://img.shields.io/badge/Excel-217346?style=flat-square&logo=microsoftexcel&logoColor=white)
![DAX](https://img.shields.io/badge/DAX-0078D4?style=flat-square&logo=microsoft&logoColor=white)

**Web & Backend**

![Flask](https://img.shields.io/badge/Flask-000000?style=flat-square&logo=flask&logoColor=white)
![React](https://img.shields.io/badge/React-20232A?style=flat-square&logo=react&logoColor=61DAFB)
![MongoDB](https://img.shields.io/badge/MongoDB-47A248?style=flat-square&logo=mongodb&logoColor=white)

</div>

---

## ◈ GITHUB STATS

<div align="center">

<img height="165em" src="https://github-readme-stats.vercel.app/api?username=anandsavarn&show_icons=true&theme=tokyonight&include_all_commits=true&count_private=true&hide_border=true&bg_color=0d1117&title_color=00d9ff&icon_color=00d9ff"/>
&nbsp;
<img height="165em" src="https://github-readme-stats.vercel.app/api/top-langs/?username=anandsavarn&layout=compact&theme=tokyonight&hide_border=true&bg_color=0d1117&title_color=00d9ff"/>

</div>

<div align="center">

<img src="https://streak-stats.demolab.com/?user=anandsavarn&theme=tokyonight&hide_border=true&background=0d1117&ring=00d9ff&fire=00d9ff&currStreakLabel=00d9ff&sideLabels=00d9ff"/>

</div>

---

## ◈ CONNECT

<div align="center">

[![Portfolio](https://img.shields.io/badge/◈_PORTFOLIO-00d9ff?style=flat-square&logo=vercel&logoColor=white)](https://anandsavarn.vercel.app)
[![LinkedIn](https://img.shields.io/badge/LINKEDIN-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/anandsavarn/)
[![Kaggle](https://img.shields.io/badge/KAGGLE-20BEFF?style=flat-square&logo=kaggle&logoColor=white)](https://www.kaggle.com/anandsavarn)
[![LeetCode](https://img.shields.io/badge/LEETCODE-FFA116?style=flat-square&logo=leetcode&logoColor=black)](https://leetcode.com/u/anandsavarn/)

</div>

---

<div align="center">

```
⟩_ "Consistency beats talent when talent doesn't work hard."
```

`📡 anandsavarn@gmail.com` · [`github.com/Anandsavarn`](https://github.com/Anandsavarn) · [`anandsavarn.vercel.app`](https://anandsavarn.vercel.app)

![footer](https://capsule-render.vercel.app/api?type=venom&color=0:00d9ff,50:050520,100:000000&height=130&section=footer)

</div>
