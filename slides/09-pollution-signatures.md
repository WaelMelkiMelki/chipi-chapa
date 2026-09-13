<div class="pollution-slide">

<h1>Five Pollution Signatures</h1>

<span class="subtitle">Telecom-specific anomalies that survived every generic check — found forensically, resolved surgically.</span>

<div class="p-list">
<div class="p-row"><span class="p-badge">P1</span><span class="p-name">Stuck RAN counters</span><span class="p-rule">PRB ≥ 99.9% AND connected users = 0</span><span class="p-count">581</span><span class="p-action">Cell-level median imputation</span></div>
<div class="p-row"><span class="p-badge">P2</span><span class="p-name">Abnormal VoIP telemetry</span><span class="p-rule">VoIP &gt; 5,000 min AND social media = 0 GB</span><span class="p-count">1,221</span><span class="p-action">Global median imputation</span></div>
<div class="p-row"><span class="p-badge">P3</span><span class="p-name">PIM interference signature</span><span class="p-rule">RSRP = −80 dBm AND SINR = 0 dB (repeating)</span><span class="p-count">3,027</span><span class="p-action">Empirical cell-level RAN medians</span></div>
<div class="p-row"><span class="p-badge">P4</span><span class="p-name">MSISDN identity oscillation</span><span class="p-rule">&gt; 1 MSISDN per subscriber within a month</span><span class="p-count">58</span><span class="p-action">Mode-based identity alignment</span></div>
<div class="p-row"><span class="p-badge">P5</span><span class="p-name">Orphaned RAN KPI records</span><span class="p-rule">NULL kpi_date (missing temporal key)</span><span class="p-count">464</span><span class="p-action">Structural deletion — temporal key not imputable</span></div>
</div>

<p class="result-band">Post-cleaning validation: 0.00% residual rate for every signature class.</p>

</div>

Note:
Generic validation was necessary but not sufficient. Five telecom-specific pollution signatures survived every standard check. P1, stuck RAN counters: PRB utilisation reported at or above 99.9 percent while the number of connected users is zero — a physically impossible measurement affecting 581 rows. P2, abnormal VoIP telemetry: over 5,000 minutes of voice usage combined with zero social media volume — an inconsistent consumption profile affecting 1,221 rows. P3, PIM interference signatures: the passive intermodulation fallback pattern of RSRP equal to -80 dBm and SINR equal to 0 dB, repeating systematically across 3,027 rows. P4, MSISDN identity oscillation: subscribers associated with more than one MSISDN within the same month, affecting 58 subscribers. P5, orphaned RAN KPI records: 464 rows with a null kpi_date, meaning the temporal key could not be imputed without inventing information. Each signature required a targeted resolution: nullification followed by cell-level or global median imputation for P1, P2, and P3; mode-based identity alignment for P4; and structural deletion for P5. Post-cleaning validation confirmed a zero percent residual rate for every class. This is what turned the data from merely valid into actually reliable.
