[Index.HTML](https://github.com/user-attachments/files/28916895/Index.HTML)
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Black Banner Company — Crafting Guide v3.2.8</title>
<style>
  @import url('https://fonts.googleapis.com/css2?family=Cinzel:wght@400;600;700&family=Crimson+Pro:ital,wght@0,300;0,400;0,600;1,400&family=Fira+Mono:wght@400;500&display=swap');

  :root {
    --ink:        #1a1209;
    --parchment:  #f2ead8;
    --aged:       #e4d9be;
    --deep:       #2c1a0a;
    --blood:      #7a1f1f;
    --gold:       #b8860b;
    --rust:       #8b3a0f;
    --muted:      #5c4a2a;
    --faint:      #d6c9a8;
    --white:      #fdfaf3;
  }

  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  html { scroll-behavior: smooth; }

  body {
    background: var(--deep);
    font-family: 'Crimson Pro', Georgia, serif;
    font-size: 17px;
    line-height: 1.65;
    color: var(--ink);
  }

  /* ── SIDEBAR NAV ── */
  #sidebar {
    position: fixed;
    top: 0; left: 0;
    width: 230px;
    height: 100vh;
    background: var(--deep);
    border-right: 2px solid var(--gold);
    overflow-y: auto;
    z-index: 100;
    padding: 0 0 2rem;
  }

  #sidebar .logo {
    padding: 1.4rem 1.2rem 1rem;
    border-bottom: 1px solid #4a3010;
  }

  #sidebar .logo h2 {
    font-family: 'Cinzel', serif;
    font-size: 0.75rem;
    letter-spacing: 0.12em;
    color: var(--gold);
    text-transform: uppercase;
    line-height: 1.4;
  }

  #sidebar .logo p {
    font-size: 0.65rem;
    color: #9a7e50;
    margin-top: 0.2rem;
    font-style: italic;
  }

  #sidebar nav { padding: 0.8rem 0; }

  #sidebar nav a {
    display: block;
    padding: 0.35rem 1.2rem;
    color: #c4a97a;
    text-decoration: none;
    font-family: 'Cinzel', serif;
    font-size: 0.62rem;
    letter-spacing: 0.08em;
    text-transform: uppercase;
    transition: color 0.2s, background 0.2s;
    border-left: 3px solid transparent;
  }

  #sidebar nav a:hover {
    color: var(--gold);
    background: rgba(184,134,11,0.08);
    border-left-color: var(--gold);
  }

  #sidebar nav .section-head {
    padding: 0.9rem 1.2rem 0.25rem;
    color: #6a4f2a;
    font-family: 'Cinzel', serif;
    font-size: 0.55rem;
    letter-spacing: 0.15em;
    text-transform: uppercase;
  }

  /* ── MAIN ── */
  #main {
    margin-left: 230px;
    background: var(--parchment);
    min-height: 100vh;
  }

  /* ── HERO ── */
  #hero {
    background: linear-gradient(160deg, #1a0c04 0%, #2c1a0a 50%, #3d2210 100%);
    padding: 4rem 4rem 3rem;
    border-bottom: 3px solid var(--gold);
    position: relative;
    overflow: hidden;
  }

  #hero::before {
    content: '☩';
    position: absolute;
    right: 3rem; top: 1.5rem;
    font-size: 6rem;
    color: rgba(184,134,11,0.08);
    pointer-events: none;
  }

  #hero .version {
    font-family: 'Fira Mono', monospace;
    font-size: 0.7rem;
    color: var(--gold);
    letter-spacing: 0.15em;
    text-transform: uppercase;
    margin-bottom: 0.8rem;
    opacity: 0.8;
  }

  #hero h1 {
    font-family: 'Cinzel', serif;
    font-size: 2.4rem;
    font-weight: 700;
    color: var(--white);
    line-height: 1.15;
    margin-bottom: 0.6rem;
    text-shadow: 0 2px 8px rgba(0,0,0,0.6);
  }

  #hero h1 span { color: var(--gold); }

  #hero .subtitle {
    color: #c4a97a;
    font-size: 1rem;
    font-style: italic;
    margin-bottom: 2rem;
  }

  .hero-pills {
    display: flex;
    flex-wrap: wrap;
    gap: 0.5rem;
  }

  .pill {
    background: rgba(184,134,11,0.15);
    border: 1px solid rgba(184,134,11,0.35);
    color: var(--gold);
    font-family: 'Fira Mono', monospace;
    font-size: 0.65rem;
    padding: 0.25rem 0.75rem;
    letter-spacing: 0.08em;
    text-transform: uppercase;
  }

  /* ── CONTENT AREA ── */
  .content { padding: 0 3.5rem 4rem; }

  /* ── SECTION BLOCKS ── */
  .guide-section {
    margin-top: 3.5rem;
    padding-top: 1rem;
    border-top: 2px solid var(--faint);
  }

  .guide-section:first-of-type { border-top: none; }

  h2.sec-title {
    font-family: 'Cinzel', serif;
    font-size: 1.5rem;
    font-weight: 700;
    color: var(--blood);
    letter-spacing: 0.04em;
    margin-bottom: 0.3rem;
  }

  h2.sec-title .tag {
    font-size: 0.6rem;
    font-family: 'Fira Mono', monospace;
    background: var(--blood);
    color: var(--white);
    padding: 0.1rem 0.45rem;
    letter-spacing: 0.1em;
    vertical-align: middle;
    margin-left: 0.5rem;
    text-transform: uppercase;
  }

  h3.sub-title {
    font-family: 'Cinzel', serif;
    font-size: 1rem;
    font-weight: 600;
    color: var(--rust);
    margin: 1.6rem 0 0.5rem;
    letter-spacing: 0.03em;
  }

  h4.item-title {
    font-family: 'Cinzel', serif;
    font-size: 0.85rem;
    font-weight: 600;
    color: var(--deep);
    margin: 1.2rem 0 0.3rem;
    letter-spacing: 0.04em;
    text-transform: uppercase;
  }

  p { margin-bottom: 0.75rem; color: #2c1a0a; }

  /* ── CALLOUT BOXES ── */
  .callout {
    border-left: 4px solid var(--gold);
    background: var(--aged);
    padding: 0.9rem 1.2rem;
    margin: 1rem 0 1.4rem;
    font-size: 0.92rem;
  }

  .callout.danger { border-left-color: var(--blood); }
  .callout.info   { border-left-color: #4a7a8a; }

  .callout strong {
    font-family: 'Cinzel', serif;
    font-size: 0.72rem;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    display: block;
    margin-bottom: 0.4rem;
    color: var(--gold);
  }

  .callout.danger strong { color: var(--blood); }
  .callout.info strong   { color: #4a7a8a; }

  /* ── ROLL OUTCOMES ── */
  .roll-box {
    background: var(--deep);
    color: var(--white);
    padding: 1rem 1.4rem;
    margin: 1rem 0 1.4rem;
  }

  .roll-box h4 {
    font-family: 'Cinzel', serif;
    font-size: 0.72rem;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    color: var(--gold);
    margin-bottom: 0.6rem;
  }

  .roll-item {
    display: flex;
    gap: 0.8rem;
    align-items: flex-start;
    margin-bottom: 0.4rem;
    font-size: 0.9rem;
    line-height: 1.4;
    color: #e8d8b8;
  }

  .roll-die {
    font-family: 'Fira Mono', monospace;
    font-size: 0.7rem;
    font-weight: 500;
    color: var(--deep);
    background: var(--gold);
    padding: 0.15rem 0.4rem;
    flex-shrink: 0;
    margin-top: 0.15rem;
    min-width: 52px;
    text-align: center;
  }

  .roll-die.bad   { background: var(--blood); }
  .roll-die.great { background: #2a6e2a; }

  /* ── TABLES ── */
  .table-wrap { overflow-x: auto; margin: 1rem 0 1.4rem; }

  table {
    width: 100%;
    border-collapse: collapse;
    font-size: 0.85rem;
  }

  thead tr { background: var(--deep); }

  thead th {
    font-family: 'Cinzel', serif;
    font-size: 0.65rem;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    color: var(--gold);
    padding: 0.55rem 0.8rem;
    text-align: left;
    white-space: nowrap;
  }

  tbody tr { border-bottom: 1px solid var(--faint); }
  tbody tr:nth-child(even) { background: var(--aged); }
  tbody tr:hover { background: #ddd0ae; }

  td {
    padding: 0.45rem 0.8rem;
    vertical-align: top;
    color: var(--ink);
  }

  td strong { color: var(--rust); }

  /* ── ITEM CARDS (potions/poisons) ── */
  .card-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(290px, 1fr));
    gap: 1rem;
    margin: 1rem 0 1.4rem;
  }

  .card {
    background: var(--white);
    border: 1px solid var(--faint);
    border-top: 3px solid var(--gold);
    padding: 1rem 1.1rem;
  }

  .card.rare    { border-top-color: #4a7a8a; }
  .card.veryrare{ border-top-color: #6a3a8a; }
  .card.legendary{ border-top-color: var(--blood); }
  .card.uncommon { border-top-color: var(--rust); }
  .card.common  { border-top-color: var(--gold); }

  .card-name {
    font-family: 'Cinzel', serif;
    font-size: 0.9rem;
    font-weight: 700;
    color: var(--deep);
    margin-bottom: 0.2rem;
  }

  .card-meta {
    font-family: 'Fira Mono', monospace;
    font-size: 0.62rem;
    color: var(--muted);
    letter-spacing: 0.05em;
    margin-bottom: 0.55rem;
    display: flex;
    flex-wrap: wrap;
    gap: 0.3rem;
  }

  .badge {
    background: var(--aged);
    padding: 0.1rem 0.4rem;
    font-size: 0.58rem;
    text-transform: uppercase;
    letter-spacing: 0.07em;
    color: var(--muted);
    border: 1px solid var(--faint);
  }

  .badge.rare     { background: #d0e8f0; color: #2a5a6a; border-color: #a0c8d8; }
  .badge.veryrare { background: #e0d0f0; color: #4a2a6a; border-color: #c0a0d8; }
  .badge.legendary{ background: #f0d0d0; color: #6a1a1a; border-color: #d8a0a0; }
  .badge.uncommon { background: #f0e0d0; color: #6a3a0a; border-color: #d8b888; }

  .card-ing {
    font-size: 0.84rem;
    margin-bottom: 0.4rem;
  }

  .card-ing strong {
    font-family: 'Cinzel', serif;
    font-size: 0.65rem;
    text-transform: uppercase;
    letter-spacing: 0.07em;
    color: var(--muted);
  }

  .card-effect {
    font-size: 0.84rem;
    color: #3a2a10;
    line-height: 1.45;
  }

  .card-stats {
    display: flex;
    gap: 1rem;
    margin-top: 0.6rem;
    padding-top: 0.5rem;
    border-top: 1px solid var(--faint);
    font-family: 'Fira Mono', monospace;
    font-size: 0.65rem;
    color: var(--muted);
  }

  .stat-block span { display: block; }
  .stat-block .val { color: var(--rust); font-weight: 500; }

  /* ── RANK TABLE ── */
  .rank-table td:first-child {
    font-family: 'Cinzel', serif;
    font-weight: 700;
    font-size: 1rem;
    color: var(--blood);
  }

  /* ── MATERIAL LIST ── */
  .mat-list { columns: 2; column-gap: 2rem; margin: 0.5rem 0 1rem; }

  .mat-item {
    break-inside: avoid;
    display: flex;
    gap: 0.5rem;
    align-items: flex-start;
    margin-bottom: 0.5rem;
    font-size: 0.87rem;
  }

  .mat-ele {
    font-family: 'Fira Mono', monospace;
    font-size: 0.6rem;
    padding: 0.1rem 0.4rem;
    background: var(--deep);
    color: var(--gold);
    flex-shrink: 0;
    margin-top: 0.2rem;
    white-space: nowrap;
  }

  .mat-name { font-weight: 600; color: var(--rust); }
  .mat-desc { color: var(--muted); }

  /* ── PROFESSION CARDS ── */
  .prof-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
    gap: 0.8rem;
    margin: 1rem 0;
  }

  .prof-card {
    background: var(--white);
    border: 1px solid var(--faint);
    padding: 0.9rem 1rem;
    transition: transform 0.15s;
    cursor: default;
  }

  .prof-card:hover { transform: translateY(-2px); }

  .prof-card h4 {
    font-family: 'Cinzel', serif;
    font-size: 0.8rem;
    color: var(--blood);
    margin-bottom: 0.3rem;
    text-transform: uppercase;
    letter-spacing: 0.05em;
  }

  .prof-card p { font-size: 0.8rem; color: var(--muted); margin: 0; }

  /* ── REPAIR TABLE ── */
  .repair-ranks {
    display: flex;
    gap: 0.5rem;
    flex-wrap: wrap;
    margin: 0.6rem 0;
  }

  .rank-badge {
    font-family: 'Fira Mono', monospace;
    font-size: 0.7rem;
    background: var(--deep);
    color: var(--gold);
    padding: 0.2rem 0.6rem;
    border: 1px solid var(--gold);
  }

  /* ── FOOTER ── */
  footer {
    background: var(--deep);
    color: #6a4f2a;
    text-align: center;
    padding: 1.5rem;
    font-family: 'Cinzel', serif;
    font-size: 0.65rem;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    border-top: 2px solid var(--gold);
  }

  /* ── RESPONSIVE ── */
  @media (max-width: 860px) {
    #sidebar { display: none; }
    #main { margin-left: 0; }
    .content { padding: 0 1.4rem 3rem; }
    #hero { padding: 2.5rem 1.4rem 2rem; }
    .mat-list { columns: 1; }
    .card-grid { grid-template-columns: 1fr; }
  }

/* ───────────────────────────────────────────────
   BLACK BANNER DARK WATERMARK THEME
   Added for GitHub Pages index.html
   ─────────────────────────────────────────────── */

:root {
  --ink: #e8dcc2;
  --parchment: #11100d;
  --aged: rgba(30, 25, 18, 0.88);
  --deep: #060606;
  --blood: #8d2626;
  --gold: #c79a3a;
  --rust: #b97b30;
  --muted: #b9aa8d;
  --faint: rgba(199, 154, 58, 0.28);
  --white: #f4ead3;
}

body {
  background: #050505;
  color: #e8dcc2;
}

#sidebar {
  background: var(--deep);
  background-size: 185px;
  background-repeat: no-repeat;
  background-position: center 22px;
  border-right: 1px solid rgba(199,154,58,.65);
  box-shadow: 8px 0 30px rgba(0,0,0,.65);
}

.sidebar-logo-img {
  display: block;
  width: 150px;
  max-width: 85%;
  margin: 0 auto 1rem auto;
  filter: drop-shadow(0 0 10px rgba(255,255,255,.12));
}

#sidebar .logo {
  padding: 1.15rem 1rem 1rem;
  text-align: center;
  border-bottom: 1px solid rgba(199,154,58,.25);
}

#sidebar .logo h2 {
  color: var(--gold);
  font-size: .9rem;
  text-shadow: 0 2px 8px rgba(0,0,0,.8);
}

#sidebar .logo p {
  color: #b9aa8d;
}

#sidebar nav a {
  color: #d9c58f;
  border-left-color: transparent;
}

#sidebar nav a:hover {
  color: #fff1c7;
  background: linear-gradient(90deg, rgba(199,154,58,.22), rgba(199,154,58,.04));
  border-left-color: var(--gold);
  box-shadow: inset 0 0 18px rgba(199,154,58,.11);
}

#sidebar nav .section-head {
  color: #8f7138;
}

#main {
  position: relative;
  margin-left: 230px;
  min-height: 100vh;
  background:
    radial-gradient(circle at center 220px, rgba(199,154,58,.08), transparent 320px),
    linear-gradient(rgba(7,7,7,.93), rgba(10,9,7,.96)),
    #080807;
  color: #e8dcc2;
  overflow: hidden;
}

#main::before {
  content: "";
  position: fixed;
  top: 50%;
  left: calc(230px + ((100vw - 230px) / 2));
  width: min(850px, 70vw);
  height: min(850px, 70vw);
  transform: translate(-50%, -50%);
  background-image: none;
  background-repeat: no-repeat;
  background-position: center;
  background-size: contain;
  opacity: .075;
  filter: grayscale(100%) contrast(115%);
  pointer-events: none;
  z-index: 0;
}

#main::after {
  content: "";
  position: fixed;
  inset: 0;
  background:
    radial-gradient(circle at center, transparent 0%, rgba(0,0,0,.2) 55%, rgba(0,0,0,.72) 100%),
    repeating-linear-gradient(0deg, rgba(255,255,255,.015), rgba(255,255,255,.015) 1px, transparent 1px, transparent 4px);
  pointer-events: none;
  z-index: 0;
}

#hero,
.content,
footer {
  position: relative;
  z-index: 2;
}

#hero {
  min-height: 620px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
  background:
    linear-gradient(rgba(0,0,0,.2), rgba(0,0,0,.55));
  border-bottom: 1px solid rgba(199,154,58,.75);
  padding: 5rem 4rem 4rem;
}

#hero::before {
  content: "";
  position: absolute;
  inset: 0;
  background-image: none;
  background-repeat: no-repeat;
  background-position: center 35px;
  background-size: min(760px, 80vw);
  opacity: .11;
  filter: grayscale(100%) contrast(125%);
  z-index: -1;
}

.hero-logo {
  width: min(360px, 70vw);
  display: block;
  margin: 0 auto 1.3rem;
  opacity: .92;
  filter: drop-shadow(0 0 22px rgba(255,255,255,.08));
}

#hero .version {
  color: #b99243;
}

#hero h1 {
  font-size: clamp(2.5rem, 6vw, 4.6rem);
  color: var(--gold);
  text-shadow: 0 2px 20px rgba(0,0,0,.95);
}

#hero h1 span {
  color: #e4c978;
}

#hero .subtitle {
  color: #d9cfba;
  font-size: 1.25rem;
}

.pill {
  background: rgba(199,154,58,.12);
  border-color: rgba(199,154,58,.45);
  color: #e5c36a;
}

.content {
  background: rgba(7,7,7,.68);
  box-shadow: inset 0 1px 0 rgba(199,154,58,.12);
}

.guide-section {
  border-top: 1px solid rgba(199,154,58,.25);
}

h2.sec-title {
  color: var(--gold);
  text-shadow: 0 2px 10px rgba(0,0,0,.6);
}

h2.sec-title .tag {
  background: rgba(122,31,31,.85);
  color: #fdf3d6;
  border: 1px solid rgba(199,154,58,.35);
}

h3.sub-title {
  color: #d8b46a;
}

h4.item-title,
.card-name {
  color: #f1d994;
}

p, td, .card-effect, .card-ing {
  color: #d8ccb0;
}

a {
  color: #e4bd5c;
}

.callout {
  background: rgba(25,22,17,.88);
  border-left: 4px solid var(--gold);
  color: #e8dcc2;
  box-shadow: 0 8px 28px rgba(0,0,0,.28);
}

.callout strong {
  color: #d9b456;
}

.callout.danger {
  border-left-color: #9d2e2e;
}

.callout.info {
  border-left-color: #5b8ea0;
}

.roll-box {
  background:
    linear-gradient(135deg, rgba(16,14,11,.95), rgba(34,25,11,.9));
  border: 1px solid rgba(199,154,58,.28);
  box-shadow: 0 8px 28px rgba(0,0,0,.28);
}

table {
  background: rgba(13,12,10,.78);
  border: 1px solid rgba(199,154,58,.24);
}

thead tr {
  background: #090806;
}

thead th {
  color: #d7b04c;
  border-bottom: 1px solid rgba(199,154,58,.35);
}

tbody tr {
  border-bottom: 1px solid rgba(199,154,58,.16);
}

tbody tr:nth-child(even) {
  background: rgba(199,154,58,.055);
}

tbody tr:hover {
  background: rgba(199,154,58,.12);
}

td strong {
  color: #ddb85f;
}

.card {
  background: rgba(18,17,15,.92);
  border: 1px solid rgba(199,154,58,.25);
  border-top: 3px solid var(--gold);
  box-shadow: 0 8px 24px rgba(0,0,0,.28);
}

.card-meta, .card-stats, .badge {
  color: #b9aa8d;
}

.badge {
  background: rgba(199,154,58,.08);
  border-color: rgba(199,154,58,.25);
}

.mat-ele {
  background: #0a0907;
  border: 1px solid rgba(199,154,58,.35);
}

.mat-name {
  color: #ddb85f;
}

.mat-item,
.mat-desc {
  color: #cfc2a8;
}

.prof-card {
  background: rgba(18,17,15,.92);
  border: 1px solid rgba(199,154,58,.22);
}

.prof-card h4 {
  color: #d8b46a;
}

.prof-card p {
  color: #cfc2a8;
}

footer {
  background: #050505;
  border-top: 1px solid rgba(199,154,58,.65);
  color: #9d854a;
}

@media (max-width: 860px) {
  #main {
    margin-left: 0;
  }

  #main::before {
    left: 50%;
    width: 95vw;
    height: 95vw;
  }

  #hero {
    min-height: 520px;
    padding: 3rem 1.4rem 2.5rem;
  }

  .hero-logo {
    width: min(280px, 72vw);
  }
}



/* ───────────────────────────────────────────────
   FINAL READABILITY PATCH — ALL TABLES / CHARTS
   This patch is intentionally placed LAST in the style block.
   It overrides light table/chart colors across the full guide.
   ─────────────────────────────────────────────── */

.table-wrap,
.guide-section .table-wrap {
  background: rgba(0, 0, 0, 0.35) !important;
  border: 1px solid rgba(199,154,58,.35) !important;
  padding: 0 !important;
  overflow-x: auto !important;
}

table,
.guide-section table,
.content table,
#main table {
  width: 100% !important;
  border-collapse: collapse !important;
  background: #11100d !important;
  border: 1px solid rgba(199,154,58,.5) !important;
  color: #f3e6c6 !important;
}

table thead,
table thead tr,
.guide-section table thead,
.guide-section table thead tr,
.content table thead,
.content table thead tr,
#main table thead,
#main table thead tr {
  background: #1f170b !important;
  color: #f0c75e !important;
}

table thead th,
.guide-section table thead th,
.content table thead th,
#main table thead th,
th {
  background: #1f170b !important;
  color: #f0c75e !important;
  border: 1px solid rgba(199,154,58,.45) !important;
  border-bottom: 2px solid rgba(199,154,58,.75) !important;
  text-shadow: none !important;
}

table tbody,
.guide-section table tbody,
.content table tbody,
#main table tbody {
  background: #11100d !important;
}

table tbody tr,
.guide-section table tbody tr,
.content table tbody tr,
#main table tbody tr {
  background: #181612 !important;
  border-bottom: 1px solid rgba(199,154,58,.25) !important;
}

table tbody tr:nth-child(even),
.guide-section table tbody tr:nth-child(even),
.content table tbody tr:nth-child(even),
#main table tbody tr:nth-child(even) {
  background: #242016 !important;
}

table tbody tr:nth-child(odd),
.guide-section table tbody tr:nth-child(odd),
.content table tbody tr:nth-child(odd),
#main table tbody tr:nth-child(odd) {
  background: #181612 !important;
}

table tbody tr:hover,
.guide-section table tbody tr:hover,
.content table tbody tr:hover,
#main table tbody tr:hover {
  background: #352812 !important;
}

table td,
.guide-section table td,
.content table td,
#main table td,
td {
  background: transparent !important;
  color: #f3e6c6 !important;
  border: 1px solid rgba(199,154,58,.20) !important;
  text-shadow: none !important;
}

table td:first-child,
.guide-section table td:first-child,
.content table td:first-child,
#main table td:first-child {
  color: #ffe2a0 !important;
}

table td strong,
.guide-section table td strong,
.content table td strong,
#main table td strong,
td strong {
  color: #ffd36f !important;
  font-weight: 700 !important;
}

.rank-table,
td.rank-table,
.rank-table td:first-child {
  color: #ffd36f !important;
  background: transparent !important;
}

/* Fix any charts/tables using inline or inherited pale colors */
table *,
.guide-section table *,
.content table *,
#main table * {
  text-shadow: none !important;
}

/* Preserve useful gold keyword emphasis while improving contrast */
td b,
td em,
td strong,
tbody b,
tbody em,
tbody strong {
  color: #ffd36f !important;
}

/* Extra safety for white/light cells from browser defaults */
tr,
tbody,
thead,
th,
td {
  box-shadow: none !important;
}

</style>
</head>
<body>

<!-- SIDEBAR -->
<aside id="sidebar">
  <div class="logo">


    <h2>Black Banner Company<br>Crafting Guide</h2>
    <p>v3.2.8 · Last updated 6 June 2026</p>
  </div>
  <nav>
    <div class="section-head">Core Rules</div>
    <a href="#intro">Introduction</a>
    <a href="#training">Training & Learning</a>
    <a href="#rank-chart">Rank Chart</a>
    <a href="#how-to-craft">How to Craft</a>
    <a href="#prime-base">Prime/Base Materials</a>

    <div class="section-head">Gathering</div>
    <a href="#harvesting">Harvesting Creatures</a>
    <a href="#metals">Exotic Metals</a>
    <a href="#stones">Stones, Woods & Weaves</a>
    <a href="#herbs">Plants & Herbs</a>

    <div class="section-head">Professions</div>
    <a href="#alchemist">Alchemist's Supplies</a>
    <a href="#brewer">Brewer's Supplies</a>
    <a href="#calligraphy">Calligraphy Supplies</a>
    <a href="#carpenter">Carpenter's Tools</a>
    <a href="#cobbler">Cobbler's Tools</a>
    <a href="#cooking">Cooking Utensils</a>
    <a href="#glassblower">Glassblower's Tools</a>
    <a href="#jeweller">Jeweller's Tools</a>
    <a href="#leatherworker">Leatherworker's Tools</a>
    <a href="#mason">Mason's Tools</a>
    <a href="#painter">Painter's Supplies</a>
    <a href="#potter">Potter's Tools</a>
    <a href="#smith">Smith's Tools</a>
    <a href="#weaver">Weaver's Tools</a>
    <a href="#woodcarver">Woodcarver's Tools</a>
    <a href="#herbalism">Herbalism Kit</a>
    <a href="#forgery">Forgery Kit</a>
    <a href="#disguise">Disguise Kit</a>
    <a href="#poisoner">Poisoner's Kit</a>

    <div class="section-head">Advanced</div>
    <a href="#interdisciplinary">Interdisciplinary Crafts</a>
    <a href="#repair">Item Repair</a>
    <a href="#spell-crafting">Spell Material Crafting</a>
    <a href="#spell-trading">Spell Trading</a>
    <a href="#modifiers">Crafting Modifier Rulings</a>
    <a href="#changelog">Changelog</a>
  </nav>
</aside>

<!-- MAIN -->
<main id="main">

  <!-- HERO -->
  <header id="hero">


    <div class="version">Official Guide · v3.2.8 · Created by Hellbread · Edited by Ooxy</div>
    <h1>Black Banner Company<br><span>Crafting Guide</span></h1>
    <p class="subtitle">Potions, poisons, armour, blades, and everything in between.</p>
    <div class="hero-pills">
      <span class="pill">20 Professions</span>
      <span class="pill">32-hr Work Week</span>
      <span class="pill">6 Rarity Tiers</span>
      <span class="pill">Prime/Base System</span>
      <span class="pill">Ranks F → S</span>
    </div>
  </header>

  <div class="content">

    <!-- ══════════════════════════════════════════════ -->
    <!-- CORE RULES -->
    <!-- ══════════════════════════════════════════════ -->

    <div class="guide-section" id="intro">
      <h2 class="sec-title">Introduction <span class="tag">Core</span></h2>
      <p>Welcome to Black Banner Company's crafting system. This guide covers everything you need to gather materials, learn professions, and craft items during your downtime weeks.</p>

      <div class="callout">
        <strong>Three Key Systems</strong>
        <b>Rank System:</b> Your progression is broken into Ranks (F through S), each covering several levels. Ranks determine what materials you can find and craft.<br><br>
        <b>The Main Chart:</b> All exotic materials and loot have a rarity tied to the rank of the quest they're found on. Use this to know what you can find and what things are worth.<br><br>
        <b>The Work Week:</b> Between adventures you have a <em>32-hour work week</em>. All crafting times in this guide use those hours. If you spend hours crafting, you cannot also use those hours for training that week.
      </div>
    </div>

    <!-- RANK CHART -->
    <div class="guide-section" id="rank-chart">
      <h2 class="sec-title">Rank Chart</h2>
      <div class="table-wrap">
        <table>
          <thead>
            <tr><th>Rank</th><th>Levels</th><th>Material Rarity</th><th>Market Value</th><th>+X Bonus</th><th>Meat/Blood Value</th></tr>
          </thead>
          <tbody>
            <tr><td class="rank-table">F</td><td>1–2</td><td>—</td><td>—</td><td>—</td><td>—</td></tr>
            <tr><td class="rank-table">E</td><td>3–5</td><td>Common</td><td>15g / unit</td><td>+0</td><td>3g / unit</td></tr>
            <tr><td class="rank-table">D</td><td>6–8</td><td>Uncommon</td><td>150g / unit</td><td>+1</td><td>30g / unit</td></tr>
            <tr><td class="rank-table">C</td><td>9–11</td><td>Rare</td><td>300g / unit</td><td>+2</td><td>60g / unit</td></tr>
            <tr><td class="rank-table">B</td><td>12–14</td><td>Rare+</td><td>850g / unit</td><td>+3</td><td>170g / unit</td></tr>
            <tr><td class="rank-table">A</td><td>15–17</td><td>Very Rare</td><td>1,500g / unit</td><td>+4</td><td>300g / unit</td></tr>
            <tr><td class="rank-table">S</td><td>18–20</td><td>Legendary</td><td>5,600g / unit</td><td>+5</td><td>1,120g / unit</td></tr>
          </tbody>
        </table>
      </div>
      <p><em>Whenever a recipe or item says "+X", substitute the X value from the row matching that material's rank above.</em></p>
    </div>

    <!-- TRAINING -->
    <div class="guide-section" id="training">
      <h2 class="sec-title">Training & Learning</h2>
      <p>To learn a new tool proficiency, hobby (musical instrument or gaming set), or language, follow these rules:</p>

      <div class="callout">
        <strong>How Training Works</strong>
        • <b>Duration:</b> 10 work weeks, committing all 32 hours each week.<br>
        • <b>Cost:</b> 25 gold per week (250g total).<br>
        • <b>You cannot craft during a training week.</b> Any crafting (even 2 hours) pauses training until the next week.<br>
        • <b>Retraining:</b> You can swap one proficiency for another with the same 10 weeks and 250g — even re-learning a lost one.<br>
        • <b>Guild Bonus:</b> Upon joining Black Banner Company, you may train one additional tool/kit proficiency beyond your character sheet.
      </div>

      <div class="callout danger">
        <strong>Important Restrictions</strong>
        • You may only become an <b>Expert</b> in <b>one</b> tool. This choice is permanent.<br>
        • You can only have one <b>hobby</b> (instrument or gaming set) at a time; retrain to change it.<br>
        • Everyone must spend 10 weeks — no exceptions, no shortcuts.
      </div>
    </div>

    <!-- HOW TO CRAFT -->
    <div class="guide-section" id="how-to-craft">
      <h2 class="sec-title">How to Craft</h2>
      <p>To craft any item in this guide, you need the appropriate tool, proficiency with that tool, any required equipment (Workshop, Lab, etc.), and the listed materials. Then roll:</p>

      <div class="callout">
        <strong>The Crafting Roll</strong>
        Roll <b>1d20 + your Proficiency Modifier</b> vs. the recipe's DC. Meet it or beat it — it succeeds.<br><br>
        <em>Note: Ability score modifiers (STR, INT, etc.) are NOT added. Only your proficiency modifier applies.</em>
      </div>

      <div class="callout info">
        <strong>Rank Requirement</strong>
        Your character level must be within one rank of the materials used to craft or wear an item. For example, an E-Rank character cannot craft or wear Ignum Fullplate, which requires B-Rank materials.
      </div>
    </div>

    <!-- PRIME/BASE SYSTEM -->
    <div class="guide-section" id="prime-base">
      <h2 class="sec-title">Prime / Base Material System</h2>
      <p>Many exotic recipes use two types of materials:</p>

      <div class="callout">
        <strong>Prime Material</strong>
        The main component that defines the item (e.g., Chitin in Chitin Half-Plate). Its properties always apply to the finished item.
      </div>

      <div class="callout">
        <strong>Base Material</strong>
        A secondary material consumed during crafting. Its properties are <em>normally lost</em> — <b>unless you roll a Natural 20</b>, in which case the item gains both Prime and Base properties (Critical Success!).<br><br>
        If multiple units of base material are needed, they must all be the same material. No mixing.
      </div>

      <p>You may use the same material as both Prime and Base, but a Nat 20 then yields no extra benefit. Diversify your materials for the best results.</p>
    </div>


    <!-- ══════════════════════════════════════════════ -->
    <!-- GATHERING -->
    <!-- ══════════════════════════════════════════════ -->

    <div class="guide-section" id="harvesting">
      <h2 class="sec-title">Harvesting Creatures <span class="tag">Gathering</span></h2>
      <p>Every corpse can be harvested. The skill check used depends on creature type:</p>

      <div class="table-wrap">
        <table>
          <thead><tr><th>Creature Type</th><th>Skill Check</th></tr></thead>
          <tbody>
            <tr><td>Aberration, Construct, Dragon, Elemental, Ooze</td><td>Arcana</td></tr>
            <tr><td>Celestial, Fey, Fiend, Undead</td><td>Religion</td></tr>
            <tr><td>Beast, Giant, Humanoid, Monstrosity, Plants</td><td>Nature / Survival</td></tr>
          </tbody>
        </table>
      </div>

      <div class="callout">
        <strong>Harvest DC</strong>
        <b>Parts:</b> DC 12 + ½ the creature's CR &nbsp;|&nbsp; <b>Venom Glands:</b> DC 12 + full CR (fail = destroyed + you're poisoned!)
      </div>

      <div class="table-wrap">
        <table>
          <thead><tr><th>Creature Size</th><th>Max Harvest Checks</th><th>Max Units per Check</th><th>Meat Rations</th><th>Gallons of Blood</th></tr></thead>
          <tbody>
            <tr><td>Small</td><td>1</td><td>—</td><td>1</td><td>1</td></tr>
            <tr><td>Medium</td><td>1</td><td>1</td><td>2</td><td>2</td></tr>
            <tr><td>Large</td><td>1</td><td>2</td><td>3</td><td>3</td></tr>
            <tr><td>Huge</td><td>2</td><td>2</td><td>4</td><td>4</td></tr>
            <tr><td>Gargantuan</td><td>2</td><td>3</td><td>6</td><td>6</td></tr>
          </tbody>
        </table>
      </div>

      <div class="callout danger">
        <strong>Blood Spoilage</strong>
        Fresh Beast blood can be drunk immediately. After 10 minutes, blood spoils — the drinker must make a DC 15 Con save or vomit.
      </div>

      <h3 class="sub-title">Harvestable Parts</h3>
      <div class="table-wrap">
        <table>
          <thead><tr><th>Material</th><th>Element</th><th>Source</th></tr></thead>
          <tbody>
            <tr><td><strong>Abominable Skin</strong></td><td>Psychic</td><td>Aberrations and unnatural beings</td></tr>
            <tr><td><strong>Bones</strong></td><td>Piercing/Bludgeoning (or dragon's element)</td><td>Any boned creature</td></tr>
            <tr><td><strong>Chitin</strong></td><td>Physical</td><td>Giant crabs, insects, remorhaz</td></tr>
            <tr><td><strong>Demon Leather</strong></td><td>Fire</td><td>Infernal Planes creatures</td></tr>
            <tr><td><strong>Ellond Hide</strong></td><td>Fire</td><td>Desert/steppe creatures</td></tr>
            <tr><td><strong>Monster Feathers</strong></td><td>Physical</td><td>Hippogriffs, rocs, giant eagles</td></tr>
            <tr><td><strong>Monster Scales</strong></td><td>Physical (or dragon's element)</td><td>Scaly creatures, dragons</td></tr>
            <tr><td><strong>Spirit Pelt</strong></td><td>Force</td><td>Outlands, Ethereal, Astral beasts</td></tr>
            <tr><td><strong>Thick Hide</strong></td><td>Cold</td><td>Thick-furred creatures</td></tr>
            <tr><td><strong>Venom Glands</strong></td><td>Poison</td><td>Venomous creatures</td></tr>
          </tbody>
        </table>
      </div>
    </div>

    <!-- EXOTIC METALS -->
    <div class="guide-section" id="metals">
      <h2 class="sec-title">Exotic Metals <span class="tag">Gathering</span></h2>
      <p>Use a miner's pick and make an Athletics check DC 15 + X to harvest an ore vein. Failure yields nothing. You can find ores up to the rank of the current quest/dungeon.</p>
      <p>Any exotic metal can substitute for iron in a mundane craft — e.g., two E-Rank Plaguesteels can cover 30g of material cost in a Fullplate recipe.</p>
      <div class="mat-list">
        <div class="mat-item"><span class="mat-ele">Physical</span><div><span class="mat-name">Adamantine</span> — The hardest metal known; crits against objects are automatic.</div></div>
        <div class="mat-item"><span class="mat-ele">Fire</span><div><span class="mat-name">Bloodmetal</span> — Crimson, blistering hot. From Gehenna and the Nine Hells.</div></div>
        <div class="mat-item"><span class="mat-ele">Physical</span><div><span class="mat-name">Cold Iron</span> — Also called Wildbane. Frigid metal lethal to fey and fiends.</div></div>
        <div class="mat-item"><span class="mat-ele">Necrotic</span><div><span class="mat-name">Fellsteel</span> — Blackened by necrotic forces, mined from the Shadowfell.</div></div>
        <div class="mat-item"><span class="mat-ele">Physical</span><div><span class="mat-name">Mithril</span> — Platinum-white and flexible, favored by Elves for its lightness.</div></div>
        <div class="mat-item"><span class="mat-ele">Lightning</span><div><span class="mat-name">Moonsteel</span> — Silvery with a purple sheen, from Mount Celestia and Elysium.</div></div>
        <div class="mat-item"><span class="mat-ele">Force</span><div><span class="mat-name">Orichalcum</span> — Bronze-gold with an azure sheen, absorbs magic. From the Outlands.</div></div>
        <div class="mat-item"><span class="mat-ele">Poison</span><div><span class="mat-name">Plaguesteel</span> — Ancient, porous, and mossy. From the Shadowfell and Hades.</div></div>
        <div class="mat-item"><span class="mat-ele">Radiant</span><div><span class="mat-name">Sunsteel</span> — Bright yet cool, rarest of the star steels. Found in the deepest caves.</div></div>
      </div>
    </div>

    <!-- STONES, WOODS, WEAVES -->
    <div class="guide-section" id="stones">
      <h2 class="sec-title">Stones, Woods & Weaves <span class="tag">Gathering</span></h2>
      <p>Collected with a DC 15 + X skill check. Woods require a greataxe; stones/coral/ice require a mining pick. Success = 1 unit (DM may grant more). A Nat 20 gives an extra unit or reveals a nearby source.</p>
      <div class="mat-list">
        <div class="mat-item"><span class="mat-ele">Cold</span><div><span class="mat-name">Coral</span> — Deep-sea organism; prized by water elementals.</div></div>
        <div class="mat-item"><span class="mat-ele">Acid</span><div><span class="mat-name">Deadwood</span> — Grey, rotten, acid-resistant swampwood.</div></div>
        <div class="mat-item"><span class="mat-ele">Piercing</span><div><span class="mat-name">Darkwood</span> — Hard as ash but half the weight; Feywild timber.</div></div>
        <div class="mat-item"><span class="mat-ele">Cold</span><div><span class="mat-name">Eternal Ice</span> — Never melts, pure polar ice from the harshest planes.</div></div>
        <div class="mat-item"><span class="mat-ele">Radiant</span><div><span class="mat-name">Heavenweave</span> — Light-woven fabric from the Positive Plane and Heaven.</div></div>
        <div class="mat-item"><span class="mat-ele">Fire</span><div><span class="mat-name">Ignum</span> — Volcanic rock from the Elemental Plane of Fire.</div></div>
        <div class="mat-item"><span class="mat-ele">Bludgeoning</span><div><span class="mat-name">Ironwood</span> — As heavy as cast iron; only grows in the Beastlands.</div></div>
        <div class="mat-item"><span class="mat-ele">Physical</span><div><span class="mat-name">Leafweave</span> — Alchemically hardened leaves; legendary among Sylvans.</div></div>
        <div class="mat-item"><span class="mat-ele">Slashing</span><div><span class="mat-name">Obsidian</span> — Born in magma; splits to razor-sharp edges.</div></div>
        <div class="mat-item"><span class="mat-ele">Psychic</span><div><span class="mat-name">Shadowsilk</span> — Black semi-transparent silk from Shadowfell spiders.</div></div>
        <div class="mat-item"><span class="mat-ele">Lightning</span><div><span class="mat-name">Skyshard</span> — Glassy, sky-blue crystal from the Elemental Planes of Air.</div></div>
        <div class="mat-item"><span class="mat-ele">Poison</span><div><span class="mat-name">Spidersilk</span> — Sticky and incredibly strong; from web-producing creatures.</div></div>
        <div class="mat-item"><span class="mat-ele">Cold</span><div><span class="mat-name">Summitwood</span> — Blistering cold to the touch; from frozen planar peaks.</div></div>
      </div>
    </div>

    <!-- PLANTS & HERBS -->
    <div class="guide-section" id="herbs">
      <h2 class="sec-title">Plants & Herbs <span class="tag">Gathering</span></h2>
      <p>Finding herbs requires a DC 15 Nature check. Harvesting them requires a DC 15 + X Nature or Survival check (DM's discretion).</p>

      <div class="table-wrap">
        <table>
          <thead><tr><th>Rarity</th><th>Rank</th><th>Value</th><th>Key Examples</th></tr></thead>
          <tbody>
            <tr><td>Common</td><td>E</td><td>15g / unit</td><td>Blue Herb, Blood Herb, Mandrake Root, White Poppy, Dried Ephedra, Drojos Ivy, Ellond Scrub, Kreen Paste (25g)</td></tr>
            <tr><td>Uncommon</td><td>D</td><td>150g / unit</td><td>Ash Chives, Kasuni Juice, Frenn Moss, Spineflower Berries, Corpse Flower, Othur Stalk</td></tr>
            <tr><td>Rare</td><td>C</td><td>300g / unit</td><td>Chromatic Mud, Ghost Blossom, Korin's Fang, Lemurma Bell, Olis Veritus, Taggit Blossom, Ucre Bramble, Xeni Leaves</td></tr>
            <tr><td>Rare+</td><td>B</td><td>850g / unit</td><td>Spirit Petals, Lunar Nectar, Ignant Petals, Wisp Stems</td></tr>
            <tr><td>Very Rare</td><td>A</td><td>1,500g / unit</td><td>Devanian Fungus, Doomsphere Whiskers, Silverstem, Galebloom, Thunder Leaf, Viping Vitalis</td></tr>
            <tr><td>Legendary</td><td>S</td><td>5,600g / unit</td><td>Dragontongue, Voidblossom, Arborian Ivy, Black Lotus</td></tr>
          </tbody>
        </table>
      </div>
    </div>


    <!-- ══════════════════════════════════════════════ -->
    <!-- PROFESSIONS -->
    <!-- ══════════════════════════════════════════════ -->

    <!-- ALCHEMIST -->
    <div class="guide-section" id="alchemist">
      <h2 class="sec-title">Alchemist's Supplies <span class="tag">Profession</span></h2>
      <p><strong>Requirements:</strong> Proficiency with Alchemist's Supplies, Alchemist's Supplies, Alchemy Lab (Workshop optional for common potions).</p>
      <p>Potions can be used as a bonus action if you're holding them and drink them yourself.</p>

      <div class="roll-box">
        <h4>Roll Outcomes</h4>
        <div class="roll-item"><span class="roll-die great">Nat 20</span><span>You gain 1 extra potion.</span></div>
        <div class="roll-item"><span class="roll-die">Success</span><span>Craft succeeds as normal.</span></div>
        <div class="roll-item"><span class="roll-die bad">Failure</span><span>You destroy 1/3 of the materials (rounded down, min 1).</span></div>
        <div class="roll-item"><span class="roll-die bad">Nat 1</span><span>All materials wasted.</span></div>
      </div>

      <h3 class="sub-title">Common Potions (Workshop Optional)</h3>
      <div class="card-grid">
        <div class="card common">
          <div class="card-name">Bottled Breath</div>
          <div class="card-meta"><span class="badge common">Common</span><span class="badge">DC 12</span></div>
          <div class="card-ing"><strong>Ingredients:</strong> Blue Herb ×3, Dried Ephedra ×3</div>
          <div class="card-effect">Exhale for Gust of Wind, or hold it to not breathe for 1 hour.</div>
          <div class="card-stats"><div class="stat-block"><span>Time</span><span class="val">2 hrs</span></div></div>
        </div>
        <div class="card common">
          <div class="card-name">Potion of Animal Friendship</div>
          <div class="card-meta"><span class="badge common">Common</span><span class="badge">DC 10</span></div>
          <div class="card-ing"><strong>Ingredients:</strong> Mandrake Root ×4</div>
          <div class="card-effect">Cast Animal Friendship (save DC 13) at will for 1 hour.</div>
          <div class="card-stats"><div class="stat-block"><span>Time</span><span class="val">1 hr</span></div></div>
        </div>
        <div class="card common">
          <div class="card-name">Potion of Climbing</div>
          <div class="card-meta"><span class="badge common">Common</span><span class="badge">DC 11</span></div>
          <div class="card-ing"><strong>Ingredients:</strong> Blue Herb ×2, Drojos Ivy ×2</div>
          <div class="card-effect">Climbing speed = walking speed + advantage on Athletics (climbing) for 1 hour.</div>
          <div class="card-stats"><div class="stat-block"><span>Time</span><span class="val">1 hr</span></div></div>
        </div>
        <div class="card common">
          <div class="card-name">Potion of Growth</div>
          <div class="card-meta"><span class="badge common">Common</span><span class="badge">DC 10</span></div>
          <div class="card-ing"><strong>Ingredients:</strong> White Poppy ×5, Blood Herb ×2</div>
          <div class="card-effect">Gain Enlarge effect for 1d4 hours (no concentration).</div>
          <div class="card-stats"><div class="stat-block"><span>Time</span><span class="val">4 hrs</span></div></div>
        </div>
      </div>

      <h3 class="sub-title">Uncommon Potions (Workshop Optional)</h3>
      <div class="card-grid">
        <div class="card uncommon">
          <div class="card-name">Oil of Slipperiness</div>
          <div class="card-meta"><span class="badge uncommon">Uncommon</span><span class="badge">DC 12</span></div>
          <div class="card-ing"><strong>Ingredients:</strong> Kasuni Juice ×3</div>
          <div class="card-effect">Freedom of Movement for 8 hours, or coat a 10 ft square (Grease effect).</div>
          <div class="card-stats"><div class="stat-block"><span>Time</span><span class="val">4 hrs</span></div></div>
        </div>
        <div class="card uncommon">
          <div class="card-name">Potion of Advantage</div>
          <div class="card-meta"><span class="badge uncommon">Uncommon</span><span class="badge">DC 13</span></div>
          <div class="card-ing"><strong>Ingredients:</strong> Frenn Moss ×2</div>
          <div class="card-effect">Advantage on one ability check, attack roll, or saving throw within the next hour.</div>
          <div class="card-stats"><div class="stat-block"><span>Time</span><span class="val">4 hrs</span></div></div>
        </div>
        <div class="card uncommon">
          <div class="card-name">Potion of Hill Giant Strength</div>
          <div class="card-meta"><span class="badge uncommon">Uncommon</span><span class="badge">DC 12</span></div>
          <div class="card-ing"><strong>Ingredients:</strong> Ash Chives ×1, Bone of a Hill Giant ×1 (D+)</div>
          <div class="card-effect">STR becomes 21 for 1 hour (no effect if already ≥21).</div>
          <div class="card-stats"><div class="stat-block"><span>Time</span><span class="val">4 hrs</span></div></div>
        </div>
      </div>

      <h3 class="sub-title">Rare Potions (Workshop Required)</h3>
      <div class="card-grid">
        <div class="card rare">
          <div class="card-name">Elixir of Health</div>
          <div class="card-meta"><span class="badge rare">Rare</span><span class="badge">DC 13</span></div>
          <div class="card-ing"><strong>Ingredients:</strong> Xeni Leaves ×2, 1g gold dust</div>
          <div class="card-effect">Cures any disease and removes blinded, deafened, paralyzed, and poisoned.</div>
          <div class="card-stats"><div class="stat-block"><span>Time</span><span class="val">4 hrs</span></div></div>
        </div>
        <div class="card rare">
          <div class="card-name">Potion of Clairvoyance</div>
          <div class="card-meta"><span class="badge rare">Rare</span><span class="badge">DC 14</span></div>
          <div class="card-ing"><strong>Ingredients:</strong> Lemurma Bell ×3</div>
          <div class="card-effect">Gain the effect of the Clairvoyance spell.</div>
          <div class="card-stats"><div class="stat-block"><span>Time</span><span class="val">8 hrs</span></div></div>
        </div>
        <div class="card rare">
          <div class="card-name">Potion of Gaseous Form</div>
          <div class="card-meta"><span class="badge rare">Rare</span><span class="badge">DC 12</span></div>
          <div class="card-ing"><strong>Ingredients:</strong> Ghost Blossom ×2</div>
          <div class="card-effect">Gaseous Form for 1 hour (no concentration). End early as a bonus action.</div>
          <div class="card-stats"><div class="stat-block"><span>Time</span><span class="val">8 hrs</span></div></div>
        </div>
        <div class="card rare">
          <div class="card-name">Potion of Heroism</div>
          <div class="card-meta"><span class="badge rare">Rare</span><span class="badge">DC 14</span></div>
          <div class="card-ing"><strong>Ingredients:</strong> Olis Veritus ×1</div>
          <div class="card-effect">+10 temp HP for 1 hour + Bless effect (no concentration).</div>
          <div class="card-stats"><div class="stat-block"><span>Time</span><span class="val">4 hrs</span></div></div>
        </div>
        <div class="card rare">
          <div class="card-name">Potion of Mind Reading</div>
          <div class="card-meta"><span class="badge rare">Rare</span><span class="badge">DC 16</span></div>
          <div class="card-ing"><strong>Ingredients:</strong> Chromatic Mud ×2</div>
          <div class="card-effect">Detect Thoughts effect (save DC 13).</div>
          <div class="card-stats"><div class="stat-block"><span>Time</span><span class="val">8 hrs</span></div></div>
        </div>
        <div class="card rare">
          <div class="card-name">Potion of Resistance</div>
          <div class="card-meta"><span class="badge rare">Rare</span><span class="badge">DC 15</span></div>
          <div class="card-ing"><strong>Ingredients:</strong> Ucre Bramble ×2</div>
          <div class="card-effect">Resistance to one damage type for 1 hour. Roll 1d10 after crafting to determine type.</div>
          <div class="card-stats"><div class="stat-block"><span>Time</span><span class="val">8 hrs</span></div></div>
        </div>
        <div class="card rare">
          <div class="card-name">Potion of Aqueous Form</div>
          <div class="card-meta"><span class="badge rare">Rare</span><span class="badge">DC 15</span></div>
          <div class="card-ing"><strong>Ingredients:</strong> Korin's Fang ×3</div>
          <div class="card-effect">Transform into a pool of water for 10 minutes. Swim speed 30ft, resistance to non-magical damage, fit through tiny gaps.</div>
          <div class="card-stats"><div class="stat-block"><span>Time</span><span class="val">8 hrs</span></div></div>
        </div>
        <div class="card rare">
          <div class="card-name">Potion of Frost Giant Strength</div>
          <div class="card-meta"><span class="badge rare">Rare</span><span class="badge">DC 16</span></div>
          <div class="card-ing"><strong>Ingredients:</strong> Taggit Blossom ×1, Frost Giant Bone ×1 (C+)</div>
          <div class="card-effect">STR becomes 23 for 1 hour.</div>
          <div class="card-stats"><div class="stat-block"><span>Time</span><span class="val">16 hrs</span></div></div>
        </div>
      </div>

      <h3 class="sub-title">Rare+ Potions (Workshop + Lab)</h3>
      <div class="card-grid">
        <div class="card rare">
          <div class="card-name">Oil of Etherealness</div>
          <div class="card-meta"><span class="badge rare">Rare+</span><span class="badge">DC 17</span></div>
          <div class="card-ing"><strong>Ingredients:</strong> Spirit Petals ×3</div>
          <div class="card-effect">Apply to a creature. Etherealness spell for 1 hour.</div>
          <div class="card-stats"><div class="stat-block"><span>Time</span><span class="val">16 hrs</span></div></div>
        </div>
        <div class="card rare">
          <div class="card-name">Potion of Fire Giant Strength</div>
          <div class="card-meta"><span class="badge rare">Rare+</span><span class="badge">DC 18</span></div>
          <div class="card-ing"><strong>Ingredients:</strong> Ignant Petals ×1, Fire Giant Bone ×1 (B+)</div>
          <div class="card-effect">STR becomes 25 for 1 hour.</div>
          <div class="card-stats"><div class="stat-block"><span>Time</span><span class="val">16 hrs</span></div></div>
        </div>
        <div class="card rare">
          <div class="card-name">Potion of Maximum Power</div>
          <div class="card-meta"><span class="badge rare">Rare+</span><span class="badge">DC 16</span></div>
          <div class="card-ing"><strong>Ingredients:</strong> Lunar Nectar ×3, Plum + Sugar + Mud</div>
          <div class="card-effect">Your next 4th level or lower damage spell within 1 minute deals maximum damage.</div>
          <div class="card-stats"><div class="stat-block"><span>Time</span><span class="val">8 hrs</span></div></div>
        </div>
        <div class="card rare">
          <div class="card-name">Potion of Vitality</div>
          <div class="card-meta"><span class="badge rare">Rare+</span><span class="badge">DC 15</span></div>
          <div class="card-ing"><strong>Ingredients:</strong> Wisp Stems ×2</div>
          <div class="card-effect">Remove all exhaustion and conditions. For 24 hours, all Hit Dice spent heal maximum.</div>
          <div class="card-stats"><div class="stat-block"><span>Time</span><span class="val">8 hrs</span></div></div>
        </div>
      </div>

      <h3 class="sub-title">Very Rare Potions (Workshop + Lab)</h3>
      <div class="card-grid">
        <div class="card veryrare">
          <div class="card-name">Potion of Flying</div>
          <div class="card-meta"><span class="badge veryrare">Very Rare</span><span class="badge">DC 15</span></div>
          <div class="card-ing"><strong>Ingredients:</strong> Thunder Leaf ×1</div>
          <div class="card-effect">Flying speed = walking speed + hover for 1 hour.</div>
          <div class="card-stats"><div class="stat-block"><span>Time</span><span class="val">8 hrs</span></div></div>
        </div>
        <div class="card veryrare">
          <div class="card-name">Potion of Invisibility</div>
          <div class="card-meta"><span class="badge veryrare">Very Rare</span><span class="badge">DC 16</span></div>
          <div class="card-ing"><strong>Ingredients:</strong> Doomsphere Whiskers ×2</div>
          <div class="card-effect">Invisible for 1 hour. Ends early if you attack or cast a spell.</div>
          <div class="card-stats"><div class="stat-block"><span>Time</span><span class="val">16 hrs</span></div></div>
        </div>
        <div class="card veryrare">
          <div class="card-name">Potion of Speed</div>
          <div class="card-meta"><span class="badge veryrare">Very Rare</span><span class="badge">DC 16</span></div>
          <div class="card-ing"><strong>Ingredients:</strong> Galebloom ×2</div>
          <div class="card-effect">Haste effect for 1 minute (no concentration).</div>
          <div class="card-stats"><div class="stat-block"><span>Time</span><span class="val">8 hrs</span></div></div>
        </div>
        <div class="card veryrare">
          <div class="card-name">Potion of Cloud Giant Strength</div>
          <div class="card-meta"><span class="badge veryrare">Very Rare</span><span class="badge">DC 20</span></div>
          <div class="card-ing"><strong>Ingredients:</strong> Devanian Fungus ×1, Thunder Leaf ×1, Cloud Giant Bone ×1 (A+)</div>
          <div class="card-effect">STR becomes 27 for 1 hour.</div>
          <div class="card-stats"><div class="stat-block"><span>Time</span><span class="val">32 hrs</span></div></div>
        </div>
        <div class="card veryrare">
          <div class="card-name">Potion of Longevity</div>
          <div class="card-meta"><span class="badge veryrare">Very Rare</span><span class="badge">DC 21</span></div>
          <div class="card-ing"><strong>Ingredients:</strong> Blue Herb ×4, Silverstem ×3, scorpion's tail, adder's fang, dead spider, tiny heart</div>
          <div class="card-effect">Reduce physical age by 1d6+6 years (min 13). Each subsequent use has 10% cumulative chance to age you instead.</div>
          <div class="card-stats"><div class="stat-block"><span>Time</span><span class="val">24 hrs</span></div></div>
        </div>
        <div class="card veryrare">
          <div class="card-name">Potion of Mind Control</div>
          <div class="card-meta"><span class="badge veryrare">Very Rare</span><span class="badge">DC 20</span></div>
          <div class="card-ing"><strong>Ingredients:</strong> Devanian Fungus ×1, Wisp Stem ×1</div>
          <div class="card-effect">Cast Dominate (Beast, Person, or Monster — roll 1d6) on a creature before your next turn ends. Lasts 1 hour, no concentration.</div>
          <div class="card-stats"><div class="stat-block"><span>Time</span><span class="val">24 hrs</span></div></div>
        </div>
      </div>

      <h3 class="sub-title">Legendary Potions (Workshop + Lab)</h3>
      <div class="card-grid">
        <div class="card legendary">
          <div class="card-name">Oil of Sharpness</div>
          <div class="card-meta"><span class="badge legendary">Legendary</span><span class="badge">DC 17</span></div>
          <div class="card-ing"><strong>Ingredients:</strong> Voidblossom ×1</div>
          <div class="card-effect">Coat one slashing/piercing weapon or 5 pieces of ammo. +3 to attack and damage for 1 hour.</div>
          <div class="card-stats"><div class="stat-block"><span>Time</span><span class="val">32 hrs</span></div></div>
        </div>
        <div class="card legendary">
          <div class="card-name">Potion of Invulnerability</div>
          <div class="card-meta"><span class="badge legendary">Legendary</span><span class="badge">DC 23</span></div>
          <div class="card-ing"><strong>Ingredients:</strong> Dragontongue ×2</div>
          <div class="card-effect">Resistance to all damage for 1 minute.</div>
          <div class="card-stats"><div class="stat-block"><span>Time</span><span class="val">32 hrs</span></div></div>
        </div>
        <div class="card legendary">
          <div class="card-name">Potion of Storm Giant Strength</div>
          <div class="card-meta"><span class="badge legendary">Legendary</span><span class="badge">DC 23</span></div>
          <div class="card-ing"><strong>Ingredients:</strong> Black Lotus ×2, Storm Giant Bone ×1 (S+)</div>
          <div class="card-effect">STR becomes 29 for 1 hour.</div>
          <div class="card-stats"><div class="stat-block"><span>Time</span><span class="val">32 hrs</span></div></div>
        </div>
        <div class="card legendary">
          <div class="card-name">Potion of Possibility</div>
          <div class="card-meta"><span class="badge legendary">Legendary</span><span class="badge">DC 22</span></div>
          <div class="card-ing"><strong>Ingredients:</strong> Arborian Ivy ×3</div>
          <div class="card-effect">Gain 2 Fragments of Possibility (last 8 hrs). Spend a fragment to roll an extra d20 on any attack, check, or save and choose which result to use.</div>
          <div class="card-stats"><div class="stat-block"><span>Time</span><span class="val">32 hrs</span></div></div>
        </div>
      </div>
    </div>

    <!-- BREWER -->
    <div class="guide-section" id="brewer">
      <h2 class="sec-title">Brewer's Supplies <span class="tag">Profession</span></h2>
      <p><strong>Requirements:</strong> Proficiency with Brewer's Supplies, Brewer's Supplies, a keg. 10 lbs of produce = 2g.</p>
      <p>Brewers can dilute potions with exotic alcohol to create two weaker doses from one potion. Great for stretching your supplies — but there's a risk of getting too drunk.</p>

      <div class="roll-box">
        <h4>Roll Outcomes</h4>
        <div class="roll-item"><span class="roll-die great">Nat 20</span><span>Gain 1 extra potion/dilution.</span></div>
        <div class="roll-item"><span class="roll-die">Success</span><span>Craft succeeds as normal.</span></div>
        <div class="roll-item"><span class="roll-die bad">Failure</span><span>Equipment failure — burn 1 unit of the alcohol or herb used (whichever costs more).</span></div>
        <div class="roll-item"><span class="roll-die bad">Nat 1</span><span>All materials wasted.</span></div>
      </div>

      <div class="table-wrap">
        <table>
          <thead><tr><th>Brew</th><th>Materials</th><th>Time</th><th>DC</th><th>Result</th></tr></thead>
          <tbody>
            <tr><td>Alcohol</td><td>20 lbs produce, 1 unit Brewer's Yeast, a keg</td><td>10 hrs</td><td>8</td><td>10 units Alcohol</td></tr>
            <tr><td>Brewer's Yeast</td><td>5 lbs produce, any container</td><td>12 hrs</td><td>12</td><td>10 units Yeast</td></tr>
            <tr><td>Exotic Alcohol</td><td>1 exotic plant, 1 Brewer's Yeast, 2 alcohol</td><td>8 hrs</td><td>10+X</td><td>2 units same-rank exotic alcohol</td></tr>
            <tr><td>Common Dilution</td><td>1 common exotic alcohol + 1 common potion</td><td>1 hr</td><td>10</td><td>2 diluted potions</td></tr>
            <tr><td>Uncommon Dilution</td><td>1 uncommon exotic alcohol + 1 uncommon potion</td><td>2 hrs</td><td>12</td><td>2 diluted potions</td></tr>
            <tr><td>Rare Dilution</td><td>1 rare exotic alcohol + 1 rare potion</td><td>4 hrs</td><td>14</td><td>2 diluted potions</td></tr>
            <tr><td>Rare+ Dilution</td><td>1 rare+ exotic alcohol + 1 rare+ potion</td><td>8 hrs</td><td>16</td><td>2 diluted potions</td></tr>
            <tr><td>Very Rare Dilution</td><td>1 very rare exotic alcohol + 1 very rare potion, Workshop + Lab</td><td>16 hrs</td><td>18</td><td>2 diluted potions</td></tr>
            <tr><td>Legendary Dilution</td><td>1 legendary exotic alcohol + 1 legendary potion, Workshop + Lab</td><td>32 hrs</td><td>20</td><td>2 diluted potions</td></tr>
          </tbody>
        </table>
      </div>

      <div class="callout danger">
        <strong>Drunk Check — When Drinking a Diluted Potion</strong>
        Roll 1d20 <em>minus</em> your Con modifier (positive Con = lower roll = better). Poison immunity = can't benefit at all. Poison resistance = −2 to roll.<br><br>
        <b>Nat 1:</b> Potion works + gain 2d4+Con max HP for 2 hours. <b>0–5:</b> Potion works. <b>6–10:</b> Potion works at end of your next turn. <b>11–16:</b> Works at end of next turn OR roll Failed Drunk Chart. <b>17–19:</b> No effect, roll Failed Drunk Chart. <b>Nat 20:</b> No effect, roll Failed Drunk Chart twice.
      </div>

      <h3 class="sub-title">Failed Drunk Chart</h3>
      <p>Roll a straight d20. All effects happen immediately and last 1 minute unless noted. Some effects are removed by a long rest or magic. (Poison resistance grants advantage on this roll where the Drunk Check directs you here.)</p>
      <div class="table-wrap">
        <table>
          <thead><tr><th>d20</th><th>Effect</th></tr></thead>
          <tbody>
            <tr><td>1–2</td><td>You start vomiting and can't see straight. You are <strong>Poisoned</strong>.</td></tr>
            <tr><td>3–4</td><td>You're wasted — movement speed reduced by 5 ft.</td></tr>
            <tr><td>5–6</td><td>Gain 1 rank of <strong>Exhaustion</strong>.</td></tr>
            <tr><td>7–8</td><td>Gain a permanent phobia (DM's choice or random); frightened when facing it. Removed by Greater Restoration.</td></tr>
            <tr><td>9–10</td><td>Polymorph into a Rat or other CR 0 creature for 1 hour.</td></tr>
            <tr><td>11–12</td><td>You age 2d4 years. <strong>Permanent.</strong></td></tr>
            <tr><td>13–14</td><td>You consider everyone friendly (including enemies). DC 10 Wis save at the start of each turn to end; also ends if you take damage.</td></tr>
            <tr><td>15</td><td>You lose your voice but become telepathic.</td></tr>
            <tr><td>16</td><td>You enlarge or shrink (DM's choice), as if Enlarge/Reduce were cast on you.</td></tr>
            <tr><td>17</td><td>You enter a Rage exactly like the Barbarian's level 1 feature.</td></tr>
            <tr><td>18</td><td>You start growing a beard — gain Poison Resistance as your liver adapts.</td></tr>
            <tr><td>19</td><td>You go invisible, as if Invisibility were cast on you.</td></tr>
            <tr><td>20</td><td>You see god, and she loves you. You charge into melee with advantage on all attacks and resistance to all damage, and refuse to flee. Auto-fail the first save; DC 10 Cha save at the start of each turn thereafter to end.</td></tr>
          </tbody>
        </table>
      </div>

      <p><strong>Expert Perks:</strong> <em>Brew Expert</em> — advantage on Persuasion, History, Arcana, Religion, Deception, Insight, and Performance checks concerning drinks (DM's discretion), plus advantage on Insight to tell if a drink is bad or poisoned. <em>Hardened Liver</em> — advantage on Constitution saves to avoid getting drunk (unless you want to).</p>
    </div>

    <!-- CALLIGRAPHY -->
    <div class="guide-section" id="calligraphy">
      <h2 class="sec-title">Calligraphy Supplies <span class="tag">Profession</span></h2>
      <p><strong>Requirements:</strong> Proficiency with Calligraphy Supplies. Higher level scrolls require a Workshop/Library.</p>
      <p>Scroll makers can use rare herbs or blood as ink — their market value is deducted from the scroll's crafting cost. You must be able to cast the spell yourself to scribe it. Scrolls are price-controlled and cannot be sold below market value.</p>

      <div class="roll-box">
        <h4>Roll Outcomes — Calligraphy Proficiency Check (not Arcana)</h4>
        <div class="roll-item"><span class="roll-die great">Nat 20</span><span>Gain 1 extra scroll.</span></div>
        <div class="roll-item"><span class="roll-die bad">Failure</span><span>Spill ink — double the hours needed (no extra cost). If this exceeds your work week, carry over to next week.</span></div>
        <div class="roll-item"><span class="roll-die bad">Nat 1</span><span>All materials and hours wasted.</span></div>
      </div>

      <p>You must be able to cast the spell yourself to scribe it. Multiple herbs/bloods may be used per craft, but each must individually meet the scroll's level requirement, and excess value over the scroll's cost is not refunded.</p>

      <h3 class="sub-title">Herb &amp; Blood Ink Values for Scroll Crafting</h3>
      <div class="table-wrap">
        <table>
          <thead><tr><th>Rarity</th><th>Rank</th><th>Herb / Blood Value</th><th>+X</th><th>Usable for Scroll Levels</th></tr></thead>
          <tbody>
            <tr><td>Common</td><td>E</td><td>15g / 3g</td><td>+0</td><td>Cantrips, 1st</td></tr>
            <tr><td>Uncommon</td><td>D</td><td>150g / 30g</td><td>+1</td><td>2nd, 3rd</td></tr>
            <tr><td>Rare</td><td>C</td><td>300g / 60g</td><td>+2</td><td>3rd, 4th</td></tr>
            <tr><td>Rare+</td><td>B</td><td>850g / 170g</td><td>+3</td><td>4th, 5th</td></tr>
            <tr><td>Very Rare</td><td>A</td><td>1,500g / 300g</td><td>+4</td><td>5th, 6th</td></tr>
            <tr><td>Legendary</td><td>S</td><td>5,600g / 1,120g</td><td>+5</td><td>6th and up</td></tr>
          </tbody>
        </table>
      </div>

      <div class="table-wrap">
        <table>
          <thead><tr><th>Scroll Level</th><th>Craft DC</th><th>Time</th><th>Market Value</th><th>Facility</th></tr></thead>
          <tbody>
            <tr><td>Cantrip</td><td>10</td><td>4 hrs</td><td>15g</td><td>Optional Workshop</td></tr>
            <tr><td>1st Level</td><td>11</td><td>6 hrs</td><td>25g</td><td>Optional Workshop</td></tr>
            <tr><td>2nd Level</td><td>12</td><td>8 hrs</td><td>250g</td><td>Optional Workshop</td></tr>
            <tr><td>3rd Level</td><td>13</td><td>12 hrs</td><td>500g</td><td>Optional Workshop</td></tr>
            <tr><td>4th Level</td><td>14</td><td>16 hrs</td><td>2,500g</td><td>Workshop</td></tr>
            <tr><td>5th Level</td><td>15</td><td>24 hrs</td><td>5,000g</td><td>Workshop</td></tr>
            <tr><td>6th Level</td><td>16</td><td>32 hrs</td><td>15,000g</td><td>Workshop</td></tr>
            <tr><td>7th Level</td><td>17</td><td>48 hrs</td><td>25,000g</td><td>Library + Workshop</td></tr>
            <tr><td>8th Level</td><td>18</td><td>72 hrs</td><td>50,000g</td><td>Library + Workshop</td></tr>
            <tr><td>9th Level</td><td>19</td><td>96 hrs</td><td>250,000g</td><td>Library + Workshop</td></tr>
          </tbody>
        </table>
      </div>

      <div class="callout info">
        <strong>Scroll Use Rules (Black Banner)</strong>
        Any class may use any spell scroll. If the spell is not on your class list, you must use the Magic Action. If it is on your list, use the normal casting time. Maximum 2 spell scrolls per contract.
      </div>
      <p><strong>Master Scrivener:</strong> reduces all materials needed and craft times by 50%. (Scrolls remain price-controlled and cannot be sold below market value, even to other players.)</p>
    </div>

    <!-- More professions are summarized for conciseness -->

    <!-- CARPENTER -->
    <div class="guide-section" id="carpenter">
      <h2 class="sec-title">Carpenter's Tools <span class="tag">Profession</span></h2>
      <p><strong>Requirements:</strong> Proficiency with Carpenter's Tools, Carpenter's Tools, Wood.</p>
      <div class="table-wrap">
        <table>
          <thead><tr><th>Craft</th><th>Materials</th><th>Time</th><th>DC</th></tr></thead>
          <tbody>
            <tr><td>Small Furniture</td><td>3 units E-Rank exotic wood</td><td>4 hrs + X</td><td>12 + X</td></tr>
            <tr><td>Medium Furniture</td><td>3 units D-Rank exotic wood</td><td>8 hrs + X</td><td>14 + X</td></tr>
            <tr><td>Large Furniture</td><td>3 units C-Rank exotic wood</td><td>12 hrs + X</td><td>16 + X</td></tr>
            <tr><td>Huge Furniture</td><td>3 units B-Rank exotic wood</td><td>16 hrs + X</td><td>18 + X</td></tr>
            <tr><td>Wooden Wheel</td><td>10 lbs wood or 5 units exotic wood</td><td>8 hrs + X</td><td>15</td></tr>
            <tr><td>2-Wheel Cart</td><td>30 lbs wood or 15 units exotic wood</td><td>16 hrs + X</td><td>15</td></tr>
            <tr><td>Home Decoration Picture Frame</td><td>1 unit D+ exotic wood, 1 gallon same-rarity blood</td><td>5 hrs × X</td><td>12 + X</td></tr>
            <tr><td>Custom Orders</td><td>2 lbs wood = 1g</td><td>Ask DM</td><td>Ask DM</td></tr>
            <tr><td>In-game Repairs</td><td>DM discretion</td><td>DM</td><td>DM</td></tr>
            <tr><td>Exotic Hand Glider</td><td>2 units D+ leather, 2 units same-rank wood</td><td>15 hrs + X</td><td>15 + X</td></tr>
          </tbody>
        </table>
      </div>
      <p><strong>Expert Perks:</strong> Emergency Repairman (reduce city damage repair cost by 20%), Handyman (5% rent reduction, stacks with other Handymen), Caravan/Ship Carpenter (50% off travel costs), Wood Expert (advantage on social checks concerning wood; sometimes on Nature checks to identify trees).</p>

      <div class="callout">
        <strong>Home Decoration</strong>
        A permanent skill-boosting artwork made in two parts: the <em>Picture Frame</em> (Carpenter) and the <em>Painting</em> (Painter). The Frame gives +X to the related skill. You can benefit from only one Home Decoration buff at a time and must spend 10 minutes marveling at it every 24 hours to use the buff.
      </div>

      <div class="callout info">
        <strong>Exotic Hand Gliders</strong>
        Carries one Medium or smaller creature, max 150 lbs + 50 lbs per X. Flying speed 60 ft; must descend at least 20 ft each round. AC 12 + X, 35 HP + 10 per X, immune to poison and psychic. Piloted as an action (proficiency with flying/water vehicles, or DC 10 Acrobatics/Sleight of Hand). Nat 1 or over-weight = nose-dive 60 ft. Material grants resistance: Demon Leather (fire), Spirit Pelt (force), Deadwood (acid), Summitwood (cold).
      </div>
    </div>

    <!-- COBBLER -->
    <div class="guide-section" id="cobbler">
      <h2 class="sec-title">Cobbler's Tools <span class="tag">Profession</span></h2>
      <p><strong>Requirements:</strong> Proficiency with Cobbler's Tools, Cobbler's Tools. Uses Prime/Base material system.</p>
      <p>Cobblers craft exotic footwear with remarkable magical properties. Each recipe requires 1 unit of prime material + 1 unit of same-rank base material.</p>
      <div class="table-wrap">
        <table>
          <thead><tr><th>Recipe</th><th>Prime Material</th><th>Time</th><th>DC</th><th>Key Effect</th></tr></thead>
          <tbody>
            <tr><td>Attention Sneakers</td><td>2 units D-Rank Monster Scales</td><td>16 hrs</td><td>16</td><td>Advantage on negotiations when you compliment your boots</td></tr>
            <tr><td>Coral Divers</td><td>1 unit B-Rank Coral</td><td>16 hrs</td><td>16</td><td>Sink to sea floor; walk underwater walls</td></tr>
            <tr><td>Darkwood Surfacers</td><td>1 unit B-Rank Darkwood</td><td>16 hrs</td><td>16</td><td>Walk on water; rocket to surface at 200 ft/round</td></tr>
            <tr><td>Desert Footwraps</td><td>1 unit C-Rank Ellond Hide</td><td>8 hrs</td><td>14</td><td>+1 to fire damage saves (max +2 total)</td></tr>
            <tr><td>Door Bashers</td><td>1 unit D-Rank Adamantine</td><td>16 hrs</td><td>16</td><td>Advantage kicking doors; advantage vs. being pushed. Requires STR 15+</td></tr>
            <tr><td>Dragonscale Greaves</td><td>1 unit C-Rank Dragonscales</td><td>8 hrs</td><td>14</td><td>+1 to saves vs. the dragon's element (max +2 total)</td></tr>
            <tr><td>Flamewalkers</td><td>1 unit C-Rank Infernal Leather</td><td>8 hrs</td><td>14</td><td>Advantage on saves vs. fire from beneath</td></tr>
            <tr><td>Heavenweave Hoppers</td><td>1 unit C-Rank Heavenweave</td><td>8 hrs</td><td>14</td><td>Walk on clouds</td></tr>
            <tr><td>Ice Slippers</td><td>1 unit C-Rank Eternal Ice</td><td>8 hrs</td><td>14</td><td>No slip on ice</td></tr>
            <tr><td>Lava Clompers</td><td>1 unit C-Rank Ignum</td><td>8 hrs</td><td>14</td><td>Walk on lava</td></tr>
            <tr><td>Mithril Jumpers</td><td>1 unit B-Rank Mithril</td><td>16 hrs</td><td>16</td><td>Add DEX mod to jump distance; reduce fall damage by 2d6</td></tr>
            <tr><td>Monster Sprinters</td><td>1 unit any-rank Monster Feathers</td><td>16 hrs</td><td>16</td><td>+1+X movement speed</td></tr>
            <tr><td>Obsidian Kickers</td><td>1 unit D-Rank Obsidian</td><td>4 hrs</td><td>12</td><td>Deal 1 piercing damage/turn to grappled creatures</td></tr>
            <tr><td>Polar Boots</td><td>1 unit C-Rank Thick Hide</td><td>8 hrs</td><td>14</td><td>+1 to saves vs. cold damage (max +2 total)</td></tr>
            <tr><td>Skyshard Skaters</td><td>1 unit B-Rank Skyshard</td><td>16 hrs</td><td>16</td><td>+12 ft movement; must move every turn; DC 15 Acrobatics to not fall prone</td></tr>
            <tr><td>Spidersilks</td><td>1 unit D-Rank Spidersilk</td><td>4 hrs</td><td>12</td><td>Walk on webs without alerting inhabitants</td></tr>
            <tr><td>Spirit Soles</td><td>1 unit C-Rank Spirit Pelt</td><td>8 hrs</td><td>14</td><td>+10 to stealth vs. hearing while in fog/mist</td></tr>
            <tr><td>Tree Climbers</td><td>1 unit D-Rank Leafweave</td><td>4 hrs</td><td>12</td><td>Advantage on Acrobatics/Athletics to climb trees</td></tr>
          </tbody>
        </table>
      </div>
      <p><strong>Foot Expert:</strong> advantage on Persuasion, History, Arcana, Religion, Deception, Insight, and Performance checks concerning feet (DM's discretion).</p>
    </div>

    <!-- COOKING -->
    <div class="guide-section" id="cooking">
      <h2 class="sec-title">Cooking Utensils <span class="tag">Profession</span></h2>
      <p><strong>Requirements:</strong> Proficiency with Cooking Utensils, Chef Feat, spice pouch (5g for 10 pinches), fire. Each recipe yields treats equal to your proficiency modifier.</p>
      <p>Exotic Rations are made by mixing 1 unit of any exotic herb/plant with 10 standard PhB rations. The rarity of the resulting rations matches the herb used.</p>

      <div class="roll-box">
        <h4>Roll Outcomes</h4>
        <div class="roll-item"><span class="roll-die great">Nat 20</span><span>Perfect recipe — 50% more treats (rounded up).</span></div>
        <div class="roll-item"><span class="roll-die bad">Failure</span><span>You burn the food — only 1 treat this craft (no retry needed).</span></div>
        <div class="roll-item"><span class="roll-die bad">Nat 1</span><span>A raccoon ate the whole recipe. Nothing left!</span></div>
      </div>

      <div class="table-wrap">
        <table>
          <thead><tr><th>Prep Recipe</th><th>Materials</th><th>Time</th><th>DC</th></tr></thead>
          <tbody>
            <tr><td>Preserving Meat</td><td>2 lbs raw meat, 1 lb salt</td><td>10 min</td><td>8 + X</td></tr>
            <tr><td>10 Exotic Rations</td><td>10 PhB rations, 1 unit any-rarity exotic plant/herb</td><td>1 hr + X</td><td>8 + X</td></tr>
          </tbody>
        </table>
      </div>

      <div class="table-wrap">
        <table>
          <thead><tr><th>Treat Rarity</th><th>Benefit (Bonus Action to eat)</th><th>Time</th><th>DC</th></tr></thead>
          <tbody>
            <tr><td>Common</td><td>Temp HP = Chef's proficiency bonus</td><td>1 hr</td><td>10</td></tr>
            <tr><td>Uncommon</td><td>Temp HP = 2× proficiency bonus</td><td>2 hrs</td><td>12</td></tr>
            <tr><td>Rare</td><td>Max HP = proficiency bonus</td><td>4 hrs</td><td>14</td></tr>
            <tr><td>Rare+</td><td>Max HP = 2× proficiency bonus</td><td>8 hrs</td><td>16</td></tr>
            <tr><td>Very Rare</td><td>Temp HP + Max HP = 3× proficiency bonus</td><td>16 hrs</td><td>18</td></tr>
            <tr><td>Legendary</td><td>Temp HP + Max HP = 5× proficiency bonus</td><td>32 hrs</td><td>22</td></tr>
          </tbody>
        </table>
      </div>
      <p>You can only benefit from one treat per minute. Gourmand perk: eat a treat as a reaction once per long rest (uses your Emergency Reaction).</p>
      <p><strong>Culinary Expert:</strong> advantage on social checks concerning food (DM's discretion), plus advantage on Insight to tell if food has gone bad or been poisoned.</p>
    </div>

    <!-- GLASSBLOWER -->
    <div class="guide-section" id="glassblower">
      <h2 class="sec-title">Glassblower's Tools <span class="tag">Profession</span></h2>
      <p><strong>Requirements:</strong> Proficiency with Glassblower's Tools. C-Rank+ requires Workshop. Weapon base materials: Adamantine, Cold Iron, Mithril.</p>
      <p>Glassblowers craft decorative objects, weapons from exotic crystals, Planeshift Forks, and Syringes. Weapons deal +X bonus damage of their material's element and can convert all weapon damage (including Sneak Attack, Divine Smite, etc.) to that element.</p>

      <div class="table-wrap">
        <table>
          <thead><tr><th>Recipe</th><th>Materials</th><th>Time</th><th>DC</th></tr></thead>
          <tbody>
            <tr><td>Pair of Glass Cups</td><td>2 lbs sand/crystal or 1 unit exotic</td><td>1 hr</td><td>10 + X</td></tr>
            <tr><td>Crystal Vial</td><td>2 lbs sand/crystal or 1 unit exotic</td><td>2 hrs</td><td>10 + X</td></tr>
            <tr><td>Glass Plate or Pot</td><td>5 lbs or 2 units exotic</td><td>4 hrs</td><td>12 + X</td></tr>
            <tr><td>Small Glass Statue</td><td>10 lbs or 3 units exotic</td><td>8 hrs</td><td>15 + X</td></tr>
            <tr><td>Uncut Lens</td><td>10 lbs or 5 units exotic</td><td>16 hrs</td><td>15 + X</td></tr>
            <tr><td>Skyshard Simple Weapon</td><td>1 unit any-rank Skyshard + 1 base</td><td>8 hrs</td><td>11 + X</td></tr>
            <tr><td>Skyshard Martial Weapon</td><td>2 units C+ Skyshard + 1 base</td><td>16 hrs</td><td>15 + X</td></tr>
            <tr><td>Eternal Ice Simple Weapon</td><td>1 unit any-rank Eternal Ice + 1 base</td><td>8 hrs</td><td>11 + X</td></tr>
            <tr><td>Eternal Ice Martial Weapon</td><td>2 units C+ Eternal Ice + 1 base</td><td>16 hrs</td><td>15 + X</td></tr>
            <tr><td>Obsidian Simple Weapon</td><td>1 unit any-rank Obsidian + 1 base</td><td>8 hrs</td><td>11 + X</td></tr>
            <tr><td>Obsidian Martial Weapon</td><td>2 units D+ Obsidian + 1 base</td><td>16 hrs</td><td>15 + X</td></tr>
            <tr><td>Syringe</td><td>1 unit any-rank Skyshard + 10 lbs premium sand (5g)</td><td>12 hrs + X</td><td>10 + X</td></tr>
            <tr><td>Recovery Dart</td><td>1 healing/diluted potion + 1 same-rarity Syringe</td><td>2 hrs + X</td><td>—</td></tr>
            <tr><td>Alchemical Dart</td><td>1 alchemical/diluted potion + 1 same-rarity Syringe</td><td>2 hrs + X</td><td>—</td></tr>
            <tr><td>Unattuned Planeshift Fork</td><td>1 unit B+ Skyshard or Eternal Ice</td><td>32 hrs</td><td>13</td></tr>
          </tbody>
        </table>
      </div>

      <div class="callout info">
        <strong>Unattuned Planeshift Fork</strong>
        Inert until attuned to a specific plane (then enables Planeshift). Attuning takes three successful DC 25 Arcana checks, made every 4 hours while on the target plane. Three failures, removal from the plane, or 24 hours elapsing destroys it. Skyshard forks tune to Elemental Air or Elemental Chaos; Eternal Ice forks tune to the Far Realms.
      </div>

      <div class="callout">
        <strong>Recovery &amp; Alchemical Darts</strong>
        A syringe thrown as a dart (10/20 ft by hand, 25/100 ft from a blowgun). Against a willing target, attack vs. AC 13; against an unwilling target, attack vs. their AC. On a hit the potion takes effect. A miss has a 50% chance to break and spill. A Critical Strike doubles healing dice (Recovery) or grants the target +1 AC and saves for 2 turns (Alchemical), and negates a diluted potion's downsides.
      </div>

      <div class="callout">
        <strong>Weapon Properties</strong>
        All glass weapons may convert all weapon damage (including Sneak Attack, Divine Smite, etc.) to their Prime Material's damage type.<br>
        <b>Eternal Ice:</b> +X Cold damage on attacks.<br>
        <b>Skyshard:</b> use your Dexterity modifier for attack and damage rolls; +X Lightning damage.<br>
        <b>Obsidian:</b> slashing or piercing weapons deal +X extra slashing or piercing damage.
      </div>
      <p><strong>Expert Perks:</strong> <em>Glasswork Expert</em> — advantage on Persuasion, History, Arcana, Religion, Deception, Insight, and Performance checks concerning glass (DM's discretion). <em>Glassblown Weaponmaster</em> — if you're proficient with a glassblower-made weapon (yours or another's), you deal +1 damage with it.</p>
    </div>

    <!-- JEWELLER -->
    <div class="guide-section" id="jeweller">
      <h2 class="sec-title">Jeweller's Tools <span class="tag">Profession</span></h2>
      <p><strong>Requirements:</strong> Proficiency with Jeweller's Tools, Tinker's Bench. Gems over 500g require a Workshop.</p>
      <div class="table-wrap">
        <table>
          <thead><tr><th>Recipe</th><th>Materials</th><th>Time</th><th>DC</th></tr></thead>
          <tbody>
            <tr><td>Magnifying Glass</td><td>Uncut lens</td><td>2 hrs</td><td>12</td></tr>
            <tr><td>Cut Gem (10g value)</td><td>Uncut gemstone</td><td>1 hr</td><td>10</td></tr>
            <tr><td>Cut Gem (50–100g)</td><td>Uncut gemstone, Tinker's Bench</td><td>4 hrs</td><td>14</td></tr>
            <tr><td>Cut Gem (500–1,000g)</td><td>Uncut gemstone, Tinker's Bench</td><td>8 hrs</td><td>18</td></tr>
            <tr><td>Cut Gem (5,000g)</td><td>Uncut gemstone, Tinker's Bench</td><td>32 hrs</td><td>22</td></tr>
            <tr><td>Cut Gem (custom cut)</td><td>Uncut gemstone, ?</td><td>Ask DM</td><td>Ask DM</td></tr>
            <tr><td>Ring of Minor Enhancement (+1 stat)</td><td>1× Cut Gem (1,000g) + 100g silver</td><td>8 hrs</td><td>16</td></tr>
            <tr><td>Ring of Major Enhancement (+2 stat)</td><td>1× Cut Gem (5,000g) + 100g silver</td><td>8 hrs</td><td>20</td></tr>
            <tr><td>Necklace of Minor Enhancement (+1 save)</td><td>1× Cut Gem (1,000g) + 100g silver</td><td>8 hrs</td><td>16</td></tr>
            <tr><td>Necklace of Major Enhancement (+2 save)</td><td>1× Cut Gem (5,000g) + 100g silver</td><td>8 hrs</td><td>20</td></tr>
          </tbody>
        </table>
      </div>
      <p>You can only wear 1 Minor and 1 Major Enhancement ring at a time.</p>

      <div class="callout">
        <strong>Custom Jewellery</strong>
        Every piece has a base (melted gold, min 10g) and any gemstones you add. Base DC is 8, then add to the DC per gem: <b>+1</b> per five 10g gems, <b>+1</b> per 50–100g gem, <b>+5</b> per 500–1,000g gem, <b>+8</b> per 5,000g+ gem. Custom jobs take hours equal to half the total DC. Modifying existing jewellery starts the formula at DC 8 (e.g., adding a 50g Moonstone = DC 9). Requires a Tinker's Bench.
      </div>
      <p><strong>Gemstones &amp; Jewels Expert:</strong> advantage on Persuasion, History, Arcana, Religion, Deception, Insight, and Performance checks concerning jewels and gemstones (DM's discretion).</p>
    </div>

    <!-- LEATHERWORKER -->
    <div class="guide-section" id="leatherworker">
      <h2 class="sec-title">Leatherworker's Tools <span class="tag">Profession</span></h2>
      <p><strong>Requirements:</strong> Proficiency with Leatherworker's Tools. C-Rank+ requires Workshop. Uses Prime/Base material system.</p>
      <p><strong>Base Materials:</strong> Abominable Skin, Chitin, Bone, Ellond Hide, Thick Hide, Monster Scales.</p>

      <h3 class="sub-title">Armour Properties by Material</h3>
      <div class="table-wrap">
        <table>
          <thead><tr><th>Material</th><th>Resistance / Bonus</th><th>Reaction (once/long rest)</th></tr></thead>
          <tbody>
            <tr><td>Abomination Skin</td><td>+1 save vs. Psychic</td><td>Reduce one Psychic source by Xd8</td></tr>
            <tr><td>Bone</td><td>+1 save vs. Piercing</td><td>Reduce one Piercing source by Xd8</td></tr>
            <tr><td>Chitin</td><td>+1 save vs. Bludgeoning</td><td>Reduce one Bludgeoning source by Xd8</td></tr>
            <tr><td>Demon Leather</td><td>Fire Resistance (full)</td><td>—</td></tr>
            <tr><td>Dragon Scale Mail</td><td>+1 AC (stacks with infusions)</td><td>—</td></tr>
            <tr><td>Ellond Hide</td><td>+1 save vs. Fire + advantage vs. heat Exhaustion</td><td>Reduce one Fire source by Xd8</td></tr>
            <tr><td>Monster Scales</td><td>+1 save vs. Slashing</td><td>Reduce one Slashing source by Xd8</td></tr>
            <tr><td>Spirit Pelt</td><td>Force Resistance (full)</td><td>—</td></tr>
            <tr><td>Thick Hide</td><td>+1 save vs. Cold + advantage vs. cold Exhaustion</td><td>Reduce one Cold source by Xd8</td></tr>
          </tbody>
        </table>
      </div>

      <div class="roll-box">
        <h4>Roll Outcomes</h4>
        <div class="roll-item"><span class="roll-die great">Nat 20</span><span>Reactivates the Base Material (item gains both properties).</span></div>
        <div class="roll-item"><span class="roll-die bad">Failure</span><span>Lose 1/3 of the prime materials (rounded up, min 1).</span></div>
        <div class="roll-item"><span class="roll-die bad">Nat 1</span><span>All materials wasted.</span></div>
      </div>

      <h3 class="sub-title">Exotic Armours</h3>
      <p><em>(L) Light · (M) Medium · (H) Heavy. Each recipe also takes 1 unit of same-rank base material unless noted.</em></p>
      <div class="table-wrap">
        <table>
          <thead><tr><th>Recipe</th><th>Prime Material</th><th>Time</th><th>DC</th></tr></thead>
          <tbody>
            <tr><td>Abomination Leather (L)</td><td>1 unit any-rank Abominable Skin</td><td>6 hrs + X</td><td>11 + X</td></tr>
            <tr><td>Abomination Hide (M)</td><td>2 units any-rank Abominable Skin</td><td>6 hrs + X</td><td>11 + X</td></tr>
            <tr><td>Abomination Studded Leather (L)</td><td>3 units any-rank Abominable Skin</td><td>8 hrs + X</td><td>13 + X</td></tr>
            <tr><td>Chitin Scale Mail (M)</td><td>2 units E+ Chitin</td><td>4 hrs + X</td><td>11 + X</td></tr>
            <tr><td>Chitin Breastplate (M)</td><td>2 units D+ Chitin</td><td>4 hrs + X</td><td>13 + X</td></tr>
            <tr><td>Chitin Half-Plate (M)</td><td>3 units C+ Chitin (+2 base)</td><td>14 hrs + X</td><td>16 + X</td></tr>
            <tr><td>Bone Splintmail (H)</td><td>1 unit D+ Bone</td><td>7 hrs + X</td><td>11 + X</td></tr>
            <tr><td>Bone Breastplate (M)</td><td>2 units D+ Bone</td><td>4 hrs + X</td><td>13 + X</td></tr>
            <tr><td>Bone Half-Plate (M)</td><td>3 units C+ Bone (+2 base)</td><td>14 hrs + X</td><td>16 + X</td></tr>
            <tr><td>Bone Full-Plate (H)</td><td>5 units C+ Bone (+3 base)</td><td>32 hrs</td><td>19 + X</td></tr>
            <tr><td>Ellond Leather Armour (L)</td><td>2 units any-rank Ellond Hide</td><td>6 hrs + X</td><td>11 + X</td></tr>
            <tr><td>Ellond Hide Armour (M)</td><td>2 units any-rank Ellond Hide</td><td>6 hrs + X</td><td>11 + X</td></tr>
            <tr><td>Ellond Studded Leather (L)</td><td>3 units any-rank Ellond Hide</td><td>8 hrs + X</td><td>13 + X</td></tr>
            <tr><td>Thick Leather Armour (L)</td><td>1 unit any-rank Thick Hide</td><td>6 hrs + X</td><td>11 + X</td></tr>
            <tr><td>Thick Hide Armour (M)</td><td>2 units any-rank Thick Hide</td><td>6 hrs + X</td><td>11 + X</td></tr>
            <tr><td>Thick Studded Leather (L)</td><td>3 units any-rank Thick Hide</td><td>8 hrs + X</td><td>13 + X</td></tr>
            <tr><td>Monster Scale Mail (M)</td><td>2 units any-rank Scales</td><td>4 hrs + X</td><td>11 + X</td></tr>
            <tr><td>Monster Scale Splint Mail (H)</td><td>2 units D+ Scales</td><td>7 hrs + X</td><td>11 + X</td></tr>
            <tr><td>Monster Scale Half-Plate (M)</td><td>3 units C+ Scales (+2 base)</td><td>14 hrs + X</td><td>16 + X</td></tr>
            <tr><td>Monster Scale Full-Plate (H)</td><td>5 units C+ Scales (+3 base)</td><td>32 hrs</td><td>19 + X</td></tr>
          </tbody>
        </table>
      </div>

      <h3 class="sub-title">Resistance Armours</h3>
      <div class="table-wrap">
        <table>
          <thead><tr><th>Recipe</th><th>Materials</th><th>Time</th><th>DC</th><th>Property</th></tr></thead>
          <tbody>
            <tr><td>Demon Leather / Hide / Studded</td><td>4 units B+ Demon Leather + 1 base</td><td>24 hrs</td><td>17 + X</td><td>Fire resistance</td></tr>
            <tr><td>Spirit Leather / Hide / Studded</td><td>4 units B+ Spirit Pelt + 1 base</td><td>24 hrs</td><td>17 + X</td><td>Force resistance</td></tr>
            <tr><td>Dragon Scale Mail (M)</td><td>4 units A+ Dragon Scales + 1 base</td><td>32 hrs</td><td>20 + X</td><td>+1 AC (stacks with infusions)</td></tr>
          </tbody>
        </table>
      </div>

      <h3 class="sub-title">Miscellaneous</h3>
      <div class="table-wrap">
        <table>
          <thead><tr><th>Recipe</th><th>Materials</th><th>Time</th><th>DC</th><th>Effect</th></tr></thead>
          <tbody>
            <tr><td>Dragon Scale Cloak</td><td>2 units C+ Dragon Scales</td><td>8 hrs + X</td><td>14 + X</td><td>+1 saves vs. the dragon's element (max +2)</td></tr>
            <tr><td>Dragon Scale Satchel</td><td>2 units D+ Dragon Scales</td><td>4 hrs + X</td><td>12 + X</td><td>Contents gain the dragon's elemental resistance</td></tr>
            <tr><td>Dragon Scale Climbing Claws</td><td>2 units D+ Dragon Bones</td><td>4 hrs + X</td><td>12 + X</td><td>Advantage on Athletics to climb (may mix dragon bones)</td></tr>
            <tr><td>Dragon Scale Instrument Inlay</td><td>2 units D+ Dragon Scales</td><td>4 hrs + X</td><td>12 + X</td><td>Advantage on Performance vs. opposing dragon type</td></tr>
            <tr><td>Exotic Hand Glider</td><td>2 units D+ leather + 2 units same-rank wood</td><td>15 hrs + X</td><td>15 + X</td><td>See Carpenter's Tools for glider rules</td></tr>
          </tbody>
        </table>
      </div>
      <p><em>You cannot mix scales/bones of different dragons unless their elements match. A dragon's element equals its breath weapon's damage type.</em></p>
      <p><strong>Leather Expert:</strong> advantage on Persuasion, History, Arcana, Religion, Deception, Insight, and Performance checks concerning leather (DM's discretion).</p>
    </div>

    <!-- MASON -->
    <div class="guide-section" id="mason">
      <h2 class="sec-title">Mason's Tools <span class="tag">Profession</span></h2>
      <p><strong>Requirements:</strong> Proficiency with Mason's Tools. C-Rank+ requires Workshop. Base materials for armour: Abominable Skin, Chitin, Ellond Hide, Thick Hide, Monster Scales, Bones. Weapon base materials: Bone, Coral, Obsidian.</p>
      <p>Masons craft stone furniture, exotic stone/bone weapons and armour, and Planeshift Forks. (Special armour properties for base materials are taken from Leatherworker's Tools.)</p>

      <div class="roll-box">
        <h4>Roll Outcomes</h4>
        <div class="roll-item"><span class="roll-die great">Nat 20</span><span>Refunds 50% of the materials.</span></div>
        <div class="roll-item"><span class="roll-die bad">Failure</span><span>Waste 1/3 of the prime materials (rounded down, min 1).</span></div>
        <div class="roll-item"><span class="roll-die bad">Nat 1</span><span>All materials wasted.</span></div>
      </div>

      <h3 class="sub-title">Stone Furniture</h3>
      <div class="table-wrap">
        <table>
          <thead><tr><th>Craft</th><th>Materials</th><th>Time</th><th>DC</th></tr></thead>
          <tbody>
            <tr><td>Small Furniture</td><td>12 lbs stone or 6 units exotic stone</td><td>4 hrs + X</td><td>12 + X</td></tr>
            <tr><td>Medium Furniture</td><td>30 lbs stone or 15 units exotic stone</td><td>8 hrs + X</td><td>14 + X</td></tr>
            <tr><td>Large Furniture</td><td>80 lbs stone or 20 units exotic stone</td><td>12 hrs + X</td><td>16 + X</td></tr>
            <tr><td>Huge Furniture</td><td>200 lbs stone or 100 units exotic stone</td><td>16 hrs + X</td><td>18 + X</td></tr>
            <tr><td>Custom Orders</td><td>2 lbs stone = 1g</td><td>Ask DM</td><td>Ask DM</td></tr>
          </tbody>
        </table>
      </div>

      <h3 class="sub-title">Weapons &amp; Armour</h3>
      <p><em>Each recipe also takes 1 unit of same-rank base material (2 for half-plate, 3 for full-plate).</em></p>
      <div class="table-wrap">
        <table>
          <thead><tr><th>Recipe</th><th>Prime Material</th><th>Time</th><th>DC</th></tr></thead>
          <tbody>
            <tr><td>Bone Simple Weapons</td><td>1 unit any-rank Bone</td><td>6 hrs + X</td><td>11 + X</td></tr>
            <tr><td>Bone Martial Weapons</td><td>2 units D+ Bone</td><td>12 hrs + X</td><td>13 + X</td></tr>
            <tr><td>Dragonbone Simple Weapons</td><td>1 unit any-rank Dragonbone</td><td>6 hrs + X</td><td>11 + X</td></tr>
            <tr><td>Dragonbone Martial Weapons</td><td>2 units D+ Dragonbone</td><td>12 hrs + X</td><td>13 + X</td></tr>
            <tr><td>Coral Simple Weapons</td><td>1 unit any-rank Coral</td><td>6 hrs + X</td><td>11 + X</td></tr>
            <tr><td>Coral Martial Weapons</td><td>2 units D+ Coral</td><td>12 hrs + X</td><td>13 + X</td></tr>
            <tr><td>Ignum Simple Weapons</td><td>1 unit any-rank Ignum</td><td>6 hrs + X</td><td>11 + X</td></tr>
            <tr><td>Ignum Martial Weapons</td><td>2 units C+ Ignum</td><td>12 hrs + X</td><td>13 + X</td></tr>
            <tr><td>Ignum Non-Plates (M/H)</td><td>4 units B+ Ignum</td><td>24 hrs</td><td>21</td></tr>
            <tr><td>Ignum Half-Plate (M)</td><td>6 units B+ Ignum (+2 base)</td><td>32 hrs</td><td>22</td></tr>
            <tr><td>Ignum Full-Plate (H)</td><td>7 units B+ Ignum (+3 base)</td><td>32 hrs</td><td>23</td></tr>
            <tr><td>Obsidian Simple Weapons</td><td>1 unit any-rank Obsidian</td><td>6 hrs + X</td><td>11 + X</td></tr>
            <tr><td>Obsidian Martial Weapons</td><td>2 units D+ Obsidian</td><td>12 hrs + X</td><td>13 + X</td></tr>
            <tr><td>Obsidian Non-Plates (M/H)</td><td>2 units D+ Obsidian</td><td>24 hrs</td><td>12 + X</td></tr>
            <tr><td>Obsidian Half-Plate (M)</td><td>3 units D+ Obsidian (+2 base)</td><td>32 hrs</td><td>14 + X</td></tr>
            <tr><td>Obsidian Full-Plate (H)</td><td>5 units D+ Obsidian (+3 base)</td><td>32 hrs</td><td>17 + X</td></tr>
            <tr><td>Unattuned Planeshift Fork</td><td>1 unit B+ Ignum, Coral, or Obsidian</td><td>32 hrs</td><td>13</td></tr>
          </tbody>
        </table>
      </div>

      <div class="callout">
        <strong>Material Properties</strong>
        <b>Bone:</b> +X piercing damage; any weapon can be bone (dragon bone counts).<br>
        <b>Dragon Bone:</b> +X damage of the dragon's element instead of piercing.<br>
        <b>Coral:</b> no underwater disadvantage, thrown weapons fly full range underwater, reroll 1s on underwater damage, +X thunder.<br>
        <b>Ignum:</b> armour gives fire resistance; bludgeoning weapons +X fire.<br>
        <b>Obsidian:</b> armour deals X piercing/turn to a creature you grapple; weapons +X slashing/piercing.
      </div>
      <p><strong>Expert Perks:</strong> Emergency Repairman (20% city repair reduction), Handyman (5% rent reduction), Stone Expert (advantage on social and stone-identification checks). Planeshift forks: Ignum → Elemental Fire, Coral → Elemental Water, Obsidian → Elemental Earth or Ysgard.</p>
    </div>

    <!-- PAINTER -->
    <div class="guide-section" id="painter">
      <h2 class="sec-title">Painter's Supplies <span class="tag">Profession</span></h2>
      <p><strong>Requirements:</strong> Proficiency with Painter's Supplies. C-Rank+ requires Workshop.</p>
      <p>Painters create skill-boosting Field Artworks (temporary, consumable) and Home Decorations (permanent). Each painting grants advantage and +X to a relevant skill, with a five-word statement set by the painter describing who uses it and the scenario it applies to.</p>

      <div class="roll-box">
        <h4>Roll Outcomes</h4>
        <div class="roll-item"><span class="roll-die great">Nat 20</span><span>Flash of genius — make a second copy with a different triggering statement.</span></div>
        <div class="roll-item"><span class="roll-die bad">Failure</span><span>Waste 1/3 of the prime materials (rounded down, min 1).</span></div>
        <div class="roll-item"><span class="roll-die bad">Nat 1</span><span>All materials wasted.</span></div>
      </div>

      <p><em>Every painting costs X units of any-rank herb/plant + X gallons of same-rarity blood, takes 5 hrs × X, and is DC 12 + X. The blood source determines the skill it boosts.</em></p>
      <div class="table-wrap">
        <table>
          <thead><tr><th>Painting / Diagram</th><th>Blood Source</th><th>Boosts (typical skill)</th></tr></thead>
          <tbody>
            <tr><td>Incredible Animal Picture</td><td>Beast blood</td><td>Animal Handling</td></tr>
            <tr><td>Fascinating Medicinal Diagram</td><td>Giant blood</td><td>Medicine</td></tr>
            <tr><td>Intimidating Portrayal</td><td>Monstrosity blood</td><td>Intimidation</td></tr>
            <tr><td>Body Art of Fiendish Athletics</td><td>Fiend blood</td><td>Athletics</td></tr>
            <tr><td>Weird Acrobatic Portrayal</td><td>Aberration blood</td><td>Acrobatics</td></tr>
            <tr><td>Historical Work of Art</td><td>Humanoid blood</td><td>History</td></tr>
            <tr><td>Marvelous Natural Landscapes</td><td>Plant 'blood'</td><td>Nature / Survival</td></tr>
            <tr><td>Divine Religious Iconography</td><td>Celestial blood</td><td>Religion</td></tr>
            <tr><td>Esoteric Arcane Impression</td><td>Dragon blood</td><td>Arcana</td></tr>
            <tr><td>Stealthy Fingerpainting</td><td>Ooze 'blood'</td><td>Stealth</td></tr>
            <tr><td>Stylized Investigative Chart</td><td>Giant blood</td><td>Investigation</td></tr>
            <tr><td>Insightful Abstraction</td><td>Celestial blood</td><td>Insight</td></tr>
            <tr><td>Performance Billboard</td><td>Humanoid blood</td><td>Performance</td></tr>
          </tbody>
        </table>
      </div>

      <div class="callout">
        <strong>Field Artwork vs. Home Decoration</strong>
        <b>Field Artwork:</b> grants X+1 to a related skill. Consumable — takes 1 minute to read and expires after one check or a rest. The crafter needs proficiency in the skill (helpers can aid); the user does not.<br>
        <b>Home Decoration:</b> permanent two-part item (Frame by a Carpenter + Painting by you). The Painting grants half of X (rounded down) additional uses; S-rank rounds up. Only one Home Decoration buff at a time; marvel at it 10 minutes every 24 hours to use it.
      </div>
      <p><strong>The Artist:</strong> advantage on Persuasion, History, Arcana, Religion, Deception, Insight, and Performance checks concerning art (DM's discretion).</p>
    </div>

    <!-- POTTER -->
    <div class="guide-section" id="potter">
      <h2 class="sec-title">Potter's Tools <span class="tag">Profession</span></h2>
      <p><strong>Requirements:</strong> Proficiency with Potter's Tools. C-Rank+ requires Workshop.</p>

      <h3 class="sub-title">Specialty Crafts</h3>
      <div class="table-wrap">
        <table>
          <thead><tr><th>Item</th><th>Materials</th><th>Time</th><th>DC</th><th>Effect</th></tr></thead>
          <tbody>
            <tr><td>Acoustic Speaker</td><td>20g materials or 1 E-Rank Skyshard</td><td>3 hrs</td><td>15</td><td>Advantage on Performance to shout (mouth) or Perception to hear (ear)</td></tr>
            <tr><td>Clay Thermos</td><td>20g materials or 1 E-Rank Skyshard</td><td>3 hrs</td><td>10</td><td>Keeps contents at temperature</td></tr>
            <tr><td>Trick Pot</td><td>50g materials or 2 E-Rank Skyshards</td><td>5 hrs</td><td>15</td><td>Hidden compartment; DC 12 + crafter's prof to detect</td></tr>
            <tr><td>Potter's Wheel</td><td>1 C-Rank Skyshard + 3 Chromatic Mud</td><td>24 hrs</td><td>10</td><td>Roll 1d4–2 (min 1) extra crafts when making Skyshard Pots, Det-caps, or Bombs</td></tr>
          </tbody>
        </table>
      </div>

      <h3 class="sub-title">Bombs</h3>
      <div class="table-wrap">
        <table>
          <thead><tr><th>Item</th><th>Materials</th><th>Time</th><th>DC</th><th>Yield</th></tr></thead>
          <tbody>
            <tr><td>Skyshard Pots</td><td>1 unit any-rank Skyshard + 12 lbs premium clay (5g)</td><td>12 hrs</td><td>10</td><td>6 Skyshard Pots</td></tr>
            <tr><td>Det-caps</td><td>1 unit any-rank Ignum + 3 lbs premium clay (1g)</td><td>4 hrs</td><td>10</td><td>6 Det-caps</td></tr>
            <tr><td>Sleep Bomb</td><td>3 D+ Skyshard Pots + 1 Det-cap + 1 Ghost Blossom (same rank)</td><td>6 hrs + X</td><td>13 + X</td><td>3 Sleep Bombs</td></tr>
            <tr><td>Smoke Bomb</td><td>3 D+ Skyshard Pots + 1 Det-cap + 1 same-rank exotic wood</td><td>6 hrs + X</td><td>13 + X</td><td>3 Smoke Bombs</td></tr>
            <tr><td>Explosive Bomb</td><td>3 D+ Skyshard Pots + 1 Det-cap + 1 same-rank exotic metal or stone</td><td>6 hrs + X</td><td>13 + X</td><td>3 Bombs</td></tr>
          </tbody>
        </table>
      </div>
      <div class="callout">
        <strong>Bomb Mechanics</strong>
        <b>Throw:</b> Action, 30 ft (or 60 ft with sling). No attack roll — choose a target point and it detonates.<br>
        <b>Sleep Bomb:</b> 10-ft sphere. DC 10+X Con save or unconscious for X turns.<br>
        <b>Explosive Bomb:</b> 5-ft radius per X. Xd8+2d8 damage of the material's type. DC 13+X Dex save for half.<br>
        <b>Smoke Bomb:</b> 10-ft radius (min), lasts 1+X turns. Material determines additional effects (Deadwood = blinding, Summitwood = slow movement, etc.)
      </div>
    </div>

    <!-- SMITH -->
    <div class="guide-section" id="smith">
      <h2 class="sec-title">Smith's Tools <span class="tag">Profession</span></h2>
      <p><strong>Requirements:</strong> Proficiency with Smith's Tools. C-Rank+ requires Workshop. Smiths do NOT craft bows or crossbows. Uses Prime/Base material system.</p>
      <p><strong>Armour Base Materials:</strong> Abominable Skin, Chitin, Ellond Hide, Thick Hide, Monster Scales, Bones.<br><strong>Weapon Base Materials:</strong> Adamantine, Cold Iron, Mithril.</p>

      <h3 class="sub-title">Exotic Metal Properties</h3>
      <div class="table-wrap">
        <table>
          <thead><tr><th>Metal</th><th>Armour Effect</th><th>Weapon Effect</th></tr></thead>
          <tbody>
            <tr><td>Adamantine</td><td>Crits against you become normal hits. Double weight.</td><td>Auto-crit against objects.</td></tr>
            <tr><td>Cold Iron</td><td>Up to 3×/day add +X to AC or save vs. fey/fiend attacks.</td><td>Advantage on damage rolls vs. fey/fiends.</td></tr>
            <tr><td>Fellsteel</td><td>Necrotic resistance.</td><td>+X necrotic damage; can convert all damage to necrotic.</td></tr>
            <tr><td>Mithril</td><td>No stealth disadvantage, no STR requirement, half weight.</td><td>Two-handed weapons usable by small creatures; all weapons gain Light. +X damage when off-hand free.</td></tr>
            <tr><td>Moonsteel</td><td>Lightning resistance.</td><td>+X lightning damage; can convert all damage to lightning.</td></tr>
            <tr><td>Bloodmetal</td><td>Fire resistance.</td><td>+X fire damage; can convert all damage to fire.</td></tr>
            <tr><td>Orichalcum</td><td>Force resistance.</td><td>+X force damage; can convert all damage to force.</td></tr>
            <tr><td>Plaguesteel</td><td>Poison resistance.</td><td>+X poison damage; can convert all damage to poison.</td></tr>
            <tr><td>Sunsteel</td><td>Radiant resistance.</td><td>+X radiant damage; can convert all damage to radiant.</td></tr>
          </tbody>
        </table>
      </div>

      <div class="roll-box">
        <h4>Roll Outcomes</h4>
        <div class="roll-item"><span class="roll-die great">Nat 20</span><span>Reactivate the base material (or refund half the materials if there's no base).</span></div>
        <div class="roll-item"><span class="roll-die bad">Failure</span><span>Waste 1/3 of the prime materials (rounded down, min 1).</span></div>
        <div class="roll-item"><span class="roll-die bad">Nat 1</span><span>All materials wasted.</span></div>
      </div>

      <h3 class="sub-title">Services &amp; Ironsmithing</h3>
      <div class="table-wrap">
        <table>
          <thead><tr><th>Craft</th><th>Materials</th><th>Time</th><th>DC</th></tr></thead>
          <tbody>
            <tr><td>Silver Simple Weapons</td><td>Base weapon + 100g</td><td>4 hrs</td><td>13</td></tr>
            <tr><td>Silver Martial Weapons</td><td>Base weapon + 100g</td><td>8 hrs</td><td>15</td></tr>
            <tr><td>Simple Weapons</td><td>½ item's market value in iron/gp</td><td>2 hrs</td><td>10</td></tr>
            <tr><td>Martial Weapons</td><td>½ item's market value in iron/gp</td><td>6 hrs</td><td>12</td></tr>
            <tr><td>Metallic Non-Plates</td><td>½ item's market value in iron/gp</td><td>8 hrs</td><td>12</td></tr>
            <tr><td>Metallic Half-Plate</td><td>½ value in iron/gp, crafter D+</td><td>24 hrs</td><td>14</td></tr>
            <tr><td>Metallic Full-Plate</td><td>½ value in iron/gp, crafter C+</td><td>32 hrs</td><td>17</td></tr>
          </tbody>
        </table>
      </div>

      <h3 class="sub-title">Exotic Armoursmithing</h3>
      <p><em>Non-Plate / Half-Plate / Full-Plate take +1 / +2 / +3 units of same-rank base material respectively.</em></p>
      <div class="table-wrap">
        <table>
          <thead><tr><th>Recipe</th><th>Prime Material</th><th>Time</th><th>DC</th></tr></thead>
          <tbody>
            <tr><td>Adamantine Non-Plates</td><td>3 units C+ Adamantine</td><td>12 hrs</td><td>14</td></tr>
            <tr><td>Adamantine Half-Plate</td><td>4 units C+ Adamantine</td><td>14 hrs</td><td>16</td></tr>
            <tr><td>Adamantine Full-Plate</td><td>5 units C+ Adamantine</td><td>32 hrs</td><td>19</td></tr>
            <tr><td>Cold Iron Non-Plates</td><td>3 units D+ Cold Iron</td><td>12 hrs</td><td>14</td></tr>
            <tr><td>Cold Iron Half-Plate</td><td>4 units D+ Cold Iron</td><td>14 hrs</td><td>16</td></tr>
            <tr><td>Cold Iron Full-Plate</td><td>5 units D+ Cold Iron</td><td>32 hrs</td><td>19</td></tr>
            <tr><td>Mithril Non-Plates</td><td>3 units D+ Mithril</td><td>12 hrs</td><td>14</td></tr>
            <tr><td>Mithril Half-Plate</td><td>4 units D+ Mithril</td><td>14 hrs</td><td>16</td></tr>
            <tr><td>Mithril Full-Plate</td><td>5 units D+ Mithril</td><td>32 hrs</td><td>19</td></tr>
          </tbody>
        </table>
      </div>

      <h3 class="sub-title">Resistance Armours</h3>
      <p><em>Applies to Fellsteel, Moonsteel, Bloodmetal, Orichalcum, Plaguesteel, and Sunsteel (resistance per the property table above).</em></p>
      <div class="table-wrap">
        <table>
          <thead><tr><th>Recipe</th><th>Prime Material</th><th>Time</th><th>DC</th></tr></thead>
          <tbody>
            <tr><td>Non-Plates</td><td>4 units B+ metal (+1 base)</td><td>24 hrs</td><td>17 + X</td></tr>
            <tr><td>Half-Plate</td><td>5 units B+ metal (+2 base)</td><td>32 hrs</td><td>18 + X</td></tr>
            <tr><td>Full-Plate</td><td>6 units B+ metal (+3 base)</td><td>32 hrs</td><td>19 + X</td></tr>
          </tbody>
        </table>
      </div>

      <h3 class="sub-title">Exotic Melee Weaponsmithing</h3>
      <div class="table-wrap">
        <table>
          <thead><tr><th>Recipe</th><th>Prime Material</th><th>Time</th><th>DC</th></tr></thead>
          <tbody>
            <tr><td>Adamantine Simple</td><td>1 unit any-rank Adamantine (+1 base)</td><td>6 hrs</td><td>13</td></tr>
            <tr><td>Adamantine Martial</td><td>2 units C+ Adamantine (+1 base)</td><td>12 hrs</td><td>15</td></tr>
            <tr><td>Cold Iron / Mithril Simple</td><td>1 unit any-rank metal (+1 base)</td><td>6 hrs</td><td>13</td></tr>
            <tr><td>Cold Iron / Mithril Martial</td><td>2 units D+ metal (+1 base)</td><td>12 hrs</td><td>15</td></tr>
            <tr><td>Fellsteel / Moonsteel / Bloodmetal / Orichalcum / Plaguesteel / Sunsteel Simple</td><td>1 unit any-rank metal (+1 base)</td><td>6 hrs</td><td>13</td></tr>
            <tr><td>…Martial</td><td>2 units C+ metal (+1 base)</td><td>12 hrs</td><td>15</td></tr>
            <tr><td>Unattuned Planeshift Fork</td><td>1 unit B+ of any exotic metal</td><td>32 hrs</td><td>13</td></tr>
          </tbody>
        </table>
      </div>

      <div class="callout">
        <strong>Recycler Perk</strong>
        Convert looted equipment into 75% of its market value in raw iron for crafting. Pure Iron Ore applies at full value. No check or crafting time needed.
      </div>
      <p><strong>Metallurgic Expert:</strong> advantage on Persuasion, History, Arcana, Religion, Deception, Insight, and Performance checks concerning iron and steel (DM's discretion). Planeshift forks tune by metal: Adamantine → a specific demi-plane, Bloodmetal → Gehenna/Nine Hells, Cold Iron → Acheron/the Abyss, Fellsteel → Limbo, Mithril → Material Plane, Moonsteel → Bytopia/Elysium/Mount Celestia, Orichalcum → Ethereal/Astral/Outlands, Plaguesteel → Shadowfell/Carceri/Hades, Sunsteel → Mechanus/Arcadia.</p>
    </div>

    <!-- WEAVER -->
    <div class="guide-section" id="weaver">
      <h2 class="sec-title">Weaver's Tools <span class="tag">Profession</span></h2>
      <p><strong>Requirements:</strong> Proficiency with Weaver's Tools. C-Rank+ requires Workshop. Base materials: Leafweave, Spidersilk.</p>

      <div class="table-wrap">
        <table>
          <thead><tr><th>Material</th><th>Clothing Effect</th><th>Armour Effect</th><th>Special</th></tr></thead>
          <tbody>
            <tr><td>Leafweave</td><td>Advantage on stealth in forests/jungles</td><td>+1 save vs. piercing + reaction to reduce Xd4 piercing (once/long rest)</td><td>No effect under other armour</td></tr>
            <tr><td>Heavenweave</td><td>Radiant resistance</td><td>Radiant resistance</td><td>Hand & Shin Wraps: unarmed strikes deal +½X radiant</td></tr>
            <tr><td>Shadowsilk</td><td>Psychic resistance</td><td>Psychic resistance</td><td>Hand & Shin Wraps: unarmed strikes deal +½X psychic</td></tr>
            <tr><td>Spidersilk</td><td>+X passive/active Perception vs. pickpockets</td><td>Half weight; B+ light armour = +1 AC; B+ medium = apply DEX up to +X (not just +2)</td><td>Reaction: reduce Xd4 poison (once/long rest)</td></tr>
          </tbody>
        </table>
      </div>

      <div class="roll-box">
        <h4>Roll Outcomes</h4>
        <div class="roll-item"><span class="roll-die great">Nat 20</span><span>Reactivate base material; if none, refund 1 unit or increase the item's value by 50%.</span></div>
        <div class="roll-item"><span class="roll-die bad">Failure</span><span>Waste 1/3 of the prime materials (rounded down, min 1).</span></div>
        <div class="roll-item"><span class="roll-die bad">Nat 1</span><span>All materials wasted.</span></div>
      </div>

      <div class="table-wrap">
        <table>
          <thead><tr><th>Recipe</th><th>Materials</th><th>Time</th><th>DC</th></tr></thead>
          <tbody>
            <tr><td>Any PhB cloth/textile item</td><td>½ item's market value in gold</td><td>4 hrs</td><td>10</td></tr>
            <tr><td>Exquisite Wall Rug</td><td>10g common weave or 1 unit any exotic weave/silk</td><td>32 hrs</td><td>20 + X</td></tr>
            <tr><td>Leafweave Clothing (No AC)</td><td>3 units D+ Leafweave</td><td>8 hrs + X</td><td>10 + X</td></tr>
            <tr><td>Leafweave Armour (L/M)</td><td>3 units D+ Leafweave</td><td>12 hrs + X</td><td>12 + X</td></tr>
            <tr><td>Spidersilk Clothing (No AC)</td><td>3 units D+ Spidersilk</td><td>8 hrs + X</td><td>10 + X</td></tr>
            <tr><td>Spidersilk Armour (L/M)</td><td>3 units D+ Spidersilk</td><td>12 hrs + X</td><td>12 + X</td></tr>
            <tr><td>Heavenweave Clothing / Armour</td><td>4 units B+ Heavenweave + 1 base</td><td>24 hrs</td><td>17 + X</td></tr>
            <tr><td>Heavenweave Wraps</td><td>2 units D+ Heavenweave</td><td>12 hrs</td><td>13 + X</td></tr>
            <tr><td>Shadowsilk Clothing / Armour</td><td>4 units B+ Shadowsilk + 1 base</td><td>24 hrs</td><td>17 + X</td></tr>
            <tr><td>Shadowsilk Wraps</td><td>2 units D+ Shadowsilk</td><td>12 hrs</td><td>13 + X</td></tr>
          </tbody>
        </table>
      </div>

      <div class="callout info">
        <strong>Exquisite Wall Rugs</strong>
        Elaborate trade goods worth +X to Persuasion when bartering with them. Values by weave rank: Common 100g · E 150g · D 750g · C 1,500g · B 4,250g · A 6,000g · S 22,400g (DM's discretion). Each rug weighs 20 lbs.
      </div>
    </div>

    <!-- WOODCARVER -->
    <div class="guide-section" id="woodcarver">
      <h2 class="sec-title">Woodcarver's Tools <span class="tag">Profession</span></h2>
      <p><strong>Requirements:</strong> Proficiency with Woodcarver's Tools. C-Rank+ requires Workshop. Base materials for arrows/weapons: Darkwood, Deadwood, Summitwood.</p>
      <p>Woodcarvers craft arrows, ranged weapons, exotic wood armour, and Planeshift Forks. Exotic arrows convert <em>all</em> their damage to the prime material's type (e.g., red dragonbone arrows deal all fire, not just extra).</p>

      <div class="callout info">
        <strong>Mithril Arrows</strong>
        No disadvantage when shooting at long range.
      </div>

      <div class="table-wrap">
        <table>
          <thead><tr><th>Recipe</th><th>Yield</th><th>Materials</th><th>Time</th><th>DC</th></tr></thead>
          <tbody>
            <tr><td>Signal Arrows</td><td>1</td><td>5g materials</td><td>6 hrs</td><td>12</td></tr>
            <tr><td>Standard Arrows/Bolts</td><td>×60</td><td>5g iron/wood</td><td>8 hrs</td><td>10</td></tr>
            <tr><td>Flight Arrows/Bolts</td><td>×30</td><td>1 unit D+ Darkwood</td><td>8 hrs</td><td>10</td></tr>
            <tr><td>Exotic Arrows – Common</td><td>×6</td><td>1 E-Rank prime + 1 E-Rank base</td><td>4 hrs</td><td>10</td></tr>
            <tr><td>Exotic Arrows – Uncommon</td><td>×60</td><td>1 D-Rank prime + 1 D-Rank base</td><td>8 hrs</td><td>12</td></tr>
            <tr><td>Exotic Arrows – Rare</td><td>×60</td><td>1 C-Rank prime + 1 C-Rank base</td><td>10 hrs</td><td>14</td></tr>
            <tr><td>Exotic Arrows – Rare+</td><td>×70</td><td>1 B-Rank prime + 1 B-Rank base</td><td>12 hrs</td><td>16</td></tr>
            <tr><td>Exotic Arrows – Very Rare</td><td>×100</td><td>1 A-Rank prime + 1 A-Rank base</td><td>14 hrs</td><td>18</td></tr>
            <tr><td>Exotic Arrows – Legendary</td><td>×280</td><td>1 S-Rank prime + 1 S-Rank base</td><td>16 hrs</td><td>20</td></tr>
          </tbody>
        </table>
      </div>

      <h3 class="sub-title">Carves &amp; Ranged Weapons</h3>
      <div class="table-wrap">
        <table>
          <thead><tr><th>Recipe</th><th>Materials</th><th>Time</th><th>DC</th></tr></thead>
          <tbody>
            <tr><td>Any PhB wood item</td><td>½ item's market value in gold</td><td>4 hrs</td><td>10</td></tr>
            <tr><td>Custom Carve (&lt;400g)</td><td>½ item's market value in gold</td><td>8 hrs</td><td>13</td></tr>
            <tr><td>Custom Carve (401–1,000g)</td><td>½ item's market value in gold</td><td>16 hrs</td><td>17</td></tr>
            <tr><td>Custom Carve (1,000–5,000g)</td><td>½ item's market value in gold</td><td>32 hrs</td><td>20</td></tr>
            <tr><td>Skyshard Ranged Weapon</td><td>2 units D+ Skyshard + 1 base</td><td>16 hrs</td><td>15 + X</td></tr>
            <tr><td>Eternal Ice Ranged Weapon</td><td>2 units D+ Eternal Ice + 1 base</td><td>16 hrs</td><td>15 + X</td></tr>
            <tr><td>Obsidian Ranged Weapon</td><td>2 units D+ Obsidian + 1 base</td><td>16 hrs</td><td>15 + X</td></tr>
            <tr><td>Dragon Bone Ranged Weapon</td><td>2 units D+ Dragon Bone + 1 base</td><td>16 hrs</td><td>15 + X</td></tr>
            <tr><td>Sun Steel Ranged Weapon</td><td>2 units D+ Sunsteel + 1 base</td><td>16 hrs</td><td>15 + X</td></tr>
            <tr><td>Unattuned Planeshift Fork</td><td>1 unit B+ Darkwood</td><td>32 hrs</td><td>13</td></tr>
          </tbody>
        </table>
      </div>
      <p><em>Ranged weapon bonus damage on hit: Skyshard +X Lightning · Eternal Ice +X Cold · Dragon Bone +X Fire · Obsidian +X Piercing · Sun Steel +X Radiant. Darkwood forks tune to Arboria, the Beastlands, or the Feywild.</em></p>

      <h3 class="sub-title">Exotic Wood Armour</h3>
      <div class="table-wrap">
        <table>
          <thead><tr><th>Recipe</th><th>Materials</th><th>Time</th><th>DC</th></tr></thead>
          <tbody>
            <tr><td>Exotic Wood Non-Plates (L/M/H)</td><td>4 units D+ exotic wood + 1 base</td><td>16 hrs</td><td>17 + X</td></tr>
            <tr><td>Exotic Wood Half-Plate (M)</td><td>5 units D+ exotic wood + 2 base</td><td>24 hrs</td><td>18 + X</td></tr>
            <tr><td>Exotic Wood Full-Plate (H)</td><td>6 units C+ exotic wood + 3 base</td><td>32 hrs</td><td>19 + X</td></tr>
            <tr><td>Deadwood Non-Plates (L/M/H)</td><td>4 units B+ Deadwood + 3 base</td><td>24 hrs</td><td>17 + X</td></tr>
            <tr><td>Deadwood Half-Plate (M)</td><td>5 units B+ Deadwood + 3 base</td><td>32 hrs</td><td>18 + X</td></tr>
            <tr><td>Deadwood Full-Plate (H)</td><td>6 units B+ Deadwood + 3 base</td><td>32 hrs</td><td>19 + X</td></tr>
            <tr><td>Summitwood Non-Plates (L/M/H)</td><td>4 units B+ Summitwood + 3 base</td><td>24 hrs</td><td>17 + X</td></tr>
            <tr><td>Summitwood Half-Plate (M)</td><td>5 units B+ Summitwood + 3 base</td><td>32 hrs</td><td>18 + X</td></tr>
            <tr><td>Summitwood Full-Plate (H)</td><td>6 units B+ Summitwood + 3 base</td><td>32 hrs</td><td>19 + X</td></tr>
          </tbody>
        </table>
      </div>

      <div class="callout">
        <strong>Wood Armour &amp; Arrow Notes</strong>
        All wood armour is half PhB weight and flame-retardant. <b>Darkwood:</b> can use literally any exotic material as its base (Deadwood/Summitwood bases grant no resistance). <b>Deadwood:</b> acid resistance. <b>Summitwood:</b> cold resistance. <b>Ironwood:</b> 5× weight, disadvantage on Dex saves, but +5×X Max HP and +1 AC at B-rank (+2 at S-rank).<br>
        <b>Flight Arrows:</b> increase a weapon's normal and long range by 25% per X (lost on impact). <b>Signal Arrows:</b> heard up to 500 ft (passive Perception 10, +1 DC per 100 ft beyond).
      </div>
      <p><strong>Expert Perks:</strong> <em>Woodmaster</em> — advantage on social checks concerning wood (DM's discretion). <em>Woodcarver Weaponmaster</em> — if you're proficient with a woodcarver-made ranged weapon (yours or another's), you deal +1 damage with it.</p>
    </div>

    <!-- HERBALISM -->
    <div class="guide-section" id="herbalism">
      <h2 class="sec-title">Herbalism Kit <span class="tag">Profession</span></h2>
      <p><strong>Requirements:</strong> Proficiency with Herbalism Kit. Rare and Very Rare potions require a Workshop. No gold cost — just have the herbs.</p>

      <div class="roll-box">
        <h4>Roll Outcomes</h4>
        <div class="roll-item"><span class="roll-die great">Nat 20</span><span>Gain 1 extra potion.</span></div>
        <div class="roll-item"><span class="roll-die bad">Failure</span><span>Waste 1/3 of your exotic materials (rounded down, min 1, most expensive first).</span></div>
        <div class="roll-item"><span class="roll-die bad">Nat 1</span><span>All materials wasted.</span></div>
      </div>

      <div class="card-grid">
        <div class="card common">
          <div class="card-name">Antitoxin</div>
          <div class="card-meta"><span class="badge common">Common</span><span class="badge">DC 7</span></div>
          <div class="card-ing"><strong>Ingredients:</strong> Ellond Scrub ×1 + any combo of Kreen Paste, Ellond Scrub, Blue Herb</div>
          <div class="card-effect">Advantage on saves vs. poison for 1 hour.</div>
          <div class="card-stats"><div class="stat-block"><span>Time</span><span class="val">1 hr</span></div><div class="stat-block"><span>Value</span><span class="val">50g</span></div></div>
        </div>
        <div class="card common">
          <div class="card-name">Potion of Healing</div>
          <div class="card-meta"><span class="badge common">Common</span><span class="badge">DC 8</span></div>
          <div class="card-ing"><strong>Ingredients:</strong> Kreen Paste, Ellond Scrub, or Blue Herb ×1+</div>
          <div class="card-effect">Heal 2d4+2 HP.</div>
          <div class="card-stats"><div class="stat-block"><span>Time</span><span class="val">2 hrs</span></div><div class="stat-block"><span>Value</span><span class="val">50g</span></div></div>
        </div>
        <div class="card uncommon">
          <div class="card-name">Potion of Greater Healing</div>
          <div class="card-meta"><span class="badge uncommon">Uncommon</span><span class="badge">DC 10</span></div>
          <div class="card-ing"><strong>Ingredients:</strong> Kreen Paste ×1 + any combo of Kreen Paste, Ellond Scrub, Blue Herb</div>
          <div class="card-effect">Heal 4d4+4 HP (or double crafter's proficiency modifier, whichever is higher).</div>
          <div class="card-stats"><div class="stat-block"><span>Time</span><span class="val">4 hrs</span></div><div class="stat-block"><span>Value</span><span class="val">100g</span></div></div>
        </div>
        <div class="card common">
          <div class="card-name">Willowshade Oil</div>
          <div class="card-meta"><span class="badge common">Common</span><span class="badge">DC 8</span></div>
          <div class="card-ing"><strong>Ingredients:</strong> Blue Herb ×1</div>
          <div class="card-effect">Apply to a petrified creature (petrified &lt;1 min) to end the condition at the start of their next turn.</div>
          <div class="card-stats"><div class="stat-block"><span>Time</span><span class="val">1 hr</span></div><div class="stat-block"><span>Value</span><span class="val">30g</span></div></div>
        </div>
        <div class="card rare">
          <div class="card-name">Potion of Superior Healing</div>
          <div class="card-meta"><span class="badge rare">Rare</span><span class="badge">DC 15</span></div>
          <div class="card-ing"><strong>Ingredients:</strong> Spineflower Berries ×4 + any healing herbs</div>
          <div class="card-effect">Heal 8d4+8 HP (or 2× crafter's proficiency modifier, whichever is higher).</div>
          <div class="card-stats"><div class="stat-block"><span>Time</span><span class="val">8 hrs</span></div><div class="stat-block"><span>Value</span><span class="val">1,000g</span></div></div>
        </div>
        <div class="card veryrare">
          <div class="card-name">Potion of Supreme Healing</div>
          <div class="card-meta"><span class="badge veryrare">Very Rare</span><span class="badge">DC 20</span></div>
          <div class="card-ing"><strong>Ingredients:</strong> Viping Vitalis ×4 + any healing herbs</div>
          <div class="card-effect">Heal 10d4+20 HP (or 4× crafter's proficiency modifier, whichever is higher).</div>
          <div class="card-stats"><div class="stat-block"><span>Time</span><span class="val">16 hrs</span></div><div class="stat-block"><span>Value</span><span class="val">10,000g</span></div></div>
        </div>
      </div>
      <p><strong>Herbalist:</strong> advantage on Persuasion, History, Arcana, Religion, Deception, Insight, and Performance checks concerning plants (DM's discretion).</p>
    </div>

    <!-- FORGERY -->
    <div class="guide-section" id="forgery">
      <h2 class="sec-title">Forgery Kit <span class="tag">Profession</span></h2>
      <p><strong>Requirements:</strong> Proficiency with Forgery Kit. C-Rank+ requires Workshop. Class features like Reliable Talent or Silvery Tongue cannot be used with forgery products.</p>
      <p><strong>Important:</strong> You can only use Altered Orders, Capital Gains, or False Progress once each per adventure — not all three.</p>

      <div class="table-wrap">
        <table>
          <thead><tr><th>Document</th><th>Effect</th><th>Check Required</th><th>Penalty on Failure</th></tr></thead>
          <tbody>
            <tr><td><strong>Altered Orders</strong></td><td>Convert a failed mission into a mild success (+1 progress for you + X allies)</td><td>Deception vs. quest giver Passive Insight 14 + (3 per rank above D)</td><td>Fine equal to quest gold reward for you and named allies</td></tr>
            <tr><td><strong>Capital Gains ×10</strong></td><td>Increase quest reward by 25%</td><td>Deception vs. quest giver Passive Insight 12 + (2 per rank above E)</td><td>Fine equal to quest reward for you and named allies</td></tr>
            <tr><td><strong>Official Resource Exchange ×2</strong></td><td>Swap an unwanted exotic material for one of equal rank at merchant</td><td>Deception vs. merchant Passive Insight 12 + (2 per rank above E)</td><td>Fine equal to material value</td></tr>
            <tr><td><strong>False Progress</strong></td><td>Add 1 extra progress point when you only received 1</td><td>Sleight of Hand vs. quest giver Passive Perception 16 + (2 per rank above D)</td><td>Lose the earned point AND one extra</td></tr>
            <tr><td><strong>Fool's Gold (100 coins)</strong></td><td>Functions as real gold outside The City</td><td>Persuasion/Deception vs. NPC Insight</td><td>250g fine in the City; don't carry more than 100 pieces</td></tr>
          </tbody>
        </table>
      </div>

      <div class="callout info">
        <strong>Official Resource Exchange &amp; Custom Forgeries</strong>
        The document's rank equals the rank of herbs/plants used to craft it. Bloods and meats can be traded for other exotic materials at a 5:1 ratio (mix/match same rarity by equal market value). <em>Custom Forgeries</em> (fake IDs, maps, contracts, scrolls, seals, etc.) need no library — the DM sets their time and DC.
      </div>
      <p><strong>Master Forger:</strong> advantage on Persuasion, History, Arcana, Religion, Deception, Insight, and Performance checks concerning deception (DM's discretion).</p>
    </div>

    <!-- DISGUISE -->
    <div class="guide-section" id="disguise">
      <h2 class="sec-title">Disguise Kit <span class="tag">Profession</span></h2>
      <p><strong>Requirements:</strong> Proficiency with Disguise Kit.</p>

      <div class="table-wrap">
        <table>
          <thead><tr><th>Item</th><th>Materials</th><th>Time</th><th>DC</th><th>Effect</th></tr></thead>
          <tbody>
            <tr><td>Feign Death Kit ×2</td><td>1 gallon blood + 1 D-Rank Ellond Hide</td><td>1 hr</td><td>13</td><td>Emergency Reaction: fake death (Performance/Deception vs. target's Insight)</td></tr>
            <tr><td>Feign Blight Kit ×3</td><td>1 gallon blood + 1 D-Rank Ellond Hide</td><td>1 hr</td><td>13</td><td>Emergency Reaction: fake a horrific disease</td></tr>
            <tr><td>False Casting</td><td>Spellcasting focus + spell materials + library</td><td>8 hrs</td><td>—</td><td>Prepare 2 false spells; fake-cast as bonus action (Performance/Deception vs. target Passive Insight)</td></tr>
            <tr><td>False Aura</td><td>1 unit any-rank Orichalcum</td><td>12 hrs</td><td>—</td><td>Sprinkle on object to fake or alter its magical aura (DC 10 + Performance mod + X to detect)</td></tr>
          </tbody>
        </table>
      </div>
      <p><em>All Emergency Reactions are the same resource — using one prevents using others until a short or long rest.</em></p>
      <p><strong>Master of Disguise:</strong> advantage on Persuasion, History, Arcana, Religion, Deception, Insight, and Performance checks concerning appearance (DM's discretion).</p>
    </div>

    <!-- POISONER -->
    <div class="guide-section" id="poisoner">
      <h2 class="sec-title">Poisoner's Kit <span class="tag">Profession</span></h2>
      <p><strong>Requirements:</strong> Proficiency with Poisoner's Kit. C-Rank+ requires Workshop (or Poisoner Feat to craft in the field). Poisoner Feat also halves crafting time when using a Workshop.</p>

      <div class="roll-box">
        <h4>Roll Outcomes</h4>
        <div class="roll-item"><span class="roll-die great">Nat 20</span><span>Gain 1 extra poison.</span></div>
        <div class="roll-item"><span class="roll-die bad">Failure</span><span>Waste 1/3 of prime materials (min 1) AND you accidentally poison yourself!</span></div>
        <div class="roll-item"><span class="roll-die bad">Nat 1</span><span>All materials wasted.</span></div>
      </div>

      <div class="card-grid">
        <div class="card common">
          <div class="card-name">Poison, Basic (Injury)</div>
          <div class="card-meta"><span class="badge common">Common</span><span class="badge">DC 12</span></div>
          <div class="card-ing"><strong>Ingredients:</strong> Blood Herbs ×3</div>
          <div class="card-effect">Coat 1 weapon or 3 ammo. Target hit takes +1d4 poison damage. Lasts 1 minute.</div>
          <div class="card-stats"><div class="stat-block"><span>Time</span><span class="val">2 hrs</span></div></div>
        </div>
        <div class="card common">
          <div class="card-name">Potion of Poison (Ingested)</div>
          <div class="card-meta"><span class="badge common">Common</span><span class="badge">DC 12</span></div>
          <div class="card-ing"><strong>Ingredients:</strong> Blood Herbs ×2, Blue Herbs ×1</div>
          <div class="card-effect">Looks like a healing potion. Takes 3d6 poison damage + DC 13 Con or poisoned (3d6/turn, reduces by 1d6 per successful save).</div>
          <div class="card-stats"><div class="stat-block"><span>Time</span><span class="val">8 hrs</span></div></div>
        </div>
        <div class="card uncommon">
          <div class="card-name">Assassin's Blood (Ingested)</div>
          <div class="card-meta"><span class="badge uncommon">Uncommon</span><span class="badge">DC 13</span></div>
          <div class="card-ing"><strong>Ingredients:</strong> Corpse Flower ×1</div>
          <div class="card-effect">DC 10 Con save or 1d12 poison damage + poisoned for 24 hours.</div>
          <div class="card-stats"><div class="stat-block"><span>Time</span><span class="val">4 hrs</span></div></div>
        </div>
        <div class="card uncommon">
          <div class="card-name">Burnt Othur Fumes (Inhaled)</div>
          <div class="card-meta"><span class="badge uncommon">Uncommon</span><span class="badge">DC 15</span></div>
          <div class="card-ing"><strong>Ingredients:</strong> Othur Stalk ×3</div>
          <div class="card-effect">DC 13 Con or 3d6 poison damage; repeat each turn. Ends after 3 successful saves.</div>
          <div class="card-stats"><div class="stat-block"><span>Time</span><span class="val">8 hrs</span></div></div>
        </div>
        <div class="card rare">
          <div class="card-name">Sleeping Gas (Inhaled)</div>
          <div class="card-meta"><span class="badge rare">Rare</span><span class="badge">DC 16</span></div>
          <div class="card-ing"><strong>Ingredients:</strong> Ghost Blossom ×1</div>
          <div class="card-effect">DC 15 Con or unconscious for 8 hours (ends if damaged or shaken).</div>
          <div class="card-stats"><div class="stat-block"><span>Time</span><span class="val">12 hrs</span></div></div>
        </div>
        <div class="card rare">
          <div class="card-name">Truth Serum (Ingested)</div>
          <div class="card-meta"><span class="badge rare">Rare</span><span class="badge">DC 14</span></div>
          <div class="card-ing"><strong>Ingredients:</strong> Chromatic Mud ×1</div>
          <div class="card-effect">DC 16 Con or can't knowingly lie for 1 hour (Zone of Truth effect).</div>
          <div class="card-stats"><div class="stat-block"><span>Time</span><span class="val">2 hrs</span></div></div>
        </div>
        <div class="card rare">
          <div class="card-name">Blackout Powder (Contact)</div>
          <div class="card-meta"><span class="badge rare">Rare</span><span class="badge">DC 16</span></div>
          <div class="card-ing"><strong>Ingredients:</strong> Xeni Leaves ×1</div>
          <div class="card-effect">Blow a 10-ft cone. DC 15 Con or poisoned + blinded for 1 hour. Eyes-closed doesn't help.</div>
          <div class="card-stats"><div class="stat-block"><span>Time</span><span class="val">12 hrs</span></div></div>
        </div>
        <div class="card rare">
          <div class="card-name">Psychedelic Decoction (Ingested)</div>
          <div class="card-meta"><span class="badge rare">Rare</span><span class="badge">DC 16</span></div>
          <div class="card-ing"><strong>Ingredients:</strong> Korin's Fang ×1, Ghost Blossom ×1</div>
          <div class="card-effect">DC 15 Con or incapacitated for 2d4 hours on a fantastical spiritual journey.</div>
          <div class="card-stats"><div class="stat-block"><span>Time</span><span class="val">12 hrs</span></div></div>
        </div>
      </div>

      <div class="callout">
        <strong>Variable Rarity Poisons (Creature Venom)</strong>
        Craft poisons from harvested venom glands. Craft DC = poison's save DC + 3 (or +5 for specialized toxins). The poison replicates the creature's original effect. Paralytic Balm, Spider Bite, Venom, Sensory Decay, and Specialized Toxins all use this framework.
      </div>

      <div class="callout info">
        <strong>Blood Poisons</strong>
        Adding non-humanoid blood worth at least half the total material cost (equal or higher rank) grants 1d4–2 (min 1) extra doses and reduces the craft DC by 5. Roll only once for duplication when using a bench.
      </div>

      <h3 class="sub-title">Special Crafts</h3>
      <div class="table-wrap">
        <table>
          <thead><tr><th>Item</th><th>Materials</th><th>Time</th><th>DC</th><th>Effect</th></tr></thead>
          <tbody>
            <tr><td>Plague Doctor's Mask</td><td>1 D+ Deadwood + 1 same-rank Plaguesteel</td><td>8 hrs</td><td>16</td><td>Hold breath to ignore non-magical Inhaled poisons of rank ≤ the mask's materials</td></tr>
            <tr><td>Malice Cube</td><td>3 units C+ Plaguesteel + 6 units same-rank Blood</td><td>8 hrs</td><td>16 + X</td><td>Change a poison's damage type to poison or necrotic; +X to its save DC (once)</td></tr>
          </tbody>
        </table>
      </div>
      <p><strong>Master Poisoner:</strong> advantage on Persuasion, History, Arcana, Religion, Deception, Insight, and Performance checks concerning poison (DM's discretion).</p>
    </div>


    <!-- ══════════════════════════════════════════════ -->
    <!-- ADVANCED -->
    <!-- ══════════════════════════════════════════════ -->

    <div class="guide-section" id="interdisciplinary">
      <h2 class="sec-title">Interdisciplinary Crafts <span class="tag">Advanced</span></h2>
      <p>These crafts require multiple crafter proficiencies. When working in pairs, one crafter rolls while the other aids (granting advantage). Solo crafters double the work hours.</p>

      <div class="table-wrap">
        <table>
          <thead><tr><th>Craft</th><th>Materials</th><th>Time</th><th>DC</th><th>Effect</th></tr></thead>
          <tbody>
            <tr><td>Exotic Elemental Shield</td><td>3 units C+ same-element exotic material + a shield</td><td>10 hrs</td><td>15 + X</td><td>Once per turn, reduce damage of that element from one source by ½X (rounded up). Nat 20 on craft = increase X by 1.</td></tr>
          </tbody>
        </table>
      </div>
      <p>Only non-physical elements qualify (e.g., Eternal Ice, Dragon Bones/Scales). The reduction applies after saving throws and resistances.</p>
    </div>

    <div class="guide-section" id="repair">
      <h2 class="sec-title">Item Repair <span class="tag">Advanced</span></h2>
      <p>Non-magical weapons, armour, shields, and tools can be damaged in play. A character proficient with the appropriate crafting tool can repair them.</p>

      <div class="callout">
        <strong>Repair Rules</strong>
        <b>Cost:</b> 50% of the prime material cost to craft a new item of the same type.<br>
        <b>Time:</b> Half the normal crafting time.<br>
        <b>On Success:</b> Item fully restored. <b>On Failure:</b> Materials consumed, item still damaged (can retry).
      </div>

      <div class="repair-ranks">
        <span class="rank-badge">E-Rank: DC 12</span>
        <span class="rank-badge">D-Rank: DC 13</span>
        <span class="rank-badge">C-Rank: DC 14</span>
        <span class="rank-badge">B-Rank: DC 15</span>
        <span class="rank-badge">A-Rank: DC 16</span>
        <span class="rank-badge">S-Rank: DC 17</span>
      </div>
      <p>Items that are completely destroyed cannot be repaired and must be crafted anew.</p>
    </div>

    <div class="guide-section" id="spell-crafting">
      <h2 class="sec-title">Spell Material Crafting <span class="tag">Advanced</span></h2>
      <p>If a spell requires a costly material component (one with a listed price), you can craft it yourself. Pay 50% of the listed price in raw materials and use the table below. Your crafting profession must logically apply to the material.</p>

      <div class="table-wrap">
        <table>
          <thead><tr><th>Spell Level</th><th>Craft Time</th><th>DC</th></tr></thead>
          <tbody>
            <tr><td>1st</td><td>1 hr</td><td>13</td></tr>
            <tr><td>2nd</td><td>2 hrs</td><td>13</td></tr>
            <tr><td>3rd</td><td>4 hrs</td><td>15</td></tr>
            <tr><td>4th</td><td>6 hrs</td><td>15</td></tr>
            <tr><td>5th</td><td>8 hrs</td><td>17</td></tr>
            <tr><td>6th</td><td>10 hrs</td><td>17</td></tr>
            <tr><td>7th</td><td>12 hrs</td><td>18</td></tr>
            <tr><td>8th</td><td>14 hrs</td><td>18</td></tr>
            <tr><td>9th</td><td>16 hrs</td><td>19</td></tr>
          </tbody>
        </table>
      </div>
    </div>

    <div class="guide-section" id="spell-trading">
      <h2 class="sec-title">Spell Trading <span class="tag">Advanced</span></h2>
      <p>Wizards can copy spells from each other's spellbooks or from scrolls without destroying the original. Cost: 2 hours + 50g per spell level.</p>
      <div class="callout">
        <strong>Rules</strong>
        • You can only trade spells with a wizard within one rank of yourself. All trades are 1:1.<br>
        • You cannot copy a spell you lack spell slots to cast. Spell must have the 'wizard' tag.<br>
        • Copying from a scroll requires a DC 10 + spell level Arcana check; failure destroys the scroll.<br>
        • Savants and Order of Scribes halve the time (Savants also halve the cost).
      </div>
    </div>

    <div class="guide-section" id="modifiers">
      <h2 class="sec-title">Crafting Modifier Rulings <span class="tag">Advanced</span></h2>
      <p>The standard crafting roll is <b>1d20 + Proficiency Modifier only</b>. Ability score modifiers (STR, INT, etc.) are not added.</p>

      <div class="table-wrap">
        <table>
          <thead><tr><th>Feature</th><th>Ruling</th></tr></thead>
          <tbody>
            <tr><td>Ability Score Modifiers</td><td><strong>Do not add.</strong> Intelligence would dominate all crafting.</td></tr>
            <tr><td>Aid (Action)</td><td><strong>Can use.</strong> Another proficient crafter spending the same work hours gives you Advantage.</td></tr>
            <tr><td>Homunculus (Artificer)</td><td><strong>Can use.</strong> Your Homunculus can Aid you only (grants Advantage). Cannot Aid others.</td></tr>
            <tr><td>Built for Success (Autognome)</td><td><strong>Can add.</strong> Uses a reaction; cannot combine with other reactions.</td></tr>
            <tr><td>Flash of Genius (Artificer)</td><td><strong>Can add.</strong> Uses a reaction; cannot combine with Built for Success.</td></tr>
            <tr><td>Knowledge of the Ages (Cleric)</td><td><strong>Can use</strong> for crafts taking 10 minutes or less.</td></tr>
            <tr><td>Astral Knowledge / Trance / Whispers of the Dead</td><td><strong>Can use.</strong> Choose temp tool at workweek start; cannot switch. No expertise or reaction-based mods apply.</td></tr>
            <tr><td>Manifold Tool (Artificer)</td><td><strong>Can use,</strong> but proficiency is temporary — no expertise or reaction mods.</td></tr>
            <tr><td>Adroit Crafter (Feat)</td><td><strong>Can use.</strong> Halves crafting time; on failure you keep components. Does not grant proficiency or expertise.</td></tr>
            <tr><td>Magic Item Adept (Artificer 10)</td><td>Gain expertise in one known tool proficiency (cannot double-expertise).</td></tr>
            <tr><td>Guidance, Lucky, Reliable Talent, Tides of Chaos, etc.</td><td><strong>Do not use.</strong> These require an Ability Check, which the Profession Check is not.</td></tr>
          </tbody>
        </table>
      </div>
    </div>

  </div><!-- /content -->

  <footer>
    Black Banner Company Crafting Guide v3.2.8 &nbsp;·&nbsp; Created by Hellbread &nbsp;·&nbsp; Edited by Ooxy &nbsp;·&nbsp; Last updated 6 June 2026
  </footer>


<div class="guide-section" id="changelog">
  <h2 class="sec-title">Changelog <span class="tag">Advanced</span></h2>
  <div class="callout info">
    <strong>Version History</strong>
    This section records major updates, rulings, balance changes, and additions made to the Black Banner Company Crafting Guide.
  </div>

  <h3 class="sub-title">v3.2.8 (6/06/26)</h3>
  <p>Herbalism gold requirements removed. Item Repair System added. Crafting Modifier Rulings updated.</p>

  <h3 class="sub-title">v3.2.7 (5/31/26)</h3>
  <p>Manifold Tool, Adroit Crafter, and Homunculus rulings updated for 2024 crafting rules.</p>

  <h3 class="sub-title">v3.2.6 (3/02/26)</h3>
  <p>Flight Arrow ranges adjusted. Mithril Arrows updated. Smithing and Glassblower weapons now convert all weapon damage to their Prime Material damage type.</p>

  <h3 class="sub-title">v3.2.5 (2/01/26)</h3>
  <p>Added custom ring options for Jewelcrafters.</p>

  <h3 class="sub-title">v3.2.4 (7/14/25)</h3>
  <p>Poisons can now be applied to exotic weapons. Added Malice Cube, Det-Caps, Potter's Wheel, and False Aura.</p>

  <h3 class="sub-title">Legacy Changelog (v3.2.3 - v3.1.1)</h3>
  <p>Previous historical updates retained from the original guide including Dragon Scale Mail changes, Pottery overhaul, Black Lotus, Voidblossom replacement, Spell Trading revisions, Artificer revisions, Deadwood, Ironwood, Summitwood, Spider Silk, Interdisciplinary Crafts, Exotic Shields, and numerous balance updates.</p>
</div>

</main>
</body>
</html>
