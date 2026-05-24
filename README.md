<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Anvita Shah — Product Designer, Art Director, Artist</title>
<link rel="preconnect" href="https://fonts.googleapis.com" />
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
<link href="https://fonts.googleapis.com/css2?family=Fraunces:ital,opsz,wght@0,9..144,300;0,9..144,400;0,9..144,500;1,9..144,300;1,9..144,400&family=JetBrains+Mono:wght@300;400;500&display=swap" rel="stylesheet" />
<style>
  :root {
    --bg: #f1ede6;
    --bg-soft: #e8e3d8;
    --ink: #1a1a1a;
    --ink-soft: #4a4a48;
    --rule: #cfc8b8;
    --accent: #6b5b3a;
    --serif: "Fraunces", "Cormorant Garamond", Georgia, serif;
    --mono: "JetBrains Mono", "Courier New", monospace;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  html { scroll-behavior: smooth; }

  body {
    background: var(--bg);
    color: var(--ink);
    font-family: var(--mono);
    font-weight: 400;
    font-size: 14px;
    line-height: 1.5;
    overflow-x: hidden;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
  }

  /* ====== Noise overlay ====== */
  body::before {
    content: "";
    position: fixed;
    inset: 0;
    pointer-events: none;
    opacity: 0.04;
    z-index: 1;
    background-image: url("data:image/svg+xml;utf8,<svg viewBox='0 0 200 200' xmlns='http://www.w3.org/2000/svg'><filter id='n'><feTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='3' stitchTiles='stitch'/></filter><rect width='100%' height='100%' filter='url(%23n)'/></svg>");
  }

  /* ====== Top Nav ====== */
  nav {
    position: fixed;
    top: 0; left: 0; right: 0;
    z-index: 100;
    padding: 22px 40px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    font-family: var(--mono);
    font-size: 13px;
    letter-spacing: 0.02em;
    background: rgba(241, 237, 230, 0.85);
    backdrop-filter: blur(8px);
    -webkit-backdrop-filter: blur(8px);
  }

  .logo {
    font-family: var(--serif);
    font-style: italic;
    font-weight: 400;
    font-size: 20px;
    letter-spacing: -0.02em;
    color: var(--ink);
    text-decoration: none;
  }

  .nav-links {
    display: flex;
    gap: 32px;
    align-items: center;
  }

  .nav-links a {
    color: var(--ink);
    text-decoration: none;
    transition: opacity 0.3s ease;
    position: relative;
  }

  .nav-links a:hover { opacity: 0.5; }

  .email-pill {
    display: inline-flex;
    align-items: center;
    gap: 10px;
    padding: 8px 14px;
    border: 1px solid var(--ink);
    border-radius: 999px;
    cursor: pointer;
    background: transparent;
    font-family: var(--mono);
    font-size: 12px;
    color: var(--ink);
    transition: all 0.3s ease;
  }

  .email-pill:hover { background: var(--ink); color: var(--bg); }

  .email-pill .copy { font-style: italic; opacity: 0.6; }

  /* ====== Hero ====== */
  header.hero {
    min-height: 100vh;
    padding: 140px 40px 80px;
    position: relative;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
  }

  .hero-name {
    font-family: var(--serif);
    font-weight: 300;
    font-size: clamp(80px, 17vw, 260px);
    line-height: 0.85;
    letter-spacing: -0.04em;
    color: var(--ink);
  }

  .hero-name .ln1 { display: block; }
  .hero-name .ln2 { display: block; font-style: italic; font-weight: 300; }

  .hero-tags {
    display: flex;
    flex-wrap: wrap;
    gap: 22px 36px;
    margin-top: 40px;
    font-family: var(--mono);
    font-size: 13px;
    color: var(--ink-soft);
  }

  .hero-tags span { position: relative; padding-left: 18px; }
  .hero-tags span::before {
    content: "";
    position: absolute;
    left: 0; top: 50%;
    width: 8px; height: 1px;
    background: var(--ink-soft);
  }

  .hero-meta {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 60px;
    margin-top: 80px;
    align-items: end;
  }

  .hero-intro {
    max-width: 480px;
    font-family: var(--serif);
    font-size: 18px;
    line-height: 1.45;
    color: var(--ink);
    font-weight: 400;
  }

  .hero-intro em { font-style: italic; }

  .hero-profile {
    justify-self: end;
  }

  .hero-profile a {
    color: var(--ink);
    text-decoration: none;
    font-family: var(--mono);
    font-size: 13px;
    padding: 10px 18px;
    border: 1px solid var(--ink);
    border-radius: 999px;
    transition: all 0.3s ease;
    display: inline-block;
  }

  .hero-profile a:hover { background: var(--ink); color: var(--bg); }

  /* ====== Section labels ====== */
  .section-label {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 24px 40px;
    border-top: 1px solid var(--rule);
    font-family: var(--mono);
    font-size: 12px;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    color: var(--ink-soft);
  }

  .section-label .label-tag {
    font-family: var(--serif);
    font-style: italic;
    font-size: 15px;
    text-transform: none;
    letter-spacing: 0;
    color: var(--ink);
  }

  /* ====== Work List ====== */
  .work {
    padding: 0 40px;
  }

  .project {
    display: grid;
    grid-template-columns: 60px 1fr 1.2fr auto;
    gap: 40px;
    align-items: center;
    padding: 32px 0;
    border-top: 1px solid var(--rule);
    cursor: pointer;
    position: relative;
    transition: padding 0.4s ease;
    text-decoration: none;
    color: inherit;
  }

  .project:last-of-type { border-bottom: 1px solid var(--rule); }

  .project .num {
    font-family: var(--mono);
    font-size: 13px;
    color: var(--ink-soft);
  }

  .project .num::before { content: "["; }
  .project .num::after { content: "]"; }

  .project .title {
    font-family: var(--serif);
    font-weight: 400;
    font-size: clamp(28px, 4vw, 48px);
    line-height: 1;
    letter-spacing: -0.02em;
    transition: transform 0.5s cubic-bezier(0.2, 0.8, 0.2, 1);
  }

  .project .descriptor {
    font-family: var(--serif);
    font-style: italic;
    font-weight: 300;
    font-size: 18px;
    color: var(--ink-soft);
  }

  .project .meta {
    font-family: var(--mono);
    font-size: 12px;
    color: var(--ink-soft);
    text-align: right;
    letter-spacing: 0.04em;
  }

  .project .meta .tags {
    display: block;
    margin-bottom: 4px;
  }

  .project .arrow {
    display: inline-block;
    transition: transform 0.4s ease;
    margin-left: 6px;
  }

  .project:hover {
    background: var(--bg-soft);
    padding-left: 24px;
    padding-right: 24px;
  }

  .project:hover .title { transform: translateX(8px); }
  .project:hover .arrow { transform: translateX(6px) rotate(-45deg); }

  /* Floating preview thumb */
  .project .preview {
    position: absolute;
    right: 100%;
    top: 50%;
    transform: translate(20px, -50%) scale(0.85);
    width: 220px;
    height: 150px;
    pointer-events: none;
    opacity: 0;
    transition: opacity 0.4s ease, transform 0.6s cubic-bezier(0.2,0.8,0.2,1);
    background: var(--bg-soft);
    border-radius: 4px;
    overflow: hidden;
    z-index: 2;
    display: flex;
    align-items: center;
    justify-content: center;
    font-family: var(--serif);
    font-style: italic;
    color: var(--ink);
    font-size: 14px;
  }

  .project:hover .preview {
    opacity: 1;
    transform: translate(-10px, -50%) scale(1);
  }

  /* Preview gradients (per project) */
  .pv-1  { background: linear-gradient(135deg, #2a2a2a, #555); color: #f1ede6; }
  .pv-2  { background: linear-gradient(135deg, #d4c2a0, #a08d63); }
  .pv-3  { background: linear-gradient(135deg, #1a3a3a, #2d5a5a); color: #f1ede6; }
  .pv-4  { background: linear-gradient(135deg, #3a2a2a, #8a5a4a); color: #f1ede6; }
  .pv-5  { background: linear-gradient(135deg, #c8b89a, #8a7860); }
  .pv-6  { background: linear-gradient(135deg, #f5d4c2, #d49a8a); }
  .pv-7  { background: linear-gradient(135deg, #2a3a4a, #5a7090); color: #f1ede6; }
  .pv-8  { background: linear-gradient(135deg, #f5e8d8, #c8b09a); }
  .pv-9  { background: linear-gradient(135deg, #4a3a5a, #8a7aa0); color: #f1ede6; }
  .pv-10 { background: linear-gradient(135deg, #d4a890, #8a5a4a); }
  .pv-11 { background: linear-gradient(135deg, #1a1a1a, #3a3a3a); color: #f1ede6; }
  .pv-12 { background: linear-gradient(135deg, #6a5a3a, #b89a6a); }
  .pv-13 { background: linear-gradient(135deg, #8a4a3a, #c87060); color: #f1ede6; }

  /* ====== About preview band ====== */
  .about-band {
    padding: 120px 40px;
    border-top: 1px solid var(--rule);
    display: grid;
    grid-template-columns: 1fr 1.2fr;
    gap: 80px;
    align-items: start;
  }

  .about-band h2 {
    font-family: var(--serif);
    font-weight: 300;
    font-size: clamp(40px, 6vw, 88px);
    line-height: 0.95;
    letter-spacing: -0.03em;
  }

  .about-band h2 em { font-style: italic; font-weight: 300; }

  .about-band .body {
    font-family: var(--serif);
    font-size: 20px;
    line-height: 1.5;
    color: var(--ink);
    font-weight: 400;
  }

  .about-band .body p + p { margin-top: 22px; }

  .about-band .body p em {
    font-style: italic;
    color: var(--accent);
  }

  /* ====== Experience ====== */
  .experience {
    padding: 80px 40px 120px;
    border-top: 1px solid var(--rule);
  }

  .exp-header {
    display: flex;
    justify-content: space-between;
    align-items: baseline;
    margin-bottom: 60px;
    font-family: var(--mono);
    font-size: 12px;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    color: var(--ink-soft);
  }

  .exp-header .label-tag {
    font-family: var(--serif);
    font-style: italic;
    font-size: 22px;
    text-transform: none;
    letter-spacing: 0;
    color: var(--ink);
  }

  .exp-list {
    display: flex;
    flex-direction: column;
  }

  .exp-row {
    display: grid;
    grid-template-columns: 60px 1.5fr 1fr 1fr auto;
    gap: 30px;
    padding: 24px 0;
    border-top: 1px solid var(--rule);
    align-items: center;
    transition: padding 0.3s ease;
  }

  .exp-row:last-child { border-bottom: 1px solid var(--rule); }

  .exp-row:hover { padding-left: 16px; padding-right: 16px; background: var(--bg-soft); }

  .exp-row .ex-num {
    font-family: var(--mono);
    font-size: 12px;
    color: var(--ink-soft);
  }
  .exp-row .ex-num::before { content: "["; }
  .exp-row .ex-num::after { content: "]"; }

  .exp-row .ex-company {
    font-family: var(--serif);
    font-size: 24px;
    font-weight: 400;
    letter-spacing: -0.01em;
  }

  .exp-row .ex-role {
    font-family: var(--serif);
    font-style: italic;
    font-size: 16px;
    color: var(--ink-soft);
    font-weight: 300;
  }

  .exp-row .ex-loc {
    font-family: var(--mono);
    font-size: 12px;
    color: var(--ink-soft);
    letter-spacing: 0.03em;
  }

  .exp-row .ex-date {
    font-family: var(--mono);
    font-size: 12px;
    color: var(--ink-soft);
    text-align: right;
    letter-spacing: 0.03em;
    white-space: nowrap;
  }

  /* ====== CTA ====== */
  .cta {
    padding: 140px 40px 60px;
    border-top: 1px solid var(--rule);
    text-align: center;
    position: relative;
  }

  .cta-eyebrow {
    font-family: var(--mono);
    font-size: 12px;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    color: var(--ink-soft);
    margin-bottom: 30px;
  }

  .cta-headline {
    font-family: var(--serif);
    font-weight: 300;
    font-size: clamp(60px, 13vw, 200px);
    line-height: 0.9;
    letter-spacing: -0.04em;
    margin-bottom: 50px;
  }

  .cta-headline em { font-style: italic; }

  .cta-sub {
    font-family: var(--serif);
    font-size: 20px;
    max-width: 540px;
    margin: 0 auto 50px;
    line-height: 1.45;
    color: var(--ink-soft);
  }

  .cta-button {
    display: inline-block;
    padding: 18px 36px;
    border: 1px solid var(--ink);
    border-radius: 999px;
    color: var(--ink);
    text-decoration: none;
    font-family: var(--mono);
    font-size: 13px;
    letter-spacing: 0.04em;
    transition: all 0.4s ease;
    background: transparent;
  }

  .cta-button:hover {
    background: var(--ink);
    color: var(--bg);
    transform: translateY(-3px);
  }

  .cta-button .br-l::before { content: "["; }
  .cta-button .br-r::after  { content: "]"; }

  /* ====== Footer ====== */
  footer {
    padding: 40px 40px 30px;
    border-top: 1px solid var(--rule);
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    gap: 40px;
    align-items: end;
    font-family: var(--mono);
    font-size: 12px;
    color: var(--ink-soft);
    letter-spacing: 0.03em;
  }

  footer .foot-name {
    font-family: var(--serif);
    font-style: italic;
    font-size: 22px;
    color: var(--ink);
  }

  footer .foot-links {
    display: flex;
    flex-direction: column;
    gap: 6px;
  }
  footer .foot-links a {
    color: var(--ink);
    text-decoration: none;
    transition: opacity 0.3s ease;
  }
  footer .foot-links a:hover { opacity: 0.5; }

  footer .foot-meta {
    text-align: right;
  }

  /* ====== Sticky scroll marker (right side) ====== */
  .scroll-marker {
    position: fixed;
    right: 20px;
    top: 50%;
    transform: translateY(-50%) rotate(90deg);
    transform-origin: right center;
    font-family: var(--mono);
    font-size: 10px;
    letter-spacing: 0.3em;
    text-transform: uppercase;
    color: var(--ink-soft);
    z-index: 50;
    pointer-events: none;
    mix-blend-mode: multiply;
  }

  /* ====== Reveal animations ====== */
  .reveal {
    opacity: 0;
    transform: translateY(24px);
    transition: opacity 0.9s ease, transform 0.9s cubic-bezier(0.2, 0.8, 0.2, 1);
  }
  .reveal.in { opacity: 1; transform: translateY(0); }

  /* Hero entrance */
  .hero-name .ln1 { animation: rise 1.1s cubic-bezier(0.2, 0.8, 0.2, 1) both; }
  .hero-name .ln2 { animation: rise 1.1s 0.12s cubic-bezier(0.2, 0.8, 0.2, 1) both; }
  .hero-tags { animation: fade 1.1s 0.45s ease both; }
  .hero-meta { animation: fade 1.1s 0.6s ease both; }

  @keyframes rise {
    from { opacity: 0; transform: translateY(60px); }
    to   { opacity: 1; transform: translateY(0); }
  }
  @keyframes fade {
    from { opacity: 0; transform: translateY(20px); }
    to   { opacity: 1; transform: translateY(0); }
  }

  /* ====== Mobile ====== */
  @media (max-width: 860px) {
    nav { padding: 16px 20px; }
    .nav-links { gap: 18px; font-size: 12px; }
    .email-pill { display: none; }

    header.hero { padding: 110px 20px 60px; }
    .hero-meta { grid-template-columns: 1fr; gap: 30px; margin-top: 50px; }
    .hero-profile { justify-self: start; }
    .hero-tags { gap: 14px 24px; font-size: 12px; }

    .section-label, .work, .about-band, .experience, .cta, footer { padding-left: 20px; padding-right: 20px; }

    .project {
      grid-template-columns: 40px 1fr auto;
      gap: 16px;
      padding: 22px 0;
    }
    .project .descriptor { display: none; }
    .project .meta { font-size: 10px; }
    .project .preview { display: none; }
    .project:hover { padding-left: 12px; padding-right: 12px; }

    .about-band { grid-template-columns: 1fr; gap: 30px; padding: 80px 20px; }
    .about-band .body { font-size: 17px; }

    .exp-row {
      grid-template-columns: 30px 1fr;
      gap: 12px;
      padding: 22px 0;
    }
    .exp-row .ex-role,
    .exp-row .ex-loc,
    .exp-row .ex-date { grid-column: 2; font-size: 11px; }
    .exp-row .ex-company { font-size: 19px; }

    footer { grid-template-columns: 1fr; gap: 20px; }
    footer .foot-meta { text-align: left; }

    .scroll-marker { display: none; }
  }
</style>
</head>
<body>

<!-- ============ NAV ============ -->
<nav>
  <a href="#top" class="logo">AS</a>
  <div class="nav-links">
    <a href="#work">Work</a>
    <a href="#about">About</a>
    <a href="#contact">Let's Talk</a>
    <button class="email-pill" id="emailBtn" aria-label="Copy email">
      <span id="emailText">anvitashah.27.10@gmail.com</span>
      <span class="copy" id="emailCopy">[copy]</span>
    </button>
  </div>
</nav>

<!-- side scroll marker -->
<div class="scroll-marker">— portfolio / 2026</div>

<!-- ============ HERO ============ -->
<header class="hero" id="top">
  <div>
    <h1 class="hero-name">
      <span class="ln1">Anvita</span>
      <span class="ln2">Shah.</span>
    </h1>

    <div class="hero-tags">
      <span>product design</span>
      <span>art direction</span>
      <span>visual identity</span>
      <span>based in New York</span>
    </div>
  </div>

  <div class="hero-meta">
    <p class="hero-intro">
      I'm a product designer, art director, and artist based in <em>New York City</em> — bringing thought and purpose to what I create, and always hoping to make an impact through design.
    </p>
    <div class="hero-profile">
      <a href="#work">[ view selected work ↓ ]</a>
    </div>
  </div>
</header>

<!-- ============ SELECTED WORK ============ -->
<div class="section-label" id="work">
  <span>Selected Work / 2019 — 2026</span>
  <span class="label-tag"><em>product design + art direction</em></span>
</div>

<section class="work">

  <!-- Product Design -->
  <a class="project reveal" href="https://www.anvitashah.com/monkeytilt" target="_blank" rel="noopener">
    <span class="num">01</span>
    <span class="title">Monkey Tilt</span>
    <span class="descriptor">crypto gaming platform</span>
    <span class="meta">
      <span class="tags">product design, brand</span>
      <span>2023 — 2025 <span class="arrow">→</span></span>
    </span>
    <span class="preview pv-1">Monkey Tilt</span>
  </a>

  <a class="project reveal" href="https://www.anvitashah.com/wcma" target="_blank" rel="noopener">
    <span class="num">02</span>
    <span class="title">Williams College Museum of Art</span>
    <span class="descriptor">digital experience</span>
    <span class="meta">
      <span class="tags">product design, ux</span>
      <span>2024 <span class="arrow">→</span></span>
    </span>
    <span class="preview pv-2">WCMA</span>
  </a>

  <a class="project reveal" href="https://www.anvitashah.com/ather-digital" target="_blank" rel="noopener">
    <span class="num">03</span>
    <span class="title">Ather Digital</span>
    <span class="descriptor">versify · music tech</span>
    <span class="meta">
      <span class="tags">ux, brand</span>
      <span>2023 <span class="arrow">→</span></span>
    </span>
    <span class="preview pv-3">Versify</span>
  </a>

  <a class="project reveal" href="https://www.anvitashah.com/monkeytiltmvp" target="_blank" rel="noopener">
    <span class="num">04</span>
    <span class="title">Monkey Tilt MVP</span>
    <span class="descriptor">launch product</span>
    <span class="meta">
      <span class="tags">product design</span>
      <span>2023 <span class="arrow">→</span></span>
    </span>
    <span class="preview pv-4">MVP</span>
  </a>

  <a class="project reveal" href="https://www.anvitashah.com/sensenodes" target="_blank" rel="noopener">
    <span class="num">05</span>
    <span class="title">Sense Nodes</span>
    <span class="descriptor">interaction · research</span>
    <span class="meta">
      <span class="tags">ux research, ixd</span>
      <span>2022 <span class="arrow">→</span></span>
    </span>
    <span class="preview pv-5">Sense Nodes</span>
  </a>

  <a class="project reveal" href="https://www.anvitashah.com/hercules" target="_blank" rel="noopener">
    <span class="num">06</span>
    <span class="title">ClassPass Design System</span>
    <span class="descriptor">hercules · systems</span>
    <span class="meta">
      <span class="tags">design system, product</span>
      <span>2022 <span class="arrow">→</span></span>
    </span>
    <span class="preview pv-6">ClassPass</span>
  </a>

  <a class="project reveal" href="https://www.anvitashah.com/gt-ai" target="_blank" rel="noopener">
    <span class="num">07</span>
    <span class="title">GT AI</span>
    <span class="descriptor">user testing study</span>
    <span class="meta">
      <span class="tags">research, ux</span>
      <span>2022 <span class="arrow">→</span></span>
    </span>
    <span class="preview pv-7">GT AI</span>
  </a>

  <a class="project reveal" href="https://www.anvitashah.com/aloyoga" target="_blank" rel="noopener">
    <span class="num">08</span>
    <span class="title">Alo Yoga Analytics</span>
    <span class="descriptor">data dashboard</span>
    <span class="meta">
      <span class="tags">product, data viz</span>
      <span>2022 <span class="arrow">→</span></span>
    </span>
    <span class="preview pv-8">Alo Yoga</span>
  </a>

  <a class="project reveal" href="https://www.anvitashah.com/procrastination" target="_blank" rel="noopener">
    <span class="num">09</span>
    <span class="title">Procrastination</span>
    <span class="descriptor">thesis · interactive</span>
    <span class="meta">
      <span class="tags">research, concept</span>
      <span>2021 <span class="arrow">→</span></span>
    </span>
    <span class="preview pv-9">Procrastination</span>
  </a>

  <!-- Art Direction -->
  <a class="project reveal" href="https://www.anvitashah.com/wella" target="_blank" rel="noopener">
    <span class="num">10</span>
    <span class="title">Wella Hair Care</span>
    <span class="descriptor">campaign · art direction</span>
    <span class="meta">
      <span class="tags">art direction, campaign</span>
      <span>2022 <span class="arrow">→</span></span>
    </span>
    <span class="preview pv-10">Wella</span>
  </a>

  <a class="project reveal" href="https://www.anvitashah.com/calia" target="_blank" rel="noopener">
    <span class="num">11</span>
    <span class="title">Calia</span>
    <span class="descriptor">dick's sporting goods</span>
    <span class="meta">
      <span class="tags">art direction, brand</span>
      <span>2022 <span class="arrow">→</span></span>
    </span>
    <span class="preview pv-11">Calia</span>
  </a>

  <a class="project reveal" href="https://www.anvitashah.com/badger-rebrand" target="_blank" rel="noopener">
    <span class="num">12</span>
    <span class="title">Badger Agency</span>
    <span class="descriptor">rebrand · identity</span>
    <span class="meta">
      <span class="tags">brand, identity</span>
      <span>2022 <span class="arrow">→</span></span>
    </span>
    <span class="preview pv-12">Badger</span>
  </a>

  <a class="project reveal" href="https://www.anvitashah.com/clairol" target="_blank" rel="noopener">
    <span class="num">13</span>
    <span class="title">Clairol</span>
    <span class="descriptor">campaign · art direction</span>
    <span class="meta">
      <span class="tags">art direction, campaign</span>
      <span>2022 <span class="arrow">→</span></span>
    </span>
    <span class="preview pv-13">Clairol</span>
  </a>

</section>

<!-- ============ ABOUT ============ -->
<div class="section-label">
  <span>About / Bio</span>
  <span class="label-tag"><em>a few words</em></span>
</div>

<section class="about-band" id="about">
  <h2>
    Designer, <em>artist,</em><br/>
    art director.
  </h2>
  <div class="body">
    <p>
      An inquisitive and passionate <em>product designer, art director, and artist</em> based in New York City. I bring thought and purpose to what I create, and always hope to make an impact through design.
    </p>
    <p>
      I've worked with <em>Monkey Tilt, Wella, Calia (Dick's Sporting Goods), Clairol, Vogue, Olay</em> and more — across consumer products, brand systems, editorial, and campaigns.
    </p>
    <p>
      MS in Information Experience Design from <em>Pratt Institute</em>, and a BFA in Communication Design with a specialization in UI/UX and branding from <em>Parsons School of Design</em>.
    </p>
  </div>
</section>

<!-- ============ EXPERIENCE ============ -->
<section class="experience">
  <div class="exp-header">
    <span>Experience / 2019 — 2026</span>
    <span class="label-tag"><em>where I've been</em></span>
  </div>

  <div class="exp-list">
    <div class="exp-row reveal">
      <span class="ex-num">01</span>
      <span class="ex-company">Jade by MK</span>
      <span class="ex-role">Design Consultant</span>
      <span class="ex-loc">Mumbai</span>
      <span class="ex-date">Nov 2025 — Jan 2026</span>
    </div>
    <div class="exp-row reveal">
      <span class="ex-num">02</span>
      <span class="ex-company">Mosaic · Monkey Tilt</span>
      <span class="ex-role">Head of Design</span>
      <span class="ex-loc">Remote</span>
      <span class="ex-date">Sep 2023 — Oct 2025</span>
    </div>
    <div class="exp-row reveal">
      <span class="ex-num">03</span>
      <span class="ex-company">Ather Digital · Versify</span>
      <span class="ex-role">UX / Brand Designer</span>
      <span class="ex-loc">New York</span>
      <span class="ex-date">Mar 2023 — Sep 2023</span>
    </div>
    <div class="exp-row reveal">
      <span class="ex-num">04</span>
      <span class="ex-company">Badger Agency</span>
      <span class="ex-role">Art Director</span>
      <span class="ex-loc">New York</span>
      <span class="ex-date">Sep 2021 — Mar 2023</span>
    </div>
    <div class="exp-row reveal">
      <span class="ex-num">05</span>
      <span class="ex-company">NU Media</span>
      <span class="ex-role">Design Associate</span>
      <span class="ex-loc">New York</span>
      <span class="ex-date">Jun 2021 — Sep 2021</span>
    </div>
    <div class="exp-row reveal">
      <span class="ex-num">06</span>
      <span class="ex-company">BeyonDesign</span>
      <span class="ex-role">Graphic Design Intern</span>
      <span class="ex-loc">Mumbai</span>
      <span class="ex-date">Aug 2020 — Sep 2020</span>
    </div>
    <div class="exp-row reveal">
      <span class="ex-num">07</span>
      <span class="ex-company">Vogue</span>
      <span class="ex-role">Creative Intern</span>
      <span class="ex-loc">Mumbai</span>
      <span class="ex-date">May 2019 — Aug 2019</span>
    </div>
  </div>
</section>

<!-- ============ CTA ============ -->
<section class="cta" id="contact">
  <div class="cta-eyebrow">— Let's work together —</div>
  <h2 class="cta-headline">
    Let's get<br/><em>started.</em>
  </h2>
  <p class="cta-sub">
    Say hi and share a few words about your project. That's all it takes to get started.
  </p>
  <a href="mailto:anvitashah.27.10@gmail.com" class="cta-button">
    <span class="br-l"></span>start a project<span class="br-r"></span>
  </a>
</section>

<!-- ============ FOOTER ============ -->
<footer>
  <div class="foot-name">Anvita Shah</div>
  <div class="foot-links">
    <a href="mailto:anvitashah.27.10@gmail.com">anvitashah.27.10@gmail.com</a>
    <a href="tel:+16464923836">+1 (646) 492 — 3836</a>
  </div>
  <div class="foot-meta">
    © 2026 · New York City
  </div>
</footer>

<script>
  // ===== Reveal on scroll =====
  const io = new IntersectionObserver((entries) => {
    entries.forEach((e) => {
      if (e.isIntersecting) {
        e.target.classList.add('in');
        io.unobserve(e.target);
      }
    });
  }, { threshold: 0.12, rootMargin: '0px 0px -8% 0px' });

  document.querySelectorAll('.reveal').forEach(el => io.observe(el));

  // ===== Email copy =====
  const btn = document.getElementById('emailBtn');
  const txt = document.getElementById('emailText');
  const cpy = document.getElementById('emailCopy');
  btn.addEventListener('click', async () => {
    try {
      await navigator.clipboard.writeText(txt.textContent.trim());
      cpy.textContent = '[got it]';
      setTimeout(() => { cpy.textContent = '[copy]'; }, 1800);
    } catch (e) {
      cpy.textContent = '[copy failed]';
      setTimeout(() => { cpy.textContent = '[copy]'; }, 1800);
    }
  });
</script>

</body>
</html>
# design
