<div class="backup-slide b6">

<span class="backup-badge">Backup slide · B6</span>

<h1>Household Multiplier &amp; Uncapped Rationale</h1>

<span class="subtitle">Why the final_priority_score is multiplied by raw num_active_lines — and why capping it would be wrong.</span>

<div class="two-col">
<div>
<span class="col-label">The multiplier in context</span>
<ul class="ctx-list">
<li><span class="ctx-key">Purpose —</span>The final_priority_score = Base_Score × num_active_lines. It reflects the fact that a single CPE serves an entire home or office — the same hardware cost, multiplied revenue consolidation.</li>
<li><span class="ctx-key">Uncapped by design —</span>Capping at P95 (4 lines) would under-value a 14-line SME account by approximately 3.5× — the same CPE dispatch serves 14 mobile plans.</li>
<li><span class="ctx-key">Safe by construction —</span>Only 3.5% of subscribers have more than 5 lines, all concentrated in the 10–14 line B2B tail (no subscribers at 5–9 lines). 2.2% carry 12+ lines (P99 = 13, max = 14) — all legitimate business accounts.</li>
</ul>
</div>
<div>
<span class="col-label">Line-count distribution evidence</span>
<table class="pct-table">
<thead>
<tr><th>Stat</th><th>Value</th></tr>
</thead>
<tbody>
<tr><td>Mean lines</td><td>1.81</td></tr>
<tr><td>P50</td><td>1 line</td></tr>
<tr><td>P75</td><td>2 lines</td></tr>
<tr><td>P90</td><td>3 lines</td></tr>
<tr><td>P95</td><td>4 lines</td></tr>
<tr><td>P99</td><td>13 lines</td></tr>
<tr><td>Max</td><td>14 lines</td></tr>
</tbody>
</table>
<span class="pct-caption">No subscribers observed at 5–9 lines — the tail concentrates at 10–14 lines.</span>
</div>
</div>

<div class="routing-block">
<div class="routing-card b2b">
<span class="rc-name">B2B / SME</span>
Multi-line accounts (num_active_lines &gt; 2) → Key Account Managers for dedicated sales cycles.
</div>
<div class="routing-card b2c">
<span class="rc-name">B2C</span>
Single-line and standard household accounts → mass-market outbound telemarketing center.
</div>
</div>
<span class="routing-caption">The score itself is not used as a direct dialling order across these two channels.</span>

<div class="top5-strip">
<span class="top5-label">Top-5 final scores — uncapped multiplier effect</span>
<div class="top5-row">
<div class="top5-chip">
<span class="t5-rank">#1</span>
<span class="t5-score">1,273.66</span>
<span class="t5-lines">14 lines</span>
</div>
<div class="top5-chip">
<span class="t5-rank">#2</span>
<span class="t5-score">1,217.35</span>
<span class="t5-lines">14 lines</span>
</div>
<div class="top5-chip">
<span class="t5-rank">#3</span>
<span class="t5-score">1,137.04</span>
<span class="t5-lines">14 lines</span>
</div>
<div class="top5-chip">
<span class="t5-rank">#4</span>
<span class="t5-score">1,114.84</span>
<span class="t5-lines">12 lines</span>
</div>
<div class="top5-chip">
<span class="t5-rank">#5</span>
<span class="t5-score">1,100.00</span>
<span class="t5-lines">11 lines</span>
</div>
</div>
<span class="top5-note">All top-5 are 11–14 line B2B accounts — median eligible score is 44.75.</span>
</div>

<p class="footer-note">Uncapped multiplier is validated by the absence of a middle-tail (5–9 lines) — the distribution is bimodal, not skewed.</p>

</div>
