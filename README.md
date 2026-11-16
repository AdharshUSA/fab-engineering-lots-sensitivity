# Engineering Lots Sensitivity Analysis in a Semiconductor Fab

Course project for **IE 490SIE: Semiconductors, Manufacturing and Its Supply Chain**, Purdue University. Team of two.

## Question

How does the share of engineering lots (test, calibration and yield-improvement wafers) change production flow, and what is the trade-off between flexibility and throughput?

## Setup

- **Dataset:** SMT2020, Dataset 4
- **Baseline:** 10 production products and 3 engineering products. 400 production lots and 80 engineering lots, with the engineering lots split equally across the three engineering products.
- **Engineering vs production lots:**

| | Engineering | Production |
|---|---|---|
| Lot size | 1 to 10 wafers | 25 wafers |
| Release | Monday and Wednesday mornings | Continuous |
| Hot lots | 20% | 2.5% |
| Extra setups | Planarization, lithography | Standard |

## Baseline findings

- Fab In and Fab Out stay steady, but WIP climbs, which points to growing cycle time.
- Dry Etch, Diffusion and Litho have the longest cycle times, mostly waiting.
- Operational efficiency losses dominate OEE. Availability losses are notable in Diffusion, Dry Etch, Litho and Wet Etch.

## Scenarios and results

| Scenario | Change | Fab In | Fab Out | WIP | Fab cycle time (weeks) |
|---|---|---|---|---|---|
| Hot lot size -20% | Smaller engineering hot lots | ~8,930 | ~6,575 | ~34,447 | ~29.2 |
| Hot lot size +40% | Larger engineering hot lots | 9,820 | 6,487 | 34,581 | 29.5 |
| Due date | 15-day due date for engineering lots | 9,830 | 6,404 | 34,841 | 29.7 |

**Conclusion:** changing hot lot sizing, especially the 20% reduction, improves flow more than relaxing due dates. A looser due date mostly shifts expectations rather than performance.

## Team

Adharsh Rajasekar, Esther Gupta
