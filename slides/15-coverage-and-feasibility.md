<div class="coverage-slide">

<h1>Address Coverage &amp; Radio Feasibility</h1>

<span class="subtitle">Worst-case RF classification across 12,412 addresses — the binding constraint on the FWA campaign.</span>

<div class="bar-block">
<span class="bar-label">Signal quality classification · 12,412 addresses</span>
<div class="stacked-bar">
<span class="seg poor">76.1%</span>
<span class="seg acceptable">17.6%</span>
<span class="seg excellent">6.3%</span>
</div>
<div class="legend">
<span class="leg-item"><span class="dot excellent"></span>Excellent — <span class="count">782</span> — 6.3%</span>
<span class="leg-item"><span class="dot acceptable"></span>Acceptable — <span class="count">2,181</span> — 17.6%</span>
<span class="leg-item"><span class="dot poor"></span>Poor — <span class="count">9,449</span> — 76.1%</span>
</div>
<span class="bar-caption">Worst-case rule: RSRP &lt; −95 dBm OR SINR &lt; 3 dB → Poor.</span>
</div>

<div class="bar-block">
<span class="bar-label">Radio feasibility classification · 12,412 addresses</span>
<div class="stacked-bar">
<span class="seg infeasible">77.9%</span>
<span class="seg fallback">18.8%</span>
<span class="seg feasible small">2.3%</span>
<span class="seg fiber"></span>
</div>
<div class="legend">
<span class="leg-item"><span class="dot feasible"></span>5G_Feasible — <span class="count">291</span> — 2.3% (premium FWA candidate)</span>
<span class="leg-item"><span class="dot fallback"></span>4G_Fallback — <span class="count">2,338</span> — 18.8% (standard FWA tier)</span>
<span class="leg-item"><span class="dot fiber"></span>Fiber_Competitor — <span class="count">109</span> — 0.9% (blocked to prevent cannibalisation)</span>
<span class="leg-item"><span class="dot infeasible"></span>Infeasible — <span class="count">9,674</span> — 77.9% (no viable service)</span>
</div>
</div>

<div class="insights-row">
<div class="insight-card">
<span class="headline">RSRP, not interference</span>
<span class="body">Poor-tier addresses average −112.06 dBm (17 dB below threshold) while their SINR averages 14.21 dB — well above the 3 dB floor. Signal strength, not interference, drives the exclusion.</span>
</div>
<div class="insight-card green">
<span class="headline">2,629 subscribers</span>
<span class="body">The addressable market is 21.2% of the base. Only 2.3% are 5G-feasible (premium tier). 18.8% are 4G-fallback (standard tier).</span>
</div>
<div class="insight-card red">
<span class="headline">Coverage investment opportunity</span>
<span class="body">The dominance of RSRP-driven exclusions signals that additional sites or small cells would unlock a larger FWA-eligible population — a directional input for future network planning.</span>
</div>
</div>

</div>

Note:
The address-level coverage grid is the single most consequential input to the entire pipeline. Two classifications are applied, both at the address level. First, signal quality: a worst-case rule on RSRP and SINR produces three tiers. Excellent — 6.3% of addresses, with RSRP above -85 dBm and SINR above 10 dB. Acceptable — 17.6%. And Poor — 76.1% of the base, or 9,449 addresses. The poor tier is dominated by weak signal strength: their average RSRP is -112 dBm, about seventeen dB below the threshold needed for a CPE to decode the control channel. Critically, their average SINR is 14.2 dB — well above the 3 dB interference floor. This is important: signal strength, not interference, is the binding constraint. Second, radio feasibility: the signal quality is combined with 4G and 5G coverage flags and with fibre availability into four categories. Infeasible — 77.9%. 4G-fallback — 18.8%. 5G-feasible — 2.3%. And fibre-competitor — 0.9%, blocked to prevent cannibalisation of existing fibre. The addressable FWA market is therefore 2,629 subscribers, 21.2% of the base. The dominant driver of the remaining 77.9 percent exclusion is the physical radio environment. This is the single most important finding of this project: the FWA opportunity is coverage-constrained, not capacity-constrained. As a corollary, the exclusion pattern is also a directional input for future network planning — additional sites or small cells in the RSRP-limited areas would unlock a larger FWA-eligible population.
