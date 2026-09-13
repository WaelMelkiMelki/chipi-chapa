<div class="arch-slide">

<h1>Solution Architecture</h1>

<span class="subtitle">Five logical layers — from raw telecom data to a pilot-ready campaign action list.</span>

<div class="mermaid">
flowchart TB
A["<b>1 · Data Reliability</b><br/>Profiling · Cleaning · Temporal standardisation<br/><i>5 source tables → trusted data</i>"]
B["<b>2 · Feature Construction</b><br/>Commercial · Usage · Network · Coverage · Service<br/><i>Five feature families</i>"]
C["<b>3 · Analytical Base Table</b><br/>Subscriber-month · 50 columns · 7 dimensions<br/><i>The unified decision layer</i>"]
D["<b>4 · Decision Intelligence</b><br/>Suitability scoring · Segmentation · Prioritisation · Churn<br/><i>Eligibility, personas, ranking, risk</i>"]
E["<b>5 · Campaign Execution</b><br/>Two-tier recommendation · PRB validation · Campaign action list<br/><i>Pilot-ready output</i>"]
A --> B --> C --> D --> E
classDef layer fill:#F5F7FA,stroke:#003366,stroke-width:2px,color:#1A1A1A,rx:6,ry:6;
classDef final fill:#CF0A2C,stroke:#003366,stroke-width:2px,color:#FFFFFF,rx:6,ry:6;
class A,B,C,D layer;
class E final;
</div>

<p class="annotation">Each layer resolves one specific engineering uncertainty before the next begins.</p>

</div>

Note:
The solution is organised into five logical layers, and this diagram is the structural spine of everything I will present. The first layer, Data Reliability, performs profiling, cleaning, and temporal standardisation across the five source tables, producing a trusted dataset. The second layer, Feature Construction, engineers five feature families: commercial, usage, network, coverage, and service consumption. The third layer — the Analytical Base Table — consolidates all of these into a single subscriber-month representation with fifty columns across seven dimensions. This ABT is the unified decision layer: every downstream module reads from it, so scoring, segmentation, churn modelling, and capacity simulation never disagree about the underlying subscriber. The fourth layer is Decision Intelligence: eligibility scoring, behavioural segmentation, multi-criteria prioritisation, and churn-risk estimation. The fifth and final layer is Campaign Execution: two-tier offer recommendation, PRB capacity validation, and the campaign action list prepared for pilot review. Each layer resolves one specific engineering uncertainty before the next layer begins. This is not a pipeline that optimises a single objective — it is a decision architecture that narrows the candidate population while increasing decision confidence at every step.
