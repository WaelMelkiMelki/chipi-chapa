<div class="usage-slide">

<h1>Usage Aggregation &amp; Device Dominance</h1>

<span class="subtitle">From daily subscriber records to monthly usage features and device readiness.</span>

<div class="mini-flow">
<span class="pill">Filter roaming</span>
<span class="mini-arrow">→</span>
<span class="pill">Aggregate to month</span>
<span class="mini-arrow">→</span>
<span class="pill">Mode-based dominance</span>
<span class="mini-arrow">→</span>
<span class="pill">Derive 5G-ready flag</span>
</div>

<div class="stats-grid">
<div class="stat-card">
<span class="stat-num">972</span>
<span class="stat-label">5G-Ready</span>
<span class="stat-sub">7.8% of subscribers</span>
</div>
<div class="stat-card">
<span class="stat-num">8,386</span>
<span class="stat-label">4G-Dominant</span>
<span class="stat-sub">67.6% of subscribers</span>
</div>
<div class="stat-card accent-red">
<span class="stat-num">3,054</span>
<span class="stat-label">Other Generation</span>
<span class="stat-sub">24.6% of subscribers</span>
</div>
</div>

<div class="feature-grid">
<div class="feature-card">
<h3>Zero-volume imputation</h3>
<span class="rule">dl_volume_mb = 0 AND peak_hour_dl_mb &gt; 0</span>
<span class="expl">Logically inconsistent — replaced by the subscriber's own monthly median.</span>
</div>
<div class="feature-card">
<h3>Peak-hour traffic ratio</h3>
<span class="rule">Σ peak_hour_dl / Σ imputed_dl</span>
<span class="expl">Retained as continuous — captures congestion risk, not just a threshold.</span>
</div>
</div>

<p class="result-band">731 unique dominant serving cells · 92.2% of subscribers need a 5G CPE dispatch for full FWA capability.</p>

</div>

Note:
With temporal alignment in place, T1's daily subscriber records become monthly usage features. Three processing decisions matter here. First, roaming records were excluded before aggregation — roaming traffic does not traverse the local serving cell and would overestimate its capacity load by 100 rows of noise. Second, the monthly totals were computed per subscriber, then the dominant device generation and dominant serving cell were derived by mode: the assumption is that FWA suitability depends on consistent daily presence at a fixed location, so the modal value is the right aggregation. Third, the 5G-ready flag was derived as whether the dominant device generation equals 5G. This gives us the key commercial constraint of the entire campaign: only 7.8% of subscribers — 972 people — are 5G-ready. Over 92% would require a 5G CPE dispatch to achieve full FWA capability. Two engineered features also emerge from T1. Zero-volume imputation: when daily downlink is reported as zero while peak-hour downlink is positive, the record is logically inconsistent, and the subscriber's own monthly median is substituted. And the peak-hour traffic ratio: the ratio of peak-hour to total monthly downlink. I retained it as a continuous variable rather than a binary flag because a threshold split showed no discriminative value — every subscriber was above it — whereas the continuous ratio captures actual congestion risk for the capacity simulation.
