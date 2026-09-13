<div class="scope-slide">

<h1>Scope, Assumptions &amp; Framing</h1>

<span class="subtitle">What this project delivers — and what it deliberately does not claim.</span>

<div class="columns">

<div class="col-left">
<p class="col-title">In scope</p>
<div class="scope-item in">Data quality, cleaning, and temporal standardisation across five heterogeneous telecom sources.</div>
<div class="scope-item in">Subscriber-month Analytical Base Table (ABT) — the unified decision layer.</div>
<div class="scope-item in">Rule-based FWA eligibility and suitability scoring (RF, fibre, capacity, ARPU).</div>
<div class="scope-item in">Behavioural segmentation, migration prioritisation, and churn-risk estimation.</div>
<div class="scope-item in">Two-tier offer recommendation, PRB capacity proxy simulation, and campaign action list.</div>
</div>

<div class="col-right">
<p class="col-title">Out of scope</p>
<div class="scope-item out">No modification of the production network or deployment of live FWA offers.</div>
<div class="scope-item out">No claim of measured campaign conversion or commercial outcomes.</div>
<div class="scope-item out">Capacity validation via PRB proxy — not a full MAC-layer scheduler simulation.</div>
<div class="scope-item out">No historical FWA campaign-response labels available for supervised propensity.</div>
</div>

</div>

<div class="assumption-band">
<p class="col-title">Three framing assumptions</p>
<div class="assumption-row">
<div class="assumption"><strong>Snapshot</strong>Single-month cross-section, January 2026.</div>
<div class="assumption"><strong>Decision-support artifacts</strong>Outputs are for business review and pilot preparation.</div>
<div class="assumption"><strong>Proxy-based capacity</strong>Results valid under adopted PRB uplift assumptions.</div>
</div>
</div>

</div>

Note:
Before we look at the architecture, I want to be explicit about scope. What this project delivers is on the left: a data quality and feature engineering layer across five heterogeneous telecom sources, a subscriber-month Analytical Base Table, a rule-based FWA suitability engine, behavioural segmentation, prioritisation, churn-risk estimation, a two-tier recommendation engine, a PRB capacity proxy simulation, and a final campaign action list. What it does not claim is on the right. We did not modify the production network, did not deploy live FWA offers, and do not claim measured campaign conversion — because no historical FWA campaign has ever been run, there are no response labels for supervised propensity modelling. Capacity validation is a PRB proxy derived from observable RAN indicators — not a full MAC-layer scheduler simulation. Three framing assumptions underpin everything that follows: a single-month cross-section from January 2026, decision-support outputs for pilot preparation, and capacity results valid under the adopted PRB uplift assumptions. Keeping these boundaries explicit protects both the analytics and the business decision. Now let me show you the architecture that operationalises this scope.
