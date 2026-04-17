# Marblehead Median Home Tax Bill Impact

GitHub Pages-ready publication package for a standalone matrix showing what each override scenario would mean for the median single-family homeowner's property-tax bill.

## Repository name

`levy-matrix-2026`

## Description

Standalone GitHub Pages site showing the median Marblehead single-family home's property-tax bill under every override scenario.

The table shows:

- Today
- Year 1
- Year 2
- Year 3
- Year 5
- Year 10

It uses Georgia typography and a single Van Gogh-inspired color scale across the table.

## Why this exists

This page is built to help readers understand what Marblehead's override vote would mean for the middle single-family homeowner.

The town's presentation titled **“Town of Marblehead | FY2027 Override”** presents the median homeowner as a single-family home assessed at **$998,600** with a current tax bill of about **$8,548** at a residential tax rate of **$8.56 per $1,000**. This page uses that median-home example as its starting point.

The same town presentation shows the service override as a three-year phase-in with three tiers:

- Tier 1 — Partial Restore — $9 million
- Tier 2 — Build — $12 million
- Tier 3 — Invest — $15 million

The trash override is treated separately. For that piece, this page uses the FY27 curbside amount shown in the town's no-override budget materials and the two smaller follow-on draws shown in the town's trash worksheet.

Because the service and trash questions are separate, the page compares all eight outcomes:

- No overrides
- Trash only
- Tier 1 only
- Tier 1 + Trash
- Tier 2 only
- Tier 2 + Trash
- Tier 3 only
- Tier 3 + Trash

This page shows the **property-tax bill path only**. If the trash and recycling override passes, the separate household fee would go away. If it does not pass, that fee stays.

## What this repo contains

- `index.html` - the standalone published page
- `README.md` - project notes and publishing instructions
- `.nojekyll` - tells GitHub Pages to serve the site as plain static files

## What the current HTML includes

The current `index.html` includes:

- the headline **“What the override vote means for the median Marblehead tax bill”**
- a short lede stating that the table uses the town's median homeowner example
- a subhed stating that trash rows show the property-tax bill only and that the separate fee goes away only if the trash and recycling override passes
- a single-scale legend labeled **“Lower to higher property-tax bills on a single scale”**
- scenario rows for all eight outcomes
- a callout stating that the service-side cumulative increases match the town presentation
- a method box titled **“How each number is built”**
- a footnote that attributes the median-home value and service-side numbers to the town's FY2027 override presentation and the trash path to the FY27 curbside amount plus the town worksheet

## How the numbers are sourced

This page intentionally keeps two town-source streams separate.

### 1. Service tiers

The service-side homeowner figures come from the town presentation **“Town of Marblehead | FY2027 Override.”**

For the median homeowner, that presentation gives these phased household increases:

- Tier 1: `129.82`, `662.32`, `918.54`
- Tier 2: `279.61`, `955.66`, `1,229.20`
- Tier 3: `429.40`, `1,149.14`, `1,537.36`

These are used as the cumulative Year 1, Year 2, and Year 3 additions in the table.

### 2. Trash

The trash-side figures come from the town's FY27 no-override budget materials plus the trash worksheet path.

The table uses these cumulative property-tax additions for the median home:

- Trash: `218.35`, `229.27`, `240.73`

Those figures are based on the FY27 curbside amount and the two follow-on draws shown in the town worksheet.

## Math used in the code

### Base bill

The table starts with the town's median-home example:

- Home value = `998,600`
- Tax rate = `8.56` per `$1,000`

So:

- `998,600 × 8.56 / 1,000 = 8,548.016`
- Displayed as `$8,548`

### Service-only rows

These use the town presentation's median-home cumulative phase-in figures.

Examples:

- Tier 1 Year 1 = `8,548.016 + 129.82 = 8,677.836`
- Tier 1 Year 2 = `8,548.016 + 662.32 = 9,210.336`
- Tier 1 Year 3 = `8,548.016 + 918.54 = 9,466.556`

The same structure is used for Tier 2 and Tier 3.

### Trash-only row

Trash starts from the town's FY27 curbside amount and the two smaller follow-on draws in the town worksheet, converted into the median home's property-tax bill path.

So:

- Trash Year 1 = `8,548.016 + 218.35 = 8,766.366`
- Trash Year 2 = `8,548.016 + 229.27 = 8,777.286`
- Trash Year 3 = `8,548.016 + 240.73 = 8,788.746`

### Combined rows

Combined rows add the service and trash cumulative additions together, then add that sum to the base bill.

Examples:

- Tier 1 + Trash Year 3 addition = `918.54 + 240.73 = 1,159.27`
- Tier 1 + Trash Year 3 bill = `8,548.016 + 1,159.27 = 9,707.286`
- Displayed as `$9,707`

- Tier 3 + Trash Year 3 addition = `1,537.36 + 240.73 = 1,778.09`
- Tier 3 + Trash Year 3 bill = `8,548.016 + 1,778.09 = 10,326.106`
- Displayed as `$10,326`

### Year 5 and Year 10

For override rows, the code starts from each row's Year 3 total and then applies 2.5% annual growth:

- `Year 5 = Year 3 total × 1.025^2`
- `Year 10 = Year 3 total × 1.025^7`

### No-override row

The no-override row grows today's bill by 2.5% annually:

- Year 1 = `8,548.016 × 1.025 = 8,761.7164`
- Year 2 = `8,548.016 × 1.025^2 = 8,980.75931`
- Year 3 = `8,548.016 × 1.025^3 = 9,205.27829`
- Year 5 = `8,548.016 × 1.025^5 = 9,671.03513`
- Year 10 = `8,548.016 × 1.025^10 = 10,942.49223`

## Design notes

- Georgia is used throughout the page for consistency and readability.
- The table uses one consistent Van Gogh-inspired scale across all scenario cells.
- Darker cells correspond to higher property-tax bills on the same scale.
- Text color switches for contrast based on background intensity.

## Features

- Fully static HTML with no build step
- Mobile-friendly responsive layout
- Georgia typography
- Single consistent color scale across the table
- Side-by-side comparison of all eight scenarios
- Year 1, Year 2, and Year 3 phase-in view
- Later-year Year 5 and Year 10 view
- Callout box and method box for quick explanation
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

`https://<your-github-username>.github.io/levy-matrix-2026/`

## Local preview

Open `index.html` directly in a browser.

## Editing content

For most updates, edit `index.html`.

## Content notes

- This is a median-home property-tax bill explainer, not a full household net-cost calculator.
- Trash rows show the property-tax bill path and should be read alongside the note about the separate fee.
- The page is designed to support reporting that distinguishes between phased-in household effects and later growth from a higher property-tax base.
- The wording is written for readers and attributes the key figures to town materials rather than presenting them as independently generated numbers.

## Suggested topics/tags

- `github-pages`
- `static-site`
- `civics`
- `local-government`
- `property-tax`
- `massachusetts`
- `marblehead`

## License

Choose the license that matches how you want others to reuse the material. If you want broad reuse with attribution, `CC BY 4.0` is a strong fit for this type of public-interest publication.
