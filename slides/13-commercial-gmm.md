<div class="gmm-slide">

<h1>Commercial Binning via GMM Intersection</h1>

<span class="subtitle">ARPU and tenure thresholds derived from the data's own distribution — not from fixed business rules.</span>

<div class="rejection-row">
<div class="reject-card">
<span class="badge">✗ Rejected</span>
<p class="text"><strong>Fixed business rules.</strong> Arbitrary round numbers (e.g. ARPU &gt; 20 TND) rarely match the true revenue concentration boundary.</p>
</div>
<div class="reject-card">
<span class="badge">✗ Rejected</span>
<p class="text"><strong>Quantile splits.</strong> Balanced group sizes are not the objective — we want natural separation between low and high populations.</p>
</div>
<div class="reject-card">
<span class="badge">✗ Rejected</span>
<p class="text"><strong>K-Means midpoint.</strong> Assumes equal cluster variance; overestimates the low-group boundary on right-skewed telecom data.</p>
</div>
</div>

<div class="selected-banner">
<span class="badge">✓ Selected</span>
<span class="text"><strong>1D GMM intersection.</strong> Models the distribution as two latent Gaussians; places the threshold at the weighted density intersection — data-driven, variance-aware, right-skew robust.</span>
</div>

<div class="results-grid">
<div class="result-card">
<span class="card-title">ARPU (TND/month) · 12,412 subscribers</span>
<div class="mini-table">
<span class="k">GMM threshold</span><span class="v">23.33 TND</span>
<span class="k">K-Means midpoint</span><span class="v">20.95 TND</span>
<span class="k">Variance ratio σ²<sub>high</sub> / σ²<sub>low</sub></span><span class="v">3.46×</span>
</div>
<div class="band-chip low"><span class="lbl">Low ARPU &lt; 23.33</span><span class="val">8,381 subs · 67.5% · mean 14.53 TND</span></div>
<div class="band-chip high"><span class="lbl">High ARPU &gt; 23.33</span><span class="val">4,031 subs · 32.5% · mean 27.37 TND</span></div>
</div>
<div class="result-card">
<span class="card-title">Tenure (months)</span>
<div class="mini-table">
<span class="k">GMM threshold</span><span class="v">90.59 mo</span>
<span class="k">K-Means midpoint</span><span class="v">≈ equivalent</span>
<span class="k">Variance ratio σ²<sub>high</sub> / σ²<sub>low</sub></span><span class="v">≈ 1×</span>
</div>
<div class="band-chip low"><span class="lbl">Short Tenure &lt; 90.59</span><span class="val">6,372 subs · 51.3% · mean 47.01 mo</span></div>
<div class="band-chip high"><span class="lbl">Long Tenure &gt; 90.59</span><span class="val">6,040 subs · 48.7% · mean 133.22 mo</span></div>
</div>
</div>

<div class="formula-band">
<span class="lead">Threshold x* where the two weighted densities meet:</span>
<span class="formula">π₁ · 𝒩(x* | μ₁, σ₁²) = π₂ · 𝒩(x* | μ₂, σ₂²)</span>
<span class="trail">Solved as a quadratic — the variance-aware root replaces the midpoint assumption.</span>
</div>

</div>

Note:
ARPU and tenure are not just descriptive numbers — they are decision variables. They feed suitability penalties, churn modelling, segmentation, and the final prioritisation. How they are binned matters. Fixed business rules, like a hard-coded ARPU threshold of 20 dinars, are simple but arbitrary — the operator's round number rarely coincides with the true revenue concentration boundary. Quantile splits force equal-sized groups, which is not the objective either; we want natural separation, not balanced counts. And K-means midpoint assumes equal variance across the two clusters, which is wrong on right-skewed telecom data — it pushes the low-group boundary too high. The choice here is a one-dimensional Gaussian mixture with two components. We fit each metric — ARPU, then tenure — as a weighted mixture of two latent Gaussians, and place the split at the intersection of the two weighted probability density functions. This is mathematically exact, variance-aware, and robust to skew. For ARPU, the high-value cluster has three-point-four-six times the variance of the low cluster, so the GMM threshold sits at twenty-three dinars thirty-three — well above the K-means midpoint of twenty dinars ninety-five. That difference prevents false positives in the suitability penalty logic. For tenure, the two clusters have nearly equal variance and the intersection is close to the midpoint — the GMM confirms this rather than assuming it. Both engineered bands are persisted and feed every downstream module that needs a discrete ARPU or tenure signal.
