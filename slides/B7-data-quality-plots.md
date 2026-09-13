<div class="backup-slide b7">

<span class="backup-badge">Backup slide · B7</span>

<h1>Data Quality Plot Reference — P1 to P5</h1>

<span class="subtitle">Detection logic, expected plot shape, and pre/post validation outcomes for the five pollution signatures.</span>

<table class="ref-table">
<thead>
<tr><th>Signature</th><th>Detection rule</th><th>Plot shape (pre)</th><th>Post-cleaning observation</th></tr>
</thead>
<tbody>
<tr><td class="sig">P1 — Stuck RAN counters</td><td class="rule">PRB ≥ 99.9% AND users = 0</td><td>Scatter: red dots clustered at far-right x-axis; normal traffic at x &lt; 80%</td><td class="post">Zero anomalies in the [0, 75%] band · 0.00% residual</td></tr>
<tr><td class="sig">P2 — Abnormal VoIP telemetry</td><td class="rule">VoIP &gt; 5,000 min AND social_media_vol = 0 GB</td><td>Scatter: red column at y &gt; 5,000 along the y-axis; normal traffic below</td><td class="post">All VoIP minutes below 5,000 min after correction · 0.00% residual</td></tr>
<tr><td class="sig">P3 — PIM interference</td><td class="rule">RSRP = −80 dBm AND SINR = 0 dB (repeating)</td><td>Scatter: single dense red square at (x = −80, y = 0); other addresses on a diagonal band</td><td class="post">No addresses at the (−80, 0) coordinate · 0.00% residual</td></tr>
<tr><td class="sig">P4 — MSISDN oscillation</td><td class="rule">&gt; 1 MSISDN per subscriber within month</td><td>Pie chart: 99.5% clean subscribers, 0.5% (58) multi-MSISDN slice</td><td class="post">100% single-MSISDN after mode-based alignment · 0.00% residual</td></tr>
<tr><td class="sig">P5 — Orphaned KPI records</td><td class="rule">NULL kpi_date (missing temporal key)</td><td>Bar chart: 464-row tall red bar against a baseline of daily counts</td><td class="post">Zero NULL kpi_date records · 464 rows structurally deleted</td></tr>
</tbody>
</table>

<p class="footer-note">All five signature classes resolved to 0.00% residual after targeted cleaning — full pre/post plots available in the report appendix (Section 2.1.6).</p>

</div>
