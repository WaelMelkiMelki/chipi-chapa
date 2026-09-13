<div class="service-slide">

<h1>Service Consumption GMM</h1>

<span class="subtitle">Three parallel GMM intersections — from continuous usage to binary offer-trigger flags.</span>

<div class="method-strip">
<span class="strip-label">Same method · applied 3× in parallel</span>
<span class="strip-content">T5 → reshape → 1D GMM (K=2) → quadratic intersection → 5% floor → binary flag</span>
</div>

<div class="cards-row">
<div class="result-card">
<p class="card-title">Streaming (GB / month)</p>
<span class="big-threshold">95.73 GB</span>
<span class="vs-midpoint">vs. K-means midpoint 90.37 GB</span>
<span class="variance-note">σ²<sub>heavy</sub> / σ²<sub>light</sub> = 4.67×</span>
<span class="flag-chip">Heavy: 2,633 subs · 21.21%</span>
<span class="offer-map">→ 5G FWA + IPTV Bundle (if IPTV inactive)</span>
</div>
<div class="result-card">
<p class="card-title">Gaming (GB / month)</p>
<span class="big-threshold">1.17 GB</span>
<span class="vs-midpoint">vs. K-means midpoint 2.35 GB</span>
<span class="variance-note">σ²<sub>heavy</sub> / σ²<sub>light</sub> = 195.19×</span>
<span class="flag-chip">Heavy: 4,170 subs · 33.59%</span>
<span class="offer-map">→ Low-Latency Gaming Add-On (if 5G coverage)</span>
</div>
<div class="result-card">
<p class="card-title">VoIP (minutes / month)</p>
<span class="big-threshold">361.86 min</span>
<span class="vs-midpoint">vs. K-means midpoint 374.78 min</span>
<span class="variance-note">σ²<sub>heavy</sub> / σ²<sub>light</sub> = 2.30×</span>
<span class="flag-chip">Heavy: 4,029 subs · 32.46%</span>
<span class="offer-map">→ Convergent Fixed-Mobile Add-On (if multi-line)</span>
</div>
</div>

<p class="bottom-line">These three binary flags are the direct inputs to the recommendation engine — streaming triggers IPTV, gaming triggers the low-latency add-on, VoIP triggers the convergent bundle.</p>

</div>

Note:
The last feature family in Chapter 2 concerns service consumption. T5 records three monthly metrics per subscriber: streaming volume, gaming volume, and VoIP minutes. Each of them is a decision variable — they trigger specific value-added offers in the recommendation engine. The same GMM intersection method I described earlier is applied three times in parallel. The result is three thresholds that a fixed business rule would almost certainly have missed. Streaming splits at 95.73 gigabytes per month; the high-variance cluster is nearly five times as dispersed as the low one, so the threshold sits above the naive K-means midpoint. 2,633 subscribers — about 21 percent — qualify as heavy streamers, and they are the primary candidates for the IPTV bundle. Gaming splits much lower than the midpoint — 1.17 gigabytes, not 2.35. The variance ratio is 195 to one: the light cluster is very tight, and the heavy tail is very diffuse. A K-means midpoint would have under-identified moderate gamers; the GMM boundary sits correctly in the sparse gap between the two latent populations. 4,170 subscribers — 33.6 percent — qualify as heavy gamers, which validates the commercial case for the low-latency gaming add-on: a third of the base has gaming traffic that justifies dedicated QoS. VoIP splits at 361.86 minutes; 4,029 subscribers — 32.5 percent — exceed it. Combined with multi-line households, this segment justifies the convergent fixed-mobile offer: bundling FWA with VoLTE and mobile lines increases switching costs and protects ARPU. These three binary flags are the direct inputs to the recommendation engine on a later slide. With them, the feature engineering stage of the pipeline is complete.
