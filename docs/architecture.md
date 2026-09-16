# Architecture – GridGuard AI

## Overview

GridGuard AI is a zero-install, single-page web application that runs entirely in the browser.  
It takes synthetic grid-asset sensor data + weather forecasts, computes an **explainable risk score** for every asset, re-ranks the highest-risk assets by **grid impact**, and produces a ready-to-execute maintenance & crew pre-positioning plan — all without any backend, API keys, or external dependencies.

## High-Level Architecture

```mermaid
graph TD
    A[Synthetic Asset Dataset] --> B[Risk Scoring Engine]
    B --> C[Explainable Risk Score 0-100]
    C --> D[Ranked Table + Top-8 Chart]
    D --> E[Maintenance & Crew Plan Generator]
    E --> F[Prioritised Action Plan]

Component,Technology,Responsibility
Data Layer,Pure JavaScript,"Holds 18 synthetic assets with sensor readings, age, maintenance history and weather"
Risk Scoring Engine,Weighted multi-factor JS,Calculates transparent 0-100 risk score using 7 normalised factors
Visualisation Layer,Chart.js + HTML tables,Sortable ranked table and Top-8 bar chart
Plan Generator,Pure JavaScript,Re-ranks by risk × grid-impact and creates crew plan
UI Shell,Single HTML + CSS,"Zero-install, runs with double-click"

Data Flow (End-to-End)

1.Ingest – Synthetic dataset loads when the page opens.
2.Score – Risk Scoring Engine calculates:
Risk = 0.20×age + 0.18×hotspot + 0.14×vibration
     + 0.14×partial_discharge + 0.14×(1-oil_quality)
     + 0.08×days_since_maintenance + 0.12×weather_severity

3.Rank & Visualise – Table and chart update automatically.
4.Act – One click generates the prioritised maintenance & crew plan.

Design Decisions

1.Explainability first – Every weight is visible so operators and regulators can understand the score.
2.Zero dependencies – Judges can open src/index.html with zero setup.
3.Risk × Grid-Impact ranking – Hospital-feeding assets get higher priority even if raw risk is slightly lower.
4.Synthetic data – Realistic 18-asset fleet is better for a 1-day hackathon than incomplete live integration.


Future Scaling Path

Stage,What changes
Today,Heuristic model + synthetic fleet
Next,Train real ML model on historical failures using IBM watsonx.ai
At scale,Live SCADA/HUMS + weather API + feedback loop from confirmed failures.

Security & Deployment Notes
1.No credentials, no API keys, no network calls → zero attack surface.
2.Runs 100% client-side.
3.Can later be connected to IBM Bob / watsonx agents when live data is available.
