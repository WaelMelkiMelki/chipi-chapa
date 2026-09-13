<div class="abt-slide">

<h1>The Analytical Base Table</h1>

<span class="subtitle">Where five sources converge into one subscriber-month decision layer.</span>

<div class="convergence">
<div class="source-stack">
<span class="source-chip">T1 · Usage + device</span>
<span class="source-chip">T2 · CRM anchor</span>
<span class="source-chip">T3 · RAN KPIs</span>
<span class="source-chip">T4 · Coverage</span>
<span class="source-chip">T5 · Service consumption</span>
</div>
<div class="arrow-cone">
<span>→</span>
<span>→</span>
<span>→</span>
<span>→</span>
<span>→</span>
</div>
<div class="abt-banner">
<span class="lead">one row per subscriber per month</span>
<span class="stat">12,412 rows · 50 columns · 7 dimensions</span>
<span class="schema">cleaned_data.abt_subscriber_month</span>
</div>
</div>

<div class="inventory">
<div class="dim-card">
<span class="dim-name">Keys</span>
<span class="dim-count">3</span>
<span class="dim-sub">subscriber · month · address</span>
</div>
<div class="dim-card">
<span class="dim-name">Commercial</span>
<span class="dim-count">15</span>
<span class="dim-sub">CRM attributes</span>
</div>
<div class="dim-card">
<span class="dim-name">Usage</span>
<span class="dim-count">4</span>
<span class="dim-sub">monthly usage</span>
</div>
<div class="dim-card">
<span class="dim-name">Device</span>
<span class="dim-count">3</span>
<span class="dim-sub">generation · cell · 5G flag</span>
</div>
<div class="dim-card">
<span class="dim-name">Coverage</span>
<span class="dim-count">8</span>
<span class="dim-sub">RSRP · SINR · feasibility</span>
</div>
<div class="dim-card">
<span class="dim-name">Service</span>
<span class="dim-count">11</span>
<span class="dim-sub">streaming · gaming · VoIP · IPTV</span>
</div>
<div class="dim-card">
<span class="dim-name">Capacity</span>
<span class="dim-count">6</span>
<span class="dim-sub">PRB · throughput · status</span>
</div>
</div>

<p class="footer-line">Row-count preservation validated at each join — no fan-out, no null introduction, no duplicated subscribers.</p>

</div>

Note:
The Analytical Base Table is the integration layer of the pipeline. Its role is not merely technical — it is the decision layer that ensures every downstream module reads from the same subscriber-month grain. The ABT consolidates five feature groups into a single table. Commercial attributes from the CRM anchor: fifteen columns. Usage behaviour from T1: four columns. Device dominance: three columns. Address-level coverage: eight columns. Service consumption: eleven columns. Network capacity context from RAN KPIs: six columns. Plus three key columns — subscriber identifier, monthly snapshot, address. That is fifty columns in total, organised into seven logical dimensions. The unifying grain is one row per subscriber per month, which is enforced by validating row-count preservation at every join step. This is critical: a fan-out at any join would multiply subscriber records and create false observations; null introduction would force imputation or record loss downstream. Both failure modes would bias scoring, segmentation, churn modelling, and capacity simulation. By validating each join against the expected cardinality, the ABT preserves exactly twelve thousand four hundred and twelve subscriber-month rows with zero duplicates and zero null introduction. This is the foundation on which every decision module operates.
