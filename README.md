# SIADS 696 Milestone II — Group 17

## Neurodiversity and Archetypes: Predicting ADHD Signals and Discovering Jungian-like Personality Clusters via Big Five–to–MBTI Feature Engineering

**Authors:** Zhiqi (Jenny) Zhu, Ki Yip (Keith) Chan, Yijing (Frank) Wang
**Course:** SIADS 696 — Milestone II
**Date:** 2026-03-03

---

## Project Overview

This project combines supervised and unsupervised machine learning to study neurodiversity from both predictive and structural perspectives.

**Part A — Supervised Learning:** Predicts self-reported ADHD signals among tech workers using the OSMI Mental Health in Tech Survey (2016–2023), augmented with BEA Regional Price Parities. A tuned Decision Tree (CV recall 0.830 ± 0.034) identifies comorbidity and geographic features as primary predictors.

**Part B — Unsupervised Learning:** Discovers interpretable personality archetypes by clustering Big Five traits augmented with continuous Jungian/MBTI-style proxy features (OpenPsychometrics IPIP-FFM dataset, n = 19,554). K-Means (K=2) reveals two macro-archetype profiles; K=3 provides finer-grained substructure validated by cross-method ranking. Stability checks confirm robustness (seed ARI = 0.996, subsample ARI = 0.970, proxy-sensitivity ARI range 0.838–1.000).

---

## Repository Structure

```
├── README.md
├── LICENSE
├── .gitignore
├── 17-milestoneii_wn26_report.pdf              # Final report (PDF)
├── Google Doc Link.md                           # Link to shared Google Doc
│
├── Part_A_Supervised_Learning/
│   ├── PartA_ML_FINAL.ipynb                     # Part A notebook (preprocessing, modeling, evaluation)
│   ├── PartA_preprocessing.ipynb                # Preprocessing pipeline notebook
│   ├── PartA_df.csv                             # Processed Part A feature matrix
│   └── OMSI_data/                               # Raw OSMI survey CSVs (2016–2023)
│       ├── 2016.csv
│       ├── 2017.csv
│       ├── 2018.csv
│       ├── 2019.csv
│       ├── 2020.csv
│       ├── 2021.csv
│       ├── 2022.csv
│       └── 2023.csv
│
└── Part_B_Unsupervised_Learning/
    ├── PartB.ipynb                              # Part B notebook (clustering, stability, sensitivity)
    ├── PartB_data.csv                           # Raw Big Five item-level responses (OpenPsychometrics)
    ├── internal_metrics.csv                     # Silhouette, DB, CH for all configurations
    ├── sensitivity_n_proxy.csv                  # Proxy-weighting sensitivity results
    ├── proxy_correlation.csv                    # Proxy–source trait correlations
    ├── cluster_assignments.csv                  # Row-level cluster labels (19,554 rows)
    ├── kmeans_cluster_profile.csv               # K-Means centroid profiles
    ├── gmm_cluster_profile.csv                  # GMM component profiles
    ├── stability_summary.csv                    # Seed & subsample stability ARI results
    └── selection_summary.csv                    # Composite rank model selection summary
```

---

## Data Sources

| Dataset | Source | Used In |
|---------|--------|---------|
| OSMI Mental Health in Tech Survey (2016–2023) | [osmhhelp.org/research.html](https://osmhhelp.org/research.html) | Part A |
| BEA Regional Price Parities | [bea.gov](https://www.bea.gov/) | Part A |
| IPIP-FFM Big Five (OpenPsychometrics) | [openpsychometrics.org/_rawdata/](http://openpsychometrics.org/_rawdata/) | Part B |

---

## How to Run

### Part A

1. Ensure raw OSMI CSV files are in `Part_A_Supervised_Learning/OMSI_data/`
2. Run `Part_A_Supervised_Learning/PartA_ML_FINAL.ipynb` end-to-end
3. Key dependencies: `pandas`, `numpy`, `scikit-learn`, `matplotlib`, `fuzzywuzzy`, `shap`

### Part B

1. Ensure `Part_B_Unsupervised_Learning/PartB_data.csv` is present
2. Run `Part_B_Unsupervised_Learning/PartB.ipynb` end-to-end
3. Key dependencies: `pandas`, `numpy`, `scikit-learn`, `matplotlib`, `seaborn`

---

## Google Doc

[View the shared Google Doc](https://docs.google.com/document/d/1THOiQUSqZisZ92xPCd7JOxg0nTVS_rPV/edit?usp=drive_link&ouid=111449203209047028657&rtpof=true&sd=true)

---

## License

This project is submitted as coursework for SIADS 696 at the University of Michigan School of Information.
