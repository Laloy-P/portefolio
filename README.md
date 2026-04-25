<html lang="fr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Portfolio — Développeur web freelance</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=DM+Serif+Display:ital@0;1&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet">
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --ink: #1a1a18;
    --ink-soft: #6b6b64;
    --paper: #f5f4ef;
    --accent: #c8a96e;
    --accent-light: #f0e8d5;
    --border: rgba(26,26,24,0.12);
    --serif: 'DM Serif Display', Georgia, serif;
    --sans: 'DM Sans', sans-serif;
  }

  html { scroll-behavior: smooth; }

  body {
    font-family: var(--sans);
    background: var(--paper);
    color: var(--ink);
    font-weight: 300;
    line-height: 1.7;
    overflow-x: hidden;
  }

  /* ── NAV ── */
  nav {
    position: fixed;
    top: 0; left: 0; right: 0;
    z-index: 100;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 1.5rem 4rem;
    background: var(--paper);
    border-bottom: 1px solid var(--border);
  }

  .nav-logo {
    font-family: var(--serif);
    font-size: 1.1rem;
    letter-spacing: 0.02em;
    color: var(--ink);
    text-decoration: none;
  }

  .nav-links {
    display: flex;
    gap: 2.5rem;
    list-style: none;
  }

  .nav-links a {
    font-size: 0.82rem;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    color: var(--ink-soft);
    text-decoration: none;
    transition: color 0.2s;
  }

  .nav-links a:hover { color: var(--ink); }

  /* ── HERO ── */
  #hero {
    min-height: 100vh;
    display: grid;
    grid-template-columns: 1fr 1fr;
    padding-top: 5rem;
  }

  .hero-left {
    display: flex;
    flex-direction: column;
    justify-content: center;
    padding: 6rem 4rem 6rem 4rem;
    border-right: 1px solid var(--border);
  }

  .hero-tag {
    font-size: 0.75rem;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    color: var(--accent);
    margin-bottom: 2rem;
    display: flex;
    align-items: center;
    gap: 0.75rem;
  }

  .hero-tag::before {
    content: '';
    display: block;
    width: 2rem;
    height: 1px;
    background: var(--accent);
  }

  .hero-title {
    font-family: var(--serif);
    font-size: clamp(2.8rem, 5vw, 4.5rem);
    line-height: 1.1;
    margin-bottom: 2rem;
    color: var(--ink);
  }

  .hero-title em {
    font-style: italic;
    color: var(--ink-soft);
  }

  .hero-desc {
    font-size: 1rem;
    color: var(--ink-soft);
    max-width: 38ch;
    margin-bottom: 3rem;
    line-height: 1.8;
  }

  .hero-cta {
    display: inline-flex;
    align-items: center;
    gap: 0.75rem;
    background: var(--ink);
    color: var(--paper);
    text-decoration: none;
    font-size: 0.82rem;
    letter-spacing: 0.08em;
    text-transform: uppercase;
    padding: 1rem 2rem;
    transition: background 0.2s, gap 0.2s;
    align-self: flex-start;
  }

  .hero-cta:hover {
    background: var(--accent);
    gap: 1.2rem;
  }

  .hero-cta-arrow { font-size: 1rem; }

  .hero-right {
    display: flex;
    flex-direction: column;
    justify-content: flex-end;
    padding: 6rem 4rem;
    gap: 3rem;
  }

  .hero-stats {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 2rem;
  }

  .stat {
    border-top: 1px solid var(--border);
    padding-top: 1.25rem;
  }

  .stat-number {
    font-family: var(--serif);
    font-size: 2.5rem;
    color: var(--ink);
    line-height: 1;
    margin-bottom: 0.4rem;
  }

  .stat-label {
    font-size: 0.78rem;
    letter-spacing: 0.08em;
    text-transform: uppercase;
    color: var(--ink-soft);
  }

  .hero-services {
    display: flex;
    flex-direction: column;
    gap: 0.75rem;
  }

  .service-item {
    display: flex;
    align-items: center;
    gap: 1rem;
    font-size: 0.9rem;
    color: var(--ink-soft);
    padding: 0.75rem 1rem;
    border: 1px solid transparent;
    transition: border-color 0.2s, color 0.2s;
    cursor: default;
  }

  .service-item:hover {
    border-color: var(--border);
    color: var(--ink);
  }

  .service-dot {
    width: 6px;
    height: 6px;
    border-radius: 50%;
    background: var(--accent);
    flex-shrink: 0;
  }

  /* ── PROJECTS ── */
  #projets {
    padding: 8rem 4rem;
    border-top: 1px solid var(--border);
  }

  .section-header {
    display: flex;
    justify-content: space-between;
    align-items: flex-end;
    margin-bottom: 5rem;
    border-bottom: 1px solid var(--border);
    padding-bottom: 2.5rem;
  }

  .section-label {
    font-size: 0.75rem;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    color: var(--accent);
    margin-bottom: 0.75rem;
  }

  .section-title {
    font-family: var(--serif);
    font-size: clamp(2rem, 3.5vw, 3rem);
    line-height: 1.15;
  }

  .section-count {
    font-family: var(--serif);
    font-size: 3rem;
    color: var(--border);
    line-height: 1;
  }

  .projects-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 0;
    border: 1px solid var(--border);
  }

  .project-card {
    padding: 2.5rem;
    border-right: 1px solid var(--border);
    border-bottom: 1px solid var(--border);
    transition: background 0.25s;
    cursor: pointer;
    position: relative;
    overflow: hidden;
  }

  .project-card:nth-child(3n) { border-right: none; }
  .project-card:nth-last-child(-n+3) { border-bottom: none; }

  .project-card::after {
    content: '';
    position: absolute;
    bottom: 0; left: 0;
    width: 0; height: 2px;
    background: var(--accent);
    transition: width 0.35s ease;
  }

  .project-card:hover { background: white; }
  .project-card:hover::after { width: 100%; }

  .project-num {
    font-size: 0.7rem;
    letter-spacing: 0.1em;
    color: var(--ink-soft);
    margin-bottom: 1.5rem;
    opacity: 0.5;
  }

  .project-type {
    display: inline-block;
    font-size: 0.7rem;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    background: var(--accent-light);
    color: var(--accent);
    padding: 0.3rem 0.75rem;
    margin-bottom: 1.25rem;
  }

  .project-title {
    font-family: var(--serif);
    font-size: 1.35rem;
    line-height: 1.25;
    margin-bottom: 1rem;
    color: var(--ink);
  }

  .project-desc {
    font-size: 0.875rem;
    color: var(--ink-soft);
    line-height: 1.7;
    margin-bottom: 2rem;
  }

  .project-tags {
    display: flex;
    flex-wrap: wrap;
    gap: 0.5rem;
    margin-bottom: 1.5rem;
  }

  .tag {
    font-size: 0.7rem;
    border: 1px solid var(--border);
    padding: 0.25rem 0.6rem;
    color: var(--ink-soft);
    letter-spacing: 0.05em;
  }

  .project-link {
    font-size: 0.78rem;
    letter-spacing: 0.08em;
    text-transform: uppercase;
    color: var(--ink);
    text-decoration: none;
    display: flex;
    align-items: center;
    gap: 0.5rem;
    transition: gap 0.2s;
  }

  .project-link:hover { gap: 0.9rem; }

  /* ── CTA SECTION ── */
  #contact {
    display: grid;
    grid-template-columns: 1fr 1fr;
    border-top: 1px solid var(--border);
    min-height: 40vh;
  }

  .contact-left {
    padding: 6rem 4rem;
    border-right: 1px solid var(--border);
    display: flex;
    flex-direction: column;
    justify-content: center;
  }

  .contact-title {
    font-family: var(--serif);
    font-size: clamp(2rem, 3vw, 2.8rem);
    line-height: 1.15;
    margin-bottom: 1.5rem;
  }

  .contact-sub {
    font-size: 0.95rem;
    color: var(--ink-soft);
    max-width: 40ch;
    margin-bottom: 2.5rem;
  }

  .contact-email {
    font-family: var(--serif);
    font-style: italic;
    font-size: 1.2rem;
    color: var(--accent);
    text-decoration: none;
    transition: opacity 0.2s;
  }

  .contact-email:hover { opacity: 0.7; }

  .contact-right {
    padding: 6rem 4rem;
    display: flex;
    flex-direction: column;
    justify-content: center;
    gap: 1.5rem;
  }

  .contact-detail {
    display: flex;
    align-items: center;
    gap: 1.25rem;
    padding-bottom: 1.5rem;
    border-bottom: 1px solid var(--border);
  }

  .contact-detail:last-child { border-bottom: none; }

  .detail-label {
    font-size: 0.75rem;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    color: var(--ink-soft);
    width: 7rem;
    flex-shrink: 0;
  }

  .detail-value {
    font-size: 0.95rem;
    color: var(--ink);
  }

  /* ── FOOTER ── */
  footer {
    border-top: 1px solid var(--border);
    padding: 2rem 4rem;
    display: flex;
    justify-content: space-between;
    align-items: center;
    font-size: 0.78rem;
    color: var(--ink-soft);
    letter-spacing: 0.04em;
  }

  /* ── ANIMATIONS ── */
  .fade-in {
    opacity: 0;
    transform: translateY(24px);
    transition: opacity 0.7s ease, transform 0.7s ease;
  }

  .fade-in.visible {
    opacity: 1;
    transform: none;
  }

  /* ── RESPONSIVE ── */
  @media (max-width: 900px) {
    nav { padding: 1.25rem 1.5rem; }
    .nav-links { gap: 1.5rem; }

    #hero { grid-template-columns: 1fr; }
    .hero-left {
      padding: 7rem 1.5rem 3rem;
      border-right: none;
      border-bottom: 1px solid var(--border);
    }
    .hero-right { padding: 3rem 1.5rem; }

    #projets { padding: 5rem 1.5rem; }
    .projects-grid { grid-template-columns: 1fr; }
    .project-card { border-right: none !important; border-bottom: 1px solid var(--border) !important; }
    .project-card:last-child { border-bottom: none !important; }

    #contact { grid-template-columns: 1fr; }
    .contact-left { padding: 4rem 1.5rem; border-right: none; border-bottom: 1px solid var(--border); }
    .contact-right { padding: 3rem 1.5rem; }

    footer { padding: 1.5rem; flex-direction: column; gap: 0.5rem; text-align: center; }

    .section-header { flex-direction: column; align-items: flex-start; gap: 1rem; }
  }
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <a href="#hero" class="nav-logo">Pierre Laloy</a>
  <ul class="nav-links">
    <li><a href="#projets">Projets</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
</nav>

<!-- HERO -->
<section id="hero">
  <div class="hero-left">
    <span class="hero-tag">Développeur web freelance</span>
    <h1 class="hero-title">
      Des sites web<br>
      <em>simples</em> et<br>
      qui durent.
    </h1>
    <p class="hero-desc">
      Je conçois et développe des sites de A à Z, avec une approche pragmatique. 
      J'accompagne aussi les projets existants pour les rendre plus clairs, plus fiables, plus faciles à utiliser.
    </p>
    <a href="#contact" class="hero-cta">
      Parlons de votre projet
      <span class="hero-cta-arrow">→</span>
    </a>
  </div>

  <div class="hero-right">
    <div class="hero-stats">
      <div class="stat">
        <div class="stat-number">A → Z</div>
        <div class="stat-label">Conception & développement</div>
      </div>
      <div class="stat">
        <div class="stat-number">100%</div>
        <div class="stat-label">Sur mesure</div>
      </div>
      <div class="stat">
        <div class="stat-number">Écoute</div>
        <div class="stat-label">Proximité & disponibilité</div>
      </div>
      <div class="stat">
        <div class="stat-number">Freelance</div>
        <div class="stat-label">Basé en France</div>
      </div>
    </div>

    <div class="hero-services">
      <div class="service-item"><span class="service-dot"></span> Création de sites vitrines & e-commerce</div>
      <div class="service-item"><span class="service-dot"></span> Refonte & modernisation de sites existants</div>
      <div class="service-item"><span class="service-dot"></span> Hébergement, mise en ligne & suivi</div>
      <div class="service-item"><span class="service-dot"></span> Maintenance & évolutions</div>
    </div>
  </div>
</section>

<!-- PROJETS -->
<section id="projets">
  <div class="section-header fade-in">
    <div>
      <div class="section-label">Réalisations</div>
      <h2 class="section-title">Quelques projets<br>récents</h2>
    </div>
    <div class="section-count">03</div>
  </div>

  <div class="projects-grid">

    <div class="project-card fade-in">
      <div class="project-num">001</div>
      <span class="project-type">Site vitrine</span>
      <h3 class="project-title">psycho-judiciaire.com</h3>
      <p class="project-desc">Création complète pour une psychologue-formatrice indépendante — structure, contenu, mise en ligne.</p>
      <div class="project-tags">
        <span class="tag">HTML</span>
        <span class="tag">CSS</span>
        <span class="tag">JavaScript</span>
      </div>
      <a href="#" class="project-link">Voir le projet →</a>
    </div>

    <div class="project-card fade-in">
      <div class="project-num">002</div>
      <span class="project-type">Refonte</span>
      <h3 class="project-title">Nom du projet ou client</h3>
      <p class="project-desc">Courte description du projet : ce qui a été fait, le contexte, les enjeux. Gardez-le simple et concret.</p>
      <div class="project-tags">
        <span class="tag">WordPress</span>
        <span class="tag">PHP</span>
        <span class="tag">CSS</span>
      </div>
      <a href="#" class="project-link">Voir le projet →</a>
    </div>

  </div>
</section>

<!-- CONTACT -->
<section id="contact">
  <div class="contact-left fade-in">
    <h2 class="contact-title">Un projet<br>en tête ?</h2>
    <p class="contact-sub">
      Proposez-moi un échange de 15 minutes, sans engagement, pour voir comment avancer ensemble simplement.
    </p>
    <a href="mailto:pierre.laloy@protonmail.com" class="contact-email">pierre.laloy@protonmail.com</a>
  </div>

  <div class="contact-right fade-in">
    <div class="contact-detail">
      <span class="detail-label">Localisation</span>
      <span class="detail-value">France — disponible à distance</span>
    </div>
    <div class="contact-detail">
      <span class="detail-label">Téléphone</span>
      <span class="detail-value">06 62 35 51 69</span>
    </div>
    <div class="contact-detail">
      <span class="detail-label">Disponibilité</span>
      <span class="detail-value">Ouvert à de nouveaux projets</span>
    </div>
    <div class="contact-detail">
      <span class="detail-label">Réponse</span>
      <span class="detail-value">Sous 24h en général</span>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <span>© 2026 — Prénom Nom</span>
  <span>Développeur web freelance</span>
</footer>

<script>
  const observer = new IntersectionObserver((entries) => {
    entries.forEach((entry, i) => {
      if (entry.isIntersecting) {
        setTimeout(() => entry.target.classList.add('visible'), i * 80);
      }
    });
  }, { threshold: 0.1 });

  document.querySelectorAll('.fade-in').forEach(el => observer.observe(el));
</script>
</body>
</html>
