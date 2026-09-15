# GridGuard AI – Outage & Equipment Failure Advisor

**Team:** Innov8  
**Track:** AI  
**Problem:** U1 – Power Outage Prediction & Grid Equipment Failure Advisor  
**GitHub:** https://github.com/Krishvks07/bob-ai-hackathon-Innov8

## Problem
Utilities still maintain transformers and substations on fixed calendar schedules. Sensors already collect temperature, vibration, partial discharge and oil quality data that show failures weeks in advance, but the data sits unused. Weather forecasts live in a separate system, so a heatwave hitting a degrading transformer never raises urgency. Result: $1M+/hour outages.

## Solution
GridGuard AI is a single-file, zero-install dashboard that:
1. Scores every asset 0-100 with seven transparent weighted factors.
2. Re-ranks CRITICAL/HIGH assets by **risk × grid-impact**.
3. Generates a prioritised maintenance & crew pre-positioning plan with concrete time windows.

## Key Features
- Explainable risk model (no black box)
- Risk × impact prioritisation
- One-click action plan
- Runs completely offline – no API keys, no installs

## Tech Stack
- Pure HTML + CSS + vanilla JavaScript (single file)
- IBM Bob used for scaffolding the risk engine, refining the ranking logic and final code review

## How to Run
1. Open `src/index.html` in any modern browser (Chrome / Edge / Firefox).
2. Click column headers to sort the table.
3. Click **Generate Maintenance & Crew Plan**.

That’s it – zero dependencies.

## Demo
- Live demo: open `src/index.html`
- Screenshots: see `demo/screenshots/`
- Video: see `demo/demo-video-link.txt`

## Known Limitations
- Uses a synthetic 18-asset fleet (realistic for a 1-day hackathon)
- Heuristic model (ready to be replaced by a watsonx.ai trained model)

## What We’re Most Proud Of
The entire solution runs from a single HTML file with full transparency of every weight, making it usable by real grid operators today and easy to evolve tomorrow.
