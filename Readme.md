<!DOCTYPE html>
<html lang="uz">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Winterr | Portfolio</title>

  <!-- Google Fonts -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800&family=Space+Grotesk:wght@500;700&display=swap" rel="stylesheet">

  <style>
    /* =========================
       RESET & BASE
    ========================== */
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    :root {
      --bg: #070b14;
      --bg-2: #0d1320;
      --card: rgba(255,255,255,0.06);
      --card-2: rgba(255,255,255,0.08);
      --stroke: rgba(255,255,255,0.10);
      --text: #f4f7ff;
      --muted: #aab5d0;
      --primary: #7c5cff;
      --primary-2: #39d0ff;
      --accent: #00f0b5;
      --danger: #ff6b81;
      --shadow: 0 20px 60px rgba(0,0,0,.35);
      --radius: 24px;
      --radius-lg: 32px;
      --container: 1180px;
      --blur: blur(16px);
    }

    html {
      scroll-behavior: smooth;
    }

    body {
      font-family: "Inter", sans-serif;
      color: var(--text);
      background:
        radial-gradient(circle at 15% 20%, rgba(124,92,255,.22), transparent 28%),
        radial-gradient(circle at 85% 10%, rgba(57,208,255,.16), transparent 25%),
        radial-gradient(circle at 50% 80%, rgba(0,240,181,.10), transparent 30%),
        linear-gradient(180deg, #060911 0%, #090f1a 35%, #060912 100%);
      min-height: 100vh;
      overflow-x: hidden;
      position: relative;
    }

    a {
      color: inherit;
      text-decoration: none;
    }

    ul {
      list-style: none;
    }

    img {
      max-width: 100%;
      display: block;
    }

    button,
    input,
    textarea {
      font: inherit;
      outline: none;
      border: none;
    }

    .container {
      width: min(100% - 32px, var(--container));
      margin-inline: auto;
    }

    .section {
      padding: 100px 0;
      position: relative;
      z-index: 2;
    }

    .section-title {
      font-family: "Space Grotesk", sans-serif;
      font-size: clamp(28px, 4vw, 48px);
      line-height: 1.05;
      margin-bottom: 14px;
      letter-spacing: -0.03em;
    }

    .section-subtitle {
      max-width: 700px;
      color: var(--muted);
      font-size: 16px;
      line-height: 1.8;
      margin-bottom: 40px;
    }

    .badge {
      display: inline-flex;
      align-items: center;
      gap: 10px;
      padding: 10px 16px;
      border-radius: 999px;
      background: rgba(255,255,255,0.06);
      border: 1px solid rgba(255,255,255,0.10);
      backdrop-filter: var(--blur);
      -webkit-backdrop-filter: var(--blur);
      color: #dce6ff;
      font-size: 14px;
      margin-bottom: 20px;
      box-shadow: var(--shadow);
    }

    .badge::before {
      content: "";
      width: 10px;
      height: 10px;
      border-radius: 50%;
      background: linear-gradient(135deg, var(--primary), var(--primary-2));
      box-shadow: 0 0 18px rgba(124,92,255,.7);
    }

    /* =========================
       FLOATING BACKGROUND
    ========================== */
    .orb {
      position: fixed;
      inset: auto;
      border-radius: 50%;
      filter: blur(70px);
      opacity: .25;
      z-index: 0;
      pointer-events: none;
      animation: floatOrb 12s ease-in-out infinite;
    }

    .orb.one {
      width: 280px;
      height: 280px;
      background: #7c5cff;
      top: 80px;
      left: -60px;
    }

    .orb.two {
      width: 300px;
      height: 300px;
      background: #00d4ff;
      right: -80px;
      top: 240px;
      animation-delay: 1.5s;
    }

    .orb.three {
      width: 240px;
      height: 240px;
      background: #00f0b5;
      left: 40%;
      bottom: 80px;
      animation-delay: 3s;
    }
    @keyframes floatOrb {
      0%, 100% { transform: translateY(0) translateX(0) scale(1); }
      50% { transform: translateY(-25px) translateX(18px) scale(1.08); }
    }

    #snow {
      position: fixed;
      inset: 0;
      z-index: 1;
      pointer-events: none;
    }

    /* =========================
       NAVBAR
    ========================== */
    .navbar-wrap {
      position: sticky;
      top: 16px;
      z-index: 50;
      padding-top: 16px;
    }

    .navbar {
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 20px;
      padding: 14px 18px;
      border-radius: 22px;
      background: rgba(12, 18, 31, 0.58);
      border: 1px solid rgba(255,255,255,0.10);
      backdrop-filter: blur(16px);
      -webkit-backdrop-filter: blur(16px);
      box-shadow: 0 10px 40px rgba(0,0,0,.25);
    }

    .brand {
      display: flex;
      align-items: center;
      gap: 12px;
      font-weight: 800;
      font-size: 18px;
      letter-spacing: -0.02em;
    }

    .brand-logo {
      width: 42px;
      height: 42px;
      border-radius: 14px;
      display: grid;
      place-items: center;
      background:
        linear-gradient(135deg, rgba(124,92,255,.28), rgba(57,208,255,.20)),
        rgba(255,255,255,0.08);
      border: 1px solid rgba(255,255,255,0.12);
      box-shadow: inset 0 1px 0 rgba(255,255,255,.08);
      font-family: "Space Grotesk", sans-serif;
      color: #fff;
    }

    .nav-links {
      display: flex;
      align-items: center;
      gap: 10px;
      flex-wrap: wrap;
    }

    .nav-links a {
      color: #dce4ff;
      padding: 10px 14px;
      border-radius: 14px;
      font-size: 14px;
      transition: .25s ease;
    }

    .nav-links a:hover {
      background: rgba(255,255,255,0.06);
      color: #fff;
    }

    .nav-cta {
      display: flex;
      align-items: center;
      gap: 12px;
    }

    .btn {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      gap: 10px;
      padding: 14px 20px;
      border-radius: 16px;
      cursor: pointer;
      transition: transform .25s ease, box-shadow .25s ease, background .25s ease;
      font-weight: 600;
      border: 1px solid transparent;
      white-space: nowrap;
    }

    .btn:hover {
      transform: translateY(-2px);
    }

    .btn-primary {
      color: white;
      background: linear-gradient(135deg, var(--primary), var(--primary-2));
      box-shadow: 0 10px 30px rgba(57,208,255,.18), 0 10px 35px rgba(124,92,255,.18);
    }

    .btn-secondary {
      background: rgba(255,255,255,0.06);
      border-color: rgba(255,255,255,0.10);
      color: #eef3ff;
      backdrop-filter: blur(12px);
    }

    .menu-toggle {
      display: none;
      width: 46px;
      height: 46px;
      border-radius: 14px;
      background: rgba(255,255,255,0.06);
      color: white;
      font-size: 20px;
      cursor: pointer;
      border: 1px solid rgba(255,255,255,0.08);
    }

    /* =========================
       HERO
    ========================== */
    .hero {
      padding: 70px 0 90px;
      position: relative;
      z-index: 2;
    }

    .hero-grid {
      display: grid;
      grid-template-columns: 1.15fr .85fr;
      gap: 30px;
      align-items: center;
    }

    .hero-left {
      position: relative;
    }

    .hero-title {
      font-family: "Space Grotesk", sans-serif;
      font-size: clamp(42px, 7vw, 78px);
      line-height: .95;
      letter-spacing: -0.05em;
      margin-bottom: 18px;
      max-width: 850px;
    }

    .hero-title .gradient {
      background: linear-gradient(135deg, #fff, #d9ddff 35%, #8bdff9 65%, #8a7cff 100%);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
    }

    .hero-text {
      max-width: 650px;
      color: var(--muted);
      font-size: 17px;
      line-height: 1.9;
      margin-bottom: 28px;
    }

    .hero-actions {
      display: flex;
      gap: 14px;
      flex-wrap: wrap;
      margin-bottom: 28px;
    }
    .hero-stats {
      display: grid;
      grid-template-columns: repeat(3, minmax(0, 1fr));
      gap: 16px;
      margin-top: 20px;
    }

    .stat-card {
      padding: 20px;
      border-radius: 22px;
      background: rgba(255,255,255,0.05);
      border: 1px solid rgba(255,255,255,0.08);
      backdrop-filter: blur(14px);
      box-shadow: var(--shadow);
    }

    .stat-card h3 {
      font-size: 28px;
      margin-bottom: 6px;
      font-family: "Space Grotesk", sans-serif;
    }

    .stat-card p {
      color: var(--muted);
      font-size: 14px;
    }

    .hero-right {
      position: relative;
    }

    .hero-card {
      position: relative;
      padding: 28px;
      border-radius: var(--radius-lg);
      background:
        linear-gradient(180deg, rgba(255,255,255,.08), rgba(255,255,255,.03));
      border: 1px solid rgba(255,255,255,.10);
      box-shadow: var(--shadow);
      overflow: hidden;
      min-height: 560px;
    }

    .hero-card::before {
      content: "";
      position: absolute;
      inset: 0;
      background:
        radial-gradient(circle at top right, rgba(124,92,255,.24), transparent 28%),
        radial-gradient(circle at bottom left, rgba(57,208,255,.16), transparent 25%);
      pointer-events: none;
    }

    .hero-profile {
      position: relative;
      z-index: 2;
      height: 100%;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
      gap: 22px;
    }

    .profile-top {
      display: flex;
      justify-content: space-between;
      gap: 20px;
      align-items: flex-start;
    }

    .profile-badge {
      padding: 10px 14px;
      border-radius: 999px;
      background: rgba(255,255,255,.06);
      border: 1px solid rgba(255,255,255,.10);
      font-size: 13px;
      color: #dbe6ff;
    }

    .avatar-wrap {
      position: relative;
      width: 100%;
      display: flex;
      justify-content: center;
      margin: 8px 0 6px;
    }

    .avatar-glow {
      position: absolute;
      width: 260px;
      height: 260px;
      border-radius: 50%;
      background: radial-gradient(circle, rgba(124,92,255,.35), transparent 70%);
      filter: blur(30px);
      top: 35px;
    }

    .avatar {
      position: relative;
      width: 250px;
      height: 250px;
      border-radius: 32px;
      background:
        linear-gradient(135deg, rgba(124,92,255,.28), rgba(57,208,255,.18)),
        rgba(255,255,255,.06);
      border: 1px solid rgba(255,255,255,.12);
      box-shadow: inset 0 1px 0 rgba(255,255,255,.10), 0 20px 50px rgba(0,0,0,.25);
      display: grid;
      place-items: center;
      font-size: 72px;
      font-weight: 800;
      font-family: "Space Grotesk", sans-serif;
      letter-spacing: -0.04em;
    }

    .profile-info {
      display: grid;
      gap: 12px;
    }

    .profile-info h3 {
      font-size: 30px;
      font-family: "Space Grotesk", sans-serif;
      letter-spacing: -0.03em;
    }

    .profile-info p {
      color: var(--muted);
      line-height: 1.8;
    }

    .tech-stack {
      display: flex;
      flex-wrap: wrap;
      gap: 12px;
      margin-top: 6px;
    }

    .chip {
      padding: 10px 14px;
      border-radius: 999px;
      background: rgba(255,255,255,.06);
      border: 1px solid rgba(255,255,255,.10);
      color: #e8edff;
      font-size: 13px;
    }

    .mini-grid {
      display: grid;
      grid-template-columns: repeat(2, minmax(0, 1fr));
      gap: 14px;
    }

    .mini-card {
      padding: 18px;
      border-radius: 20px;
      background: rgba(255,255,255,.05);
      border: 1px solid rgba(255,255,255,.08);
    }

    .mini-card h4 {
      margin-bottom: 8px;
      font-size: 16px;
    }

    .mini-card p {
      color: var(--muted);
      font-size: 14px;
      line-height: 1.7;
    }

    /* =========================
       ABOUT
    ========================== */
    .about-grid {
      display: grid;
      grid-template-columns: .9fr 1.1fr;
      gap: 28px;
      align-items: stretch;
    }
    .glass-card {
      background: rgba(255,255,255,0.05);
      border: 1px solid rgba(255,255,255,0.08);
      border-radius: 28px;
      box-shadow: var(--shadow);
      backdrop-filter: blur(14px);
      -webkit-backdrop-filter: blur(14px);
    }

    .about-visual {
      padding: 24px;
      min-height: 480px;
      position: relative;
      overflow: hidden;
    }

    .about-visual::before {
      content: "";
      position: absolute;
      inset: 0;
      background:
        radial-gradient(circle at 20% 20%, rgba(57,208,255,.14), transparent 24%),
        radial-gradient(circle at 80% 80%, rgba(124,92,255,.18), transparent 28%);
      pointer-events: none;
    }

    .visual-box {
      position: relative;
      z-index: 2;
      height: 100%;
      border-radius: 24px;
      padding: 24px;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
      background:
        linear-gradient(180deg, rgba(255,255,255,.06), rgba(255,255,255,.03));
      border: 1px solid rgba(255,255,255,.08);
    }

    .visual-top {
      display: flex;
      justify-content: space-between;
      align-items: center;
      gap: 16px;
      margin-bottom: 18px;
    }

    .dots {
      display: flex;
      gap: 8px;
    }

    .dots span {
      width: 12px;
      height: 12px;
      border-radius: 50%;
      display: block;
      background: rgba(255,255,255,.16);
    }

    .code-screen {
      border-radius: 20px;
      background: #08101c;
      border: 1px solid rgba(255,255,255,.08);
      padding: 18px;
      min-height: 250px;
      font-family: ui-monospace, SFMono-Regular, Menlo, monospace;
      font-size: 13px;
      color: #cfe1ff;
      line-height: 1.8;
      overflow: hidden;
      position: relative;
    }

    .code-line {
      display: block;
      white-space: pre-wrap;
    }

    .code-line .pink { color: #ff87c7; }
    .code-line .blue { color: #6ecfff; }
    .code-line .green { color: #7df7b6; }
    .code-line .yellow { color: #ffe38d; }
    .code-line .purple { color: #b59dff; }

    .about-content {
      padding: 34px;
      display: flex;
      flex-direction: column;
      justify-content: center;
    }

    .about-content p {
      color: var(--muted);
      line-height: 1.95;
      margin-bottom: 16px;
      font-size: 16px;
    }

    .about-list {
      display: grid;
      grid-template-columns: repeat(2, minmax(0, 1fr));
      gap: 14px;
      margin-top: 18px;
    }

    .about-item {
      padding: 18px;
      border-radius: 20px;
      background: rgba(255,255,255,.04);
      border: 1px solid rgba(255,255,255,.08);
    }

    .about-item h4 {
      margin-bottom: 8px;
      font-size: 16px;
    }

    .about-item p {
      margin: 0;
      font-size: 14px;
      line-height: 1.8;
    }

    /* =========================
       SKILLS
    ========================== */
    .skills-grid {
      display: grid;
      grid-template-columns: repeat(4, minmax(0, 1fr));
      gap: 18px;
    }

    .skill-card {
      padding: 24px;
      border-radius: 24px;
      background: rgba(255,255,255,.05);
      border: 1px solid rgba(255,255,255,.08);
      box-shadow: var(--shadow);
      transition: transform .25s ease, border-color .25s ease;
    }

    .skill-card:hover {
      transform: translateY(-6px);
      border-color: rgba(124,92,255,.45);
    }

    .skill-icon {
      width: 58px;
      height: 58px;
      border-radius: 18px;
      display: grid;
      place-items: center;
      margin-bottom: 16px;
      background: linear-gradient(135deg, rgba(124,92,255,.22), rgba(57,208,255,.14));
      border: 1px solid rgba(255,255,255,.08);
      font-size: 24px;
    }

    .skill-card h3 {
      margin-bottom: 10px;
      font-size: 18px;
    }

    .skill-card p {
      color: var(--muted);
      line-height: 1.8;
      font-size: 14px;
      margin-bottom: 18px;
    }

    .progress {
      width: 100%;
      height: 10px;
      border-radius: 999px;
      background: rgba(255,255,255,.06);
      overflow: hidden;
      border: 1px solid rgba(255,255,255,.06);
    }
    .progress span {
      display: block;
      height: 100%;
      border-radius: inherit;
      background: linear-gradient(90deg, var(--primary), var(--primary-2));
    }

    /* =========================
       SERVICES
    ========================== */
    .services-grid {
      display: grid;
      grid-template-columns: repeat(3, minmax(0, 1fr));
      gap: 20px;
    }

    .service-card {
      padding: 28px;
      border-radius: 28px;
      background:
        linear-gradient(180deg, rgba(255,255,255,.06), rgba(255,255,255,.03));
      border: 1px solid rgba(255,255,255,.08);
      box-shadow: var(--shadow);
      position: relative;
      overflow: hidden;
      transition: transform .25s ease, border-color .25s ease;
    }

    .service-card:hover {
      transform: translateY(-6px);
      border-color: rgba(57,208,255,.35);
    }

    .service-card::before {
      content: "";
      position: absolute;
      inset: auto -50px -50px auto;
      width: 160px;
      height: 160px;
      background: radial-gradient(circle, rgba(124,92,255,.22), transparent 70%);
      filter: blur(8px);
    }

    .service-icon {
      width: 64px;
      height: 64px;
      border-radius: 20px;
      display: grid;
      place-items: center;
      background: linear-gradient(135deg, rgba(124,92,255,.22), rgba(57,208,255,.14));
      border: 1px solid rgba(255,255,255,.08);
      margin-bottom: 18px;
      font-size: 26px;
    }

    .service-card h3 {
      margin-bottom: 12px;
      font-size: 20px;
    }

    .service-card p {
      color: var(--muted);
      line-height: 1.85;
      font-size: 15px;
    }

    /* =========================
       PROJECTS
    ========================== */
    .projects-grid {
      display: grid;
      grid-template-columns: repeat(3, minmax(0, 1fr));
      gap: 20px;
    }

    .project-card {
      border-radius: 28px;
      overflow: hidden;
      background: rgba(255,255,255,.05);
      border: 1px solid rgba(255,255,255,.08);
      box-shadow: var(--shadow);
      transition: transform .28s ease, border-color .28s ease;
    }

    .project-card:hover {
      transform: translateY(-6px);
      border-color: rgba(124,92,255,.35);
    }

    .project-cover {
      height: 220px;
      position: relative;
      overflow: hidden;
      background:
        radial-gradient(circle at 20% 20%, rgba(57,208,255,.22), transparent 28%),
        radial-gradient(circle at 80% 80%, rgba(124,92,255,.24), transparent 30%),
        linear-gradient(135deg, #0f1727, #0a1220);
      display: flex;
      align-items: center;
      justify-content: center;
    }

    .project-cover::after {
      content: "";
      position: absolute;
      inset: 0;
      background: linear-gradient(180deg, transparent, rgba(0,0,0,.25));
    }

    .project-shape {
      width: 72%;
      height: 72%;
      border-radius: 28px;
      border: 1px solid rgba(255,255,255,.10);
      background:
        linear-gradient(135deg, rgba(255,255,255,.08), rgba(255,255,255,.02));
      backdrop-filter: blur(10px);
      box-shadow: inset 0 1px 0 rgba(255,255,255,.06);
      position: relative;
      z-index: 2;
      display: grid;
      place-items: center;
      font-family: "Space Grotesk", sans-serif;
      font-size: 26px;
      letter-spacing: -0.03em;
    }

    .project-body {
      padding: 24px;
    }

    .project-tags {
      display: flex;
      flex-wrap: wrap;
      gap: 10px;
      margin-bottom: 14px;
    }

    .project-tags span {
      padding: 8px 12px;
      border-radius: 999px;
      font-size: 12px;
      color: #dfe8ff;
      background: rgba(255,255,255,.05);
      border: 1px solid rgba(255,255,255,.08);
    }

    .project-body h3 {
      font-size: 20px;
      margin-bottom: 12px;
    }

    .project-body p {
      color: var(--muted);
      line-height: 1.85;
      font-size: 15px;
      margin-bottom: 18px;
    }

    .project-links {
      display: flex;
      gap: 12px;
      flex-wrap: wrap;
    }
    .project-link {
      padding: 12px 16px;
      border-radius: 14px;
      background: rgba(255,255,255,.05);
      border: 1px solid rgba(255,255,255,.08);
      transition: .25s ease;
      font-size: 14px;
    }

    .project-link:hover {
      background: rgba(255,255,255,.08);
    }

    /* =========================
       TIMELINE
    ========================== */
    .timeline {
      display: grid;
      gap: 18px;
    }

    .timeline-item {
      padding: 24px;
      border-radius: 24px;
      background: rgba(255,255,255,.05);
      border: 1px solid rgba(255,255,255,.08);
      box-shadow: var(--shadow);
      position: relative;
      overflow: hidden;
    }

    .timeline-item::before {
      content: "";
      position: absolute;
      left: 0;
      top: 24px;
      bottom: 24px;
      width: 4px;
      border-radius: 999px;
      background: linear-gradient(180deg, var(--primary), var(--primary-2));
    }

    .timeline-item-inner {
      padding-left: 18px;
    }

    .timeline-item h3 {
      margin-bottom: 8px;
      font-size: 20px;
    }

    .timeline-meta {
      color: #c6d1ee;
      font-size: 14px;
      margin-bottom: 12px;
    }

    .timeline-item p {
      color: var(--muted);
      line-height: 1.9;
    }

    /* =========================
       CONTACT
    ========================== */
    .contact-grid {
      display: grid;
      grid-template-columns: .9fr 1.1fr;
      gap: 24px;
      align-items: stretch;
    }

    .contact-card,
    .contact-form-wrap {
      padding: 30px;
      border-radius: 28px;
      background: rgba(255,255,255,.05);
      border: 1px solid rgba(255,255,255,.08);
      box-shadow: var(--shadow);
      backdrop-filter: blur(14px);
    }

    .contact-card p {
      color: var(--muted);
      line-height: 1.9;
      margin-bottom: 20px;
    }

    .contact-list {
      display: grid;
      gap: 14px;
    }

    .contact-item {
      display: flex;
      gap: 14px;
      align-items: flex-start;
      padding: 16px;
      border-radius: 20px;
      background: rgba(255,255,255,.04);
      border: 1px solid rgba(255,255,255,.08);
    }

    .contact-icon {
      width: 48px;
      height: 48px;
      border-radius: 16px;
      display: grid;
      place-items: center;
      background: linear-gradient(135deg, rgba(124,92,255,.22), rgba(57,208,255,.14));
      border: 1px solid rgba(255,255,255,.08);
      flex-shrink: 0;
    }

    .contact-item h4 {
      margin-bottom: 6px;
    }

    .contact-item p,
    .contact-item a {
      margin: 0;
      color: var(--muted);
      line-height: 1.8;
      font-size: 14px;
    }

    .contact-form {
      display: grid;
      gap: 16px;
    }

    .form-row {
      display: grid;
      grid-template-columns: repeat(2, minmax(0, 1fr));
      gap: 16px;
    }

    .input,
    .textarea {
      width: 100%;
      border-radius: 18px;
      padding: 16px 18px;
      color: white;
      background: rgba(255,255,255,.05);
      border: 1px solid rgba(255,255,255,.08);
    }

    .textarea {
      min-height: 150px;
      resize: vertical;
    }

    .input::placeholder,
    .textarea::placeholder {
      color: #9fb0d3;
    }

    /* =========================
       FOOTER
    ========================== */
    footer {
      padding: 28px 0 50px;
      position: relative;
      z-index: 2;
    }

    .footer-box {
      display: flex;
      justify-content: space-between;
      gap: 16px;
      align-items: center;
      flex-wrap: wrap;
      padding: 20px 22px;
      border-radius: 24px;
      background: rgba(255,255,255,.05);
      border: 1px solid rgba(255,255,255,.08);
    }

    .footer-box p {
      color: var(--muted);
    }

    .footer-social {
      display: flex;
      gap: 12px;
      flex-wrap: wrap;
    }

    .footer-social a {
      padding: 10px 14px;
      border-radius: 14px;
      background: rgba(255,255,255,.05);
      border: 1px solid rgba(255,255,255,.08);
      transition: .25s ease;
    }

    .footer-social a:hover {
      background: rgba(255,255,255,.08);
    }
    /* =========================
       REVEAL ANIMATION
    ========================== */
    .reveal {
      opacity: 0;
      transform: translateY(24px);
      transition: opacity .8s ease, transform .8s ease;
    }

    .reveal.show {
      opacity: 1;
      transform: translateY(0);
    }

    /* =========================
       RESPONSIVE
    ========================== */
    @media (max-width: 1100px) {
      .hero-grid,
      .about-grid,
      .contact-grid {
        grid-template-columns: 1fr;
      }

      .skills-grid {
        grid-template-columns: repeat(2, minmax(0, 1fr));
      }

      .services-grid,
      .projects-grid {
        grid-template-columns: repeat(2, minmax(0, 1fr));
      }

      .hero-card {
        min-height: auto;
      }
    }

    @media (max-width: 820px) {
      .nav-links,
      .nav-cta .btn-secondary {
        display: none;
      }

      .menu-toggle {
        display: inline-grid;
        place-items: center;
      }

      .nav-links.mobile-open {
        position: absolute;
        top: calc(100% + 12px);
        left: 0;
        right: 0;
        display: grid;
        gap: 8px;
        padding: 14px;
        border-radius: 22px;
        background: rgba(12, 18, 31, 0.92);
        border: 1px solid rgba(255,255,255,.10);
        box-shadow: var(--shadow);
      }

      .nav-links.mobile-open a {
        background: rgba(255,255,255,.04);
      }

      .hero-stats {
        grid-template-columns: 1fr;
      }

      .about-list,
      .services-grid,
      .projects-grid,
      .skills-grid,
      .form-row {
        grid-template-columns: 1fr;
      }
    }

    @media (max-width: 560px) {
      .section {
        padding: 80px 0;
      }

      .navbar {
        padding: 12px 14px;
      }

      .hero {
        padding-top: 48px;
      }

      .hero-title {
        font-size: 40px;
      }

      .hero-text {
        font-size: 15px;
      }

      .hero-card,
      .about-content,
      .contact-card,
      .contact-form-wrap {
        padding: 22px;
      }

      .avatar {
        width: 210px;
        height: 210px;
        font-size: 60px;
      }
    }
  </style>
</head>
<body>

  <!-- BACKGROUND -->
  <canvas id="snow"></canvas>
  <div class="orb one"></div>
  <div class="orb two"></div>
  <div class="orb three"></div>

  <!-- NAVBAR -->
  <div class="container navbar-wrap">
    <nav class="navbar">
      <a href="#home" class="brand">
        <span class="brand-logo">W</span>
        <span>Winterr</span>
      </a>

      <div class="nav-links" id="navLinks">
        <a href="#home">Home</a>
        <a href="#about">About</a>
        <a href="#skills">Skills</a>
        <a href="#services">Services</a>
        <a href="#projects">Projects</a>
        <a href="#experience">Experience</a>
        <a href="#contact">Contact</a>
      </div>

      <div class="nav-cta">
        <a href="#contact" class="btn btn-secondary">Let’s Talk</a>
        <a href="#projects" class="btn btn-primary">View Work</a>
        <button class="menu-toggle" id="menuToggle">☰</button>
      </div>
    </nav>
  </div>

  <!-- HERO -->
  <section class="hero" id="home">
    <div class="container hero-grid">
      <div class="hero-left reveal">
        <div class="badge">Creative Frontend Developer • UI/UX Focused</div>

        <h1 class="hero-title">
          <span class="gradient">Winterr</span><br>
          Modern, premium va estetik
          <span class="gradient">web portfolio</span>
          tajribasi yaratadi.
        </h1>

        <p class="hero-text">
          Men zamonaviy, tezkor va foydalanuvchi uchun qulay veb-saytlar yaratishga ixtisoslashgan frontend developer/man.
          Chiroyli dizayn, toza kod va kuchli animatsiyalar orqali brendlarni internetda professional ko‘rinishga olib chiqaman.
        </p>

        <div class="hero-actions">
          <a href="#projects" class="btn btn-primary">My Projects</a>
          <a href="#contact" class="btn btn-secondary">Hire Me</a>
        </div>
        <div class="hero-stats">
          <div class="stat-card">
            <h3>20+</h3>
            <p>Completed Projects</p>
          </div>
          <div class="stat-card">
            <h3>2+</h3>
            <p>Years of Experience</p>
          </div>
          <div class="stat-card">
            <h3>100%</h3>
            <p>Responsive & Clean UI</p>
          </div>
        </div>
      </div>

      <div class="hero-right reveal">
        <div class="hero-card">
          <div class="hero-profile">
            <div class="profile-top">
              <div class="profile-badge">Available for Freelance</div>
              <div class="profile-badge">Based in Uzbekistan</div>
            </div>

            <div class="avatar-wrap">
              <div class="avatar-glow"></div>
              <div class="avatar">W</div>
            </div>

            <div class="profile-info">
              <h3>Winterr</h3>
              <p>
                Frontend Developer / Web Designer. Minimal, premium va tez ishlaydigan portfolio,
                landing page, business site va personal brand saytlar tayyorlayman.
              </p>

              <div class="tech-stack">
                <span class="chip">HTML</span>
                <span class="chip">CSS</span>
                <span class="chip">JavaScript</span>
                <span class="chip">Responsive Design</span>
                <span class="chip">UI/UX</span>
              </div>
            </div>

            <div class="mini-grid">
              <div class="mini-card">
                <h4>Clean Code</h4>
                <p>Toza struktura, reusable komponentlar va optimallashtirilgan frontend yechimlar.</p>
              </div>
              <div class="mini-card">
                <h4>Modern Visuals</h4>
                <p>Glassmorphism, gradients, hover animatsiyalar va premium UI tajribasi.</p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- ABOUT -->
  <section class="section" id="about">
    <div class="container">
      <div class="badge reveal">About Me</div>
      <h2 class="section-title reveal">Winterr haqida qisqacha</h2>
      <p class="section-subtitle reveal">
        Men chiroyli ko‘rinadigan, tez ishlaydigan va foydalanuvchiga qulay bo‘lgan web interfeyslar yaratishga qiziqaman.
        Har bir loyiha men uchun faqat kod emas — bu dizayn, tajriba va sifatning uyg‘unligi.
      </p>

      <div class="about-grid">
        <div class="about-visual glass-card reveal">
          <div class="visual-box">
            <div>
              <div class="visual-top">
                <div class="dots">
                  <span></span>
                  <span></span>
                  <span></span>
                </div>
                <div class="profile-badge">winterr.dev</div>
              </div>

              <div class="code-screen">
                <span class="code-line"><span class="pink">const</span> <span class="blue">developer</span> = {</span>
                <span class="code-line">  name: <span class="green">"Winterr"</span>,</span>
                <span class="code-line">  role: <span class="green">"Frontend Developer"</span>,</span>
                <span class="code-line">  focus: [<span class="green">"UI/UX"</span>, <span class="green">"Responsive Design"</span>, <span class="green">"Animation"</span>],</span>
                <span class="code-line">  stack: [<span class="green">"HTML"</span>, <span class="green">"CSS"</span>, <span class="green">"JavaScript"</span>],</span>
                <span class="code-line">  mission: <span class="green">"Build elegant digital experiences"</span></span>
                <span class="code-line">};</span>
                <br>
                <span class="code-line"><span class="yellow">function</span> <span class="purple">createImpact</span>() {</span>
  <span class="code-line">  <span class="pink">return</span> <span class="green">"Design + Code + Performance"</span>;</span>
                <span class="code-line">}</span>
              </div>
            </div>

            <div class="mini-grid">
              <div class="mini-card">
                <h4>Frontend Focus</h4>
                <p>Pixel-perfect interfeys, animation va zamonaviy layoutlar.</p>
              </div>
              <div class="mini-card">
                <h4>Performance</h4>
                <p>Yengil, tez va mobil qurilmalar uchun optimallashtirilgan saytlar.</p>
              </div>
            </div>
          </div>
        </div>

        <div class="about-content glass-card reveal">
          <h3 style="font-size: 30px; margin-bottom: 16px; font-family: 'Space Grotesk', sans-serif;">Elegant design, strong frontend, real impact.</h3>

          <p>
            Men foydalanuvchi ko‘rganda “wow” deydigan, lekin ichki tomondan ham tartibli va toza yozilgan saytlar yaratishni yoqtiraman.
            Portfolio, personal brand, landing page, startup sahifalari va business web sahifalarni zamonaviy uslubda tayyorlayman.
          </p>

          <p>
            Maqsadim — nafaqat chiroyli dizayn, balki mijozga foyda keltiradigan, ishonch uyg‘otadigan va professional taassurot qoldiradigan web tajriba yaratish.
          </p>

          <div class="about-list">
            <div class="about-item">
              <h4>Design Thinking</h4>
              <p>Foydalanuvchi tajribasi, vizual balans va o‘qilishi qulay struktura.</p>
            </div>
            <div class="about-item">
              <h4>Responsive Layout</h4>
              <p>Desktop, planshet va telefonlarda birdek chiroyli ko‘rinish.</p>
            </div>
            <div class="about-item">
              <h4>Interactive UI</h4>
              <p>Hover effektlar, animatsiyalar va premium micro-interactions.</p>
            </div>
            <div class="about-item">
              <h4>Clean Structure</h4>
              <p>Keyinchalik oson tahrir qilinadigan, tartibli va tushunarli kod.</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- SKILLS -->
  <section class="section" id="skills">
    <div class="container">
      <div class="badge reveal">My Skills</div>
      <h2 class="section-title reveal">Texnologiyalar va kuchli tomonlarim</h2>
      <p class="section-subtitle reveal">
        Quyidagi yo‘nalishlarda kuchli ishlayman. Bu foizlar namunaviy ko‘rsatkich bo‘lib, o‘zing xohlaganingcha o‘zgartirishing mumkin.
      </p>

      <div class="skills-grid">
        <div class="skill-card reveal">
          <div class="skill-icon">💻</div>
          <h3>HTML5</h3>
          <p>Semantik struktura, SEO uchun to‘g‘ri markup va tartibli sahifa arxitekturasi.</p>
          <div class="progress"><span style="width:95%"></span></div>
        </div>

        <div class="skill-card reveal">
          <div class="skill-icon">🎨</div>
          <h3>CSS3 / UI Styling</h3>
          <p>Glassmorphism, gradient, layout, responsive design va animatsion interfeyslar.</p>
          <div class="progress"><span style="width:92%"></span></div>
        </div>

        <div class="skill-card reveal">
          <div class="skill-icon">⚡</div>
          <h3>JavaScript</h3>
          <p>Interaktiv elementlar, DOM bilan ishlash, dynamic section va UI behavior.</p>
          <div class="progress"><span style="width:85%"></span></div>
        </div>

        <div class="skill-card reveal">
          <div class="skill-icon">📱</div>
          <h3>Responsive Design</h3>
          <p>Har qanday ekranga moslashadigan, mobilga optimallashtirilgan dizayn yechimlari.</p>
          <div class="progress"><span style="width:96%"></span></div>
        </div>
      </div>
    </div>
  </section>
        <!-- SERVICES -->
  <section class="section" id="services">
    <div class="container">
      <div class="badge reveal">Services</div>
      <h2 class="section-title reveal">Nimalar tayyorlay olaman</h2>
      <p class="section-subtitle reveal">
        Agar sen shaxsiy portfolio, biznes landing page yoki chiroyli modern website xohlasang — shu yo‘nalishlarda ishlash mumkin.
      </p>

      <div class="services-grid">
        <div class="service-card reveal">
          <div class="service-icon">🌐</div>
          <h3>Portfolio Website</h3>
          <p>
            Shaxsiy brend, ishlaring va xizmatlaringni professional ko‘rsatib beradigan premium portfolio saytlar.
          </p>
        </div>

        <div class="service-card reveal">
          <div class="service-icon">🚀</div>
          <h3>Landing Page</h3>
          <p>
            Mahsulot, xizmat yoki startup uchun conversion-focused, zamonaviy va tez ishlaydigan landing sahifalar.
          </p>
        </div>

        <div class="service-card reveal">
          <div class="service-icon">✨</div>
          <h3>UI Redesign</h3>
          <p>
            Eski yoki oddiy saytni premium ko‘rinishga olib chiqish, layout va foydalanuvchi tajribasini yaxshilash.
          </p>
        </div>
      </div>
    </div>
  </section>

  <!-- PROJECTS -->
  <section class="section" id="projects">
    <div class="container">
      <div class="badge reveal">Projects</div>
      <h2 class="section-title reveal">Tanlangan loyihalar</h2>
      <p class="section-subtitle reveal">
        Hozircha demo tarzida 3 ta loyiha blokini qo‘ydim. Keyin bularning o‘rniga o‘zing qilgan ishlarni qo‘yib chiqamiz.
      </p>

      <div class="projects-grid">
        <article class="project-card reveal">
          <div class="project-cover">
            <div class="project-shape">Nova UI</div>
          </div>
          <div class="project-body">
            <div class="project-tags">
              <span>HTML</span>
              <span>CSS</span>
              <span>JavaScript</span>
            </div>
            <h3>Creative Agency Landing</h3>
            <p>
              Premium ko‘rinishdagi agency landing page. Kuchli hero section, xizmatlar bo‘limi va call-to-action bloklari bilan.
            </p>
            <div class="project-links">
              <a href="#" class="project-link">Live Demo</a>
              <a href="#" class="project-link">Source Code</a>
            </div>
          </div>
        </article>

        <article class="project-card reveal">
          <div class="project-cover">
            <div class="project-shape">Shopix</div>
          </div>
          <div class="project-body">
            <div class="project-tags">
              <span>E-Commerce</span>
              <span>UI</span>
              <span>Responsive</span>
            </div>
            <h3>Product Showcase Website</h3>
            <p>
              Mahsulotlarni zamonaviy usulda ko‘rsatish uchun tayyorlangan product showcase sahifa dizayni.
            </p>
            <div class="project-links">
              <a href="#" class="project-link">Live Demo</a>
              <a href="#" class="project-link">Source Code</a>
            </div>
          </div>
        </article>

        <article class="project-card reveal">
          <div class="project-cover">
            <div class="project-shape">Finora</div>
          </div>
          <div class="project-body">
            <div class="project-tags">
              <span>Portfolio</span>
              <span>Branding</span>
              <span>UX</span>
            </div>
            <h3>Personal Brand Portfolio</h3>
            <p>
              Personal brend uchun tayyorlangan portfolio sahifasi — minimalist, premium va yuqori vizual sifatga ega.
            </p>
            <div class="project-links">
              <a href="#" class="project-link">Live Demo</a>
              <a href="#" class="project-link">Source Code</a>
            </div>
          </div>
        </article>
      </div>
    </div>
  </section>
              <!-- EXPERIENCE -->
  <section class="section" id="experience">
    <div class="container">
      <div class="badge reveal">Experience</div>
      <h2 class="section-title reveal">Yo‘nalish va tajriba</h2>
      <p class="section-subtitle reveal">
        Agar xohlasang bu bo‘limni keyin real tajribang, o‘qigan joying yoki ishlagan loyihalaring bilan to‘ldirib beraman.
      </p>

      <div class="timeline">
        <div class="timeline-item reveal">
          <div class="timeline-item-inner">
            <h3>Frontend Development</h3>
            <div class="timeline-meta">HTML • CSS • JavaScript • Responsive UI</div>
            <p>
              Zamonaviy veb interfeyslar, personal portfolio va landing page dizaynlarini yaratish,
              layout tuzish va animatsion komponentlar bilan ishlash.
            </p>
          </div>
        </div>

        <div class="timeline-item reveal">
          <div class="timeline-item-inner">
            <h3>UI / UX Practice</h3>
            <div class="timeline-meta">Visual hierarchy • Spacing • Usability</div>
            <p>
              Foydalanuvchi uchun qulay, toza va professional ko‘rinadigan interfeyslar tayyorlash,
              rang, tipografiya va section strukturasini balansli qurish.
            </p>
          </div>
        </div>

        <div class="timeline-item reveal">
          <div class="timeline-item-inner">
            <h3>Freelance Ready Projects</h3>
            <div class="timeline-meta">Portfolio • Business Site • Landing Page</div>
            <p>
              Mijoz ehtiyojiga mos sahifalar tayyorlash, kontentni chiroyli joylashtirish va zamonaviy frontend yechimlar berish.
            </p>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- CONTACT -->
  <section class="section" id="contact">
    <div class="container">
      <div class="badge reveal">Contact</div>
      <h2 class="section-title reveal">Birga ishlashni boshlaymizmi?</h2>
      <p class="section-subtitle reveal">
        Pastdagi contact ma’lumotlarini o‘zingnikiga almashtir. Xohlasang keyingi xabarda men buni sening real Telegram,
        Instagram, GitHub va emailing bilan to‘liq moslab beraman.
      </p>

      <div class="contact-grid">
        <div class="contact-card reveal">
          <h3 style="font-size: 28px; margin-bottom: 14px; font-family: 'Space Grotesk', sans-serif;">Let’s build something beautiful.</h3>
          <p>
            Agar senga portfolio, landing page yoki modern business website kerak bo‘lsa, men bilan bog‘lanishing mumkin.
            Tezkor, estetik va sifatli natija berishga harakat qilaman.
          </p>

          <div class="contact-list">
            <div class="contact-item">
              <div class="contact-icon">📧</div>
              <div>
                <h4>Email</h4>
                <p>winterr@example.com</p>
              </div>
            </div>

            <div class="contact-item">
              <div class="contact-icon">📱</div>
              <div>
                <h4>Telegram</h4>
                <p>@winterr</p>
              </div>
            </div>

            <div class="contact-item">
              <div class="contact-icon">📍</div>
              <div>
                <h4>Location</h4>
                <p>Uzbekistan</p>
              </div>
            </div>
          </div>
        </div>

        <div class="contact-form-wrap reveal">
          <form class="contact-form">
            <div class="form-row">
              <input class="input" type="text" placeholder="Your name">
              <input class="input" type="email" placeholder="Your email">
            </div>
            <input class="input" type="text" placeholder="Subject">
            <textarea class="textarea" placeholder="Write your message..."></textarea>
            <button type="submit" class="btn btn-primary">Send Message</button>
          </form>
        </div>
      </div>
    </div>
  </section>
  <!-- FOOTER -->
  <footer>
    <div class="container">
      <div class="footer-box">
        <p>© 2025 Winterr. All rights reserved.</p>
        <div class="footer-social">
          <a href="#">Instagram</a>
          <a href="#">Telegram</a>
          <a href="#">GitHub</a>
          <a href="#">Behance</a>
        </div>
      </div>
    </div>
  </footer>

  <script>
    /* =========================
       MOBILE MENU
    ========================== */
    const menuToggle = document.getElementById("menuToggle");
    const navLinks = document.getElementById("navLinks");

    menuToggle.addEventListener("click", () => {
      navLinks.classList.toggle("mobile-open");
    });

    document.querySelectorAll(".nav-links a").forEach(link => {
      link.addEventListener("click", () => {
        navLinks.classList.remove("mobile-open");
      });
    });

    /* =========================
       REVEAL ON SCROLL
    ========================== */
    const reveals = document.querySelectorAll(".reveal");

    const revealObserver = new IntersectionObserver((entries) => {
      entries.forEach(entry => {
        if (entry.isIntersecting) {
          entry.target.classList.add("show");
        }
      });
    }, { threshold: 0.12 });

    reveals.forEach(item => revealObserver.observe(item));

    /* =========================
       SNOW / PARTICLES CANVAS
    ========================== */
    const canvas = document.getElementById("snow");
    const ctx = canvas.getContext("2d");

    let particles = [];
    let w, h;

    function resizeCanvas() {
      w = canvas.width = window.innerWidth;
      h = canvas.height = window.innerHeight;
    }

    function createParticles() {
      particles = [];
      const count = Math.min(140, Math.floor(window.innerWidth / 10));

      for (let i = 0; i < count; i++) {
        particles.push({
          x: Math.random() * w,
          y: Math.random() * h,
          r: Math.random() * 2.8 + 0.5,
          speedY: Math.random() * 0.9 + 0.2,
          speedX: (Math.random() - 0.5) * 0.3,
          alpha: Math.random() * 0.7 + 0.2
        });
      }
    }

    function drawParticles() {
      ctx.clearRect(0, 0, w, h);

      for (const p of particles) {
        ctx.beginPath();
        ctx.arc(p.x, p.y, p.r, 0, Math.PI * 2);
        ctx.fillStyle = rgba(255,255,255);
        ctx.fill();

        p.y += p.speedY;
        p.x += p.speedX;

        if (p.y > h + 10) {
          p.y = -10;
          p.x = Math.random() * w;
        }

        if (p.x > w + 10) p.x = -10;
        if (p.x < -10) p.x = w + 10;
      }

      requestAnimationFrame(drawParticles);
    }

    window.addEventListener("resize", () => {
      resizeCanvas();
      createParticles();
    });

    resizeCanvas();
    createParticles();
    drawParticles();
  </script>
</body>
</html>
