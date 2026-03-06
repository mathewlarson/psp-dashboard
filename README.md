# Public Safety Pulse — Dashboard README
## Version 26 · March 2026

**Live:** https://mathewlarson.github.io/psp-dashboard
**Organization:** City Science Lab San Francisco × MIT Media Lab City Science

---

## What This Is

Public Safety Pulse (PSP) is a Phase 0 analytical dashboard built on 28.6 million public records from San Francisco (2003–2026). It demonstrates the data foundation and product vision for Phase 1: a continuous, block-level public experience measurement system for city agencies and community benefit districts.

Single HTML file. No server required. No API keys. Open in any browser.

---

## Quick Start

```bash
# Open directly
open psp_dashboard_v26.html

# Or serve locally
python3 -m http.server 8000
# then: http://localhost:8000/psp_dashboard_v26.html

# Live version
# https://mathewlarson.github.io/psp-dashboard
```

---

## Tab Reference

| Tab | What It Shows |
|-----|---------------|
| **Home** | Problem / approach / outcome orientation. Navigation to all tabs. |
| **The Vision** | Phase 1 roadmap. Static product mockup. Interactive Mid-Market prototype. |
| **Neighborhood Baseline Map** | 41 SF neighborhoods. 5 data layers. Time windows 1M/3M/12M. Time Lapse 2016–2026. |
| **What the Data Shows** | 5-layer overview. 4 validated findings. Structural break chart. Escalation events. |
| **Perception & the Gap** | City Survey data. CityBeat poll. Perception gap visualization. Panel model finding. |
| **Interventions** | Phase 0 operational signals. Early warning patterns. Proactive detection framing. |
| **Partners** | City Science Lab SF + MIT Media Lab City Science. |
| **Data & Methods** | Full methodology. Data sources. Model specification. |

---

## Neighborhood Baseline Map — Controls

| Control | Function |
|---------|----------|
| **Layer row** | All / Safety / Conditions / Foot Traffic / Economic / Sentiment — recolors map |
| **1M / 3M / 12M** | Time window — applies per-neighborhood score deltas, map recolors |
| **⏱ TL** | Opens Time Lapse strip — animate 2016–2026 with play/scrub |
| **Click neighborhood** | Opens full detail drawer (full-width on mobile) |

**Reading the map:** Each neighborhood colored relative to its own 20-year historical average — not compared to other neighborhoods. Red = currently elevated above that neighborhood's norm. Green = quieter than usual.

**Time Lapse:** Runs 2016–2026 — the decade that includes the 2019 structural break, COVID period, and partial recovery. Color changes are meaningful and visible across all neighborhoods.

---

## Phase 1 Vision Prototype — Mid-Market CBD

The interactive map on The Vision tab shows 12 blocks across the Market/Mission corridor (5th to 10th St) with illustrative Phase 1 data.

**Reading the blocks:**
- Fill color = sentiment score (green = strong, red = concern)
- Border color = urgency triage: purple (critical) · red (high) · amber (moderate) · green (low)
- Border weight increases with urgency

**Layer toggles:** Each has a distinct colored dot — purple (Sentiment), red (Safety), amber (Conditions), indigo (Perception Gap).

**Block detail:** Click any block to see urgency badge, sentiment/safety/conditions/gap scores, primary driver analysis, and recommended interventions.

All data is illustrative. Labeled "Phase 1 Vision Prototype · not live data."

---

## Data

All data is embedded in the HTML. No external files required.

### Neighborhood Scores (41 neighborhoods)

| Layer | Primary Sources | Records | Coverage |
|-------|----------------|---------|----------|
| Safety Incidents | SFPD Incidents, CAD, Fire/EMS | 6.9M | 2003–2026 |
| Street Conditions | 311 (graffiti, encampments, dumping, cleaning) | 8.4M | 2008–2026 |
| Foot Traffic & Transit | SFMTA ridership, parking, permits | ~3M | 2012–2026 |
| Economic Vitality | Business registrations, sales tax revenue | ~2M | 2005–2026 |
| Public Sentiment (proxy) | SF Controller's City Survey | Biennial | 1996–2024 |

Scores = deviation from each neighborhood's own historical baseline. Higher = elevated above normal.

**Time window adjustments:** `TW_DELTA` applies per-neighborhood score deltas for 1M and 3M windows — directional approximations, not recomputed from raw data.

---

## Phase 0 Findings (Validated)

**1. The 2018–2019 Structural Break**
The predictive relationship between conditions and perceived safety — stable at R²=0.824 for 15 years — broke down sharply in 2018–2019.

**2. Government Responsiveness as the Dominant Post-2019 Predictor**
After 2019, the strongest predictor of neighborhood safety perception shifted to whether government appears to be paying attention and responding. Source: panel fixed-effects model, 41 neighborhoods, 2003–2018 training window.

**3. The Perception Gap**
Conditions measured monthly for 41 neighborhoods. Resident experience measured at district level, every two years. That gap is where intervention resources get misallocated.

**4. 118 Escalation Events**
Rate-ratio methodology identified 118 events where multiple signals simultaneously exceeded neighborhood baselines by ≥1.3× for two or more consecutive weeks.

---

## What Phase 0 Can and Cannot Measure

**Can:** Incident rate, response time, resolution rate at neighborhood level. Directional patterns and precursor signals. Escalation events using baseline-relative thresholds.

**Cannot:** Whether specific interventions changed resident experience. Public sentiment at block level or in real time. Causal links between operations and neighborhood sentiment.

Phase 1 addresses all "cannot" items through direct sentiment collection.

---

## Deployment

```bash
cp psp_dashboard_v26.html index.html
git add index.html
git commit -m "PSP Dashboard v26"
git push origin main
# → live at https://mathewlarson.github.io/psp-dashboard
```

Repo must be **public** for GitHub Pages free tier.

---

## Version History

| Version | Date | Summary |
|---------|------|---------|
| v26 | Mar 2026 | Time Lapse 2016–2026; per-layer colored dots on vision map buttons; 4-point clean polygon; border-color urgency system; district label rendering fixed |
| v25 | Mar 2026 | Two-tier dark timeline bar; VBLOCKS rebuilt with correct SF coordinates; uniform radius + urgency-border design; block detail panel with driver + recommended actions |
| v24 | Mar 2026 | Time Lapse back inside map-body (absolute bottom); gray mask removed; polygon tightened; label repositioned |
| v23 | Mar 2026 | Drawer top-layer z-index; full-width mobile drawer; pilot zone label redesigned |
| v22 | Mar 2026 | Legend bottom-left; score box bottom-right; Time Lapse as compact pill button |
| v21 | Mar 2026 | Two-row toolbar; functional time windows (TW_DELTA); nav z-index fix |
| v20 | Mar 2026 | Static SVG product mockup; partners blurb removed |
| v19 | Mar 2026 | Sticky header removed; early warning → proactive detection frame |
| v18 | Mar 2026 | 18-block vision map; pilot zone polygon; escalation two-column cards |
| v14–v17 | Mar 2026 | Navigation fixes; full copy overhaul; map viewport; toolbar |

---

## Known Limitations

- Public sentiment is a proxy from the biennial SF Controller's City Survey (11 supervisor districts, not 41 neighborhoods)
- Foot traffic uses SFMTA ridership/parking proxies — not direct pedestrian counts
- Economic Vitality lags real conditions by 1–3 months
- TW_DELTA time-window adjustments are directional, not recomputed from raw data
- All Vision Map block data is illustrative

---

## Contact

**Mathew Larson** — City Science Lab San Francisco × MIT Media Lab City Science

City Science Lab SF: https://citysciencelab.org
MIT Media Lab City Science: https://www.media.mit.edu/groups/city-science/overview/
