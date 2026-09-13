<div class="temporal-slide">

<h1>Temporal Standardisation</h1>

<span class="subtitle">One monthly axis for the ABT — while preserving daily resolution for feature engineering.</span>

<div class="before-after">
<div class="panel before">
<span class="panel-title">Heterogeneous grains</span>
<ul>
<li>T1 — daily (snapshot_date)</li>
<li>T3 — daily (kpi_date)</li>
<li>T2 — monthly (snapshot_month)</li>
<li>T5 — monthly (month)</li>
</ul>
</div>
<div class="transform-arrow">→</div>
<div class="panel after">
<span class="panel-title">Unified monthly key</span>
<span class="unified-key">snapshot_month = 2026-01-01</span>
<span class="annotation">All 4 tables aligned · 4 row counts preserved</span>
</div>
</div>

<div class="dual-grain">
<div class="card"><strong>T1 · Daily table</strong><span class="retained">Retained: snapshot_date</span><br>Required for zero-volume imputation &amp; peak-hour ratio.</div>
<div class="card"><strong>T3 · RAN KPI</strong><span class="retained">Retained: kpi_date</span><br>Required for temporal alignment validation.</div>
<div class="strip-footer">Both tables also carry snapshot_month for ABT joins.</div>
</div>

<p class="validation-band">Three assertions passed: 0 nulls · day-of-month = 01 · exactly one distinct month per table.</p>

</div>

Note:
Cleaned data is not the same as aligned data. The five source tables originally carried four different temporal resolutions: T1 and T3 are recorded at daily grain, with snapshot_date and kpi_date columns respectively; T2 and T5 are already monthly, but under different column names. Before any join could happen, all four tables were standardised to a single monthly key: snapshot_month, set to January 2026. But — and this is the key architectural decision — the daily columns were not discarded. T1's snapshot_date and T3's kpi_date are retained because two downstream features require the original daily resolution: zero-volume imputation and the peak-hour traffic ratio. This dual-grain design solves two competing requirements simultaneously: the ABT demands one monthly grain to prevent Cartesian fan-out, while feature engineering needs the underlying daily signal intact. Three programmatic assertions validated the result: zero null snapshot_month values, day-of-month always equal to the first, and exactly one distinct month per table. All passed. What we now have is a temporally consistent foundation — the base on which every feature and every subscriber-month record is built.
