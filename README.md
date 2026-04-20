<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Green Guinguette – Bal des Solutions</title>
<link href="https://fonts.googleapis.com/css2?family=Boogaloo&family=Fredoka:wght@400;600;700&display=swap" rel="stylesheet">
<style>
  :root {
    --orange: #F97316;
    --orange-dark: #EA580C;
    --green: #22C55E;
    --green-dark: #15803D;
    --green-deeper: #166534;
    --white: #ffffff;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    min-height: 100vh;
    background-color: var(--orange);
    font-family: 'Fredoka', sans-serif;
    display: flex;
    flex-direction: column;
    align-items: center;
    text-align: center;
    padding: 40px 20px 60px;
    background-image:
      radial-gradient(circle at 15% 20%, rgba(255,255,255,0.08) 0%, transparent 50%),
      radial-gradient(circle at 85% 80%, rgba(0,0,0,0.06) 0%, transparent 50%);
  }

  /* HEADER */
  .logo-wrap {
    margin-bottom: 6px;
    animation: popIn 0.6s cubic-bezier(0.34,1.56,0.64,1) both;
  }

  .logo-wrap h1 {
    font-family: 'Boogaloo', cursive;
    font-size: clamp(80px, 22vw, 130px);
    color: var(--green);
    line-height: 0.85;
    letter-spacing: -3px;
    text-shadow:
      5px 5px 0 var(--green-deeper),
      -2px -2px 0 var(--green-deeper),
      2px -2px 0 var(--green-deeper),
      -2px 2px 0 var(--green-deeper);
  }

  .badge {
    display: inline-block;
    background: var(--white);
    color: var(--orange-dark);
    font-family: 'Boogaloo', cursive;
    font-size: 18px;
    letter-spacing: 2px;
    padding: 5px 20px;
    border-radius: 999px;
    margin-bottom: 10px;
    border: 3px solid var(--orange-dark);
    animation: popIn 0.6s 0.1s cubic-bezier(0.34,1.56,0.64,1) both;
  }

  .welcome {
    font-family: 'Fredoka', sans-serif;
    font-weight: 700;
    font-size: clamp(14px, 4vw, 19px);
    color: var(--white);
    letter-spacing: 2px;
    text-transform: uppercase;
    margin-bottom: 32px;
    opacity: 0.95;
    animation: fadeUp 0.5s 0.2s ease both;
  }

  /* LINKS */
  .section-label {
    font-family: 'Fredoka', sans-serif;
    font-weight: 600;
    font-size: 11px;
    letter-spacing: 3.5px;
    text-transform: uppercase;
    color: rgba(255,255,255,0.65);
    margin-bottom: 10px;
    margin-top: 8px;
    width: 100%;
    max-width: 440px;
  }

  .links-col {
    width: 100%;
    max-width: 440px;
    display: flex;
    flex-direction: column;
    gap: 11px;
    margin-bottom: 20px;
  }

  .link-btn {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 12px;
    background: var(--green);
    color: var(--white);
    text-decoration: none;
    border-radius: 18px;
    padding: 15px 22px;
    font-family: 'Fredoka', sans-serif;
    font-weight: 700;
    font-size: 17px;
    border: 3px solid var(--green-dark);
    transition: transform 0.13s, background 0.13s, box-shadow 0.13s;
    box-shadow: 0 4px 0 var(--green-deeper);
    position: relative;
  }

  .link-btn:hover {
    background: var(--green-dark);
    transform: translateY(-3px);
    box-shadow: 0 7px 0 var(--green-deeper);
  }

  .link-btn:active {
    transform: translateY(2px);
    box-shadow: 0 2px 0 var(--green-deeper);
  }

  .link-btn .btn-icon {
    font-size: 22px;
    line-height: 1;
    flex-shrink: 0;
  }

  .btn-text {
    display: flex;
    flex-direction: column;
    align-items: center;
    flex: 1;
  }

  .btn-text span { display: block; }
  .btn-text .handle { font-size: 17px; font-weight: 700; }
  .btn-text .sub { font-size: 12px; font-weight: 400; opacity: 0.8; }

  /* EVENT CARD */
  .event-card {
    width: 100%;
    max-width: 440px;
    background: var(--white);
    border-radius: 22px;
    border: 3px solid var(--orange-dark);
    overflow: hidden;
    margin-bottom: 22px;
    box-shadow: 0 6px 0 var(--orange-dark);
    animation: fadeUp 0.5s 0.35s ease both;
  }

  .event-header {
    background: var(--green);
    padding: 14px 18px;
    border-bottom: 3px solid var(--green-dark);
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 10px;
  }

  .event-header .etitle {
    font-family: 'Boogaloo', cursive;
    font-size: 24px;
    color: var(--white);
    text-shadow: 2px 2px 0 var(--green-deeper);
    letter-spacing: 1px;
  }

  .event-header .enum {
    background: var(--white);
    color: var(--green-dark);
    font-family: 'Boogaloo', cursive;
    font-size: 14px;
    padding: 2px 10px;
    border-radius: 999px;
  }

  .event-body {
    padding: 18px 20px;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 12px;
  }

  .meta-row {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
    justify-content: center;
  }

  .meta-pill {
    background: #FFF7ED;
    border: 2px solid #FDBA74;
    border-radius: 999px;
    padding: 5px 14px;
    font-weight: 700;
    font-size: 13px;
    color: var(--orange-dark);
    font-family: 'Fredoka', sans-serif;
  }

  .feats-row {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
    justify-content: center;
  }

  .feat-tag {
    background: #F0FDF4;
    border: 2px solid #86EFAC;
    border-radius: 10px;
    padding: 5px 12px;
    font-weight: 700;
    font-size: 12px;
    color: var(--green-dark);
    font-family: 'Fredoka', sans-serif;
    letter-spacing: 0.5px;
  }

  .fb-btn {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 9px;
    width: 100%;
    background: #1877F2;
    color: var(--white);
    border: none;
    border-radius: 14px;
    padding: 13px 18px;
    font-family: 'Fredoka', sans-serif;
    font-weight: 700;
    font-size: 16px;
    cursor: pointer;
    text-decoration: none;
    transition: background 0.12s, transform 0.1s;
    box-shadow: 0 3px 0 #0D5EC5;
  }

  .fb-btn:hover { background: #0D65CE; transform: translateY(-2px); }
  .fb-btn:active { transform: translateY(1px); }

  /* QR SECTION */
  .qr-section {
    width: 100%;
    max-width: 440px;
    background: var(--white);
    border-radius: 22px;
    border: 3px solid var(--green-dark);
    padding: 22px 20px;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 14px;
    box-shadow: 0 6px 0 var(--green-deeper);
    animation: fadeUp 0.5s 0.45s ease both;
  }

  .qr-label {
    font-family: 'Boogaloo', cursive;
    font-size: 18px;
    color: var(--orange-dark);
    letter-spacing: 1px;
  }

  #qr-container canvas,
  #qr-container img {
    border-radius: 10px;
    display: block;
  }

  .qr-url {
    font-family: 'Fredoka', sans-serif;
    font-size: 12px;
    color: #9A3412;
    font-weight: 600;
    letter-spacing: 1px;
    text-transform: uppercase;
    word-break: break-all;
    max-width: 280px;
  }

  .footer {
    margin-top: 28px;
    font-family: 'Fredoka', sans-serif;
    font-size: 12px;
    color: rgba(255,255,255,0.45);
    font-weight: 600;
    letter-spacing: 2px;
    text-transform: uppercase;
  }

  /* ANIMATIONS */
  @keyframes popIn {
    from { opacity: 0; transform: scale(0.7); }
    to   { opacity: 1; transform: scale(1); }
  }

  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(18px); }
    to   { opacity: 1; transform: translateY(0); }
  }

  .link-btn { animation: fadeUp 0.4s ease both; }
  .link-btn:nth-child(1) { animation-delay: 0.22s; }
  .link-btn:nth-child(2) { animation-delay: 0.30s; }
  .link-btn:nth-child(3) { animation-delay: 0.38s; }
</style>
</head>
<body>

<div class="logo-wrap">
  <h1>GREEN</h1>
</div>
<div class="badge">GUINGUETTE #04</div>
<p class="welcome">🌿 Bienvenue au bal des solutions 🌿</p>

<!-- INSTAGRAM LINKS -->
<p class="section-label">Nos Instagrams</p>
<div class="links-col">
  <a href="https://www.instagram.com/genauassociation/" target="_blank" class="link-btn">
    <span class="btn-icon">🌱</span>
    <div class="btn-text">
      <span class="handle">@genauassociation</span>
      <span class="sub">Association Genau</span>
    </div>
  </a>
  <a href="https://www.instagram.com/we.r.solar/" target="_blank" class="link-btn">
    <span class="btn-icon">☀️</span>
    <div class="btn-text">
      <span class="handle">@we.r.solar</span>
      <span class="sub">We R Solar</span>
    </div>
  </a>
  <a href="https://www.instagram.com/lasonocyclette/" target="_blank" class="link-btn">
    <span class="btn-icon">🚲</span>
    <div class="btn-text">
      <span class="handle">@lasonocyclette</span>
      <span class="sub">La Sono Cyclette</span>
    </div>
  </a>
</div>

<!-- EVENT CARD -->
<div class="event-card">
  <div class="event-header">
    <span class="etitle">GREEN GUINGUETTE</span>
    <span class="enum">#04</span>
  </div>
  <div class="event-body">
    <div class="meta-row">
      <span class="meta-pill">📅 27 Sept.</span>
      <span class="meta-pill">⏰ 17h – 21h</span>
      <span class="meta-pill">📍 Parc du Heyritz</span>
    </div>
    <div class="feats-row">
      <span class="feat-tag">🎧 DJ SETS</span>
      <span class="feat-tag">🍹 FOOD & DRINKS</span>
      <span class="feat-tag">🎪 FREE OPEN AIR</span>
    </div>
    <a href="https://www.facebook.com/events/" target="_blank" class="fb-btn">
      <svg width="18" height="18" viewBox="0 0 24 24" fill="white">
        <path d="M24 12.073c0-6.627-5.373-12-12-12s-12 5.373-12 12c0 5.99 4.388 10.954 10.125 11.854v-8.385H7.078v-3.47h3.047V9.43c0-3.007 1.792-4.669 4.533-4.669 1.312 0 2.686.235 2.686.235v2.953H15.83c-1.491 0-1.956.925-1.956 1.874v2.25h3.328l-.532 3.47h-2.796v8.385C19.612 23.027 24 18.062 24 12.073z"/>
      </svg>
      Voir l'événement Facebook
    </a>
  </div>
</div>

<!-- QR CODE -->
<div class="qr-section">
  <p class="qr-label">📲 Scanner pour partager la page</p>
  <div id="qr-container"></div>
  <p class="qr-url" id="qr-url-label">green-guinguette · bal des solutions</p>
</div>

<p class="footer">Made with 💚 · Green Guinguette 2025</p>

<script src="https://cdn.jsdelivr.net/npm/qrcodejs@1.0.0/qrcode.min.js"></script>
<script>
  var pageUrl = window.location.href;
  document.getElementById('qr-url-label').textContent = pageUrl.length > 60
    ? pageUrl.slice(0, 57) + '...'
    : pageUrl;

  new QRCode(document.getElementById('qr-container'), {
    text: pageUrl,
    width: 200,
    height: 200,
    colorDark: '#15803D',
    colorLight: '#ffffff',
    correctLevel: QRCode.CorrectLevel.H
  });
</script>

</body>
</html>
