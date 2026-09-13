<div class="pipeline-slide">

<h1>End-to-End Pipeline Overview</h1>

<span class="subtitle">From five raw tables to a unified subscriber-month decision layer.</span>

<div class="flow">
<div class="stage"><span class="idx">01</span><strong>Sources</strong><span class="gloss">T1 · T2 · T3 · T4 · T5</span></div>
<span class="arrow">→</span>
<div class="stage"><span class="idx">02</span><strong>Validation</strong><span class="gloss">Grain · Nulls · Ranges · Joins</span></div>
<span class="arrow">→</span>
<div class="stage"><span class="idx">03</span><strong>Standardisation</strong><span class="gloss">Temporal alignment to snapshot month</span></div>
<span class="arrow">→</span>
<div class="stage"><span class="idx">04</span><strong>Feature Engineering</strong><span class="gloss">5 families · commercial → service</span></div>
<span class="arrow">→</span>
<div class="stage"><span class="idx">05</span><strong>ABT Construction</strong><span class="gloss">50 columns · 7 dimensions</span></div>
<span class="arrow">→</span>
<div class="stage"><span class="idx">06</span><strong>Decision Modules</strong><span class="gloss">Scoring · Segmentation · Churn · Recommendation</span></div>
</div>

<p class="philosophy">Each stage resolves one specific engineering uncertainty before passing a refined artefact to the next.</p>

</div>

Note:
Here is the pipeline as a left-to-right sequence of processing stages. It is the operational counterpart to the five-layer architecture I showed earlier. We start with five source tables. The first stage validates them: grain integrity, null rates, physical ranges, and referential joins. The second stage aligns every table to a common monthly snapshot — a subscriber-day table and a cell-day table cannot be joined to a subscriber-month CRM anchor without this step. The third stage engineers five feature families: commercial, usage, network, coverage, and service consumption. The fourth stage consolidates all of them into the Analytical Base Table — fifty columns across seven dimensions. The final stage is where decision modules consume the ABT: suitability scoring, behavioural segmentation, churn estimation, and offer recommendation. The guiding principle is that each stage resolves one specific engineering uncertainty — a bad join, an anomalous measurement, a missing temporal alignment — before passing a refined artefact forward. This is why the pipeline is not a single monolithic model: it is a sequence of narrow, auditable decisions, each one narrowing the candidate population while increasing decision confidence.
