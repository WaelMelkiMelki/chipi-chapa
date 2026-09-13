<div class="backup-slide b1">

<span class="backup-badge">Backup slide · B1</span>

<h1>GMM Intersection — Mathematical Derivation</h1>

<span class="subtitle">Two-component Gaussian mixture, exact PDF intersection, closed-form quadratic solution.</span>

<div class="two-col">
<div>
<span class="col-label">Setup</span>
<span class="body-text">Two latent components with parameters (π₁, μ₁, σ₁²) and (π₂, μ₂, σ₂²), mixture density:</span>
<span class="mono-line">p(x) = π₁ · 𝒩(x | μ₁, σ₁²) + π₂ · 𝒩(x | μ₂, σ₂²)</span>
<span class="body-text">Defining condition for the intersection x*:</span>
<span class="mono-line">π₁ · 𝒩(x* | μ₁, σ₁²) = π₂ · 𝒩(x* | μ₂, σ₂²)</span>
</div>
<div>
<span class="col-label">Closed form (after taking logs)</span>
<span class="mono-line">A = 1/(2σ₂²) − 1/(2σ₁²)</span>
<span class="mono-line">B = μ₁/σ₁² − μ₂/σ₂²</span>
<span class="mono-line">C = μ₂²/(2σ₂²) − μ₁²/(2σ₁²) + ln(π₁σ₂ / π₂σ₁)</span>
<span class="mono-line">A x² + B x + C = 0</span>
<span class="mono-line">x* = (−B ± √(B² − 4AC)) / (2A)</span>
</div>
</div>

<div class="two-col">
<div>
<span class="col-label">Variance asymmetry</span>
<span class="body-text">When σ₁² ≠ σ₂², the intersection tilts toward the cluster with larger spread. A K-Means midpoint assumes σ₁² = σ₂², biasing the threshold on right-skewed telecom data.</span>
</div>
<div>
<span class="col-label">Root selection</span>
<span class="body-text">The valid threshold is the real root strictly between μ₁ and μ₂. If no such root exists, the algorithm falls back to the midpoint. Equal-variance case degenerates to linear solve.</span>
</div>
</div>

<div class="worked-strip">
<span class="ws-label">Worked example — ARPU (TND / month)</span>
<div class="ws-row">
<div class="ws-chip">
<span class="ws-k">Low cluster</span>
<span class="ws-v">μ₁ = 14.53</span>
</div>
<div class="ws-chip">
<span class="ws-k">High cluster</span>
<span class="ws-v">μ₂ = 27.37</span>
</div>
<div class="ws-chip">
<span class="ws-k">Naive</span>
<span class="ws-v">Midpoint = 20.95</span>
</div>
<div class="ws-chip highlight">
<span class="ws-k">Variance-aware</span>
<span class="ws-v">GMM x* = 23.33</span>
</div>
</div>
<span class="ws-note">High cluster σ² is 3.46× the low cluster σ² — the threshold shifts 2.38 TND right of the midpoint.</span>
</div>

<p class="edge-footer">No real roots → midpoint fallback · Equal variances → linear solve · Minimum viable proportion &lt; 5% → 95th percentile fallback.</p>

</div>
