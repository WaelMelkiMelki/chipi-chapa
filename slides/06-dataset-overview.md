<div class="dataset-slide">

<h1>Dataset Overview</h1>

<span class="subtitle">Five heterogeneous tables, different grains, one integration challenge.</span>

<div class="mermaid">
flowchart LR
T2["<b>T2 · CRM Master</b><br/>subscriber_id · snapshot_month<br/><i>Commercial anchor</i>"]
T1["<b>T1 · Daily</b><br/>subscriber_id · snapshot_date<br/><i>Usage & device</i>"]
T5["<b>T5 · Service</b><br/>subscriber_id · snapshot_month<br/><i>Streaming · Gaming · VoIP</i>"]
T4["<b>T4 · Address</b><br/>address_id<br/><i>RSRP · SINR · 4G/5G flags</i>"]
T3["<b>T3 · RAN KPI</b><br/>cell_id · kpi_date<br/><i>PRB · Throughput</i>"]
T1 -- subscriber_id --> T2
T5 -- subscriber_id --> T2
T4 -- address_id --> T2
T3 -- cell_id --> T4
T3 -. serving cell .-> T1
classDef hub fill:#CF0A2C,stroke:#003366,stroke-width:2px,color:#FFFFFF,rx:6,ry:6;
classDef spoke fill:#F5F7FA,stroke:#003366,stroke-width:2px,color:#1A1A1A,rx:6,ry:6;
class T2 hub;
class T1,T3,T4,T5 spoke;
</div>

<p class="caption">Hub-and-spoke structure centred on T2 — validating every join is prerequisite to any downstream work.</p>

</div>

Note:
The pipeline consumes five heterogeneous tables from the operator's data platform. T2, the CRM master, is the commercial anchor — one row per subscriber per month, carrying ARPU, contract type, tenure, and the churn label. Around it, four spokes. T1, daily subscriber activity: usage, sessions, device generation, serving cell. T5, monthly service consumption: streaming, gaming, VoIP, IPTV, IoT. T4, a static address-level coverage grid: predicted RSRP, SINR, 4G and 5G flags, and fibre coverage. And T3, daily cell-level RAN KPIs: PRB utilisation and downlink throughput. These tables have four different grains: subscriber-day, subscriber-month, cell-day, and static address. Joining them without care would fan out the subscriber count, inflate traffic volumes, and bias every downstream decision. Validating grain integrity, referential integrity, and temporal alignment is therefore not a formality — it is the prerequisite for trusting any of the numbers that follow.
