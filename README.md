# Quantum dot heat engine: efficiency at maximum power

An interactive, single-page demo of the quantum dot heat engine studied in

> Sang Hoon Lee, Jaegon Um, and Hyunggyu Park, **"Nonuniversality of heat-engine efficiency at maximum power,"** *Physical Review E* **98**, 052137 (2018). [doi:10.1103/PhysRevE.98.052137](https://doi.org/10.1103/PhysRevE.98.052137)

The paper shows that the well-known "half-Carnot" rule for the efficiency at maximum power, η_op ≈ η_C/2 near equilibrium, can fail for a tightly coupled engine. It fails when the power is maximized by tuning only the quantum dot's gate voltage at a fixed source–drain bias. In that case η_op ≈ η_C instead.

This demo was created by **Claude Opus 5.5** (Anthropic).

## What the demo shows

- **Energy diagram.** The hot lead, the cold lead, and the dot level at the current optimum, with electrons animated at a rate proportional to the particle current.
- **Efficiency at maximum power against η_C.** Three optimization schemes are shown together with η_C, η_C/2, and the Curzon–Ahlborn efficiency:
  - *Gate and bias* is the global optimization over both E_QD and Δμ (Sec. III, Eq. 18).
  - *Bias only* fixes E_QD and varies Δμ (Sec. IV, Eq. 22).
  - *Gate only* fixes Δμ and varies E_QD (Sec. V, Eq. 40).
  
  Optional toggles divide the curves by η_C and overlay the small-η_C expansions from the paper.
- **Power landscape.** A heat map of the power over (E_QD, Δμ). It marks the reversible edge Δμ = η_C·E_QD and the slice being optimized.
- **Power along each slice.** Power plotted against η/η_C. The near-parabolic curve for bias-only tuning peaks at ½. The gate-only curve peaks close to 1.
- **The flux-order argument.** A slider for the order n of a flux J ∝ (X + ξX_t)Xⁿ. It shows the peak moving to η_op = η_C (n + 1)/(n + 2), which approaches η_C as n → ∞ (Eqs. 46–48).

## Model

Units are k_B = 1 and T₂ = 1, with T₁ = T₂/(1 − η_C). Tunnelling rates are normalized so that q + q̃ = ε + ε̃ = 1. The power is

```
W = ½ (q − ε) Δμ,   q = 1 / (1 + e^{E_QD/T₁}),   ε = 1 / (1 + e^{(E_QD − Δμ)/T₂})
```

and the efficiency is η = Δμ / E_QD.

All optima are found numerically in the browser. The code works with log W for numerical stability and uses a grid scan followed by golden-section refinement. The results reproduce these values from the paper:

- q* → 0.0832 as η_C → 0 and q* → 0.2178 as η_C → 1.
- The expansions in Eqs. 18, 22, and 40 at small η_C.
- About 33% higher efficiency and about 71% of the global maximum power for gate-only tuning at η_C = 0.3 and Δμ = T₂. The paper quotes roughly 30% and 70% in Sec. V C.

## Running it

It is one self-contained file with no build step and no dependencies. The only external request is to Google Fonts, and fallback fonts are used if it fails.

- **Locally:** open `index.html` in any modern browser.
- **GitHub Pages:** push the repository, then go to *Settings → Pages* and choose *Deploy from a branch*, selecting the branch and `/ (root)`. The demo will be served at `https://<user>.github.io/<repo>/`.

The page adapts to light and dark mode, works on mobile, and respects the reduced-motion setting.

## Files

| File | Purpose |
| --- | --- |
| `index.html` | The complete interactive demo (HTML, CSS, and JavaScript in one file) |
| `README.md` | This file |

## Credits

- Physics and results: Sang Hoon Lee, Jaegon Um, and Hyunggyu Park, [Phys. Rev. E 98, 052137 (2018)](https://doi.org/10.1103/PhysRevE.98.052137).
- Interactive demo: created by Claude Opus 5.5 (Anthropic).

This is an independent educational visualization and is not affiliated with the authors or the American Physical Society.
