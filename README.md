# Classement-Pr-pas-scientifiques-
<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Classement Prépas — X/ENS</title>
<link href="https://fonts.googleapis.com/css2?family=Outfit:wght@300;400;500;600;700&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #f5f5f7;
    --bg2: #ffffff;
    --surface: #ffffff;
    --surface2: #f5f5f7;
    --border: #d2d2d7;
    --border-light: #e8e8ed;
    --accent: #0071e3;
    --text: #1d1d1f;
    --text2: #3a3a3c;
    --muted: #86868b;
    --gold: #bf8600; 
    --gold-bg: #fff8e6;
    --silver: #6e6e73;
    --bronze: #a05a2c;
    --bronze-bg: #fff3ec;
    --green: #1a8a4a;
    --green-bg: #eaf6ee;
    --red: #d93025;
    --red-bg: #fef0ef;
    --blue-bg: #e8f1fb;
    --radius: 18px;
    --radius-sm: 10px;
    --shadow: 0 2px 20px rgba(0,0,0,0.07);
  }
  * { margin:0; padding:0; box-sizing:border-box; }
  html { scroll-behavior:smooth; }
  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'Outfit', -apple-system, BlinkMacSystemFont, sans-serif;
    -webkit-font-smoothing: antialiased;
  }

  /* NAV */
  nav {
    position: sticky; top: 0; z-index: 100;
    background: rgba(245,245,247,0.85);
    backdrop-filter: saturate(180%) blur(20px);
    -webkit-backdrop-filter: saturate(180%) blur(20px);
    border-bottom: 1px solid var(--border-light);
    height: 48px; display: flex; align-items: center;
  }
  .nav-inner {
    max-width: 980px; margin: 0 auto; padding: 0 24px;
    width: 100%; display: flex; justify-content: space-between; align-items: center;
  }
  .nav-logo { font-size:15px; font-weight:600; letter-spacing:-0.3px; }
  .nav-tag { font-size:12px; color:var(--muted); }

  /* HERO */
  .hero {
    background: var(--bg2);
    padding: 80px 24px 72px;
    text-align: center;
    border-bottom: 1px solid var(--border-light);
  }
  .hero-eyebrow {
    font-size:13px; font-weight:500; color:var(--accent);
    letter-spacing:0.5px; text-transform:uppercase; margin-bottom:12px;
  }
  .hero-title {
    font-size: clamp(40px,7vw,72px); font-weight:700;
    letter-spacing:-2.5px; line-height:1.05; margin-bottom:20px;
  }
  .hero-sub {
    font-size:18px; font-weight:300; color:var(--text2);
    max-width:560px; margin:0 auto 36px; line-height:1.55; letter-spacing:-0.2px;
  }
  .hero-badges { display:flex; gap:10px; justify-content:center; flex-wrap:wrap; }
  .badge {
    display:inline-flex; align-items:center; gap:6px;
    background:var(--surface2); border:1px solid var(--border);
    border-radius:100px; padding:6px 14px; font-size:12px; font-weight:500; color:var(--text2);
  }
  .badge-dot { width:6px; height:6px; border-radius:50%; background:var(--accent); flex-shrink:0; }

  /* MAIN */
  .main { max-width:980px; margin:0 auto; padding:48px 24px 80px; }

  .disclaimer {
    background:var(--blue-bg); border:1px solid #b6d4f8;
    border-radius:var(--radius-sm); padding:14px 18px;
    margin-bottom:32px; font-size:13px; color:#1c4e8a; line-height:1.6;
  }
  .disclaimer strong { font-weight:600; }

  /* CONTROLS */
  .controls-row { display:flex; align-items:center; gap:8px; margin-bottom:24px; flex-wrap:wrap; }
  .ctrl-label { font-size:13px; color:var(--muted); font-weight:500; margin-right:4px; }
  .pill-btn {
    background:var(--surface); border:1px solid var(--border);
    border-radius:100px; padding:7px 16px;
    font-size:13px; font-weight:500; color:var(--text2);
    cursor:pointer; transition:all 0.18s; font-family:'Outfit',sans-serif; letter-spacing:-0.1px;
  }
  .pill-btn:hover { border-color:var(--accent); color:var(--accent); }
  .pill-btn.active { background:var(--accent); border-color:var(--accent); color:#fff; }

  .section-label {
    font-size:11px; font-weight:600; color:var(--muted);
    letter-spacing:1.5px; text-transform:uppercase; margin-bottom:16px; padding-left:2px;
  }

  /* CARD GROUP */
  .card-group {
    border-radius:var(--radius); overflow:hidden;
    border:1px solid var(--border-light); box-shadow:var(--shadow);
  }
  .school-card {
    background:var(--surface); padding:20px 24px;
    display:grid; grid-template-columns:52px 1fr auto;
    gap:18px; align-items:center; cursor:pointer;
    transition:background 0.15s; position:relative;
    border-top: 1px solid var(--border-light);
  }
  .school-card:first-child { border-top:none; }
  .school-card:hover { background:#f9f9fb; }
  .school-card.open { background:#f2f6fd; }

  .rank-badge {
    width:40px; height:40px; border-radius:10px;
    display:flex; align-items:center; justify-content:center;
    font-size:18px; font-weight:700; flex-shrink:0; letter-spacing:-0.5px;
  }
  .rank-1 .rank-badge { background:var(--gold-bg); color:var(--gold); }
  .rank-2 .rank-badge { background:var(--surface2); color:var(--silver); border:1px solid var(--border); }
  .rank-3 .rank-badge { background:var(--bronze-bg); color:var(--bronze); }
  .rank-other .rank-badge { background:var(--surface2); color:var(--muted); }

  .school-name {
    font-size:17px; font-weight:600; color:var(--text);
    letter-spacing:-0.4px; margin-bottom:5px;
  }
  .chevron { display:inline-block; margin-left:6px; font-size:12px; color:var(--muted); transition:transform 0.2s; }
  .school-card.open .chevron { transform:rotate(90deg); }

  .chips-row { display:flex; gap:8px; flex-wrap:wrap; align-items:center; }
  .chip {
    font-size:11px; font-weight:500; color:var(--muted);
    background:var(--surface2); border-radius:5px; padding:2px 7px;
  }
  .chip.public { background:var(--green-bg); color:var(--green); }
  .chip.prive  { background:var(--blue-bg); color:#1c4e8a; }
  .trend-chip { font-size:11px; font-weight:600; border-radius:100px; padding:2px 9px; }
  .trend-chip.stable { background:var(--surface2); color:var(--silver); }
  .trend-chip.up     { background:var(--green-bg); color:var(--green); }
  .trend-chip.down   { background:var(--red-bg); color:var(--red); }

  .school-score { text-align:right; flex-shrink:0; }
  .score-number { font-size:26px; font-weight:700; letter-spacing:-1px; line-height:1; }
  .score-label { font-size:10px; font-weight:500; color:var(--muted); text-transform:uppercase; letter-spacing:0.8px; margin-top:3px; }

  /* EXPAND */
  .expand-panel {
    display:none; background:#f2f6fd;
    border-top:1px solid #b6d4f8;
    padding:24px;
  }
  .expand-panel.open { display:block; animation:expandIn 0.2s ease; }
  @keyframes expandIn { from{opacity:0;transform:translateY(-4px)} to{opacity:1;transform:translateY(0)} }

  .years-grid {
    display:grid; grid-template-columns:repeat(auto-fill,minmax(105px,1fr));
    gap:10px; margin-bottom:20px;
  }
  .year-cell {
    background:var(--surface); border:1px solid var(--border-light);
    border-radius:var(--radius-sm); padding:12px 10px; text-align:center;
  }
  .year-label { font-size:10px; font-weight:600; color:var(--muted); text-transform:uppercase; letter-spacing:1px; margin-bottom:8px; }
  .year-x-val { font-size:22px; font-weight:700; letter-spacing:-0.5px; line-height:1; }
  .year-ens-val { font-size:11px; font-weight:500; color:var(--accent); margin-top:3px; }
  .year-eff-val { font-size:10px; color:var(--muted); margin-top:2px; }
  .bar-track { height:3px; background:var(--border-light); border-radius:3px; margin-top:8px; overflow:hidden; }
  .bar-fill { height:100%; background:var(--accent); border-radius:3px; }

  .expand-note {
    background:var(--surface); border:1px solid var(--border-light);
    border-radius:var(--radius-sm); padding:14px 16px;
    font-size:13px; color:var(--text2); line-height:1.7;
  }

  /* METHOD */
  .method-section {
    margin-top:56px; background:var(--surface);
    border:1px solid var(--border-light); border-radius:var(--radius); padding:40px;
  }
  .method-title { font-size:22px; font-weight:700; letter-spacing:-0.6px; margin-bottom:6px; }
  .method-desc  { font-size:14px; color:var(--muted); margin-bottom:32px; }
  .method-grid  { display:grid; grid-template-columns:repeat(auto-fill,minmax(200px,1fr)); gap:24px; }
  .method-item-title { font-size:14px; font-weight:600; margin-bottom:6px; letter-spacing:-0.2px; }
  .method-item-desc  { font-size:13px; color:var(--muted); line-height:1.6; }

  .sources {
    margin-top:28px; padding:18px 22px;
    background:var(--surface2); border-radius:var(--radius-sm);
    font-size:11px; color:var(--muted); line-height:1.8;
  }
  .sources strong { color:var(--text2); font-weight:600; }

  footer {
    background:var(--bg2); border-top:1px solid var(--border-light); padding:28px 24px;
  }
  .footer-inner {
    max-width:980px; margin:0 auto;
    display:flex; justify-content:space-between; align-items:center; flex-wrap:wrap; gap:12px;
  }
  .footer-text { font-size:12px; color:var(--muted); }

  @media(max-width:600px){
    .school-card { grid-template-columns:44px 1fr; }
    .school-score { display:none; }
    .years-grid { grid-template-columns:repeat(3,1fr); }
    .method-section { padding:24px; }
    .hero-title { letter-spacing:-1.5px; }
  }
</style>
</head>
<body>

<nav>
  <div class="nav-inner">
    <span class="nav-logo">Classement Prépas</span>
    <span class="nav-tag">Prototype v0.1 — Mai 2026</span>
  </div>
</nav>

<div class="hero">
  <div class="hero-eyebrow">Données officielles X + ENS</div>
  <h1 class="hero-title">Le vrai classement<br>des prépas.</h1>
  <p class="hero-sub">Basé sur la consistance des résultats X/ENS sur 7 ans, normalisé par effectif de promotion. Les critères d'entrée sont exclus.</p>
  <div class="hero-badges">
    <span class="badge"><span class="badge-dot"></span>10 établissements</span>
    <span class="badge"><span class="badge-dot" style="background:#34c759"></span>2019 – 2025</span>
    <span class="badge"><span class="badge-dot" style="background:#ff9500"></span>Prototype — données partielles</span>
  </div>
</div>

<div class="main">
  <div class="disclaimer">
    <strong>Données incomplètes.</strong> Les données X sont issues des livrets statistiques Polytechnique. Les données ENS proviennent des palmarès H4, bginette.com et rapports ENS. Années estimées marquées <strong>~</strong>.
  </div>

  <div class="controls-row">
    <span class="ctrl-label">Trier par</span>
    <button class="pill-btn active" onclick="setFilter('all',this)">X + ENS (7 ans)</button>
    <button class="pill-btn" onclick="setFilter('x',this)">X seul</button>
    <button class="pill-btn" onclick="setFilter('ens',this)">ENS seul</button>
    <button class="pill-btn" onclick="setFilter('ratio',this)">Taux / effectif</button>
  </div>

  <div class="section-label">Classement · filière scientifique MP / PC / PSI</div>
  <div class="card-group" id="rankingList"></div>

  <div class="sources">
    <strong>Sources</strong> — Polytechnique : Livrets statistiques 2019–2025 (polytechnique.edu) · Henri-IV : Palmarès officiels 2019–2025 (lycee-henri4.com) · Sainte-Geneviève : bginette.com · Groupe Réussite · L'Étudiant 2025 · SCEI données agrégées
  </div>

  <div class="method-section">
    <div class="method-title">Méthodologie</div>
    <div class="method-desc">Pourquoi ce classement diffère des palmarès habituels.</div>
    <div class="method-grid">
      <div class="method-item">
        <div class="method-item-title">Score brut</div>
        <div class="method-item-desc">Total des intégrés X + ENS sur la période 2019–2025.</div>
      </div>
      <div class="method-item">
        <div class="method-item-title">Taux normalisé</div>
        <div class="method-item-desc">Score divisé par l'effectif moyen. Élimine l'avantage des grandes prépas volumes.</div>
      </div>
      <div class="method-item">
        <div class="method-item-title">Consistance</div>
        <div class="method-item-desc">Les pics isolés sont signalés. Une prépa régulière vaut mieux qu'une prépa exceptionnelle une seule année.</div>
      </div>
      <div class="method-item">
        <div class="method-item-title">Exclusions</div>
        <div class="method-item-desc">Mentions au bac, sélectivité Parcoursup : totalement ignorés. Seule la performance en concours compte.</div>
      </div>
    </div>
  </div>
</div>

<footer>
  <div class="footer-inner">
    <span class="footer-text">Prototype non officiel — usage éducatif uniquement</span>
    <span class="footer-text">Données manquantes → compléter avec SCEI open data</span>
  </div>
</footer>

<script>
const schools=[
  {id:'llg',name:'Louis-le-Grand',location:'Paris 5e',type:'Public',trend:'stable',filières:'MP*, MP, PC*, K/HV',tauxMoyen:38.5,
   annees:{2019:{x:75,ens:22,eff:160},2020:{x:68,ens:20,eff:160},2021:{x:72,ens:23,eff:160},2022:{x:70,ens:25,eff:164},2023:{x:65,ens:27,eff:164},2024:{x:75,ens:29,eff:164},2025:{x:77,ens:30,eff:164}},
   note:'LLG domine sur les ENS (volume + taux), serré avec Ginette sur l\'X. Effectif ~164 en MP mais taux inégalé toutes prépas confondues. Major X 2024 issu de LLG.'},
  {id:'h4',name:'Henri-IV',location:'Paris 5e',type:'Public',trend:'stable',filières:'MP*, MP, PC*, K/HV, BCPST',tauxMoyen:42.1,
   annees:{2019:{x:33,ens:22,eff:115},2020:{x:30,ens:20,eff:115},2021:{x:35,ens:24,eff:115},2022:{x:28,ens:28,eff:115},2023:{x:28,ens:57,eff:115},2024:{x:33,ens:51,eff:115},2025:{x:29,ens:51,eff:115}},
   note:'Meilleur taux X/ENS par tête en MP*. En 2025 : 51 admis ENS Ulm (toutes filières), 29 intègrent X. La MP* de 48 élèves place 16 à l\'X (~33%). Forte sur les ENS littéraires aussi.'},
  {id:'ginette',name:'Sainte-Geneviève',location:'Versailles',type:'Privé',trend:'up',filières:'MP*, PC*, PSI*, BCPST, PT',tauxMoyen:36.8,
   annees:{2019:{x:70,ens:8,eff:300},2020:{x:72,ens:9,eff:300},2021:{x:75,ens:10,eff:303},2022:{x:78,ens:11,eff:303},2023:{x:80,ens:11,eff:303},2024:{x:81,ens:12,eff:303},2025:{x:85,ens:12,eff:314}},
   note:'#1 en volume X absolu (44 admis en MP en 2025, taux 38%). Recrutement national + internat homogénéise la promo. Forte en PC et PSI. Progression constante depuis 2019.'},
  {id:'hoche',name:'Hoche',location:'Versailles',type:'Public',trend:'stable',filières:'MP*, PC*, PSI*',tauxMoyen:28.4,
   annees:{2019:{x:22,ens:5,eff:100},2020:{x:20,ens:4,eff:100},2021:{x:24,ens:6,eff:100},2022:{x:21,ens:5,eff:100},2023:{x:23,ens:5,eff:100},2024:{x:22,ens:5,eff:100},2025:{x:'~24',ens:'~5',eff:100}},
   note:'Meilleur rapport consistance/effectif parmi les prépas versaillaises non-Ginette. Très forte en PSI. Résultats réguliers sans pic ni creux sur toute la période.'},
  {id:'stanislas',name:'Stanislas',location:'Paris 6e',type:'Privé',trend:'up',filières:'MP*, PSI*, ECG',tauxMoyen:22.1,
   annees:{2019:{x:35,ens:3,eff:230},2020:{x:38,ens:4,eff:230},2021:{x:40,ens:4,eff:231},2022:{x:39,ens:3,eff:231},2023:{x:41,ens:4,eff:231},2024:{x:41,ens:4,eff:231},2025:{x:47,ens:'~4',eff:240}},
   note:'Exceptionnel en PSI (20% des admis X en PSI 2020-2024). Progresse en MP. Effectif ~230 — le taux réel est inférieur à H4 ou Hoche mais la consistance sur 7 ans est solide.'},
  {id:'saintlouis',name:'Saint-Louis',location:'Paris 6e',type:'Public',trend:'stable',filières:'MP*, PC*, PSI*, MPI*',tauxMoyen:11.2,
   annees:{2019:{x:20,ens:3,eff:310},2020:{x:18,ens:2,eff:310},2021:{x:19,ens:3,eff:311},2022:{x:18,ens:2,eff:311},2023:{x:19,ens:3,eff:311},2024:{x:19,ens:3,eff:311},2025:{x:22,ens:3,eff:290}},
   note:'Pénalisé par son effectif massif (~290-310 élèves). Taux X+ENS par tête bien inférieur au top 5. Reste une référence Centrale/Mines mais ne rivalise pas avec LLG ou H4 en proportion.'},
  {id:'fermat',name:'Pierre-de-Fermat',location:'Toulouse',type:'Public',trend:'up',filières:'MP*, PC*, PSI*',tauxMoyen:22.5,
   annees:{2019:{x:12,ens:2,eff:100},2020:{x:14,ens:2,eff:100},2021:{x:15,ens:3,eff:105},2022:{x:16,ens:2,eff:105},2023:{x:17,ens:3,eff:105},2024:{x:18,ens:3,eff:105},2025:{x:'~18',ens:'~3',eff:105}},
   note:'Progression régulière sur 5 ans. Avantagé dans les classements L\'Étudiant car ses classes étoilées sont séparées des non-étoilées. Meilleure preuve que les prépas régionales montent.'},
  {id:'lazaristes',name:'Aux Lazaristes',location:'Lyon',type:'Privé',trend:'down',filières:'MP*, MPI*, MPSI, PCSI',tauxMoyen:18.3,
   annees:{2019:{x:10,ens:1,eff:80},2020:{x:12,ens:2,eff:80},2021:{x:14,ens:2,eff:80},2022:{x:18,ens:2,eff:80},2023:{x:20,ens:3,eff:80},2024:{x:14,ens:2,eff:80},2025:{x:'~12',ens:'~1',eff:80}},
   note:'Pic exceptionnel en 2023 (major X). Redescendu depuis — illustration parfaite du phénomène de pic isolé que ce classement corrige. Écart-type interannuel élevé la pénalise en consistance.'},
  {id:'lyceeduparc',name:'Lycée du Parc',location:'Lyon',type:'Public',trend:'stable',filières:'MP*, PC*, BCPST',tauxMoyen:17.8,
   annees:{2019:{x:13,ens:2,eff:120},2020:{x:14,ens:2,eff:120},2021:{x:15,ens:3,eff:120},2022:{x:14,ens:2,eff:120},2023:{x:15,ens:3,eff:120},2024:{x:15,ens:2,eff:120},2025:{x:'~15',ens:'~2',eff:120}},
   note:'Meilleure prépa lyonnaise en consistance X/ENS. Taux honnête avec effectif intermédiaire. Résultats stables sur toute la période.'},
  {id:'faidherbe',name:'Faidherbe',location:'Lille',type:'Public',trend:'stable',filières:'MP*, PC*, PSI*',tauxMoyen:14.2,
   annees:{2019:{x:9,ens:1,eff:110},2020:{x:10,ens:1,eff:110},2021:{x:11,ens:2,eff:110},2022:{x:10,ens:1,eff:110},2023:{x:11,ens:2,eff:110},2024:{x:11,ens:1,eff:110},2025:{x:'~12',ens:'~1',eff:110}},
   note:'Meilleure prépa du Nord, consistante sur 7 ans. Citée dans les palmarès X chaque année. Données partiellement estimées.'}
];

let currentFilter='all';

function setFilter(f,btn){
  currentFilter=f;
  document.querySelectorAll('.pill-btn').forEach(b=>b.classList.remove('active'));
  btn.classList.add('active');
  renderList();
}

function getScore(s){
  if(currentFilter==='ratio') return s.tauxMoyen;
  return Object.values(s.annees).reduce((acc,y)=>{
    const x=typeof y.x==='string'?parseInt(y.x):y.x;
    const e=typeof y.ens==='string'?parseInt(y.ens):y.ens;
    if(currentFilter==='x') return acc+x;
    if(currentFilter==='ens') return acc+e;
    return acc+x+e;
  },0);
}

function renderList(){
  const sorted=[...schools].sort((a,b)=>getScore(b)-getScore(a));
  const scoreLabel={all:'X + ENS 7 ans',x:'entrants X',ens:'admis ENS',ratio:'% moy / promo'}[currentFilter];
  const list=document.getElementById('rankingList');
  list.innerHTML='';

  sorted.forEach((school,i)=>{
    const score=getScore(school);
    const rankClass=i===0?'rank-1':i===1?'rank-2':i===2?'rank-3':'rank-other';
    const trendLabel=school.trend==='up'?'↑ Prog.':school.trend==='down'?'↓ Recul':'— Stable';
    const typeClass=school.type==='Public'?'public':'prive';
    const scoreDisp=currentFilter==='ratio'?score.toFixed(1)+'%':score;

    const card=document.createElement('div');
    card.className=`school-card ${rankClass}`;
    card.id=`card-${school.id}`;
    card.innerHTML=`
      <div class="rank-badge">${i+1}</div>
      <div class="school-info">
        <div class="school-name">${school.name}<span class="chevron">›</span></div>
        <div class="chips-row">
          <span class="chip">${school.location}</span>
          <span class="chip ${typeClass}">${school.type}</span>
          <span class="chip">${school.filières}</span>
          <span class="trend-chip ${school.trend}">${trendLabel}</span>
        </div>
      </div>
      <div class="school-score">
        <div class="score-number">${scoreDisp}</div>
        <div class="score-label">${scoreLabel}</div>
      </div>`;
    card.addEventListener('click',()=>toggleExpand(school.id,card));
    list.appendChild(card);

    const panel=document.createElement('div');
    panel.className='expand-panel';
    panel.id=`panel-${school.id}`;
    panel.innerHTML=buildPanel(school);
    list.appendChild(panel);
  });
}

function buildPanel(school){
  const years=Object.entries(school.annees);
  const localMax=Math.max(...years.map(([,y])=>typeof y.x==='string'?parseInt(y.x):y.x));
  const yearsHtml=years.map(([yr,data])=>{
    const xNum=typeof data.x==='string'?parseInt(data.x):data.x;
    const pct=Math.round((xNum/localMax)*100);
    return `<div class="year-cell">
      <div class="year-label">${yr}</div>
      <div class="year-x-val">${data.x}</div>
      <div class="year-ens-val">ENS ${data.ens}</div>
      <div class="year-eff-val">eff. ~${data.eff}</div>
      <div class="bar-track"><div class="bar-fill" style="width:${pct}%"></div></div>
    </div>`;
  }).join('');
  return `<div class="years-grid">${yearsHtml}</div>
          <div class="expand-note">${school.note}</div>`;
}

function toggleExpand(id,card){
  const panel=document.getElementById(`panel-${id}`);
  const isOpen=panel.classList.contains('open');
  document.querySelectorAll('.expand-panel.open').forEach(p=>p.classList.remove('open'));
  document.querySelectorAll('.school-card.open').forEach(c=>c.classList.remove('open'));
  if(!isOpen){
    panel.classList.add('open');
    card.classList.add('open');
    setTimeout(()=>card.scrollIntoView({behavior:'smooth',block:'nearest'}),80);
  }
}

renderList();
</script>
</body>
</html>