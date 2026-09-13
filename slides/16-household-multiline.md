<div class="household-slide">

<h1>Household &amp; Multi-Line Features</h1>

<span class="subtitle">One third of the base is a household or B2B account — a single CPE can consolidate multiple mobile lines.</span>

<div class="columns">
<div class="donut-panel">
<span class="donut-label">Structural split · 12,412 subscribers</span>
<div class="donut-wrap">
<div class="donut"></div>
<div class="donut-center"><span class="big-num">12,412</span><span class="big-lbl">subscribers</span></div>
</div>
<ul class="donut-legend">
<li><span class="dot single"></span>Single-Line (B2C / Individual) — <span class="count">8,308</span> — 66.9%</li>
<li><span class="dot multi"></span>Multi-Line (Household / B2B) — <span class="count">4,104</span> — 33.1%</li>
</ul>
</div>
<div class="dist-panel">
<span class="dist-label">Active line-count distribution</span>
<div class="dist-row r1">
<span class="bucket">1 line · bulk</span>
<div class="bar-track"><div class="bar-fill"></div></div>
<span class="cnt">~6,000</span>
</div>
<div class="dist-row r2">
<span class="bucket">2 lines</span>
<div class="bar-track"><div class="bar-fill"></div></div>
<span class="cnt">~4,300</span>
</div>
<div class="dist-row r34">
<span class="bucket">3–4 lines</span>
<div class="bar-track"><div class="bar-fill"></div></div>
<span class="cnt">~1,900</span>
</div>
<div class="dist-row r1014">
<span class="bucket">10–14 lines</span>
<div class="bar-track"><div class="bar-fill tail"></div></div>
<span class="cnt">~200</span>
</div>
<span class="dist-note">No subscribers at 5–9 lines; the tail concentrates at 10–14 lines (P99 = 13, max = 14). Bucket counts are approximate — derived from percentile distribution.</span>
</div>
</div>

<div class="insights-row">
<div class="insight-card">
<span class="headline">Revenue consolidation per CPE</span>
<span class="body">A single fixed FWA router serves an entire household or office. Migrating a multi-line account consolidates multiple mobile plans behind one CPE deployment — the same hardware cost as a single-line migration with multiplied revenue impact.</span>
</div>
<div class="insight-card red">
<span class="headline">The B2B tail justifies the uncapped multiplier</span>
<span class="body">Only 3.5% of subscribers have more than 5 lines, all in the 10–14 line B2B range; 2.2% carry 12+ lines. Capping the multiplier would under-value legitimate enterprise accounts.</span>
</div>
</div>

<p class="tagline">Multi-line segments are the highest-value targets for the initial CPE dispatch wave.</p>

</div>

Note:
The last piece of feature engineering closes Chapter 2. FWA is inherently a shared connectivity solution: one CPE router serves an entire home or office. Differentiating single-line accounts from multi-line accounts is therefore critical for offer structure and for prioritisation. The structural split is clean: two-thirds of the base — 66.9 percent, or 8,308 subscribers — are single-line. The remaining third — 33.1 percent, 4,104 subscribers — are multi-line households or B2B accounts. The line-count distribution shows the tail: the vast majority hold one or two lines, and there are zero subscribers at five to nine lines — the tail concentrates at ten to fourteen lines, with P99 at thirteen and an absolute maximum of fourteen. This long tail has two strategic implications. First, the multi-line segment is a high-value target: a single fixed connection can consolidate several mobile lines behind one CPE deployment. The same hardware cost as a single-line migration, with multiplied revenue impact. Second, the long tail justifies the uncapped household multiplier that will be used in the final prioritisation stage: capping the multiplier would under-value legitimate 11-to-14-line enterprise accounts. Only 3.5 percent of subscribers have more than five lines, and those are the accounts we want to prioritise. The multi_line_flag and the raw num_active_lines column both flow into every downstream module that needs household context.
