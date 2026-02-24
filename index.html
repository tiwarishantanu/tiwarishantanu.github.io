<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>BTC Binary Option Pricer — BS Live</title>
<style>
  * { box-sizing: border-box; margin: 0; padding: 0; }
  body {
    background-color: #0a1628;
    background-image:
      radial-gradient(ellipse 70% 50% at 15% 40%, rgba(247,147,26,0.13) 0%, transparent 60%),
      radial-gradient(ellipse 55% 45% at 85% 70%, rgba(247,147,26,0.09) 0%, transparent 55%),
      url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='110' height='110'%3E%3Ctext x='12' y='78' font-size='62' fill='rgba(247%2C147%2C26%2C0.055)' font-family='Arial%2Csans-serif' font-weight='bold'%3E%E2%82%BF%3C/text%3E%3C/svg%3E");
    background-size: auto, auto, 110px 110px;
    color: #1e293b;
    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', 'Inter', sans-serif;
    min-height: 100vh;
    display: flex;
    justify-content: center;
    padding: 24px;
  }
  .page-wrap { width: 100%; max-width: 560px; }

  .header { margin-bottom: 16px; width: 100%; }
  .header h1 {
    font-size: 2.8rem; font-weight: 900; color: #ffffff;
    margin: 0; padding: 0; white-space: nowrap; width: 100%;
  }

  .top-section { display: flex; flex-direction: column; gap: 8px; width: 100%; margin-bottom: 16px; }

  .row-card {
    background: #fff; border: 1px solid #e2e8f0;
    border-radius: 14px; padding: 14px 20px;
    box-shadow: 0 1px 3px rgba(0,0,0,0.05);
  }
  .row-label {
    font-size: 0.58rem; font-weight: 700; color: #94a3b8;
    text-transform: uppercase; letter-spacing: 0.1em;
    margin-bottom: 5px; display: flex; align-items: center; gap: 5px;
  }
  .btc-headline { display: flex; align-items: baseline; gap: 12px; justify-content: center; }
  .big-price {
    font-size: 2.6rem; font-weight: 700; color: #1e293b;
    font-family: 'SF Mono', ui-monospace, monospace;
    letter-spacing: -0.03em; line-height: 1;
  }
  .staleness  { font-size: 0.72rem; }
  .price-meta { font-size: 0.65rem; color: #94a3b8; margin-top: 4px; text-align: center; }

  .timer-card { text-align: center; padding: 10px 20px 14px; }
  .timer-big {
    font-size: 4.2rem; font-weight: 700; color: #6366f1;
    letter-spacing: 8px; line-height: 1;
    font-family: 'SF Mono', ui-monospace, monospace;
  }

  .price-pair { display: grid; grid-template-columns: 1fr 1fr; }
  .price-col  { padding: 6px 0; text-align: center; }
  .price-col + .price-col { border-left: 1px solid #e2e8f0; }
  .pcol-label {
    font-size: 0.57rem; font-weight: 700; text-transform: uppercase;
    letter-spacing: 0.1em; color: #94a3b8; margin-bottom: 4px;
  }
  .pcol-val {
    font-size: 2.8rem; font-weight: 700;
    font-family: 'SF Mono', ui-monospace, monospace;
    letter-spacing: -0.02em; line-height: 1;
  }
  .pcol-green { color: #16a34a; }
  .pcol-red   { color: #dc2626; }
  .pcol-mkt   { color: #334155; font-size: 2.4rem; }
  .pcol-edge  { font-size: 0.67rem; font-weight: 600; margin-top: 5px; min-height: 1em; }

  .status-dot { display: inline-block; width: 6px; height: 6px; border-radius: 50%; }
  .dot-green  { background: #10b981; animation: pulse 1.5s infinite; }
  .dot-yellow { background: #f59e0b; animation: pulse 1.5s infinite; }
  .dot-red    { background: #ef4444; }
  @keyframes pulse { 0%,100%{opacity:1} 50%{opacity:.3} }

  .detail-grid { display: flex; flex-direction: column; gap: 8px; width: 100%; margin-bottom: 10px; }
  .card {
    background: #fff; border: 1px solid #e2e8f0;
    border-radius: 14px; padding: 18px 20px;
    box-shadow: 0 1px 3px rgba(0,0,0,0.05);
  }
  .card h2 {
    font-size: 0.6rem; color: #94a3b8; text-transform: uppercase;
    letter-spacing: 0.1em; font-weight: 700; margin-bottom: 12px;
    display: flex; align-items: center; gap: 6px;
  }

  label {
    font-size: 0.72rem; font-weight: 500; color: #64748b;
    display: block; margin-bottom: 4px; margin-top: 12px;
  }
  input[type=number], input[type=text] {
    width: 100%; background: #f8fafc; border: 1.5px solid #e2e8f0;
    border-radius: 8px; color: #1e293b; padding: 7px 10px;
    font-family: 'SF Mono', ui-monospace, monospace; font-size: 0.85rem;
    outline: none; transition: border-color 0.15s, box-shadow 0.15s;
  }
  input[type=number]:focus, input[type=text]:focus {
    border-color: #a5b4fc; box-shadow: 0 0 0 3px rgba(99,102,241,0.1); background: #fff;
  }
  input[type=range] { width: 100%; accent-color: #6366f1; cursor: pointer; }

  .sigma-row { display: flex; align-items: center; gap: 8px; margin-top: 4px; }
  .sigma-row input[type=range] { flex: 1; }
  .sigma-num { width: 64px !important; text-align: center; padding: 5px 6px !important; font-size: 0.8rem !important; }

  .auto-iv-btn {
    background: #f1f5f9; border: 1.5px solid #e2e8f0; border-radius: 6px;
    color: #94a3b8; font-family: inherit; font-size: 0.62rem; font-weight: 700;
    padding: 4px 9px; cursor: pointer; white-space: nowrap;
    letter-spacing: 0.06em; transition: all 0.15s; text-transform: uppercase;
  }
  .auto-iv-btn:hover  { border-color: #a5b4fc; color: #6366f1; background: #eef2ff; }
  .auto-iv-btn.active { background: #6366f1; border-color: #6366f1; color: #fff; }

  .formula {
    background: #f8fafc; border: 1.5px solid #e2e8f0; border-radius: 10px;
    padding: 12px 14px; font-size: 0.7rem; color: #64748b; line-height: 2;
    font-family: 'SF Mono', ui-monospace, monospace;
  }
  .formula span { color: #6366f1; font-weight: 600; }
  .d2-val { color: #1e293b; font-weight: 700; }
</style>
</head>
<body>
<div class="page-wrap">

<div class="header">
  <h1>BTC 5 MINUTE UP DOWN</h1>
</div>

<div class="top-section">

  <!-- Row 1: BTC / USD -->
  <div class="row-card" style="text-align:center">
    <div class="row-label"><span class="status-dot dot-yellow" id="dot"></span>BTC / USD &mdash; Binance Live</div>
    <div class="btc-headline">
      <div class="big-price" id="btc-price">&mdash;</div>
      <div class="staleness" id="staleness"></div>
    </div>
    <div class="price-meta" id="price-meta">Connecting&hellip;</div>
  </div>

  <!-- Row 2: Time to Expiry -->
  <div class="row-card timer-card">
    <div class="row-label">Time to Expiry</div>
    <div class="timer-big" id="timer">&mdash;</div>
  </div>

  <!-- Row 3: BS Fair Value -->
  <div class="row-card">
    <div class="row-label">Fair Value &mdash; Black-Scholes</div>
    <div class="price-pair">
      <div class="price-col">
        <div class="pcol-label">Up</div>
        <div class="pcol-val pcol-green" id="bs-up">&mdash;</div>
        <div class="pcol-edge" id="edge-up"></div>
      </div>
      <div class="price-col">
        <div class="pcol-label">Down</div>
        <div class="pcol-val pcol-red" id="bs-down">&mdash;</div>
        <div class="pcol-edge" id="edge-down"></div>
      </div>
    </div>
  </div>

  <!-- Row 4: Polymarket Price -->
  <div class="row-card">
    <div class="row-label">Polymarket Price</div>
    <div class="price-pair">
      <div class="price-col">
        <div class="pcol-label">Up</div>
        <div class="pcol-val pcol-mkt" id="mkt-up-display">&mdash;</div>
      </div>
      <div class="price-col">
        <div class="pcol-label">Down</div>
        <div class="pcol-val pcol-mkt" id="mkt-down-display">&mdash;</div>
      </div>
    </div>
  </div>

</div>

<!-- DETAIL -->
<div class="detail-grid">

  <!-- Market Inputs -->
  <div class="card">
    <h2>Market Inputs</h2>
    <label>Polymarket URL or timestamp</label>
    <input type="text" id="end-ts" placeholder="paste URL or timestamp&hellip;" oninput="updateEndTs()">
    <label>Manual seconds remaining</label>
    <input type="number" id="manual-sec" placeholder="e.g. 240" oninput="setManual()">
    <label>Strike / Price to Beat (K)</label>
    <input type="number" id="strike" placeholder="e.g. 67599.08" step="0.01">
    <label style="display:flex;align-items:center;justify-content:space-between;margin-bottom:4px;margin-top:12px">
      <span>Sigma &mdash; Annual Vol: <strong id="sigma-label" style="color:#6366f1">70.0%</strong></span>
      <button class="auto-iv-btn" id="auto-iv-btn" onclick="toggleAutoIV()">Auto IV</button>
    </label>
    <div class="sigma-row">
      <input type="range" id="sigma" min="0.10" max="2.00" step="0.005" value="0.70" oninput="updateSigmaFromSlider()">
      <input type="number" id="sigma-num" class="sigma-num" min="10" max="200" step="0.1" value="70.0" oninput="updateSigmaFromNum()">
    </div>
    <label>Market Up Price (&cent;)</label>
    <input type="number" id="mkt-up" placeholder="e.g. 51" step="1">
    <label>Market Down Price (&cent;)</label>
    <input type="number" id="mkt-down" placeholder="e.g. 50" step="1">
  </div>

  <!-- Greeks + IV -->
  <div class="card">
    <h2>Greeks &amp; Implied Vol</h2>
    <div class="formula" id="formula">
      d&#8322; = [ln(S/K) + (r &minus; &sigma;&sup2;/2)&middot;T] / (&sigma;&middot;&radic;T)<br>
      Up = N(d&#8322;) &nbsp;&nbsp; Down = N(&minus;d&#8322;)
    </div>
    <div id="iv-output" style="font-size:0.82rem;color:#64748b;line-height:2;margin-top:14px;">
      Enter market prices to compute implied vol.
    </div>
  </div>

</div>

</div><!-- /.page-wrap -->

<script>
// ── CORS proxy (required for Polymarket + Binance REST APIs) ──────────────────
// allorigins.win proxies requests that would otherwise be blocked cross-origin.
const PROXY = url => `https://api.allorigins.win/raw?url=${encodeURIComponent(url)}`;

// ── State ─────────────────────────────────────────────────────────────────────
let endTs         = null;
let startTs       = null;
let manualSec     = null;
let lastBtcPrice  = null;
let lastPriceAt   = null;    // unix ms timestamp of last WS trade
let tradeCount    = 0;
let rolling       = false;
let autoIV        = false;
let lastComputedIV = null;
let currentTokenIds = { up: null, down: null };
let _strikePollTs = 0;

// ── Header fit ────────────────────────────────────────────────────────────────
function fitHeader() {
  const h1 = document.querySelector('.header h1');
  if (!h1) return;
  h1.style.wordSpacing = '0px';
  const targetW = h1.parentElement.clientWidth;
  const naturalW = h1.scrollWidth;
  const words = h1.textContent.trim().split(/\s+/).length;
  const gaps = words - 1;
  if (gaps > 0 && targetW > naturalW)
    h1.style.wordSpacing = ((targetW - naturalW) / gaps) + 'px';
}
document.addEventListener('DOMContentLoaded', fitHeader);
window.addEventListener('resize', fitHeader);

// ── ISO timestamp helper ──────────────────────────────────────────────────────
function toISO(ts) {
  return new Date(ts * 1000).toISOString().slice(0, 19) + 'Z';
}

// ── Binance WebSocket — live BTC price ────────────────────────────────────────
function connectBinanceWS() {
  const ws = new WebSocket('wss://stream.binance.com:9443/ws/btcusdt@aggTrade');

  ws.onopen = () => {
    document.getElementById('dot').className = 'status-dot dot-green';
    document.getElementById('price-meta').textContent = 'Binance aggTrade · connected';
  };

  ws.onmessage = (e) => {
    const d = JSON.parse(e.data);
    lastBtcPrice = parseFloat(d.p);
    lastPriceAt  = Date.now();
    tradeCount++;

    document.getElementById('btc-price').textContent =
      '$' + lastBtcPrice.toLocaleString('en-US', { minimumFractionDigits: 2, maximumFractionDigits: 2 });

    const msAgo = Math.round(Date.now() - lastPriceAt);
    document.getElementById('price-meta').textContent =
      `Binance aggTrade · ${msAgo}ms ago · trade #${tradeCount}`;
    document.getElementById('staleness').innerHTML =
      `<span style="color:#10b981;font-weight:600">✓ Live</span>`;
    document.getElementById('dot').className = 'status-dot dot-green';
  };

  ws.onerror = () => {
    document.getElementById('dot').className = 'status-dot dot-red';
    document.getElementById('staleness').innerHTML =
      '<span style="color:#ef4444;font-weight:600">⚠ WS error</span>';
  };

  ws.onclose = () => {
    document.getElementById('dot').className = 'status-dot dot-yellow';
    document.getElementById('staleness').innerHTML =
      '<span style="color:#f59e0b;font-weight:600">⟳ reconnecting…</span>';
    setTimeout(connectBinanceWS, 2000);
  };
}

// ── Fetch market data (gamma-api via proxy → CLOB for live midpoints) ─────────
async function fetchMarket(start_ts) {
  const slug = `btc-updown-5m-${start_ts}`;
  const r = await fetch(PROXY(`https://gamma-api.polymarket.com/events?slug=${slug}`));
  const data = await r.json();
  if (!data || !data.length) throw new Error(`No market: ${slug}`);

  const market   = data[0].markets[0];
  const prices   = JSON.parse(market.outcomePrices);
  const tokenIds = JSON.parse(market.clobTokenIds);

  // CLOB midpoints have CORS:* — use them directly for the freshest prices
  let upPrice   = parseFloat(prices[0]);
  let downPrice = parseFloat(prices[1]);
  try {
    const [m0, m1] = await Promise.all([
      fetch(`https://clob.polymarket.com/midpoint?token_id=${tokenIds[0]}`).then(r => r.json()),
      fetch(`https://clob.polymarket.com/midpoint?token_id=${tokenIds[1]}`).then(r => r.json()),
    ]);
    if (m0.mid != null) upPrice   = parseFloat(m0.mid);
    if (m1.mid != null) downPrice = parseFloat(m1.mid);
  } catch(e) { /* use gamma prices */ }

  return {
    up_price:   upPrice,
    down_price: downPrice,
    token_ids:  tokenIds,
    active:     market.active,
    closed:     market.closed,
  };
}

// ── Fetch strike (Polymarket crypto-price API via proxy → Binance fallback) ───
async function fetchStrike(start_ts) {
  // Primary: Polymarket's internal crypto-price endpoint (same data as UI shows)
  try {
    const url = `https://polymarket.com/api/crypto/crypto-price?symbol=BTC` +
      `&eventStartTime=${encodeURIComponent(toISO(start_ts))}` +
      `&variant=fiveminute&endDate=${encodeURIComponent(toISO(start_ts + 300))}`;
    const r = await fetch(PROXY(url));
    const d = await r.json();
    if (d.openPrice != null) return { price: d.openPrice, source: 'polymarket' };
  } catch(e) {}

  // Fallback: Binance 1m kline open at window start
  try {
    const url = `https://api.binance.com/api/v3/klines?symbol=BTCUSDT&interval=1m` +
      `&startTime=${start_ts * 1000}&endTime=${(start_ts + 60) * 1000}&limit=1`;
    const r = await fetch(PROXY(url));
    const klines = await r.json();
    if (klines && klines[0]) return { price: parseFloat(klines[0][1]), source: 'binance_kline' };
  } catch(e) {}

  return null;
}

// ── Strike poller — retries every 10s until Polymarket confirms ───────────────
function startStrikePoller(ts) {
  _strikePollTs = ts;
  let attempt = 0;
  const poll = async () => {
    if (_strikePollTs !== ts) return;
    attempt++;
    const result = await fetchStrike(ts);
    if (result) {
      document.getElementById('strike').value = result.price.toFixed(2);
      if (result.source === 'polymarket') {
        console.log(`Strike confirmed (Polymarket): $${result.price.toFixed(2)}`);
        return;  // stop — confirmed
      }
      console.log(`Strike approx (${result.source}): $${result.price.toFixed(2)} — retrying in 10s`);
    }
    const delay = attempt < 30 ? 10000 : 30000;
    setTimeout(poll, delay);
  };
  poll();
}

// ── Roll to next window ────────────────────────────────────────────────────────
async function rollToNext() {
  if (rolling || !startTs) return;
  rolling = true;
  const nextStart = startTs + 300;

  document.getElementById('formula').innerHTML =
    `<span style="color:#6366f1">⟳ Rolling to window ${nextStart}…</span>`;

  if (lastBtcPrice) document.getElementById('strike').value = lastBtcPrice.toFixed(2);

  startTs = nextStart;
  endTs   = nextStart + 300;
  document.getElementById('end-ts').value =
    `https://polymarket.com/event/btc-updown-5m-${nextStart}`;
  document.getElementById('timer').style.fontSize = '4.2rem';
  document.getElementById('timer').style.color    = '#6366f1';

  const pollMarket = async () => {
    try {
      const d = await fetchMarket(nextStart);
      document.getElementById('mkt-up').value   = Math.round(d.up_price   * 100);
      document.getElementById('mkt-down').value = Math.round(d.down_price * 100);
      if (d.token_ids) { currentTokenIds.up = d.token_ids[0]; currentTokenIds.down = d.token_ids[1]; }
      startStrikePoller(nextStart);
      console.log(`Market loaded: up=${d.up_price} down=${d.down_price}`);
      rolling = false;
    } catch(e) {
      setTimeout(pollMarket, 2000);
    }
  };
  pollMarket();
}

// ── Manual controls ───────────────────────────────────────────────────────────
function updateEndTs() {
  const raw = document.getElementById('end-ts').value.trim();
  const urlMatch = raw.match(/btc-updown-5m-([\d]+)/);
  if (urlMatch) { startTs = parseInt(urlMatch[1]); endTs = startTs + 300; manualSec = null; return; }
  const v = parseFloat(raw);
  if (!isNaN(v) && v > 1e9) { startTs = v; endTs = v + 300; manualSec = null; }
}
document.getElementById('end-ts').addEventListener('paste', () => setTimeout(updateEndTs, 50));

function setManual() {
  const v = parseFloat(document.getElementById('manual-sec').value);
  if (!isNaN(v) && v >= 0) { manualSec = v; endTs = null; }
}
function setSigma(v) {
  v = Math.min(Math.max(v, 0.10), 2.00);
  document.getElementById('sigma').value     = v.toFixed(4);
  document.getElementById('sigma-num').value = (v * 100).toFixed(1);
  document.getElementById('sigma-label').textContent = (v * 100).toFixed(1) + '%';
}
function updateSigmaFromSlider() { if (autoIV) toggleAutoIV(); setSigma(parseFloat(document.getElementById('sigma').value)); }
function updateSigmaFromNum()    { if (autoIV) toggleAutoIV(); const v = parseFloat(document.getElementById('sigma-num').value); if (!isNaN(v)) setSigma(v / 100); }
function toggleAutoIV() {
  autoIV = !autoIV;
  document.getElementById('auto-iv-btn').classList.toggle('active', autoIV);
  if (autoIV && lastComputedIV) setSigma(lastComputedIV);
}
function getT() {
  if (endTs)            return Math.max(0, endTs - Date.now() / 1000);
  if (manualSec !== null) return Math.max(0, manualSec);
  return null;
}

// ── Black-Scholes ─────────────────────────────────────────────────────────────
function normCDF(x) {
  const a = [0.254829592, -0.284496736, 1.421413741, -1.453152027, 1.061405429], p = 0.3275911;
  const sign = x >= 0 ? 1 : -1;
  x = Math.abs(x) / Math.sqrt(2);
  const t = 1 / (1 + p * x);
  const y = 1 - (((((a[4]*t+a[3])*t)+a[2])*t+a[1])*t+a[0]) * t * Math.exp(-x*x);
  return 0.5 * (1 + sign * y);
}
function invNormCDF(p) {
  if (p <= 0) return -Infinity; if (p >= 1) return Infinity;
  if (p < 0.5) return -invNormCDF(1 - p);
  const r = p - 0.5, s = r * r;
  const a = [2.515517, 0.802853, 0.010328], b = [1.432788, 0.189269, 0.001308];
  return r + r * (a[0] + s*(a[1]+s*a[2])) / (1 + s*(b[0]+s*(b[1]+s*b[2])));
}
function bsPrice(S, K, T_sec, sigma) {
  if (T_sec <= 0 || S <= 0 || K <= 0 || sigma <= 0) return { up: null, down: null, d2: null };
  const T = T_sec / (365.25 * 24 * 3600), sqrtT = Math.sqrt(T);
  const d2 = (Math.log(S / K) - 0.5 * sigma * sigma * T) / (sigma * sqrtT);
  return { up: normCDF(d2), down: normCDF(-d2), d2, sqrtT };
}
function computeIV(S, K, T_sec, mktUp) {
  if (T_sec <= 0 || mktUp <= 0 || mktUp >= 1) return null;
  const T = T_sec / (365.25*24*3600), sqrtT = Math.sqrt(T), lnSK = Math.log(S/K);
  let lo = 0.01, hi = 10.0;
  for (let i = 0; i < 50; i++) {
    const mid = (lo + hi) / 2;
    const d2 = (lnSK - 0.5*mid*mid*T) / (mid*sqrtT);
    if (normCDF(d2) > mktUp) hi = mid; else lo = mid;
  }
  return (lo + hi) / 2;
}
function fmt(v) { return (v * 100).toFixed(1) + '¢'; }

// ── Main tick ─────────────────────────────────────────────────────────────────
function tick() {
  const T = getT();

  // Stale price warning (WS drives price-meta; just guard here)
  if (lastPriceAt && Date.now() - lastPriceAt > 5000) {
    document.getElementById('staleness').innerHTML =
      '<span style="color:#ef4444;font-weight:600">⚠ Feed stale</span>';
  }

  if (T !== null) {
    if (T < 2) {
      document.getElementById('timer').textContent    = '↻';
      document.getElementById('timer').style.fontSize = '3.5rem';
      document.getElementById('timer').style.color    = '#6366f1';
      document.getElementById('bs-up').textContent    = '—';
      document.getElementById('bs-down').textContent  = '—';
      document.getElementById('edge-up').textContent  = '';
      document.getElementById('edge-down').textContent = '';
      rollToNext();
      return;
    }
    const m = Math.floor(T / 60), s = Math.floor(T % 60);
    document.getElementById('timer').textContent =
      String(m).padStart(2,'0') + ':' + String(s).padStart(2,'0');
    document.getElementById('timer').style.fontSize = '4.2rem';
    document.getElementById('timer').style.color    = '#6366f1';
  }

  const S     = lastBtcPrice;
  const K     = parseFloat(document.getElementById('strike').value);
  if (autoIV && lastComputedIV) setSigma(lastComputedIV);
  const sigma = parseFloat(document.getElementById('sigma').value);
  const T_sec = T;

  if (S && K && sigma && T_sec !== null && T_sec > 2) {
    const { up, down, d2, sqrtT } = bsPrice(S, K, T_sec, sigma);
    document.getElementById('bs-up').textContent   = fmt(up);
    document.getElementById('bs-down').textContent = fmt(down);

    const mktUp   = parseFloat(document.getElementById('mkt-up').value)   / 100;
    const mktDown = parseFloat(document.getElementById('mkt-down').value) / 100;

    if (!isNaN(mktUp)) {
      document.getElementById('mkt-up-display').textContent = `${(mktUp*100).toFixed(1)}¢`;
      const edge = up - mktUp;
      const el = document.getElementById('edge-up');
      el.textContent = (edge >= 0 ? '+' : '') + (edge*100).toFixed(1) + '¢ edge';
      el.style.color = edge >= 0.02 ? '#10b981' : edge <= -0.02 ? '#ef4444' : '#94a3b8';
    }
    if (!isNaN(mktDown)) {
      document.getElementById('mkt-down-display').textContent = `${(mktDown*100).toFixed(1)}¢`;
      const edge = down - mktDown;
      const el = document.getElementById('edge-down');
      el.textContent = (edge >= 0 ? '+' : '') + (edge*100).toFixed(1) + '¢ edge';
      el.style.color = edge >= 0.02 ? '#10b981' : edge <= -0.02 ? '#ef4444' : '#94a3b8';
    }

    document.getElementById('formula').innerHTML =
      `<span>S</span> $${S.toLocaleString('en-US',{minimumFractionDigits:2,maximumFractionDigits:2})} &nbsp;
       <span>K</span> $${K.toLocaleString('en-US',{minimumFractionDigits:2,maximumFractionDigits:2})} &nbsp;
       <span>S−K</span> ${(S-K >= 0?'+':'')}$${(S-K).toFixed(2)}<br>
       <span>σ</span> ${(sigma*100).toFixed(0)}% &nbsp;
       <span>T</span> ${T_sec.toFixed(0)}s &nbsp;
       <span>σ√T</span> ${(sigma*sqrtT).toFixed(5)}<br>
       <span>d₂</span> = <span class="d2-val">${d2.toFixed(4)}</span><br>
       Up = N(d₂) &nbsp;&nbsp; Down = N(−d₂)`;

    if (!isNaN(mktUp) && mktUp > 0 && mktUp < 1) {
      const iv = computeIV(S, K, T_sec, mktUp);
      if (iv) lastComputedIV = iv;
      const ivPct = iv ? (iv*100).toFixed(1) : '—';
      const autoTag = autoIV
        ? `<span style="color:#6366f1;font-size:0.65rem;font-weight:600"> ← driving σ (AUTO IV on)</span>`
        : `<span style="color:#94a3b8;font-size:0.65rem"> (click Auto IV to use)</span>`;
      const edge = up - mktUp;
      document.getElementById('iv-output').innerHTML =
        `Implied Annual Vol: <span style="color:#6366f1;font-weight:700">${ivPct}%</span>${autoTag}
         &nbsp;·&nbsp; Market Up: <span style="color:#6366f1;font-weight:600">${(mktUp*100).toFixed(1)}¢</span><br>
         At σ=${(sigma*100).toFixed(1)}%, BS Up = ${fmt(up)}, market = ${fmt(mktUp)} →
         <span style="color:${edge>0.02?'#10b981':edge<-0.02?'#ef4444':'#94a3b8'};font-weight:600">
           ${edge>0.02?'▲ Up cheap by '+(edge*100).toFixed(1)+'¢':edge<-0.02?'▼ Up rich by '+(-edge*100).toFixed(1)+'¢':'≈ Fairly priced'}
         </span>`;
    }
  }
}

// ── Mid-window market price refresh (every 5s using CLOB midpoints directly) ──
async function refreshMarketPrices() {
  if (!startTs || rolling) return;
  const T = getT();
  if (T === null || T < 2) return;

  // If we have token IDs, use CLOB directly (CORS:* — no proxy needed)
  if (currentTokenIds.up && currentTokenIds.down) {
    try {
      const [m0, m1] = await Promise.all([
        fetch(`https://clob.polymarket.com/midpoint?token_id=${currentTokenIds.up}`).then(r => r.json()),
        fetch(`https://clob.polymarket.com/midpoint?token_id=${currentTokenIds.down}`).then(r => r.json()),
      ]);
      if (m0.mid != null) document.getElementById('mkt-up').value   = Math.round(parseFloat(m0.mid) * 100);
      if (m1.mid != null) document.getElementById('mkt-down').value = Math.round(parseFloat(m1.mid) * 100);
    } catch(e) {}
  } else {
    // No token IDs yet — fetch via proxy to get them
    try {
      const d = await fetchMarket(startTs);
      document.getElementById('mkt-up').value   = Math.round(d.up_price   * 100);
      document.getElementById('mkt-down').value = Math.round(d.down_price * 100);
      if (d.token_ids) { currentTokenIds.up = d.token_ids[0]; currentTokenIds.down = d.token_ids[1]; }
    } catch(e) {}
  }
}

// ── Auto-bootstrap: load current 5-min window on page open ────────────────────
async function autoBootstrap() {
  const nowTs = Math.floor(Date.now() / 1000);
  const currentStart = Math.floor(nowTs / 300) * 300;

  startTs = currentStart;
  endTs   = currentStart + 300;
  document.getElementById('end-ts').value =
    `https://polymarket.com/event/btc-updown-5m-${currentStart}`;

  const waitForMarket = async () => {
    try {
      const d = await fetchMarket(currentStart);
      document.getElementById('mkt-up').value   = Math.round(d.up_price   * 100);
      document.getElementById('mkt-down').value = Math.round(d.down_price * 100);
      if (d.token_ids) { currentTokenIds.up = d.token_ids[0]; currentTokenIds.down = d.token_ids[1]; }
      startStrikePoller(currentStart);
    } catch(e) {
      setTimeout(waitForMarket, 2000);
    }
  };
  waitForMarket();
}

// ── Start everything ──────────────────────────────────────────────────────────
connectBinanceWS();
setInterval(tick, 250);
setInterval(refreshMarketPrices, 5000);
autoBootstrap();
tick();
</script>
</body>
</html>
