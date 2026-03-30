<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Pratiksha Sharma — GitHub Profile</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,700;0,900;1,400&family=DM+Mono:wght@300;400;500&family=Cabinet+Grotesk:wght@400;500;700;800;900&display=swap" rel="stylesheet">
<style>
  :root {
    --pink-soft: #FFB6C1;
    --pink-mid: #FF69B4;
    --pink-hot: #FF1493;
    --pink-deep: #C71585;
    --pink-blush: #FFF0F5;
    --pink-dust: #FFE4EE;
    --dark: #1a0a10;
    --dark-mid: #2d1220;
    --charcoal: #3d1a28;
    --white: #FFFAF8;
    --accent-gold: #FFD700;
    --accent-cyan: #00E5FF;
    --text-light: #f5d4e0;
    --mono: 'DM Mono', monospace;
    --display: 'Playfair Display', serif;
    --body: 'Cabinet Grotesk', sans-serif;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background: var(--dark);
    color: var(--white);
    font-family: var(--body);
    overflow-x: hidden;
    cursor: none;
  }

  /* Custom cursor */
  .cursor {
    width: 20px; height: 20px;
    border: 2px solid var(--pink-hot);
    border-radius: 50%;
    position: fixed;
    pointer-events: none;
    z-index: 9999;
    transition: transform 0.15s ease, background 0.15s ease;
    transform: translate(-50%, -50%);
  }
  .cursor-dot {
    width: 6px; height: 6px;
    background: var(--pink-hot);
    border-radius: 50%;
    position: fixed;
    pointer-events: none;
    z-index: 9999;
    transform: translate(-50%, -50%);
  }
  .cursor.hovering { transform: translate(-50%, -50%) scale(2.5); background: rgba(255,20,147,0.15); }

  /* Animated background */
  .bg-grid {
    position: fixed;
    inset: 0;
    background-image: 
      linear-gradient(rgba(255,105,180,0.06) 1px, transparent 1px),
      linear-gradient(90deg, rgba(255,105,180,0.06) 1px, transparent 1px);
    background-size: 50px 50px;
    z-index: 0;
    animation: gridMove 20s linear infinite;
  }
  @keyframes gridMove {
    0% { background-position: 0 0; }
    100% { background-position: 50px 50px; }
  }

  .noise {
    position: fixed;
    inset: 0;
    opacity: 0.03;
    background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noise'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noise)'/%3E%3C/svg%3E");
    z-index: 0;
    pointer-events: none;
  }

  /* Floating orbs */
  .orb {
    position: fixed;
    border-radius: 50%;
    filter: blur(80px);
    pointer-events: none;
    z-index: 0;
    animation: orbFloat 8s ease-in-out infinite alternate;
  }
  .orb-1 { width: 400px; height: 400px; background: radial-gradient(circle, rgba(255,20,147,0.25), transparent); top: -100px; right: -100px; }
  .orb-2 { width: 300px; height: 300px; background: radial-gradient(circle, rgba(199,21,133,0.2), transparent); bottom: 20%; left: -80px; animation-delay: -3s; }
  .orb-3 { width: 200px; height: 200px; background: radial-gradient(circle, rgba(255,105,180,0.15), transparent); top: 40%; right: 15%; animation-delay: -6s; }
  @keyframes orbFloat { 0% { transform: translate(0,0) scale(1); } 100% { transform: translate(20px, 30px) scale(1.1); } }

  /* Layout */
  .container { max-width: 1100px; margin: 0 auto; padding: 0 30px; position: relative; z-index: 1; }

  /* ===== HERO ===== */
  .hero {
    min-height: 100vh;
    display: flex;
    align-items: center;
    position: relative;
    overflow: hidden;
    padding: 80px 0;
  }

  .hero-inner {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 60px;
    align-items: center;
    width: 100%;
  }

  .hero-tag {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    font-family: var(--mono);
    font-size: 12px;
    color: var(--pink-mid);
    background: rgba(255,105,180,0.1);
    border: 1px solid rgba(255,105,180,0.3);
    padding: 6px 16px;
    border-radius: 100px;
    margin-bottom: 24px;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    animation: fadeInUp 0.6s ease both;
  }
  .hero-tag::before { content: ''; width: 6px; height: 6px; background: var(--pink-hot); border-radius: 50%; animation: pulse 2s ease-in-out infinite; }
  @keyframes pulse { 0%,100% { opacity: 1; transform: scale(1); } 50% { opacity: 0.5; transform: scale(0.8); } }

  .hero-name {
    font-family: var(--display);
    font-size: clamp(48px, 6vw, 80px);
    font-weight: 900;
    line-height: 0.95;
    letter-spacing: -0.02em;
    animation: fadeInUp 0.6s 0.1s ease both;
  }
  .hero-name .line-1 { display: block; color: var(--white); }
  .hero-name .line-2 { display: block; color: var(--pink-hot); font-style: italic; }

  .hero-title {
    font-family: var(--mono);
    font-size: 14px;
    color: rgba(255,182,193,0.7);
    margin-top: 20px;
    letter-spacing: 0.08em;
    animation: fadeInUp 0.6s 0.2s ease both;
  }

  .hero-bio {
    font-size: 17px;
    line-height: 1.7;
    color: var(--text-light);
    margin-top: 24px;
    max-width: 460px;
    animation: fadeInUp 0.6s 0.3s ease both;
  }
  .hero-bio strong { color: var(--pink-soft); font-weight: 700; }

  .hero-stats {
    display: flex;
    gap: 32px;
    margin-top: 36px;
    animation: fadeInUp 0.6s 0.4s ease both;
  }
  .stat-item { text-align: center; }
  .stat-num {
    font-family: var(--display);
    font-size: 36px;
    font-weight: 900;
    color: var(--pink-hot);
    line-height: 1;
    display: block;
  }
  .stat-label {
    font-family: var(--mono);
    font-size: 11px;
    color: rgba(255,182,193,0.6);
    text-transform: uppercase;
    letter-spacing: 0.1em;
    margin-top: 4px;
  }

  .hero-links {
    display: flex;
    gap: 14px;
    margin-top: 36px;
    flex-wrap: wrap;
    animation: fadeInUp 0.6s 0.5s ease both;
  }
  .hero-btn {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    padding: 12px 24px;
    border-radius: 8px;
    font-family: var(--body);
    font-weight: 700;
    font-size: 14px;
    text-decoration: none;
    transition: all 0.2s ease;
    letter-spacing: 0.02em;
  }
  .hero-btn.primary {
    background: var(--pink-hot);
    color: var(--white);
    box-shadow: 0 0 30px rgba(255,20,147,0.4);
  }
  .hero-btn.primary:hover { transform: translateY(-2px); box-shadow: 0 0 50px rgba(255,20,147,0.6); }
  .hero-btn.ghost {
    background: transparent;
    color: var(--pink-soft);
    border: 1.5px solid rgba(255,105,180,0.4);
  }
  .hero-btn.ghost:hover { border-color: var(--pink-hot); color: var(--pink-hot); transform: translateY(-2px); }

  /* Hero visual side */
  .hero-visual {
    position: relative;
    display: flex;
    justify-content: center;
    align-items: center;
    animation: fadeIn 1s 0.3s ease both;
  }

  .avatar-ring {
    width: 280px; height: 280px;
    border-radius: 50%;
    background: linear-gradient(135deg, var(--pink-hot), var(--pink-deep), #8B0057);
    padding: 3px;
    position: relative;
    animation: rotate 10s linear infinite;
  }
  @keyframes rotate { 0% { filter: hue-rotate(0deg); } 100% { filter: hue-rotate(360deg); } }

  .avatar-inner {
    width: 100%;
    height: 100%;
    border-radius: 50%;
    background: var(--dark-mid);
    display: flex;
    align-items: center;
    justify-content: center;
    font-family: var(--display);
    font-size: 80px;
    font-weight: 900;
    color: var(--pink-hot);
    position: relative;
    overflow: hidden;
  }
  .avatar-inner::before {
    content: '';
    position: absolute;
    inset: 0;
    background: radial-gradient(circle at 30% 30%, rgba(255,105,180,0.2), transparent 60%);
  }

  .floating-badges {
    position: absolute;
    inset: 0;
  }
  .badge {
    position: absolute;
    background: var(--dark-mid);
    border: 1px solid rgba(255,20,147,0.4);
    border-radius: 12px;
    padding: 10px 16px;
    font-family: var(--mono);
    font-size: 11px;
    color: var(--pink-soft);
    white-space: nowrap;
    display: flex;
    align-items: center;
    gap: 8px;
    animation: badgeFloat 4s ease-in-out infinite alternate;
    box-shadow: 0 4px 24px rgba(255,20,147,0.15);
  }
  .badge:nth-child(1) { top: -10px; left: -60px; animation-delay: 0s; }
  .badge:nth-child(2) { top: 50px; right: -70px; animation-delay: -1.5s; }
  .badge:nth-child(3) { bottom: 30px; left: -70px; animation-delay: -3s; }
  .badge:nth-child(4) { bottom: -10px; right: -50px; animation-delay: -2s; }
  .badge-dot { width: 8px; height: 8px; border-radius: 50%; background: var(--pink-hot); }
  @keyframes badgeFloat { 0% { transform: translateY(0); } 100% { transform: translateY(-8px); } }

  /* ===== SECTIONS ===== */
  section { padding: 80px 0; position: relative; z-index: 1; }
  
  .section-label {
    font-family: var(--mono);
    font-size: 11px;
    color: var(--pink-hot);
    text-transform: uppercase;
    letter-spacing: 0.2em;
    margin-bottom: 8px;
  }
  .section-title {
    font-family: var(--display);
    font-size: clamp(32px, 4vw, 52px);
    font-weight: 900;
    line-height: 1.05;
    color: var(--white);
    margin-bottom: 48px;
  }
  .section-title .accent { color: var(--pink-hot); font-style: italic; }

  /* Divider */
  .divider {
    height: 1px;
    background: linear-gradient(90deg, transparent, rgba(255,20,147,0.4), transparent);
    margin: 0;
  }

  /* ===== SKILLS ===== */
  .skills-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: 20px;
  }
  .skill-card {
    background: rgba(255,20,147,0.05);
    border: 1px solid rgba(255,20,147,0.15);
    border-radius: 16px;
    padding: 28px;
    transition: all 0.3s ease;
    position: relative;
    overflow: hidden;
  }
  .skill-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 2px;
    background: linear-gradient(90deg, transparent, var(--pink-hot), transparent);
    opacity: 0;
    transition: opacity 0.3s;
  }
  .skill-card:hover { border-color: rgba(255,20,147,0.4); transform: translateY(-4px); box-shadow: 0 20px 60px rgba(255,20,147,0.1); }
  .skill-card:hover::before { opacity: 1; }
  .skill-card-title {
    font-family: var(--mono);
    font-size: 12px;
    color: var(--pink-mid);
    text-transform: uppercase;
    letter-spacing: 0.15em;
    margin-bottom: 16px;
    display: flex;
    align-items: center;
    gap: 8px;
  }
  .skill-tags {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
  }
  .skill-tag {
    font-family: var(--mono);
    font-size: 12px;
    padding: 5px 12px;
    border-radius: 6px;
    background: rgba(255,105,180,0.1);
    color: var(--pink-soft);
    border: 1px solid rgba(255,105,180,0.2);
    transition: all 0.2s;
  }
  .skill-tag:hover { background: rgba(255,20,147,0.2); color: var(--white); border-color: var(--pink-hot); cursor: default; }

  /* ===== PROJECTS ===== */
  .projects-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 24px;
  }
  .project-card {
    background: var(--dark-mid);
    border: 1px solid rgba(255,20,147,0.2);
    border-radius: 20px;
    padding: 36px;
    position: relative;
    overflow: hidden;
    transition: all 0.3s ease;
    cursor: default;
  }
  .project-card::after {
    content: '';
    position: absolute;
    inset: 0;
    background: radial-gradient(circle at var(--mx, 50%) var(--my, 50%), rgba(255,20,147,0.08), transparent 60%);
    opacity: 0;
    transition: opacity 0.3s;
    pointer-events: none;
  }
  .project-card:hover { border-color: rgba(255,20,147,0.5); transform: translateY(-6px); box-shadow: 0 30px 80px rgba(255,20,147,0.15); }
  .project-card:hover::after { opacity: 1; }
  
  .project-number {
    font-family: var(--display);
    font-size: 72px;
    font-weight: 900;
    color: rgba(255,20,147,0.08);
    position: absolute;
    top: 10px; right: 24px;
    line-height: 1;
    user-select: none;
    transition: color 0.3s;
  }
  .project-card:hover .project-number { color: rgba(255,20,147,0.12); }

  .project-icon {
    width: 50px; height: 50px;
    background: linear-gradient(135deg, var(--pink-deep), var(--pink-hot));
    border-radius: 14px;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 22px;
    margin-bottom: 20px;
    box-shadow: 0 8px 24px rgba(255,20,147,0.3);
  }
  .project-name {
    font-family: var(--display);
    font-size: 24px;
    font-weight: 700;
    color: var(--white);
    margin-bottom: 6px;
  }
  .project-subtitle {
    font-family: var(--mono);
    font-size: 11px;
    color: var(--pink-mid);
    text-transform: uppercase;
    letter-spacing: 0.15em;
    margin-bottom: 16px;
  }
  .project-desc {
    font-size: 15px;
    line-height: 1.7;
    color: rgba(245,212,224,0.8);
    margin-bottom: 20px;
  }
  .project-stack {
    display: flex;
    flex-wrap: wrap;
    gap: 6px;
    margin-bottom: 24px;
  }
  .stack-tag {
    font-family: var(--mono);
    font-size: 10px;
    padding: 4px 10px;
    background: rgba(255,20,147,0.1);
    border: 1px solid rgba(255,20,147,0.25);
    border-radius: 4px;
    color: var(--pink-soft);
    letter-spacing: 0.05em;
  }
  .project-links {
    display: flex;
    gap: 12px;
  }
  .proj-link {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    font-size: 13px;
    font-weight: 700;
    color: var(--pink-hot);
    text-decoration: none;
    letter-spacing: 0.02em;
    transition: all 0.2s;
    padding: 8px 16px;
    border: 1.5px solid rgba(255,20,147,0.3);
    border-radius: 8px;
  }
  .proj-link:hover { background: rgba(255,20,147,0.15); border-color: var(--pink-hot); }

  /* ===== EXPERIENCE/EDUCATION ===== */
  .timeline {
    position: relative;
    padding-left: 32px;
  }
  .timeline::before {
    content: '';
    position: absolute;
    left: 0; top: 0; bottom: 0;
    width: 2px;
    background: linear-gradient(180deg, var(--pink-hot), transparent);
  }
  .timeline-item {
    position: relative;
    margin-bottom: 44px;
    padding-bottom: 44px;
    border-bottom: 1px solid rgba(255,20,147,0.1);
  }
  .timeline-item:last-child { border-bottom: none; margin-bottom: 0; }
  .timeline-dot {
    position: absolute;
    left: -37px;
    top: 4px;
    width: 12px; height: 12px;
    border-radius: 50%;
    background: var(--pink-hot);
    box-shadow: 0 0 16px rgba(255,20,147,0.6);
    border: 2px solid var(--dark);
  }
  .timeline-date {
    font-family: var(--mono);
    font-size: 11px;
    color: var(--pink-mid);
    letter-spacing: 0.1em;
    margin-bottom: 6px;
    text-transform: uppercase;
  }
  .timeline-org {
    font-family: var(--display);
    font-size: 22px;
    font-weight: 700;
    color: var(--white);
    margin-bottom: 2px;
  }
  .timeline-role {
    font-size: 14px;
    color: var(--pink-soft);
    font-weight: 600;
    margin-bottom: 10px;
  }
  .timeline-detail {
    font-size: 15px;
    color: rgba(245,212,224,0.7);
    line-height: 1.6;
  }
  .timeline-badge {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    font-family: var(--mono);
    font-size: 11px;
    padding: 4px 12px;
    background: rgba(255,215,0,0.1);
    border: 1px solid rgba(255,215,0,0.3);
    color: var(--accent-gold);
    border-radius: 100px;
    margin-top: 10px;
  }

  /* ===== ACHIEVEMENTS ===== */
  .achievements-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
    gap: 18px;
  }
  .achievement-card {
    background: rgba(255,20,147,0.05);
    border: 1px solid rgba(255,20,147,0.15);
    border-radius: 14px;
    padding: 24px;
    transition: all 0.3s;
    text-align: center;
  }
  .achievement-card:hover { background: rgba(255,20,147,0.1); border-color: rgba(255,20,147,0.35); transform: scale(1.03); }
  .achievement-icon { font-size: 36px; margin-bottom: 12px; display: block; }
  .achievement-title { font-weight: 700; font-size: 15px; color: var(--white); margin-bottom: 6px; }
  .achievement-desc { font-size: 13px; color: rgba(245,212,224,0.6); line-height: 1.5; }

  /* ===== CERTIFICATIONS ===== */
  .cert-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 18px;
  }
  .cert-card {
    background: rgba(0,229,255,0.04);
    border: 1px solid rgba(0,229,255,0.15);
    border-radius: 14px;
    padding: 24px 28px;
    display: flex;
    align-items: flex-start;
    gap: 18px;
    transition: all 0.3s;
  }
  .cert-card:hover { border-color: rgba(0,229,255,0.3); background: rgba(0,229,255,0.08); }
  .cert-icon {
    width: 44px; height: 44px;
    background: rgba(0,229,255,0.1);
    border-radius: 12px;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 20px;
    flex-shrink: 0;
  }
  .cert-name { font-weight: 700; font-size: 15px; color: var(--white); margin-bottom: 4px; }
  .cert-issuer { font-family: var(--mono); font-size: 11px; color: rgba(0,229,255,0.7); margin-bottom: 4px; }
  .cert-date { font-size: 13px; color: rgba(245,212,224,0.5); }

  /* ===== CONTACT ===== */
  .contact-row {
    display: flex;
    gap: 18px;
    flex-wrap: wrap;
    justify-content: center;
  }
  .contact-card {
    background: rgba(255,20,147,0.08);
    border: 1px solid rgba(255,20,147,0.25);
    border-radius: 14px;
    padding: 20px 28px;
    display: flex;
    align-items: center;
    gap: 14px;
    text-decoration: none;
    transition: all 0.3s;
    min-width: 200px;
  }
  .contact-card:hover { background: rgba(255,20,147,0.18); border-color: var(--pink-hot); transform: translateY(-4px); box-shadow: 0 16px 40px rgba(255,20,147,0.2); }
  .contact-icon { font-size: 22px; }
  .contact-label { font-family: var(--mono); font-size: 10px; color: var(--pink-mid); text-transform: uppercase; letter-spacing: 0.1em; margin-bottom: 2px; }
  .contact-value { font-size: 14px; font-weight: 700; color: var(--white); }

  /* Footer */
  .footer {
    text-align: center;
    padding: 48px 0 32px;
    font-family: var(--mono);
    font-size: 12px;
    color: rgba(255,182,193,0.3);
    letter-spacing: 0.1em;
    position: relative;
    z-index: 1;
  }
  .footer span { color: var(--pink-hot); }

  /* Tab system */
  .tab-bar {
    display: flex;
    gap: 4px;
    background: rgba(255,20,147,0.05);
    border: 1px solid rgba(255,20,147,0.15);
    border-radius: 12px;
    padding: 6px;
    width: fit-content;
    margin-bottom: 36px;
  }
  .tab-btn {
    font-family: var(--mono);
    font-size: 12px;
    padding: 8px 20px;
    border-radius: 8px;
    border: none;
    background: transparent;
    color: rgba(255,182,193,0.6);
    cursor: pointer;
    transition: all 0.2s;
    letter-spacing: 0.05em;
    text-transform: uppercase;
  }
  .tab-btn.active {
    background: var(--pink-hot);
    color: var(--white);
    box-shadow: 0 4px 16px rgba(255,20,147,0.4);
  }
  .tab-content { display: none; }
  .tab-content.active { display: block; }

  /* Animated counter */
  @keyframes countUp {
    from { opacity: 0; transform: translateY(10px); }
    to { opacity: 1; transform: translateY(0); }
  }

  /* Scroll reveal */
  .reveal {
    opacity: 0;
    transform: translateY(30px);
    transition: opacity 0.7s ease, transform 0.7s ease;
  }
  .reveal.visible { opacity: 1; transform: translateY(0); }

  /* Top nav bar */
  .topnav {
    position: fixed;
    top: 0; left: 0; right: 0;
    z-index: 100;
    padding: 14px 0;
    background: rgba(26,10,16,0.8);
    backdrop-filter: blur(20px);
    border-bottom: 1px solid rgba(255,20,147,0.1);
  }
  .topnav-inner {
    max-width: 1100px;
    margin: 0 auto;
    padding: 0 30px;
    display: flex;
    align-items: center;
    justify-content: space-between;
  }
  .topnav-logo {
    font-family: var(--display);
    font-size: 18px;
    font-weight: 900;
    color: var(--pink-hot);
    font-style: italic;
  }
  .topnav-links {
    display: flex;
    gap: 28px;
    list-style: none;
  }
  .topnav-links a {
    font-family: var(--mono);
    font-size: 12px;
    color: rgba(255,182,193,0.6);
    text-decoration: none;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    transition: color 0.2s;
  }
  .topnav-links a:hover { color: var(--pink-hot); }

  .available-pill {
    display: flex;
    align-items: center;
    gap: 6px;
    font-family: var(--mono);
    font-size: 11px;
    color: #4ade80;
    background: rgba(74,222,128,0.1);
    border: 1px solid rgba(74,222,128,0.3);
    padding: 5px 12px;
    border-radius: 100px;
  }
  .available-dot { width: 6px; height: 6px; background: #4ade80; border-radius: 50%; animation: pulse 2s ease-in-out infinite; }

  /* Animations */
  @keyframes fadeIn { from { opacity: 0; } to { opacity: 1; } }
  @keyframes fadeInUp { from { opacity: 0; transform: translateY(20px); } to { opacity: 1; transform: translateY(0); } }

  /* Responsive */
  @media (max-width: 768px) {
    .hero-inner { grid-template-columns: 1fr; }
    .hero-visual { display: none; }
    .projects-grid { grid-template-columns: 1fr; }
    .cert-grid { grid-template-columns: 1fr; }
  }

  .github-link-big {
    display: inline-flex;
    align-items: center;
    gap: 10px;
    background: linear-gradient(135deg, var(--pink-hot), var(--pink-deep));
    color: var(--white);
    text-decoration: none;
    padding: 16px 36px;
    border-radius: 12px;
    font-weight: 800;
    font-size: 16px;
    letter-spacing: 0.02em;
    box-shadow: 0 8px 32px rgba(255,20,147,0.4);
    transition: all 0.3s;
    margin-top: 20px;
  }
  .github-link-big:hover { transform: translateY(-4px) scale(1.02); box-shadow: 0 16px 48px rgba(255,20,147,0.5); }
</style>
</head>
<body>

<div class="cursor" id="cursor"></div>
<div class="cursor-dot" id="cursorDot"></div>
<div class="bg-grid"></div>
<div class="noise"></div>
<div class="orb orb-1"></div>
<div class="orb orb-2"></div>
<div class="orb orb-3"></div>

<!-- TOP NAV -->
<nav class="topnav">
  <div class="topnav-inner">
    <div class="topnav-logo">PS.</div>
    <ul class="topnav-links">
      <li><a href="#about">About</a></li>
      <li><a href="#projects">Projects</a></li>
      <li><a href="#skills">Skills</a></li>
      <li><a href="#achievements">Beyond Code</a></li>
      <li><a href="#contact">Contact</a></li>
    </ul>
    <div class="available-pill">
      <span class="available-dot"></span>
      Open to Opportunities
    </div>
  </div>
</nav>

<!-- HERO -->
<section class="hero" id="about">
  <div class="container">
    <div class="hero-inner">
      <div class="hero-left">
        <div class="hero-tag">✦ github.com/pratikshasharma23</div>
        <h1 class="hero-name">
          <span class="line-1">Pratiksha</span>
          <span class="line-2">Sharma.</span>
        </h1>
        <p class="hero-title">// Full-Stack Developer · AI Enthusiast · KIIT University '27</p>
        <p class="hero-bio">
          <strong>3rd-year CSE student</strong> building production-grade web apps with React, Node.js & MongoDB. I love crafting <strong>AI-integrated</strong> experiences with clean architecture, real-time features & slick UIs.
        </p>
        <div class="hero-stats">
          <div class="stat-item">
            <span class="stat-num">9.01</span>
            <span class="stat-label">CGPA</span>
          </div>
          <div class="stat-item">
            <span class="stat-num">2+</span>
            <span class="stat-label">Projects</span>
          </div>
          <div class="stat-item">
            <span class="stat-num">2</span>
            <span class="stat-label">Certs</span>
          </div>
          <div class="stat-item">
            <span class="stat-num">🖤</span>
            <span class="stat-label">Black Belt</span>
          </div>
        </div>
        <div class="hero-links">
          <a class="hero-btn primary" href="https://github.com/pratikshasharma23" target="_blank">
            <svg width="16" height="16" fill="currentColor" viewBox="0 0 24 24"><path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/></svg>
            View GitHub
          </a>
          <a class="hero-btn ghost" href="https://www.linkedin.com/in/pratiksha-sharma23" target="_blank">
            <svg width="16" height="16" fill="currentColor" viewBox="0 0 24 24"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433c-1.144 0-2.063-.926-2.063-2.065 0-1.138.92-2.063 2.063-2.063 1.14 0 2.064.925 2.064 2.063 0 1.139-.925 2.065-2.064 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
            LinkedIn
          </a>
          <a class="hero-btn ghost" href="mailto:sharma.pratiksha2302@gmail.com">
            📧 Email Me
          </a>
        </div>
      </div>

      <div class="hero-visual">
        <div class="floating-badges">
          <div class="badge"><span class="badge-dot"></span>React · Node.js</div>
          <div class="badge"><span class="badge-dot"></span>9.01 CGPA</div>
          <div class="badge"><span class="badge-dot"></span>KIIT Univ '27</div>
          <div class="badge"><span class="badge-dot"></span>AI · Docker</div>
        </div>
        <div class="avatar-ring">
          <div class="avatar-inner">PS</div>
        </div>
      </div>
    </div>
  </div>
</section>

<div class="divider"></div>

<!-- PROJECTS -->
<section id="projects">
  <div class="container">
    <div class="reveal">
      <div class="section-label">// Featured Work</div>
      <h2 class="section-title">What I've <span class="accent">Built</span></h2>
    </div>
    <div class="projects-grid reveal">

      <!-- Project 1 -->
      <div class="project-card" id="chatty-card">
        <div class="project-number">01</div>
        <div class="project-icon">💬</div>
        <div class="project-name">Chatty</div>
        <div class="project-subtitle">Full-Stack Real-Time Chat App</div>
        <p class="project-desc">
          A scalable real-time messaging platform with JWT-based authentication, live presence indicators & media uploads. Built end-to-end from auth to deployment.
        </p>
        <div class="project-stack">
          <span class="stack-tag">React</span>
          <span class="stack-tag">Node.js</span>
          <span class="stack-tag">Express.js</span>
          <span class="stack-tag">MongoDB</span>
          <span class="stack-tag">Socket.io</span>
          <span class="stack-tag">JWT</span>
          <span class="stack-tag">Cloudinary</span>
          <span class="stack-tag">REST API</span>
        </div>
        <div class="project-links">
          <a class="proj-link" href="https://github.com/pratikshasharma23/fullstack-chat-app" target="_blank">
            <svg width="14" height="14" fill="currentColor" viewBox="0 0 24 24"><path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/></svg>
            GitHub Repo
          </a>
        </div>
      </div>

      <!-- Project 2 -->
      <div class="project-card">
        <div class="project-number">02</div>
        <div class="project-icon">🤖</div>
        <div class="project-name">ResumeLift</div>
        <div class="project-subtitle">AI-Powered Resume Builder</div>
        <p class="project-desc">
          AI-integrated resume builder leveraging Google Gemini for intelligent content generation. Production-ready with Docker containerisation & GitHub Actions CI/CD.
        </p>
        <div class="project-stack">
          <span class="stack-tag">React (Vite)</span>
          <span class="stack-tag">Tailwind CSS</span>
          <span class="stack-tag">Node.js</span>
          <span class="stack-tag">Express</span>
          <span class="stack-tag">MongoDB</span>
          <span class="stack-tag">Docker</span>
          <span class="stack-tag">GitHub Actions</span>
          <span class="stack-tag">Gemini AI</span>
        </div>
        <div class="project-links">
          <a class="proj-link" href="https://github.com/pratikshasharma23" target="_blank">
            <svg width="14" height="14" fill="currentColor" viewBox="0 0 24 24"><path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/></svg>
            GitHub
          </a>
        </div>
      </div>

    </div>
  </div>
</section>

<div class="divider"></div>

<!-- SKILLS -->
<section id="skills">
  <div class="container">
    <div class="reveal">
      <div class="section-label">// Tech Arsenal</div>
      <h2 class="section-title">Skills & <span class="accent">Stack</span></h2>
    </div>
    <div class="skills-grid reveal">
      <div class="skill-card">
        <div class="skill-card-title">🖥️ Languages</div>
        <div class="skill-tags">
          <span class="skill-tag">JavaScript</span>
          <span class="skill-tag">Python</span>
          <span class="skill-tag">Java</span>
          <span class="skill-tag">C</span>
          <span class="skill-tag">SQL</span>
        </div>
      </div>
      <div class="skill-card">
        <div class="skill-card-title">⚛️ Frontend</div>
        <div class="skill-tags">
          <span class="skill-tag">React.js</span>
          <span class="skill-tag">Next.js</span>
          <span class="skill-tag">Tailwind CSS</span>
          <span class="skill-tag">HTML5</span>
          <span class="skill-tag">Vite</span>
        </div>
      </div>
      <div class="skill-card">
        <div class="skill-card-title">🔧 Backend</div>
        <div class="skill-tags">
          <span class="skill-tag">Node.js</span>
          <span class="skill-tag">Express.js</span>
          <span class="skill-tag">Django</span>
          <span class="skill-tag">Socket.io</span>
          <span class="skill-tag">REST API</span>
          <span class="skill-tag">JWT Auth</span>
        </div>
      </div>
      <div class="skill-card">
        <div class="skill-card-title">🗄️ Databases</div>
        <div class="skill-tags">
          <span class="skill-tag">MongoDB</span>
          <span class="skill-tag">MySQL</span>
          <span class="skill-tag">Cloudinary</span>
        </div>
      </div>
      <div class="skill-card">
        <div class="skill-card-title">🚀 DevOps & Tools</div>
        <div class="skill-tags">
          <span class="skill-tag">Docker</span>
          <span class="skill-tag">GitHub Actions</span>
          <span class="skill-tag">Git</span>
          <span class="skill-tag">CI/CD</span>
          <span class="skill-tag">VS Code</span>
          <span class="skill-tag">IntelliJ</span>
        </div>
      </div>
      <div class="skill-card">
        <div class="skill-card-title">🧠 CS Fundamentals</div>
        <div class="skill-tags">
          <span class="skill-tag">DSA</span>
          <span class="skill-tag">OOP</span>
          <span class="skill-tag">OS</span>
          <span class="skill-tag">Computer Networks</span>
          <span class="skill-tag">System Design</span>
        </div>
      </div>
    </div>
  </div>
</section>

<div class="divider"></div>

<!-- EDUCATION -->
<section id="education">
  <div class="container">
    <div class="reveal">
      <div class="section-label">// Academic Journey</div>
      <h2 class="section-title">Edu<span class="accent">cation</span></h2>
    </div>
    <div class="timeline reveal">
      <div class="timeline-item">
        <div class="timeline-dot"></div>
        <div class="timeline-date">Jul 2023 – Aug 2027</div>
        <div class="timeline-org">KIIT University</div>
        <div class="timeline-role">B.Tech — Computer Science & Engineering · Bhubaneswar, Odisha</div>
        <div class="timeline-detail">Building deep expertise in full-stack development, AI integration, and system design.</div>
        <div class="timeline-badge">⭐ CGPA: 9.01 / 10</div>
      </div>
      <div class="timeline-item">
        <div class="timeline-dot"></div>
        <div class="timeline-date">Jun 2020 – May 2023</div>
        <div class="timeline-org">Delhi Public School, Kolkata</div>
        <div class="timeline-role">Class XII (ISC Board) · Class X (ICSE Board)</div>
        <div class="timeline-detail">Consistent academic excellence across boards.</div>
        <div class="timeline-badge">📚 Class XII: 92.7% · Class X: 96%</div>
      </div>
    </div>
  </div>
</section>

<div class="divider"></div>

<!-- CERTIFICATIONS -->
<section id="certs">
  <div class="container">
    <div class="reveal">
      <div class="section-label">// Verified Learning</div>
      <h2 class="section-title">Certifi<span class="accent">cations</span></h2>
    </div>
    <div class="cert-grid reveal">
      <div class="cert-card">
        <div class="cert-icon">🎓</div>
        <div>
          <div class="cert-name">Database Management Systems</div>
          <div class="cert-issuer">NPTEL · IIT</div>
          <div class="cert-date">Jan 2025 – Mar 2025</div>
        </div>
      </div>
      <div class="cert-card">
        <div class="cert-icon">🤖</div>
        <div>
          <div class="cert-name">AI & Machine Learning with Python</div>
          <div class="cert-issuer">InternsElite</div>
          <div class="cert-date">Aug 2025 – Oct 2025</div>
        </div>
      </div>
    </div>
  </div>
</section>

<div class="divider"></div>

<!-- ACHIEVEMENTS -->
<section id="achievements">
  <div class="container">
    <div class="reveal">
      <div class="section-label">// Beyond The Keyboard</div>
      <h2 class="section-title">I'm More Than <span class="accent">Code</span></h2>
    </div>
    <div class="achievements-grid reveal">
      <div class="achievement-card">
        <span class="achievement-icon">💃</span>
        <div class="achievement-title">IIT Kharagpur — Runner-Up</div>
        <div class="achievement-desc">Took 2nd place at IIT KGP's cultural fest 2025 in dance. Also performed at ISL (Indian Super League).</div>
      </div>
      <div class="achievement-card">
        <span class="achievement-icon">🥋</span>
        <div class="achievement-title">International Karate Competitor</div>
        <div class="achievement-desc">Black Belt in Karate. Represented India at an International Karate Competition.</div>
      </div>
      <div class="achievement-card">
        <span class="achievement-icon">🏸</span>
        <div class="achievement-title">Multi-Sport Athlete</div>
        <div class="achievement-desc">Active in Badminton, Basketball, Athletics & Table Tennis.</div>
      </div>
      <div class="achievement-card">
        <span class="achievement-icon">🌐</span>
        <div class="achievement-title">Multilingual</div>
        <div class="achievement-desc">Fluent in English & Hindi. Conversational in Bengali and Odia.</div>
      </div>
    </div>
  </div>
</section>

<div class="divider"></div>

<!-- CONTACT -->
<section id="contact">
  <div class="container" style="text-align: center;">
    <div class="reveal">
      <div class="section-label" style="justify-content: center; display: flex;">// Let's Connect</div>
      <h2 class="section-title">Get In <span class="accent">Touch</span></h2>
      <p style="font-size: 17px; color: rgba(245,212,224,0.7); max-width: 500px; margin: 0 auto 40px; line-height: 1.7;">Open to internships, collabs & exciting opportunities. Let's build something amazing together! ✨</p>
    </div>
    <div class="contact-row reveal">
      <a class="contact-card" href="mailto:sharma.pratiksha2302@gmail.com">
        <span class="contact-icon">📧</span>
        <div>
          <div class="contact-label">Email</div>
          <div class="contact-value">sharma.pratiksha2302</div>
        </div>
      </a>
      <a class="contact-card" href="https://github.com/pratikshasharma23" target="_blank">
        <span class="contact-icon">
          <svg width="22" height="22" fill="white" viewBox="0 0 24 24"><path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/></svg>
        </span>
        <div>
          <div class="contact-label">GitHub</div>
          <div class="contact-value">pratikshasharma23</div>
        </div>
      </a>
      <a class="contact-card" href="https://www.linkedin.com/in/pratiksha-sharma23" target="_blank">
        <span class="contact-icon">💼</span>
        <div>
          <div class="contact-label">LinkedIn</div>
          <div class="contact-value">pratiksha-sharma23</div>
        </div>
      </a>
      <a class="contact-card" href="tel:+916290169499">
        <span class="contact-icon">📱</span>
        <div>
          <div class="contact-label">Mobile</div>
          <div class="contact-value">+91 62901 69499</div>
        </div>
      </a>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer class="footer">
  <div style="font-size: 24px; margin-bottom: 12px;">🌸</div>
  designed & coded with <span>♥</span> by Pratiksha Sharma · 2026<br>
  <span style="color: rgba(255,182,193,0.2); font-size: 11px; margin-top: 8px; display: block;">// she/her · KIIT University · Bhubaneswar, India</span>
</footer>

<script>
  // Cursor
  const cursor = document.getElementById('cursor');
  const cursorDot = document.getElementById('cursorDot');
  document.addEventListener('mousemove', (e) => {
    cursor.style.left = e.clientX + 'px';
    cursor.style.top = e.clientY + 'px';
    cursorDot.style.left = e.clientX + 'px';
    cursorDot.style.top = e.clientY + 'px';
  });
  document.querySelectorAll('a, button, .skill-tag, .achievement-card, .project-card').forEach(el => {
    el.addEventListener('mouseenter', () => cursor.classList.add('hovering'));
    el.addEventListener('mouseleave', () => cursor.classList.remove('hovering'));
  });

  // Mouse glow on project cards
  document.querySelectorAll('.project-card').forEach(card => {
    card.addEventListener('mousemove', (e) => {
      const rect = card.getBoundingClientRect();
      const x = ((e.clientX - rect.left) / rect.width * 100).toFixed(1);
      const y = ((e.clientY - rect.top) / rect.height * 100).toFixed(1);
      card.style.setProperty('--mx', x + '%');
      card.style.setProperty('--my', y + '%');
    });
  });

  // Scroll reveal
  const reveals = document.querySelectorAll('.reveal');
  const observer = new IntersectionObserver((entries) => {
    entries.forEach((e, i) => {
      if (e.isIntersecting) {
        setTimeout(() => e.target.classList.add('visible'), i * 80);
      }
    });
  }, { threshold: 0.1 });
  reveals.forEach(el => observer.observe(el));

  // Smooth scroll for nav
  document.querySelectorAll('a[href^="#"]').forEach(a => {
    a.addEventListener('click', (e) => {
      e.preventDefault();
      const target = document.querySelector(a.getAttribute('href'));
      if (target) target.scrollIntoView({ behavior: 'smooth', block: 'start' });
    });
  });
</script>
</body>
</html>
