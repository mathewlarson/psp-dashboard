# Public Safety Pulse

**City Science Lab San Francisco × MIT Media Lab City Science**

> Phase 0 · Pre-publication · Working Instrument

Measure the feeling. Improve the response.

San Francisco invests heavily in public safety — but there has never been a reliable, high-frequency way to know whether residents and visitors actually feel the difference. Public Safety Pulse is being built to change that.

👉 **[View the dashboard](https://mathewlarson.github.io/psp-dashboard)**

---

## What This Is

Phase 0 of Public Safety Pulse — a working instrument that demonstrates the problem, establishes the baseline, and makes the case for Phase 1 direct sentiment measurement.

The dashboard integrates 28.6 million public records across five data layers covering 41 San Francisco neighborhoods from 2003 to 2026. It surfaces four validated findings about the current state of SF's public safety data — and shows exactly where the existing data runs out.

**Not for public release or citation without authorization from City Science Lab San Francisco.**

---

## What the Dashboard Contains

| Tab | What's there |
|-----|-------------|
| **The Vision** | Phase 1 product roadmap, data-to-impact pipeline, interactive Mid-Market prototype |
| **What the Data Shows** | Five-layer data overview, structural break finding, escalation patterns |
| **Perception & the Gap** | 20-year sentiment trend, district breakdown, measurement gap analysis, government responsiveness finding |
| **Interventions** | Directional evidence on CBD and city interventions, early warning patterns |
| **Explore the Data** | Interactive map of 41 neighborhoods with time-lapse from 2003 |
| **Partners** | City Science Lab SF × MIT Media Lab City Science |
| **Data & Methods** | Full methodology, data sources, validation status |

---

## Key Findings (Phase 0)

All findings are either verified against source data or explicitly labeled directional on the dashboard.

1. **Structural break (2019)** — Panel fixed effects model (R²=0.824, 121 observations, 1996–2023) shows conditions reliably predicted safety perception for 15 years, then decoupled post-2019. Prediction error increased 4.7× (RMSE 0.13 → 0.61).

2. **118 escalation events detected** — Identified via rate-ratio methodology (≥1.3×, 2+ weeks, 2+ signal types) across 41 neighborhoods. Two distinct neighborhood types: chronically elevated vs. disruptive spike.

3. **Government responsiveness is now the leading predictor of felt safety** — Stronger than crime rates, stronger than cleanliness scores. Replacing the pre-2019 conditions-based model.

4. **Perception data gap** — City Survey 3.63/5.0 citywide in 2023 (historic low). CityBeat 2026: 83% of SF likely voters feel safe downtown during the day (up from 64% in 2023). Neither source provides the neighborhood-level, monthly signal needed for operational decisions.

---

## Data Sources

All data publicly available via DataSF, SFMTA, US Census Bureau, and open APIs. No proprietary data.

- SFPD Incident Reports (2003–2026)
- SF 311 Service Requests (2008–2026)
- SF Controller's Office City Survey (1996–2023)
- SFMTA Ridership Data
- SF Business Registrations & Permits
- CityBeat Poll 2026 (EMC Research / United Airlines)

Full methodology in the Data & Methods tab of the dashboard.

---

## Partners

**City Science Lab San Francisco** — Fiscally sponsored by SPUR. Focused on AI and systems modeling for civic innovation.

**MIT Media Lab City Science** — CityScope platform, Place Pulse dataset (1.17M pairwise comparisons), 28-lab global City Science Network.

---

## Contact

Mathew Larson — City Science Lab San Francisco  
GitHub: [@mathewlarson](https://github.com/mathewlarson)
