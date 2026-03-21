<div align="center">

# MolarPrep

### Stock solution and molarity preparation for laboratory workflows

<a href="https://ebalderasr.github.io/MolarPrep/">
  <img src="icon-512.png" alt="MolarPrep" width="120">
</a>

<br>

**[→ Open the live app](https://ebalderasr.github.io/MolarPrep/)**

<br>

[![Stack](https://img.shields.io/badge/Stack-HTML_·_CSS_·_JavaScript-4A90D9?style=for-the-badge)]()
[![Focus](https://img.shields.io/badge/Focus-Solution_Prep_·_Lab_Workflows-34C759?style=for-the-badge)]()
[![License](https://img.shields.io/badge/License-MIT-blue?style=for-the-badge)](./LICENSE)
[![Part of](https://img.shields.io/badge/Part_of-Host_Cell_Lab_Suite-5856D6?style=for-the-badge)](https://github.com/ebalderasr)

</div>

---

## What is MolarPrep?

MolarPrep is a **browser-based solution preparation calculator** that covers the two most common reagent setup scenarios in a laboratory: weighing a dry solid to a target molarity, and pipetting the right volume from a liquid stock defined by density and purity.

Both modules handle unit scaling automatically and validate inputs before computing, so the result is always expressed in a practical unit without manual prefix conversion.

No installation. No server. Runs entirely in the browser.

---

## Why it matters

Preparing stock solutions involves multi-step unit conversions that are a frequent source of errors — especially under time pressure or when working across concentration scales (M, mM, µM, nM). Without a dedicated tool:

- Mass calculations require manually converting target molarity and volume into consistent units before applying m = M × V × MW
- Liquid reagent preparation involves a two-step calculation (density + purity → stock molarity, then C₁V₁ = C₂V₂) that is commonly collapsed or done incorrectly
- The appropriate output unit (g, mg, µg / L, mL, µL) must be chosen by the user, introducing another judgment call

MolarPrep handles all conversions internally and selects the output prefix automatically based on scale.

---

## How it works

### Module 1 — Solid reagent (mass to weigh)

Enter the target molarity, final volume, and molecular weight. MolarPrep returns the mass to weigh out.

**Formula**

$$m \ (\text{g}) = M \left(\frac{\text{mol}}{\text{L}}\right) \times V \ (\text{L}) \times MW \left(\frac{\text{g}}{\text{mol}}\right)$$

Supported molarity units: M, mM, µM, nM. Supported volume units: L, mL. Output is auto-scaled to g, mg, or µg depending on magnitude.

### Module 2 — Liquid reagent (concentrated stock volume)

Use this when the reagent is a liquid sold by density and purity (e.g. acids, organic solvents). Enter density, purity, molecular weight, target molarity, and final volume.

**Step A — Estimate stock molarity from density and purity**

$$M_1 = \frac{P \times \rho \times 1000}{MW}$$

where P = purity fraction (e.g. 0.98), ρ = density in g/mL, MW = molecular weight in g/mol.

**Step B — Apply dilution equation**

$$V_1 = \frac{M_2 \times V_2}{M_1}$$

Output is auto-scaled to L, mL, or µL.

### Output validation

Non-positive or missing values return `ERR`. All outputs are checked for physical consistency before display.

---

## Features

| | |
|---|---|
| **Solid reagent module** | Computes mass to weigh from molarity, volume, and MW |
| **Liquid reagent module** | Estimates stock molarity from density and purity, then solves C₁V₁ = C₂V₂ |
| **Auto unit scaling** | Output switches between g/mg/µg and L/mL/µL based on magnitude |
| **Input validation** | Non-positive or missing values return ERR before computing |
| **Offline-first PWA** | Service Worker caches all assets; works without internet after first load |
| **Bilingual UI** | Full Spanish / English interface |
| **No installation** | Opens instantly in any modern browser; installable on Android, iOS, and desktop |

---

## Tech stack

**Frontend**

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat-square&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)

**Deployment**

![GitHub Pages](https://img.shields.io/badge/GitHub_Pages-222222?style=flat-square&logo=github&logoColor=white)
![PWA](https://img.shields.io/badge/PWA-5A0FC8?style=flat-square&logo=pwa&logoColor=white)

Fully static — no backend, no framework, no build step.

---

## Project structure

```
MolarPrep/
├── index.html              ← markup only
├── manifest.json           ← PWA manifest
├── sw.js                   ← Service Worker (cache-first, offline support)
├── icon-192.png
├── icon-512.png
├── icon-maskable-192.png
├── icon-maskable-512.png
└── og-image.png            ← Open Graph social preview
```

---

## Author

**Emiliano Balderas Ramírez**
Bioengineer · PhD Candidate in Biochemical Sciences
Instituto de Biotecnología (IBt), UNAM

[![LinkedIn](https://img.shields.io/badge/LinkedIn-emilianobalderas-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/emilianobalderas/)
[![Email](https://img.shields.io/badge/Email-ebalderas%40live.com.mx-D14836?style=flat-square&logo=gmail&logoColor=white)](mailto:ebalderas@live.com.mx)

---

## Related

[**DiluteIt**](https://github.com/ebalderasr/DiluteIt) — universal dilution solver (C₁V₁ = C₂V₂) for any of the four variables.

[**CellSplit**](https://github.com/ebalderasr/CellSplit) — Neubauer cell counting and passage planning for CHO cultures.

[**PulseGrowth**](https://github.com/ebalderasr/PulseGrowth) — growth kinetics and metabolic rate estimation for mammalian cell culture.

[**CellBlock**](https://github.com/ebalderasr/CellBlock) — shared biosafety cabinet scheduling for cell culture research groups.

---

<div align="center"><i>MolarPrep — enter your target, get your mass or volume.</i></div>
