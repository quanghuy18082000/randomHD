# Random Team Picker 🎲

A single-page web app to split people into balanced teams in a fair and fun way.

- Import members from **Excel (.xlsx)** or **CSV**, or add them manually
- Balanced random picking with a roulette animation
- Auto-assign remaining members evenly
- Export results to CSV / text
- Built-in Excel template download

## Live demo

Published with GitHub Pages: https://quanghuy18082000.github.io/randomHD/

## Run locally

Just open `index.html` in any modern browser — no build step needed.

### Excel import format

First row must be headers. Recognized columns:

| Column | Meaning |
|--------|---------|
| `Name` | Person name (required) |
| `Gender` | Used for balancing (Female / Male) |
| Any other column | Treated as a balancing "Type" (Department, Seniority, Level…) |
