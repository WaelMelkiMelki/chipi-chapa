<div class="churn-slide">

<h1>Churn Risk Model</h1>

<span class="subtitle">Supervised binary classification of relative churn risk — percentile ranking, not absolute prediction.</span>

<div class="design-strip">
<div class="design-pill">
<span class="dp-key">Algorithm</span>
<span class="dp-val">XGBoost (binary:logistic)</span>
</div>
<div class="design-pill">
<span class="dp-key">Imbalance</span>
<span class="dp-val">scale_pos_weight = 10.91 (SMOTE rejected)</span>
</div>
<div class="design-pill">
<span class="dp-key">Calibration</span>
<span class="dp-val">Platt scaling (sigmoid)</span>
</div>
</div>

<div class="columns">
<div class="perf-card">
<span class="card-title">Holdout performance · training base 12,412</span>
<div class="perf-grid">
<div class="perf-tile">
<span class="pt-k">ROC-AUC</span>
<span class="pt-v">0.7076</span>
<span class="pt-sub">above telecom range 0.65–0.75</span>
</div>
<div class="perf-tile">
<span class="pt-k">PR-AUC</span>
<span class="pt-v">0.1791</span>
<span class="pt-sub">2.14× baseline 0.0838</span>
</div>
<div class="perf-tile">
<span class="pt-k">Recall @ τ=0.15</span>
<span class="pt-v">0.3798</span>
<span class="pt-sub">operating point</span>
</div>
<div class="perf-tile">
<span class="pt-k">Precision @ τ=0.15</span>
<span class="pt-v">0.2303</span>
<span class="pt-sub">2.74× on eligible diagnostic</span>
</div>
</div>
</div>
<div class="band-col">
<span class="col-title">Percentile risk bands · eligible population (2,629)</span>
<div class="band-bar">
<span class="seg low">Low — 75.0%</span>
<span class="seg med">Med — 15.0%</span>
<span class="seg high">5.0%</span>
<span class="seg crit">5.0%</span>
</div>
<span class="threshold-line">p75 = 0.0543 · p90 = 0.0727 · p95 = 0.1202</span>
<div class="action-list">
<div class="action-row low">
<span class="a-band">Low</span>
<span class="a-act">Standard FWA offer — no overlay</span>
<span class="a-count">1,972</span>
</div>
<div class="action-row med">
<span class="a-band">Medium</span>
<span class="a-act">Discounted entry + 6-mo commitment</span>
<span class="a-count">394</span>
</div>
<div class="action-row high">
<span class="a-band">High</span>
<span class="a-act">Outbound + premium save offer</span>
<span class="a-count">131</span>
</div>
<div class="action-row crit">
<span class="a-band">Critical</span>
<span class="a-act">Executive save desk</span>
<span class="a-count">132</span>
</div>
</div>
</div>
</div>

<div class="shap-row">
<div class="shap-card">
<span class="s-key">ARPU</span>
Higher ARPU → lower churn risk.
</div>
<div class="shap-card">
<span class="s-key">Contract type</span>
Postpaid: bimodal — lock-in for some, bill-shock for others.
</div>
<div class="shap-card">
<span class="s-key">Tenure</span>
Short tenure increases risk, decays with length.
</div>
<div class="shap-card">
<span class="s-key">Usage</span>
U-shaped: both very low and very high usage elevate risk.
</div>
</div>

<div class="impact-band">
<span class="lead">Retention efficiency:</span>
<span class="main">657 at-risk subscribers (&gt;p75) — 263 in High+Critical receive the retention overlay. 2.14× lift over random targeting.</span>
</div>

</div>

Note:
The last decision layer in Chapter 4 addresses retention risk. The objective is a supervised binary classifier that estimates relative churn risk for each eligible subscriber, using the historical subscription records with a ground-truth churn label. XGBoost is the algorithm of choice: it handles mixed-type data natively, applies direct regularisation to leaf weights, and consistently outperforms alternatives on tabular data. Two design decisions matter for interpretation. First, class imbalance: the training base has 8.4 percent churners, so scale_pos_weight is set to 10.91 — the gradient contribution of churners is scaled to match the negative class. SMOTE was rejected because synthetic samples would violate logical telecom constraints. Second, calibration: Platt scaling maps raw XGBoost scores to well-calibrated probabilities. Isotonic regression was rejected as prone to overfitting on this sample size. The holdout performance is ROC 0.7076 and PR-AUC 0.1791, a factor of 2.14 over the random baseline. On the training base, at the operating threshold of 0.15, recall is 0.38 and precision is 0.23. Two operational choices are worth flagging. First, the model is trained at the full-base prevalence of 8.4 percent but applied to the eligible population whose prevalence is 4.6 percent, so the absolute probabilities slightly overstate risk. Second, absolute thresholds are therefore not used. Instead, risk bands are constructed as percentiles on the eligible population: p75, p90, and p95. Low risk holds 1,972 subscribers — 75 percent. Medium, 394. High, 131. Critical, 132. The 657 subscribers above p75 form the retention target set, and the 263 in High and Critical receive the retention overlay in the offer structure. SHAP analysis confirms the directionality of the top drivers: ARPU is negatively correlated with churn; contract type has bimodal effects; short tenure increases risk; and monthly usage follows a U-shape. The business impact is focused targeting: without this model, the retention team would contact all 2,629 eligible subscribers. With it, they contact 657, and the discrimination is a factor of 2.14 better than random. Chapter 4 closes here. Chapter 5 turns these signals into offers, capacity validation, and a campaign action list.
