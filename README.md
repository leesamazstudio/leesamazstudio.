# leesamazstudio.
Premium creative media, branding, photography and design studio based in Pretoria, South Africa.
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Lee Samaz Studio — Your Vision. Our Art.</title>
<link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=Barlow+Condensed:wght@300;400;600;700;900&family=Barlow:wght@300;400;500;600&display=swap" rel="stylesheet">
<style>
  :root {
    --red: #E8001D;
    --black: #0a0a0a;
    --white: #F5F2ED;
    --gold: #C9A84C;
    --grey: #1a1a1a;
    --mid: #2a2a2a;
    --text-muted: #888;
  }

  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  html { scroll-behavior: smooth; }

  body {
    background: var(--black);
    color: var(--white);
    font-family: 'Barlow', sans-serif;
    font-weight: 300;
    overflow-x: hidden;
    cursor: none;
  }

  /* CUSTOM CURSOR */
  .cursor {
    position: fixed;
    width: 12px; height: 12px;
    background: var(--red);
    border-radius: 50%;
    pointer-events: none;
    z-index: 9999;
    transform: translate(-50%, -50%);
    transition: transform 0.1s, width 0.2s, height 0.2s, opacity 0.2s;
    mix-blend-mode: normal;
  }
  .cursor-follower {
    position: fixed;
    width: 36px; height: 36px;
    border: 1px solid rgba(232,0,29,0.5);
    border-radius: 50%;
    pointer-events: none;
    z-index: 9998;
    transform: translate(-50%, -50%);
    transition: transform 0.15s ease, width 0.25s, height 0.25s, opacity 0.25s;
  }
  body:hover .cursor { opacity: 1; }
  a, button { cursor: none; }

  /* NOISE OVERLAY */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noise'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noise)' opacity='0.04'/%3E%3C/svg%3E");
    pointer-events: none;
    z-index: 1;
    opacity: 0.6;
  }

  /* ===== NAV ===== */
  nav {
    position: fixed;
    top: 0; left: 0; right: 0;
    z-index: 1000;
    padding: 20px 48px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    transition: background 0.4s, padding 0.4s;
  }
  nav.scrolled {
    background: rgba(10,10,10,0.96);
    backdrop-filter: blur(20px);
    padding: 14px 48px;
    border-bottom: 1px solid rgba(255,255,255,0.06);
  }
  .nav-logo {
    display: flex;
    align-items: center;
    gap: 12px;
    text-decoration: none;
  }
  .nav-logo img {
    width: 44px; height: 44px;
    border-radius: 50%;
    object-fit: cover;
  }
  .nav-logo-text {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 20px;
    letter-spacing: 3px;
    color: var(--white);
    line-height: 1;
  }
  .nav-logo-text span { color: var(--red); }
  .nav-links {
    display: flex;
    gap: 36px;
    list-style: none;
  }
  .nav-links a {
    font-family: 'Barlow Condensed', sans-serif;
    font-size: 13px;
    font-weight: 600;
    letter-spacing: 2px;
    text-transform: uppercase;
    color: rgba(245,242,237,0.7);
    text-decoration: none;
    transition: color 0.2s;
    position: relative;
  }
  .nav-links a::after {
    content: '';
    position: absolute;
    bottom: -4px; left: 0; right: 0;
    height: 1px;
    background: var(--red);
    transform: scaleX(0);
    transform-origin: left;
    transition: transform 0.3s;
  }
  .nav-links a:hover { color: var(--white); }
  .nav-links a:hover::after { transform: scaleX(1); }
  .nav-cta {
    font-family: 'Barlow Condensed', sans-serif;
    font-size: 12px;
    font-weight: 700;
    letter-spacing: 3px;
    text-transform: uppercase;
    padding: 10px 24px;
    background: var(--red);
    color: var(--white);
    border: none;
    text-decoration: none;
    transition: background 0.2s, transform 0.2s;
    display: inline-block;
  }
  .nav-cta:hover { background: #cc0019; transform: translateY(-1px); }

  /* ===== HERO ===== */
  #hero {
    position: relative;
    min-height: 100vh;
    display: grid;
    grid-template-columns: 1fr 1fr;
    overflow: hidden;
  }
  .hero-left {
    display: flex;
    flex-direction: column;
    justify-content: center;
    padding: 140px 60px 80px 80px;
    position: relative;
    z-index: 2;
  }
  .hero-tag {
    font-family: 'Barlow Condensed', sans-serif;
    font-size: 11px;
    font-weight: 700;
    letter-spacing: 4px;
    text-transform: uppercase;
    color: var(--red);
    margin-bottom: 28px;
    display: flex;
    align-items: center;
    gap: 12px;
  }
  .hero-tag::before {
    content: '';
    width: 32px; height: 1px;
    background: var(--red);
  }
  .hero-headline {
    font-family: 'Bebas Neue', sans-serif;
    font-size: clamp(72px, 9vw, 130px);
    line-height: 0.92;
    letter-spacing: 2px;
    margin-bottom: 8px;
  }
  .hero-headline .red { color: var(--red); }
  .hero-headline .stroke {
    -webkit-text-stroke: 1px rgba(245,242,237,0.3);
    color: transparent;
  }
  .hero-sub {
    font-family: 'Barlow Condensed', sans-serif;
    font-size: 18px;
    font-weight: 300;
    letter-spacing: 6px;
    text-transform: uppercase;
    color: rgba(245,242,237,0.5);
    margin-bottom: 48px;
    margin-top: 16px;
  }
  .hero-desc {
    font-size: 15px;
    line-height: 1.8;
    color: rgba(245,242,237,0.6);
    max-width: 400px;
    margin-bottom: 48px;
  }
  .hero-btns {
    display: flex;
    gap: 16px;
    flex-wrap: wrap;
  }
  .btn-primary {
    font-family: 'Barlow Condensed', sans-serif;
    font-size: 12px;
    font-weight: 700;
    letter-spacing: 3px;
    text-transform: uppercase;
    padding: 16px 36px;
    background: var(--red);
    color: var(--white);
    border: none;
    text-decoration: none;
    display: inline-block;
    transition: all 0.25s;
    position: relative;
    overflow: hidden;
  }
  .btn-primary::before {
    content: '';
    position: absolute;
    inset: 0;
    background: rgba(255,255,255,0.08);
    transform: translateX(-100%);
    transition: transform 0.3s;
  }
  .btn-primary:hover::before { transform: translateX(0); }
  .btn-primary:hover { transform: translateY(-2px); box-shadow: 0 8px 32px rgba(232,0,29,0.4); }
  .btn-outline {
    font-family: 'Barlow Condensed', sans-serif;
    font-size: 12px;
    font-weight: 700;
    letter-spacing: 3px;
    text-transform: uppercase;
    padding: 15px 36px;
    background: transparent;
    color: var(--white);
    border: 1px solid rgba(245,242,237,0.25);
    text-decoration: none;
    display: inline-block;
    transition: all 0.25s;
  }
  .btn-outline:hover {
    border-color: var(--white);
    background: rgba(255,255,255,0.04);
    transform: translateY(-2px);
  }

  .hero-stats {
    display: flex;
    gap: 40px;
    margin-top: 60px;
    padding-top: 40px;
    border-top: 1px solid rgba(255,255,255,0.08);
  }
  .hero-stat-num {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 38px;
    color: var(--white);
    line-height: 1;
  }
  .hero-stat-num span { color: var(--red); }
  .hero-stat-label {
    font-size: 11px;
    letter-spacing: 2px;
    text-transform: uppercase;
    color: var(--text-muted);
    margin-top: 4px;
  }

  .hero-right {
    position: relative;
    overflow: hidden;
  }
  .hero-right::before {
    content: '';
    position: absolute;
    inset: 0;
    background: linear-gradient(to right, var(--black), transparent 40%),
                linear-gradient(to bottom, transparent 60%, var(--black));
    z-index: 1;
  }
  .hero-img-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    grid-template-rows: 1fr 1fr;
    height: 100%;
    gap: 4px;
  }
  .hero-img-grid img {
    width: 100%; height: 100%;
    object-fit: cover;
    object-position: center;
    transition: transform 6s ease;
    animation: kenburns 12s ease-in-out infinite alternate;
  }
  @keyframes kenburns {
    from { transform: scale(1); }
    to { transform: scale(1.08); }
  }
  .hero-img-grid .span2 { grid-column: span 2; }

  /* Floating badge */
  .hero-badge {
    position: absolute;
    bottom: 48px;
    right: 48px;
    z-index: 10;
    background: var(--red);
    width: 110px; height: 110px;
    border-radius: 50%;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    text-align: center;
    animation: spin-slow 20s linear infinite;
  }
  @keyframes spin-slow {
    from { transform: rotate(0deg); }
    to { transform: rotate(360deg); }
  }
  .hero-badge-inner {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 11px;
    letter-spacing: 4px;
    line-height: 1.3;
    animation: spin-slow 20s linear infinite reverse;
  }

  /* Scrolling marquee */
  .marquee-section {
    background: var(--red);
    padding: 14px 0;
    overflow: hidden;
    white-space: nowrap;
    position: relative;
    z-index: 2;
  }
  .marquee-inner {
    display: inline-flex;
    animation: marquee 25s linear infinite;
  }
  .marquee-inner span {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 20px;
    letter-spacing: 4px;
    padding: 0 40px;
    color: rgba(245,242,237,0.9);
  }
  .marquee-inner .dot {
    color: rgba(245,242,237,0.4);
    padding: 0;
  }
  @keyframes marquee {
    from { transform: translateX(0); }
    to { transform: translateX(-50%); }
  }

  /* ===== SECTION STYLES ===== */
  section {
    padding: 120px 80px;
    position: relative;
  }
  .section-tag {
    font-family: 'Barlow Condensed', sans-serif;
    font-size: 11px;
    font-weight: 700;
    letter-spacing: 4px;
    text-transform: uppercase;
    color: var(--red);
    margin-bottom: 16px;
    display: flex;
    align-items: center;
    gap: 12px;
  }
  .section-tag::before {
    content: '';
    width: 24px; height: 1px;
    background: var(--red);
  }
  .section-title {
    font-family: 'Bebas Neue', sans-serif;
    font-size: clamp(48px, 6vw, 80px);
    line-height: 0.95;
    letter-spacing: 2px;
    margin-bottom: 24px;
  }
  .section-title .red { color: var(--red); }
  .section-title .stroke {
    -webkit-text-stroke: 1px rgba(245,242,237,0.25);
    color: transparent;
  }

  /* ===== ABOUT ===== */
  #about {
    background: var(--grey);
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 80px;
    align-items: center;
    padding: 120px 80px;
  }
  .about-img-stack {
    position: relative;
    height: 580px;
  }
  .about-img-stack img {
    position: absolute;
    object-fit: cover;
    border: 3px solid rgba(255,255,255,0.04);
  }
  .about-img-stack .img-main {
    width: 75%; height: 80%;
    top: 0; left: 0;
    z-index: 2;
  }
  .about-img-stack .img-secondary {
    width: 55%; height: 55%;
    bottom: 0; right: 0;
    z-index: 3;
    border: 4px solid var(--black);
  }
  .about-img-stack .img-accent {
    width: 40%; height: 30%;
    top: 55%; left: 20%;
    z-index: 1;
    filter: brightness(0.4);
  }
  .about-tag-block {
    position: absolute;
    top: 32px; right: 0;
    background: var(--red);
    padding: 20px 24px;
    z-index: 4;
    text-align: center;
  }
  .about-tag-block .num {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 42px;
    line-height: 1;
    color: var(--white);
  }
  .about-tag-block .lbl {
    font-family: 'Barlow Condensed', sans-serif;
    font-size: 10px;
    font-weight: 700;
    letter-spacing: 2px;
    text-transform: uppercase;
    color: rgba(245,242,237,0.7);
    margin-top: 2px;
  }
  .about-text p {
    font-size: 15px;
    line-height: 1.85;
    color: rgba(245,242,237,0.65);
    margin-bottom: 20px;
  }
  .about-values {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 16px;
    margin-top: 40px;
  }
  .value-card {
    padding: 20px;
    border: 1px solid rgba(255,255,255,0.07);
    background: rgba(255,255,255,0.02);
    transition: border-color 0.3s, background 0.3s;
  }
  .value-card:hover {
    border-color: var(--red);
    background: rgba(232,0,29,0.04);
  }
  .value-title {
    font-family: 'Barlow Condensed', sans-serif;
    font-size: 13px;
    font-weight: 700;
    letter-spacing: 2px;
    text-transform: uppercase;
    color: var(--red);
    margin-bottom: 8px;
  }
  .value-desc {
    font-size: 13px;
    line-height: 1.6;
    color: rgba(245,242,237,0.5);
  }

  /* ===== SERVICES ===== */
  #services {
    background: var(--black);
  }
  .services-header {
    display: flex;
    justify-content: space-between;
    align-items: flex-end;
    margin-bottom: 70px;
  }
  .services-grid {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 1px;
    background: rgba(255,255,255,0.06);
  }
  .service-card {
    background: var(--black);
    padding: 40px 32px;
    position: relative;
    overflow: hidden;
    transition: background 0.3s;
    group: true;
  }
  .service-card::before {
    content: '';
    position: absolute;
    bottom: 0; left: 0; right: 0;
    height: 2px;
    background: var(--red);
    transform: scaleX(0);
    transform-origin: left;
    transition: transform 0.4s;
  }
  .service-card:hover { background: rgba(232,0,29,0.04); }
  .service-card:hover::before { transform: scaleX(1); }
  .service-icon {
    font-size: 32px;
    margin-bottom: 24px;
    display: block;
  }
  .service-num {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 64px;
    color: rgba(255,255,255,0.04);
    position: absolute;
    top: 16px; right: 20px;
    line-height: 1;
    letter-spacing: -2px;
  }
  .service-name {
    font-family: 'Barlow Condensed', sans-serif;
    font-size: 20px;
    font-weight: 700;
    letter-spacing: 1px;
    text-transform: uppercase;
    color: var(--white);
    margin-bottom: 12px;
  }
  .service-desc {
    font-size: 13px;
    line-height: 1.7;
    color: rgba(245,242,237,0.45);
    margin-bottom: 24px;
  }
  .service-price {
    font-family: 'Barlow Condensed', sans-serif;
    font-size: 13px;
    font-weight: 600;
    letter-spacing: 1px;
    color: var(--red);
    padding: 6px 14px;
    border: 1px solid rgba(232,0,29,0.3);
    display: inline-block;
  }

  /* ===== PORTFOLIO ===== */
  #portfolio {
    background: var(--grey);
    padding: 120px 0;
  }
  #portfolio .inner-pad {
    padding: 0 80px;
    margin-bottom: 60px;
  }
  .portfolio-filter {
    display: flex;
    gap: 4px;
    flex-wrap: wrap;
    margin-top: 32px;
  }
  .filter-btn {
    font-family: 'Barlow Condensed', sans-serif;
    font-size: 11px;
    font-weight: 700;
    letter-spacing: 3px;
    text-transform: uppercase;
    padding: 8px 20px;
    background: transparent;
    color: rgba(245,242,237,0.5);
    border: 1px solid rgba(255,255,255,0.1);
    cursor: none;
    transition: all 0.2s;
  }
  .filter-btn.active, .filter-btn:hover {
    background: var(--red);
    color: var(--white);
    border-color: var(--red);
  }
  .portfolio-masonry {
    display: grid;
    grid-template-columns: repeat(12, 1fr);
    grid-auto-rows: 60px;
    gap: 4px;
    padding: 0 4px;
  }
  .portfolio-item {
    overflow: hidden;
    position: relative;
  }
  .portfolio-item img {
    width: 100%; height: 100%;
    object-fit: cover;
    transition: transform 0.5s ease;
  }
  .portfolio-item:hover img { transform: scale(1.06); }
  .portfolio-overlay {
    position: absolute;
    inset: 0;
    background: linear-gradient(to top, rgba(10,10,10,0.9) 0%, transparent 60%);
    opacity: 0;
    transition: opacity 0.3s;
    display: flex;
    align-items: flex-end;
    padding: 24px;
  }
  .portfolio-item:hover .portfolio-overlay { opacity: 1; }
  .portfolio-label {
    font-family: 'Barlow Condensed', sans-serif;
    font-size: 13px;
    font-weight: 700;
    letter-spacing: 2px;
    text-transform: uppercase;
    color: var(--white);
  }
  .portfolio-cat {
    font-size: 11px;
    letter-spacing: 1px;
    color: var(--red);
    text-transform: uppercase;
  }

  /* Grid layout for portfolio items */
  .pi-1 { grid-column: 1 / 6; grid-row: 1 / 8; }
  .pi-2 { grid-column: 6 / 9; grid-row: 1 / 5; }
  .pi-3 { grid-column: 9 / 13; grid-row: 1 / 7; }
  .pi-4 { grid-column: 6 / 9; grid-row: 5 / 9; }
  .pi-5 { grid-column: 1 / 5; grid-row: 8 / 14; }
  .pi-6 { grid-column: 5 / 9; grid-row: 9 / 14; }
  .pi-7 { grid-column: 9 / 13; grid-row: 7 / 14; }
  .pi-8 { grid-column: 1 / 4; grid-row: 14 / 19; }
  .pi-9 { grid-column: 4 / 9; grid-row: 14 / 19; }
  .pi-10 { grid-column: 9 / 13; grid-row: 14 / 19; }

  /* ===== COURSES ===== */
  #courses {
    background: var(--black);
    position: relative;
    overflow: hidden;
  }
  #courses::before {
    content: 'ACADEMY';
    position: absolute;
    font-family: 'Bebas Neue', sans-serif;
    font-size: 300px;
    color: rgba(255,255,255,0.015);
    top: 50%; left: 50%;
    transform: translate(-50%, -50%);
    letter-spacing: 20px;
    pointer-events: none;
    white-space: nowrap;
  }
  .courses-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 1px;
    background: rgba(255,255,255,0.06);
    margin-top: 64px;
  }
  .course-card {
    background: var(--black);
    padding: 48px 36px;
    position: relative;
    overflow: hidden;
    transition: background 0.3s;
  }
  .course-card:hover { background: rgba(232,0,29,0.04); }
  .course-card::after {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 2px;
    background: var(--red);
  }
  .course-duration {
    font-family: 'Barlow Condensed', sans-serif;
    font-size: 11px;
    font-weight: 700;
    letter-spacing: 3px;
    text-transform: uppercase;
    color: var(--red);
    margin-bottom: 16px;
  }
  .course-name {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 32px;
    letter-spacing: 1px;
    line-height: 1.05;
    margin-bottom: 16px;
  }
  .course-desc {
    font-size: 13px;
    line-height: 1.7;
    color: rgba(245,242,237,0.5);
    margin-bottom: 32px;
  }
  .course-price {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 42px;
    color: var(--white);
    line-height: 1;
  }
  .course-price small {
    font-family: 'Barlow', sans-serif;
    font-size: 13px;
    color: rgba(245,242,237,0.4);
    font-weight: 300;
    display: block;
    margin-top: 4px;
  }
  .course-features {
    list-style: none;
    margin-top: 24px;
    padding-top: 24px;
    border-top: 1px solid rgba(255,255,255,0.07);
  }
  .course-features li {
    font-size: 13px;
    color: rgba(245,242,237,0.55);
    padding: 6px 0;
    display: flex;
    align-items: center;
    gap: 10px;
  }
  .course-features li::before {
    content: '✦';
    color: var(--red);
    font-size: 8px;
    flex-shrink: 0;
  }

  /* ===== PRICING ===== */
  #pricing {
    background: var(--grey);
    position: relative;
  }
  .pricing-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 1px;
    background: rgba(255,255,255,0.06);
    margin-top: 64px;
  }
  .price-card {
    background: var(--grey);
    padding: 52px 40px;
    position: relative;
    transition: background 0.3s;
  }
  .price-card.featured {
    background: var(--black);
    border-left: 2px solid var(--red);
    border-right: 2px solid var(--red);
  }
  .price-card.featured::before {
    content: 'MOST POPULAR';
    position: absolute;
    top: -1px; left: 50%;
    transform: translateX(-50%);
    background: var(--red);
    font-family: 'Barlow Condensed', sans-serif;
    font-size: 10px;
    font-weight: 700;
    letter-spacing: 3px;
    padding: 5px 16px;
    white-space: nowrap;
  }
  .price-tier {
    font-family: 'Barlow Condensed', sans-serif;
    font-size: 11px;
    font-weight: 700;
    letter-spacing: 4px;
    text-transform: uppercase;
    color: var(--red);
    margin-bottom: 20px;
  }
  .price-amount {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 64px;
    line-height: 1;
    color: var(--white);
    margin-bottom: 4px;
  }
  .price-amount sup {
    font-size: 24px;
    vertical-align: top;
    margin-top: 12px;
    display: inline-block;
  }
  .price-from {
    font-size: 12px;
    color: rgba(245,242,237,0.35);
    letter-spacing: 1px;
    text-transform: uppercase;
    margin-bottom: 32px;
  }
  .price-features {
    list-style: none;
    border-top: 1px solid rgba(255,255,255,0.07);
    padding-top: 28px;
  }
  .price-features li {
    font-size: 13px;
    color: rgba(245,242,237,0.6);
    padding: 8px 0;
    display: flex;
    align-items: center;
    gap: 12px;
    border-bottom: 1px solid rgba(255,255,255,0.04);
  }
  .price-features li .check { color: var(--red); }
  .price-btn {
    display: block;
    margin-top: 36px;
    text-align: center;
    font-family: 'Barlow Condensed', sans-serif;
    font-size: 12px;
    font-weight: 700;
    letter-spacing: 3px;
    text-transform: uppercase;
    padding: 14px;
    text-decoration: none;
    transition: all 0.25s;
  }
  .price-btn.outline {
    border: 1px solid rgba(255,255,255,0.15);
    color: var(--white);
  }
  .price-btn.outline:hover {
    border-color: var(--red);
    color: var(--red);
  }
  .price-btn.solid {
    background: var(--red);
    color: var(--white);
  }
  .price-btn.solid:hover { background: #cc0019; }

  /* ===== TESTIMONIALS ===== */
  #testimonials {
    background: var(--black);
    overflow: hidden;
  }
  .testimonials-inner {
    display: grid;
    grid-template-columns: 1fr 2fr;
    gap: 80px;
    align-items: start;
  }
  .testimonials-left .big-quote {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 200px;
    color: var(--red);
    line-height: 0.8;
    opacity: 0.15;
    display: block;
    margin-top: -20px;
    margin-bottom: 32px;
  }
  .testimonials-right {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 1px;
    background: rgba(255,255,255,0.06);
  }
  .testimonial-card {
    background: var(--black);
    padding: 36px 32px;
    position: relative;
    transition: background 0.3s;
  }
  .testimonial-card:hover { background: rgba(232,0,29,0.04); }
  .testimonial-stars {
    color: var(--gold);
    font-size: 14px;
    letter-spacing: 2px;
    margin-bottom: 16px;
  }
  .testimonial-text {
    font-size: 14px;
    line-height: 1.75;
    color: rgba(245,242,237,0.65);
    font-style: italic;
    margin-bottom: 20px;
  }
  .testimonial-author {
    font-family: 'Barlow Condensed', sans-serif;
    font-size: 13px;
    font-weight: 700;
    letter-spacing: 1px;
    text-transform: uppercase;
    color: var(--white);
  }
  .testimonial-role {
    font-size: 11px;
    color: var(--red);
    letter-spacing: 1px;
    text-transform: uppercase;
    margin-top: 2px;
  }

  /* ===== PROCESS ===== */
  #process {
    background: var(--grey);
  }
  .process-steps {
    display: grid;
    grid-template-columns: repeat(6, 1fr);
    gap: 1px;
    background: rgba(255,255,255,0.06);
    margin-top: 64px;
  }
  .process-step {
    background: var(--grey);
    padding: 36px 24px;
    position: relative;
    overflow: hidden;
    transition: background 0.3s;
  }
  .process-step:hover { background: rgba(232,0,29,0.04); }
  .step-num {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 56px;
    color: var(--red);
    line-height: 1;
    margin-bottom: 16px;
    opacity: 0.7;
  }
  .step-name {
    font-family: 'Barlow Condensed', sans-serif;
    font-size: 14px;
    font-weight: 700;
    letter-spacing: 2px;
    text-transform: uppercase;
    color: var(--white);
    margin-bottom: 10px;
  }
  .step-desc {
    font-size: 12px;
    line-height: 1.65;
    color: rgba(245,242,237,0.45);
  }
  .step-arrow {
    position: absolute;
    top: 36px; right: 16px;
    font-size: 20px;
    color: rgba(255,255,255,0.08);
  }

  /* ===== CONTACT ===== */
  #contact {
    background: var(--black);
    position: relative;
    overflow: hidden;
  }
  #contact::after {
    content: '';
    position: absolute;
    top: 0; right: 0; bottom: 0;
    width: 50%;
    background: url('/mnt/user-data/uploads/394382.jpg') center/cover no-repeat;
    opacity: 0.08;
    pointer-events: none;
  }
  .contact-inner {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 80px;
    position: relative;
    z-index: 2;
  }
  .contact-info-item {
    display: flex;
    gap: 20px;
    padding: 24px 0;
    border-bottom: 1px solid rgba(255,255,255,0.07);
    align-items: flex-start;
  }
  .contact-info-icon {
    font-size: 20px;
    flex-shrink: 0;
    margin-top: 2px;
  }
  .contact-info-label {
    font-family: 'Barlow Condensed', sans-serif;
    font-size: 10px;
    font-weight: 700;
    letter-spacing: 3px;
    text-transform: uppercase;
    color: var(--red);
    margin-bottom: 4px;
  }
  .contact-info-value {
    font-size: 15px;
    color: var(--white);
  }
  .contact-info-value a {
    color: var(--white);
    text-decoration: none;
    transition: color 0.2s;
  }
  .contact-info-value a:hover { color: var(--red); }

  .contact-form {
    display: flex;
    flex-direction: column;
    gap: 16px;
  }
  .form-row { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; }
  .form-group { display: flex; flex-direction: column; gap: 8px; }
  .form-group label {
    font-family: 'Barlow Condensed', sans-serif;
    font-size: 10px;
    font-weight: 700;
    letter-spacing: 3px;
    text-transform: uppercase;
    color: rgba(245,242,237,0.4);
  }
  .form-group input, .form-group textarea, .form-group select {
    background: rgba(255,255,255,0.04);
    border: 1px solid rgba(255,255,255,0.1);
    color: var(--white);
    padding: 14px 18px;
    font-family: 'Barlow', sans-serif;
    font-size: 14px;
    outline: none;
    transition: border-color 0.2s;
    width: 100%;
  }
  .form-group input:focus, .form-group textarea:focus, .form-group select:focus {
    border-color: var(--red);
  }
  .form-group textarea { resize: vertical; min-height: 120px; }
  .form-group select option { background: var(--black); }
  .form-submit {
    font-family: 'Barlow Condensed', sans-serif;
    font-size: 12px;
    font-weight: 700;
    letter-spacing: 3px;
    text-transform: uppercase;
    padding: 16px 48px;
    background: var(--red);
    color: var(--white);
    border: none;
    cursor: none;
    transition: all 0.25s;
    align-self: flex-start;
  }
  .form-submit:hover { background: #cc0019; transform: translateY(-2px); }

  /* ===== SOCIAL ROW ===== */
  .social-row {
    display: flex;
    gap: 20px;
    margin-top: 40px;
    padding-top: 40px;
    border-top: 1px solid rgba(255,255,255,0.08);
    flex-wrap: wrap;
  }
  .social-link {
    font-family: 'Barlow Condensed', sans-serif;
    font-size: 11px;
    font-weight: 700;
    letter-spacing: 3px;
    text-transform: uppercase;
    color: rgba(245,242,237,0.45);
    text-decoration: none;
    transition: color 0.2s;
    display: flex;
    align-items: center;
    gap: 8px;
  }
  .social-link::before { content: '↗'; color: var(--red); }
  .social-link:hover { color: var(--white); }

  /* ===== FOOTER ===== */
  footer {
    background: var(--grey);
    padding: 48px 80px;
    display: grid;
    grid-template-columns: 1fr auto 1fr;
    align-items: center;
    border-top: 1px solid rgba(255,255,255,0.06);
  }
  .footer-copy {
    font-size: 12px;
    color: rgba(245,242,237,0.3);
    letter-spacing: 1px;
  }
  .footer-logo {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 18px;
    letter-spacing: 4px;
    color: rgba(245,242,237,0.3);
    text-align: center;
  }
  .footer-logo span { color: var(--red); }
  .footer-tagline {
    font-size: 12px;
    color: rgba(245,242,237,0.2);
    letter-spacing: 3px;
    text-transform: uppercase;
    text-align: right;
  }

  /* ===== ANIMATIONS ===== */
  .reveal {
    opacity: 0;
    transform: translateY(30px);
    transition: opacity 0.7s ease, transform 0.7s ease;
  }
  .reveal.visible {
    opacity: 1;
    transform: translateY(0);
  }
  .reveal-delay-1 { transition-delay: 0.1s; }
  .reveal-delay-2 { transition-delay: 0.2s; }
  .reveal-delay-3 { transition-delay: 0.3s; }
  .reveal-delay-4 { transition-delay: 0.4s; }

  /* ===== RESPONSIVE ===== */
  @media (max-width: 1100px) {
    section { padding: 80px 40px; }
    #hero { grid-template-columns: 1fr; }
    .hero-right { height: 50vh; }
    .hero-left { padding: 140px 40px 60px; }
    #about { grid-template-columns: 1fr; padding: 80px 40px; }
    .about-img-stack { height: 360px; }
    .services-grid { grid-template-columns: repeat(2, 1fr); }
    .courses-grid { grid-template-columns: repeat(2, 1fr); }
    .pricing-grid { grid-template-columns: 1fr; }
    .price-card.featured { border: 2px solid var(--red); }
    .testimonials-inner { grid-template-columns: 1fr; }
    .process-steps { grid-template-columns: repeat(3, 1fr); }
    .contact-inner { grid-template-columns: 1fr; }
    #contact::after { display: none; }
    footer { grid-template-columns: 1fr; text-align: center; gap: 12px; }
    .footer-tagline { text-align: center; }
    nav { padding: 16px 24px; }
    .nav-links { display: none; }
    .portfolio-masonry { grid-template-columns: repeat(6, 1fr); }
    .pi-1 { grid-column: 1 / 4; grid-row: 1 / 6; }
    .pi-2 { grid-column: 4 / 7; grid-row: 1 / 4; }
    .pi-3 { grid-column: 1 / 4; grid-row: 6 / 10; }
    .pi-4 { grid-column: 4 / 7; grid-row: 4 / 8; }
    .pi-5 { grid-column: 1 / 4; grid-row: 10 / 14; }
    .pi-6 { grid-column: 4 / 7; grid-row: 8 / 12; }
    .pi-7 { grid-column: 1 / 4; grid-row: 14 / 18; }
    .pi-8 { grid-column: 4 / 7; grid-row: 12 / 16; }
    .pi-9 { grid-column: 1 / 4; grid-row: 18 / 22; }
    .pi-10 { grid-column: 4 / 7; grid-row: 16 / 21; }
  }
  @media (max-width: 680px) {
    section { padding: 60px 20px; }
    #about { padding: 60px 20px; }
    .hero-left { padding: 120px 20px 60px; }
    .hero-stats { flex-wrap: wrap; gap: 24px; }
    .services-grid { grid-template-columns: 1fr; }
    .courses-grid { grid-template-columns: 1fr; }
    .testimonials-right { grid-template-columns: 1fr; }
    .process-steps { grid-template-columns: repeat(2, 1fr); }
    .form-row { grid-template-columns: 1fr; }
    footer { padding: 32px 20px; }
    .about-values { grid-template-columns: 1fr; }
  }
</style>
</head>
<body>

<div class="cursor" id="cursor"></div>
<div class="cursor-follower" id="cursor-follower"></div>

<!-- NAV -->
<nav id="navbar">
  <a href="#hero" class="nav-logo">
    <img src="/mnt/user-data/uploads/186716.webp" alt="Lee Samaz Studio Logo">
    <div>
      <div class="nav-logo-text"><span>LEE</span> SAMAZ</div>
      <div class="nav-logo-text" style="font-size:12px;letter-spacing:5px;color:rgba(245,242,237,0.4);">STUDIO</div>
    </div>
  </a>
  <ul class="nav-links">
    <li><a href="#about">About</a></li>
    <li><a href="#services">Services</a></li>
    <li><a href="#portfolio">Portfolio</a></li>
    <li><a href="#courses">Academy</a></li>
    <li><a href="#pricing">Pricing</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
  <a href="https://wa.me/27618201231" class="nav-cta">WhatsApp Us</a>
</nav>

<!-- HERO -->
<section id="hero">
  <div class="hero-left">
    <div class="hero-tag">Est. 2019 · Pretoria, South Africa</div>
    <h1 class="hero-headline">
      <span class="stroke">YOUR</span><br>
      VISION.<br>
      <span class="red">OUR</span><br>
      ART.
    </h1>
    <p class="hero-sub">Premium Creative Media & Branding</p>
    <p class="hero-desc">Lee Samaz Studio is where bold ideas meet professional execution. We build brands, capture moments, and craft visual stories that are impossible to ignore.</p>
    <div class="hero-btns">
      <a href="#portfolio" class="btn-primary">View Our Work</a>
      <a href="#contact" class="btn-outline">Get a Quote</a>
    </div>
    <div class="hero-stats">
      <div>
        <div class="hero-stat-num">500<span>+</span></div>
        <div class="hero-stat-label">Projects Done</div>
      </div>
      <div>
        <div class="hero-stat-num">200<span>+</span></div>
        <div class="hero-stat-label">Happy Clients</div>
      </div>
      <div>
        <div class="hero-stat-num">5<span>+</span></div>
        <div class="hero-stat-label">Years Active</div>
      </div>
    </div>
  </div>
  <div class="hero-right">
    <div class="hero-img-grid">
      <img src="/mnt/user-data/uploads/394355.jpg" alt="Brand Design" style="animation-delay:0s">
      <img src="/mnt/user-data/uploads/394369.jpg" alt="Wedding Design" style="animation-delay:1.5s">
      <img src="/mnt/user-data/uploads/394367.jpg" alt="Event" style="animation-delay:3s">
      <img src="/mnt/user-data/uploads/394406.jpg" alt="Graphic Design" style="animation-delay:2s">
    </div>
    <div class="hero-badge">
      <div class="hero-badge-inner">YOUR<br>BRAND<br>MATTERS</div>
    </div>
  </div>
</section>

<!-- MARQUEE -->
<div class="marquee-section">
  <div class="marquee-inner">
    <span>GRAPHIC DESIGN</span><span class="dot">✦</span>
    <span>PHOTOGRAPHY</span><span class="dot">✦</span>
    <span>VIDEO EDITING</span><span class="dot">✦</span>
    <span>BRANDING</span><span class="dot">✦</span>
    <span>DRONE CINEMA</span><span class="dot">✦</span>
    <span>DIGITAL MARKETING</span><span class="dot">✦</span>
    <span>WEDDINGS & EVENTS</span><span class="dot">✦</span>
    <span>3D ARCHITECTURE</span><span class="dot">✦</span>
    <span>ONLINE ACADEMY</span><span class="dot">✦</span>
    <!-- Repeat for seamless loop -->
    <span>GRAPHIC DESIGN</span><span class="dot">✦</span>
    <span>PHOTOGRAPHY</span><span class="dot">✦</span>
    <span>VIDEO EDITING</span><span class="dot">✦</span>
    <span>BRANDING</span><span class="dot">✦</span>
    <span>DRONE CINEMA</span><span class="dot">✦</span>
    <span>DIGITAL MARKETING</span><span class="dot">✦</span>
    <span>WEDDINGS & EVENTS</span><span class="dot">✦</span>
    <span>3D ARCHITECTURE</span><span class="dot">✦</span>
    <span>ONLINE ACADEMY</span><span class="dot">✦</span>
  </div>
</div>

<!-- ABOUT -->
<section id="about">
  <div class="about-img-stack reveal">
    <img src="/mnt/user-data/uploads/394386.jpg" alt="Studio Work" class="img-main">
    <img src="/mnt/user-data/uploads/394382.jpg" alt="Wedding Photography" class="img-secondary">
    <img src="/mnt/user-data/uploads/394383.jpg" alt="Event" class="img-accent">
    <div class="about-tag-block">
      <div class="num">2019</div>
      <div class="lbl">Founded</div>
    </div>
  </div>
  <div class="about-text">
    <div class="section-tag reveal">About Us</div>
    <h2 class="section-title reveal reveal-delay-1">WE ARE <span class="red">MORE</span><br>THAN<br><span class="stroke">DESIGNERS</span></h2>
    <p class="reveal reveal-delay-2">Lee Samaz Studio is a premium creative media and branding studio based in Pretoria, South Africa. Founded by Lee Samunawo, what started as a one-man creative hustle has evolved into a dynamic team of 6 passionate specialists — each mastering different domains of visual design, media production, and digital strategy.</p>
    <p class="reveal reveal-delay-3">We are storytellers, visual architects, and brand builders. Every project is approached with cinematic storytelling principles — delivering work that carries emotional weight, atmosphere, and creative depth. Proudly African. Globally competitive. Always authentic.</p>
    <div class="about-values">
      <div class="value-card reveal reveal-delay-1">
        <div class="value-title">Creativity</div>
        <div class="value-desc">We push boundaries and explore new creative frontiers for every client.</div>
      </div>
      <div class="value-card reveal reveal-delay-2">
        <div class="value-title">Quality</div>
        <div class="value-desc">Premium output on every project — no shortcuts, no compromises.</div>
      </div>
      <div class="value-card reveal reveal-delay-3">
        <div class="value-title">Impact</div>
        <div class="value-desc">We measure success by the real-world results our work creates.</div>
      </div>
      <div class="value-card reveal reveal-delay-4">
        <div class="value-title">Culture</div>
        <div class="value-desc">Proudly African, globally competitive, always authentic.</div>
      </div>
    </div>
  </div>
</section>

<!-- SERVICES -->
<section id="services">
  <div class="services-header">
    <div>
      <div class="section-tag reveal">What We Do</div>
      <h2 class="section-title reveal reveal-delay-1">OUR <span class="red">SERVICES</span><br><span class="stroke">& EXPERTISE</span></h2>
    </div>
    <a href="#contact" class="btn-outline reveal">Get Custom Quote ↗</a>
  </div>
  <div class="services-grid">
    <div class="service-card reveal">
      <span class="service-num">01</span>
      <span class="service-icon">🎨</span>
      <div class="service-name">Graphic Design</div>
      <div class="service-desc">Flyers, posters, banners, menus, certificates, invitations, social media graphics and much more. Built to communicate, captivate, and convert.</div>
      <span class="service-price">From R250</span>
    </div>
    <div class="service-card reveal reveal-delay-1">
      <span class="service-num">02</span>
      <span class="service-icon">⬡</span>
      <div class="service-name">Logo & Branding</div>
      <div class="service-desc">Custom logo design, brand guidelines, colour palettes, typography systems and complete brand identity kits.</div>
      <span class="service-price">From R500</span>
    </div>
    <div class="service-card reveal reveal-delay-2">
      <span class="service-num">03</span>
      <span class="service-icon">📸</span>
      <div class="service-name">Photography</div>
      <div class="service-desc">Event photography, product shoots, portrait sessions, corporate headshots, weddings, lobola, and lifestyle photography.</div>
      <span class="service-price">From R600</span>
    </div>
    <div class="service-card reveal reveal-delay-3">
      <span class="service-num">04</span>
      <span class="service-icon">🎬</span>
      <div class="service-name">Video Editing</div>
      <div class="service-desc">Professional video editing, reels, highlight videos, drone footage, corporate promos and cinematic cuts.</div>
      <span class="service-price">From R500</span>
    </div>
    <div class="service-card reveal">
      <span class="service-num">05</span>
      <span class="service-icon">🚁</span>
      <div class="service-name">Drone Cinema</div>
      <div class="service-desc">High-definition aerial media, luxury real estate showcases, commercial aerial promotions and cinematic event capture.</div>
      <span class="service-price">From R1,500</span>
    </div>
    <div class="service-card reveal reveal-delay-1">
      <span class="service-num">06</span>
      <span class="service-icon">📱</span>
      <div class="service-name">Social Media</div>
      <div class="service-desc">Content creation, page management, ad design, campaign strategy and digital marketing consultation.</div>
      <span class="service-price">From R1,500/mo</span>
    </div>
    <div class="service-card reveal reveal-delay-2">
      <span class="service-num">07</span>
      <span class="service-icon">💍</span>
      <div class="service-name">Weddings & Events</div>
      <div class="service-desc">Full event branding, wedding stationery, signage, backdrops, lobola packages and day-of materials.</div>
      <span class="service-price">From R1,000</span>
    </div>
    <div class="service-card reveal reveal-delay-3">
      <span class="service-num">08</span>
      <span class="service-icon">🏗️</span>
      <div class="service-name">3D Architecture</div>
      <div class="service-desc">Photorealistic 3D renders, 2D floor plans, interior space visualization and luxury exterior presentations.</div>
      <span class="service-price">From R2,500</span>
    </div>
  </div>
</section>

<!-- PORTFOLIO -->
<section id="portfolio">
  <div class="inner-pad">
    <div class="section-tag reveal">Our Work</div>
    <h2 class="section-title reveal reveal-delay-1">SELECTED <span class="red">PORTFOLIO</span><br><span class="stroke">& PROJECTS</span></h2>
    <div class="portfolio-filter reveal reveal-delay-2">
      <button class="filter-btn active">All Work</button>
      <button class="filter-btn">Design</button>
      <button class="filter-btn">Photography</button>
      <button class="filter-btn">Events</button>
      <button class="filter-btn">Branding</button>
    </div>
  </div>
  <div class="portfolio-masonry">
    <div class="portfolio-item pi-1">
      <img src="/mnt/user-data/uploads/394406.jpg" alt="Brand Design">
      <div class="portfolio-overlay">
        <div>
          <div class="portfolio-cat">Graphic Design</div>
          <div class="portfolio-label">Farida Skincare Branding</div>
        </div>
      </div>
    </div>
    <div class="portfolio-item pi-2">
      <img src="/mnt/user-data/uploads/394385.jpg" alt="Branding">
      <div class="portfolio-overlay">
        <div>
          <div class="portfolio-cat">Branding</div>
          <div class="portfolio-label">Brand Identity Kit</div>
        </div>
      </div>
    </div>
    <div class="portfolio-item pi-3">
      <img src="/mnt/user-data/uploads/394359.jpg" alt="Wedding">
      <div class="portfolio-overlay">
        <div>
          <div class="portfolio-cat">Photography</div>
          <div class="portfolio-label">Couples Session</div>
        </div>
      </div>
    </div>
    <div class="portfolio-item pi-4">
      <img src="/mnt/user-data/uploads/394388.jpg" alt="Graphic Design">
      <div class="portfolio-overlay">
        <div>
          <div class="portfolio-cat">Design</div>
          <div class="portfolio-label">Poster Series</div>
        </div>
      </div>
    </div>
    <div class="portfolio-item pi-5">
      <img src="/mnt/user-data/uploads/394391.jpg" alt="Event Setup">
      <div class="portfolio-overlay">
        <div>
          <div class="portfolio-cat">Events</div>
          <div class="portfolio-label">Lobola Luncheon Design</div>
        </div>
      </div>
    </div>
    <div class="portfolio-item pi-6">
      <img src="/mnt/user-data/uploads/394393.jpg" alt="Logo Design">
      <div class="portfolio-overlay">
        <div>
          <div class="portfolio-cat">Photography</div>
          <div class="portfolio-label">Traditional Ceremony</div>
        </div>
      </div>
    </div>
    <div class="portfolio-item pi-7">
      <img src="/mnt/user-data/uploads/394409.jpg" alt="Photography">
      <div class="portfolio-overlay">
        <div>
          <div class="portfolio-cat">Photography</div>
          <div class="portfolio-label">Portrait Session</div>
        </div>
      </div>
    </div>
    <div class="portfolio-item pi-8">
      <img src="/mnt/user-data/uploads/394369.jpg" alt="Wedding">
      <div class="portfolio-overlay">
        <div>
          <div class="portfolio-cat">Events</div>
          <div class="portfolio-label">Wedding Styling</div>
        </div>
      </div>
    </div>
    <div class="portfolio-item pi-9">
      <img src="/mnt/user-data/uploads/394386.jpg" alt="Design Work">
      <div class="portfolio-overlay">
        <div>
          <div class="portfolio-cat">Graphic Design</div>
          <div class="portfolio-label">Agricultural Campaign</div>
        </div>
      </div>
    </div>
    <div class="portfolio-item pi-10">
      <img src="/mnt/user-data/uploads/394383.jpg" alt="Event Design">
      <div class="portfolio-overlay">
        <div>
          <div class="portfolio-cat">Branding</div>
          <div class="portfolio-label">Logo Design Collection</div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- COURSES / ACADEMY -->
<section id="courses">
  <div class="section-tag reveal">Lee Samaz Academy</div>
  <h2 class="section-title reveal reveal-delay-1">LEARN <span class="red">CREATIVE</span><br><span class="stroke">SKILLS ONLINE</span></h2>
  <p class="reveal reveal-delay-2" style="max-width:540px;font-size:15px;line-height:1.8;color:rgba(245,242,237,0.55);margin-top:16px;">100% online. Learn from anywhere. Build a real portfolio and launch your creative career with practical, mentor-led courses.</p>
  <div class="courses-grid">
    <div class="course-card reveal">
      <div class="course-duration">3 Months · Beginner</div>
      <div class="course-name">GRAPHIC DESIGN<br>BEGINNER COURSE</div>
      <div class="course-desc">Master design fundamentals — typography, layout, colour theory, and your first professional projects.</div>
      <div class="course-price">R1,500 <small>ZAR · Full course</small></div>
      <ul class="course-features">
        <li>Video tutorials — learn at your pace</li>
        <li>Weekly practical assignments</li>
        <li>1-on-1 mentorship sessions</li>
        <li>Portfolio-building projects</li>
        <li>WhatsApp support group</li>
      </ul>
      <a href="#contact" class="btn-primary" style="display:inline-block;margin-top:28px;">Enroll Now</a>
    </div>
    <div class="course-card reveal reveal-delay-1" style="border-top:2px solid var(--gold)">
      <div class="course-duration">6 Months · Advanced</div>
      <div class="course-name">PROFESSIONAL DESIGN<br>MASTERCLASS</div>
      <div class="course-desc">Advanced branding, luxury identity design, marketing campaigns, and client-ready deliverables.</div>
      <div class="course-price">R3,500 <small>ZAR · Full course</small></div>
      <ul class="course-features">
        <li>All Beginner Course content</li>
        <li>Advanced branding modules</li>
        <li>Business & pricing skills</li>
        <li>Freelance career launch kit</li>
        <li>Certificate of completion</li>
      </ul>
      <a href="#contact" class="btn-primary" style="display:inline-block;margin-top:28px;background:var(--gold);">Enroll Now</a>
    </div>
    <div class="course-card reveal reveal-delay-2">
      <div class="course-duration">3–4 Months</div>
      <div class="course-name">PHOTOGRAPHY<br>COURSE</div>
      <div class="course-desc">Camera operation, lighting techniques, editing in Lightroom/Photoshop, and building a photography portfolio.</div>
      <div class="course-price">R2,800 <small>ZAR · Full course</small></div>
      <ul class="course-features">
        <li>Camera basics to pro techniques</li>
        <li>Studio & natural lighting</li>
        <li>Professional retouching</li>
        <li>Event photography prep</li>
        <li>1-on-1 mentorship</li>
      </ul>
      <a href="#contact" class="btn-primary" style="display:inline-block;margin-top:28px;">Enroll Now</a>
    </div>
    <div class="course-card reveal">
      <div class="course-duration">2–3 Months</div>
      <div class="course-name">DRONE<br>CINEMATOGRAPHY</div>
      <div class="course-desc">Aerial storytelling, flight operations, post-production colour grading and commercial drone content creation.</div>
      <div class="course-price">R2,500 <small>ZAR · Full course</small></div>
      <ul class="course-features">
        <li>Flight operation basics</li>
        <li>Cinematic drone techniques</li>
        <li>Colour grading workflow</li>
        <li>Commercial applications</li>
        <li>Portfolio project</li>
      </ul>
      <a href="#contact" class="btn-primary" style="display:inline-block;margin-top:28px;">Enroll Now</a>
    </div>
    <div class="course-card reveal reveal-delay-1">
      <div class="course-duration">5–6 Months</div>
      <div class="course-name">2D & 3D<br>ARCHITECTURE</div>
      <div class="course-desc">SketchUp-based layouts, photorealistic 3D renders, interior visualization and architectural brief translation.</div>
      <div class="course-price">R4,500 <small>ZAR · Full course</small></div>
      <ul class="course-features">
        <li>SketchUp foundations</li>
        <li>Floor plan design</li>
        <li>3D photorealistic rendering</li>
        <li>Interior & exterior projects</li>
        <li>Spatial psychology mapping</li>
      </ul>
      <a href="#contact" class="btn-primary" style="display:inline-block;margin-top:28px;">Enroll Now</a>
    </div>
    <div class="course-card reveal reveal-delay-2" style="display:flex;flex-direction:column;justify-content:center;align-items:center;text-align:center;background:rgba(232,0,29,0.04);">
      <div style="font-family:'Bebas Neue',sans-serif;font-size:56px;line-height:1;margin-bottom:16px;">START<br><span style="color:var(--red)">TODAY</span></div>
      <p style="font-size:13px;color:rgba(245,242,237,0.5);line-height:1.7;max-width:240px;margin-bottom:28px;">All courses are 100% online. No qualifications needed — just the drive to create.</p>
      <a href="https://wa.me/27618201231" class="btn-primary">WhatsApp to Enroll</a>
      <div style="margin-top:20px;font-size:11px;letter-spacing:2px;text-transform:uppercase;color:rgba(245,242,237,0.3);">+27 61 820 1231</div>
    </div>
  </div>
</section>

<!-- PRICING -->
<section id="pricing">
  <div class="section-tag reveal">Pricing</div>
  <h2 class="section-title reveal reveal-delay-1">TRANSPARENT<br><span class="red">FAIR</span> <span class="stroke">PRICING</span></h2>
  <p class="reveal reveal-delay-2" style="max-width:480px;font-size:15px;line-height:1.8;color:rgba(245,242,237,0.55);margin-top:16px;">No hidden costs. No surprises. Final quotes depend on project scope — contact us for a custom package tailored to your vision.</p>
  <div class="pricing-grid">
    <div class="price-card reveal">
      <div class="price-tier">Starter Package</div>
      <div class="price-amount"><sup>R</sup>350</div>
      <div class="price-from">Starting from</div>
      <ul class="price-features">
        <li><span class="check">✦</span> Single logo design</li>
        <li><span class="check">✦</span> Business card design</li>
        <li><span class="check">✦</span> 2 social media posts</li>
        <li><span class="check">✦</span> 3 revision rounds</li>
        <li><span class="check">✦</span> PNG + PDF delivery</li>
        <li style="color:rgba(245,242,237,0.2)"><span style="color:rgba(245,242,237,0.15)">✦</span> Brand guidelines</li>
        <li style="color:rgba(245,242,237,0.2)"><span style="color:rgba(245,242,237,0.15)">✦</span> Social media kit</li>
      </ul>
      <a href="#contact" class="price-btn outline">Get Started</a>
    </div>
    <div class="price-card featured reveal reveal-delay-1">
      <div class="price-tier">Professional Package</div>
      <div class="price-amount"><sup>R</sup>1,500</div>
      <div class="price-from">Starting from</div>
      <ul class="price-features">
        <li><span class="check">✦</span> Full brand identity</li>
        <li><span class="check">✦</span> Logo + style guide</li>
        <li><span class="check">✦</span> Social media kit</li>
        <li><span class="check">✦</span> Business card + letterhead</li>
        <li><span class="check">✦</span> 5 revision rounds</li>
        <li><span class="check">✦</span> All file formats</li>
        <li style="color:rgba(245,242,237,0.2)"><span style="color:rgba(245,242,237,0.15)">✦</span> Monthly content mgmt</li>
      </ul>
      <a href="#contact" class="price-btn solid">Get Started</a>
    </div>
    <div class="price-card reveal reveal-delay-2">
      <div class="price-tier">Premium Package</div>
      <div class="price-amount"><sup>R</sup>4,000</div>
      <div class="price-from">Starting from</div>
      <ul class="price-features">
        <li><span class="check">✦</span> Complete brand package</li>
        <li><span class="check">✦</span> Logo + guidelines + assets</li>
        <li><span class="check">✦</span> Social media management</li>
        <li><span class="check">✦</span> 20 posts/month content</li>
        <li><span class="check">✦</span> Video editing included</li>
        <li><span class="check">✦</span> Priority support</li>
        <li><span class="check">✦</span> Unlimited revisions</li>
      </ul>
      <a href="#contact" class="price-btn outline">Get Started</a>
    </div>
  </div>
</section>

<!-- TESTIMONIALS -->
<section id="testimonials">
  <div class="testimonials-inner">
    <div class="testimonials-left">
      <div class="section-tag reveal">Testimonials</div>
      <h2 class="section-title reveal reveal-delay-1">REAL <span class="red">CLIENTS.</span><br>REAL<br><span class="stroke">RESULTS.</span></h2>
      <span class="big-quote">"</span>
      <p class="reveal" style="font-size:14px;color:rgba(245,242,237,0.45);line-height:1.8;">Join 200+ satisfied clients who trust Lee Samaz Studio to bring their vision to life.</p>
      <a href="https://wa.me/27618201231" class="btn-primary reveal" style="margin-top:32px;display:inline-block;">Start Your Project</a>
    </div>
    <div class="testimonials-right">
      <div class="testimonial-card reveal">
        <div class="testimonial-stars">★★★★★</div>
        <p class="testimonial-text">"Lee Samaz Studio transformed my brand completely. I went from looking like a side hustle to looking like a million-rand company. The logo they designed gets compliments every single day."</p>
        <div class="testimonial-author">Nomsa M.</div>
        <div class="testimonial-role">Entrepreneur, Pretoria</div>
      </div>
      <div class="testimonial-card reveal reveal-delay-1">
        <div class="testimonial-stars">★★★★★</div>
        <p class="testimonial-text">"Hired them for my sister's lobola event and they absolutely nailed every design element. The backdrop, the invitations, the signage — everything was perfection. Will use them again and again."</p>
        <div class="testimonial-author">Thabiso K.</div>
        <div class="testimonial-role">Event Organiser</div>
      </div>
      <div class="testimonial-card reveal reveal-delay-2">
        <div class="testimonial-stars">★★★★★</div>
        <p class="testimonial-text">"My menu designs and social media graphics have completely changed how customers see my restaurant. Within a month of launching the new brand, my bookings increased significantly."</p>
        <div class="testimonial-author">Busi N.</div>
        <div class="testimonial-role">Restaurant Owner</div>
      </div>
      <div class="testimonial-card reveal reveal-delay-3">
        <div class="testimonial-stars">★★★★★</div>
        <p class="testimonial-text">"The video editing for our company event was beyond our expectations. Professional, cinematic, and delivered ahead of schedule. Lee Samaz Studio is the real deal."</p>
        <div class="testimonial-author">Sipho D.</div>
        <div class="testimonial-role">Corporate Client</div>
      </div>
    </div>
  </div>
</section>

<!-- PROCESS -->
<section id="process">
  <div class="section-tag reveal">How We Work</div>
  <h2 class="section-title reveal reveal-delay-1">OUR <span class="red">CREATIVE</span><br><span class="stroke">PROCESS</span></h2>
  <div class="process-steps">
    <div class="process-step reveal">
      <div class="step-num">01</div>
      <div class="step-arrow">→</div>
      <div class="step-name">Discovery</div>
      <div class="step-desc">Deep consultation to understand your brand, goals, target audience, and creative vision.</div>
    </div>
    <div class="process-step reveal reveal-delay-1">
      <div class="step-num">02</div>
      <div class="step-arrow">→</div>
      <div class="step-name">Research</div>
      <div class="step-desc">We study your industry, competitors, and market to ground our creative strategy in insight.</div>
    </div>
    <div class="process-step reveal reveal-delay-2">
      <div class="step-num">03</div>
      <div class="step-arrow">→</div>
      <div class="step-name">Concept</div>
      <div class="step-desc">Our team develops multiple creative directions before presenting the strongest ideas.</div>
    </div>
    <div class="process-step reveal reveal-delay-3">
      <div class="step-num">04</div>
      <div class="step-arrow">→</div>
      <div class="step-name">Design</div>
      <div class="step-desc">We bring the chosen concept to life with expert craft — typography, colour, imagery.</div>
    </div>
    <div class="process-step reveal reveal-delay-4">
      <div class="step-num">05</div>
      <div class="step-arrow">→</div>
      <div class="step-name">Review</div>
      <div class="step-desc">You review, we listen. Revisions are made until every detail is exactly right for you.</div>
    </div>
    <div class="process-step reveal">
      <div class="step-num">06</div>
      <div class="step-name">Delivery</div>
      <div class="step-desc">Final files packaged professionally and delivered in all formats for print and digital use.</div>
    </div>
  </div>
</section>

<!-- CONTACT -->
<section id="contact">
  <div class="contact-inner">
    <div>
      <div class="section-tag reveal">Get In Touch</div>
      <h2 class="section-title reveal reveal-delay-1">LET'S <span class="red">BUILD</span><br>YOUR<br><span class="stroke">BRAND</span></h2>
      <p class="reveal reveal-delay-2" style="font-size:15px;line-height:1.8;color:rgba(245,242,237,0.55);margin-bottom:40px;">Ready to elevate your brand? Reach out and let's create something extraordinary together. We respond within 24 hours.</p>
      <div class="contact-info-item reveal">
        <span class="contact-info-icon">📞</span>
        <div>
          <div class="contact-info-label">Call / WhatsApp</div>
          <div class="contact-info-value">
            <a href="tel:+27618201231">+27 61 820 1231</a><br>
            <a href="tel:+27642948911">+27 64 294 8911</a>
          </div>
        </div>
      </div>
      <div class="contact-info-item reveal reveal-delay-1">
        <span class="contact-info-icon">✉️</span>
        <div>
          <div class="contact-info-label">Email</div>
          <div class="contact-info-value"><a href="mailto:leesamazstudio@gmail.com">leesamazstudio@gmail.com</a></div>
        </div>
      </div>
      <div class="contact-info-item reveal reveal-delay-2">
        <span class="contact-info-icon">📍</span>
        <div>
          <div class="contact-info-label">Location</div>
          <div class="contact-info-value">Pretoria, South Africa<br><span style="color:rgba(245,242,237,0.4);font-size:13px;">Nationwide & international delivery</span></div>
        </div>
      </div>
      <div class="social-row reveal">
        <a href="https://facebook.com/p/Lee-Samaz-Studio" class="social-link" target="_blank">Facebook</a>
        <a href="https://instagram.com/leesamaz.designer" class="social-link" target="_blank">Instagram</a>
        <a href="https://tiktok.com/@leesamazstudios" class="social-link" target="_blank">TikTok</a>
        <a href="https://x.com/designersamaz" class="social-link" target="_blank">Twitter/X</a>
        <a href="https://linkedin.com/in/lee-samaz" class="social-link" target="_blank">LinkedIn</a>
      </div>
    </div>
    <div class="contact-form reveal">
      <div class="form-row">
        <div class="form-group">
          <label>First Name</label>
          <input type="text" placeholder="Lee">
        </div>
        <div class="form-group">
          <label>Last Name</label>
          <input type="text" placeholder="Samaz">
        </div>
      </div>
      <div class="form-group">
        <label>Email Address</label>
        <input type="email" placeholder="you@yourbrand.com">
      </div>
      <div class="form-group">
        <label>Phone / WhatsApp</label>
        <input type="tel" placeholder="+27 ...">
      </div>
      <div class="form-group">
        <label>Service Interested In</label>
        <select>
          <option value="">Select a service...</option>
          <option>Graphic Design</option>
          <option>Logo & Brand Identity</option>
          <option>Photography</option>
          <option>Video Editing & Cinematography</option>
          <option>Drone Cinematography</option>
          <option>Social Media & Digital Marketing</option>
          <option>Wedding & Event Design</option>
          <option>3D Architecture</option>
          <option>Online Academy Course</option>
          <option>Full Brand Package</option>
        </select>
      </div>
      <div class="form-group">
        <label>Tell Us About Your Project</label>
        <textarea placeholder="Describe your vision, budget, deadline..."></textarea>
      </div>
      <button class="form-submit" onclick="handleSubmit(event)">Send Message ✦</button>
      <p id="form-success" style="display:none;color:var(--red);font-size:13px;letter-spacing:1px;margin-top:12px;">✦ Message received! We'll respond within 24 hours.</p>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <div class="footer-copy">© 2024–2025 Lee Samaz Studio. All Rights Reserved.</div>
  <div class="footer-logo"><span>LEE</span> SAMAZ STUDIO</div>
  <div class="footer-tagline">Your Vision. Our Art.</div>
</footer>

<script>
  // Custom cursor
  const cursor = document.getElementById('cursor');
  const follower = document.getElementById('cursor-follower');
  let mouseX = 0, mouseY = 0, followerX = 0, followerY = 0;

  document.addEventListener('mousemove', (e) => {
    mouseX = e.clientX; mouseY = e.clientY;
    cursor.style.left = mouseX + 'px';
    cursor.style.top = mouseY + 'px';
  });

  function animateFollower() {
    followerX += (mouseX - followerX) * 0.1;
    followerY += (mouseY - followerY) * 0.1;
    follower.style.left = followerX + 'px';
    follower.style.top = followerY + 'px';
    requestAnimationFrame(animateFollower);
  }
  animateFollower();

  document.querySelectorAll('a, button').forEach(el => {
    el.addEventListener('mouseenter', () => {
      cursor.style.width = '20px'; cursor.style.height = '20px';
      follower.style.width = '56px'; follower.style.height = '56px';
    });
    el.addEventListener('mouseleave', () => {
      cursor.style.width = '12px'; cursor.style.height = '12px';
      follower.style.width = '36px'; follower.style.height = '36px';
    });
  });

  // Nav scroll
  const navbar = document.getElementById('navbar');
  window.addEventListener('scroll', () => {
    navbar.classList.toggle('scrolled', window.scrollY > 60);
  });

  // Reveal on scroll
  const reveals = document.querySelectorAll('.reveal');
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        entry.target.classList.add('visible');
        observer.unobserve(entry.target);
      }
    });
  }, { threshold: 0.12 });
  reveals.forEach(el => observer.observe(el));

  // Portfolio filter (visual only)
  document.querySelectorAll('.filter-btn').forEach(btn => {
    btn.addEventListener('click', () => {
      document.querySelectorAll('.filter-btn').forEach(b => b.classList.remove('active'));
      btn.classList.add('active');
    });
  });

  // Form submit
  function handleSubmit(e) {
    e.preventDefault();
    document.getElementById('form-success').style.display = 'block';
  }

  // Smooth scroll for nav links
  document.querySelectorAll('a[href^="#"]').forEach(a => {
    a.addEventListener('click', e => {
      e.preventDefault();
      const target = document.querySelector(a.getAttribute('href'));
      if (target) target.scrollIntoView({ behavior: 'smooth' });
    });
  });
</script>
</body>
</html>
