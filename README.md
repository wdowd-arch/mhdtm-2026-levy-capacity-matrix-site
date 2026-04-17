# Eight Ways the Vote Could Go

GitHub Pages-ready publication package for an interactive explainer covering the tax, levy, and service implications of every Marblehead override scenario.

## Repository name

`marblehead-override-matrix-2026`

## Description

Interactive GitHub Pages explainer showing eight possible Marblehead override outcomes, including:

- property-tax impact on the median homeowner
- added levy capacity created by each override path
- services restored, added, or left cut

## Why this exists

Marblehead voters face two separate override questions: a three-tier service override and a standalone trash override. Because the questions are independent, there are eight possible outcomes.

This page is built to help readers compare those outcomes clearly.

For the homeowner view, the page uses the median-home example from the town presentation **“Town of Marblehead | FY2027 Override”**: a single-family home assessed at **$998,600** with a current tax bill of about **$8,548** at a residential rate of **$8.56 per $1,000**.

For the service side, the page uses the town presentation's phased median-home figures for Tier 1, Tier 2, and Tier 3. For the trash side, it uses the FY27 curbside amount shown in the no-override budget materials and the two smaller follow-on draws shown in the town's trash worksheet.

## What this repo contains

- `index.html` - the main interactive publication page
- `README.md` - project notes and publishing instructions
- `.nojekyll` - tells GitHub Pages to serve the site as plain static files

## How the numbers are sourced

This page keeps the town's public-facing service figures and the trash worksheet figures separate.

### Median-home property-tax figures

The homeowner figures are built from the town presentation **“Town of Marblehead | FY2027 Override.”**

For the median home, that presentation gives these phased cumulative increases:

- Tier 1: `129.82`, `662.32`, `918.54`
- Tier 2: `279.61`, `955.66`, `1,229.20`
- Tier 3: `429.40`, `1,149.14`, `1,537.36`

The trash path adds these cumulative property-tax amounts to the same median-home baseline:

- Trash: `218.35`, `229.27`, `240.73`

Combined rows add the service and trash cumulative increases together.

### Levy-capacity figures

The levy tab shows the added override authority created by each scenario, not the town's full levy.

Year 1 shows the first draw only.

Year 3 reflects the phased-in path after earlier draws are carried forward at 2.5% growth.

The service-side draw paths used are:

- Tier 1: `1.3M`, `5.3M`, `2.4M`
- Tier 2: `2.8M`, `6.7M`, `2.5M`
- Tier 3: `4.3M`, `7.1M`, `3.6M`

The trash draw path used is:

- `2.186516M`, `0.0546629M`, `0.05739605M`

## What the interactive page includes

The page opens with a short explainer and then presents eight expandable scenario cards:

- Tier 3 + Trash
- Tier 3 only
- Tier 2 + Trash
- Tier 2 only
- Tier 1 + Trash
- Tier 1 only
- Trash only
- No overrides

Inside each card are three tabs:

### 1. Tax impact

Shows the year-by-year property-tax increase for the median home in:

- Year 1
- Year 2
- Year 3

It also notes when the separate household trash fee remains.

### 2. Levy capacity

Shows the added levy authority for:

- Year 1
- Year 3
- Year 5
- Year 10

This tab is intended to show how override authority grows over time under Proposition 2½.

### 3. Services

Lists what is restored, added, or funded under a scenario, and what remains cut or unaddressed.

## Math used in the code

### Base bill

- Home value = `998,600`
- Tax rate = `8.56` per `$1,000`

So:

- `998,600 × 8.56 / 1,000 = 8,548.016`
- Displayed as `$8,548`

### Median-home tax rows

Examples:

- Tier 1 Year 3 = `8,548.016 + 918.54 = 9,466.556`
- Tier 2 Year 3 = `8,548.016 + 1,229.20 = 9,777.216`
- Tier 3 Year 3 = `8,548.016 + 1,537.36 = 10,085.376`
- Tier 3 + Trash Year 3 = `8,548.016 + 1,537.36 + 240.73 = 10,326.106`

### Levy-capacity rows

For each scenario, Year 1 is the first draw only.

Year 3 is:

- `draw1 × 1.025^2 + draw2 × 1.025 + draw3`

Year 5 is:

- `Year 3 × 1.025^2`

Year 10 is:

- `Year 3 × 1.025^7`

Example for Tier 1 only:

- Year 1 = `1.3M`
- Year 3 = `1.3 × 1.025^2 + 5.3 × 1.025 + 2.4 ≈ 9.2M`
- Year 5 ≈ `9.7M`
- Year 10 ≈ `10.9M`

Example for Tier 3 + Trash:

- Year 1 = `4.3 + 2.186516 ≈ 6.5M`
- Year 3 ≈ `17.8M`
- Year 5 ≈ `18.7M`
- Year 10 ≈ `21.2M`

## Features

- Expand/collapse scenario cards
- Tax impact view for the median homeowner
- Levy-capacity view showing added override authority over time
- Service breakdowns listing what is restored, added, or left cut
- Mobile-friendly static deployment with no build pipeline

## Technical notes

This page is a single self-contained HTML document that loads React and Babel from CDNs.

That makes it easy to publish on GitHub Pages without a build step, but it also means the page depends on those external CDN assets at runtime.

## Publishing on GitHub Pages

1. Create a GitHub repository using the suggested name above.
2. Upload the files in this folder.
3. Open the repository on GitHub.
4. Go to `Settings` > `Pages`.
5. Under `Build and deployment`, choose `Deploy from a branch`.
6. Select your main branch and the `/ (root)` folder.
7. Save and wait for deployment.

Your published site will then be available at:

`https://<your-github-username>.github.io/marblehead-override-matrix-2026/`

## Local preview

Open `index.html` in a browser.

Because the page uses CDN-hosted scripts, an internet connection is required unless you replace those dependencies with local files.

## Editing content

All scenario data and copy live inside `index.html`.

Typical edits include:

- adjusting scenario labels
- updating tax or levy figures
- revising service lists
- changing explanatory notes for clarity

## Content notes

- This page distinguishes between the median-home property-tax path and the separate household trash fee.
- The levy tab shows added override authority, not the town's full levy.
- The page is written for readers and attributes its key numbers to the town presentation and related town budget materials.

## Suggested topics/tags

- `github-pages`
- `react`
- `civic-tech`
- `budget`
- `override`
- `property-tax`
- `massachusetts`
- `marblehead`

## License

Choose the license that fits your publishing goals. For public-interest explanatory content, `CC BY 4.0` is often a good default if you want sharing with attribution.
