<div class="prb-slide">

<h1>Network KPI Aggregation &amp; PRB Capacity Proxy</h1>

<span class="subtitle">Baseline RAN state: mean PRB ≈ 20%, P95 median ≈ 34%, absolute max 74.68% — below the 80% planning cap.</span>

<!-- Gauge geometry: fill and reserved zone are track children; markers, cap
     line/label and buffer bracket are gauge-wrap children positioned from
     custom.css (wrap-child placement avoids clipping by the track's
     overflow:hidden). Marker scale positions (left:%) live in custom.css. -->
<div class="gauge-wrap">
<div class="gauge-track">
<div class="gauge-fill"></div>
<div class="gauge-reserved"><span class="zone-label">Reserved headroom</span></div>
</div>
<div class="gauge-marker"><span class="m-label">Mean 20.29%</span></div>
<div class="gauge-marker is-p95"><span class="m-label">Median of cell P95s · 33.97%</span></div>
<div class="gauge-marker is-max"><span class="m-label">Max 74.68%</span></div>
<div class="gauge-cap-line"></div>
<div class="gauge-cap-label">80% hard cap</div>
<div class="gauge-buffer"><span class="b-label">5.32 pp buffer</span></div>
<div class="gauge-scale"><span>0%</span><span>50%</span><span>100%</span></div>
</div>

<div class="metrics-row">
<div class="metric-card">
<span class="val">731</span>
<span class="lbl">Cells analyzed</span>
<span class="sub">From 21,965 daily RAN KPI rows</span>
</div>
<div class="metric-card success">
<span class="val">0 ✓</span>
<span class="lbl">Cells CONSTRAINED</span>
<span class="sub">Zero exceed the 80% threshold</span>
</div>
<div class="metric-card danger">
<span class="val">5.32 pp</span>
<span class="lbl">Baseline safety buffer</span>
<span class="sub">Max 74.68% vs 80% cap</span>
</div>
</div>

<p class="result-band">The 80% rule becomes a permanent safeguard for post-migration simulation — but at baseline, no cell triggers it.</p>

</div>

Note:
With capacity being one of the five decision dimensions, the RAN baseline must be measured explicitly. The pipeline aggregated 21,965 daily RAN KPI records across 731 unique cells into monthly cell-level metrics. Four indicators were computed per cell: mean PRB utilisation, P95 PRB utilisation, maximum PRB utilisation, and average downlink throughput. The P95 was chosen as the primary load indicator because it captures sustained high-load behaviour while remaining robust to isolated anomalies; the maximum captures worst-case saturation. A cell is classified as CONSTRAINED if either its P95 or its maximum reaches the 80% planning threshold. The result is unambiguous: at baseline, zero cells are CONSTRAINED. The population mean PRB utilisation is 20.29%, the median of cell P95s is 33.97%, and the absolute maximum observed anywhere in the footprint is 74.68% — 5.32 percentage points below the 80% operational cap. This is a major finding. It means the 80% rule does not act as a filter on the current subscriber base — it acts as a permanent safeguard that will be enforced during the post-migration capacity simulation you will see later. Right now, the binding constraint on the FWA campaign is radio coverage, not capacity headroom.
