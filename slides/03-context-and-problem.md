<div class="context-slide">

<h1>Project Context &amp; Engineering Problem</h1>

<span class="subtitle">FWA migration is not a targeting problem — it is a constrained, multi-criteria engineering decision.</span>

<div class="columns">

<div class="col-left">
<p class="col-title">Planning context</p>
<div class="anchor-grid">
<div class="anchor-card"><strong>Snapshot</strong><span>Single-month cross-sectional view — January 2026.</span></div>
<div class="anchor-card"><strong>Coverage grid</strong><span>Static address-level RF table (T4) — RSRP, SINR, fiber, 4G/5G flags.</span></div>
<div class="anchor-card"><strong>Source data</strong><span>Five core tables in the polluted_data PostgreSQL schema.</span></div>
<div class="anchor-card"><strong>Capacity rule</strong><span>Hard operational ceiling: 80% PRB utilisation per serving cell.</span></div>
</div>
</div>

<div class="col-right">
<p class="col-title">Five decision dimensions</p>
<div class="dimension"><span class="idx">1</span><div class="body"><strong>Radio feasibility</strong><span>Can the address sustain an FWA link? (RSRP, SINR, coverage flags)</span></div></div>
<div class="dimension"><span class="idx">2</span><div class="body"><strong>Network capacity</strong><span>Can the serving cell absorb the added PRB load? (80% cap)</span></div></div>
<div class="dimension"><span class="idx">3</span><div class="body"><strong>Commercial value</strong><span>Does ARPU and household profile justify the CPE dispatch?</span></div></div>
<div class="dimension"><span class="idx">4</span><div class="body"><strong>Churn risk</strong><span>Will migration act as retention, or is the subscriber already leaving?</span></div></div>
<div class="dimension"><span class="idx">5</span><div class="body"><strong>Service suitability</strong><span>Does the usage profile support a personalised value-added offer?</span></div></div>
</div>

</div>

<p class="bottom-strip">The solution transforms heterogeneous telecom data into a ranked, capacity-aware campaign action list.</p>

</div>

Note:
Before I present the solution, I want to reframe the problem. FWA migration is often described as a targeting exercise: which subscribers to contact. It is not. It is a constrained multi-criteria engineering decision. Four anchors define the planning context: a single-month cross-sectional snapshot from January 2026; a static address-level coverage grid; five heterogeneous source tables in the operator's data platform; and a hard operational ceiling of 80% PRB utilisation per serving cell. Given this context, five decision dimensions must be resolved for every subscriber. First, radio feasibility: can the address sustain an FWA link at all? Second, network capacity: can the serving cell absorb the added load without breaching the 80% cap? Third, commercial value: does ARPU and household profile justify the CPE dispatch cost? Fourth, churn risk: will migration act as retention, or is the subscriber already leaving? Fifth, service suitability: does the usage profile support a personalised value-added offer — IPTV, gaming, convergent? The solution I will present transforms heterogeneous telecom data into a ranked, capacity-aware campaign action list that resolves all five dimensions simultaneously.
