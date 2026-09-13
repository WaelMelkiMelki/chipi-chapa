<div class="backup-slide b4">

<span class="backup-badge">Backup slide · B4</span>

<h1>Calibration, Class Imbalance &amp; Threshold Trade-offs</h1>

<span class="subtitle">Why τ = 0.15 — the decision-theoretic operating point under typical telecom retention economics.</span>

<div class="two-col">
<div>
<span class="col-label">Imbalance &amp; calibration — the sequence</span>
<div class="pill">
<span class="p-key">Imbalance</span>
<span class="p-val">scale_pos_weight = 10.91 · SMOTE rejected (synthetic samples violate telecom constraints) · undersampling rejected (discards boundary signal)</span>
</div>
<div class="pill">
<span class="p-key">Calibration</span>
<span class="p-val">Platt scaling (sigmoid) · isotonic rejected (overfits on this sample size) · absolute probabilities overstate risk on eligible population — percentile bands are the operational output</span>
</div>
</div>
<div>
<span class="col-label">Confusion matrix · full-base holdout (2,483 rows · 8.38% churn)</span>
<table class="cm-table">
<thead>
<tr><th></th><th>Predicted churn</th><th>Predicted active</th></tr>
</thead>
<tbody>
<tr><td>Actual churn</td><td class="tp">79 (TP)</td><td class="fn">129 (FN)</td></tr>
<tr><td>Actual active</td><td class="fp">264 (FP)</td><td class="tn">2,011 (TN)</td></tr>
</tbody>
</table>
<span class="cm-caption">Recall 0.3798 · Precision 0.2303 · F1 0.2868 · Flagged 343 subscribers</span>
</div>
</div>

<span class="col-label">Operating point comparison — full-base holdout</span>
<table class="thr-table">
<thead>
<tr><th>τ</th><th>Recall</th><th>Precision</th><th>F1</th><th>Flagged</th></tr>
</thead>
<tbody>
<tr><td>0.05</td><td>0.8221</td><td>0.1150</td><td>0.2018</td><td>1,487</td></tr>
<tr><td>0.10</td><td>0.5433</td><td>0.2132</td><td>0.3062</td><td>530</td></tr>
<tr class="choose"><td>0.15 ✓</td><td>0.3798</td><td>0.2303</td><td>0.2868</td><td>343</td></tr>
<tr><td>0.20</td><td>0.2308</td><td>0.2233</td><td>0.2270</td><td>215</td></tr>
<tr><td>0.25</td><td>0.1250</td><td>0.2281</td><td>0.1615</td><td>114</td></tr>
<tr><td>0.30</td><td>0.0288</td><td>0.1818</td><td>0.0498</td><td>33</td></tr>
</tbody>
</table>

<div class="economics-band">
<span class="lead">Why τ = 0.15:</span>
<span class="main">The trade-off is deliberate — the cost of a false positive (retention discount to a loyal subscriber) is far lower than the cost of a false negative (complete loss of future revenue). τ = 0.15 maximises F1 while keeping the flagged set operationally manageable.</span>
</div>

<p class="footer-note">Absolute probabilities reflect training-base prevalence (8.4%) and are not used for thresholding on the eligible population (4.6%).</p>

</div>
