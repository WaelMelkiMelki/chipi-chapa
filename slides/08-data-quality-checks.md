<div class="dq-slide">

<h1>Data Quality &amp; Consistency Checks</h1>

<span class="subtitle">Four validation gates — asked as questions, answered with empirical results.</span>

<div class="dq-grid">
<div class="dq-card">
<span class="badge">G1 · Grain Integrity</span>
<p class="question">Is the declared key actually unique?</p>
<p class="method">Row-level duplicate check at each table's expected primary key.</p>
<span class="result">Zero duplicate violations across T1–T5</span>
</div>
<div class="dq-card">
<span class="badge">G2 · Nulls &amp; Schema</span>
<p class="question">Are required fields parseable and populated?</p>
<p class="method">Null rates per column + datetime parsing + Boolean-flag integrity.</p>
<span class="result">Zero invalid dates · Zero invalid Booleans</span>
</div>
<div class="dq-card">
<span class="badge">G3 · Impossible Values</span>
<p class="question">Do measurements respect physical constraints?</p>
<p class="method">Range checks against operational and RF plausibility bounds.</p>
<span class="result">Zero negative traffic · PRB ∈ [0,100] · Zero positive RSRP</span>
</div>
<div class="dq-card">
<span class="badge">G4 · Joinability</span>
<p class="question">Can the tables be reliably linked?</p>
<p class="method">Referential integrity on every declared foreign-key path.</p>
<span class="result">Zero missing links · 100% serving-cell match</span>
</div>
</div>

<p class="result-band">All four gates passed with zero violations — a valid foundation, but not yet a clean one.</p>

</div>

Note:
Before any transformation is applied, the five source tables go through four generic validation gates. First, grain integrity: is the declared key actually unique? Each table is checked against its expected primary key — subscriber-day for T1, subscriber-month for T2 and T5, cell-day for T3, address-level for T4. Zero duplicate violations were found. Second, nulls and schema consistency: are required fields parseable and populated? All datetime fields parse cleanly, and all Boolean flags carry valid representations — zero invalid entries. Third, impossible values: do measurements respect physical constraints? Traffic volumes cannot be negative, PRB utilisation must lie in [0, 100], and realistic RSRP values must be negative. Zero violations detected. Fourth, joinability: can the tables be reliably linked? Every declared foreign-key path — subscriber_id, address_id, cell_id — returned zero missing links, and the serving-cell consistency check matched at one hundred percent. All four gates passed. That is a valid foundation — but as the next slide will show, it is not yet a clean one. Telecom-specific anomalies can survive every generic check.
