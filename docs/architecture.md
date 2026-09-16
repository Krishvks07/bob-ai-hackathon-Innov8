# Architecture – GridGuard AI

## Overview

GridGuard AI is a zero-install, single-page web application that runs entirely in the browser.  
It takes synthetic (or real) grid-asset sensor data + weather forecasts, computes an **explainable risk score** for every asset, re-ranks the highest-risk assets by **grid impact**, and produces a ready-to-execute maintenance & crew pre-positioning plan — all without any backend, API keys, or external dependencies.

## High-Level Architecture

```mermaid
graph TD
    A[Synthetic Asset Dataset<br/>sensors · age · maintenance · weather] --> B[Risk Scoring Engine]
    B --> C[Explainable Risk Score<br/>0–100]
    C --> D[Ranked Table + Top-8 Chart]
    D --> E[Maintenance & Crew Plan Generator]
    E --> F[Prioritised Action Plan<br/>risk × grid-impact]
    
    style A fill:#e1f5fe
    style B fill:#fff3e0
    style C fill:#e8f5e9
    style D fill:#f3e5f5
    style E fill:#fce4ec
    style F fill:#e0f2f1

Component,Technology,Responsibility
Data Layer,Pure JavaScript objects / arrays,"Holds the synthetic fleet of 18 assets with sensor readings (hotspot temp, vibration, partial discharge, oil quality), age, days since last maintenance, and regional weather severity forecast."
Risk Scoring Engine,Weighted multi-factor formula (JS),Calculates a transparent 0–100 risk score using 7 normalised factors. Every weight is visible and adjustable.
Visualisation Layer,Chart.js (CDN) + HTML tables,Renders a sortable ranked table and a Top-8 bar chart of the highest-risk assets.
Plan Generator,Pure JavaScript,"Re-ranks CRITICAL/HIGH assets by risk × grid-impact, assigns action windows (24–48 h vs 5–7 days), pulls the exact sensor drivers, and flags the region that needs crews first."
UI Shell,Single HTML file + vanilla CSS,"Completely self-contained. No build step, no npm, no server required. Opens with a double-click."
