# Solution Overview – GridGuard AI

GridGuard AI is an explainable risk-scoring and action-planning dashboard.

### Core mechanism
Every asset receives a transparent risk score (0-100) using these weights:

- 0.20 × age  
- 0.18 × hotspot temperature  
- 0.14 × vibration  
- 0.14 × partial discharge  
- 0.14 × (1 – oil quality)  
- 0.08 × days since maintenance  
- 0.12 × weather severity forecast  

All factors are normalised. The operator can see exactly why an asset scored what it did – critical for regulatory justification.

### One-click plan
1. Filter to CRITICAL / HIGH risk assets  
2. Re-rank by **risk × grid-impact** (so a hospital feeder ranks higher than a slightly riskier low-impact feeder)  
3. Assign action window (24-48 h or 5-7 days)  
4. Surface the real sensor drivers that caused the score  
5. Flag the geographic region that needs crew pre-positioning first  

### Why this is different
- Completely transparent (no black-box model)  
- Zero infrastructure – single HTML file  
- Designed so a real operator can open it and act in under 60 seconds


# Solution Overview

GridGuard AI is a single-page, zero-install dashboard that:

1. Scores every asset with a transparent 7-factor risk model
2. Visualises the ranked fleet
3. Generates a prioritised maintenance & crew pre-positioning plan with one click

The risk formula is deliberately explainable so operators and regulators can see exactly why an asset scored what it did.

Assets are then re-ranked by **risk × grid-impact** so that a transformer feeding a hospital is prioritised even if its raw risk is slightly lower than one in a low-impact area.
