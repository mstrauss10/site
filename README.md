# Trend Engine — Static Dashboard

Institutional-grade continuous trend engine dashboard. Fully static build — no server required.

**Live demo** · [GitHub Pages](https://YOUR_USERNAME.github.io/YOUR_REPO/)

---

## What's inside

| File / Folder | Description |
|---|---|
| `index.html` | Single-page dashboard (all 4 tabs) |
| `data/` | 96 pre-computed JSON snapshots |
| `.nojekyll` | Tells GitHub Pages to skip Jekyll processing |

## Tabs

- **📊 Dashboard** — Universe snapshot, trade blotter, signal time-series charts, heatmap, exposure validation
- **🏛 Research** — Macro regime cards, history chart, signal decile analysis, cross-bin interaction matrix
- **⚡ Strategy Signals** — 8-strategy signal matrix + individual signal history
- **🔗 Correlations** — Cross-signal Spearman correlation matrix

## Deploying to GitHub Pages

```bash
# 1. Create a new GitHub repo (e.g. trend-engine-demo)
# 2. Push only the static_version/ contents to the repo root:

git init
git add .
git commit -m "Initial static dashboard"
git remote add origin https://github.com/YOUR_USERNAME/trend-engine-demo.git
git push -u origin main

# 3. In GitHub repo settings → Pages → Source: Deploy from branch → main / (root)
# 4. Visit https://YOUR_USERNAME.github.io/trend-engine-demo/
```

> **Note:** All data was pre-computed using live market signals (SPY, QQQ, GLD, TLT) via Yahoo Finance.
> The "Refresh" button re-renders from the cached data — it does not pull new market data.

## Data coverage

| Ticker | Bars | Start |
|---|---|---|
| SPY | ~178 monthly | Jan 2010 |
| QQQ | ~178 monthly | Jan 2010 |
| GLD | ~178 monthly | Jan 2010 |
| TLT | ~178 monthly | Jan 2010 |

## Regenerating the data

Run from the project root (requires Python + `.venv`):

```bash
python generate_static_data.py   # generates data/*.json
python build_static_html.py      # rebuilds index.html from static/index.html
```
