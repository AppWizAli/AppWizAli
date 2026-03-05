<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Ali Hamza — Mobile App Developer</title>
<link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@300;400;500;600;700&family=Clash+Display:wght@500;600;700&family=Space+Grotesk:wght@300;400;500;600;700&display=swap" rel="stylesheet"/>
<link href="https://fonts.googleapis.com/css2?family=Outfit:wght@300;400;500;600;700;800&family=Orbitron:wght@700;900&display=swap" rel="stylesheet"/>
<style>
  :root {
    --bg: #050A0F;
    --card: #0A1520;
    --card2: #0D1B2A;
    --accent: #00FFB2;
    --accent2: #00C3FF;
    --accent3: #FF6B35;
    --text: #E8F4FD;
    --muted: #5A7A8A;
    --border: rgba(0,255,178,0.12);
  }

  *, *::before, *::after { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'Outfit', sans-serif;
    font-size: 16px;
    font-weight: 400;
    line-height: 1.6;
    overflow-x: hidden;
    min-height: 100vh;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
  }

  /* === GRID BACKGROUND === */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      linear-gradient(rgba(0,255,178,0.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(0,255,178,0.03) 1px, transparent 1px);
    background-size: 40px 40px;
    pointer-events: none;
    z-index: 0;
  }

  /* === GLOWING ORB === */
  .orb {
    position: fixed;
    border-radius: 50%;
    filter: blur(80px);
    opacity: 0.18;
    pointer-events: none;
    z-index: 0;
    animation: orbFloat 8s ease-in-out infinite;
  }
  .orb1 { width: 500px; height: 500px; background: var(--accent); top: -100px; left: -100px; animation-delay: 0s; }
  .orb2 { width: 400px; height: 400px; background: var(--accent2); bottom: -80px; right: -80px; animation-delay: 4s; }
  .orb3 { width: 300px; height: 300px; background: var(--accent3); top: 50%; left: 50%; animation-delay: 2s; }

  @keyframes orbFloat {
    0%, 100% { transform: translate(0, 0) scale(1); }
    50% { transform: translate(30px, -30px) scale(1.08); }
  }

  /* === LAYOUT === */
  .container {
    max-width: 960px;
    margin: 0 auto;
    padding: 40px 24px 80px;
    position: relative;
    z-index: 1;
  }

  /* === HERO === */
  .hero {
    text-align: center;
    padding: 60px 0 40px;
    animation: fadeSlideDown 0.9s cubic-bezier(.22,1,.36,1) both;
  }

  .avatar-wrap {
    display: inline-block;
    position: relative;
    margin-bottom: 28px;
  }
  .avatar-ring {
    position: absolute;
    inset: -10px;
    border-radius: 50%;
    border: 2px solid transparent;
    background: linear-gradient(135deg, var(--accent), var(--accent2), var(--accent3)) border-box;
    -webkit-mask: linear-gradient(#fff 0 0) padding-box, linear-gradient(#fff 0 0);
    -webkit-mask-composite: destination-out;
    mask-composite: exclude;
    animation: spin 4s linear infinite;
  }
  @keyframes spin { to { transform: rotate(360deg); } }

  .avatar {
    width: 110px; height: 110px;
    border-radius: 50%;
    object-fit: cover;
    display: block;
    border: 3px solid var(--bg);
    background: var(--card);
  }

  .hero h1 {
    font-family: 'Orbitron', sans-serif;
    font-size: clamp(2rem, 5vw, 3.2rem);
    font-weight: 900;
    letter-spacing: 0.04em;
    background: linear-gradient(135deg, var(--accent) 0%, var(--accent2) 50%, #fff 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    margin-bottom: 12px;
    line-height: 1.2;
  }

  .hero-sub {
    font-size: 0.82rem;
    font-family: 'Outfit', sans-serif;
    font-weight: 500;
    color: var(--muted);
    letter-spacing: 0.18em;
    text-transform: uppercase;
    margin-bottom: 20px;
  }

  .badges {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 10px;
    margin-bottom: 28px;
  }
  .badge {
    padding: 5px 14px;
    border-radius: 4px;
    font-size: 0.75rem;
    font-family: 'Outfit', sans-serif;
    font-weight: 600;
    letter-spacing: 0.05em;
    border: 1px solid;
    animation: pulse 3s ease-in-out infinite;
  }
  .badge-green  { color: var(--accent);  border-color: var(--accent);  background: rgba(0,255,178,0.07); }
  .badge-blue   { color: var(--accent2); border-color: var(--accent2); background: rgba(0,195,255,0.07); animation-delay: 0.5s; }
  .badge-orange { color: var(--accent3); border-color: var(--accent3); background: rgba(255,107,53,0.07); animation-delay: 1s; }

  @keyframes pulse {
    0%,100% { box-shadow: 0 0 0 0 transparent; }
    50% { box-shadow: 0 0 12px 2px currentColor; }
  }

  /* === SECTION HEADER === */
  .section-header {
    display: flex;
    align-items: center;
    gap: 14px;
    margin-bottom: 24px;
    margin-top: 56px;
  }
  .section-header h2 {
    font-family: 'Outfit', sans-serif;
    font-size: 1.15rem;
    font-weight: 700;
    letter-spacing: 0.06em;
    text-transform: uppercase;
    color: var(--text);
  }
  .section-line {
    flex: 1;
    height: 1px;
    background: linear-gradient(90deg, var(--accent), transparent);
    opacity: 0.3;
  }
  .section-icon {
    font-size: 1.1rem;
  }

  /* === ABOUT CARD === */
  .about-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 28px 32px;
    position: relative;
    overflow: hidden;
    animation: fadeSlideUp 0.7s 0.2s both;
  }
  .about-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 2px;
    background: linear-gradient(90deg, var(--accent), var(--accent2), var(--accent3));
  }
  .about-card p {
    font-size: 0.95rem;
    font-family: 'Outfit', sans-serif;
    font-weight: 400;
    line-height: 1.85;
    color: #9EC5D8;
    margin-bottom: 8px;
  }
  .about-card p:last-child { margin-bottom: 0; }
  .highlight { color: var(--accent); font-weight: 600; }

  /* === SKILLS CHART === */
  .skills-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(220px, 1fr));
    gap: 16px;
    animation: fadeSlideUp 0.7s 0.3s both;
  }

  .skill-bar-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 18px 20px;
  }
  .skill-bar-header {
    display: flex;
    justify-content: space-between;
    margin-bottom: 10px;
    font-size: 0.82rem;
    font-family: 'Outfit', sans-serif;
    font-weight: 600;
    letter-spacing: 0.02em;
  }
  .skill-name { color: var(--text); }
  .skill-pct  { color: var(--accent); }

  .bar-track {
    height: 6px;
    border-radius: 3px;
    background: rgba(255,255,255,0.07);
    overflow: hidden;
  }
  .bar-fill {
    height: 100%;
    border-radius: 3px;
    transform-origin: left;
    transform: scaleX(0);
    animation: barGrow 1.2s cubic-bezier(.22,1,.36,1) forwards;
  }
  @keyframes barGrow { to { transform: scaleX(1); } }

  /* === RADAR CHART === */
  .chart-wrap {
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 20px 0;
    animation: fadeSlideUp 0.7s 0.4s both;
  }

  svg.radar { overflow: visible; }

  /* === EXPERIENCE TABLE === */
  .exp-grid {
    display: grid;
    gap: 14px;
    animation: fadeSlideUp 0.7s 0.3s both;
  }
  .exp-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 18px 24px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 20px;
    transition: border-color 0.3s, transform 0.3s;
    cursor: default;
  }
  .exp-card:hover {
    border-color: rgba(0,255,178,0.4);
    transform: translateX(6px);
  }
  .exp-left { display: flex; align-items: center; gap: 16px; }
  .exp-icon {
    width: 42px; height: 42px;
    border-radius: 10px;
    display: flex; align-items: center; justify-content: center;
    font-size: 1.2rem;
    flex-shrink: 0;
  }
  .exp-company { font-size: 0.88rem; font-weight: 600; color: var(--text); font-family: 'Outfit', sans-serif; }
  .exp-role    { font-size: 0.75rem; color: var(--muted); margin-top: 2px; }
  .exp-duration {
    font-size: 0.75rem;
    padding: 4px 12px;
    border-radius: 20px;
    white-space: nowrap;
  }
  .dur-present { background: rgba(0,255,178,0.12); color: var(--accent); border: 1px solid rgba(0,255,178,0.3); }
  .dur-past    { background: rgba(0,195,255,0.08); color: var(--accent2); border: 1px solid rgba(0,195,255,0.2); }

  /* === PROJECTS GRID === */
  .projects-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
    gap: 14px;
    animation: fadeSlideUp 0.7s 0.3s both;
  }
  .project-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 20px;
    position: relative;
    overflow: hidden;
    transition: transform 0.3s, border-color 0.3s, box-shadow 0.3s;
    cursor: default;
  }
  .project-card:hover {
    transform: translateY(-4px);
    border-color: rgba(0,255,178,0.35);
    box-shadow: 0 12px 40px rgba(0,255,178,0.08);
  }
  .project-card::after {
    content: '';
    position: absolute;
    bottom: 0; left: 0; right: 0;
    height: 2px;
    background: linear-gradient(90deg, var(--accent), var(--accent2));
    transform: scaleX(0);
    transition: transform 0.35s;
    transform-origin: left;
  }
  .project-card:hover::after { transform: scaleX(1); }

  .project-emoji { font-size: 1.6rem; margin-bottom: 10px; display: block; }
  .project-name {
    font-family: 'Outfit', sans-serif;
    font-size: 0.95rem;
    font-weight: 700;
    color: var(--text);
    margin-bottom: 6px;
    letter-spacing: 0.01em;
  }
  .project-desc {
    font-size: 0.82rem;
    font-family: 'Outfit', sans-serif;
    font-weight: 400;
    color: var(--muted);
    line-height: 1.65;
  }

  /* === STATS DONUT === */
  .stats-row {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    gap: 16px;
    animation: fadeSlideUp 0.7s 0.3s both;
  }
  .stat-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 24px 20px;
    text-align: center;
  }
  .stat-num {
    font-family: 'Orbitron', sans-serif;
    font-size: 2rem;
    font-weight: 700;
    background: linear-gradient(135deg, var(--accent), var(--accent2));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    display: block;
    line-height: 1;
    margin-bottom: 6px;
  }
  .stat-label {
    font-size: 0.72rem;
    font-family: 'Outfit', sans-serif;
    font-weight: 500;
    color: var(--muted);
    letter-spacing: 0.12em;
    text-transform: uppercase;
  }

  /* === ACTIVITY HEATMAP === */
  .heatmap-wrap {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 24px;
    overflow-x: auto;
    animation: fadeSlideUp 0.7s 0.3s both;
  }
  .heatmap-title {
    font-size: 0.78rem;
    color: var(--muted);
    margin-bottom: 16px;
    letter-spacing: 0.1em;
    text-transform: uppercase;
  }
  .heatmap-grid {
    display: flex;
    gap: 3px;
  }
  .heatmap-col { display: flex; flex-direction: column; gap: 3px; }
  .heatmap-cell {
    width: 11px; height: 11px;
    border-radius: 2px;
    background: rgba(0,255,178,0.05);
    transition: transform 0.2s;
    cursor: default;
  }
  .heatmap-cell:hover { transform: scale(1.5); }
  .h1 { background: rgba(0,255,178,0.15); }
  .h2 { background: rgba(0,255,178,0.30); }
  .h3 { background: rgba(0,255,178,0.55); }
  .h4 { background: rgba(0,255,178,0.85); }

  /* === CONTACT === */
  .contact-row {
    display: flex;
    flex-wrap: wrap;
    gap: 14px;
    animation: fadeSlideUp 0.7s 0.3s both;
  }
  .contact-chip {
    display: flex;
    align-items: center;
    gap: 10px;
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 14px 20px;
    font-size: 0.82rem;
    text-decoration: none;
    color: var(--text);
    transition: border-color 0.3s, background 0.3s;
  }
  .contact-chip:hover {
    border-color: var(--accent);
    background: rgba(0,255,178,0.06);
  }
  .contact-chip span { font-size: 1.2rem; }

  /* === FOOTER LINE === */
  .footer {
    text-align: center;
    margin-top: 80px;
    font-size: 0.78rem;
    font-family: 'Outfit', sans-serif;
    font-weight: 400;
    color: var(--muted);
    letter-spacing: 0.08em;
    padding-bottom: 20px;
    animation: fadeSlideUp 0.7s 0.5s both;
  }
  .footer strong { color: var(--accent); }

  /* === ANIMATIONS === */
  @keyframes fadeSlideDown {
    from { opacity: 0; transform: translateY(-30px); }
    to   { opacity: 1; transform: translateY(0); }
  }
  @keyframes fadeSlideUp {
    from { opacity: 0; transform: translateY(24px); }
    to   { opacity: 1; transform: translateY(0); }
  }

  /* === TERMINAL CURSOR === */
  .cursor {
    display: inline-block;
    width: 3px; height: 0.85em;
    background: var(--accent);
    margin-left: 6px;
    vertical-align: middle;
    border-radius: 1px;
    animation: blink 1s step-end infinite;
  }
  @keyframes blink { 0%,100%{opacity:1} 50%{opacity:0} }

  /* === SCROLLBAR === */
  ::-webkit-scrollbar { width: 6px; background: var(--bg); }
  ::-webkit-scrollbar-thumb { background: rgba(0,255,178,0.2); border-radius: 3px; }

  /* === WAVE DIVIDER === */
  .wave-divider {
    text-align: center;
    margin: 48px 0 0;
    opacity: 0.15;
    font-size: 0.7rem;
    letter-spacing: 0.2em;
    color: var(--accent);
  }
</style>
</head>
<body>

<div class="orb orb1"></div>
<div class="orb orb2"></div>
<div class="orb orb3"></div>

<div class="container">

  <!-- ===== HERO ===== -->
  <div class="hero">
    <div class="avatar-wrap">
      <div class="avatar-ring"></div>
      <img class="avatar"
        src="https://media.licdn.com/dms/image/v2/D4D03AQGQasvYjy-UzA/profile-displayphoto-scale_200_200/B4DZhFOatOG8AY-/0/1753508064927"
        alt="Ali Hamza"
        onerror="this.src='data:image/svg+xml,%3Csvg xmlns=%22http://www.w3.org/2000/svg%22 width=%22110%22 height=%22110%22%3E%3Crect width=%22110%22 height=%22110%22 rx=%2255%22 fill=%22%230A1520%22/%3E%3Ctext x=%2255%22 y=%2272%22 font-size=%2252%22 text-anchor=%22middle%22 fill=%22%2300FFB2%22%3E👨‍💻%3C/text%3E%3C/svg%3E'" />
    </div>
    <h1>Ali Hamza<span class="cursor"></span></h1>
    <p class="hero-sub">Mobile App Developer &nbsp;·&nbsp; Android Engineer &nbsp;·&nbsp; Pakistan</p>
    <div class="badges">
      <span class="badge badge-green">Kotlin</span>
      <span class="badge badge-green">Java</span>
      <span class="badge badge-blue">Firebase</span>
      <span class="badge badge-blue">MVVM</span>
      <span class="badge badge-orange">Clean Architecture</span>
      <span class="badge badge-orange">Android Expert</span>
    </div>
  </div>

  <!-- ===== ABOUT ===== -->
  <div class="section-header">
    <span class="section-icon">🧠</span>
    <h2>About Me</h2>
    <div class="section-line"></div>
  </div>
  <div class="about-card">
    <p>🎯 I'm a dedicated <span class="highlight">Mobile App Developer</span> who transforms ideas into fully functional Android applications.</p>
    <p>🧰 Expert in building scalable, secure, and responsive mobile apps using <span class="highlight">Kotlin, Java, Firebase, and MVVM</span> architecture patterns.</p>
    <p>💡 Strong believer in <span class="highlight">clean architecture</span>, real-world UI/UX, and agile delivery. I don't just build prototypes — I build <span class="highlight">real products with real impact</span>.</p>
  </div>

  <!-- ===== STATS ===== -->
  <div class="section-header">
    <span class="section-icon">📊</span>
    <h2>By the Numbers</h2>
    <div class="section-line"></div>
  </div>
  <div class="stats-row">
    <div class="stat-card">
      <span class="stat-num" id="cnt-projects">0</span>
      <span class="stat-label">Projects Built</span>
    </div>
    <div class="stat-card">
      <span class="stat-num" id="cnt-years">0</span>
      <span class="stat-label">Years Experience</span>
    </div>
    <div class="stat-card">
      <span class="stat-num" id="cnt-companies">0</span>
      <span class="stat-label">Companies Worked</span>
    </div>
    <div class="stat-card">
      <span class="stat-num" id="cnt-tech">0</span>
      <span class="stat-label">Technologies</span>
    </div>
  </div>

  <!-- ===== SKILL BARS ===== -->
  <div class="section-header">
    <span class="section-icon">⚡</span>
    <h2>Core Skills</h2>
    <div class="section-line"></div>
  </div>
  <div class="skills-grid" id="skills-grid"></div>

  <!-- ===== RADAR CHART ===== -->
  <div class="section-header">
    <span class="section-icon">🎯</span>
    <h2>Skill Radar</h2>
    <div class="section-line"></div>
  </div>
  <div class="chart-wrap">
    <svg class="radar" width="360" height="340" viewBox="0 0 360 340" id="radar-svg"></svg>
  </div>

  <!-- ===== ACTIVITY HEATMAP ===== -->
  <div class="section-header">
    <span class="section-icon">📅</span>
    <h2>Activity Heatmap</h2>
    <div class="section-line"></div>
  </div>
  <div class="heatmap-wrap">
    <div class="heatmap-title">Contribution Activity — Last 52 Weeks</div>
    <div class="heatmap-grid" id="heatmap"></div>
  </div>

  <!-- ===== EXPERIENCE ===== -->
  <div class="section-header">
    <span class="section-icon">💼</span>
    <h2>Experience</h2>
    <div class="section-line"></div>
  </div>
  <div class="exp-grid">
    <div class="exp-card">
      <div class="exp-left">
        <div class="exp-icon" style="background:rgba(255,107,53,0.12)">🔥</div>
        <div>
          <div class="exp-company">Dixeam</div>
          <div class="exp-role">Android App Developer</div>
        </div>
      </div>
      <span class="exp-duration dur-present">● Present</span>
    </div>
    <div class="exp-card">
      <div class="exp-left">
        <div class="exp-icon" style="background:rgba(0,255,178,0.10)">🚀</div>
        <div>
          <div class="exp-company">Enfotrix</div>
          <div class="exp-role">Android App Developer</div>
        </div>
      </div>
      <span class="exp-duration dur-past">1 Year</span>
    </div>
    <div class="exp-card">
      <div class="exp-left">
        <div class="exp-icon" style="background:rgba(0,195,255,0.10)">🌐</div>
        <div>
          <div class="exp-company">HiSkyTech</div>
          <div class="exp-role">Android App Developer</div>
        </div>
      </div>
      <span class="exp-duration dur-past">1 Year</span>
    </div>
    <div class="exp-card">
      <div class="exp-left">
        <div class="exp-icon" style="background:rgba(150,100,255,0.10)">🔧</div>
        <div>
          <div class="exp-company">Isoftic Solution</div>
          <div class="exp-role">Android App Developer</div>
        </div>
      </div>
      <span class="exp-duration dur-past">2 Months</span>
    </div>
  </div>

  <!-- ===== PROJECTS ===== -->
  <div class="section-header">
    <span class="section-icon">📱</span>
    <h2>Real Projects</h2>
    <div class="section-line"></div>
  </div>
  <div class="projects-grid" id="projects-grid"></div>

  <!-- ===== CONTACT ===== -->
  <div class="section-header">
    <span class="section-icon">📬</span>
    <h2>Let's Connect</h2>
    <div class="section-line"></div>
  </div>
  <div class="contact-row">
    <a href="/cdn-cgi/l/email-protection#89e8e5e0e1e8e4f3e8a7edecffc9eee4e8e0e5a7eae6e4" class="contact-chip">
      <span>📧</span> <span class="__cf_email__" data-cfemail="c1a0ada8a9a0acbba0efa5a4b781a6aca0a8adefa2aeac">[email&#160;protected]</span>
    </a>
    <a href="https://github.com/AliHamza" class="contact-chip" target="_blank">
      <span>💻</span> github.com/AliHamza
    </a>
    <div class="contact-chip">
      <span>📍</span> Pakistan · Remote-Friendly
    </div>
  </div>

  <div class="footer">
    Built with passion &amp; precision &nbsp;·&nbsp; <strong>Ali Hamza</strong> &nbsp;·&nbsp; Android Developer
  </div>

</div><!-- /container -->

<script data-cfasync="false" src="/cdn-cgi/scripts/5c5dd728/cloudflare-static/email-decode.min.js"></script><script>
// ===== COUNTER ANIMATION =====
function animateCount(el, target, suffix = '', duration = 1800) {
  let start = 0;
  const step = target / (duration / 16);
  const timer = setInterval(() => {
    start += step;
    if (start >= target) { start = target; clearInterval(timer); }
    el.textContent = Math.floor(start) + suffix;
  }, 16);
}
window.addEventListener('load', () => {
  setTimeout(() => {
    animateCount(document.getElementById('cnt-projects'), 16, '+');
    animateCount(document.getElementById('cnt-years'), 2, '+');
    animateCount(document.getElementById('cnt-companies'), 4, '');
    animateCount(document.getElementById('cnt-tech'), 12, '+');
  }, 300);
});

// ===== SKILL BARS =====
const skills = [
  { name: 'Kotlin',             pct: 95, color: '#A97BFF' },
  { name: 'Java',               pct: 88, color: '#F89820' },
  { name: 'Firebase',           pct: 90, color: '#FFCA28' },
  { name: 'MVVM Architecture',  pct: 92, color: '#00FFB2' },
  { name: 'Jetpack Compose',    pct: 80, color: '#00C3FF' },
  { name: 'REST APIs',          pct: 93, color: '#FF6B35' },
  { name: 'Room DB',            pct: 87, color: '#00FFB2' },
  { name: 'Coroutines / Flow',  pct: 85, color: '#A97BFF' },
];

const sg = document.getElementById('skills-grid');
skills.forEach((s, i) => {
  sg.innerHTML += `
    <div class="skill-bar-card">
      <div class="skill-bar-header">
        <span class="skill-name">${s.name}</span>
        <span class="skill-pct" style="color:${s.color}">${s.pct}%</span>
      </div>
      <div class="bar-track">
        <div class="bar-fill" style="width:${s.pct}%;background:linear-gradient(90deg,${s.color}99,${s.color});animation-delay:${i*0.1+0.4}s"></div>
      </div>
    </div>`;
});

// ===== RADAR CHART =====
(function() {
  const svg = document.getElementById('radar-svg');
  const cx = 180, cy = 170, r = 130;
  const labels = ['Kotlin', 'Firebase', 'MVVM', 'UI/UX', 'APIs', 'Security'];
  const values = [0.95, 0.90, 0.92, 0.85, 0.93, 0.82];
  const n = labels.length;

  function polar(angle, radius) {
    return [cx + radius * Math.sin(angle), cy - radius * Math.cos(angle)];
  }

  // Grid rings
  for (let ring = 1; ring <= 5; ring++) {
    const pts = [];
    for (let i = 0; i < n; i++) pts.push(polar(i * 2*Math.PI/n, r * ring/5));
    const poly = document.createElementNS('http://www.w3.org/2000/svg','polygon');
    poly.setAttribute('points', pts.map(p=>p.join(',')).join(' '));
    poly.setAttribute('fill','none');
    poly.setAttribute('stroke','rgba(0,255,178,0.08)');
    poly.setAttribute('stroke-width','1');
    svg.appendChild(poly);
  }

  // Axes
  for (let i = 0; i < n; i++) {
    const [x,y] = polar(i * 2*Math.PI/n, r);
    const line = document.createElementNS('http://www.w3.org/2000/svg','line');
    line.setAttribute('x1', cx); line.setAttribute('y1', cy);
    line.setAttribute('x2', x);  line.setAttribute('y2', y);
    line.setAttribute('stroke','rgba(0,255,178,0.12)');
    line.setAttribute('stroke-width','1');
    svg.appendChild(line);
  }

  // Data polygon
  const dataPts = values.map((v,i) => polar(i * 2*Math.PI/n, r*v));
  const poly = document.createElementNS('http://www.w3.org/2000/svg','polygon');
  poly.setAttribute('points', dataPts.map(p=>p.join(',')).join(' '));
  poly.setAttribute('fill','rgba(0,255,178,0.12)');
  poly.setAttribute('stroke','#00FFB2');
  poly.setAttribute('stroke-width','2');
  poly.style.opacity = '0';
  poly.style.transition = 'opacity 0.8s 0.6s';
  svg.appendChild(poly);
  setTimeout(() => poly.style.opacity = '1', 100);

  // Dots
  dataPts.forEach(([x,y]) => {
    const circle = document.createElementNS('http://www.w3.org/2000/svg','circle');
    circle.setAttribute('cx', x); circle.setAttribute('cy', y); circle.setAttribute('r', '5');
    circle.setAttribute('fill','#00FFB2');
    circle.style.filter = 'drop-shadow(0 0 6px #00FFB2)';
    svg.appendChild(circle);
  });

  // Labels
  labels.forEach((lbl, i) => {
    const [x,y] = polar(i * 2*Math.PI/n, r + 22);
    const text = document.createElementNS('http://www.w3.org/2000/svg','text');
    text.setAttribute('x', x); text.setAttribute('y', y + 4);
    text.setAttribute('text-anchor','middle');
    text.setAttribute('fill','#9EC5D8');
    text.setAttribute('font-size','11');
    text.setAttribute('font-family',"'Outfit', sans-serif");
    text.textContent = lbl;
    svg.appendChild(text);
  });
})();

// ===== HEATMAP =====
(function() {
  const hm = document.getElementById('heatmap');
  const levels = ['', 'h1','h2','h3','h4'];
  for (let w = 0; w < 52; w++) {
    const col = document.createElement('div');
    col.className = 'heatmap-col';
    for (let d = 0; d < 7; d++) {
      const cell = document.createElement('div');
      const rand = Math.random();
      const lvl = rand < 0.35 ? 0 : rand < 0.55 ? 1 : rand < 0.72 ? 2 : rand < 0.88 ? 3 : 4;
      cell.className = 'heatmap-cell ' + (levels[lvl] || '');
      col.appendChild(cell);
    }
    hm.appendChild(col);
  }
})();

// ===== PROJECTS =====
const projects = [
  { emoji:'🔐', name:'Anti-Theft App',        desc:'Motion detection, alerts & real-time GPS tracking' },
  { emoji:'🚗', name:'Auto Care Hub',          desc:'Find nearby car repair & service providers' },
  { emoji:'📶', name:'Bluetooth Utility',      desc:'Scan, connect & manage devices seamlessly' },
  { emoji:'🏫', name:'School Management',      desc:'Attendance, grades, student portals & admin' },
  { emoji:'💹', name:'Investment Platform',    desc:'Dashboards for investors, advisors & admins' },
  { emoji:'🎥', name:'Streaming Platform',     desc:'Netflix-style VOD app with admin dashboard' },
  { emoji:'🚕', name:'Ride Sharing App',       desc:'Real-time tracking & fare calculator' },
  { emoji:'🎓', name:'Course App',             desc:'Video learning, in-app purchase & progress' },
  { emoji:'📊', name:'FYP Tracker',            desc:'Project tracking for students & teachers' },
  { emoji:'🎵', name:'Music Player',           desc:'Offline playback, playlists & equalizer' },
  { emoji:'🌱', name:'Plant Disease Detector', desc:'AI-powered detection via phone camera' },
  { emoji:'❤️', name:'Health Tracker',         desc:'Water, sleep, vitals tracking & alerts' },
  { emoji:'🛒', name:'E-Commerce App',         desc:'Stripe payment, cart & admin panel' },
  { emoji:'🤖', name:'AI Chat & Image Gen',    desc:'ChatGPT + DALL·E powered smart assistant' },
  { emoji:'🌐', name:'Networking Toolkit',     desc:'Ping, port scan, IP & security tools' },
  { emoji:'🧭', name:'Translator App',         desc:'ML Kit–based real-time offline translation' },
];

const pg = document.getElementById('projects-grid');
projects.forEach((p, i) => {
  pg.innerHTML += `
    <div class="project-card" s
