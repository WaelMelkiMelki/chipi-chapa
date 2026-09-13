<div class="segmentation-slide">

<h1>Behavioural Segmentation via K-Prototypes</h1>

<span class="subtitle">Mixed-type clustering of 2,629 eligible subscribers — four interpretable personas.</span>

<div class="algo-row">
<div class="algo-card">
<span class="algo-name">✗ K-Means</span>
<span class="algo-sub">requires one-hot encoding; inflates distance</span>
</div>
<div class="algo-card">
<span class="algo-name">✗ K-Modes</span>
<span class="algo-sub">discards numerical signal entirely</span>
</div>
<div class="algo-card">
<span class="algo-name">✗ GMM</span>
<span class="algo-sub">assumes Gaussian; invalid for boolean/categorical</span>
</div>
<div class="algo-card">
<span class="algo-name">✗ Hierarchical</span>
<span class="algo-sub">custom distance metric; O(n³) expensive</span>
</div>
<div class="algo-card chosen">
<span class="algo-name">✓ K-Prototypes</span>
<span class="algo-sub">native mixed-type via Euclidean + Hamming</span>
</div>
</div>

<div class="kstrip">
<span class="kstrip-label">K selected by dual validation:</span>
<span class="kstrip-content">cost elbow + silhouette · business constraint K ∈ [3,6] · optimal K = 4 · silhouette peak = 0.2765</span>
</div>

<div class="persona-row">
<div class="persona-card c0">
<span class="chip">Cluster 0</span>
<span class="pname">High-Value Prepaid Streamers</span>
<span class="pstat"><span class="pk">Size</span><span class="pv">1,003 · 38.2%</span></span>
<span class="pstat"><span class="pk">Contract</span><span class="pv">Prepaid 51.1%</span></span>
<span class="pstat"><span class="pk">Usage</span><span class="pv">~299 GB / mo</span></span>
<span class="pstat"><span class="pk">ARPU</span><span class="pv">~35 TND</span></span>
<span class="pstat"><span class="pk">5G-handset</span><span class="pv">13.6%</span></span>
<span class="pstat"><span class="pk">Take-rate</span><span class="pv">40%</span></span>
<span class="note">Premium tier — IPTV bundling candidates.</span>
</div>
<div class="persona-card c1">
<span class="chip">Cluster 1</span>
<span class="pname">Mass-Market Prepaid Base</span>
<span class="pstat"><span class="pk">Size</span><span class="pv">1,298 · 49.4%</span></span>
<span class="pstat"><span class="pk">Contract</span><span class="pv">Prepaid 82.6%</span></span>
<span class="pstat"><span class="pk">Usage</span><span class="pv">~260 GB / mo</span></span>
<span class="pstat"><span class="pk">ARPU</span><span class="pv">~18 TND</span></span>
<span class="pstat"><span class="pk">5G-handset</span><span class="pv">5.9%</span></span>
<span class="pstat"><span class="pk">Take-rate</span><span class="pv">10%</span></span>
<span class="note">Volume segment — Standard tier.</span>
</div>
<div class="persona-card c2">
<span class="chip">Cluster 2 · highest priority</span>
<span class="pname">Ultra-Heavy Postpaid Power-Users</span>
<span class="pstat"><span class="pk">Size</span><span class="pv">275 · 10.5%</span></span>
<span class="pstat"><span class="pk">Contract</span><span class="pv">Postpaid 57.1%</span></span>
<span class="pstat"><span class="pk">Usage</span><span class="pv">~1,364 GB / mo</span></span>
<span class="pstat"><span class="pk">ARPU</span><span class="pv">~31 TND</span></span>
<span class="pstat"><span class="pk">5G-handset</span><span class="pv">8.4%</span></span>
<span class="pstat"><span class="pk">Take-rate</span><span class="pv">60%</span></span>
<span class="note">Retention-sensitive — Premium 5G bundle.</span>
</div>
<div class="persona-card c3">
<span class="chip">Cluster 3</span>
<span class="pname">Mid-Tier Prepaid Heavy-Users</span>
<span class="pstat"><span class="pk">Size</span><span class="pv">53 · 2.0%</span></span>
<span class="pstat"><span class="pk">Contract</span><span class="pv">Prepaid 69.8%</span></span>
<span class="pstat"><span class="pk">Usage</span><span class="pv">~412 GB / mo</span></span>
<span class="pstat"><span class="pk">ARPU</span><span class="pv">~24 TND</span></span>
<span class="pstat"><span class="pk">5G-handset</span><span class="pv">0.0%</span></span>
<span class="pstat"><span class="pk">Take-rate</span><span class="pv">25%</span></span>
<span class="note">Niche micro-segment — Standard + streaming add-on.</span>
</div>
</div>

<div class="priority-band">
<span class="lead">Downstream impact:</span>
<span class="main">Clusters 0 and 2 route to Premium Tier 1 offers; Clusters 1 and 3 to Standard. Cluster 2 carries the highest baseline prioritisation and take-rate weight (60%).</span>
</div>

</div>

Note:
The eligible population is not a homogeneous group. Although all 2,629 subscribers satisfy the minimum technical and commercial conditions for FWA migration, they differ significantly in revenue, usage intensity, contract type, and handset capability. The objective here is to segment this eligible base into interpretable behavioural personas using unsupervised clustering. Telecom subscriber data is inherently mixed-type: some features are continuous, like ARPU and monthly data volume, and others are categorical, like contract type and handset readiness. K-Means requires one-hot encoding, which distorts distance metrics. K-Modes discards numerical signal entirely. GMM assumes Gaussian distributions, invalid for categorical variables. Hierarchical clustering requires custom distance metrics and scales as O n cubed. The choice is K-Prototypes, which handles mixed numerical and categorical data natively via a combined Euclidean plus Hamming distance with an automatically weighted gamma parameter. The optimal number of clusters was determined by a dual-validation approach: the cost function elbow and the silhouette score on the numerical subspace, constrained by a business rule limiting K to the interval three to six. Four clusters emerged as the optimum: peak silhouette of 0.2765 with a cost elbow at K equals four. This produces four personas. Cluster 1 — Mass-Market Prepaid Base — is the largest, at 1,298 subscribers and 49.4 percent of the eligible base. Cluster 0 — High-Value Prepaid Streamers — the second largest, 1,003 subscribers, with the highest average ARPU at 35 dinars per month. Cluster 2 — Ultra-Heavy Postpaid Power-Users — the smallest commercial-segment of significance, 275 subscribers, with the highest monthly usage at over 1,364 gigabytes, postpaid-majority contracts, and the strongest retention-sensitive profile. And Cluster 3 — Mid-Tier Prepaid Heavy-Users — a niche micro-segment of 53 subscribers with usage matching postpaid power users. Each cluster carries a differentiated take-rate assumption: 60 percent for Cluster 2, 40 percent for Cluster 0, 25 percent for Cluster 3, and 10 percent for Cluster 1. These take rates feed the capacity simulation later. Clusters 0 and 2 route to Premium Tier 1 offers; Clusters 1 and 3 to Standard. The four-persona framework transforms the eligible base from a homogeneous list into a structured portfolio of commercially distinct segments.
