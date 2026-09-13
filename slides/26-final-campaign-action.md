<div class="campaign-slide">

<h1>Final Campaign Action List</h1>

<span class="subtitle">From analytical outputs to a CRM-ready campaign — 5 operational categories, one decision cascade.</span>

<div class="cat-row">
<div class="cat-chip exclude">
<span class="c-name">Exclude</span>
<span class="c-count">9,783</span>
<span class="c-pct">78.8%</span>
</div>
<div class="cat-chip empty">
<span class="c-name">Waitlist</span>
<span class="c-count">0</span>
<span class="c-pct">0.0%</span>
</div>
<div class="cat-chip empty">
<span class="c-name">Manual Review</span>
<span class="c-count">0</span>
<span class="c-pct">0.0%</span>
</div>
<div class="cat-chip later">
<span class="c-name">Contact Later</span>
<span class="c-count">1,971</span>
<span class="c-pct">15.9%</span>
</div>
<div class="cat-chip now">
<span class="c-name">Contact Now</span>
<span class="c-count">658</span>
<span class="c-pct">5.3%</span>
</div>
</div>

<div class="cascade-block">
<span class="cascade-label">Decision cascade — evaluated in order</span>
<div class="cascade-row r-exclude">
<span class="idx">1</span>
<span class="cat-name">Exclude</span>
<span class="rule">FWA_suitability_score = 0 OR rollout_status = Blocked</span>
<span class="cnt">9,783</span>
</div>
<div class="cascade-row">
<span class="idx">2</span>
<span class="cat-name">Waitlist</span>
<span class="rule">rollout_status = Waitlist</span>
<span class="cnt">0</span>
</div>
<div class="cascade-row">
<span class="idx">3</span>
<span class="cat-name">Manual Review</span>
<span class="rule">churn_risk_band ∈ {High, Critical} AND FWA_suitability_band = Marginal</span>
<span class="cnt">0</span>
</div>
<div class="cascade-row r-now">
<span class="idx">4</span>
<span class="cat-name">Contact Now</span>
<span class="rule">final_priority_score ≥ Q3 AND rollout_status = Approved</span>
<span class="cnt">658</span>
</div>
<div class="cascade-row r-later">
<span class="idx">5</span>
<span class="cat-name">Contact Later</span>
<span class="rule">final_priority_score &lt; Q3 AND rollout_status = Approved</span>
<span class="cnt">1,971</span>
</div>
</div>

<div class="routing-block">
<div class="route-card b2b">
<span class="rc-name">B2B / SME channel</span>
Multi-line accounts (num_active_lines &gt; 2) route to Key Account Managers for dedicated B2B sales cycles, custom SLAs, and enterprise onboarding.
</div>
<div class="route-card b2c">
<span class="rc-name">B2C channel</span>
Single-line and standard household accounts route to the mass-market outbound telemarketing center for standard Wave 1 execution.
</div>
</div>
<span class="routing-caption">The score itself is not used as a direct dialling order across these two channels.</span>

<div class="insight-band">
<span class="lead">Operational readiness:</span>
<span class="main">658 Contact Now subscribers form the Wave 1 pilot list. 98.9% of exclusions are RF-driven — the campaign's binding constraint is physical, not commercial.</span>
</div>

</div>

Note:
This is the operational payoff of the entire pipeline: the final campaign action list. Five operational categories are produced, each assigned by a strict decision cascade evaluated in order. Rule one excludes subscribers who failed a suitability hard stop or whose serving cell is blocked by capacity. Nine thousand seven hundred and eighty-three subscribers — 78.8 percent of the base — fall here. Ninety-eight point nine percent of these exclusions are RF-driven; the remainder are fibre cannibalisation. Rule two, Waitlist, is empty in this snapshot because no cell is currently constrained. Rule three, Manual Review, is empty because no eligible subscriber falls in the Marginal suitability band. Rule four assigns Contact Now to subscribers in the top quartile of final priority score whose rollout status is Approved — 658 subscribers, 5.3 percent. Rule five assigns Contact Later to the remaining eligible population, 1,971 subscribers. One operational nuance matters for real deployment: the prioritisation score is not used as a direct dialling order across B2B and B2C. Multi-line accounts with more than two active lines are routed to Key Account Managers for dedicated B2B sales cycles with custom SLAs; single-line and standard household accounts are routed to the mass-market outbound telemarketing center for standard Wave 1 execution. This bifurcation ensures that the mathematical prioritisation aligns with real telecom sales operations. The campaign list is persisted as a structured output, ready for CRM integration and pilot preparation. The single sentence that summarises this slide: six hundred and fifty-eight subscribers form the Wave 1 pilot list, and the campaign's binding constraint is physical — not commercial.
