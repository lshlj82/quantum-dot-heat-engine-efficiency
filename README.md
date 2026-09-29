# Quantum dot heat engine: efficiency at maximum power

An interactive, single-page demo of the quantum dot heat engine studied in

> Sang Hoon Lee, Jaegon Um, and Hyunggyu Park, **"Nonuniversality of heat-engine efficiency at maximum power,"** *Physical Review E* **98**, 052137 (2018). [doi:10.1103/PhysRevE.98.052137](https://doi.org/10.1103/PhysRevE.98.052137)

The paper shows that the well-known "half-Carnot" rule for the efficiency at maximum power, η<sub>op</sub> ≈ η<sub>C</sub>/2 near equilibrium, can fail for a tightly coupled engine. It fails when the power is maximized by tuning only the quantum dot's gate voltage at a fixed source–drain bias. In that case η<sub>op</sub> ≈ η<sub>C</sub> instead.

This demo was created by **Claude Opus 5.5** (Anthropic).

## What the demo shows

- **Energy diagram with a live simulation.** The hot and cold leads (their Fermi edges smeared in proportion to temperature) and the dot level at the current optimum. Electrons hop at their actual tunnelling rates, drawn from a stochastic (Gillespie) simulation of the master equation, Eq. (2), including backward hops. Brackets show the energy bookkeeping per electron: heat <i>Q</i><sub>1</sub> = <i>E</i><sub>QD</sub> absorbed from the hot lead, heat <i>Q</i><sub>2</sub> = <i>E</i><sub>QD</sub> − Δμ released to the cold lead, and work <i>W</i> = Δμ. Live counters compare the simulated current, power, and efficiency with the exact values, and the speed can be set to 1×, 10×, or 100×.
- **Efficiency at maximum power against η<sub>C</sub>.** Three optimization schemes are shown together with η<sub>C</sub>, η<sub>C</sub>/2, and the Curzon–Ahlborn efficiency:
  - *Gate and bias* is the global optimization over both <i>E</i><sub>QD</sub> and Δμ (Sec. III, Eq. 18).
  - *Bias only* fixes <i>E</i><sub>QD</sub> and varies Δμ (Sec. IV, Eq. 22).
  - *Gate only* fixes Δμ and varies <i>E</i><sub>QD</sub> (Sec. V, Eq. 40).
  
  Optional toggles divide the curves by η<sub>C</sub> and overlay the small-η<sub>C</sub> expansions from the paper.
- **Power landscape.** A heat map of the power over (<i>E</i><sub>QD</sub>, Δμ). It marks the reversible edge Δμ = η<sub>C</sub>·<i>E</i><sub>QD</sub> and the slice being optimized.
- **Power along each slice.** Power plotted against η/η<sub>C</sub>. The near-parabolic curve for bias-only tuning peaks at ½. The gate-only curve peaks close to 1.
- **The flux-order argument.** A slider for the order <i>n</i> of a flux <i>J</i> ∝ (<i>X</i> + <i>ξX</i><sub>t</sub>)<i>X</i><sup><i>n</i></sup>. It shows the peak moving to η<sub>op</sub> = η<sub>C</sub> (<i>n</i> + 1)/(<i>n</i> + 2), which approaches η<sub>C</sub> as <i>n</i> → ∞ (Eqs. 46–48).

## Model

Units are <i>k</i><sub>B</sub> = 1 and <i>T</i><sub>2</sub> = 1, with <i>T</i><sub>1</sub> = <i>T</i><sub>2</sub>/(1 − η<sub>C</sub>). Tunnelling rates are normalized so that q + q̃ = ε + ε̃ = 1. The power is

$$
\dot W = \tfrac{1}{2}(q-\epsilon)\,\Delta\mu, \qquad
q = \frac{1}{1+e^{E_\mathrm{QD}/T_1}}, \qquad
\epsilon = \frac{1}{1+e^{(E_\mathrm{QD}-\Delta\mu)/T_2}}
$$

and the efficiency is η = Δμ / <i>E</i><sub>QD</sub>.

All optima are found numerically in the browser. The code works with log W for numerical stability and uses a grid scan followed by golden-section refinement. The results reproduce these values from the paper:

- <i>q</i>* → 0.0832 as η<sub>C</sub> → 0 and <i>q</i>* → 0.2178 as η<sub>C</sub> → 1.
- The expansions in Eqs. 18, 22, and 40 at small η<sub>C</sub>.
- About 33% higher efficiency and about 71% of the global maximum power for gate-only tuning at η<sub>C</sub> = 0.3 and Δμ = <i>T</i><sub>2</sub>. The paper quotes roughly 30% and 70% in Sec. V C.

## Credits

- Physics and results: Sang Hoon Lee, Jaegon Um, and Hyunggyu Park, [Phys. Rev. E 98, 052137 (2018)](https://doi.org/10.1103/PhysRevE.98.052137).
- Interactive demo: created by Claude Opus 5.5 (Anthropic).

This is an independent educational visualization and is not affiliated with the authors or the American Physical Society.
