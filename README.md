<!doctype html>
<html lang="en">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width,initial-scale=1">
<title>Case study — Knix · Rise DTC</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;500;600;700;800&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">
<style>
:root {
  --surface: #ffffff;
  --surface-alt: #f8f9fa;
  --surface-dark: #1a1a1a;
  --text: #1a1a1a;
  --text-muted: #555555;
  --text-on-dark: #ffffff;
  --text-on-dark-muted: #b8b8b8;
  --brand: #ffd700;
  --brand-hover: #e6c200;
  --on-brand: #1a1a1a;
  --border: #eeeeee;
  --border-strong: #333333;
  --success: #1f7a3a;
  --success-bg: #e6f4ea;
  --warning: #b45309;
  --warning-bg: #fef3c7;
  --error: #ba1a1a;
  --error-bg: #ffdad6;
  --font-sans: 'Montserrat', system-ui, -apple-system, sans-serif;
  --font-mono: 'JetBrains Mono', ui-monospace, SFMono-Regular, Menlo, monospace;
  --max-w: 1180px;
  --radius-sm: 6px;
  --radius: 12px;
  --radius-pill: 999px;
}
* { box-sizing: border-box; }
html, body { margin: 0; padding: 0; }
body {
  font-family: var(--font-sans); font-size: 16px; line-height: 1.6;
  color: var(--text); background: var(--surface);
  -webkit-font-smoothing: antialiased;
}

/* Layout */
.container { max-width: var(--max-w); margin: 0 auto; padding: 0 32px; }
.section { padding: 96px 0; border-top: 1px solid var(--border); }
.section.hero { padding: 120px 0 96px; border-top: 0; }
.section.alt { background: var(--surface-alt); }
.section.dark { background: var(--surface-dark); color: var(--text-on-dark); border-top: 0; }

/* Type */
.eyebrow { font-size: 12px; font-weight: 700; letter-spacing: 0.1em; text-transform: uppercase; color: var(--text-muted); margin: 0 0 16px; }
.section.dark .eyebrow { color: var(--brand); }
h1 { font-size: 56px; font-weight: 700; line-height: 1.1; letter-spacing: -0.02em; margin: 0 0 24px; }
h2 { font-size: 32px; font-weight: 700; line-height: 1.2; letter-spacing: -0.01em; margin: 0 0 24px; }
h3 { font-size: 22px; font-weight: 600; line-height: 1.35; margin: 0 0 12px; }
p { margin: 0 0 16px; }
.lead { font-size: 19px; line-height: 1.55; color: var(--text-muted); max-width: 760px; }

/* Header */
.header { padding: 24px 0; border-bottom: 1px solid var(--border); }
.header-inner { display: flex; justify-content: space-between; align-items: center; }
.brand-mark { font-size: 18px; font-weight: 800; letter-spacing: -0.02em; }
.brand-mark .dot { color: var(--brand); }

/* Buttons */
.btn { display: inline-flex; align-items: center; justify-content: center; font-family: inherit; font-size: 15px; font-weight: 600; padding: 14px 28px; border-radius: var(--radius-pill); border: 0; cursor: pointer; text-decoration: none; transition: background 0.15s, color 0.15s, border-color 0.15s; letter-spacing: 0.01em; }
.btn-primary { background: var(--brand); color: var(--on-brand); }
.btn-primary:hover { background: var(--brand-hover); }
.btn-dark { background: var(--surface-dark); color: var(--text-on-dark); }
.btn-dark:hover { background: #000; }
.btn-ghost-dark { background: transparent; color: var(--text-on-dark); border: 1.5px solid var(--text-on-dark); }
.btn-ghost-dark:hover { background: var(--text-on-dark); color: var(--text); }

/* Tags */
.tag { display: inline-block; padding: 6px 12px; border-radius: var(--radius-pill); background: var(--surface-alt); color: var(--text); font-size: 11px; font-weight: 700; letter-spacing: 0.08em; text-transform: uppercase; }
.tag.brand { background: var(--brand); color: var(--on-brand); }
.tag.dark { background: var(--surface-dark); color: var(--text-on-dark); }

/* Stat */
.stat .num { font-size: 84px; font-weight: 800; line-height: 1.0; letter-spacing: -0.03em; margin: 0 0 12px; }
.stat .num.brand { color: var(--brand); }
.stat .label { font-size: 12px; font-weight: 700; letter-spacing: 0.1em; text-transform: uppercase; color: var(--text-muted); margin: 0; }
.section.dark .stat .label { color: var(--text-on-dark-muted); }
.stat-strip { display: grid; grid-template-columns: repeat(4, 1fr); gap: 48px; }

/* Card */
.card { background: var(--surface); border: 1px solid var(--border); border-radius: var(--radius); padding: 40px; }

/* Numbered method cards */
.method { display: grid; grid-template-columns: repeat(2, 1fr); gap: 24px; }
.method .step { background: var(--surface); border: 1px solid var(--border); border-radius: var(--radius); padding: 36px; display: grid; grid-template-columns: 64px 1fr; gap: 24px; align-items: start; }
.method .step .num { font-size: 40px; font-weight: 800; line-height: 1.0; letter-spacing: -0.03em; color: var(--text-muted); margin: 0; font-variant-numeric: tabular-nums; }
.method .step.featured .num { color: var(--brand); }
.method .step h3 { margin: 0 0 8px; }
.method .step p { margin: 0; font-size: 14px; color: var(--text-muted); }

/* Callout */
.callout { border-left: 4px solid var(--warning); background: var(--warning-bg); padding: 24px 28px; border-radius: 0 var(--radius-sm) var(--radius-sm) 0; }
.callout h3 { margin: 0 0 8px; font-size: 16px; }
.callout p { margin: 0; }

/* Table */
table { width: 100%; border-collapse: collapse; font-size: 15px; }
thead th { background: var(--surface-alt); text-align: left; padding: 16px; font-size: 12px; font-weight: 700; letter-spacing: 0.08em; text-transform: uppercase; color: var(--text-muted); border-bottom: 1px solid var(--border); }
tbody td { padding: 18px 16px; border-bottom: 1px solid var(--border); font-variant-numeric: tabular-nums; }
tbody tr:last-child td { border-bottom: 0; }
.delta-up { color: var(--success); font-weight: 600; }
.delta-down { color: var(--error); font-weight: 600; }

/* Pull quote */
.quote { font-size: 32px; font-weight: 600; line-height: 1.3; letter-spacing: -0.01em; max-width: 880px; margin: 0 0 32px; }
.quote-meta { font-size: 14px; font-weight: 600; color: var(--text-muted); }
.quote-meta .who { color: var(--text); }

/* Findings */
.findings { display: grid; grid-template-columns: repeat(3, 1fr); gap: 24px; }
.finding { background: var(--surface); border: 1px solid var(--border); border-radius: var(--radius); padding: 32px; }
.finding .num { font-size: 32px; font-weight: 800; line-height: 1.0; letter-spacing: -0.02em; color: var(--brand); margin: 0 0 16px; }
.finding h4 { margin: 0 0 8px; font-size: 18px; font-weight: 600; line-height: 1.4; }
.finding p { margin: 0; font-size: 14px; color: var(--text-muted); }

/* Body block */
.body-block { max-width: 760px; }
.body-block p { font-size: 16px; line-height: 1.7; color: var(--text); }

@media (max-width: 720px) {
  .container { padding: 0 20px; }
  .section { padding: 64px 0; }
  .section.hero { padding: 80px 0 56px; }
  h1 { font-size: 36px; }
  h2 { font-size: 26px; }
  .stat .num { font-size: 56px; }
  .stat-strip, .method, .findings { grid-template-columns: 1fr; gap: 20px; }
  .method .step { grid-template-columns: 48px 1fr; padding: 24px; }
  .method .step .num { font-size: 28px; }
  .quote { font-size: 22px; }
}
</style>
</head>
<body>

<header class="header">
  <div class="container header-inner">
    <span class="brand-mark">RISE<span class="dot">.</span>DTC</span>
    <span class="tag">Case study</span>
  </div>
</header>

<!-- HERO -->
<section class="section hero">
  <div class="container">
    <p class="eyebrow">Case study · DTC apparel · 2024–2026</p>
    <h1>How Knix scaled to $725M<br>without losing margin.</h1>
    <p class="lead">Knix came to us with a creative pipeline that was burning $180k/month and a blended ROAS stuck at 1.8. Eighteen months later they're at $725M attributed revenue, ROAS 4.2, and CAC down 30%. Here's exactly what we did.</p>
    <div style="display:flex; gap:12px; margin-top:32px;">
      <a class="btn btn-primary" href="#approach">See the approach</a>
      <a class="btn btn-dark" href="#results">Skip to results</a>
    </div>
  </div>
</section>

<!-- HEADLINE STATS -->
<section class="section dark">
  <div class="container">
    <p class="eyebrow">Outcomes · 18 months</p>
    <div class="stat-strip">
      <div class="stat"><p class="num brand">$725M</p><p class="label">Attributed revenue</p></div>
      <div class="stat"><p class="num">4.2x</p><p class="label">Blended ROAS</p></div>
      <div class="stat"><p class="num brand">−30%</p><p class="label">Blended CAC</p></div>
      <div class="stat"><p class="num">3.4x</p><p class="label">Creative throughput</p></div>
    </div>
  </div>
</section>

<!-- THE PROBLEM -->
<section class="section">
  <div class="container">
    <p class="eyebrow">01 · The problem</p>
    <h2>The pipeline was the bottleneck.</h2>
    <div class="body-block">
      <p>Knix had a great product, a loyal audience, and a paid-social budget that wasn't compounding. The team was launching ~40 creatives a month and running them flat — same audiences, same hooks, same fatigue curves. Every month looked like the last, except more expensive.</p>
      <p>The creative pipeline was the choke point. Concepts took three weeks to ship. Half landed on the wrong audience. Nobody could tell you which hook drove ROAS because attribution was averaged across the whole account. The team was working hard and learning slowly.</p>
      <p>The CFO had a quarterly target. The CMO had a creative team that was already at capacity. The numbers had to move without the cost line moving with them.</p>
    </div>
    <div class="callout" style="margin-top:32px; max-width:760px;">
      <h3>The diagnosis</h3>
      <p>This is a measurement problem dressed as a creative problem. Until you can attribute ROAS to a specific hook, you can't tell good creative from lucky creative. Until you can tell the difference, you can't compound.</p>
    </div>
  </div>
</section>

<!-- THE APPROACH -->
<section id="approach" class="section alt">
  <div class="container">
    <p class="eyebrow">02 · The approach</p>
    <h2>The Rise method, applied to Knix.</h2>
    <p class="lead" style="margin-bottom:48px;">Four phases. No phase moves until the previous one is measurable. Boring on purpose.</p>

    <div class="method">
      <div class="step">
        <p class="num">01</p>
        <div>
          <h3>Audit, then nothing else.</h3>
          <p>Two weeks tearing apart the existing account structure. Tagged every creative by hook, format, and audience. Found three hooks driving 60% of revenue — and 80% of spend going to the other forty.</p>
        </div>
      </div>
      <div class="step">
        <p class="num">02</p>
        <div>
          <h3>Rebuild the creative pipeline.</h3>
          <p>Cut concept-to-launch from 21 days to 5. Standardized brief format. One creative team, one ops team, one weekly review. Throughput went from 40 a month to 135.</p>
        </div>
      </div>
      <div class="step">
        <p class="num">03</p>
        <div>
          <h3>Test by hook, not by ad.</h3>
          <p>Every concept ships in three formats and two audiences from day one. Kill or scale at 72 hours. No creative over a month old in the top-spend bucket.</p>
        </div>
      </div>
      <div class="step featured">
        <p class="num">04</p>
        <div>
          <h3>Scale only what compounds.</h3>
          <p>Reinvest into hooks where ROAS is rising on increasing spend. Cap budget on hooks where ROAS is flat. Most accounts skip this step. It's the only one that matters.</p>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- TRAJECTORY CHART -->
<section class="section">
  <div class="container">
    <p class="eyebrow">03 · Trajectory</p>
    <h2>Monthly attributed revenue, $K.</h2>
    <p class="lead" style="margin-bottom:48px;">The inflection lands in month four — the moment the new creative pipeline hit full throughput and the test-by-hook discipline started compounding. After that the curve doesn't bend, it keeps climbing.</p>
    <div style="background:var(--surface-dark); color:var(--text-on-dark); padding:48px; border-radius:var(--radius);">
    <svg viewBox="0 0 880 320" width="100%" font-family="Montserrat, sans-serif">
      <!-- Gridlines & y-axis labels -->
      <g font-size="11" fill="#b8b8b8">
        <text x="0" y="24">$80M</text><line x1="56" y1="20" x2="880" y2="20" stroke="#333"/>
        <text x="0" y="84">$60M</text><line x1="56" y1="80" x2="880" y2="80" stroke="#333"/>
        <text x="0" y="144">$40M</text><line x1="56" y1="140" x2="880" y2="140" stroke="#333"/>
        <text x="0" y="204">$20M</text><line x1="56" y1="200" x2="880" y2="200" stroke="#333"/>
        <text x="0" y="264">$0</text><line x1="56" y1="260" x2="880" y2="260" stroke="#333"/>
      </g>
      <!-- Bars: 12 months, growing -->
      <g>
        <rect x="76"  y="222" width="44" height="38"  fill="#ffd700"/>
        <text x="98"  y="214" text-anchor="middle" fill="#fff" font-weight="700" font-size="11">12.6</text>
        <rect x="140" y="216" width="44" height="44"  fill="#ffd700"/>
        <text x="162" y="208" text-anchor="middle" fill="#fff" font-weight="700" font-size="11">14.7</text>
        <rect x="204" y="208" width="44" height="52"  fill="#ffd700"/>
        <text x="226" y="200" text-anchor="middle" fill="#fff" font-weight="700" font-size="11">17.2</text>
        <rect x="268" y="190" width="44" height="70"  fill="#ffd700"/>
        <text x="290" y="182" text-anchor="middle" fill="#fff" font-weight="700" font-size="11">23.4</text>
        <rect x="332" y="170" width="44" height="90"  fill="#ffd700"/>
        <text x="354" y="162" text-anchor="middle" fill="#fff" font-weight="700" font-size="11">30.1</text>
        <rect x="396" y="148" width="44" height="112" fill="#ffd700"/>
        <text x="418" y="140" text-anchor="middle" fill="#fff" font-weight="700" font-size="11">37.4</text>
        <rect x="460" y="124" width="44" height="136" fill="#ffd700"/>
        <text x="482" y="116" text-anchor="middle" fill="#fff" font-weight="700" font-size="11">45.2</text>
        <rect x="524" y="108" width="44" height="152" fill="#ffd700"/>
        <text x="546" y="100" text-anchor="middle" fill="#fff" font-weight="700" font-size="11">50.6</text>
        <rect x="588" y="88"  width="44" height="172" fill="#ffd700"/>
        <text x="610" y="80"  text-anchor="middle" fill="#fff" font-weight="700" font-size="11">57.4</text>
        <rect x="652" y="68"  width="44" height="192" fill="#ffd700"/>
        <text x="674" y="60"  text-anchor="middle" fill="#fff" font-weight="700" font-size="11">64.0</text>
        <rect x="716" y="52"  width="44" height="208" fill="#ffd700"/>
        <text x="738" y="44"  text-anchor="middle" fill="#fff" font-weight="700" font-size="11">69.3</text>
        <rect x="780" y="36"  width="44" height="224" fill="#ffd700"/>
        <text x="802" y="28"  text-anchor="middle" fill="#fff" font-weight="700" font-size="11">74.5</text>
      </g>
      <!-- Inflection annotation -->
      <g>
        <line x1="290" y1="270" x2="290" y2="295" stroke="#ffd700" stroke-width="1.5" stroke-dasharray="3,3"/>
        <text x="290" y="308" text-anchor="middle" fill="#ffd700" font-size="11" font-weight="700">Pipeline live</text>
      </g>
      <!-- X labels -->
      <g font-size="11" fill="#b8b8b8" text-anchor="middle">
        <text x="98"  y="280">M1</text>
        <text x="162" y="280">M2</text>
        <text x="226" y="280">M3</text>
        <text x="290" y="280">M4</text>
        <text x="354" y="280">M5</text>
        <text x="418" y="280">M6</text>
        <text x="482" y="280">M7</text>
        <text x="546" y="280">M8</text>
        <text x="610" y="280">M9</text>
        <text x="674" y="280">M10</text>
        <text x="738" y="280">M11</text>
        <text x="802" y="280">M12</text>
      </g>
    </svg>
    </div>
  </div>
</section>

<!-- CHANNEL RESULTS -->
<section id="results" class="section">
  <div class="container">
    <p class="eyebrow">04 · Channel results</p>
    <h2>Where the lift came from.</h2>
    <p class="lead" style="margin-bottom:32px;">Spend mix shifted toward Meta and TikTok as the test-by-hook discipline made them the highest-leverage surfaces. Google held flat by design — it's the floor, not the ceiling.</p>
    <div class="card" style="padding:0; overflow:hidden;">
      <table>
        <thead>
          <tr><th>Channel</th><th>Spend</th><th>Revenue</th><th>ROAS</th><th>Δ ROAS</th></tr>
        </thead>
        <tbody>
          <tr><td>Meta</td><td>$92M</td><td>$418M</td><td>4.5x</td><td><span class="delta-up">+1.4x</span></td></tr>
          <tr><td>TikTok</td><td>$24M</td><td>$108M</td><td>4.5x</td><td><span class="delta-up">+2.1x</span></td></tr>
          <tr><td>Google</td><td>$32M</td><td>$104M</td><td>3.3x</td><td><span class="delta-up">+0.4x</span></td></tr>
          <tr><td>Email / SMS</td><td>$3M</td><td>$54M</td><td>18.0x</td><td><span class="delta-up">+3.2x</span></td></tr>
          <tr><td>Affiliate</td><td>$6M</td><td>$41M</td><td>6.8x</td><td><span class="delta-up">+0.9x</span></td></tr>
        </tbody>
      </table>
    </div>
  </div>
</section>

<!-- PULL QUOTE -->
<section class="section alt">
  <div class="container">
    <p class="quote">Rise rebuilt our entire creative pipeline in six weeks and tripled our ROAS without raising the budget. They tell you what's working and what's wasting money — that's it.</p>
    <p class="quote-meta"><span class="who">Joanna Griffiths</span> · Founder, Knix</p>
  </div>
</section>

<!-- LESSONS -->
<section class="section">
  <div class="container">
    <p class="eyebrow">05 · Three things to take away</p>
    <h2>What this case study is actually about.</h2>
    <p class="lead" style="margin-bottom:48px;">If you read nothing else, read these three.</p>
    <div class="findings">
      <div class="finding">
        <p class="num">01</p>
        <h4>ROAS is a measurement problem.</h4>
        <p>Until every hook is attributed individually, your account average is hiding both the winners and the losers. Fix the measurement before you touch the spend.</p>
      </div>
      <div class="finding">
        <p class="num">02</p>
        <h4>Throughput is the moat.</h4>
        <p>Best-in-class brands ship 5–10x more creative than the median. Not because they have bigger teams. Because they removed the bottleneck between concept and launch.</p>
      </div>
      <div class="finding">
        <p class="num">03</p>
        <h4>Compound or kill.</h4>
        <p>Most accounts keep creatives running because "they're still profitable." That's the trap. Reinvest only into hooks where ROAS rises with spend. Everything else is a tax on next month.</p>
      </div>
    </div>
  </div>
</section>

<!-- CLOSING CTA -->
<section class="section dark">
  <div class="container">
    <p class="eyebrow">Closing</p>
    <h1 style="color:var(--text-on-dark); max-width:760px;">Want this trajectory<br>for your brand?</h1>
    <p style="color:var(--text-on-dark-muted); max-width:600px; margin-bottom:32px; font-size:18px;">We do this for around forty DTC brands at any given time. If you're spending $250k+/month on paid social and the line isn't compounding, we should talk.</p>
    <div style="display:flex; gap:12px; flex-wrap:wrap;">
      <a class="btn btn-primary" href="#">Schedule a call</a>
      <a class="btn btn-ghost-dark" href="#">Read the method</a>
    </div>
  </div>
</section>

</body>
</html>
