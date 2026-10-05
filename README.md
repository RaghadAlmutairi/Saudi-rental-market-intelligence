# Saudi Residential Rental Market Intelligence

Market intelligence project for the **AWS Agentic AI Business Professional** Nanodegree (Udacity), built in **Amazon Quick Suite** using Spaces, Quick Research, and a custom chat agent.

**Question:** Which of Riyadh, Jeddah, Dammam, or Al-Khobar should a residential rental investor evaluate first, based on 2021 listing data and 2025-2026 market signals?

**Answer (Medium confidence):** Evaluate **Dammam and Al-Khobar** first, then Jeddah, then Riyadh. This is a prioritization result, not an investment decision.

## Key findings

| # | Insight | Confidence |
|---|---|---|
| 1 | Riyadh's five-year rent freeze (from 25 Sep 2025) caps near-term income growth | High (freeze exists) / Medium (impact) |
| 2 | Dammam and Al-Khobar: steady ~2-3% growth, no freeze, fragmented competition | Medium |
| 3 | Jeddah: highest rents, but the 382,500-unit pipeline is regional (Western KSA), not Jeddah-specific | Medium |
| 4 | Institutional competition is concentrated in Riyadh | Medium |

## Repository structure

```
.
├── README.md
├── report/
│   └── Research_Brief_Raghad_Almutairi.docx    # Main submission document
├── deliverables/                               # Agent outputs (Markdown)
│   ├── 01_market_analysis.md
│   ├── 02_reliability_evaluation.md
│   └── 03_market_intelligence_brief.md
├── research/                                   # Quick Research report (PDF)
├── data/
│   └── Saudi_Arabia_Real_Estate.csv            # Aqar rental listings, 2021
├── screenshots/                                # Evidence, Figures 1-10
└── .gitignore
```

## Method

1. **Dataset:** [Saudi Arabia Real Estate (Aqar)](https://www.kaggle.com/datasets/lama122/saudi-arabia-real-estate-aqar) from Kaggle: 3,718 rental listings, scraped 2021.
2. **Agent:** a Quick Suite chat agent with the dataset (in a Space) as its knowledge base. Rules: use medians, label every claim DATASET or EXTERNAL RESEARCH, never invent figures, no yield/ROI conclusions.
3. **Quick Research:** six-topic Fast-mode project on rent growth, supply, vacancy, regulation, and competition (2025-2026).
4. **Outputs:** Market Analysis, Reliability and Confidence Evaluation, and Market Intelligence Brief, then a validation pass against the raw CSV.

## Data quality finding

The raw CSV has **2,197 exact duplicate rows** out of 3,718, leaving **1,521 unique listings**. Medians on unique listings keep the same city ranking, but some figures change:

| City | Unique listings | Median rent (SAR), unique | Median rent (SAR), raw | Furnished % (unique) | Furnished % (raw) |
|---|---|---|---|---|---|
| Riyadh | 904 | 80,000 | 80,000 | 10.5 | 10.1 |
| Jeddah | 411 | 100,000 | 95,000 | 16.5 | 17.1 |
| Dammam | 123 | 60,000 | 60,000 | 12.2 | 21.8 |
| Al-Khobar | 83 | 65,000 | 75,000 | 18.1 | 1.5 |

The apparent "furnished niche" in Al-Khobar (1.5%) was a duplicate artifact and is withdrawn. Dammam and Al-Khobar rest on small samples. The agent outputs in `deliverables/` were generated from the raw data and carry a correction note at the top.


## Author

Raghad Almutairi, October 2026
