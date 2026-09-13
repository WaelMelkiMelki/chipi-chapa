<div class="capacity-slide">

<h1>Post-Migration Capacity Simulation</h1>

<span class="subtitle">PRB proxy validation of the 2,629 recommended migrations — under the adopted 80% cap.</span>

<div class="method-strip">
<span class="mp-pill">Monthly GB (per sub)</span>
<span class="mp-arrow">→</span>
<span class="mp-pill">Throughput proxy (uniform 30-day)</span>
<span class="mp-arrow">→</span>
<span class="mp-pill">Offer multiplier (1.0 / 1.25 / 1.5)</span>
<span class="mp-arrow">→</span>
<span class="mp-pill">Cumulative cell PRB</span>
</div>

<div class="gauge-wrap">
<div class="gauge-track">
<div class="gauge-fill"></div>
<div class="gauge-reserved"><span class="zone-label">Reserved headroom</span></div>
</div>
<div class="gauge-cap-line"></div>
<span class="gauge-cap-label">80% hard cap</span>
<div class="gauge-marker is-base"><span class="m-label">Baseline mean · 40.47%</span></div>
<div class="gauge-marker is-post"><span class="m-label">Post-migration mean · 40.54%</span></div>
<div class="gauge-marker is-max"><span class="m-label">Max cell · 68.26%</span></div>
<div class="gauge-buffer"><span class="b-label">11.74 pp buffer</span></div>
<div class="gauge-scale"><span>0%</span><span>50%</span><span>100%</span></div>
</div>

<div class="metrics-row">
<div class="metric-card">
<span class="val">2,629</span>
<span class="lbl">Approved cells/subs</span>
<span class="sub">100% approval rate</span>
</div>
<div class="metric-card danger">
<span class="val">68.26%</span>
<span class="lbl">Max cumulative cell PRB</span>
<span class="sub">CELL_TN_0272, 37 subs</span>
</div>
<div class="metric-card">
<span class="val">11.74 pp</span>
<span class="lbl">Baseline safety buffer</span>
<span class="sub">to the 80% operational cap</span>
</div>
</div>

<div class="sens-strip">
<span class="sens-chip">Baseline → max <strong>68.26%</strong></span>
<span class="sens-chip">Peak ×1.2 → max <strong>68.84%</strong></span>
<span class="sens-chip">Peak ×1.5 → max <strong>69.70%</strong></span>
<span class="sens-trail">All scenarios remain below 80%.</span>
</div>

<div class="insight-band">
<span class="lead">Network safety confirmed:</span>
<span class="main">Under the adopted PRB proxy assumptions, no eligible subscriber is rejected by the capacity gate. Coverage remains the only binding constraint.</span>
</div>

</div>

Note:
Slide 14 established the baseline RAN state: the maximum observed PRB utilisation across 731 cells was 74.68 percent, below the 80 percent operational cap. This slide answers the natural follow-up: what happens after the 2,629 recommended migrations are placed on their serving cells? The simulation uses a PRB proxy model rather than a full MAC-layer scheduler simulation. Each subscriber's monthly data consumption is converted to a continuous throughput requirement, assuming a uniform distribution across thirty days. The throughput is multiplied by an offer-based traffic factor — one point zero for base-only offers, one point two five for single add-ons, and one point five for multi-addon bundles. The result is divided by the cell's average throughput to estimate a fractional PRB uplift per subscriber. A fifteen percent hard cap prevents outliers from breaking the linear proxy. Cumulative PRB per cell is computed as the sum of all subscriber uplifts plus the cell's baseline P95. Three rollout statuses are then assigned: Approved up to 80 percent, Waitlist between 80 and 90, Blocked above 90. The result is unambiguous. The post-migration mean PRB across the subscriber-weighted population moves from 40.47 to 40.54 percent. The maximum cumulative cell PRB on any cell is 68.26 percent — 11.74 percentage points below the 80 percent cap. Zero cells are flagged Waitlist or Blocked. Every one of the 2,629 subscribers receives Approved status. The 15 percent cap was not triggered for any subscriber; the maximum raw uplift was 1.9 percent. Sensitivity analysis with peak-demand factors of 1.2 and 1.5 times average raises the maximum cell load only to 68.84 and 69.70 percent respectively — still below the cap. The engineering conclusion is important: under the adopted proxy assumptions, capacity does not filter the candidate set. Coverage remains the only binding constraint on the FWA campaign.
