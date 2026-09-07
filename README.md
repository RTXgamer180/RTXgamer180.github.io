
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>xxx-jj_playz | Gaming</title>
  <meta name="description" content="Welcome to xxx-jj_playz — gaming, chaos, and awesome videos.">
  <style>
    :root {
      --bg: #080811;
      --panel: #11111f;
      --panel-2: #17172a;
      --text: #f5f5ff;
      --muted: #aaaac2;
      --accent: #8b5cf6;
      --accent-2: #22d3ee;
      --border: rgba(255,255,255,.1);
    }

    * { box-sizing: border-box; margin: 0; padding: 0; }

    html { scroll-behavior: smooth; }

    body {
      background: var(--bg);
      color: var(--text);
      font-family: Arial, Helvetica, sans-serif;
      line-height: 1.6;
      overflow-x: hidden;
    }

    a { color: inherit; text-decoration: none; }

    /* Animated background */
    .background {
      position: fixed;
      inset: 0;
      z-index: -1;
      overflow: hidden;
      pointer-events: none;
      background:
        radial-gradient(circle at 15% 20%, rgba(139,92,246,.15), transparent 35%),
        radial-gradient(circle at 85% 80%, rgba(34,211,238,.1), transparent 35%),
        var(--bg);
    }

    .background::before {
      content: "";
      position: absolute;
      inset: -50%;
      background-image:
        linear-gradient(rgba(255,255,255,.025) 1px, transparent 1px),
        linear-gradient(90deg, rgba(255,255,255,.025) 1px, transparent 1px);
      background-size: 55px 55px;
      transform: rotate(12deg);
      animation: gridMove 25s linear infinite;
    }

    @keyframes gridMove {
      from { transform: translate(0,0) rotate(12deg); }
      to { transform: translate(55px,55px) rotate(12deg); }
    }

    .container {
      width: min(1100px, calc(100% - 32px));
      margin: auto;
    }

    /* Navigation */
    nav {
      position: sticky;
      top: 0;
      z-index: 10;
      background: rgba(8,8,17,.8);
      backdrop-filter: blur(16px);
      border-bottom: 1px solid var(--border);
    }

    .nav-inner {
      min-height: 72px;
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 20px;
    }

    .logo {
      font-size: 1.25rem;
      font-weight: 900;
      letter-spacing: -1px;
    }

    .logo span { color: var(--accent-2); }

    .nav-links {
      display: flex;
      gap: 24px;
      align-items: center;
      font-size: .9rem;
      color: var(--muted);
    }

    .nav-links a:hover { color: white; }

    .nav-btn {
      background: var(--accent);
      color: white;
      padding: 9px 16px;
      border-radius: 10px;
      font-weight: 700;
    }

    /* Hero */
    .hero {
      min-height: 620px;
      display: flex;
      align-items: center;
      text-align: center;
      padding: 90px 0;
    }

    .hero-content { width: 100%; }

    .tag {
      display: inline-block;
      padding: 7px 14px;
      border: 1px solid rgba(139,92,246,.5);
      background: rgba(139,92,246,.1);
      color: #c4b5fd;
      border-radius: 999px;
      font-size: .8rem;
      font-weight: 700;
      margin-bottom: 24px;
      letter-spacing: 1px;
    }

    h1 {
      font-size: clamp(3rem, 9vw, 6.5rem);
      line-height: .95;
      letter-spacing: -5px;
      font-weight: 1000;
      margin-bottom: 24px;
    }

    h1 .gradient {
      background: linear-gradient(90deg, #a78bfa, #22d3ee);
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
    }

    .hero p {
      max-width: 600px;
      margin: auto;
      color: var(--muted);
      font-size: 1.1rem;
    }

    .buttons {
      display: flex;
      justify-content: center;
      flex-wrap: wrap;
      gap: 12px;
      margin-top: 34px;
    }

    .btn {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      gap: 9px;
      padding: 14px 24px;
      border-radius: 12px;
      font-weight: 800;
      transition: .2s;
      border: 1px solid var(--border);
    }

    .btn:hover { transform: translateY(-3px); }

    .btn-primary {
      background: #ef4444;
      border-color: #ef4444;
      box-shadow: 0 8px 30px rgba(239,68,68,.2);
    }

    .btn-secondary {
      background: var(--panel);
    }

    .btn-secondary:hover { border-color: var(--accent); }

    /* Stats */
    .stats {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 14px;
      margin-bottom: 100px;
    }

    .stat {
      background: rgba(17,17,31,.7);
      border: 1px solid var(--border);
      border-radius: 16px;
      padding: 24px;
      text-align: center;
    }

    .stat strong {
      display: block;
      font-size: 1.8rem;
      color: white;
    }

    .stat span {
      color: var(--muted);
      font-size: .85rem;
    }

    /* Sections */
    section { padding: 80px 0; }

    .section-title {
      font-size: 2rem;
      font-weight: 900;
      letter-spacing: -1px;
      margin-bottom: 8px;
    }

    .section-subtitle {
      color: var(--muted);
      margin-bottom: 30px;
    }

    /* Video cards */
    .videos {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 20px;
    }

    .video-card {
      background: var(--panel);
      border: 1px solid var(--border);
      border-radius: 18px;
      overflow: hidden;
      transition: .25s;
    }

    .video-card:hover {
      transform: translateY(-6px);
      border-color: rgba(139,92,246,.6);
      box-shadow: 0 15px 40px rgba(0,0,0,.2);
    }

    .thumbnail {
      aspect-ratio: 16 / 9;
      background: linear-gradient(135deg, #27204a, #111827);
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 3rem;
      position: relative;
      overflow: hidden;
    }

    .thumbnail::after {
      content: "▶";
      position: absolute;
      inset: 0;
      display: grid;
      place-items: center;
      color: white;
      background: rgba(0,0,0,.2);
      opacity: 0;
      transition: .2s;
    }

    .video-card:hover .thumbnail::after { opacity: 1; }

    .video-info { padding: 18px; }

    .video-info h3 {
      font-size: 1.05rem;
      margin-bottom: 8px;
    }

    .video-info p {
      color: var(--muted);
      font-size: .85rem;
    }

    .video-link {
      display: inline-block;
      margin-top: 14px;
      color: var(--accent-2);
      font-size: .85rem;
      font-weight: 700;
    }

    /* About */
    .about-box {
      display: grid;
      grid-template-columns: 1.2fr .8fr;
      gap: 24px;
      align-items: stretch;
    }

    .about-text, .about-side {
      background: var(--panel);
      border: 1px solid var(--border);
      border-radius: 20px;
      padding: 30px;
    }

    .about-text p {
      color: var(--muted);
      margin-top: 16px;
    }

    .about-side {
      background: linear-gradient(135deg, rgba(139,92,246,.16), rgba(34,211,238,.08));
    }

    .about-side h3 { margin-bottom: 15px; }

    .about-side ul {
      list-style: none;
      color: var(--muted);
    }

    .about-side li {
      margin: 10px 0;
      display: flex;
      gap: 10px;
    }

    .about-side li::before {
      content: "✦";
      color: var(--accent-2);
    }

    /* CTA */
    .cta {
      text-align: center;
      padding: 80px 20px;
      background: linear-gradient(135deg, rgba(139,92,246,.15), rgba(34,211,238,.08));
      border: 1px solid var(--border);
      border-radius: 24px;
      margin-bottom: 80px;
    }

    .cta h2 {
      font-size: clamp(2rem, 5vw, 3rem);
      margin-bottom: 12px;
    }

    .cta p {
      color: var(--muted);
      margin-bottom: 25px;
    }

    /* Footer */
    footer {
      border-top: 1px solid var(--border);
      padding: 35px 0;
      color: var(--muted);
      font-size: .85rem;
    }

    .footer-inner {
      display: flex;
      justify-content: space-between;
      gap: 20px;
      flex-wrap: wrap;
    }

    .socials {
      display: flex;
      gap: 18px;
    }

    .socials a:hover { color: var(--accent-2); }

    @media (max-width: 700px) {
      .nav-links a:not(.nav-btn) { display: none; }

      .hero { min-height: 540px; padding: 70px 0; }

      h1 {
        letter-spacing: -3px;
        font-size: clamp(2.8rem, 14vw, 5rem);
      }

      .hero p { font-size: 1rem; }

      .stats { margin-bottom: 40px; }

      .videos { grid-template-columns: 1fr; }

      .about-box { grid-template-columns: 1fr; }

      section { padding: 55px 0; }

      .footer-inner { justify-content: center; text-align: center; }
    }
  </style>
</head>
<body>

  <div class="background"></div>

  <nav>
    <div class="container nav-inner">
      <a href="#" class="logo">xxx<span>-jj_playz</span></a>

      <div class="nav-links">
        <a href="#videos">Videos</a>
        <a href="#about">About</a>
        <a href="https://www.youtube.com/@xxx-jj_playz" target="_blank" rel="noopener" class="nav-btn">YouTube ↗</a>
      </div>
    </div>
  </nav>

  <main>

    <section class="hero">
      <div class="container hero-content">
        <div class="tag">🎮 WELCOME TO THE CHANNEL</div>

        <h1>
          PLAY.<br>
          <span class="gradient">CHAOS.</span><br>
          REPEAT.
        </h1>

        <p>
          Gaming videos, funny moments, and whatever happens when
          xxx-jj_playz loads into a lobby. 🚀
        </p>

        <div class="buttons">
          <a href="https://www.youtube.com/@xxx-jj_playz" target="_blank" rel="noopener" class="btn btn-primary">
            ▶ WATCH ON YOUTUBE
          </a>
          <a href="#videos" class="btn btn-secondary">
            EXPLORE VIDEOS ↓
          </a>
        </div>
      </div>
    </section>

    <div class="container">
      <div class="stats">
        <div class="stat">
          <strong>🎮</strong>
          <span>Gaming Content</span>
        </div>
        <div class="stat">
          <strong>🔥</strong>
          <span>New Adventures</span>
        </div>
        <div class="stat">
          <strong>💜</strong>
          <span>Join the Community</span>
        </div>
      </div>
    </div>

    <section id="videos">
      <div class="container">
        <h2 class="section-title">Latest Videos</h2>
        <p class="section-subtitle">The latest chaos from the channel.</p>

        <div class="videos">

          <!-- Replace these with your actual video links and titles -->
          <a href="https://www.youtube.com/@xxx-jj_playz" target="_blank" rel="noopener" class="video-card">
            <div class="thumbnail">🎮</div>
            <div class="video-info">
              <h3>NEW VIDEO COMING SOON</h3>
              <p>Check out the channel for the latest uploads.</p>
              <span class="video-link">Watch on YouTube ↗</span>
            </div>
          </a>

          <a href="https://www.youtube.com/@xxx-jj_playz" target="_blank" rel="noopener" class="video-card">
            <div class="thumbnail">⚡</div>
            <div class="video-info">
              <h3>GAMING • FUN • CHAOS</h3>
              <p>More awesome moments coming your way.</p>
              <span class="video-link">Watch on YouTube ↗</span>
            </div>
          </a>

          <a href="https://www.youtube.com/@xxx-jj_playz" target="_blank" rel="noopener" class="video-card">
            <div class="thumbnail">🚀</div>
            <div class="video-info">
              <h3>SUBSCRIBE FOR MORE</h3>
              <p>Don't miss the next adventure.</p>
              <span class="video-link">Visit Channel ↗</span>
            </div>
          </a>

        </div>
      </div>
    </section>

    <section id="about">
      <div class="container">
        <div class="about-box">
          <div class="about-text">
            <h2 class="section-title">About Me</h2>
            <p>
              Yo! I'm <strong>xxx-jj_playz</strong> 👋
              Welcome to my little corner of the internet.
              I make gaming content, share funny moments,
              and have a lot of fun along the way.
            </p>
            <p>
              If you enjoy gaming and a bit of chaos,
              you're in the right place.
            </p>
          </div>

          <div class="about-side">
            <h3>What you'll find here</h3>
            <ul>
              <li>Gaming adventures</li>
              <li>Funny moments</li>
              <li>Epic fails</li>
              <li>New videos & more</li>
            </ul>
          </div>
        </div>
      </div>
    </section>

    <div class="container">
      <div class="cta">
        <h2>READY TO JOIN THE CHAOS?</h2>
        <p>Subscribe and become part of the community.</p>
        <a href="https://www.youtube.com/@xxx-jj_playz" target="_blank" rel="noopener" class="btn btn-primary">
          🔴 SUBSCRIBE ON YOUTUBE
        </a>
      </div>
    </div>

  </main>

  <footer>
    <div class="container footer-inner">
      <div>© 2026 xxx-jj_playz. All rights reserved.</div>
      <div class="socials">
        <a href="https://www.youtube.com/@xxx-jj_playz" target="_blank" rel="noopener">YouTube</a>
        <a href="#about">About</a>
      </div>
    </div>
  </footer>

</body>
</html>
