# Copper Observatory

A buildless HTML/CSS/JavaScript dashboard for six China-focused copper market indicators.

- `dist/index.html`: dashboard structure
- `dist/styles.css`: responsive frosted-glass theme
- `dist/app.js`: chart rendering, source panels, production selector, and CSV export
- `dist/data.json`: sourced observations and provenance, verified on 2026-11-25

The dashboard is a research snapshot, not an automatically updating or licensed live data feed. Original currencies and reporting bases are preserved. SMM and NBS production series are separate. Argus RC and the prior SHFE inventory observation are explicitly calculated. Daily and published weekly Yangshan warrant assessments are separate views.

Each observation references a source key with an external URL. Updates should retain observation dates, publication dates where available, units, and calculation labels. Do not fill missing history with synthetic values or splice different providers into one series.

To preview locally, serve `dist/` over HTTP. No build step or runtime dependencies are required.

Regime watch adds a sourced research thesis on negative processing fees, by-product offsets, business exposures and six indicator interpretations. `dist/regime.js` renders the accessible analysis tabs. Company case data and source references live in `data.json` under `regime`; company cash-cost components are not full profitability estimates. CSV export includes the company case observations.

## Deploy on Vercel

Import this repository with the repository root as the Root Directory. The committed `vercel.json` selects the Other framework preset, skips install/build commands, and serves `dist/`. No environment variables or dependencies are required. An already connected project redeploys when `main` changes.

If project settings were previously overridden, leave Root Directory empty (the repository root); the site entry point is `dist/index.html`. Do not set the Root Directory to `dist` while also using `outputDirectory: dist`.

The phone layout includes accessible navigation, larger controls, a chart sized to its container, and stacked indicator interpretations.
