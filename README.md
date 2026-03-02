# Cerulean Labs — Space Debris Risk Tracker

Interactive 3D visualization of 12,000+ tracked in-orbit space debris objects with a configurable risk scoring methodology.

## Live Demo

Open `index.html` in any modern browser, or deploy to GitHub Pages.

## Features

- **3D Globe** — All tracked in-orbit debris plotted on an interactive globe. Color-coded by risk level, sized by radar cross-section. Click any object for full details.
- **Risk Scoring Engine** — 4-factor composite score (Altitude, Size, Inclination, Longevity) producing CRITICAL / HIGH / MODERATE / LOW ratings. Fully configurable via the Risk Config panel.
- **Dashboard** — Altitude density histogram, country breakdown chart, risk overview cards, and key statistics.
- **Filters** — Filter by risk level, country, altitude range, and debris size.
- **Data Refresh** — Upload a newer SATCAT CSV from Space-Track.org to update the visualization in real time.

## Risk Scoring Methodology

| Factor | Range | Scoring |
|--------|-------|---------|
| **Altitude** | 0-3 | Perigee 600-1000km = 3, 400-600 or 1000-1500km = 2, other = 1 |
| **Size** | 0-3 | LARGE = 3, MEDIUM = 2, SMALL = 1 |
| **Inclination** | 0-2 | Sun-synchronous (95-105 deg) = 2, Polar (60-85 deg) = 1, other = 0 |
| **Longevity** | 0-2 | Perigee >= 800km = 2, >= 600km = 1, other = 0 |

**Total (0-10):** CRITICAL (8+), HIGH (6-7), MODERATE (4-5), LOW (1-3)

## Updating Data

1. Log in to [Space-Track.org](https://www.space-track.org)
2. Use Query Builder: Class = `satcat`, Predicate = `OBJECT_TYPE`, Value = `DEBRIS`, Format = `CSV`
3. Download the CSV file
4. In the app, click **Update Data** and select the CSV file
5. The globe and all charts will refresh automatically

## Deploying to GitHub Pages

1. Fork or clone this repository
2. Go to repo Settings > Pages
3. Set source to `Deploy from a branch`, select `main` / `root`
4. Your site will be live at `https://<username>.github.io/cerulean-debris-tracker/`

## Tech Stack

- [Globe.gl](https://globe.gl/) — 3D globe visualization (Three.js)
- [Chart.js](https://www.chartjs.org/) — Dashboard charts
- [Space-Track.org](https://www.space-track.org/) — SATCAT debris catalog (18th Space Defense Squadron)

## About Cerulean Labs

Cerulean Labs is developing next-generation space debris monitoring solutions, combining publicly available tracking data with proprietary ion-propulsion orbital sensors. Future integration with Dawn Aerospace HTHL platform for enhanced coverage.

---

Built by Cerulean Labs. Data sourced from the US Space Surveillance Network via Space-Track.org.
