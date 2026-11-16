# Engineering Lots Sensitivity Analysis in a Semiconductor Fab

Course project for **IE 490SIE: Semiconductors, Manufacturing and Its Supply Chain**, Purdue University. Team of two.

## Question

How does the share of engineering lots (test, calibration and yield-improvement wafers) change production flow, and what is the trade-off between flexibility and throughput?

## Setup

- **Dataset:** SMT2020, Dataset 4, simulated with fab release plans (FabInPlan files) for a 52-week year, 1 Jan to 31 Dec 2018
- **Baseline:** 10 production products and 3 engineering products (E1 to E3), dispatching FIFO. About 400 production lots and 80 engineering lots a week, with the engineering lots split equally across the three engineering products.

| | Engineering | Production |
|---|---|---|
| Lot size | 1 to 10 wafers per lot (average about 5.6) | 25 wafers |
| Release | Monday and Wednesday mornings | Continuous |
| Hot lots | 20% (840 of 4,200 lots) | 2.5% (520 of 20,797 lots) |
| Extra setups | Planarization, lithography | Standard |

**Many lots, few wafers.** In the release plans, engineering lots are 16.8% of all lots (4,200 of 24,997) but only 4.3% of wafers (23,367 of 543,292). The presentation notes that engineering lots can take up to a third of WIP lots.

## Baseline findings

- Fab In and Fab Out stay steady, but WIP climbs toward the end of the period, which points to growing cycle time. Scrap stays near zero.
- Dry Etch, Diffusion and Litho have the longest inline cycle times, mostly waiting. TF_Met, Def_Met and Planar have the shortest.
- Operational efficiency losses dominate OEE. Availability losses are notable in Diffusion, Dry Etch, Litho and Wet Etch.

## Scenarios and results

| Scenario | What changes in the release plan | Fab In (wafers) | Fab Out (wafers) | WIP (wafers) | Fab cycle time (weeks) |
|---|---|---|---|---|---|
| Hot lot size -20% | Lot size of all 4,200 engineering lots set to 20 (from 25) | about 8,930 | about 6,575 | about 34,447 | about 29.2 |
| Hot lot size +40% | Lot size set to 35 for 2,800 engineering lots (two of the three engineering products; the third stays at 25) | 9,820 | 6,487 | 34,581 | 29.50 |
| Due date | Engineering due dates pushed out by 15 days; lots otherwise unchanged | 9,830 | 6,404 | 34,841 | 29.71 |
| More engineering products | Engineering lots rise from 4,200 to 5,158 a year (about 99 a week instead of 81); wafers from 543,292 to 548,616 | not tabulated | not tabulated | highest of all runs | longest of all runs |

The first three rows are the figures from the project presentation. For the fourth scenario the write-up reports results qualitatively: WIP higher than in every other run and the longest average fab cycle time, with the same bottlenecks as the baseline. Dry Etch and Diffusion still have the tallest inline cycle-time bars with a large waiting share, Litho and Wet Etch stay high, and Metrology and Planar remain well below them. Exact values for that run are not in the source files, so none are quoted here.

## Conclusions

- Changing lot sizing, especially the 20% reduction, improves flow more than relaxing due dates. Across the three tabulated runs it gives the lowest WIP (about 34,447 wafers) and the shortest fab cycle time (about 29.2 weeks).
- A 15-day due date leaves the fab looking like the baseline: high WIP and long waits. It shifts expectations rather than improving operations.
- Adding engineering lots pushes the fab further into congestion without moving the bottlenecks.

## Limitations

- The gaps between the three tabulated scenarios are small (about 0.5 week of fab cycle time, under 2%). The presentation does not report replications or confidence intervals, so treat the ranking as indicative.
- The figures come from the course presentation and scenario write-up. The simulation model and raw outputs are not included here.

## Team

Adharsh Rajasekar, Esther Gupta
