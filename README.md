# 🧪 MolarPrep | Host Cell Lab Suite
> **Solution preparation without decimal errors.**

MolarPrep is a professional tool designed for high-stakes laboratory environments. It eliminates calculation fatigue when preparing molar solutions from dry reagents or liquid stocks.

<p align="center">
  <img src="icon-512.png" width="180" alt="MolarPrep Logo">
</p>

<p align="center">
  <a href="https://ebalderasr.github.io/MolarPrep/">
    <img src="https://img.shields.io/badge/🚀_LAUNCH_LIVE_APP-CLICK_HERE_TO_START-00e5ff?style=for-the-badge&labelColor=000000" alt="Launch MolarPrep App">
  </a>
</p>

---

## 🧬 Scientific Fundamentals

The app implements the standard mass-concentration-volume relations, optimized with **Smart Units** to avoid decimal point displacement errors.

### 1. Solid Reagents
The required mass ($m$) for a specific molarity is derived from:
$$m (g) = M \left( \frac{mol}{L} \right) \times V (L) \times MW \left( \frac{g}{mol} \right)$$

### 2. Liquid Reagents (Stock to Solution)
For concentrated liquid reagents, the stock molarity ($M_{1}$) is first calculated:
$$M_{1} = \frac{P \times \rho \times 1000}{MW}$$
Where $P$ is the purity in decimal and $\rho$ is the density in $g/mL$. Then, the dilution equation is applied:
$$V_{1} = \frac{M_{2} \times V_{2}}{M_{1}}$$

## 🔍 Equipment Specs
* **Sensitivity:** For masses below $1.0 mg$, MolarPrep switches to $\mu g$ display. Use analytical balances with $d = 0.01 mg$.
* **Units:** $M$, $mM$, $\mu M$, and $nM$.

## ⚡ Features
* **Offline First:** Fully functional without internet once installed thanks to the Service Worker.
* **Smart Filtering:** Non-positive values trigger an `ERR` state to prevent lab mistakes.
* **PWA Ready:** Install on Android/iOS via the persistent **[ INSTALL ]** button.

## 👨‍🔬 Author
**Emiliano Balderas**
Biotechnology Engineer | PhD Student in Biochemistry
*Instituto de Biotecnología (IBt) - UNAM*.

---
**Host Cell Lab Suite** – *Brutalist tools for high-performance biotechnology.*