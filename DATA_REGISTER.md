# Data register

Every dataset used in this project, where it came from, and what the licence allows.

| Dataset | Source | Licence | Downloaded | Notes |
|---|---|---|---|---|
| FreshRetailNet-50K | Hugging Face dataset (Dingdong); paper: [arXiv 2505.16319](https://arxiv.org/abs/2505.16319) | Paper CC BY 4.0. Check the data licence on the Hugging Face dataset card before publishing derived files | _date_ | Hourly sales, 863 perishable products, 898 stores, stockout flags, discounts, weather. |
| Context figures | [UNEP Food Waste Index 2024, via UN News](https://news.un.org/en/node/1148036) | Cited, not re-hosted | _date_ | 1.05 bn tonnes wasted in 2022; 131 Mt in retail. |

**Policy:** raw files stay in `data/raw/` and are never committed. Published outputs are code, aggregates and charts.
