# Saudi Residential Rental Market Intelligence

Market intelligence project for the **AWS Agentic AI Business Professional** Nanodegree (Udacity), built in **Amazon Quick Suite** with Spaces, Quick Research, and a custom chat agent.

**Question:** Which of Riyadh, Jeddah, Dammam, or Al-Khobar should a residential rental investor evaluate first, based on 2021 listing data and 2025-2026 market signals?

**Answer (Medium confidence):** Evaluate **Dammam and Al-Khobar** first, then Jeddah, then Riyadh. This is a prioritization result, not an investment decision.

## Key findings

| # | Insight | Confidence |
|---|---|---|
| 1 | Riyadh's five-year rent freeze (from 25 Sep 2025) caps near-term income growth | High (freeze exists) / Medium (impact) |
| 2 | Dammam and Al-Khobar: steady ~2-3% growth, no freeze, fragmented competition | Medium |
| 3 | Jeddah: highest rents, but the 382,500-unit pipeline covers all of Western KSA, not Jeddah alone | Medium |
| 4 | Institutional competition is concentrated in Riyadh | Medium |

## Repository structure

| Path | Contents |
|---|---|
| [`report/`](report) | **Research Brief** (main submission document, PDF) |
| [`deliverables/`](deliverables) | Agent outputs: `1_Market_Analysis`, `2_Reliability`, `3_Brief` (PDF) |
| [`Quick Research/`](Quick%20Research) | Quick Research report: external market signals, 2025-2026 |
| [`data/`](data) | `Saudi Arabia Real Estate.csv`: Aqar rental listings, 2021 |
| `Market Intelligence Agent Screanshots.pdf` | Screenshot evidence for each project step |
| `README.md` | This file |

## Method

1. **Dataset:** [Saudi Arabia Real Estate (Aqar)](https://www.kaggle.com/datasets/lama122/saudi-arabia-real-estate-aqar) from Kaggle: 3,718 rental listings, scraped 2021.
2. **Agent:** a Quick Suite chat agent with the dataset (in a Space) as its knowledge base. Rules: use medians, label every claim DATASET or EXTERNAL RESEARCH, never invent figures, no yield or ROI conclusions.
3. **Quick Research:** six-topic Fast-mode project on rent growth, supply, vacancy, regulation, and competition (captured 5 October 2026).
4. **Outputs:** Market Analysis, Reliability and Confidence Evaluation, and Market Intelligence Brief, then a validation pass against the raw CSV.

## Data quality finding (read before using the deliverables)

The raw CSV contains **2,197 exact duplicate rows** out of 3,718, leaving **1,521 unique listings**. The city ranking is unchanged, but some figures differ:

| City | Unique listings | Median rent (SAR), unique | Median rent (SAR), raw | Furnished %, unique | Furnished %, raw |
|---|---|---|---|---|---|
| Riyadh | 904 | 80,000 | 80,000 | 10.5 | 10.1 |
| Jeddah | 411 | 100,000 | 95,000 | 16.5 | 17.1 |
| Dammam | 123 | 60,000 | 60,000 | 12.2 | 21.8 |
| Al-Khobar | 83 | 65,000 | 75,000 | 18.1 | 1.5 |

- The **Research Brief uses unique listings** throughout.
- The **agent outputs in `deliverables/` were generated from the raw data**, so they show the raw figures (e.g. Jeddah SAR 95K, Al-Khobar SAR 75K).
- The apparent Al-Khobar "furnished niche" (1.5% in raw data) was a duplicate artifact. It is **withdrawn**: no furnished gap exists.
- Dammam and Al-Khobar rest on small samples (123 and 83 listings).



## Author

Raghad Almutairi, October 2026
