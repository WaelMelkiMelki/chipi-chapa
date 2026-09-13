<div class="penalty-slide">

<h1>Additive Penalties &amp; Suitability Bands</h1>

<span class="subtitle">Two independent deductions on the eligible base — and four ordinal output bands.</span>

<div class="penalty-row">
<div class="penalty-card">
<span class="badge">Penalty · −20 pts</span>
<span class="headline">No 5G coverage</span>
<span class="condition">coverage_5g_flag == FALSE</span>
<span class="rate">2,338 / 2,629 eligible — <strong>88.9%</strong></span>
<span class="rationale">Address falls back to 4G LTE (≈ 2.0 bps/Hz vs 4.5 bps/Hz on 5G NR) — a permanent throughput ceiling.</span>
</div>
<div class="penalty-card red">
<span class="badge">Penalty · −15 pts</span>
<span class="headline">Low ARPU band</span>
<span class="condition">arpu_band == 'Low ARPU'</span>
<span class="rate">1,560 / 2,629 eligible — <strong>59.3%</strong></span>
<span class="rationale">Monthly revenue may not justify CPE dispatch and acquisition cost within the target payback period.</span>
</div>
</div>

<div class="band-block">
<span class="band-label">Suitability band distribution · 12,412 subscribers</span>
<div class="band-bar">
<span class="seg excluded">Excluded — 78.8%</span>
<span class="seg standard">Standard — 11.7%</span>
<span class="seg premium">9.5%</span>
<span class="seg marginal"></span>
</div>
<div class="band-legend">
<span class="leg-item"><span class="dot excluded"></span>Excluded — <span class="count">9,783</span> — 78.8%</span>
<span class="leg-item"><span class="dot standard"></span>Standard — <span class="count">1,448</span> — 11.7%</span>
<span class="leg-item"><span class="dot premium"></span>Premium — <span class="count">1,181</span> — 9.5%</span>
<span class="leg-item"><span class="dot marginal"></span>Marginal — <span class="count">0</span> — 0.0%</span>
</div>
<span class="band-caption">Premium includes High-ARPU 4G LTE candidates — commercial value offsets lower radio performance.</span>
</div>

<div class="score-strip">
<div class="score-tile">
<span class="val">73</span>
<span class="lbl">Mean score</span>
<span class="sub">population</span>
</div>
<div class="score-tile">
<span class="val">10</span>
<span class="lbl">Std dev</span>
</div>
<div class="score-tile">
<span class="val">65 – 100</span>
<span class="lbl">Range</span>
<span class="sub">min to max</span>
</div>
<div class="score-tile">
<span class="val">65</span>
<span class="lbl">Floor</span>
<span class="sub">double-penalized 100−20−15</span>
</div>
</div>

<div class="paradox-band">
<span class="lead">The commercial paradox of the eligible base:</span>
<span class="main">The subscribers who pass the technical feasibility gate tend to be the least valuable commercially — 88.9% lack 5G coverage and 59.3% fall in the Low-ARPU band.</span>
</div>

</div>

Note:
The subscribers who pass all three hard stops are then scored with additive penalties. Two penalties are applied independently, and each one subtracts an integer from the base score of one hundred. The first penalty is minus twenty points for addresses without 5G coverage. It is nearly universal: 2,338 out of the 2,629 eligible subscribers — 88.9 percent — fall into this penalty. Without 5G coverage, FWA falls back to 4G LTE, whose spectral efficiency is roughly half that of 5G NR. The penalty reflects a permanent throughput ceiling, not a temporary limitation. The second penalty is minus fifteen points for subscribers in the Low-ARPU band. It applies to 1,560 subscribers — 59.3 percent of the eligible base. The rationale is commercial: a subscriber generating only 14 to 18 dinars of monthly revenue may not recover the CPE dispatch and acquisition cost within the target payback period. The final suitability score is bounded between 65 and 100. The double-penalized minimum of 65 is the Standard band floor. A subscriber with a perfect technical profile and high ARPU scores 100 — this is the Premium band. The four output bands are: Premium, 1,181 subscribers. Standard, 1,448. Marginal, zero. And Excluded, 9,783. The distribution reveals a subtle but important commercial paradox. The subscribers who pass the technical feasibility gate — the ones easiest to serve from an engineering standpoint — tend to be the least valuable commercially. Eighty-nine percent lack 5G coverage and nearly sixty percent fall in the low-ARPU band. This is exactly why the segmentation, prioritisation, and recommendation stages that follow matter: they must find the value that the raw suitability score alone cannot see.
