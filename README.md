# GridGuard AI – Outage & Equipment Failure Advisor

**Team:** Innov8  
**Track:** AI  
**Problem:** U1 – Power Outage Prediction & Grid Equipment Failure Advisor  
**Hackathon:** IBM BoB AI Innovation Hackathon 2026

## Problem
Utilities still run maintenance on fixed calendars while sensors already detect failure signatures weeks in advance. Weather data sits in a separate system, so a heatwave hitting a degrading transformer never triggers extra urgency. Failures cost $1M+ per hour of outage.

## Solution
GridGuard AI turns raw sensor + weather data into an **explainable risk score** and a **one-click prioritised action plan**.

- Risk score (0-100) using 7 transparent weighted factors
- Re-ranks assets by risk × grid-impact
- Generates concrete crew dispatch windows and region priority

## Key Features
- Fully explainable risk model (no black box)
- One-click Maintenance & Crew Plan
- Zero-install single HTML file
- Built with help of IBM Bob (scaffolding + iteration + review)

## Tech Stack
- Pure HTML + CSS + JavaScript
- Chart.js (CDN)
- No backend, no API keys, no build step

## How to Run
1. Open `src/index.html` in any modern browser (Chrome / Edge / Firefox)
2. Click column headers to sort the table
3. Click **Generate Maintenance & Crew Plan**

That’s it – no installation required.

## Demo
- Live demo: See `demo/live-demo-url.txt`
- Video: See `demo/demo-video-link.txt`
- Screenshots: `demo/screenshots/`

## Known Limitations
- Uses synthetic 18-asset fleet (realistic for a 1-day hackathon)
- Heuristic model (ready to be replaced by watsonx.ai trained model)

## What We’re Most Proud Of
The completely transparent risk formula + the risk × grid-impact re-ranking that prioritises hospital-feeding assets correctly.
