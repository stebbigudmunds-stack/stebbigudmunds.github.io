# stebbigudmunds.github.io
Shoulder Instability
[shoulder-instability-simple.html](https://github.com/user-attachments/files/34503577/shoulder-instability-simple.html)
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>Shoulder instability simple</title>
<style>
  :root {
    --bg:#f4f5f3; --card:#fff; --ink:#1c2321; --muted:#5d6864; --line:#d9dedb; --accent:#17594a;
    --ok:#1f7a5c; --ok-bg:#dff1ea; --warn:#8f5d00; --warn-bg:#fbeecb; --bad:#a8322a; --bad-bg:#f9dfdc; --neutral-bg:#e9ecea;
  }
  @media (prefers-color-scheme: dark) {
    :root {
      --bg:#141817; --card:#1e2422; --ink:#e8ecea; --muted:#9daaa5; --line:#35403c; --accent:#6fcdb3;
      --ok:#6fcdb3; --ok-bg:#183a30; --warn:#eebf62; --warn-bg:#3d3012; --bad:#f19a92; --bad-bg:#47211e; --neutral-bg:#2a322f;
    }
  }
  * { box-sizing:border-box; }
  body { margin:0; background:var(--bg); color:var(--ink); font:16px/1.5 -apple-system,BlinkMacSystemFont,"Segoe UI",Roboto,sans-serif; }
  .wrap { max-width:640px; margin:auto; padding:24px 16px 40px; }
  h1 { font-size:25px; margin:0; letter-spacing:-.01em; }
  .sub { color:var(--muted); font-size:14px; margin:4px 0 16px; }
  .card { background:var(--card); border:1px solid var(--line); border-radius:12px; padding:16px; margin-bottom:12px; }
  h2 { font-size:16px; margin:0 0 12px; }
  .grid { display:grid; grid-template-columns:1fr 1fr; gap:12px; }
  label.f { display:grid; gap:3px; font-size:14px; align-content:start; }
  label.f small { color:var(--muted); font-size:12.5px; }
  input[type=number], select { width:100%; padding:9px 10px; font:inherit; color:inherit; background:var(--bg); border:1px solid var(--line); border-radius:7px; }
  input:focus-visible, select:focus-visible, button:focus-visible, summary:focus-visible, a:focus-visible { outline:2px solid var(--accent); outline-offset:1px; }
  .check { display:flex; gap:9px; align-items:flex-start; font-size:14px; margin-top:12px; }
  .check input { width:18px; height:18px; margin:2px 0 0; flex:none; accent-color:var(--accent); }
  .check small { display:block; color:var(--muted); font-size:12.5px; }
  details { font-size:14px; margin-top:12px; }
  summary { cursor:pointer; font-weight:600; color:var(--accent); }
  details ul { margin:6px 0 0; padding-left:18px; }
  details li { margin:3px 0; }
  .pill { display:inline-block; padding:4px 12px; border-radius:99px; font-weight:700; font-size:14px; }
  .pill.ok { color:var(--ok); background:var(--ok-bg); } .pill.warn { color:var(--warn); background:var(--warn-bg); }
  .pill.bad { color:var(--bad); background:var(--bad-bg); } .pill.neutral { color:var(--muted); background:var(--neutral-bg); }
  .result { border-left:5px solid var(--accent); }
  .kicker { font-size:12px; color:var(--muted); text-transform:uppercase; letter-spacing:.05em; margin-top:14px; }
  .proc { font-size:24px; font-weight:700; line-height:1.2; margin:2px 0 8px; }
  .result p { margin:6px 0; font-size:15px; }
  .calc { font-size:14px; font-variant-numeric:tabular-nums; margin:10px 0 0; display:grid; grid-template-columns:auto 1fr; gap:3px 12px; }
  .calc dt { color:var(--muted); } .calc dd { margin:0; }
  svg { display:block; width:100%; height:auto; margin-top:12px; }
  svg text { fill:var(--ink); font:12px -apple-system,BlinkMacSystemFont,"Segoe UI",sans-serif; }
  .senior { background:var(--warn-bg); border-color:transparent; }
  .senior h2 { margin-bottom:4px; }
  .senior ul { margin:0; padding-left:18px; font-size:14.5px; } .senior li { margin:3px 0; }
  .err { color:var(--bad); font-weight:600; margin:0; }
  .muted { color:var(--muted); font-size:14px; margin:0; }
  .foot { color:var(--muted); font-size:13px; margin:16px 2px 0; }
  .foot a { color:var(--accent); }
  button { font:inherit; font-size:14px; padding:6px 12px; color:inherit; background:var(--card); border:1px solid var(--line); border-radius:7px; cursor:pointer; }
  button:hover { border-color:var(--accent); }
  .btns { display:flex; gap:6px; margin-bottom:12px; }
  @media (max-width:420px) { .grid { gap:10px; } .proc { font-size:21px; } }
</style>
</head>
<body>
<div class="wrap">
  <h1>Shoulder instability simple</h1>
  <p class="sub">For recurrent traumatic anterior instability with symptoms despite rehabilitation. Not for first-time dislocation, or for posterior, multidirectional or voluntary instability: discuss those with your supervisor.</p>

  <div class="btns">
    <button type="button" id="example">Show an example</button>
    <button type="button" id="clear">Clear</button>
  </div>

  <form id="f" autocomplete="off">
    <div class="card">
      <h2>1. Measure on CT (mm)</h2>
      <div class="grid">
        <label class="f">Glenoid diameter (D) <input type="number" name="D" min="0" step="0.1" inputmode="decimal"></label>
        <label class="f">Glenoid bone loss (d) <input type="number" name="d" min="0" step="0.1" inputmode="decimal"><small>0 if none</small></label>
        <label class="f">Hill-Sachs width <input type="number" name="hsw" min="0" step="0.1" inputmode="decimal"><small>0 if no lesion</small></label>
        <label class="f">Bone bridge <input type="number" name="bb" min="0" step="0.1" inputmode="decimal"></label>
      </div>
      <details>
        <summary>How to measure</summary>
        <ul>
          <li><b>D:</b> on the 3D en face glenoid view, draw a best-fit circle on the inferior glenoid. Its diameter is D. Use the other shoulder if the circle is hard to fit.</li>
          <li><b>d:</b> the width of glenoid missing from the anterior edge of that circle.</li>
          <li><b>Hill-Sachs width:</b> measured on the posterior 3D view of the humeral head, across the lesion from medial to lateral.</li>
          <li><b>Bone bridge:</b> the intact bone between the rotator cuff attachment and the lateral edge of the Hill-Sachs lesion.</li>
        </ul>
      </details>
    </div>

    <div class="card">
      <h2>2. Patient</h2>
      <div class="grid">
        <label class="f">Age <input type="number" name="age" min="0" max="110" step="1" inputmode="numeric"></label>
        <label class="f">Sport
          <select name="sport">
            <option value="0">None or low-risk recreational</option>
            <option value="1">Recreational contact / overhead</option>
            <option value="2">Competitive, other</option>
            <option value="3">Competitive contact / overhead</option>
          </select>
        </label>
      </div>
      <label class="check"><input type="checkbox" name="lax"><span>Hyperlaxity<small>Beighton 4 or more of 9, or external rotation at the side over 85&deg;</small></span></label>
      <label class="check"><input type="checkbox" name="failed"><span>Previous stabilisation has failed</span></label>
    </div>
  </form>

  <div id="out" aria-live="polite"></div>

  <p class="foot">Teaching and decision support only. It has not been clinically validated, so confirm every plan with your supervising surgeon. Nothing you enter is stored or sent. <a href="shoulder-instability.html">Open the full version</a> for ISIS, GTIMS, function and soft-tissue factors.</p>
</div>

<script>
/* ---------- Pure logic: no DOM access, so it can be tested directly ---------- */
const OP = {
  BANKART: 'Arthroscopic Bankart repair',
  BR: 'Arthroscopic Bankart + remplissage',
  LAT: 'Latarjet',
  FREE: 'Free bone block (iliac crest or distal tibial allograft)',
};
const LIMITS = { sub: 13.5, crit: 20, near: 8, high: 3 };

function plan(i) {
  const num = v => (v === '' || v === null || v === undefined || Number.isNaN(+v)) ? null : +v;
  const D = num(i.D), d = num(i.d), hsw = num(i.hsw), bb = num(i.bb), age = num(i.age);
  const r = { missing: [], errors: [], add: [], senior: [] };

  if (D === null) r.missing.push('glenoid diameter');
  if (d === null) r.missing.push('glenoid bone loss');
  if (hsw === null) r.missing.push('Hill-Sachs width');
  if (hsw !== 0 && bb === null) r.missing.push('bone bridge');
  if (age === null) r.missing.push('age');
  if (D !== null && D <= 0) r.errors.push('Glenoid diameter must be greater than 0.');
  if (D !== null && d !== null && d >= D) r.errors.push('Glenoid bone loss must be smaller than the glenoid diameter.');
  if ([d, hsw, bb].some(v => v !== null && v < 0)) r.errors.push('Measurements cannot be negative.');
  if (r.missing.length || r.errors.length) return r;

  r.noHS = hsw === 0;
  r.D = D; r.d = d; r.hsw = hsw; r.bb = bb;
  r.gbl = d / D * 100;
  r.gt = 0.83 * D - d;
  r.hsi = r.noHS ? 0 : hsw + (bb || 0);
  r.dtd = r.gt - r.hsi;
  r.gtAfter = 0.83 * D;
  r.zone = r.noHS ? 'none' : r.hsi >= r.gt ? 'off' : r.dtd < LIMITS.near ? 'near' : 'central';
  r.risk = (age <= 20 ? 2 : 0) + (+i.sport || 0) + (i.lax ? 1 : 0);
  const high = r.high = r.risk >= LIMITS.high;
  const off = r.zone === 'off', near = r.zone === 'near';
  const pct = r.gbl.toFixed(1) + '%';

  if (i.failed) {
    r.op = 'Revision: plan with a senior';
    r.why = 'A failed stabilisation needs its own work-up. Latarjet is the usual choice after a failed soft-tissue repair, and a free bone block after a failed Latarjet.';
    r.cls = 'revision';
  } else if (r.gbl >= 40) {
    r.op = OP.FREE; r.cls = 'bone';
    r.why = 'Bone loss of ' + pct + ' may be more than a coracoid graft can restore.';
    r.senior.push('Bone loss is very large. Plan the graft with a senior.');
  } else if (r.gbl >= LIMITS.crit) {
    r.op = OP.LAT; r.cls = 'bone';
    r.why = 'Bone loss of ' + pct + ' is above the critical level of ' + LIMITS.crit + '%, so the glenoid needs bone restored.';
  } else if (r.gbl >= LIMITS.sub) {
    if (off || high) {
      r.op = OP.LAT; r.cls = 'bone';
      r.why = 'Moderate bone loss (' + pct + ') together with ' + (off ? 'an off-track lesion' : 'a high-risk patient') + '.';
    } else {
      r.op = OP.BR; r.cls = 'soft';
      r.why = 'Moderate bone loss (' + pct + ') in a lower-risk patient. A Bankart repair alone gives poorer function above about ' + LIMITS.sub + '%, so remplissage is added.';
    }
  } else if (off) {
    if (high) {
      r.op = OP.LAT; r.cls = 'bone';
      r.why = 'Off-track lesion in a high-risk patient.';
    } else {
      r.op = OP.BR; r.cls = 'soft';
      r.why = 'Off-track lesion with little glenoid bone loss in a lower-risk patient, so remplissage fills the humeral defect.';
      r.senior.push('Some surgeons prefer Latarjet for all off-track lesions.');
    }
  } else if (near) {
    if (high) {
      r.op = OP.LAT; r.cls = 'bone';
      r.why = 'The lesion is close to the edge of the track and the patient is high risk.';
    } else {
      r.op = OP.BR; r.cls = 'soft';
      r.why = 'On-track, but close to the edge of the track, where a Bankart repair alone fails more often.';
    }
  } else {
    r.op = OP.BANKART; r.cls = 'soft';
    const place = r.noHS ? 'no Hill-Sachs lesion' : 'a lesion well inside the track';
    if (high) {
      r.why = 'Little bone loss and ' + place + ', but the patient is high risk.';
      r.senior.push('High-risk patient: discuss whether to add remplissage or choose Latarjet.');
    } else {
      r.why = 'Little bone loss and ' + place + ' in a lower-risk patient.';
    }
  }

  if (r.cls === 'bone' && !r.noHS) {
    if (r.hsi >= r.gtAfter) r.add.push('Remplissage or another humeral procedure: the lesion stays off-track even with a fully restored glenoid.');
  }
  if (r.cls === 'soft' && i.lax) r.add.push('Capsular plication or shift, because of the hyperlaxity.');

  if (!r.noHS && Math.abs(r.dtd) < 2) r.senior.push('The result is within 2 mm of the on/off-track line, which is close to measurement error. Re-measure.');
  if (D < 15 || D > 45) r.senior.push('A glenoid diameter of ' + D + ' mm is unusual. Check the measurement.');
  if (age >= 40) r.senior.push('Age 40 or over: check the rotator cuff and axillary nerve.');
  return r;
}

if (typeof module !== 'undefined' && module.exports) module.exports = { plan, OP };
</script>

<script>
/* ---------- UI ---------- */
if (typeof document !== 'undefined') {
  const form = document.getElementById('f');
  const out = document.getElementById('out');
  const ZONE = {
    off: ['Off-track', 'bad'], near: ['On-track, near the edge', 'warn'],
    central: ['On-track', 'ok'], none: ['No Hill-Sachs lesion', 'neutral'],
  };
  const clamp = (v, a, b) => Math.max(a, Math.min(b, v));
  const f1 = n => n.toFixed(1);

  function bar(r) {
    const W = 480, L = 10, R = 470, gt = Math.max(r.gt, 0);
    const maxV = Math.max(r.hsi, gt, 1) * 1.2;
    const x = v => L + (R - L) * clamp(v, 0, maxV) / maxV;
    const lbl = (v, y, t, s) => '<text x="' + clamp(x(v), 60, W - 60) + '" y="' + y + '" text-anchor="middle" style="' + (s || '') + '">' + t + '</text>';
    return '<svg viewBox="0 0 ' + W + ' 72" role="img" aria-label="Hill-Sachs interval ' + f1(r.hsi) + ' mm compared with glenoid track ' + f1(r.gt) + ' mm">' +
      '<rect x="' + L + '" y="24" width="' + (x(gt) - L) + '" height="20" style="fill:var(--ok-bg)"/>' +
      '<rect x="' + x(gt) + '" y="24" width="' + (R - x(gt)) + '" height="20" style="fill:var(--bad-bg)"/>' +
      '<line x1="' + x(gt) + '" x2="' + x(gt) + '" y1="20" y2="50" style="stroke:var(--ink);stroke-width:2"/>' +
      lbl(gt, 64, 'Track ' + f1(r.gt)) +
      '<line x1="' + x(r.hsi) + '" x2="' + x(r.hsi) + '" y1="16" y2="46" style="stroke:var(--accent);stroke-width:4"/>' +
      lbl(r.hsi, 12, 'Lesion ' + f1(r.hsi), 'font-weight:700') + '</svg>';
  }

  function render() {
    const v = {};
    for (const el of form.elements) if (el.name) v[el.name] = el.type === 'checkbox' ? el.checked : el.value;
    const r = plan(v);

    if (r.errors.length) { out.innerHTML = '<div class="card">' + r.errors.map(e => '<p class="err">' + e + '</p>').join('') + '</div>'; return; }
    if (r.missing.length) { out.innerHTML = '<div class="card"><p class="muted">Still needed: ' + r.missing.join(', ') + '.</p></div>'; return; }

    const z = ZONE[r.zone];
    let h = '<div class="card result"><span class="pill ' + z[1] + '">' + z[0] + '</span>';
    h += '<div class="kicker">Suggested operation</div><div class="proc">' + r.op + '</div><p>' + r.why + '</p>';
    if (r.add.length) h += '<p><b>Add:</b> ' + r.add.join(' ') + '</p>';
    h += '<dl class="calc">' +
      '<dt>Glenoid track</dt><dd>0.83 &times; ' + r.D + ' &minus; ' + r.d + ' = <b>' + f1(r.gt) + ' mm</b></dd>';
    if (!r.noHS) {
      h += '<dt>Hill-Sachs interval</dt><dd>' + r.hsw + ' + ' + r.bb + ' = <b>' + f1(r.hsi) + ' mm</b></dd>' +
        '<dt>Compare</dt><dd>' + f1(r.hsi) + (r.hsi >= r.gt ? ' &ge; ' : ' &lt; ') + f1(r.gt) + ': <b>' + (r.zone === 'off' ? 'off-track' : 'on-track') + '</b></dd>';
    }
    h += '<dt>Glenoid bone loss</dt><dd>' + r.d + ' &divide; ' + r.D + ' = <b>' + f1(r.gbl) + '%</b></dd>' +
      '<dt>Patient risk</dt><dd><b>' + r.risk + '/6</b>, ' + (r.high ? 'high' : 'lower') + '</dd></dl>';
    if (!r.noHS) h += bar(r);
    h += '</div>';
    if (r.senior.length) h += '<div class="card senior"><h2>Discuss with a senior</h2><ul>' + r.senior.map(s => '<li>' + s + '</li>').join('') + '</ul></div>';
    out.innerHTML = h;
  }

  function clearForm() {
    for (const el of form.elements) {
      if (!el.name) continue;
      if (el.type === 'checkbox') el.checked = false;
      else if (el.tagName === 'SELECT') el.selectedIndex = 0;
      else el.value = '';
    }
  }
  document.getElementById('example').addEventListener('click', () => {
    clearForm();
    const e = { D: 28, d: 2, hsw: 14, bb: 9, age: 27, sport: '1' };
    for (const k in e) form.elements[k].value = e[k];
    render();
  });
  document.getElementById('clear').addEventListener('click', () => { clearForm(); render(); });
  form.addEventListener('input', render);
  form.addEventListener('submit', e => e.preventDefault());
  render();
}
</script>
</body>
</html>
