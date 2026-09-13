<div class="backup-slide b5">

<span class="backup-badge">Backup slide · B5</span>

<h1>Capacity Simulation — Assumptions &amp; Sensitivity</h1>

<span class="subtitle">PRB proxy model — engineering boundary conditions, formula chain, and robustness scenarios.</span>

<div class="formula-strip">
<span class="fs-step">GB</span>
<span class="fs-arrow">→</span>
<span class="fs-step">throughput</span>
<span class="fs-arrow">→</span>
<span class="fs-step">× offer multiplier</span>
<span class="fs-arrow">→</span>
<span class="fs-step">÷ cell throughput</span>
<span class="fs-arrow">→</span>
<span class="fs-step">× 100</span>
<span class="fs-arrow">→</span>
<span class="fs-step">% uplift</span>
<span class="fs-arrow">→</span>
<span class="fs-step">cap at 15%</span>
</div>

<div class="two-col">
<div>
<span class="col-label">Five modelling assumptions</span>
<ul class="asm-list">
<li><span class="asm-idx">1</span><span>Uniform 30-day distribution: monthly GB converted to continuous throughput assuming even daily demand; P95 baseline partially compensates for peak-hour concentration.</span></li>
<li><span class="asm-idx">2</span><span>Spectral efficiency parity: FWA CPE assumed to achieve current cell-average throughput per PRB — conservative, since outdoor CPE typically outperforms indoor handsets.</span></li>
<li><span class="asm-idx">3</span><span>P95 baseline: cell load measured at P95, not mean — flags cells approaching saturation even when average appears low.</span></li>
<li><span class="asm-idx">4</span><span>Offer-based traffic multiplier: 1.0 base-only, 1.25 single add-on, 1.5 multi-addon — a proxy for value-add traffic growth.</span></li>
<li><span class="asm-idx">5</span><span>Cumulative cell-level gate: enforced on (baseline P95 + Σ subscriber uplifts), capturing aggregate cell load — not per-subscriber isolation.</span></li>
</ul>
</div>
<div>
<span class="col-label">Sensitivity scenarios</span>
<table class="sens-table">
<thead>
<tr><th>Scenario</th><th>Max cell PRB</th><th>Status</th></tr>
</thead>
<tbody>
<tr><td>Baseline</td><td class="pct">68.26%</td><td class="status">11.74 pp below cap</td></tr>
<tr><td>Peak-demand ×1.2</td><td class="pct">68.84%</td><td class="status">11.16 pp below cap</td></tr>
<tr><td>Peak-demand ×1.5</td><td class="pct">69.70%</td><td class="status">10.30 pp below cap</td></tr>
<tr><td>No 15% cap</td><td class="pct">68.26%</td><td class="status">cap not triggered</td></tr>
</tbody>
</table>
</div>
</div>

<div class="boundary-band">
<span class="lead">Honest boundary:</span>
<span class="main">The PRB proxy model sacrifices physical-layer granularity in exchange for scalability, transparency, and reproducibility. It is a screening tool — not a substitute for vendor-grade RAN simulations during deployment.</span>
</div>

<p class="footer-note">The 15% per-subscriber cap serves as a numerical stabiliser: it was not triggered for any subscriber (maximum raw uplift 1.90%).</p>

</div>
