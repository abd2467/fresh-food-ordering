# Fresh food ordering when stockouts hide demand

> **Decision:** _to be filled in when the analysis is done._ Ordering on corrected demand cuts waste by X% and raises fill rate by Y points; a Z% markdown at N hours before expiry adds $W profit per store per week.

**Status:** set up 2026-11-27; analysis not started.

**The question:** How much better can a store order fresh products, and set markdowns, once it corrects for demand hidden by stockouts?

## The problem
The world wasted 1.05 billion tonnes of food in 2022, 19% of food available to consumers; retail alone wasted 131 million tonnes (UNEP Food Waste Index 2024). For fresh products, stores face a trap: when a shelf empties, recorded sales stop, so the data understates real demand, and ordering systems trained on those sales under-order. Most forecasting projects use M5-style data that doesn't flag stockouts. FreshRetailNet-50K does, and its authors found that recovering hidden demand removed a 7.37% underestimation. This project turns that correction into ordering and markdown decisions.

## Approach
1. Select 50 to 200 store-product series from FreshRetailNet-50K.
2. Recover true demand during stockout hours (censored-demand model or the authors' baseline); reproduce the 7.37% bias direction.
3. Simulate a shelf-life-aware ordering policy (newsvendor or perishable reorder policy), trained on raw sales vs corrected demand.
4. Estimate the discount response and add a markdown rule for products near expiry.
5. Compare on a held-out period: units wasted, fill rate, profit.
6. Behavioural angle: markdown depth vs reference prices; test (not assume) a pull-to-centre ordering bias.

## Repo layout
| Folder | Contents |
|---|---|
| `data/` | Raw data (not committed) and processed files |
| `notebooks/` | Numbered analysis notebooks |
| `src/` | Reusable scripts |
| `app/` | Streamlit dashboard |
| `reports/` | Decision memo and charts |
| `notes/` | Learning log, SQL log, setup guide, project map |

## Data
See [DATA_REGISTER.md](DATA_REGISTER.md). Raw data is not re-hosted here.

## How AI was used
See [AI_USE.md](AI_USE.md).

## Reproduce
```bash
git clone https://github.com/abd2467/fresh-food-ordering.git
cd fresh-food-ordering
python3 -m venv .venv
# Mac/Linux: source .venv/bin/activate    Windows: .venv\Scripts\activate
pip install -r requirements.txt
```
