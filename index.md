<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Massimo Armano — Statistics & Data</title>
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=DM+Serif+Display:ital@0;1&family=DM+Mono:wght@400;500&family=DM+Sans:ital,opsz,wght@0,9..40,300;0,9..40,400;0,9..40,500;1,9..40,300&display=swap" rel="stylesheet" />
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    :root {
      --bg:        #0d1117;
      --surface:   #161b22;
      --border:    #30363d;
      --text:      #e6edf3;
      --text-muted:#8b949e;
      --teal:      #2dd4bf;
      --teal-dim:  #1a9e8f;
      --teal-soft: rgba(45,212,191,0.10);
      --teal-bdr:  rgba(45,212,191,0.22);
    }

    html { scroll-behavior: smooth; scroll-snap-type: y mandatory; }

    body {
      font-family: 'DM Sans', sans-serif;
      background: var(--bg);
      color: var(--text);
      overflow-x: hidden;
    }

    /* NAV */
    nav {
      position: fixed;
      top: 0; left: 0; right: 0;
      z-index: 100;
      display: flex;
      align-items: center;
      justify-content: space-between;
      padding: 1rem 2.5rem;
      background: rgba(13,17,23,0.88);
      backdrop-filter: blur(16px);
      border-bottom: 1px solid var(--border);
    }

    .nav-logo {
      font-family: 'DM Mono', monospace;
      font-size: 0.78rem;
      color: var(--teal);
      letter-spacing: 0.08em;
    }

    .nav-links { display: flex; gap: 2rem; align-items: center; }

    .nav-links a {
      font-size: 0.83rem;
      color: var(--text-muted);
      text-decoration: none;
      transition: color 0.18s;
    }
    .nav-links a:hover { color: var(--text); }

    .nav-cta {
      padding: 0.38rem 1rem;
      border: 1px solid var(--teal-bdr);
      border-radius: 4px;
      color: var(--teal) !important;
      font-weight: 500;
      transition: background 0.18s !important;
    }
    .nav-cta:hover { background: var(--teal-soft) !important; }

    /* SECTIONS */
    section {
      min-height: 100vh;
      scroll-snap-align: start;
      padding: 8rem 2.5rem 5rem;
      max-width: 1100px;
      margin: 0 auto;
    }

    /* PAGE 1 — ABOUT */
    #about {
      display: grid;
      grid-template-columns: 300px 1fr;
      gap: 5rem;
      align-items: start;
    }

    .about-left { position: sticky; top: 7rem; }

    .about-photo {
      width: 100%;
      aspect-ratio: 4/5;
      object-fit: cover;
      border-radius: 6px;
      display: block;
      filter: grayscale(18%) contrast(1.04);
      border: 1px solid var(--border);
      box-shadow: 0 0 0 1px var(--teal-bdr), 0 24px 64px rgba(0,0,0,0.55);
    }

    .photo-caption {
      margin-top: 0.75rem;
      font-family: 'DM Mono', monospace;
      font-size: 0.67rem;
      color: var(--text-muted);
      letter-spacing: 0.05em;
    }

    .eyebrow {
      font-family: 'DM Mono', monospace;
      font-size: 0.7rem;
      letter-spacing: 0.12em;
      color: var(--teal);
      text-transform: uppercase;
      margin-bottom: 0.9rem;
    }

    h1 {
      font-family: 'DM Serif Display', serif;
      font-size: clamp(2.8rem, 5vw, 4rem);
      line-height: 1.06;
      font-weight: 400;
      color: var(--text);
      letter-spacing: -0.02em;
      margin-bottom: 0.5rem;
    }
    h1 em { font-style: italic; color: var(--teal); }

    .tagline {
      font-size: 0.95rem;
      color: var(--text-muted);
      font-weight: 300;
      line-height: 1.65;
      margin-bottom: 2rem;
    }

    .divider {
      width: 40px; height: 1px;
      background: var(--border);
      margin: 1.75rem 0;
    }

    .bio p {
      font-size: 0.95rem;
      line-height: 1.85;
      color: #b0bec9;
      font-weight: 300;
      margin-bottom: 1.1rem;
    }
    .bio p strong { font-weight: 500; color: var(--text); }

    .skills-strip {
      display: flex;
      flex-wrap: wrap;
      gap: 0.4rem;
      margin: 1.75rem 0;
    }

    .skill-tag {
      font-family: 'DM Mono', monospace;
      font-size: 0.67rem;
      padding: 0.25rem 0.65rem;
      border: 1px solid var(--teal-bdr);
      border-radius: 3px;
      color: var(--teal);
      background: var(--teal-soft);
      letter-spacing: 0.04em;
    }

    .contacts-label {
      font-family: 'DM Mono', monospace;
      font-size: 0.67rem;
      letter-spacing: 0.1em;
      color: var(--text-muted);
      text-transform: uppercase;
      margin-bottom: 0.85rem;
    }

    .contact-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 0.55rem;
      margin-bottom: 2rem;
    }

    .contact-link {
      display: flex;
      align-items: center;
      gap: 0.6rem;
      padding: 0.65rem 0.85rem;
      border: 1px solid var(--border);
      border-radius: 5px;
      text-decoration: none;
      color: var(--text);
      font-size: 0.8rem;
      background: var(--surface);
      transition: border-color 0.18s, background 0.18s, color 0.18s;
    }
    .contact-link:hover {
      border-color: var(--teal-bdr);
      background: var(--teal-soft);
      color: var(--teal);
    }
    .contact-link .icon { opacity: 0.55; font-size: 0.88rem; flex-shrink: 0; }
    .contact-link .link-label { font-weight: 500; font-size: 0.82rem; }
    .contact-link .link-sub { font-size: 0.69rem; color: var(--text-muted); }

    .scroll-cta {
      display: inline-flex;
      align-items: center;
      gap: 0.7rem;
      padding: 0.82rem 1.9rem;
      background: var(--teal);
      color: #0d1117;
      font-size: 0.87rem;
      font-weight: 500;
      text-decoration: none;
      border-radius: 5px;
      letter-spacing: 0.02em;
      transition: background 0.18s, transform 0.15s;
    }
    .scroll-cta:hover { background: var(--teal-dim); transform: translateY(-2px); }
    .scroll-cta .arrow { transition: transform 0.2s; }
    .scroll-cta:hover .arrow { transform: translateY(3px); }

    /* PAGE 2 — PROJECTS */
    #projects { padding-top: 8rem; }

    .section-header {
      display: flex;
      align-items: baseline;
      justify-content: space-between;
      margin-bottom: 3rem;
      padding-bottom: 1.25rem;
      border-bottom: 1px solid var(--border);
    }

    .section-header h2 {
      font-family: 'DM Serif Display', serif;
      font-size: clamp(1.9rem, 4vw, 2.8rem);
      font-weight: 400;
      letter-spacing: -0.02em;
      color: var(--text);
    }

    .section-header .count {
      font-family: 'DM Mono', monospace;
      font-size: 0.72rem;
      color: var(--text-muted);
      letter-spacing: 0.05em;
    }

    .projects-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 1.25rem;
    }

    .project-card {
      background: var(--surface);
      border: 1px solid var(--border);
      border-radius: 8px;
      padding: 1.6rem;
      display: flex;
      flex-direction: column;
      gap: 0.85rem;
      position: relative;
      overflow: hidden;
      transition: border-color 0.2s, transform 0.2s, box-shadow 0.2s;
    }

    .project-card::before {
      content: '';
      position: absolute;
      top: 0; left: 0;
      width: 3px; height: 0;
      background: var(--teal);
      transition: height 0.25s ease;
    }
    .project-card:hover {
      border-color: var(--teal-bdr);
      transform: translateY(-3px);
      box-shadow: 0 12px 40px rgba(0,0,0,0.35);
    }
    .project-card:hover::before { height: 100%; }

    .project-type {
      font-family: 'DM Mono', monospace;
      font-size: 0.63rem;
      letter-spacing: 0.1em;
      text-transform: uppercase;
      color: var(--teal);
    }

    .project-card h3 {
      font-family: 'DM Serif Display', serif;
      font-size: 1.18rem;
      font-weight: 400;
      line-height: 1.28;
      color: var(--text);
    }

    .project-card .subtitle {
      font-size: 0.77rem;
      color: var(--text-muted);
      margin-top: -0.35rem;
    }

    .project-card p {
      font-size: 0.86rem;
      line-height: 1.75;
      color: var(--text-muted);
      font-weight: 300;
      flex: 1;
    }

    .project-tags {
      display: flex;
      flex-wrap: wrap;
      gap: 0.38rem;
    }

    .project-tag {
      font-family: 'DM Mono', monospace;
      font-size: 0.62rem;
      padding: 0.2rem 0.55rem;
      background: var(--teal-soft);
      border: 1px solid var(--teal-bdr);
      border-radius: 3px;
      color: var(--teal);
      letter-spacing: 0.04em;
    }

    .project-links {
      display: flex;
      gap: 0.7rem;
      flex-wrap: wrap;
      align-items: center;
      padding-top: 0.55rem;
      border-top: 1px solid var(--border);
    }

    .project-link {
      font-size: 0.77rem;
      font-weight: 500;
      color: var(--teal);
      text-decoration: none;
      display: flex;
      align-items: center;
      gap: 0.28rem;
      transition: color 0.15s;
    }
    .project-link:hover { color: var(--text); }

    /* featured */
    .project-card.featured {
      grid-column: 1 / -1;
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 2rem;
      align-items: start;
    }
    .featured-right { display: flex; flex-direction: column; gap: 0.85rem; }

    /* back to top */
    .back-top {
      display: inline-flex;
      align-items: center;
      gap: 0.45rem;
      margin-top: 3rem;
      font-family: 'DM Mono', monospace;
      font-size: 0.72rem;
      color: var(--text-muted);
      text-decoration: none;
      letter-spacing: 0.04em;
      transition: color 0.18s;
    }
    .back-top:hover { color: var(--teal); }

    /* footer */
    footer {
      text-align: center;
      padding: 2rem;
      font-family: 'DM Mono', monospace;
      font-size: 0.68rem;
      color: var(--text-muted);
      letter-spacing: 0.05em;
      border-top: 1px solid var(--border);
    }

    /* RESPONSIVE */
    @media (max-width: 768px) {
      nav { padding: 1rem 1.2rem; }
      section { padding: 5.5rem 1.2rem 3rem; }
      #about { grid-template-columns: 1fr; gap: 2rem; }
      .about-left { position: static; }
      .about-photo { max-width: 150px; }
      .contact-grid { grid-template-columns: 1fr; }
      .projects-grid { grid-template-columns: 1fr; }
      .project-card.featured { grid-column: auto; grid-template-columns: 1fr; }
      .section-header { flex-direction: column; gap: 0.4rem; }
    }

    /* ANIMATIONS */
    @keyframes fadeUp {
      from { opacity: 0; transform: translateY(16px); }
      to   { opacity: 1; transform: translateY(0); }
    }

    .about-left { animation: fadeUp 0.6s 0.08s ease both; }
    .about-right > * { animation: fadeUp 0.5s ease both; }
    .about-right > *:nth-child(1) { animation-delay: 0.06s; }
    .about-right > *:nth-child(2) { animation-delay: 0.13s; }
    .about-right > *:nth-child(3) { animation-delay: 0.20s; }
    .about-right > *:nth-child(4) { animation-delay: 0.27s; }
    .about-right > *:nth-child(5) { animation-delay: 0.34s; }
    .about-right > *:nth-child(6) { animation-delay: 0.41s; }
    .about-right > *:nth-child(7) { animation-delay: 0.48s; }
    .about-right > *:nth-child(8) { animation-delay: 0.55s; }
  </style>
</head>
<body>

<nav>
  <span class="nav-logo">MA_portfolio.v2</span>
  <div class="nav-links">
    <a href="#about">About</a>
    <a href="#projects">Projects</a>
    <a href="assets/docs/CV_Armano_Massimo_.pdf" target="_blank" class="nav-cta">CV ↗</a>
  </div>
</nav>


<!-- PAGE 1 — ABOUT -->
<section id="about">

  <div class="about-left">
    <img src="assets/docs/professional_pic.jpeg" alt="Massimo Armano" class="about-photo" />
    <p class="photo-caption">Massimo Armano — Turin, Italy</p>
  </div>

  <div class="about-right">

    <p class="eyebrow">MSc Statistics · Turin, Italy</p>

    <h1>Massimo<br><em>Armano</em></h1>

    <p class="tagline">
      Recent graduate with strong quantitative skills and practical experience working with real datasets
    </p>

    <div class="divider"></div>

    <div class="bio">
  <p>
    I hold a <strong>Master's degree in Statistical and Economic Methods for Decision-Making</strong>
    (LM-82) from the University of Turin, where I also received the <strong>Thesis Abroad Prize</strong>
    for a research project carried out at <strong>MaIAGE – INRAE</strong> in France. There, I implemented
    and applied a <strong>Bayesian factor model</strong> to <strong>wheat and biscuit NIRS data</strong>.
  </p>
  <p>
    Following my graduation, I continued to freelance working on this research through a collaboration between the
    <strong>University of Turin</strong> and <strong>MaIAGE – INRAE</strong>, with a temporary academic
    affiliation at the <strong>Department of Economics and Statistics “Cognetti De Martiis”</strong>.
    This led to a co-authored short paper on Bayesian factor models for NIRS data, submitted to SIS 2026.
    Motivated, adaptable, and driven by continuous learning, I'm open to opportunities in
    <strong>data science, data analysis, data engineering</strong>, and related fields where data and
    analytical thinking can generate real value.
  </p>
</div>

    <div class="skills-strip">
      <span class="skill-tag">Python</span>
      <span class="skill-tag">R</span>
      <span class="skill-tag">SQL</span>
      <span class="skill-tag">SAS · Stata</span>
      <span class="skill-tag">Bayesian inference</span>
      <span class="skill-tag">MCMC</span>
      <span class="skill-tag">Statistical learning</span>
      <span class="skill-tag">Power BI</span>
      <span class="skill-tag">Data visualisation</span>
      <span class="skill-tag">R Markdown</span>
    </div>

    <div class="divider"></div>

    <p class="contacts-label">Contact &amp; links</p>

    <div class="contact-grid">
      <a href="mailto:massimoarmano.ov@gmail.com" class="contact-link">
        <span class="icon">✉</span>
        <div>
          <div class="link-label">Email</div>
          <div class="link-sub">massimoarmano.ov@gmail.com</div>
        </div>
      </a>
      <a href="https://www.linkedin.com/in/massimo-armano-107174176/" target="_blank" class="contact-link">
        <span class="icon">in</span>
        <div>
          <div class="link-label">LinkedIn</div>
          <div class="link-sub">massimo-armano</div>
        </div>
      </a>
      <a href="https://github.com/Massimo-ov" target="_blank" class="contact-link">
        <span class="icon">⌥</span>
        <div>
          <div class="link-label">GitHub</div>
          <div class="link-sub">Massimo-ov</div>
        </div>
      </a>
      <a href="assets/docs/CV_Armano_Massimo_.pdf" target="_blank" class="contact-link">
        <span class="icon">↓</span>
        <div>
          <div class="link-label">Curriculum Vitae</div>
          <div class="link-sub">Download PDF</div>
        </div>
      </a>
    </div>

    <a href="#projects" class="scroll-cta">
      View my projects <span class="arrow">↓</span>
    </a>

  </div>
</section>


<!-- PAGE 2 — PROJECTS -->
<section id="projects">

  <div class="section-header">
    <h2>Projects</h2>
    <span class="count">03 selected works</span>
  </div>

  <div class="projects-grid">

    <div class="project-card">
      <p class="project-type">Master's Thesis</p>
      <h3>Sparse Bayesian Infinite Factor Model</h3>
      <p class="subtitle">Application to NIRS Spectroscopy Data, Supervisors: A. Lanteri, G. Kon Kam King</p>
      <p>
        Application of a sparse Bayesian infinite factor model on biscuit dough and wheat near-infrared spectroscopy (NIRS) data.
        Includes hierarchical modelling, MCMC implementation via Gibbs sampling, posterior shrinkage analysis,
        and an in-depth interpretability study of latent factor structure. Culminating project of the MSc in
        Statistics at UniTo.
      </p>
      <div class="project-tags">
        <span class="project-tag">Bayesian statistics</span>
        <span class="project-tag">Factor models</span>
        <span class="project-tag">MCMC / Gibbs sampling</span>
        <span class="project-tag">R</span>
        <span class="project-tag">NIRS data</span>
        <span class="project-tag">Dimensionality reduction</span>
      </div>
      <div class="project-links">
        <a href="assets/docs/thesis.pdf" target="_blank" class="project-link">↓ Thesis PDF</a>
        <a href="assets/docs/thesis_pres.pdf" target="_blank" class="project-link">↓ Presentation</a>
        <a href="https://github.com/Massimo-ov/Master-s-thesis-Sparse-Bayesian-infinite-factor-model-applications-on-NIRS-data-" target="_blank" class="project-link">⌥ GitHub</a>
      </div>
    </div>

    <div class="project-card">
      <p class="project-type">University project — Spatial Statistics</p>
      <h3>Variography &amp; Geostatistical Modelling</h3>
      <p class="subtitle">with Matteo Cucca, supervised by R. Ignaccolo (UniTo)</p>
      <p>
        Exploratory spatial analysis and variogram modelling project. Covers empirical variogram computation,
        theoretical model fitting (spherical, exponential, Matérn), and kriging interpolation. Fully implemented
        as a reproducible R Markdown workflow.
      </p>
      <div class="project-tags">
        <span class="project-tag">Spatial statistics</span>
        <span class="project-tag">Variogram</span>
        <span class="project-tag">Kriging</span>
        <span class="project-tag">R / R Markdown</span>
        <span class="project-tag">Geostatistics</span>
      </div>
      <div class="project-links">
        <a href="assets/docs/HW4_Cucca_Armano.pdf" target="_blank" class="project-link">↓ Report PDF</a>
        <a href="assets/docs/STATISTICA SPAZIALE pres2024.pptx" target="_blank" class="project-link">↓ Presentation</a>
        <a href="https://github.com/Massimo-ov/UniTo-spatial-statistic-project-" target="_blank" class="project-link">⌥ GitHub</a>
      </div>
    </div>

    <div class="project-card">
      <p class="project-type">Short paper — SIS Roma 2026 (submitted)</p>
      <h3>NIRS Covariates via Sparse Bayesian Infinite Factor Models</h3>
      <p class="subtitle">with A. Lanteri &amp; G. Kon Kam King · UniTo; MaIAGE – INRAE</p>
      <p>
        Short paper <em>"Including Near-Infrared Spectroscopy Covariates via Sparse Bayesian Infinite Factor Models"</em>,
        submitted to the 53rd Meeting of the Italian Statistical Society (SIS Roma 2026). The GitHub repository covers
        the full modelling pipeline: data preprocessing, MCMC sampling, and results reporting for biscuit-dough
        NIRS datasets.
      </p>
      <div class="project-tags">
        <span class="project-tag">Bayesian factor models</span>
        <span class="project-tag">NIRS</span>
        <span class="project-tag">R</span>
        <span class="project-tag">MCMC</span>
        <span class="project-tag">Reproducible research</span>
      </div>
      <div class="project-links">
        <a href="https://github.com/Massimo-ov/NIRS-via-SBIFM-SIS2026" target="_blank" class="project-link">⌥ GitHub</a>
      </div>
    </div>

  </div>

  <a href="#about" class="back-top">↑ back to top</a>

</section>

<footer>© 2025 Massimo Armano — Statistics &amp; Data Science · Turin, Italy</footer>

</body>
</html>
