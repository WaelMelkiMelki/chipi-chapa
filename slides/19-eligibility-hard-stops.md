<div class="eligibility-slide">

<h1>FWA Eligibility &amp; Hard Stops</h1>

<span class="subtitle">Rule-based scoring: Base 100, three non-negotiable exclusions, two additive penalties.</span>

<div class="arch-strip">
<span class="arch-pill">Base 100</span>
<span class="arch-arrow">→</span>
<span class="arch-pill">3 Hard Stops</span>
<span class="arch-arrow">→</span>
<span class="arch-pill step-penalty">Additive Penalties (−20 / −15)</span>
<span class="arch-arrow">→</span>
<span class="arch-pill">Band Mapping (Premium / Standard / Marginal / Excluded)</span>
</div>

<div class="hs-row">
<div class="hs-card p1">
<span class="priority-badge">Priority 1</span>
<span class="headline">Fibre cannibalisation</span>
<span class="condition">radio_feasibility_class == 'Fiber_Competitor'</span>
<span class="reason-code">Fiber_Cannibalization</span>
<span class="count">109 subscribers</span>
<span class="rationale">Address already served by FTTH — migrating would cannibalise higher-margin fibre revenue.</span>
</div>
<div class="hs-card p2">
<span class="priority-badge">Priority 2</span>
<span class="headline">RF infeasibility</span>
<span class="condition">radio_feasibility_class == 'Infeasible'</span>
<span class="reason-code">RF_Failure</span>
<span class="count">9,674 subscribers</span>
<span class="rationale">No viable 4G or 5G coverage at the address — physically impossible regardless of commercial factors.</span>
</div>
<div class="hs-card p3">
<span class="priority-badge">Priority 3</span>
<span class="headline">Cell overload</span>
<span class="condition">current_capacity_proxy_status == 'CONSTRAINED'</span>
<span class="reason-code">Cell_Overload</span>
<span class="count">0 subscribers</span>
<span class="rationale">PRB utilisation at or above 80%. Not triggered — baseline RAN has headroom.</span>
</div>
</div>

<div class="funnel-bar">
<span class="seg excluded">Excluded — 78.8%</span>
<span class="seg eligible">Eligible — 21.2%</span>
</div>
<div class="funnel-legend">
<span class="leg-item"><span class="dot excluded"></span>Excluded <span class="count">9,783</span> (78.8%)</span>
<span class="leg-item"><span class="dot eligible"></span>Eligible <span class="count">2,629</span> (21.2%)</span>
</div>
<span class="funnel-caption">Priorities evaluated in order — first trigger determines the reason code.</span>

<span class="key-insight">98.9% of exclusions are RF-driven. Zero subscribers are excluded by the capacity gate — coverage is the binding constraint.</span>

</div>

Note:
Chapter 4 opens with the first decision layer applied to the Analytical Base Table: the FWA eligibility and suitability scoring engine. The engine is deliberately rule-based, not learned, because the key decision factors — RF thresholds, fibre status, network capacity, ARPU bands — are explicit operational constraints, not patterns to be discovered. The engine starts every subscriber at a base score of one hundred. Three hard stops can immediately set that score to zero, each with a recorded reason code. Hard stops are evaluated in strict priority order — priority one is fibre cannibalisation: an address already served by fibre-to-the-home is blocked, because migrating it to FWA would replace a higher-margin fixed connection with a lower-margin wireless one. One hundred and nine subscribers are excluded this way. Priority two is RF infeasibility: no 4G or 5G coverage at the address. This is the dominant exclusion — 9,674 subscribers, or 77.9 percent of the base. Priority three is cell overload: the serving cell is at or above the eighty percent PRB cap. Zero subscribers trigger this — the baseline network has capacity headroom. Subscribers who pass all three hard stops then receive up to two additive penalties, minus twenty points for no 5G coverage and minus fifteen for the low-ARPU band. The full distribution produces four bands — Premium, Standard, Marginal, and Excluded. The single most important finding on this slide: ninety-eight point nine percent of exclusions are RF-driven; zero are capacity-driven. Coverage is the binding constraint on the FWA campaign, and every downstream decision inherits that fact.
