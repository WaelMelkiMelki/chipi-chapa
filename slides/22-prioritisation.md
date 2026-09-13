<div class="prioritisation-slide">

<h1>Migration Prioritisation via MCDA</h1>

<span class="subtitle">Four weighted dimensions, one 0–100 priority score — deterministic, auditable, no labels required.</span>

<div class="dim-row">
<div class="dim-tile">
<span class="weight">0.40</span>
<span class="dname">Technical Suitability</span>
<span class="ddesc">Min-max normalised FWA_suitability_score (embeds coverage, device, ARPU, usage penalties).</span>
</div>
<div class="dim-tile">
<span class="weight">0.30</span>
<span class="dname">Commercial Value</span>
<span class="ddesc">Min-max normalised arpu_monthly_tnd — proxies CPE payback economics.</span>
</div>
<div class="dim-tile">
<span class="weight">0.20</span>
<span class="dname">Strategic Persona</span>
<span class="ddesc">Per-cluster weight from K-Prototypes (encodes non-linear strategic value).</span>
</div>
<div class="dim-tile">
<span class="weight">0.10</span>
<span class="dname">Loyalty &amp; Tenure</span>
<span class="ddesc">Min-max normalised tenure_months — proxies switching inertia.</span>
</div>
</div>

<div class="formula-band">
<span class="lead">Composite priority score (scaled to 0–100):</span>
<span class="formula">P = (0.40 · S<sub>tech</sub> + 0.30 · S<sub>comm</sub> + 0.20 · S<sub>strat</sub> + 0.10 · S<sub>loyal</sub>) × 100</span>
</div>

<div class="columns">
<div>
<span class="col-label">Strategic persona weights (S_strat)</span>
<div class="w-bar-row c2">
<span class="w-label">Cluster 2 — Ultra-Heavy Postpaid</span>
<div class="bar-track"><div class="bar-fill"></div></div>
<span class="w-val">1.0</span>
</div>
<div class="w-bar-row c0">
<span class="w-label">Cluster 0 — High-Value Prepaid</span>
<div class="bar-track"><div class="bar-fill"></div></div>
<span class="w-val">0.8</span>
</div>
<div class="w-bar-row c3">
<span class="w-label">Cluster 3 — Mid-Tier Prepaid</span>
<div class="bar-track"><div class="bar-fill"></div></div>
<span class="w-val">0.6</span>
</div>
<div class="w-bar-row c1">
<span class="w-label">Cluster 1 — Mass-Market Prepaid</span>
<div class="bar-track"><div class="bar-fill"></div></div>
<span class="w-val">0.4</span>
</div>
</div>
<div>
<span class="col-label">Top-decile composition (Rank 1–262)</span>
<div class="top-row">
<div class="top-chip c0">
<span class="lbl">Cluster 0</span>
<span class="val">203 subs · 77.5%</span>
</div>
<div class="top-chip c2">
<span class="lbl">Cluster 2</span>
<span class="val">57 subs · 21.8%</span>
</div>
<div class="top-chip c3">
<span class="lbl">Cluster 3</span>
<span class="val">2 subs · 0.8%</span>
</div>
</div>
<div class="absence-callout">
<strong>Cluster 1: 0 subscribers in top decile</strong>
The MCDA successfully filters out low-ARPU mass-market users from the initial CPE dispatch wave.
</div>
</div>
</div>

<div class="sens-band">
<span class="lead">Robustness check:</span>
<span class="main">±10% weight perturbation → 94.2% top-decile membership overlap. The ranking is stable across a reasonable range of business preferences.</span>
</div>

</div>

Note:
With the eligible population scored and segmented, the next question is sequencing: in which order should the operator approach the 2,629 candidates? The answer is a multi-criteria decision analysis framework with four orthogonal dimensions. Technical Suitability carries the largest weight, 0.40, because radio coverage and device readiness fundamentally constrain what can be served. Commercial Value carries 0.30 and reflects CPE payback economics: a subscriber at 35 dinars ARPU recovers the CPE cost in three to four months; a subscriber at 18 dinars needs seven to eight. Strategic Persona carries 0.20, encoding the cluster-level value that ARPU alone does not express — a postpaid power user generating 1,364 gigabytes per month has strategic value beyond their 31-dinar ARPU because their migration also offloads traffic from the RAN and protects a retention-sensitive contract. And Loyalty carries 0.10, a tie-breaking dimension proxied by tenure months. The strategic persona weights are differentiated: Cluster 2 at the maximum 1.0, Cluster 0 at 0.8, Cluster 3 at 0.6, and Cluster 1 at 0.4. The composite score is scaled to 0 to 100. Two validation results are worth highlighting. First, the top decile — the 262 highest-priority subscribers — contains 77.5 percent Cluster 0 and 21.8 percent Cluster 2, and zero subscribers from Cluster 1. This is exactly the intended outcome: the MCDA filters out low-ARPU mass-market users from the initial CPE dispatch wave. Second, the ranking is stable: a sensitivity analysis varying each dimension weight by plus or minus ten percent produces a 94.2 percent overlap in the top-decile membership. The ranking is robust to a reasonable range of business preferences. A deliberate design note: ARPU appears twice — once as a suitability penalty, once as the commercial value dimension — and this double counting is intentional, reflecting the operator's explicit priority on CPE payback within the target horizon.
