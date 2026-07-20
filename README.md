PropIQ — Real Estate Investment Analyzer

PropIQ is a browser-based real estate investment underwriting tool that scores a single-family property across four investment strategies using a deterministic, rule-based formula, so a buyer can quickly compare a deal's fit for owner-occupied house-hacking versus pure rental or flip strategies.

Live Demo  ·  Single self-contained HTML file — no build step, no installation


What it does

Investment strategies scored

PropIQ scores a property across four strategies and blends them into a single composite score:


House Hack — 40% weight
Buy & Hold — 25% weight
BRRRR — 20% weight
Flip — 15% weight


House Hack carries the highest weight because FHA 3.5%-down financing requires owner-occupancy, making it the most accessible entry strategy for most users.

Scoring methodology

Scoring is fully deterministic — every score is computed from fixed rule-based point bands (e.g., monthly cash flow > $300 → 25 points, ≥ $150 → 20 points, ≥ $0 → 15 points, and so on). There is no randomness and no model-dependent variance in the core score: identical inputs always produce identical outputs, making results auditable and reproducible.

The final Composite Score blends the strategy-weighted score with a separate Property score (value/comp confidence, income potential, neighborhood, condition, and market factors), then averages the two.

Financial calculations


PITI (principal, interest, taxes, insurance)
MIP (FHA mortgage insurance premium)
Monthly cash flow
Cap rate
Cash-on-cash return
NOI (net operating income)


Inputs

Address, purchase price, bedrooms, bathrooms, square footage, year built, property tax, insurance, monthly rent, annual appreciation %, vacancy %, condition score, ARV (after-repair value), rehab budget, days-on-market, and reserve amount.

Outputs

A 0–100 composite score with letter-grade framing, an animated visual score gauge, per-strategy score breakdowns, a transparent formula display, and Chart.js-rendered charts.

Interactive features

All inputs recalculate the score and every downstream metric in real time, enabling live sensitivity analysis — for example, watching how the composite score and cash flow respond as purchase price or rehab budget change.


Optional AI-assisted research

PropIQ includes an optional feature that calls the Anthropic API directly from the browser to research a property address and web-search for comps, then auto-populate the input fields and a full comps table.


Uses the user's own Anthropic API key, entered client-side and stored only in that browser's local storage — never sent to or stored on any server PropIQ controls
Constructs a structured prompt, calls Claude with web search tool access, parses the structured JSON response, and auto-fills roughly 14 form fields
Fully optional — the core scoring engine and all financial calculations work identically with manual input if this feature isn't used or fails (e.g., due to browser CORS restrictions)



Tech stack


Vanilla JavaScript — no frontend framework (not React, not Vue)
Chart.js v4.4.1 — loaded via CDN, the only external library
No backend — single self-contained HTML file; runs entirely in the browser with no server, database, or build step
Optional client-side integration with the Anthropic API for AI-assisted property research (see above)


Run it

Open index.html in any browser. No installation, no dependencies to install, no configuration required for core functionality.


Built as a personal project under DeLuca Capital LLC.
