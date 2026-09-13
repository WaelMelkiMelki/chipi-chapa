<div class="backup-slide b3">

<span class="backup-badge">Backup slide · B3</span>

<h1>ABT Join Sequence &amp; Grain Preservation</h1>

<span class="subtitle">Six sequential joins, five cardinality guarantees, zero row-count violation.</span>

<div class="two-col">
<div>
<span class="col-label">Six joins (in order)</span>
<div class="join-row first">
<span class="j-idx">1</span>
<span class="j-name">t2_commercial_features</span>
<span class="j-card">1:1</span>
<span class="j-on">anchor · 12,412 rows</span>
</div>
<div class="join-row">
<span class="j-idx">2</span>
<span class="j-name">LEFT JOIN t1_usage_aggregates</span>
<span class="j-card">1:1</span>
<span class="j-on">on subscriber_id + snapshot_month</span>
</div>
<div class="join-row">
<span class="j-idx">3</span>
<span class="j-name">LEFT JOIN t1_dominant_service</span>
<span class="j-card">1:1</span>
<span class="j-on">on subscriber_id + snapshot_month</span>
</div>
<div class="join-row">
<span class="j-idx">4</span>
<span class="j-name">LEFT JOIN t4_coverage_features</span>
<span class="j-card">N:1</span>
<span class="j-on">on address_id</span>
</div>
<div class="join-row">
<span class="j-idx">5</span>
<span class="j-name">LEFT JOIN t5_service_consumption</span>
<span class="j-card">1:1</span>
<span class="j-on">on subscriber_id + snapshot_month</span>
</div>
<div class="join-row">
<span class="j-idx">6</span>
<span class="j-name">LEFT JOIN t3_cell_monthly_kpi</span>
<span class="j-card">N:1</span>
<span class="j-on">via dominant_serving_cell_id</span>
</div>
</div>
<div>
<span class="col-label">Five guarantees enforced</span>
<ul class="guarantee-list">
<li><span class="g-chip">1:1</span><span>T2 → T1 usage (aggregated per subscriber-month)</span></li>
<li><span class="g-chip">1:1</span><span>T2 → T1 device dominance</span></li>
<li><span class="g-chip">N:1</span><span>T4 coverage broadcast by address</span></li>
<li><span class="g-chip">1:1</span><span>T2 → T5 service consumption</span></li>
<li><span class="g-chip">N:1</span><span>T3 RAN KPIs broadcast via cell</span></li>
</ul>
</div>
</div>

<div class="alt-strip">
<div class="alt-chip">
<span class="alt-name">SQL CTE all-joins</span>
fast but opaque; hard to debug
</div>
<div class="alt-chip">
<span class="alt-name">Row-by-row iteration</span>
O(n×m); memory-inefficient
</div>
<div class="alt-chip chosen">
<span class="alt-name">Pandas step-by-step ✓</span>
per-join assertion + row-count check
</div>
</div>

<p class="validation-footer">Validated at each join: row count preserved (12,412) · no fan-out · zero null introduction · 50 columns · zero duplicates.</p>

</div>
