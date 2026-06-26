# Random Team Picker 🎲

A single-page web app to split people into balanced teams in a fair and fun way.

## Features

- 📥 Import members from **Excel (.xlsx / .xls)**, paste **CSV**, or add manually
- 🎯 Balanced random picking with a roulette animation
- ⚖️ Auto-assign remaining members evenly across teams
- 📤 Export results to CSV / text
- 📄 Built-in Excel template download
- 💾 Auto-saves to the browser (localStorage)

## Live demo

Published with GitHub Pages: https://quanghuy18082000.github.io/randomHD/

## Run locally

Just open `index.html` in any modern browser — no build step needed.

## Import format

The first row must be the **header row**. These columns are recognized
(case-insensitive); any other column is ignored:

| Column   | Required | Meaning                                                       |
|----------|----------|---------------------------------------------------------------|
| `Name`   | ✅ Yes   | Person's name                                                 |
| `Gender` | optional | Used for balancing — `Male` / `Female`. `Sex` also works      |
| `Type`   | optional | Balancing group — `A` / `B` / `C` / `D`                       |
| `Role`   | optional | Set `Captain` to make this person a team leader (see below)   |

Example CSV:

```csv
Name,Gender,Type,Role
Alex,Male,,Captain
Chris,Male,A
Pat,Female,C
```

## Captains (team leaders)

People whose `Role` is `Captain` are **not** put into the random pool. Instead,
their names fill the **leaders of the 4 teams** in the order they appear
(1st captain → Team 1, 2nd → Team 2, and so on). If no captains are imported,
the default leaders in `CONFIG` are used.

## How balancing works

When you pick (or auto-assign), the app keeps teams fair by balancing in this
priority order:

1. **Gender first** — it evens out gender across all teams (Male, then Female).
2. **Type second** — once gender is balanced, it evens out the `Type` value
   (A → B → C → D).

Among the candidates that are equally good for balance, one is chosen at random,
so it still feels like a draw while staying fair.

## Configuration

Team names, leaders, and colors live in the `CONFIG` object at the top of the
`<script>` block in `index.html` — edit them there to customize.
