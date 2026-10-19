# A Modular Two-Stage Bioprocess Unit for Converting Food Waste into PHA

**Biotechnology Research Internship — Week 4: Prototype Development and Findings Documentation**
**Rabi Narayan Patra** | 24 October 2026

A conceptual prototype for a biotechnological product, synthesising the three preceding components of this
project into a unit that could be built.

## The product

A **modular, transportable bioprocess unit** that converts food waste into polyhydroxyalkanoate (PHA)
bioplastic **at the point where the waste is generated**.

| Module | Function |
|---|---|
| **A — Acidogenesis** | Leach-bed reactor; pH held at 5.2 so methanogens are inhibited and carboxylic acids accumulate instead of biogas |
| **B — PHA accumulation** | 200 L fed-batch bioreactor; engineered *Cupriavidus necator*; pH 7.0, 30 °C, DO 30%, C/N 6 |
| **C — Recovery** | Cross-flow filtration + **enzymatic** lysis of non-PHA biomass, avoiding chlorinated solvent |
| **D — Control and enzyme selection** | The shared sensing, control and data layer |

## The mechanism at the heart of the design

The hardest problem is that the cheap, concentrated acid stream that makes the economics work is also what
kills the organism — inhibition sets in above ~5 g/L. Diluting the feed works but throws away the advantage.

Instead, a **pH-static control loop** measures residual acid every 15 minutes and adds feed only as fast as
the culture consumes it, holding the reactor near **1 g/L** while the feed vessel holds a concentrated stream.
The culture never sees the high concentration; the process still uses one. **It also fails safe** — if the
sensor drifts, the culture is starved rather than poisoned, and starvation costs time while poisoning costs the
batch.

## Why it is deliberately small

Food waste is 75–80% water and is generated in small quantities at thousands of separate sites. Collecting it
centrally consumes the very cost advantage it provides. A unit at the point of generation removes the transport
step, and the product leaves as a dense dry powder. **Scale is achieved by replication rather than
enlargement**, which avoids the oxygen-transfer and mixing problems that dominate conventional scale-up.

## Projected performance

**~1.1 kg/day dry PHA powder from ~20 kg/day dry food waste** (≈90 kg wet) — the throughput of one canteen.

| Stage | Yield assumption | Output |
|---|---|---|
| Acidogenesis | 0.21 g acids per g dry waste | 4.2 kg/day VFA |
| Accumulation | 0.30 g PHA per g VFA | 1.26 kg/day PHA |
| Recovery | 90% | **1.13 kg/day powder** |

**Overall mass yield 5.7%** — and the document is explicit that this is the central engineering fact of the
process. No plausible biological improvement changes that order of magnitude, which is exactly why the
feedstock must be free. Target titre **45 g/L**, set between the published VFA value (42.3 g/L) and the
purified-substrate best (58.5 g/L).

## Risk assessment

**Twelve failure modes scored before mitigation.** The uncomfortable and useful conclusion: **the
highest-scoring risks are not technical.** R9 — the product cannot be sold at a profit — scores as highly as
R1, that the organism is poisoned. R7, the recovery step, is the module with the weakest published evidence
behind it.

Two of the top risks are answered by the *architecture* rather than by a contingency, which is what scoring
before mitigation reveals: R1 by the control loop, R6 (feedstock variability) by measuring rather than
assuming the feed.

## Development plan

Four stages, each ending in a **go/no-go gate with a stated stop condition**, ordered so the cheapest question
is asked first — a failure at Gate 1 costs 12 weeks; the same failure at Gate 3 would cost two years.

| Gate | Scale | Question | Stop condition |
|---|---|---|---|
| 1 | 1 L · 12 wk | Does the mass balance close? | Yield < 0.15 g PHA per g VFA |
| 2 | 200 L · 24 wk | Does the control loop hold at scale? | Setpoint not held within ±0.3 g/L |
| 3 | 2 modules · 30 wk | Does the chain run on real waste? | Recovery < 70% or M_w < 200 kDa |
| 4 | desk · 8 wk | Can it be sold at a profit? | Commercial case does not close |

## Repository contents

```
├── README.md
├── Prototype_Design_and_Development_Plan_Biotech.docx   # the document (18 pages, ~4,930 words)
├── Prototype_Design_and_Development_Plan_Biotech.pdf
├── references.md                                        # the 16 sources
└── figures/                                             # all seven figures
```

**In the v1.0 release bundle:** the document in both formats, all seven figures, and the figure-generation
script.

## A note on the file format

The task specifies PDF; the portal's upload box accepts **Word only**. Both are provided.

## Author

**Rabi Narayan Patra** — Biotechnology Research Intern, 2026.
GitHub: [@rabinarayanpatra350-biotech](https://github.com/rabinarayanpatra350-biotech)
