<div class="backup-slide b2">

<span class="backup-badge">Backup slide · B2</span>

<h1>Algorithm Comparison Tables</h1>

<span class="subtitle">Measured trade-offs for the three algorithm choices in the pipeline — clustering, churn, and score re-encoding.</span>

<div class="table-block">
<span class="table-title">Clustering — K-Prototypes vs alternatives (evaluated on 2,629 eligible subscribers)</span>
<table>
<thead>
<tr><th>Criterion</th><th>K-Means</th><th>K-Modes</th><th>GMM</th><th>Hierarchical</th><th>K-Prototypes ✓</th></tr>
</thead>
<tbody>
<tr><td>Mixed-type support</td><td>None</td><td>None</td><td>None</td><td>Manual</td><td class="choose">Native</td></tr>
<tr><td>Categorical distance</td><td>None</td><td>Hamming</td><td>None</td><td>Manual</td><td class="choose">Hamming</td></tr>
<tr><td>Booleans supported</td><td>No</td><td>Yes</td><td>No</td><td>Yes</td><td class="choose">Yes</td></tr>
<tr><td>Scalability</td><td>Fast</td><td>Fast</td><td>Moderate</td><td>O(n³)</td><td class="choose">Fast</td></tr>
<tr><td>Interpretability</td><td>High</td><td>High</td><td>Moderate</td><td>High</td><td class="choose">High</td></tr>
</tbody>
</table>
</div>

<div class="table-block">
<span class="table-title">Churn classification — XGBoost vs alternatives (holdout 2,483 rows · 8.38% churn · baseline PR-AUC 0.0838)</span>
<table>
<thead>
<tr><th>Model</th><th>ROC-AUC</th><th>PR-AUC (× baseline)</th><th>Recall @0.15</th><th>Precision @0.15</th></tr>
</thead>
<tbody>
<tr><td>Logistic Regression</td><td>0.6242</td><td>0.1182 (1.41×)</td><td>0.0337</td><td>0.1094</td></tr>
<tr><td>Random Forest</td><td>0.6823</td><td>0.1601 (1.91×)</td><td>0.1779</td><td>0.1623</td></tr>
<tr class="choose"><td>XGBoost ✓</td><td>0.7076</td><td>0.1791 (2.14×)</td><td>0.3798</td><td>0.2303</td></tr>
</tbody>
</table>
</div>

<div class="table-block">
<span class="table-title">Final prioritisation — XGBoost regressor (surrogate model, not predictive)</span>
<table>
<thead>
<tr><th>Property</th><th>Value</th><th>Interpretation</th></tr>
</thead>
<tbody>
<tr><td>Test R²</td><td>0.9996</td><td>Memorises the linear MCDA formula</td></tr>
<tr><td>Purpose</td><td>Twofold</td><td class="choose">(1) Validate monotonic ranking · (2) Lightweight CRM API</td></tr>
<tr><td>Top feature (Gain)</td><td>fwa_suitability_score (89.59%)</td><td>Anchors on the most informative column</td></tr>
</tbody>
</table>
</div>

<p class="footer-note">All three comparisons used identical data splits and calibration protocols — the choices reflect measured trade-offs, not defaults.</p>

</div>
