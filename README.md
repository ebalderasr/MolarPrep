# 🧪 MolarPrep

> **Fast, reliable molarity and stock-solution calculations for laboratory workflows.**  
> Part of **Host Cell**, a growing suite of bioprocess tools.

<p align="center">
  <img src="icon-512.png" width="180" alt="MolarPrep Logo">
</p>

<p align="center">
  <a href="https://ebalderasr.github.io/MolarPrep/">
    <img src="https://img.shields.io/badge/🚀_Launch_Live_App-MolarPrep-00e5ff?style=for-the-badge&labelColor=000000" alt="Launch MolarPrep App">
  </a>
</p>

<p align="center">
  <a href="https://github.com/ebalderasr/MolarPrep">Repo</a> •
  <a href="https://ebalderasr.github.io/MolarPrep/">Live App</a>
</p>

---

## What is MolarPrep?

**MolarPrep** is a lightweight web app for preparing solutions with fewer calculation mistakes, especially in repetitive or high-pressure lab work.

It helps you calculate:

1. **How much solid reagent to weigh** to prepare a target molar solution
2. **How much concentrated liquid stock to pipette** (using density and purity)

The app is designed to reduce common errors such as:
- decimal point shifts
- unit conversion mistakes
- confusion between **mM / µM / nM**
- stock concentration estimation from reagent density + purity

---

## Part of the Host Cell Suite

**MolarPrep** is part of **Host Cell**, a suite of practical tools for bioprocessing and lab workflows.

### Host Cell vision
A modular toolbox for:
- solution preparation
- bioprocess calculations
- experimental planning
- data organization
- fast operational decisions in the lab

This project focuses on **clarity, speed, and reproducibility**, with a minimal interface that works well on desktop and mobile.

---

## How it works

MolarPrep currently includes **two calculation modules**.

### 1) Solid reagents (mass to weigh)

Use this when you have a dry reagent and want to prepare a solution with a target molarity.

**Formula used:**

\[
m(g) = M\left(\frac{mol}{L}\right) \times V(L) \times MW\left(\frac{g}{mol}\right)
\]

Where:
- **m** = required mass in grams
- **M** = target molarity
- **V** = final volume
- **MW** = molecular weight

✅ Supports target molarity units:
- **M**
- **mM**
- **µM**
- **nM**

✅ Supports final volume units:
- **L**
- **mL**

---

### 2) Liquid reagents (concentrated stock volume)

Use this when your reagent is a liquid stock (for example acids/solvents/reagents sold by density and purity) and you need to prepare a target molar solution.

#### Step A: Estimate stock molarity from density and purity

\[
M_1 = \frac{P \times \rho \times 1000}{MW}
\]

Where:
- **P** = purity fraction (e.g., 98% → 0.98)
- **ρ** = density in g/mL
- **MW** = molecular weight in g/mol

#### Step B: Use dilution equation

\[
V_1 = \frac{M_1? no}
\]

\[
V_1 = \frac{M_2 \times V_2}{M_1}
\]

Where:
- **M₁** = stock molarity
- **V₁** = volume of stock required
- **M₂** = target molarity
- **V₂** = target final volume

✅ Output is automatically displayed in practical units (L / mL / µL depending on scale)

---

## Smart output and error handling

MolarPrep includes a simple validation layer to reduce bad inputs:

- **Non-positive values** return `ERR`
- Invalid or missing inputs return `ERR`
- Small outputs are automatically shown with a better metric prefix:
  - g → mg → µg
  - L → mL → µL

This is intentionally simple and explicit so users can catch mistakes quickly.

---

## Quick usage guide

### A. Solid reagent workflow
1. Enter **Molecular Weight (g/mol)**
2. Enter **Target Molarity** + choose unit (M, mM, µM, nM)
3. Enter **Final Volume** + choose unit (L or mL)
4. Click **Calculate Mass**
5. Weigh the reported mass

### B. Liquid reagent workflow
1. Enter **Density (g/mL)**
2. Enter **Purity (%)**
3. Enter **Molecular Weight (g/mol)**
4. Enter **Target Molarity (M)**
5. Enter **Target Volume (mL)**
6. Click **Calculate Stock**
7. Pipette the reported stock volume and complete to final volume

---

## Why this tool exists

In real lab workflows, calculation mistakes often come from:
- fatigue
- context switching
- repeated manual conversions
- rushed preparation before experiments

MolarPrep aims to be a small but dependable utility for these everyday tasks.

---

## Features

- ✅ **Two core modules**: solids and liquid stocks
- ✅ **Unit-aware inputs** (M, mM, µM, nM; L, mL)
- ✅ **Smart metric output formatting**
- ✅ **Offline-ready PWA** (after first load)
- ✅ **Mobile-friendly interface**
- ✅ **Simple, transparent formulas**

---

## Installation / PWA (optional)

MolarPrep can be installed as a Progressive Web App (PWA) on supported browsers.

### Desktop / Android
- Open the live app
- Click the **Install** button (if shown), or use browser install prompt

### iPhone / iPad (Safari)
- Open the live app
- Tap **Share**
- Select **Add to Home Screen**

Once installed, it can work offline after the necessary files are cached.

---

## Project structure (current)

```text
MolarPrep/
├── index.html        # Main app UI + logic
├── manifest.json     # PWA metadata
├── sw.js             # Service worker (offline cache)
├── icon-192.png      # App icon
├── icon-512.png      # App icon (high-res)
├── og-image.png      # Social preview image
└── README.md