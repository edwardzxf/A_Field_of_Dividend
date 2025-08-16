# Investor Communication and Payout Policy: A Field Experiment

**Journal:** *Review of Finance*

**Authors:** Xiaoqiao Wang, Jing Xie, Bohui Zhang, and Xiaofeng Zhao

**Release:** Aug 2025

**Download at SSRN:** https://papers.ssrn.com/sol3/papers.cfm?abstract_id=4255987

This repository contains the materials to reproduce the statistics and tables for **“Investor Communication and Payout Policy: A Field Experiment.”** The workflow uses **SAS** for data construction and **Stata** for statistical analysis and table generation.

---

## 🚀 Quick start (no CSMAR access needed)

**Good news:** The **final combined dataset `wxxz_rof_regdata.dta` is included in this repository** (see `data/processed/`). With this file you can reproduce the main tables directly in Stata—**no CSMAR access required**.

1. Open Stata and set the repo as your working directory.
2. Run:

   ```stata
   do code/stata/RoF_Regression_Results.do
   ```

   This reproduces **Tables 2–6** and the **appendix tables**.
3. For additional online-appendix regressions, run:

   ```stata
   do code/stata/RoF_Regression_OnlineApp.do
   ```

---

## Repository structure

```
.
├── code
│   ├── sas/                    # 0.N.name.sas, RoF_1.sas ... RoF_4.sas
│   └── stata/                  # RoF_Regression_Results.do, RoF_Regression_OnlineApp.do
├── data
│   ├── raw/                    # (not included) licensed CSMAR inputs
│   └── processed/
│       └── wxxz_rof_regdata.dta   # INCLUDED final combined dataset for Stata
├── output
│   ├── tables/                 # Table 1; Tables 2–6; appendix tables
│   └── logs/                   # SAS/Stata logs
└── README.md
```

---

## Data

All original datasets are sourced from **CSMAR**. Because CSMAR is a licensed database, the **raw files are not distributed** here.
However, to enable full replication of the main results, **we include the final combined Stata dataset**:

* `data/processed/wxxz_rof_regdata.dta` — the analysis-ready file used by the Stata scripts.

(For completeness: during development, intermediate SAS files such as `wxxz_rof_regdata.sas7bdat` were created before exporting to Stata.)

---

## Code workflow (SAS → Stata)

The SAS scripts document how the dataset was originally built from CSMAR. Running them is **optional** if you use the included `wxxz_rof_regdata.dta`.

| Purpose                                                      | Code name(s)                         | Input data used        |
| ------------------------------------------------------------ | ------------------------------------ | ---------------------- |
| Clean firm fundamental information                           | `0.N.name.sas` where **N ∈ {1,…,8}** | CSMAR                  |
| Combine firm fundamental information                         | `RoF_1.sas`                          | CSMAR                  |
| Construct treatment/control sample                           | `RoF_2.sas`                          | CSMAR                  |
| Generate final regression dataset                            | `RoF_3.sas`                          | CSMAR                  |
| Generate statistics (**Table 1**), Online Appendix **6 & 8** | `RoF_4.sas`                          | CSMAR                  |
| Generate **Tables 2–6** and remaining appendix tables        | `RoF_Regression_Results.do`          | `wxxz_rof_regdata.dta` |

*Also included:* `RoF_Regression_OnlineApp.do` for additional online-appendix regressions.

---

## Software requirements

* SAS (9.4 or later recommended) — only needed to rebuild from raw CSMAR inputs
* Stata (16 or later recommended) — needed to reproduce Tables 2–6 and appendix tables using the included dataset

---

## Notes

* Variable definitions follow **Appendix 1** of the paper.
* If you change the folder layout, update the path globals or `cd` lines at the top of each `.do` file.

---

## Citation

If you use these materials, please cite:

> Wang, X., Xie, J., Zhang, B., & Zhao, X. (2025). **Investor Communication and Payout Policy: A Field Experiment.** *Review of Finance*, _Forthcoming_.

---

## Contact

For replication questions, please open a GitHub issue in this repository.
