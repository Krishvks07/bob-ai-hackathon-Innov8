# Architecture

```mermaid
graph TD
    A[Synthetic Asset Dataset<br/>sensors + age + maintenance + weather] --> B[Risk Scoring Engine<br/>7 weighted factors]
    B --> C[Ranked Table + Top-8 Chart]
    C --> D[Maintenance & Crew Plan Generator<br/>risk × grid-impact]
    D --> E[Prioritised Action Plan]
Component,Technology,Responsibility
Data,JavaScript arrays,18 realistic synthetic assets
Risk Engine,Pure JS,Weighted multi-factor scoring
Ranking,Pure JS,risk × grid-impact
UI,HTML + CSS + Chart.js (CDN),"Table, chart, plan output"
Deployment,Single HTML file,"Zero install, works offline"
