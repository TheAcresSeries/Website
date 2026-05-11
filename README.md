# Website
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>The Acres Series — Shane Michael Quaker</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,700;1,400&family=Lora:ital,wght@0,400;0,500;1,400&display=swap" rel="stylesheet">
  <style>
    :root {
      --green:   #2a4f24;
      --green-lt:#3d7033;
      --amber:   #c8903a;
      --amber-lt:#e8b870;
      --dark:    #111a0e;
      --cream:   #f4efe3;
      --cream-dk:#e8dfc8;
      --mist:    rgba(244,239,227,0.07);
    }

    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    body {
      background: var(--dark);
      color: var(--cream);
      font-family: 'Lora', serif;
      font-size: 17px;
      line-height: 1.75;
      overflow-x: hidden;
    }

    /* ─── NAV ─────────────────────────────── */
    nav {
      position: fixed;
      top: 0; left: 0; right: 0;
      z-index: 100;
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 1.1rem 3rem;
      background: rgba(17,26,14,0.92);
      backdrop-filter: blur(10px);
      border-bottom: 1px solid rgba(200,144,58,0.2);
    }

    .nav-logo {
      font-family: 'Playfair Display', serif;
      font-size: 1.1rem;
      letter-spacing: 0.12em;
      color: var(--amber);
      text-decoration: none;
      text-transform: uppercase;
    }

    .nav-links {
      display: flex;
      gap: 2.2rem;
      list-style: none;
    }

    .nav-links a {
      color: var(--cream-dk);
      text-decoration: none;
      font-size: 0.85rem;
      letter-spacing: 0.1em;
      text-transform: uppercase;
      transition: color 0.25s;
    }

    .nav-links a:hover { color: var(--amber-lt); }

    /* ─── HERO ────────────────────────────── */
    .hero {
      min-height: 100vh;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      text-align: center;
      padding: 7rem 2rem 5rem;
      position: relative;
      overflow: hidden;
    }

    .hero::before {
      content: '';
      position: absolute;
      inset: 0;
      background:
        radial-gradient(ellipse 80% 60% at 50% 40%, rgba(42,79,36,0.55) 0%, transparent 70%),
        radial-gradient(ellipse 50% 40% at 50% 100%, rgba(200,144,58,0.18) 0%, transparent 70%);
      pointer-events: none;
    }

    .fireflies {
      position: absolute;
      inset: 0;
      overflow: hidden;
      pointer-events: none;
    }

    .ff {
      position: absolute;
      width: 3px; height: 3px;
      border-radius: 50%;
      background: var(--amber-lt);
      opacity: 0;
      animation: fly 8s infinite ease-in-out;
    }

    @keyframes fly {
      0%   { opacity: 0;   transform: translate(0, 0); }
      30%  { opacity: 0.7; }
      70%  { opacity: 0.4; }
      100% { opacity: 0;   transform: translate(var(--tx), var(--ty)); }
    }

    .ff:nth-child(1)  { top:20%; left:10%; --tx:40px;  --ty:-60px; animation-delay:0s;   animation-duration:7s; }
    .ff:nth-child(2)  { top:60%; left:80%; --tx:-30px; --ty:-80px; animation-delay:1s;   animation-duration:9s; }
    .ff:nth-child(3)  { top:35%; left:65%; --tx:20px;  --ty:50px;  animation-delay:2s;   animation-duration:6s; }
    .ff:nth-child(4)  { top:75%; left:25%; --tx:60px;  --ty:-40px; animation-delay:3.5s; animation-duration:8s; }
    .ff:nth-child(5)  { top:15%; left:50%; --tx:-50px; --ty:60px;  animation-delay:0.5s; animation-duration:10s;}
    .ff:nth-child(6)  { top:85%; left:60%; --tx:-20px; --ty:-70px; animation-delay:4s;   animation-duration:7s; }
    .ff:nth-child(7)  { top:50%; left:15%; --tx:70px;  --ty:30px;  animation-delay:2.5s; animation-duration:9s; }
    .ff:nth-child(8)  { top:10%; left:85%; --tx:-60px; --ty:40px;  animation-delay:1.5s; animation-duration:8s; }

    /* repo badge */
    .repo-badge {
      display: inline-flex;
      align-items: center;
      gap: 0.5rem;
      background: rgba(200,144,58,0.12);
      border: 1px solid rgba(200,144,58,0.35);
      border-radius: 20px;
      padding: 0.35rem 1rem;
      font-size: 0.75rem;
      letter-spacing: 0.18em;
      text-transform: uppercase;
      color: var(--amber-lt);
      margin-bottom: 1.6rem;
      position: relative;
      animation: fadeUp 1s ease both;
    }

    .repo-badge::before {
      content: '';
      width: 7px; height: 7px;
      border-radius: 50%;
      background: var(--amber);
      display: inline-block;
    }

    .hero-eyebrow {
      font-size: 0.78rem;
      letter-spacing: 0.25em;
      text-transform: uppercase;
      color: var(--amber);
      margin-bottom: 1.4rem;
      position: relative;
      animation: fadeUp 1s 0.1s ease both;
    }

    .hero-title {
      font-family: 'Playfair Display', serif;
      font-size: clamp(3.2rem, 9vw, 7rem);
      font-weight: 700;
      line-height: 1.05;
      letter-spacing: -0.01em;
      color: var(--cream);
      position: relative;
      animation: fadeUp 1s 0.2s ease both;
    }

    .hero-title em {
      font-style: italic;
      color: var(--amber-lt);
    }

    .hero-rule {
      width: 60px;
      height: 2px;
      background: var(--amber);
      margin: 2rem auto;
      position: relative;
      animation: fadeUp 1s 0.35s ease both;
    }

    .hero-tagline {
      font-style: italic;
      font-size: 1.18rem;
      color: var(--cream-dk);
      max-width: 520px;
      position: relative;
      animation: fadeUp 1s 0.5s ease both;
    }

    .hero-cta {
      margin-top: 2.8rem;
      display: flex;
      gap: 1.2rem;
      flex-wrap: wrap;
      justify-content: center;
      position: relative;
      animation: fadeUp 1s 0.65s ease both;
    }

    /* repo stats row */
    .repo-stats {
      margin-top: 2.8rem;
      display: flex;
      gap: 2rem;
      justify-content: center;
      flex-wrap: wrap;
      position: relative;
      animation: fadeUp 1s 0.8s ease both;
    }

    .repo-stat {
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 0.25rem;
    }

    .repo-stat-value {
      font-family: 'Playfair Display', serif;
      font-size: 1.5rem;
      color: var(--amber-lt);
    }

    .repo-stat-label {
      font-size: 0.7rem;
      letter-spacing: 0.18em;
      text-transform: uppercase;
      color: rgba(244,239,227,0.45);
    }

    .stat-divider {
      width: 1px;
      height: 40px;
      background: rgba(200,144,58,0.2);
      align-self: center;
    }

    .btn {
      display: inline-block;
      padding: 0.8rem 2.2rem;
      font-family: 'Lora', serif;
      font-size: 0.88rem;
      letter-spacing: 0.1em;
      text-transform: uppercase;
      text-decoration: none;
      border-radius: 2px;
      transition: all 0.25s;
      cursor: pointer;
    }

    .btn-primary {
      background: var(--amber);
      color: var(--dark);
      border: 2px solid var(--amber);
    }
    .btn-primary:hover { background: var(--amber-lt); border-color: var(--amber-lt); }

    .btn-ghost {
      background: transparent;
      color: var(--cream);
      border: 2px solid rgba(244,239,227,0.35);
    }
    .btn-ghost:hover { border-color: var(--cream); }

    @keyframes fadeUp {
      from { opacity: 0; transform: translateY(24px); }
      to   { opacity: 1; transform: translateY(0); }
    }

    .scroll-hint {
      position: absolute;
      bottom: 2.5rem;
      left: 50%;
      transform: translateX(-50%);
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 0.5rem;
      opacity: 0.45;
      animation: fadeUp 1s 1.2s ease both;
    }

    .scroll-hint span {
      font-size: 0.72rem;
      letter-spacing: 0.2em;
      text-transform: uppercase;
    }

    .scroll-line {
      width: 1px;
      height: 40px;
      background: linear-gradient(to bottom, var(--amber), transparent);
      animation: scrollPulse 2s infinite;
    }

    @keyframes scrollPulse {
      0%, 100% { opacity: 0.4; }
      50%       { opacity: 1; }
    }

    /* ─── SECTION SHARED ──────────────────── */
    section { padding: 5rem 2rem; }

    .section-inner {
      max-width: 1100px;
      margin: 0 auto;
    }

    .section-label {
      font-size: 0.75rem;
      letter-spacing: 0.25em;
      text-transform: uppercase;
      color: var(--amber);
      margin-bottom: 0.6rem;
    }

    .section-title {
      font-family: 'Playfair Display', serif;
      font-size: clamp(2rem, 4vw, 3rem);
      line-height: 1.15;
      margin-bottom: 1rem;
    }

    .section-divider {
      width: 48px;
      height: 2px;
      background: var(--amber);
      margin-bottom: 1.6rem;
    }

    /* ─── REPOSITORY BRANCHES ─────────────── */
    .branches-section {
      background: linear-gradient(180deg, var(--dark) 0%, #0d1a0a 100%);
    }

    .branches-header {
      display: flex;
      align-items: flex-end;
      justify-content: space-between;
      flex-wrap: wrap;
      gap: 1rem;
      margin-bottom: 3rem;
    }

    .branches-header-text {}

    .branch-count-badge {
      font-size: 0.75rem;
      letter-spacing: 0.12em;
      text-transform: uppercase;
      color: rgba(244,239,227,0.45);
      padding: 0.3rem 0.8rem;
      border: 1px solid rgba(244,239,227,0.12);
      border-radius: 12px;
      align-self: center;
    }

    .branches-list {
      display: flex;
      flex-direction: column;
      gap: 0;
      border: 1px solid rgba(200,144,58,0.18);
      border-radius: 6px;
      overflow: hidden;
    }

    .branch-item {
      display: grid;
      grid-template-columns: 200px 1fr auto;
      align-items: start;
      gap: 2rem;
      padding: 2rem 2.4rem;
      border-bottom: 1px solid rgba(200,144,58,0.1);
      background: rgba(244,239,227,0.02);
      transition: background 0.25s;
      position: relative;
    }

    .branch-item:last-child { border-bottom: none; }

    .branch-item:hover {
      background: rgba(42,79,36,0.12);
    }

    .branch-item::before {
      content: '';
      position: absolute;
      left: 0; top: 0; bottom: 0;
      width: 3px;
      background: linear-gradient(to bottom, var(--green-lt), var(--amber));
      transform: scaleY(0);
      transform-origin: top;
      transition: transform 0.35s;
    }

    .branch-item:hover::before { transform: scaleY(1); }

    .branch-meta {
      display: flex;
      flex-direction: column;
      gap: 0.4rem;
    }

    .branch-icon {
      display: flex;
      align-items: center;
      gap: 0.5rem;
      font-size: 0.72rem;
      letter-spacing: 0.15em;
      text-transform: uppercase;
      color: rgba(200,144,58,0.6);
      margin-bottom: 0.5rem;
    }

    .branch-icon svg {
      width: 14px; height: 14px;
      fill: none;
      stroke: currentColor;
      stroke-width: 1.5;
    }

    .branch-num {
      font-family: 'Playfair Display', serif;
      font-size: 3.5rem;
      font-weight: 700;
      color: rgba(200,144,58,0.1);
      line-height: 1;
      margin-top: -0.5rem;
    }

    .branch-title {
      font-family: 'Playfair Display', serif;
      font-size: 1.65rem;
      color: var(--cream);
      margin-bottom: 0.2rem;
    }

    .branch-setting {
      font-style: italic;
      font-size: 0.85rem;
      color: rgba(244,239,227,0.5);
      margin-bottom: 0.8rem;
    }

    .branch-body {
      font-size: 0.95rem;
      color: rgba(244,239,227,0.75);
      line-height: 1.75;
    }

    .branch-actions {
      display: flex;
      flex-direction: column;
      gap: 0.7rem;
      align-self: start;
      padding-top: 0.3rem;
    }

    .branch-btn {
      display: inline-block;
      padding: 0.5rem 1.2rem;
      font-family: 'Lora', serif;
      font-size: 0.78rem;
      letter-spacing: 0.1em;
      text-transform: uppercase;
      text-decoration: none;
      border-radius: 2px;
      text-align: center;
      white-space: nowrap;
      transition: all 0.25s;
    }

    .branch-btn-primary {
      background: var(--amber);
      color: var(--dark);
      border: 1px solid var(--amber);
    }
    .branch-btn-primary:hover { background: var(--amber-lt); border-color: var(--amber-lt); }

    .branch-btn-ghost {
      background: transparent;
      color: var(--cream-dk);
      border: 1px solid rgba(244,239,227,0.2);
    }
    .branch-btn-ghost:hover { border-color: rgba(244,239,227,0.5); }

    /* ─── THEME BANNER ────────────────────── */
    .theme-section {
      background:
        linear-gradient(135deg, rgba(42,79,36,0.7) 0%, rgba(17,26,14,0.95) 100%);
      border-top: 1px solid rgba(200,144,58,0.2);
      border-bottom: 1px solid rgba(200,144,58,0.2);
    }

    .theme-inner {
      max-width: 900px;
      margin: 0 auto;
      text-align: center;
    }

    .theme-quote {
      font-family: 'Playfair Display', serif;
      font-style: italic;
      font-size: clamp(1.3rem, 3vw, 2rem);
      line-height: 1.5;
      color: var(--cream);
      margin-bottom: 1.5rem;
    }

    .theme-attr {
      font-size: 0.8rem;
      letter-spacing: 0.18em;
      text-transform: uppercase;
      color: var(--amber);
    }

    /* ─── CHARACTERS ──────────────────────── */
    .chars-section {
      background: #0a1508;
    }

    .chars-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(220px, 1fr));
      gap: 1.2rem;
      margin-top: 3rem;
    }

    .char-card {
      padding: 1.6rem 1.4rem;
      border: 1px solid rgba(244,239,227,0.08);
      border-radius: 3px;
      transition: background 0.3s, border-color 0.3s;
    }

    .char-card:hover {
      background: rgba(42,79,36,0.18);
      border-color: rgba(200,144,58,0.25);
    }

    .char-initial {
      width: 44px; height: 44px;
      border-radius: 50%;
      background: linear-gradient(135deg, var(--green), var(--green-lt));
      display: flex;
      align-items: center;
      justify-content: center;
      font-family: 'Playfair Display', serif;
      font-size: 1.3rem;
      color: var(--amber-lt);
      margin-bottom: 1rem;
    }

    .char-name {
      font-family: 'Playfair Display', serif;
      font-size: 1.08rem;
      margin-bottom: 0.35rem;
    }

    .char-role {
      font-size: 0.75rem;
      letter-spacing: 0.1em;
      text-transform: uppercase;
      color: var(--amber);
      margin-bottom: 0.7rem;
    }

    .char-desc {
      font-size: 0.88rem;
      color: rgba(244,239,227,0.65);
      line-height: 1.6;
    }

    /* ─── AUTHOR ──────────────────────────── */
    .author-section {
      background: var(--dark);
    }

    .author-inner {
      max-width: 800px;
      margin: 0 auto;
      display: grid;
      grid-template-columns: 160px 1fr;
      gap: 3rem;
      align-items: center;
    }

    .author-avatar {
      width: 160px; height: 160px;
      border-radius: 50%;
      background: linear-gradient(135deg, var(--green), #1a3318);
      border: 3px solid rgba(200,144,58,0.35);
      display: flex;
      align-items: center;
      justify-content: center;
      font-family: 'Playfair Display', serif;
      font-size: 2.8rem;
      color: var(--amber);
    }

    .author-text .section-label { margin-bottom: 0.4rem; }

    .author-name {
      font-family: 'Playfair Display', serif;
      font-size: 1.9rem;
      margin-bottom: 0.5rem;
    }

    .author-bio {
      font-size: 0.95rem;
      color: rgba(244,239,227,0.75);
      line-height: 1.8;
    }

    /* ─── FOOTER ──────────────────────────── */
    footer {
      background: #060d05;
      border-top: 1px solid rgba(200,144,58,0.15);
      padding: 2.5rem 2rem;
      text-align: center;
    }

    .footer-logo {
      font-family: 'Playfair Display', serif;
      font-size: 1.3rem;
      color: var(--amber);
      margin-bottom: 0.8rem;
    }

    .footer-links {
      display: flex;
      justify-content: center;
      gap: 2rem;
      list-style: none;
      margin-bottom: 1.5rem;
    }

    .footer-links a {
      font-size: 0.8rem;
      letter-spacing: 0.1em;
      text-transform: uppercase;
      color: rgba(244,239,227,0.5);
      text-decoration: none;
      transition: color 0.2s;
    }

    .footer-links a:hover { color: var(--amber-lt); }

    .footer-copy {
      font-size: 0.8rem;
      color: rgba(244,239,227,0.3);
    }

    /* ─── RESPONSIVE ──────────────────────── */
    @media (max-width: 900px) {
      .branch-item {
        grid-template-columns: 1fr;
        gap: 1rem;
      }
      .branch-actions {
        flex-direction: row;
        flex-wrap: wrap;
      }
      .branch-num { font-size: 2.5rem; }
    }

    @media (max-width: 700px) {
      nav { padding: 1rem 1.5rem; }
      .nav-links { gap: 1.2rem; }
      .author-inner { grid-template-columns: 1fr; text-align: center; }
      .author-avatar { margin: 0 auto; }
      .section-divider { margin: 0 auto 1.6rem; }
      .branches-header { flex-direction: column; align-items: flex-start; }
    }
  </style>
</head>
<body>

<!-- NAV -->
<nav>
  <a href="#" class="nav-logo">The Acres Series</a>
  <ul class="nav-links">
    <li><a href="#books">Books</a></li>
    <li><a href="#characters">Characters</a></li>
    <li><a href="#author">Author</a></li>
  </ul>
</nav>

<!-- HERO -->
<section class="hero">
  <div class="fireflies">
    <div class="ff"></div><div class="ff"></div><div class="ff"></div>
    <div class="ff"></div><div class="ff"></div><div class="ff"></div>
    <div class="ff"></div><div class="ff"></div>
  </div>

  <div class="repo-badge">
    <span>Repository</span>
  </div>
  <p class="hero-eyebrow">A trilogy by Shane Michael Quaker</p>
  <h1 class="hero-title">The <em>Acres</em><br>Series</h1>
  <div class="hero-rule"></div>
  <p class="hero-tagline">Some minds travel through time. One girl travels through them all.</p>
  <div class="hero-cta">
    <a href="#books" class="btn btn-primary">Explore the Books</a>
    <a href="#characters" class="btn btn-ghost">Meet the Characters</a>
  </div>

  <div class="repo-stats">
    <div class="repo-stat">
      <span class="repo-stat-value">3</span>
      <span class="repo-stat-label">Branches</span>
    </div>
    <div class="stat-divider"></div>
    <div class="repo-stat">
      <span class="repo-stat-value">2</span>
      <span class="repo-stat-label">Settings</span>
    </div>
    <div class="stat-divider"></div>
    <div class="repo-stat">
      <span class="repo-stat-value">∞</span>
      <span class="repo-stat-label">Timelines</span>
    </div>
    <div class="stat-divider"></div>
    <div class="repo-stat">
      <span class="repo-stat-value">1</span>
      <span class="repo-stat-label">Mind-Traveler</span>
    </div>
  </div>

  <div class="scroll-hint">
    <span>Scroll</span>
    <div class="scroll-line"></div>
  </div>
</section>

<!-- BOOKS / BRANCHES -->
<section class="branches-section" id="books">
  <div class="section-inner">
    <div class="branches-header">
      <div class="branches-header-text">
        <p class="section-label">The Trilogy</p>
        <h2 class="section-title">Three Books.<br>One Unforgettable Journey.</h2>
        <div class="section-divider"></div>
      </div>
      <span class="branch-count-badge">3 branches</span>
    </div>

    <div class="branches-list">

      <!-- Branch 1: Acres -->
      <div class="branch-item">
        <div class="branch-meta">
          <div class="branch-icon">
            <svg viewBox="0 0 24 24"><path d="M6 3v12M6 15a3 3 0 1 0 0 6 3 3 0 0 0 0-6zM18 6a3 3 0 1 0 0-6 3 3 0 0 0 0 6zM6 9c3 0 12 1 12-3" stroke-linecap="round"/></svg>
            Branch
          </div>
          <div class="branch-num">I</div>
          <p class="book-tag" style="font-size:0.72rem;letter-spacing:.18em;text-transform:uppercase;color:var(--amber);margin-bottom:.3rem;">Book One</p>
        </div>
        <div>
          <h3 class="branch-title">Acres</h3>
          <p class="branch-setting">Gettysburg, Pennsylvania · 19th Century &amp; Present Day</p>
          <p class="branch-body">
            Alicia is a sharp-witted, observant teenager living on a sprawling property outside Gettysburg. She has an extraordinary gift — the ability to slip inside the consciousness of others, living or long dead, and experience their world through their own eyes. From her treehouse on the acres, she mind-travels into Russell and Abigail, two siblings navigating daily survival, fishing trips, and sibling bickering along a 19th-century Pennsylvania creek. Back in the present, Alicia juggles her wry family dynamic — her sports-obsessed brother Mason, the perpetually hungry Patrick, and her observant parents Rachel and Kyle — while quietly investigating the mystery of who vandalized her school by spelling out an "A" in forks. Sharp, funny, and layered with historical texture, <em>Acres</em> introduces a narrator unlike any other: one who watches history from the inside out.
          </p>
        </div>
        <div class="branch-actions">
          <a href="acres.html" class="branch-btn branch-btn-primary">Read Synopsis</a>
          <a href="#" class="branch-btn branch-btn-ghost">Learn More</a>
        </div>
      </div>

      <!-- Branch 2: Scar -->
      <div class="branch-item">
        <div class="branch-meta">
          <div class="branch-icon">
            <svg viewBox="0 0 24 24"><path d="M6 3v12M6 15a3 3 0 1 0 0 6 3 3 0 0 0 0-6zM18 6a3 3 0 1 0 0-6 3 3 0 0 0 0 6zM6 9c3 0 12 1 12-3" stroke-linecap="round"/></svg>
            Branch
          </div>
          <div class="branch-num">II</div>
          <p class="book-tag" style="font-size:0.72rem;letter-spacing:.18em;text-transform:uppercase;color:var(--amber);margin-bottom:.3rem;">Book Two</p>
        </div>
        <div>
          <h3 class="branch-title">Scar</h3>
          <p class="branch-setting">Savannah, Georgia · The Historic District</p>
          <p class="branch-body">
            When the family embarks on an eleven-hour road trip south to Savannah to visit Alicia's cousin Daphne, the story shifts into something richer and stranger. Alicia's mind-travel abilities deepen in Daphne's centuries-old home near the city's famous squares. She discovers a lighthouse tunnel, a hidden archive of names carved in stone, and begins to communicate with the ghost of Emma Lou Riley — known by the daisies always tucked into her hair — who died far too young and was buried under the wrong name. As Alicia unravels Emma's identity, she also navigates ocean voyages gone wrong through the minds of strangers, witnesses grief at a graveside funeral, and wonders how the living and the dead remember each other. Meanwhile, back in Pennsylvania, Michael and Travis face juvenile court for the school prank. <em>Scar</em> is about what history leaves behind — names on stones, flowers in hair, and the marks that remain long after a person is gone.
          </p>
        </div>
        <div class="branch-actions">
          <a href="scar.html" class="branch-btn branch-btn-primary">Read Synopsis</a>
          <a href="#" class="branch-btn branch-btn-ghost">Learn More</a>
        </div>
      </div>

      <!-- Branch 3: Arc -->
      <div class="branch-item">
        <div class="branch-meta">
          <div class="branch-icon">
            <svg viewBox="0 0 24 24"><path d="M6 3v12M6 15a3 3 0 1 0 0 6 3 3 0 0 0 0-6zM18 6a3 3 0 1 0 0-6 3 3 0 0 0 0 6zM6 9c3 0 12 1 12-3" stroke-linecap="round"/></svg>
            Branch
          </div>
          <div class="branch-num">III</div>
          <p class="book-tag" style="font-size:0.72rem;letter-spacing:.18em;text-transform:uppercase;color:var(--amber);margin-bottom:.3rem;">Book Three</p>
        </div>
        <div>
          <h3 class="branch-title">Arc</h3>
          <p class="branch-setting">Gettysburg, Pennsylvania · The Acres &amp; Below</p>
          <p class="branch-body">
            Back home on the acres for the Fourth of July, Alicia is settled, sun-warmed, and surrounded by friends and family. Daphne has made the trip North. The siblings are in full summer mode. But Alicia's mind-travels into Russell and Abigail take a turn toward the dangerous — leading her deeper underground than she has ever gone, into a hidden crystal cave beneath the property where the walls hold entire landscapes, the ceiling maps the night sky, and children's voices echo an old nursery rhyme. When Abigail begins to sink into the shifting ground and Russell dives after her without hesitation, the line between past and present blurs in ways Alicia cannot undo. <em>Arc</em> is the series at its most thrilling and emotional — a summer story that ends in the deep dark, and a final image that will stay with readers long after the last page. The arc of the series bends toward courage, history, and the strange, fierce love between siblings across centuries.
          </p>
        </div>
        <div class="branch-actions">
          <a href="arc.html" class="branch-btn branch-btn-primary">Read Synopsis</a>
          <a href="#" class="branch-btn branch-btn-ghost">Learn More</a>
        </div>
      </div>

    </div>
  </div>
</section>

<!-- THEME QUOTE -->
<section class="theme-section">
  <div class="theme-inner">
    <p class="theme-quote">"Mind-traveling can be so boring sometimes. Watching people fish is not my cup of tea. At least the acres look nice."</p>
    <p class="theme-attr">— Alicia, Acres: Book One</p>
  </div>
</section>

<!-- CHARACTERS -->
<section class="chars-section" id="characters">
  <div class="section-inner">
    <p class="section-label">The Cast</p>
    <h2 class="section-title">Characters</h2>
    <div class="section-divider"></div>

    <div class="chars-grid">

      <div class="char-card">
        <div class="char-initial">A</div>
        <h4 class="char-name">Alicia</h4>
        <p class="char-role">Narrator · Mind-Traveler</p>
        <p class="char-desc">Sharp, sarcastic, and perceptive. Her extraordinary ability to enter other people's consciousness makes her witness to history — whether she wants to be or not.</p>
      </div>

      <div class="char-card">
        <div class="char-initial">R</div>
        <h4 class="char-name">Russell</h4>
        <p class="char-role">19th Century · The Acres</p>
        <p class="char-desc">A stubborn, funny boy who can't spell his own name but would walk into the earth itself to protect his sister. Alicia's favorite mind-travel host.</p>
      </div>

      <div class="char-card">
        <div class="char-initial">Ab</div>
        <h4 class="char-name">Abigail</h4>
        <p class="char-role">19th Century · The Acres</p>
        <p class="char-desc">Russell's quick-tongued younger sister. Smarter than anyone gives her credit for, and brave far beyond what her era would expect of her.</p>
      </div>

      <div class="char-card">
        <div class="char-initial">M</div>
        <h4 class="char-name">Mason</h4>
        <p class="char-role">Alicia's Older Brother</p>
        <p class="char-desc">Cool, unbothered, and master of the staring contest. He has exactly two modes: unbothered and winning.</p>
      </div>

      <div class="char-card">
        <div class="char-initial">P</div>
        <h4 class="char-name">Patrick</h4>
        <p class="char-role">Alicia's Younger Brother</p>
        <p class="char-desc">Enthusiastic, perpetually hungry, and a born negotiator who can extract concessions from his mother with alarming efficiency.</p>
      </div>

      <div class="char-card">
        <div class="char-initial">Mi</div>
        <h4 class="char-name">Michael</h4>
        <p class="char-role">Love Interest</p>
        <p class="char-desc">Thoughtful and quietly romantic. He arranged an "A" in forks across the school lawn — and faced the consequences with dignity when Alicia kept his secret.</p>
      </div>

      <div class="char-card">
        <div class="char-initial">D</div>
        <h4 class="char-name">Daphne</h4>
        <p class="char-role">Cousin · Savannah, GA</p>
        <p class="char-desc">Fearless, hilarious, and an eager partner in ghost-hunting. She lives in a haunted house and treats it as a perk rather than a problem.</p>
      </div>

      <div class="char-card">
        <div class="char-initial">E</div>
        <h4 class="char-name">Emma "Daisy" Riley</h4>
        <p class="char-role">Ghost · Savannah</p>
        <p class="char-desc">Identified by the daisies always tucked into her hair. She wanders Daphne's historic Savannah home — and Alicia promises to plant seeds for her in the North too.</p>
      </div>

    </div>
  </div>
</section>

<!-- AUTHOR -->
<section class="author-section" id="author">
  <div class="author-inner">
    <div class="author-avatar">SQ</div>
    <div class="author-text">
      <p class="section-label">About the Author</p>
      <h2 class="author-name">Shane Michael Quaker</h2>
      <div class="section-divider"></div>
      <p class="author-bio">Shane Michael Quaker is the author of The Acres Series, a coming-of-age trilogy set in Gettysburg, Pennsylvania and Savannah, Georgia. The series follows Alicia, a teenager with the rare ability to mind-travel through time and consciousness, as she uncovers history, family secrets, and the mysteries of the acres she calls home.</p>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <p class="footer-logo">The Acres Series</p>
  <ul class="footer-links">
    <li><a href="#books">Books</a></li>
    <li><a href="#characters">Characters</a></li>
    <li><a href="#author">Author</a></li>
  </ul>
  <p class="footer-copy">© 2025 Shane Michael Quaker. All rights reserved.</p>
</footer>

</body>
</html>
