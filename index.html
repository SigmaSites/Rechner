<!DOCTYPE html>
<html lang="de">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
<title>Taschenrechner</title>
<link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@300;400;600;700&family=Syne:wght@700;800&display=swap" rel="stylesheet" media="print" onload="this.media='all'">
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --bg: #0d0d0f;
    --surface: #16161a;
    --surface2: #1e1e24;
    --border: #2a2a35;
    --accent: #e8ff47;
    --accent2: #ff6b35;
    --accent3: #47b8ff;
    --text: #f0f0f5;
    --muted: #6b6b80;
  }

  html, body {
    width: 100%; height: 100%;
    overflow: hidden;
    background: var(--bg);
    font-family: 'JetBrains Mono', monospace;
    color: var(--text);
    -webkit-tap-highlight-color: transparent;
  }

  body {
    display: flex;
    flex-direction: column;
    height: 100dvh; /* dynamic viewport height for mobile */
  }

  /* ── TAB BAR (bottom) ── */
  .tab-bar {
    order: 2;
    display: flex;
    background: var(--surface);
    border-top: 1px solid var(--border);
    flex-shrink: 0;
    padding-bottom: env(safe-area-inset-bottom);
  }

  .tab {
    flex: 1;
    padding: 10px 4px 8px;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 3px;
    font-family: 'Syne', sans-serif;
    font-size: 9px;
    font-weight: 800;
    letter-spacing: 0.08em;
    text-transform: uppercase;
    color: var(--muted);
    cursor: pointer;
    border: none;
    background: none;
    border-top: 2px solid transparent;
    transition: color 0.2s, border-color 0.2s;
  }

  .tab .icon { font-size: 20px; line-height: 1; }
  .tab.active { color: var(--accent); border-top-color: var(--accent); }

  /* ── PAGES ── */
  .pages {
    order: 1;
    flex: 1;
    min-height: 0;
    position: relative;
  }

  .page {
    display: none;
    position: absolute;
    inset: 0;
    flex-direction: column;
  }
  .page.active { display: flex; }

  /* ════════════════════════════
     RECHNER
  ════════════════════════════ */
  .display {
    flex: 1;
    display: flex;
    flex-direction: column;
    justify-content: flex-end;
    padding: 12px 20px 10px;
    min-height: 0;
    border-bottom: 1px solid var(--border);
  }

  .display-history {
    font-size: 13px;
    color: var(--muted);
    text-align: right;
    min-height: 18px;
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
    margin-bottom: 4px;
  }

  .display-main {
    font-size: clamp(36px, 12vw, 56px);
    font-weight: 300;
    text-align: right;
    letter-spacing: -0.02em;
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
    transition: color 0.15s;
  }

  .display-main.error { color: var(--accent2); }

  .buttons {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 1px;
    background: var(--border);
    flex-shrink: 0;
  }

  .btn {
    background: var(--surface);
    border: none;
    /* height fills remaining space equally */
    aspect-ratio: unset;
    height: calc((100dvh - env(safe-area-inset-bottom) - 57px - 90px - 1px) / 5);
    font-family: 'JetBrains Mono', monospace;
    font-size: clamp(16px, 4.5vw, 22px);
    color: var(--text);
    cursor: pointer;
    display: flex;
    align-items: center;
    justify-content: center;
    position: relative;
    overflow: hidden;
    user-select: none;
    transition: background 0.08s;
  }

  .btn:active { background: var(--surface2); }

  .btn.fn  { color: var(--muted); font-size: clamp(13px, 3.5vw, 17px); }
  .btn.op  { color: var(--accent); font-size: clamp(18px, 5vw, 26px); }
  .btn.eq  { background: var(--accent); color: #000; font-weight: 700; font-size: clamp(18px, 5vw, 26px); }
  .btn.eq:active { background: #cde82f; }
  .btn.zero { grid-column: span 2; }
  .btn.clr { color: var(--accent2); }

  /* ════════════════════════════
     STATISTIK
  ════════════════════════════ */
  .scroll-page {
    flex: 1;
    overflow-y: auto;
    -webkit-overflow-scrolling: touch;
    padding: 14px 14px 6px;
    display: flex;
    flex-direction: column;
    gap: 10px;
  }

  .section-title {
    font-family: 'Syne', sans-serif;
    font-size: 9px;
    font-weight: 800;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    color: var(--muted);
  }

  .field-label {
    font-size: 9px;
    letter-spacing: 0.1em;
    color: var(--muted);
    text-transform: uppercase;
    margin-bottom: 5px;
  }

  .field-hint {
    font-size: 10px;
    color: var(--muted);
    margin-top: 3px;
  }

  input[type="text"], input[type="number"] {
    width: 100%;
    background: var(--surface2);
    border: 1px solid var(--border);
    color: var(--text);
    font-family: 'JetBrains Mono', monospace;
    font-size: 14px;
    padding: 10px 14px;
    border-radius: 8px;
    outline: none;
    transition: border-color 0.2s;
    -webkit-appearance: none;
  }

  input:focus { border-color: var(--accent); }

  .action-btn {
    background: var(--accent);
    color: #000;
    border: none;
    border-radius: 8px;
    padding: 11px;
    font-family: 'Syne', sans-serif;
    font-size: 11px;
    font-weight: 800;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    cursor: pointer;
    width: 100%;
    transition: opacity 0.15s;
  }
  .action-btn:active { opacity: 0.8; }

  .result-cards {
    display: flex;
    flex-direction: column;
    gap: 8px;
  }

  .rcard {
    background: var(--surface2);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 10px 14px;
    transition: border-color 0.3s;
  }

  .rcard.mean   { border-color: var(--accent); }
  .rcard.modal  { border-color: var(--accent2); }
  .rcard.median { border-color: var(--accent3); }

  .rcard-label {
    font-size: 9px;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    color: var(--muted);
    margin-bottom: 2px;
  }

  .rcard-value {
    font-size: 22px;
    font-weight: 600;
    color: var(--accent);
    line-height: 1.2;
  }

  .rcard.modal  .rcard-value { color: var(--accent2); }
  .rcard.median .rcard-value { color: var(--accent3); }

  .rcard-sub {
    font-size: 10px;
    color: var(--muted);
    margin-top: 2px;
    line-height: 1.4;
  }

  /* ════════════════════════════
     VERGLEICHEN
  ════════════════════════════ */
  .cmp-row {
    display: flex;
    align-items: flex-end;
    gap: 10px;
  }

  .cmp-row .field-wrap { flex: 1; }

  .sym-box {
    width: 52px;
    height: 44px;
    background: var(--surface2);
    border: 2px solid var(--border);
    border-radius: 8px;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-shrink: 0;
    transition: border-color 0.3s, background 0.3s;
  }

  .sym-box span {
    font-size: 22px;
    font-weight: 700;
    color: var(--muted);
    transition: color 0.3s;
  }

  .sym-box.lt { border-color: var(--accent3); background: rgba(71,184,255,0.08); }
  .sym-box.gt { border-color: var(--accent2); background: rgba(255,107,53,0.08); }
  .sym-box.eq { border-color: var(--accent);  background: rgba(232,255,71,0.08); }
  .sym-box.lt span { color: var(--accent3); }
  .sym-box.gt span { color: var(--accent2); }
  .sym-box.eq span { color: var(--accent); }

  .cmp-result-card {
    background: var(--surface2);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 14px;
    text-align: center;
    transition: border-color 0.3s;
  }

  .cmp-result-card.lt { border-color: var(--accent3); }
  .cmp-result-card.gt { border-color: var(--accent2); }
  .cmp-result-card.eq { border-color: var(--accent); }

  .cmp-result-text {
    font-size: 15px;
    font-weight: 600;
    color: var(--muted);
    transition: color 0.3s;
  }

  .cmp-result-card.lt .cmp-result-text { color: var(--accent3); }
  .cmp-result-card.gt .cmp-result-text { color: var(--accent2); }
  .cmp-result-card.eq .cmp-result-text { color: var(--accent); }

  .cmp-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 8px;
  }

  .cmp-card {
    background: var(--surface2);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 10px 12px;
  }
</style>
</head>
<body>

<div class="pages">

  <!-- ── RECHNER ── -->
  <div class="page active" id="page-calc">
    <div class="display">
      <div class="display-history" id="history"></div>
      <div class="display-main" id="displayMain">0</div>
    </div>
    <div class="buttons">
      <button class="btn fn clr" onclick="clearAll()">AC</button>
      <button class="btn fn"     onclick="toggleSign()">+/−</button>
      <button class="btn fn"     onclick="percent()">%</button>
      <button class="btn op"     onclick="setOp('/')">÷</button>

      <button class="btn" onclick="input('7')">7</button>
      <button class="btn" onclick="input('8')">8</button>
      <button class="btn" onclick="input('9')">9</button>
      <button class="btn op" onclick="setOp('*')">×</button>

      <button class="btn" onclick="input('4')">4</button>
      <button class="btn" onclick="input('5')">5</button>
      <button class="btn" onclick="input('6')">6</button>
      <button class="btn op" onclick="setOp('-')">−</button>

      <button class="btn" onclick="input('1')">1</button>
      <button class="btn" onclick="input('2')">2</button>
      <button class="btn" onclick="input('3')">3</button>
      <button class="btn op" onclick="setOp('+')">+</button>

      <button class="btn zero" onclick="input('0')">0</button>
      <button class="btn"  onclick="inputDot()">.</button>
      <button class="btn eq" onclick="calculate()">=</button>
    </div>
  </div>

  <!-- ── STATISTIK ── -->
  <div class="page" id="page-stats">
    <div class="scroll-page">
      <div class="section-title">Statistische Auswertung</div>

      <div>
        <div class="field-label">Zahlenreihe</div>
        <input type="text" id="statInput" placeholder="z.B. 3, 7, 7, 2, 9" />
        <div class="field-hint">Komma oder Leerzeichen · Enter zum Berechnen</div>
      </div>

      <button class="action-btn" onclick="calcStats()">Berechnen</button>

      <div class="result-cards">
        <div class="rcard mean">
          <div class="rcard-label">Durchschnitt (Mittelwert)</div>
          <div class="rcard-value" id="valMean">—</div>
          <div class="rcard-sub"  id="subMean">Summe ÷ Anzahl</div>
        </div>
        <div class="rcard modal">
          <div class="rcard-label">Modalwert (Modus)</div>
          <div class="rcard-value" id="valModal">—</div>
          <div class="rcard-sub"  id="subModal">Am häufigsten vorkommend</div>
        </div>
        <div class="rcard median">
          <div class="rcard-label">Zentralwert (Median)</div>
          <div class="rcard-value" id="valMedian">—</div>
          <div class="rcard-sub"  id="subMedian">Mittlerer Wert der sortierten Reihe</div>
        </div>
      </div>
    </div>
  </div>

  <!-- ── VERGLEICHEN ── -->
  <div class="page" id="page-compare">
    <div class="scroll-page">
      <div class="section-title">Zahlen Vergleichen</div>

      <div class="cmp-row">
        <div class="field-wrap">
          <div class="field-label">Zahl A</div>
          <input type="number" id="cmpA" placeholder="z.B. 42" oninput="doCompare()" />
        </div>
        <div class="sym-box" id="cmpSymbol"><span id="cmpIcon">?</span></div>
        <div class="field-wrap">
          <div class="field-label">Zahl B</div>
          <input type="number" id="cmpB" placeholder="z.B. 99" oninput="doCompare()" />
        </div>
      </div>

      <div class="cmp-result-card" id="cmpResultCard">
        <div class="cmp-result-text" id="cmpResult">Gib zwei Zahlen ein</div>
      </div>

      <div class="cmp-grid" id="cmpExtra" style="display:none">
        <div class="cmp-card">
          <div class="rcard-label">Differenz (A − B)</div>
          <div class="rcard-value" id="cmpDiff" style="color:var(--accent)">—</div>
        </div>
        <div class="cmp-card">
          <div class="rcard-label">Verhältnis (A ÷ B)</div>
          <div class="rcard-value" id="cmpRatio" style="color:var(--accent3)">—</div>
        </div>
        <div class="cmp-card">
          <div class="rcard-label">% Unterschied</div>
          <div class="rcard-value" id="cmpPct" style="color:var(--accent2)">—</div>
        </div>
        <div class="cmp-card">
          <div class="rcard-label">Größerer Wert</div>
          <div class="rcard-value" id="cmpMax" style="color:var(--accent)">—</div>
        </div>
      </div>
    </div>
  </div>

</div><!-- /pages -->

<!-- ── TAB BAR (bottom) ── -->
<div class="tab-bar">
  <button class="tab active" id="tab-calc" onclick="switchTab('calc')">
    <span class="icon">🔢</span>Rechner
  </button>
  <button class="tab" id="tab-stats" onclick="switchTab('stats')">
    <span class="icon">📊</span>Statistik
  </button>
  <button class="tab" id="tab-compare" onclick="switchTab('compare')">
    <span class="icon">⚖️</span>Vergleichen
  </button>
</div>

<script>
// ── TABS ──
function switchTab(tab) {
  ['calc','stats','compare'].forEach(t => {
    document.getElementById('tab-'+t).classList.toggle('active', t===tab);
    document.getElementById('page-'+t).classList.toggle('active', t===tab);
  });
}

// ── CALCULATOR ──
let current='0', prev='', operator=null, freshResult=false;
const disp = document.getElementById('displayMain');
const hist = document.getElementById('history');

function updateDisplay(v){ disp.classList.remove('error'); disp.textContent=v; }

function input(d){
  if(freshResult){ current=d; freshResult=false; }
  else current = current==='0' ? d : current+d;
  updateDisplay(current);
}

function inputDot(){
  if(freshResult){ current='0.'; freshResult=false; }
  else if(!current.includes('.')) current+='.';
  updateDisplay(current);
}

function clearAll(){ current='0'; prev=''; operator=null; freshResult=false; hist.textContent=''; updateDisplay('0'); }
function toggleSign(){ current=String(-parseFloat(current)); updateDisplay(current); }
function percent(){ current=String(parseFloat(current)/100); updateDisplay(current); }

function setOp(op){
  if(operator && !freshResult) calculate(true);
  prev=current; operator=op; freshResult=true;
  const s={'/':'÷','*':'×','-':'−','+':'+'};
  hist.textContent=prev+' '+s[op];
}

function calculate(chain=false){
  if(!operator||!prev) return;
  const a=parseFloat(prev), b=parseFloat(current);
  let res;
  switch(operator){
    case '+': res=a+b; break;
    case '-': res=a-b; break;
    case '*': res=a*b; break;
    case '/': res=b===0?'Fehler':a/b; break;
  }
  const s={'/':'÷','*':'×','-':'−','+':'+'};
  if(!chain) hist.textContent=prev+' '+s[operator]+' '+current+' =';
  if(res==='Fehler'){
    disp.classList.add('error'); disp.textContent='Fehler';
    operator=null; prev=''; current='0'; freshResult=true; return;
  }
  res=parseFloat(res.toPrecision(12));
  current=String(res); freshResult=true; operator=null;
  updateDisplay(current);
}

document.addEventListener('keydown',e=>{
  if(!document.getElementById('page-calc').classList.contains('active')) return;
  if('0123456789'.includes(e.key)) input(e.key);
  else if(e.key==='.') inputDot();
  else if(e.key==='+') setOp('+');
  else if(e.key==='-') setOp('-');
  else if(e.key==='*') setOp('*');
  else if(e.key==='/'){e.preventDefault();setOp('/');}
  else if(e.key==='Enter'||e.key==='=') calculate();
  else if(e.key==='Backspace'){
    if(current.length>1) current=current.slice(0,-1); else current='0';
    updateDisplay(current);
  }
  else if(e.key==='Escape') clearAll();
});

// ── STATS ──
function parseNums(str){
  return str.split(/[\s,;]+/).map(s=>parseFloat(s.replace(',','.'))).filter(n=>!isNaN(n));
}

function calcStats(){
  const raw=document.getElementById('statInput').value.trim();
  if(!raw) return;
  const nums=raw.split(/[\s,;]+/).map(s=>parseFloat(s.replace(',','.'))).filter(n=>!isNaN(n));
  if(!nums.length){ document.getElementById('valMean').textContent='Ungültig'; return; }

  const sum=nums.reduce((a,b)=>a+b,0);
  const mean=sum/nums.length;
  document.getElementById('valMean').textContent=rnd(mean);
  document.getElementById('subMean').textContent=`Summe ${rnd(sum)} ÷ ${nums.length}`;

  const freq={};
  nums.forEach(n=>freq[n]=(freq[n]||0)+1);
  const maxF=Math.max(...Object.values(freq));
  const modes=Object.keys(freq).filter(k=>freq[k]===maxF).map(Number);
  if(maxF===1){
    document.getElementById('valModal').textContent='Keiner';
    document.getElementById('subModal').textContent='Alle gleich häufig';
  } else {
    document.getElementById('valModal').textContent=modes.join(', ');
    document.getElementById('subModal').textContent=`Erscheint ${maxF}× in der Reihe`;
  }

  const sorted=[...nums].sort((a,b)=>a-b);
  const mid=Math.floor(sorted.length/2);
  let median;
  if(sorted.length%2===0){
    median=(sorted[mid-1]+sorted[mid])/2;
    document.getElementById('subMedian').textContent=`Mittel aus ${sorted[mid-1]} und ${sorted[mid]}`;
  } else {
    median=sorted[mid];
    document.getElementById('subMedian').textContent=`Pos. ${mid+1} von ${sorted.length}`;
  }
  document.getElementById('valMedian').textContent=rnd(median);
}

document.getElementById('statInput').addEventListener('keydown',e=>{ if(e.key==='Enter') calcStats(); });

// ── COMPARE ──
function doCompare(){
  const a=parseFloat(document.getElementById('cmpA').value);
  const b=parseFloat(document.getElementById('cmpB').value);
  const box=document.getElementById('cmpSymbol');
  const icon=document.getElementById('cmpIcon');
  const card=document.getElementById('cmpResultCard');
  const res=document.getElementById('cmpResult');
  const extra=document.getElementById('cmpExtra');

  box.className='sym-box'; card.className='cmp-result-card';

  if(isNaN(a)||isNaN(b)){
    icon.textContent='?'; res.textContent='Gib zwei Zahlen ein';
    extra.style.display='none'; return;
  }

  extra.style.display='grid';
  document.getElementById('cmpDiff').textContent=rnd(a-b);
  document.getElementById('cmpRatio').textContent=b!==0?rnd(a/b):'∞';
  document.getElementById('cmpPct').textContent=b!==0?rnd(Math.abs((a-b)/b)*100)+' %':'∞';
  document.getElementById('cmpMax').textContent=rnd(Math.max(a,b));

  if(a<b){
    icon.textContent='<'; box.classList.add('lt'); card.classList.add('lt');
    res.textContent=`${rnd(a)} ist kleiner als ${rnd(b)}`;
  } else if(a>b){
    icon.textContent='>'; box.classList.add('gt'); card.classList.add('gt');
    res.textContent=`${rnd(a)} ist größer als ${rnd(b)}`;
  } else {
    icon.textContent='='; box.classList.add('eq'); card.classList.add('eq');
    res.textContent=`${rnd(a)} ist gleich ${rnd(b)}`;
  }
}

function rnd(n){ return parseFloat(n.toPrecision(10)).toString(); }

// Vollbild beim ersten Antippen
document.addEventListener('click', function goFS() {
  const el = document.documentElement;
  if (el.requestFullscreen) el.requestFullscreen();
  else if (el.webkitRequestFullscreen) el.webkitRequestFullscreen();
  document.removeEventListener('click', goFS);
}, { once: true });
</script>
</body>
</html>
