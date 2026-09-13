<div class="cleaning-slide">

<h1>Cleaning Pipeline</h1>

<span class="subtitle">From polluted source schema to a trusted cleaned_data foundation.</span>

<div class="band band-in">
<span class="schema-label">polluted_data</span>
<div class="chip-row">
<span class="chip">T1 · Daily</span>
<span class="chip">T2 · CRM</span>
<span class="chip">T3 · RAN KPI</span>
<span class="chip">T4 · Address</span>
<span class="chip">T5 · Service</span>
</div>
</div>

<div class="v-arrow">↓</div>

<div class="rules-list">
<div class="rule-row"><span class="p-badge">P1</span><span class="action">→ <strong>Cell-level median imputation</strong> (581 rows)</span></div>
<div class="rule-row"><span class="p-badge">P2</span><span class="action">→ <strong>Global median imputation</strong> (1,221 rows)</span></div>
<div class="rule-row"><span class="p-badge">P3</span><span class="action">→ <strong>Empirical cell-level RAN medians</strong> (3,027 rows)</span></div>
<div class="rule-row"><span class="p-badge">P4</span><span class="action">→ <strong>Mode-based identity alignment</strong> (58 subscribers)</span></div>
<div class="rule-row"><span class="p-badge">P5</span><span class="action">→ <strong>Structural deletion</strong> (464 rows)</span></div>
</div>

<div class="v-arrow">↓</div>

<div class="band band-out">
<span class="schema-label">cleaned_data</span>
<div class="chip-row">
<span class="chip">T1 · Daily</span>
<span class="chip">T2 · CRM</span>
<span class="chip">T3 · RAN KPI</span>
<span class="chip">T4 · Address</span>
<span class="chip">T5 · Service</span>
</div>
</div>

<p class="result-band">Post-resolution residual rate: 0.00% — trusted foundation for ABT construction.</p>

</div>

Note:
Once the pollution signatures were identified, the cleaning pipeline was executed end-to-end. The input schema is polluted_data — the five operational tables as they exist in the operator's platform. The five detection-and-resolution rules from the previous slide were applied in a defined order: cell-level median imputation for the stuck RAN counters, global median imputation for the abnormal VoIP telemetry, empirical cell-level RAN medians for the PIM interference signatures, mode-based identity alignment for the MSISDN oscillation, and structural deletion for the orphaned RAN KPI records with missing temporal keys. The output schema is cleaned_data — the same five tables, but with a validated, temporally standardised, and anomaly-free foundation. Post-resolution validation confirmed a zero percent residual rate for every signature class. This cleaned_data schema is the foundation on which every feature, every subscriber-month record, and every downstream decision will be built. In short: this is where the project stops asking whether the data can be trusted, and starts building on it.
