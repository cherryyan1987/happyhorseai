<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>HappyHorse 1.0 — #1 AI Video Generator on AI Video Arena</title>
  <meta
    name="description"
    content="HappyHorse 1.0 is a multimodal AI model for text-to-image, text-to-video, and image-to-video generation. Try HappyHorse AI now."
  />
  <link rel="icon" href="hapyhorse logo.png" />
  <style>
    :root {
      --bg: #060816;
      --bg2: #0b1023;
      --card: rgba(255, 255, 255, 0.08);
      --border: rgba(255, 255, 255, 0.12);
      --text: #f8fafc;
      --muted: #cbd5e1;
      --primary: #8b5cf6;
      --secondary: #22d3ee;
      --pink: #ec4899;
      --shadow: 0 20px 60px rgba(0, 0, 0, 0.35);
    }

    * {
      box-sizing: border-box;
    }

    html {
      scroll-behavior: smooth;
    }

    body {
      margin: 0;
      font-family: Inter, Arial, sans-serif;
      color: var(--text);
      background:
        radial-gradient(circle at 15% 20%, rgba(139, 92, 246, 0.35), transparent 25%),
        radial-gradient(circle at 85% 15%, rgba(34, 211, 238, 0.25), transparent 20%),
        radial-gradient(circle at 50% 85%, rgba(236, 72, 153, 0.18), transparent 25%),
        linear-gradient(180deg, var(--bg) 0%, var(--bg2) 100%);
      min-height: 100vh;
      overflow-x: hidden;
    }

    body::before {
      content: "";
      position: fixed;
      inset: 0;
      background-image:
        linear-gradient(rgba(255, 255, 255, 0.04) 1px, transparent 1px),
        linear-gradient(90deg, rgba(255, 255, 255, 0.04) 1px, transparent 1px);
      background-size: 38px 38px;
      mask-image: radial-gradient(circle at center, black 35%, transparent 85%);
      pointer-events: none;
    }

    .container {
      width: min(1120px, calc(100% - 32px));
      margin: 0 auto;
      position: relative;
      z-index: 1;
    }

    .navbar {
      padding: 20px 0;
    }

    .nav-inner {
      display: flex;
      justify-content: space-between;
      align-items: center;
      gap: 20px;
      padding: 14px 18px;
      border: 1px solid var(--border);
      background: rgba(255,255,255,0.05);
      backdrop-filter: blur(14px);
      border-radius: 20px;
      box-shadow: var(--shadow);
    }

    .brand {
      display: flex;
      align-items: center;
      gap: 12px;
      font-weight: 700;
      letter-spacing: 0.2px;
      color: var(--text);
      text-decoration: none;
    }

    .logo {
      width: 44px;
      height: 44px;
      border-radius: 14px;
      background: linear-gradient(135deg, var(--primary), var(--secondary));
      display: flex;
      align-items: center;
      justify-content: center;
      padding: 6px;
      box-shadow: 0 10px 30px rgba(139, 92, 246, 0.35);
      flex-shrink: 0;
    }

    .logo img {
      width: 100%;
      height: 100%;
      object-fit: contain;
      border-radius: 8px;
      display: block;
    }

    .brand span {
      font-size: 18px;
    }

    .nav-links {
      display: flex;
      align-items: center;
      gap: 18px;
      flex-wrap: wrap;
    }

    .nav-links a {
      color: var(--muted);
      text-decoration: none;
      font-size: 14px;
      transition: 0.2s ease;
    }

    .nav-links a:hover {
      color: var(--text);
    }

    .btn {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      gap: 10px;
      padding: 14px 22px;
      border-radius: 999px;
      text-decoration: none;
      font-weight: 700;
      transition: 0.25s ease;
      border: 1px solid transparent;
      cursor: pointer;
    }

    .btn:hover {
      transform: translateY(-2px);
    }

    .btn-primary {
      color: white;
      background: linear-gradient(135deg, var(--primary), var(--secondary));
      box-shadow: 0 16px 40px rgba(139, 92, 246, 0.35);
    }

    .btn-secondary {
      color: var(--text);
      background: rgba(255,255,255,0.05);
      border-color: var(--border);
    }

    .hero {
      display: grid;
      grid-template-columns: 1.08fr 0.92fr;
      gap: 28px;
      align-items: center;
      padding: 72px 0 56px;
    }

    .pill {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      padding: 8px 14px;
      border-radius: 999px;
      border: 1px solid var(--border);
      background: rgba(255,255,255,0.05);
      color: #dbeafe;
      font-size: 13px;
      margin-bottom: 20px;
    }

    h1 {
      margin: 0;
      font-size: clamp(38px, 5.4vw, 70px);
      line-height: 1.02;
      letter-spacing: -0.04em;
      max-width: 760px;
    }

    .gradient-text {
      background: linear-gradient(135deg, #ffffff 10%, #a78bfa 40%, #67e8f9 75%, #f9a8d4 100%);
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
    }

    .hero p {
      margin: 22px 0 30px;
      color: var(--muted);
      font-size: 18px;
      line-height: 1.8;
      max-width: 680px;
    }

    .hero-actions {
      display: flex;
      flex-wrap: wrap;
      gap: 14px;
    }

    .hero-note {
      margin-top: 18px;
      color: #cbd5e1;
      font-size: 14px;
    }

    .hero-card {
      position: relative;
      padding: 22px;
      border-radius: 28px;
      border: 1px solid var(--border);
      background: linear-gradient(180deg, rgba(255,255,255,0.08), rgba(255,255,255,0.03));
      backdrop-filter: blur(16px);
      box-shadow: var(--shadow);
      overflow: hidden;
    }

    .hero-card::before {
      content: "";
      position: absolute;
      inset: -1px;
      border-radius: inherit;
      padding: 1px;
      background: linear-gradient(135deg, rgba(139,92,246,0.6), rgba(34,211,238,0.45), rgba(236,72,153,0.35));
      -webkit-mask: linear-gradient(#000 0 0) content-box, linear-gradient(#000 0 0);
      -webkit-mask-composite: xor;
      mask-composite: exclude;
      pointer-events: none;
    }

    .window-bar {
      display: flex;
      gap: 8px;
      margin-bottom: 16px;
    }

    .dot {
      width: 10px;
      height: 10px;
      border-radius: 50%;
      background: rgba(255,255,255,0.35);
    }

    .preview-grid {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 14px;
    }

    .preview-item {
      min-height: 122px;
      border-radius: 20px;
      padding: 16px;
      border: 1px solid rgba(255,255,255,0.08);
      position: relative;
      overflow: hidden;
    }

    .preview-item::after {
      content: "";
      position: absolute;
      width: 120px;
      height: 120px;
      right: -30px;
      bottom: -30px;
      border-radius: 50%;
      background: radial-gradient(circle, rgba(255,255,255,0.18), transparent 70%);
    }

    .art1 { background: linear-gradient(135deg, rgba(139,92,246,0.28), rgba(99,102,241,0.12)); }
    .art2 { background: linear-gradient(135deg, rgba(34,211,238,0.24), rgba(59,130,246,0.10)); }
    .art3 { background: linear-gradient(135deg, rgba(236,72,153,0.24), rgba(139,92,246,0.10)); }
    .art4 { background: linear-gradient(135deg, rgba(255,255,255,0.10), rgba(34,211,238,0.08)); }

    .preview-label {
      font-size: 12px;
      letter-spacing: 0.05em;
      color: #dbeafe;
      text-transform: uppercase;
    }

    .preview-title {
      margin-top: 10px;
      font-size: 18px;
      font-weight: 700;
      line-height: 1.35;
    }

    section {
      padding: 22px 0 44px;
    }

    .section-title {
      margin-bottom: 22px;
    }

    .section-title h2 {
      margin: 0 0 10px;
      font-size: clamp(28px, 4vw, 44px);
      letter-spacing: -0.03em;
    }

    .section-title p {
      margin: 0;
      color: var(--muted);
      line-height: 1.8;
      max-width: 760px;
    }

    .stats,
    .features {
      display: grid;
      gap: 16px;
    }

    .stats {
      grid-template-columns: repeat(3, 1fr);
    }

    .features {
      grid-template-columns: repeat(3, 1fr);
    }

    .card {
      padding: 24px;
      border-radius: 24px;
      background: rgba(255,255,255,0.05);
      border: 1px solid var(--border);
      box-shadow: var(--shadow);
    }

    .card strong {
      display: block;
      font-size: 28px;
      margin-bottom: 8px;
    }

    .card span,
    .card p {
      color: var(--muted);
      line-height: 1.75;
      margin: 0;
    }

    .icon {
      width: 46px;
      height: 46px;
      border-radius: 16px;
      display: grid;
      place-items: center;
      margin-bottom: 16px;
      background: linear-gradient(135deg, rgba(139,92,246,0.28), rgba(34,211,238,0.18));
      border: 1px solid rgba(255,255,255,0.1);
      font-size: 20px;
    }

    .feature-card h3 {
      margin: 0 0 10px;
      font-size: 20px;
    }

    .cta-box {
      padding: 34px;
      border-radius: 30px;
      border: 1px solid var(--border);
      background:
        radial-gradient(circle at top right, rgba(34, 211, 238, 0.18), transparent 28%),
        radial-gradient(circle at bottom left, rgba(139, 92, 246, 0.24), transparent 32%),
        rgba(255,255,255,0.05);
      backdrop-filter: blur(16px);
      box-shadow: var(--shadow);
    }

    .cta-box h2 {
      margin: 0 0 12px;
      font-size: clamp(30px, 4vw, 48px);
    }

    .cta-box p {
      margin: 0 0 24px;
      color: var(--muted);
      line-height: 1.8;
      max-width: 760px;
    }

    footer {
      padding: 0 0 34px;
      color: #94a3b8;
      font-size: 14px;
    }

    .footer-inner {
      padding-top: 20px;
      border-top: 1px solid rgba(255,255,255,0.08);
      display: flex;
      justify-content: space-between;
      gap: 12px;
      flex-wrap: wrap;
    }

    @media (max-width: 980px) {
      .hero,
      .stats,
      .features {
        grid-template-columns: 1fr;
      }
    }

    @media (max-width: 760px) {
      .nav-inner {
        flex-wrap: wrap;
      }

      .nav-links {
        width: 100%;
        justify-content: space-between;
      }

      .preview-grid {
        grid-template-columns: 1fr;
      }

      .hero-card,
      .card,
      .cta-box {
        border-radius: 22px;
      }

      h1 {
        font-size: clamp(34px, 10vw, 54px);
      }
    }
  </style>
</head>
<body>
  <header class="navbar">
    <div class="container">
      <div class="nav-inner">
        <a class="brand" href="https://happyhorseai.site/" target="_blank" rel="noopener noreferrer">
          <div class="logo">
            <img src="hapyhorse logo.png" alt="HappyHorse AI Logo" />
          </div>
          <span>HappyHorse AI</span>
        </a>

        <div class="nav-links">
          <a href="#features">Features</a>
          <a href="#use-cases">Use Cases</a>
          <a href="#launch">Launch</a>
          <a
            class="btn btn-primary"
            href="https://happyhorseai.site/"
            target="_blank"
            rel="noopener noreferrer"
          >
            Try HappyHorse AI
          </a>
        </div>
      </div>
    </div>
  </header>

  <main>
    <section class="hero container">
      <div>
        <div class="pill">🏆 Ranked #1 on AI Video Arena</div>

        <h1>
          HappyHorse 1.0 — #1 AI Video Generator on AI Video Arena
        </h1>

        <p>
          A multimodal AI model for text-to-image, text-to-video, and image-to-video generation.
          Create stunning visuals, cinematic motion, and dynamic content through one fast,
          browser-based workflow.
        </p>

        <div class="hero-actions">
          <a
            class="btn btn-primary"
            href="https://happyhorseai.site/"
            target="_blank"
            rel="noopener noreferrer"
          >
            🚀 Launch App
          </a>
          <a class="btn btn-secondary" href="#features">Explore Features</a>
        </div>

        <div class="hero-note">
          Text → Image · Text → Video · Image → Video
        </div>
      </div>

      <div class="hero-card">
        <div class="window-bar">
          <div class="dot"></div>
          <div class="dot"></div>
          <div class="dot"></div>
        </div>

        <div class="preview-grid">
          <div class="preview-item art1">
            <div class="preview-label">Text to Image</div>
            <div class="preview-title">Generate polished visual outputs</div>
          </div>
          <div class="preview-item art2">
            <div class="preview-label">Text to Video</div>
            <div class="preview-title">Turn prompts into cinematic motion</div>
          </div>
          <div class="preview-item art3">
            <div class="preview-label">Image to Video</div>
            <div class="preview-title">Animate static images into scenes</div>
          </div>
          <div class="preview-item art4">
            <div class="preview-label">Speed</div>
            <div class="preview-title">Fast generations for rapid creation</div>
          </div>
        </div>
      </div>
    </section>

    <section class="container">
      <div class="stats">
        <div class="card">
          <strong>Text → Image</strong>
          <span>Create high-quality AI images from simple prompts.</span>
        </div>
        <div class="card">
          <strong>Text → Video</strong>
          <span>Generate short-form video content with visual coherence.</span>
        </div>
        <div class="card">
          <strong>Image → Video</strong>
          <span>Bring still images to life with dynamic motion and animation.</span>
        </div>
      </div>
    </section>

    <section class="container" id="features">
      <div class="section-title">
        <h2>Built for multimodal visual creation</h2>
        <p>
          HappyHorse 1.0 unifies image and video generation into one streamlined experience,
          helping creators, marketers, and businesses move from idea to output faster.
        </p>
      </div>

      <div class="features">
        <div class="card feature-card">
          <div class="icon">🎨</div>
          <h3>Text-to-Image</h3>
          <p>
            Create promotional visuals, concept art, thumbnails, and social content directly
            from text prompts.
          </p>
        </div>

        <div class="card feature-card">
          <div class="icon">🎬</div>
          <h3>Text-to-Video</h3>
          <p>
            Generate short-form AI video for storytelling, ads, launch content, and creative
            experimentation.
          </p>
        </div>

        <div class="card feature-card">
          <div class="icon">🖼️</div>
          <h3>Image-to-Video</h3>
          <p>
            Transform static images into moving scenes and dynamic visual sequences with
            minimal effort.
          </p>
        </div>
      </div>
    </section>

    <section class="container" id="use-cases">
      <div class="section-title">
        <h2>Designed for real-world use cases</h2>
        <p>
          Use HappyHorse AI to create assets for social media, marketing, product promotion,
          creative testing, and fast visual prototyping.
        </p>
      </div>

      <div class="features">
        <div class="card feature-card">
          <div class="icon">📣</div>
          <h3>Marketing Creatives</h3>
          <p>
            Produce campaign visuals, launch assets, and ad concepts faster than traditional
            creative workflows.
          </p>
        </div>

        <div class="card feature-card">
          <div class="icon">📱</div>
          <h3>Social Content</h3>
          <p>
            Generate images and videos for TikTok, Instagram, YouTube Shorts, and product
            launches.
          </p>
        </div>

        <div class="card feature-card">
          <div class="icon">⚡</div>
          <h3>Rapid Iteration</h3>
          <p>
            Explore multiple visual directions quickly and refine ideas before committing to
            full production.
          </p>
        </div>
      </div>
    </section>

    <section class="container" id="launch">
      <div class="cta-box">
        <h2>Start creating with HappyHorse AI</h2>
        <p>
          Try HappyHorse 1.0 through the HappyHorse AI platform and generate images and videos
          from text and images in seconds.
        </p>
        <a
          class="btn btn-primary"
          href="https://happyhorseai.site/"
          target="_blank"
          rel="noopener noreferrer"
        >
          Go to HappyHorse AI
        </a>
      </div>
    </section>
  </main>

  <footer>
    <div class="container footer-inner">
      <span>© 2026 HappyHorse AI</span>
      <span>HappyHorse 1.0 · Text-to-Image · Text-to-Video · Image-to-Video</span>
    </div>
  </footer>
</body>
</html>
