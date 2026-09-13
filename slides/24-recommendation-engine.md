<div class="recommendation-slide">

<h1>Two-Tier Service Recommendation</h1>

<span class="subtitle">Tier 1 preserves billing rhythm; Tier 2 triggers value-add bundles from consumption signals.</span>

<span class="block-label">Tier 1 · Base plan — frictionless 1:1 mapping from contract_type</span>
<div class="tier1-row">
<div class="tier1-pill">
<span class="t1-route">Prepaid / Hybrid → FWA Prepaid</span>
<span class="t1-count">1,733 subs · 66.0%</span>
</div>
<div class="tier1-pill">
<span class="t1-route">Postpaid → FWA Postpaid</span>
<span class="t1-count">896 subs · 34.0%</span>
</div>
</div>

<span class="block-label">Tier 2 · Value-add bundles — three independent rules evaluated in parallel</span>
<div class="rule-row">
<div class="rule-card green">
<span class="rule-name">IPTV Upsell</span>
<span class="rule-cond">streaming_heavy ∧ ¬iptv_active</span>
<span class="rule-offer"><strong>5G FWA + IPTV Bundle</strong> — ARPU uplift +25–35 TND</span>
<span class="rule-hit">544 subs · 20.7%</span>
</div>
<div class="rule-card red">
<span class="rule-name">Gaming Add-On</span>
<span class="rule-cond">gaming_heavy ∧ 5G coverage</span>
<span class="rule-offer"><strong>Low-Latency Gaming Add-On</strong> — dedicated QoS</span>
<span class="rule-hit">89 subs · 3.4%</span>
</div>
<div class="rule-card">
<span class="rule-name">Convergent</span>
<span class="rule-cond">high_voip ∧ multi_line</span>
<span class="rule-offer"><strong>Convergent Fixed-Mobile Add-On</strong> — 10% + 5% discount</span>
<span class="rule-hit">392 subs · 14.9%</span>
</div>
</div>

<span class="block-label">Final offer distribution · 2,629 eligible subscribers</span>
<div class="offer-bar">
<span class="seg base">Base Only — 65.3%</span>
<span class="seg iptv">Base + IPTV — 18.6%</span>
<span class="seg conv">Base + Convergent — 12.8%</span>
<span class="seg multi"></span>
<span class="seg game"></span>
</div>
<div class="offer-legend">
<span class="leg-item"><span class="dot base"></span>Base Only — <span class="count">1,716</span> — 65.3%</span>
<span class="leg-item"><span class="dot iptv"></span>Base + IPTV — <span class="count">488</span> — 18.6%</span>
<span class="leg-item"><span class="dot conv"></span>Base + Convergent — <span class="count">336</span> — 12.8%</span>
<span class="leg-item"><span class="dot multi"></span>Multi-Addon Bundle — <span class="count">56</span> — 2.1%</span>
<span class="leg-item"><span class="dot game"></span>Base + Gaming — <span class="count">33</span> — 1.3%</span>
</div>

<div class="insight-band">
<span class="lead">Monetisation headline:</span>
<span class="main">34.7% of the eligible base (913 subscribers) receives at least one value-add bundle — the pipeline functions as both eligibility filter and digital service monetisation framework.</span>
</div>

</div>

Note:
Chapter 5 opens with the recommendation engine. Its role is not to confirm commercial conversion — no historical response labels exist — but to assign an interpretable candidate offer for each eligible subscriber. The engine is deterministic and rule-based. Tier 1 is a frictionless one-to-one mapping from the subscriber's existing contract type to the FWA base plan: prepaid and hybrid subscribers keep the top-up rhythm and route to FWA Prepaid, which is 66 percent of the eligible base. Postpaid subscribers route to FWA Postpaid, integrating seamlessly into the existing monthly billing cycle, which is 34 percent. Tier 2 consists of three independent conditional rules, each combining a lifestyle signal with a network feasibility condition. Rule one: streaming-heavy subscribers without an active IPTV subscription receive the 5G FWA plus IPTV bundle, converting unmanaged OTT consumption into a managed, revenue-generating service with a monthly ARPU uplift of 25 to 35 dinars. This rule fires for 544 subscribers — 20.7 percent of the eligible base. Rule two: heavy gamers on addresses with verified 5G coverage receive the low-latency gaming add-on with dedicated QoS. This rule fires for 89 subscribers — 3.4 percent — deliberately narrow so the operator only commits to low-latency QoS where 5G can physically deliver it. Rule three: high-VoIP subscribers managing multiple active lines receive the convergent fixed-mobile add-on. This rule fires for 392 subscribers — 14.9 percent. The final offer distribution is 65.3 percent base only, 18.6 percent base plus IPTV, 12.8 percent base plus convergent, 2.1 percent multi-addon bundle, and 1.3 percent base plus gaming. In total, 34.7 percent of the eligible base — 913 subscribers — receives at least one value-add bundle. This is the moment in the pipeline where a coverage-constrained eligibility filter becomes a monetisation framework: the funnel does not merely exclude, it personalises.
