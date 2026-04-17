# Marblehead levy paths from an FY2027 baseline

GitHub Pages-ready publication package for a standalone explainer showing how Marblehead's total property tax levy changes over time from an FY2027 baseline under each override outcome.

## Repository name

`levy-capacity-matrix-2026`

## Description

Standalone static page showing Marblehead's levy paths from an FY2027 base under eight scenarios:

- No overrides
- Trash only
- Tier 1 only
- Tier 1 + Trash
- Tier 2 only
- Tier 2 + Trash
- Tier 3 only
- Tier 3 + Trash

The table shows the FY27 base, Year 1, Year 2, Year 3, Year 10, Year 20, and Year 30.

## Why this exists

This page is meant to help readers see that the override debate is not only about a one-year bill increase. It is also about how much permanent levy capacity is created and how that capacity grows over time under Proposition 2½.

The page starts with an FY2027 base levy and then layers in the override draws using the town's three-year phase-in structure. The service override has three tiers:

- Tier 1 — Partial Restore — $9 million
- Tier 2 — Build — $12 million
- Tier 3 — Invest — $15 million

The trash path uses the FY27 curbside amount shown in the no-override budget and then adds the two smaller follow-on draws shown in town materials.

This widget is designed to complement a separate homeowner-impact explainer. Used together, the two pages help readers distinguish between household tax effects and townwide levy growth.

## What this repo contains

- `index.html` - the published page
- `.nojekyll` - tells GitHub Pages to serve the site as plain static files
- `README.md` - project notes and publishing instructions

## What the page shows

The page compares levy paths for every ballot outcome from the same FY2027 starting point.

- Year 1 shows the FY2027 base plus the first override draw only.
- Year 2 carries the base and prior draw forward at 2.5% and then adds the second draw.
- Year 3 does the same and then adds the third draw.
- Year 10, Year 20, and Year 30 show how those paths keep growing over time.

If residents do not approve the trash and recycling override, they would continue paying the separate trash and recycling fee.

## Math used in the table

Let:

- `L` = FY2027 base levy
- `d1` = first-year draw
- `d2` = second-year draw
- `d3` = third-year draw

Then:

- `Year 1 = L + d1`
- `Year 2 = (L × 1.025) + (d1 × 1.025) + d2`
- `Year 3 = (L × 1.025^2) + (d1 × 1.025^2) + (d2 × 1.025) + d3`

For later years, the same logic continues: the base and all prior draws remain in the levy path and keep growing by 2.5% a year.

### Draws used

Service tiers:

- Tier 1: `1.3M`, `5.3M`, `2.4M`
- Tier 2: `2.8M`, `6.7M`, `2.5M`
- Tier 3: `4.3M`, `7.1M`, `3.6M`

Trash:

- `2,186,516`
- `54,662.90`
- `57,396.05`

## Audience

- Marblehead voters
- Local reporters and editors
- Civic groups explaining budget choices
- Readers who want to compare short-term and long-term effects

## Features

- Fully static HTML with no build step
- Mobile-friendly responsive table
- FY2027 baseline framing
- Year 1, Year 2, and Year 3 phase-in view
- Long-range comparison through Year 30
- GitHub Pages compatible from the repository root

## Publishing on GitHub Pages

1. Create a GitHub repository using the suggested name above.
2. Upload the files in this folder.
3. Open the repository on GitHub.
4. Go to `Settings` > `Pages`.
5. Under `Build and deployment`, choose `Deploy from a branch`.
6. Select your main branch and the `/ (root)` folder.
7. Save and wait for the Pages deployment to finish.

Your published site will then be available at:

`https://<your-github-username>.github.io/levy-capacity-matrix-2026/`

## Local preview

Open `index.html` directly in a browser.

## Editing content

For most updates, edit `index.html`.

## Content notes

- Figures are shown in millions of dollars unless otherwise noted.
- The table is a levy-path explainer, not a homeowner tax-bill calculator.
- The page uses the town's three-year phase-in structure for the service override and the trash path materials supplied for FY27 through FY29.
- The page is designed to accompany reporting on how override choices change permanent taxing authority over time.

## Suggested topics/tags

- `github-pages`
- `static-site`
- `civics`
- `municipal-finance`
- `property-tax`
- `proposition-2-5`
- `massachusetts`
- `marblehead`

## License

Choose the license that matches how you want others to reuse the material. If you want broad reuse with attribution, `CC BY 4.0` is a strong fit for this type of public-interest publication.
