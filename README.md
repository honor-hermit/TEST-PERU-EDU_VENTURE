<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Peru EduVenture | 페루 교육 탐험 | US to Peru</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,700;0,900;1,400&family=DM+Sans:wght@300;400;500;600&family=Noto+Serif+KR:wght@400;700;900&display=swap" rel="stylesheet">
<style>
  :root {
    --sun: #F5A623;
    --earth: #C4703A;
    --jungle: #2D6A4F;
    --sky: #1A3A5C;
    --cream: #FAF5EC;
    --gold: #D4A847;
    --snow: #FFFFFF;
    --mist: rgba(250,245,236,0.08);
    --shadow: rgba(20,10,5,0.55);
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  html { scroll-behavior: smooth; }

  body {
    font-family: 'DM Sans', sans-serif;
    background: var(--cream);
    color: var(--sky);
    overflow-x: hidden;
  }

  /* ── LANGUAGE TOGGLE ── */
  .lang-bar {
    position: fixed; top: 0; left: 0; right: 0; z-index: 999;
    display: flex; justify-content: space-between; align-items: center;
    padding: 12px 32px;
    background: rgba(26,58,92,0.92);
    backdrop-filter: blur(10px);
    gap: 12px;
  }
  .lang-bar-left { display: flex; align-items: center; }
  .concept-btn {
    display: flex; align-items: center; gap: 8px;
    background: rgba(245,166,35,0.15);
    border: 1.5px solid rgba(245,166,35,0.5);
    color: var(--sun); padding: 6px 18px; border-radius: 20px;
    font-size: 0.82rem; font-weight: 700; cursor: pointer;
    letter-spacing: 0.04em; text-decoration: none;
    transition: all 0.25s; white-space: nowrap;
    font-family: 'DM Sans', 'Noto Serif KR', sans-serif;
  }
  .concept-btn:hover { background: var(--sun); color: var(--sky); border-color: var(--sun); }
  .concept-btn .dot { width: 7px; height: 7px; border-radius: 50%; background: var(--sun); flex-shrink:0; animation: blink 1.8s infinite; }
  .concept-btn:hover .dot { background: var(--sky); }
  @keyframes blink { 0%,100%{opacity:1;transform:scale(1)} 50%{opacity:0.4;transform:scale(1.5)} }
  .lang-bar-right { display: flex; gap: 12px; align-items: center; }
  .lang-btn {
    background: none; border: 1.5px solid rgba(255,255,255,0.4);
    color: #fff; padding: 5px 16px; border-radius: 20px;
    font-size: 0.82rem; cursor: pointer; letter-spacing: 0.05em;
    transition: all 0.25s;
  }
  .lang-btn.active, .lang-btn:hover {
    background: var(--gold); border-color: var(--gold); color: var(--sky);
  }
  .lang-btn { font-family: 'DM Sans', 'Noto Serif KR', sans-serif; }

  /* ── HERO ── */
  .hero {
    min-height: 100vh;
    background:
      linear-gradient(180deg, rgba(26,58,92,0.75) 0%, rgba(196,112,58,0.55) 60%, rgba(45,106,79,0.7) 100%),
      url('https://images.unsplash.com/photo-1526392060635-9d6019884377?w=1800&q=80') center/cover no-repeat;
    display: flex; flex-direction: column; justify-content: center; align-items: center;
    text-align: center; padding: 80px 24px 60px;
    position: relative; overflow: hidden;
  }
  .hero::before {
    content: '';
    position: absolute; inset: 0;
    background: radial-gradient(ellipse at 50% 80%, rgba(245,166,35,0.18) 0%, transparent 70%);
  }
  .hero-badge {
    background: var(--gold); color: var(--sky);
    font-size: 0.78rem; font-weight: 600; letter-spacing: 0.14em; text-transform: uppercase;
    padding: 6px 20px; border-radius: 20px; margin-bottom: 28px;
    animation: fadeDown 0.9s ease both;
  }
  .hero h1 {
    font-family: 'Playfair Display', 'Noto Serif KR', serif;
    font-size: clamp(2.8rem, 7vw, 6.2rem);
    font-weight: 900; line-height: 1.08;
    color: #fff;
    text-shadow: 0 4px 32px var(--shadow);
    margin-bottom: 12px;
    animation: fadeUp 1s 0.2s ease both;
  }
  .hero h1 .accent { color: var(--sun); font-style: italic; }
  .hero .subtitle {
    font-size: clamp(1rem, 2.2vw, 1.35rem);
    color: rgba(255,255,255,0.88);
    max-width: 640px; line-height: 1.65;
    margin: 18px auto 36px;
    animation: fadeUp 1s 0.4s ease both;
  }
  .hero .ko { font-family: 'Noto Serif KR', serif; font-size: 1.08rem; color: rgba(255,255,255,0.72); display: block; margin-top: 6px; }
  .hero-cta {
    display: flex; gap: 16px; flex-wrap: wrap; justify-content: center;
    animation: fadeUp 1s 0.6s ease both;
  }
  .btn-primary {
    background: var(--sun); color: var(--sky);
    font-size: 1rem; font-weight: 700; padding: 16px 38px;
    border-radius: 50px; border: none; cursor: pointer;
    text-decoration: none; display: inline-block;
    box-shadow: 0 6px 30px rgba(245,166,35,0.45);
    transition: transform 0.2s, box-shadow 0.2s;
    font-family: 'DM Sans', 'Noto Serif KR', sans-serif;
  }
  .btn-primary:hover { transform: translateY(-3px); box-shadow: 0 12px 40px rgba(245,166,35,0.6); }
  .btn-outline {
    background: transparent; color: #fff;
    font-size: 1rem; font-weight: 600; padding: 15px 32px;
    border-radius: 50px; border: 2px solid rgba(255,255,255,0.6);
    cursor: pointer; text-decoration: none; display: inline-block;
    transition: all 0.2s;
    font-family: 'DM Sans', 'Noto Serif KR', sans-serif;
  }
  .btn-outline:hover { background: rgba(255,255,255,0.15); border-color: #fff; }

  /* Hemisphere indicator */
  .hemi-strip {
    background: linear-gradient(90deg, var(--sky) 50%, var(--jungle) 50%);
    color: #fff; text-align: center; padding: 14px 24px;
    font-size: 0.9rem; font-weight: 500; letter-spacing: 0.05em;
    display: flex; align-items: center; justify-content: center; gap: 18px;
    flex-wrap: wrap;
  }
  .hemi-strip .arrow { font-size: 1.4rem; color: var(--sun); }

  /* ── SECTIONS ── */
  section { padding: 80px 24px; }
  .container { max-width: 1100px; margin: 0 auto; }
  .section-label {
    font-size: 0.78rem; font-weight: 700; letter-spacing: 0.18em; text-transform: uppercase;
    color: var(--earth); margin-bottom: 10px;
  }
  .section-title {
    font-family: 'Playfair Display', 'Noto Serif KR', serif;
    font-size: clamp(2rem, 4.5vw, 3rem);
    font-weight: 900; line-height: 1.2; color: var(--sky);
    margin-bottom: 16px;
  }
  .section-title .ko-sub {
    display: block; font-size: 0.55em;
    color: var(--earth); font-weight: 700; margin-top: 4px;
  }
  .section-desc { font-size: 1.05rem; color: #4a5568; line-height: 1.75; max-width: 620px; }

  /* ── FEATURES GRID ── */
  .features { background: var(--sky); }
  .features .section-title { color: #fff; }
  .features .section-label { color: var(--sun); }
  .features .section-desc { color: rgba(255,255,255,0.72); }
  .feat-grid {
    display: grid; grid-template-columns: repeat(auto-fit, minmax(240px,1fr));
    gap: 24px; margin-top: 48px;
  }
  .feat-card {
    background: rgba(255,255,255,0.06); border: 1px solid rgba(255,255,255,0.12);
    border-radius: 20px; padding: 36px 28px;
    transition: transform 0.25s, background 0.25s;
  }
  .feat-card:hover { transform: translateY(-6px); background: rgba(255,255,255,0.11); }
  .feat-icon { font-size: 2.4rem; margin-bottom: 18px; display: block; }
  .feat-card h3 {
    font-family: 'Playfair Display', serif; font-size: 1.22rem;
    color: var(--sun); margin-bottom: 6px;
  }
  .feat-card .ko-h { font-family: 'Noto Serif KR', serif; font-size: 0.88rem; color: var(--gold); display: block; margin-bottom: 12px; }
  .feat-card p { font-size: 0.93rem; color: rgba(255,255,255,0.7); line-height: 1.65; }
  .feat-card .ko-p { font-family: 'Noto Serif KR', serif; font-size: 0.82rem; color: rgba(255,255,255,0.5); display: block; margin-top: 6px; }

  /* ── ITINERARY ── */
  .itinerary { background: var(--cream); }
  .timeline { margin-top: 48px; position: relative; }
  .timeline::before {
    content: ''; position: absolute; left: 32px; top: 0; bottom: 0; width: 2px;
    background: linear-gradient(180deg, var(--sun), var(--jungle));
  }
  .tl-item {
    display: flex; gap: 28px; margin-bottom: 36px; position: relative;
  }
  .tl-dot {
    width: 64px; height: 64px; border-radius: 50%;
    background: var(--sky); color: #fff; font-weight: 800;
    display: flex; align-items: center; justify-content: center;
    flex-shrink: 0; font-size: 0.82rem; border: 3px solid var(--sun);
    position: relative; z-index: 1;
    font-family: 'Playfair Display', serif;
  }
  .tl-body {
    background: #fff; border-radius: 16px; padding: 24px 28px;
    flex: 1; box-shadow: 0 2px 20px rgba(26,58,92,0.08);
    border-left: 4px solid var(--sun);
  }
  .tl-body h4 {
    font-family: 'Playfair Display', serif; font-size: 1.12rem;
    color: var(--sky); margin-bottom: 4px;
  }
  .tl-body .ko-tl { font-family: 'Noto Serif KR', serif; font-size: 0.82rem; color: var(--earth); display: block; margin-bottom: 10px; }
  .tl-body p { font-size: 0.93rem; color: #666; line-height: 1.65; }
  .tl-tag {
    display: inline-block; font-size: 0.72rem; font-weight: 700;
    padding: 3px 10px; border-radius: 10px; margin-top: 10px; margin-right: 6px;
    letter-spacing: 0.06em; text-transform: uppercase;
  }
  .tag-edu { background: rgba(45,106,79,0.12); color: var(--jungle); }
  .tag-fun { background: rgba(245,166,35,0.15); color: #a0690b; }
  .tag-health { background: rgba(196,112,58,0.12); color: var(--earth); }

  /* ── PRE-EDU ── */
  .pre-edu { background: linear-gradient(135deg, #fff8ee 0%, #f0f7f4 100%); }
  .pre-edu-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 48px; align-items: center; margin-top: 40px; }
  @media(max-width:700px) { .pre-edu-grid { grid-template-columns: 1fr; } }
  .pre-edu-img {
    border-radius: 24px; overflow: hidden;
    box-shadow: 0 12px 50px rgba(26,58,92,0.18);
    aspect-ratio: 4/3; position: relative;
  }
  .pre-edu-img img { width: 100%; height: 100%; object-fit: cover; }
  .pre-edu-img .yt-overlay {
    position: absolute; inset: 0;
    background: rgba(26,58,92,0.45);
    display: flex; flex-direction: column;
    align-items: center; justify-content: center;
    cursor: pointer; transition: background 0.2s;
    text-decoration: none;
  }
  .pre-edu-img .yt-overlay:hover { background: rgba(26,58,92,0.3); }
  .yt-play { width: 64px; height: 64px; background: #FF0000; border-radius: 50%; display: flex; align-items: center; justify-content: center; }
  .yt-play svg { fill: #fff; width: 28px; margin-left: 4px; }
  .yt-overlay span { color: #fff; margin-top: 12px; font-size: 0.9rem; font-weight: 600; }
  .pre-edu-list { list-style: none; margin-top: 24px; }
  .pre-edu-list li {
    display: flex; gap: 12px; align-items: flex-start;
    padding: 14px 0; border-bottom: 1px dashed rgba(26,58,92,0.12);
    font-size: 0.95rem; color: #4a5568; line-height: 1.6;
  }
  .pre-edu-list li .icon { font-size: 1.3rem; flex-shrink: 0; margin-top: 1px; }
  .pre-edu-list li .ko-li { font-family: 'Noto Serif KR', serif; font-size: 0.8rem; color: var(--earth); display: block; }

  /* ── ALTITUDE ── */
  .altitude { background: var(--earth); color: #fff; }
  .altitude .section-title { color: #fff; }
  .altitude .section-label { color: rgba(255,255,255,0.6); }
  .alt-cards { display: grid; grid-template-columns: repeat(auto-fit, minmax(200px,1fr)); gap: 20px; margin-top: 40px; }
  .alt-card {
    background: rgba(255,255,255,0.1); border-radius: 16px; padding: 28px 22px;
    border: 1px solid rgba(255,255,255,0.15); text-align: center;
  }
  .alt-card .icon { font-size: 2.2rem; margin-bottom: 14px; display: block; }
  .alt-card h4 { font-family: 'Playfair Display', serif; color: var(--sun); font-size: 1rem; margin-bottom: 4px; }
  .alt-card .ko-alt { font-family: 'Noto Serif KR', serif; font-size: 0.78rem; color: rgba(255,255,255,0.6); display: block; margin-bottom: 10px; }
  .alt-card p { font-size: 0.88rem; color: rgba(255,255,255,0.75); line-height: 1.6; }

  /* ── PRICING ── */
  .pricing { background: #fff; }
  .price-cards { display: grid; grid-template-columns: repeat(auto-fit, minmax(280px,1fr)); gap: 28px; margin-top: 48px; }
  .price-card {
    border-radius: 24px; padding: 40px 32px; text-align: center;
    border: 2px solid rgba(26,58,92,0.1);
    transition: transform 0.25s, box-shadow 0.25s;
    position: relative;
  }
  .price-card:hover { transform: translateY(-8px); box-shadow: 0 20px 60px rgba(26,58,92,0.14); }
  .price-card.featured {
    background: var(--sky); color: #fff;
    border-color: var(--sky);
    transform: scale(1.04);
  }
  .price-card.featured:hover { transform: scale(1.04) translateY(-6px); }
  .price-badge {
    position: absolute; top: -14px; left: 50%; transform: translateX(-50%);
    background: var(--sun); color: var(--sky);
    font-size: 0.72rem; font-weight: 800; padding: 5px 16px; border-radius: 20px;
    letter-spacing: 0.1em; text-transform: uppercase; white-space: nowrap;
  }
  .price-tier { font-size: 0.82rem; font-weight: 700; letter-spacing: 0.12em; text-transform: uppercase; color: var(--earth); margin-bottom: 8px; }
  .price-card.featured .price-tier { color: var(--sun); }
  .price-name { font-family: 'Playfair Display', serif; font-size: 1.5rem; font-weight: 900; color: var(--sky); margin-bottom: 4px; }
  .price-card.featured .price-name { color: #fff; }
  .price-ko { font-family: 'Noto Serif KR', serif; font-size: 0.82rem; color: var(--earth); display: block; margin-bottom: 18px; }
  .price-card.featured .price-ko { color: rgba(255,255,255,0.65); }
  .price-amount { font-size: 3rem; font-weight: 900; color: var(--sky); line-height: 1; }
  .price-card.featured .price-amount { color: var(--sun); }
  .price-per { font-size: 0.82rem; color: #888; }
  .price-card.featured .price-per { color: rgba(255,255,255,0.6); }
  .price-divider { height: 1px; background: rgba(26,58,92,0.1); margin: 22px 0; }
  .price-card.featured .price-divider { background: rgba(255,255,255,0.15); }
  .price-features { list-style: none; margin-bottom: 28px; text-align: left; }
  .price-features li { padding: 7px 0; font-size: 0.9rem; color: #555; display: flex; gap: 10px; }
  .price-card.featured .price-features li { color: rgba(255,255,255,0.82); }
  .price-features li::before { content: '✓'; color: var(--jungle); font-weight: 800; flex-shrink: 0; }
  .price-card.featured .price-features li::before { color: var(--sun); }

  /* ── YOUTUBE SECTION ── */
  .yt-section { background: linear-gradient(135deg, #1a1a2e, #16213e); color: #fff; }
  .yt-section .section-label { color: #ff6b6b; }
  .yt-section .section-title { color: #fff; }
  .yt-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(260px,1fr)); gap: 20px; margin-top: 40px; }
  .yt-card {
    background: rgba(255,255,255,0.05); border-radius: 16px; overflow: hidden;
    border: 1px solid rgba(255,255,255,0.1);
    text-decoration: none; transition: transform 0.2s, background 0.2s;
  }
  .yt-card:hover { transform: translateY(-5px); background: rgba(255,255,255,0.1); }
  .yt-thumb {
    position: relative; aspect-ratio: 16/9;
    background: linear-gradient(135deg, #2d3748, #1a202c);
    display: flex; align-items: center; justify-content: center;
    overflow: hidden;
  }
  .yt-thumb img { width: 100%; height: 100%; object-fit: cover; }
  .yt-play-sm { position: absolute; background: rgba(255,0,0,0.85); border-radius: 8px; padding: 8px 12px; }
  .yt-play-sm svg { fill: #fff; width: 18px; display: block; }
  .yt-info { padding: 16px 18px; }
  .yt-info h4 { font-size: 0.95rem; color: #fff; margin-bottom: 4px; line-height: 1.4; }
  .yt-info .ko-yt { font-family: 'Noto Serif KR', serif; font-size: 0.78rem; color: rgba(255,255,255,0.5); display: block; }

  /* ── FOOTER ── */
  footer {
    background: var(--sky); color: rgba(255,255,255,0.7);
    text-align: center; padding: 40px 24px;
    font-size: 0.88rem;
  }
  footer strong { color: var(--sun); }
  footer .ko-footer { font-family: 'Noto Serif KR', serif; display: block; margin-top: 6px; font-size: 0.82rem; }

  /* ── ANIMATIONS ── */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(30px); }
    to { opacity: 1; transform: translateY(0); }
  }
  @keyframes fadeDown {
    from { opacity: 0; transform: translateY(-20px); }
    to { opacity: 1; transform: translateY(0); }
  }

  /* ── LANG DISPLAY ── */
  .en { display: block; }
  .ko { display: none; }
  body.ko-mode .en { display: none !important; }
  body.ko-mode .ko { display: block !important; }
  body.ko-mode .ko-inline { display: inline !important; }
  body.ko-mode .en-inline { display: none !important; }
  .ko-inline { display: none; }
  .en-inline { display: inline; }

  /* Keep both visible elements where both needed */
  .bilingual .en, .bilingual .ko { display: block; }

  /* Responsive */
  @media(max-width:600px) {
    .timeline::before { left: 24px; }
    .tl-dot { width: 48px; height: 48px; font-size: 0.72rem; }
    .price-card.featured { transform: scale(1); }
  }
</style>
</head>
<body>

<!-- LANG BAR -->
<div class="lang-bar">
  <div class="lang-bar-left">
    <a href="concept.html" class="concept-btn">
      <span class="dot"></span>
      <span class="en-inline">What is Edu-Vacance?</span>
      <span class="ko-inline">에듀바캉스란?</span>
    </a>
  </div>
  <div class="lang-bar-right">
    <span style="color:rgba(255,255,255,0.6);font-size:0.82rem;">🌐</span>
    <button class="lang-btn active" onclick="setLang('en')" id="btn-en">English</button>
    <button class="lang-btn" onclick="setLang('ko')" id="btn-ko">한국어</button>
  </div>
</div>

<!-- HERO -->
<section class="hero">
  <div class="hero-badge">
    <span class="en-inline">✈ Summer 2025 · 14 Days · US → Peru</span>
    <span class="ko-inline">✈ 2025년 여름 · 14일 · 미국 → 페루</span>
  </div>
  <h1>
    <span class="en-inline">Discover <span class="accent">Peru</span><br>Through Young Eyes</span>
    <span class="ko-inline"><span class="accent">페루</span>를 탐험하다<br>아이들의 시선으로</span>
  </h1>
  <p class="subtitle">
    <span class="en-inline">An educational adventure from the Northern to Southern Hemisphere — where ancient civilizations meet mountain peaks and jungle wonders.</span>
    <span class="ko-inline">북반구에서 남반구로 — 고대 문명과 안데스 산맥, 정글의 경이로움이 만나는 교육적 모험.</span>
  </p>
  <div class="hero-cta">
    <a href="booking.html" class="btn-primary">
      <span class="en-inline">Book Now</span>
      <span class="ko-inline">지금 예약하기</span>
    </a>
    <a href="#features" class="btn-outline">
      <span class="en-inline">Learn More</span>
      <span class="ko-inline">자세히 보기</span>
    </a>
  </div>
</section>

<!-- HEMISPHERE STRIP -->
<div class="hemi-strip">
  <span>🇺🇸 <strong>United States</strong> — Northern Hemisphere</span>
  <span class="arrow">✈ →</span>
  <span>🇵🇪 <strong>Peru</strong> — Southern Hemisphere</span>
  <span style="font-size:0.78rem;opacity:0.7;width:100%;text-align:center;margin-top:4px;font-family:'Noto Serif KR',serif;">
    북반구 (미국) → 남반구 (페루) | 계절이 반대! 우리가 여름일 때 페루는 겨울 건기 — 최적의 탐험 시즌
  </span>
</div>

<!-- FEATURES -->
<section class="features" id="features">
  <div class="container">
    <div class="section-label">Why Peru EduVenture · 왜 페루 에듀벤처인가</div>
    <h2 class="section-title">
      <span class="en-inline">More Than a Vacation.</span>
      <span class="ko-inline">단순한 여행 그 이상.</span>
      <span class="section-title ko-sub" style="font-size:1rem;">
        <span class="en-inline">A transformative journey your child will never forget.</span>
        <span class="ko-inline">아이가 평생 기억할 변화의 여정.</span>
      </span>
    </h2>
    <div class="feat-grid">
      <div class="feat-card">
        <span class="feat-icon">🎒</span>
        <h3>Educational Field Trip</h3>
        <span class="ko-h">교육적 현장 학습</span>
        <p>Expert-guided visits to Machu Picchu, Nazca Lines, and the Amazon — turning history, geography, and science into living experiences.</p>
        <span class="ko-p">마추픽추, 나스카 라인, 아마존 — 역사, 지리, 과학이 살아있는 체험이 됩니다.</span>
      </div>
      <div class="feat-card">
        <span class="feat-icon">🌍</span>
        <h3>Hemisphere Discovery</h3>
        <span class="ko-h">반구 탐험</span>
        <p>Experience seasonal reversal firsthand — US summer becomes Peru's dry winter season, perfect for high-altitude trekking and exploration.</p>
        <span class="ko-p">북반구 여름 = 남반구 건기. 아이들이 지구과학을 몸으로 배웁니다.</span>
      </div>
      <div class="feat-card">
        <span class="feat-icon">🎡</span>
        <h3>Fun & Leisure</h3>
        <span class="ko-h">레저 & 즐거운 활동</span>
        <p>Sandboarding on desert dunes, cooking Peruvian cuisine, salsa dancing, and colorful festivals balanced with structured learning.</p>
        <span class="ko-p">사막 샌드보딩, 페루 요리 체험, 살사 댄싱 — 배움과 즐거움의 완벽한 균형.</span>
      </div>
      <div class="feat-card">
        <span class="feat-icon">🏔️</span>
        <h3>Altitude Safety Team</h3>
        <span class="ko-h">고산병 전담 안전팀</span>
        <p>Licensed medical professionals specializing in altitude sickness accompany every group. Acclimatization protocols designed for children.</p>
        <span class="ko-p">고산병 전문 의료진이 동행합니다. 어린이 맞춤 고도 적응 프로그램 포함.</span>
      </div>
      <div class="feat-card">
        <span class="feat-icon">📚</span>
        <h3>Pre-Trip Education</h3>
        <span class="ko-h">사전 교육 프로그램</span>
        <p>6-week prep curriculum with videos, worksheets, and live online sessions before departure — so kids arrive ready to learn deeply.</p>
        <span class="ko-p">출발 전 6주 사전 학습 커리큘럼으로 아이가 깊이 있는 학습을 준비합니다.</span>
      </div>
      <div class="feat-card">
        <span class="feat-icon">👨‍👩‍👧</span>
        <h3>Family-Centered</h3>
        <span class="ko-h">가족 중심 여행</span>
        <p>Designed for families with kids ages 8–16. Small groups of max 12 families ensure personalized attention and safe bonding experiences.</p>
        <span class="ko-p">8~16세 자녀를 둔 가족을 위한 맞춤 여행. 최대 12가족의 소그룹으로 운영됩니다.</span>
      </div>
    </div>
  </div>
</section>

<!-- ITINERARY -->
<section class="itinerary" id="itinerary">
  <div class="container">
    <div class="section-label">2-Week Journey · 2주 여정</div>
    <h2 class="section-title">
      <span class="en-inline">Your 14-Day Peru Adventure</span>
      <span class="ko-inline">14일 페루 탐험 일정</span>
    </h2>
    <p class="section-desc">
      <span class="en-inline">Every day is a masterclass in discovery — carefully sequenced to build knowledge while keeping energy and excitement high.</span>
      <span class="ko-inline">매일이 탐험의 연속 — 지식을 쌓으면서도 활력과 흥미를 유지하도록 정교하게 설계된 일정.</span>
    </p>
    <div class="timeline">
      <div class="tl-item">
        <div class="tl-dot">1–2</div>
        <div class="tl-body">
          <h4>Lima: Gateway to Peru</h4>
          <span class="ko-tl">리마: 페루의 관문</span>
          <p>Arrive, acclimatize at sea level, explore Miraflores district, visit Larco Museum (pre-Inca gold), and enjoy a welcome ceviche dinner.</p>
          <span class="tl-tag tag-edu">🏛 History</span>
          <span class="tl-tag tag-fun">🍽 Food</span>
        </div>
      </div>
      <div class="tl-item">
        <div class="tl-dot">3–5</div>
        <div class="tl-body">
          <h4>Cusco: Inca Capital & Altitude Adjustment</h4>
          <span class="ko-tl">쿠스코: 잉카 수도 & 고도 적응</span>
          <p>Gradual altitude ascent (3,400m). Medical team monitors each child. Explore Sacsayhuamán fortress, local markets, and traditional weaving workshops.</p>
          <span class="tl-tag tag-edu">🔬 Science</span>
          <span class="tl-tag tag-health">⚕ Medical Care</span>
          <span class="tl-tag tag-fun">🎨 Craft</span>
        </div>
      </div>
      <div class="tl-item">
        <div class="tl-dot">6–7</div>
        <div class="tl-body">
          <h4>Sacred Valley & Machu Picchu</h4>
          <span class="ko-tl">성스러운 계곡 & 마추픽추</span>
          <p>The crown jewel! Dawn entry to Machu Picchu with certified archaeologist guide. Terraced agriculture workshop, llama interaction, and sunset panoramic view.</p>
          <span class="tl-tag tag-edu">🗺 Geography</span>
          <span class="tl-tag tag-fun">🦙 Nature</span>
        </div>
      </div>
      <div class="tl-item">
        <div class="tl-dot">8–9</div>
        <div class="tl-body">
          <h4>Amazon Rainforest — Tambopata</h4>
          <span class="ko-tl">아마존 열대우림 — 탐보파타</span>
          <p>Jungle canopy walk, macaw clay lick observation at dawn, piranha fishing, medicinal plant tour with indigenous guides, and night wildlife spotting.</p>
          <span class="tl-tag tag-edu">🌿 Biology</span>
          <span class="tl-tag tag-fun">🦜 Wildlife</span>
        </div>
      </div>
      <div class="tl-item">
        <div class="tl-dot">10–11</div>
        <div class="tl-body">
          <h4>Lake Titicaca — World's Highest Lake</h4>
          <span class="ko-tl">티티카카 호수 — 세계 최고 고도 호수</span>
          <p>Float on reed islands built by the Uros people, kayaking, astronomy night session (clear skies at 3,800m), and homestay with local Quechua family.</p>
          <span class="tl-tag tag-edu">🔭 Astronomy</span>
          <span class="tl-tag tag-fun">🚣 Water Sports</span>
        </div>
      </div>
      <div class="tl-item">
        <div class="tl-dot">12–14</div>
        <div class="tl-body">
          <h4>Paracas, Nazca & Lima Farewell</h4>
          <span class="ko-tl">파라카스, 나스카 & 리마 작별</span>
          <p>Sandboarding in Huacachina desert oasis, Nazca Lines aerial tour, Ballestas Islands (Galápagos of Peru), and farewell gala dinner in Lima.</p>
          <span class="tl-tag tag-fun">🏄 Adventure</span>
          <span class="tl-tag tag-edu">✈ Aerial Tour</span>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- 360° VIRTUAL TOUR -->
<section style="background:#0f1e2e; padding:80px 24px;">
  <div class="container">
    <div class="section-label" style="color:var(--sun);">360° Virtual Tour · 360° 가상 투어</div>
    <h2 class="section-title" style="color:#fff; margin-bottom:10px;">
      <span class="en-inline">Step Inside Machu Picchu — Before You Go</span>
      <span class="ko-inline">떠나기 전, 마추픽추를 미리 경험하세요</span>
    </h2>
    <p class="section-desc" style="color:rgba(255,255,255,0.65); margin-bottom:36px;">
      <span class="en-inline">Explore the ancient Inca citadel in full 360° panorama. Drag to look around — this is what awaits you on Day 6 of your adventure.</span>
      <span class="ko-inline">고대 잉카 유적지를 360° 파노라마로 탐험해보세요. 드래그하여 주변을 둘러보세요 — 6일차에 직접 만나게 될 풍경입니다.</span>
    </p>
    <div style="
      border-radius: 20px;
      overflow: hidden;
      box-shadow: 0 20px 60px rgba(0,0,0,0.5);
      border: 1.5px solid rgba(255,255,255,0.1);
      max-width: 760px;
      margin: 0 auto;
    ">
      <iframe
        width="100%"
        height="450"
        src="https://www.airpano.com/embed.php?3D=machu-picchu-peru"
        frameborder="0"
        marginheight="0"
        marginwidth="0"
        scrolling="no"
        framespacing="0"
        allowfullscreen
        style="display:block;">
      </iframe>
    </div>
    <div style="text-align:right; max-width:760px; margin:10px auto 0; font-size:0.78rem; color:rgba(255,255,255,0.35);">
      Courtesy of <a href="https://www.airpano.com/" target="_blank" style="color:var(--gold); text-decoration:none;">www.AirPano.ru</a>
    </div>
    <p style="text-align:center; margin-top:20px; font-size:0.88rem; color:rgba(255,255,255,0.45);">
      <span class="en-inline">🖱 Click and drag to explore · Scroll to zoom · Best viewed fullscreen</span>
      <span class="ko-inline">🖱 클릭 후 드래그로 탐험 · 스크롤로 줌 · 전체화면으로 보면 더 좋아요</span>
    </p>
  </div>
</section>

<!-- PRE-EDUCATIONAL CONTENT -->
<section class="pre-edu" id="pre-edu">
  <div class="container">
    <div class="section-label">Pre-Trip Learning · 사전 학습 프로그램</div>
    <h2 class="section-title">
      <span class="en-inline">Learn Before You Go</span>
      <span class="ko-inline">출발 전, 먼저 배워요</span>
    </h2>
    <div class="pre-edu-grid">
      <div class="pre-edu-img">
        <img src="https://images.unsplash.com/photo-1503676260728-1c00da094a0b?w=800&q=80" alt="Kids learning">
        <a href="https://www.youtube.com/@NatGeoKids" target="_blank" class="yt-overlay">
          <div class="yt-play">
            <svg viewBox="0 0 24 24"><path d="M8 5v14l11-7z"/></svg>
          </div>
          <span>▶ Watch Our Educational Videos</span>
          <span style="font-family:'Noto Serif KR',serif;font-size:0.8rem;opacity:0.8;margin-top:4px;">▶ 교육 영상 보러가기</span>
        </a>
      </div>
      <div>
        <p class="section-desc" style="margin-bottom:8px;">
          <span class="en-inline">Six weeks before departure, your family receives our curated pre-education package — building excitement and knowledge together.</span>
          <span class="ko-inline">출발 6주 전부터 사전 교육 패키지를 제공합니다. 가족이 함께 기대감과 지식을 키워가는 시간.</span>
        </p>
        <ul class="pre-edu-list">
          <li>
            <span class="icon">📺</span>
            <div>
              <strong class="en-inline">Weekly YouTube Video Series</strong>
              <strong class="ko-inline">주간 유튜브 영상 시리즈</strong>
              <span class="ko-li">매주 페루의 역사, 지리, 문화에 대한 영상 제공</span>
              <br><span style="font-size:0.88rem;color:#666;" class="en-inline">Peru history, geography & culture videos released weekly</span>
            </div>
          </li>
          <li>
            <span class="icon">📝</span>
            <div>
              <strong class="en-inline">Printable Activity Workbooks</strong>
              <strong class="ko-inline">출력 가능한 학습 워크북</strong>
              <span class="ko-li">연령별 맞춤 워크시트와 퀴즈 포함</span>
              <br><span style="font-size:0.88rem;color:#666;" class="en-inline">Age-appropriate worksheets, maps, and quiz sheets</span>
            </div>
          </li>
          <li>
            <span class="icon">💻</span>
            <div>
              <strong class="en-inline">Live Online Q&A Sessions</strong>
              <strong class="ko-inline">실시간 온라인 Q&A 세션</strong>
              <span class="ko-li">전문 가이드와 직접 소통하는 준비 세션</span>
              <br><span style="font-size:0.88rem;color:#666;" class="en-inline">Bi-weekly Zoom with your expert guide before departure</span>
            </div>
          </li>
          <li>
            <span class="icon">🗺️</span>
            <div>
              <strong class="en-inline">Interactive Digital Map of Peru</strong>
              <strong class="ko-inline">페루 인터랙티브 디지털 지도</strong>
              <span class="ko-li">방문 예정지를 미리 탐색하는 디지털 지도</span>
              <br><span style="font-size:0.88rem;color:#666;" class="en-inline">Kids pin and explore every destination before arrival</span>
            </div>
          </li>
        </ul>
      </div>
    </div>
  </div>
</section>

<!-- ALTITUDE SAFETY -->
<section class="altitude" id="safety">
  <div class="container">
    <div class="section-label">Safety First · 안전 최우선</div>
    <h2 class="section-title" style="color:#fff;">
      <span class="en-inline">Altitude Sickness? We've Got It Covered.</span>
      <span class="ko-inline">고산병? 저희가 완벽히 대비합니다.</span>
    </h2>
    <p class="section-desc" style="color:rgba(255,255,255,0.75);">
      <span class="en-inline">Peru's Andean altitude (up to 3,800m) is manageable with the right preparation. Our specialized medical team ensures every child is safe and comfortable.</span>
      <span class="ko-inline">페루 안데스의 고도(최대 3,800m)는 적절한 준비로 안전하게 즐길 수 있습니다. 전담 의료팀이 모든 아이의 안전을 보장합니다.</span>
    </p>
    <div class="alt-cards">
      <div class="alt-card">
        <span class="icon">👩‍⚕️</span>
        <h4>On-Tour Medic</h4>
        <span class="ko-alt">동행 의료진</span>
        <p>Certified wilderness medicine doctor travels with every group, monitoring each child daily.</p>
      </div>
      <div class="alt-card">
        <span class="icon">📊</span>
        <h4>Acclimatization Protocol</h4>
        <span class="ko-alt">고도 적응 프로토콜</span>
        <p>Carefully staged altitude ascent over 3 days with rest periods and coca tea therapy.</p>
      </div>
      <div class="alt-card">
        <span class="icon">🧪</span>
        <h4>Oxygen Supply</h4>
        <span class="ko-alt">산소 공급 장비</span>
        <p>Portable oxygen concentrators available at all high-altitude accommodations.</p>
      </div>
      <div class="alt-card">
        <span class="icon">🏥</span>
        <h4>Emergency Network</h4>
        <span class="ko-alt">긴급 의료 네트워크</span>
        <p>Pre-arranged partnerships with top hospitals in Lima, Cusco, and Arequipa for rapid response.</p>
      </div>
      <div class="alt-card">
        <span class="icon">📋</span>
        <h4>Health Pre-Screening</h4>
        <span class="ko-alt">건강 사전 검진</span>
        <p>All participants complete health assessments 4 weeks before departure for personalized care plans.</p>
      </div>
    </div>
  </div>
</section>

<!-- PRICING -->
<section class="pricing" id="pricing">
  <div class="container">
    <div class="section-label">Investment · 여행 비용</div>
    <h2 class="section-title">
      <span class="en-inline">Choose Your Package</span>
      <span class="ko-inline">패키지를 선택하세요</span>
    </h2>
    <p class="section-desc">
      <span class="en-inline">All packages include flights from major US hubs, accommodation, meals, guides, pre-trip education kit, and medical support.</span>
      <span class="ko-inline">모든 패키지에는 미국 주요 도시 출발 항공편, 숙박, 식사, 가이드, 사전 교육 키트, 의료 지원이 포함됩니다.</span>
    </p>
    <div class="price-cards">
      <div class="price-card">
        <div class="price-tier">Explorer</div>
        <div class="price-name">Family Starter<br><span style="font-family:'Noto Serif KR',serif;font-size:0.7em;color:var(--earth);">기본 패키지</span></div>
        <div class="price-amount">$4,800</div>
        <div class="price-per">per person (adult) · 성인 1인 기준</div>
        <div class="price-divider"></div>
        <ul class="price-features">
          <li>14-day guided tour · 14일 가이드 투어</li>
          <li>4-star accommodation · 4성급 숙박</li>
          <li>All meals included · 전 식사 포함</li>
          <li>Pre-trip education kit · 사전 교육 키트</li>
          <li>Medical team support · 의료팀 지원</li>
          <li>Airport transfers · 공항 이동</li>
        </ul>
        <a href="booking.html" class="btn-primary" style="width:100%;text-align:center;display:block;">
          <span class="en-inline">Book Explorer</span>
          <span class="ko-inline">기본 예약하기</span>
        </a>
      </div>

      <div class="price-card featured">
        <div class="price-badge">⭐ Most Popular · 인기 1위</div>
        <div class="price-tier">Premium</div>
        <div class="price-name">EduVenture Plus<br><span style="font-family:'Noto Serif KR',serif;font-size:0.7em;">프리미엄 패키지</span></div>
        <div class="price-amount">$6,500</div>
        <div class="price-per">per person (adult) · 성인 1인 기준</div>
        <div class="price-divider"></div>
        <ul class="price-features">
          <li>Everything in Explorer</li>
          <li>5-star lodge upgrades · 5성급 업그레이드</li>
          <li>Exclusive Machu Picchu dawn access</li>
          <li>Amazon private boat charter</li>
          <li>Dedicated bilingual guide (EN/KO) · 영한 전담 가이드</li>
          <li>Live online classes (6 weeks) · 6주 온라인 수업</li>
          <li>Children 50% off · 어린이 50% 할인</li>
        </ul>
        <a href="booking.html" class="btn-primary" style="width:100%;text-align:center;display:block;background:var(--sun);">
          <span class="en-inline">Book Premium</span>
          <span class="ko-inline">프리미엄 예약하기</span>
        </a>
      </div>

      <div class="price-card">
        <div class="price-tier">Elite</div>
        <div class="price-name">Private Family<br><span style="font-family:'Noto Serif KR',serif;font-size:0.7em;color:var(--earth);">프라이빗 패키지</span></div>
        <div class="price-amount">$11,200</div>
        <div class="price-per">per family (up to 4) · 가족 기준 (최대 4인)</div>
        <div class="price-divider"></div>
        <ul class="price-features">
          <li>Fully private itinerary · 완전 맞춤 일정</li>
          <li>Private jet charter option · 전세기 옵션</li>
          <li>Personal physician · 전담 의사</li>
          <li>Custom curriculum · 맞춤 교육 커리큘럼</li>
          <li>Photography & video package</li>
          <li>Post-trip education report · 여행 후 교육 리포트</li>
        </ul>
        <a href="booking.html" class="btn-primary" style="width:100%;text-align:center;display:block;">
          <span class="en-inline">Book Private</span>
          <span class="ko-inline">프라이빗 예약하기</span>
        </a>
      </div>
    </div>
  </div>
</section>

<!-- YOUTUBE SECTION -->
<section class="yt-section" id="videos">
  <div class="container">
    <div class="section-label">📺 Educational Resources · 교육 자료</div>
    <h2 class="section-title">
      <span class="en-inline">Start Learning About Peru Today</span>
      <span class="ko-inline">오늘부터 페루를 배워보세요</span>
    </h2>
    <p class="section-desc" style="color:rgba(255,255,255,0.65);">
      <span class="en-inline">Watch our curated pre-trip videos and explore Peru before you even board the plane. Recommended YouTube channels below.</span>
      <span class="ko-inline">출발 전 추천 영상을 통해 페루를 미리 만나보세요. 아래 추천 채널에서 시작하세요.</span>
    </p>
    <div class="yt-grid">
      <a href="https://www.youtube.com/@NatGeoKids" target="_blank" class="yt-card">
        <div class="yt-thumb" style="background:linear-gradient(135deg,#1a3c5c,#0f2234);">
          <img src="https://img.youtube.com/vi/KXm9KHm7lhg/hqdefault.jpg" alt="Nat Geo Kids" onerror="this.style.display='none'">
          <div class="yt-play-sm"><svg viewBox="0 0 24 24"><path d="M8 5v14l11-7z"/></svg></div>
        </div>
        <div class="yt-info">
          <h4>Nat Geo Kids — Peru & Amazon</h4>
          <span class="ko-yt">내셔널 지오그래픽 키즈 — 페루 & 아마존</span>
        </div>
      </a>
      <a href="https://www.youtube.com/@crashcourse" target="_blank" class="yt-card">
        <div class="yt-thumb" style="background:linear-gradient(135deg,#2d4a1e,#1a2c12);">
          <img src="https://img.youtube.com/vi/GgPgbAFXOio/hqdefault.jpg" alt="Crash Course" onerror="this.style.display='none'">
          <div class="yt-play-sm"><svg viewBox="0 0 24 24"><path d="M8 5v14l11-7z"/></svg></div>
        </div>
        <div class="yt-info">
          <h4>CrashCourse — World History: Inca</h4>
          <span class="ko-yt">크래시코스 — 세계사: 잉카 제국</span>
        </div>
      </a>
      <a href="https://www.youtube.com/results?search_query=machu+picchu+kids+educational" target="_blank" class="yt-card">
        <div class="yt-thumb" style="background:linear-gradient(135deg,#4a1e2d,#2c1218);">
          <img src="https://img.youtube.com/vi/tE7IuJEqBWg/hqdefault.jpg" alt="Machu Picchu" onerror="this.style.display='none'">
          <div class="yt-play-sm"><svg viewBox="0 0 24 24"><path d="M8 5v14l11-7z"/></svg></div>
        </div>
        <div class="yt-info">
          <h4>Machu Picchu: Kid-Friendly Explainer</h4>
          <span class="ko-yt">마추픽추 어린이 설명 영상</span>
        </div>
      </a>
      <a href="https://www.youtube.com/results?search_query=amazon+rainforest+kids+documentary" target="_blank" class="yt-card">
        <div class="yt-thumb" style="background:linear-gradient(135deg,#1e3a2d,#0f2018);">
          <img src="https://img.youtube.com/vi/6tPr0g8KYEU/hqdefault.jpg" alt="Amazon" onerror="this.style.display='none'">
          <div class="yt-play-sm"><svg viewBox="0 0 24 24"><path d="M8 5v14l11-7z"/></svg></div>
        </div>
        <div class="yt-info">
          <h4>Amazon Rainforest — Kids' Documentary</h4>
          <span class="ko-yt">아마존 열대우림 — 어린이 다큐멘터리</span>
        </div>
      </a>
    </div>
    <div style="text-align:center;margin-top:32px;">
      <a href="https://www.youtube.com/results?search_query=peru+educational+kids+travel" target="_blank" class="btn-outline">
        <span class="en-inline">🎬 View Full YouTube Playlist</span>
        <span class="ko-inline">🎬 전체 유튜브 재생목록 보기</span>
      </a>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <strong>Peru EduVenture</strong> · Educational Travel Specialists
  <span class="ko-footer">페루 에듀벤처 · 교육 여행 전문</span>
  <p style="margin-top:14px;font-size:0.8rem;">
    📧 <a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="60090e060f2010051215050415050e141512054e030f0d">[email&#160;protected]</a> &nbsp;|&nbsp; 📞 +1 (800) 555-PERU &nbsp;|&nbsp; 💬 카카오톡: PeruEdu
  </p>
  <p style="margin-top:10px;font-size:0.75rem;opacity:0.55;">© 2025 Peru EduVenture LLC. All rights reserved. · 모든 권리 보유.</p>
</footer>

<script data-cfasync="false" src="/cdn-cgi/scripts/5c5dd728/cloudflare-static/email-decode.min.js"></script><script>
function setLang(lang) {
  document.bo
