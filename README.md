# Investor Communication and Payout Policy: A Field Experiment

**Journal:** *Review of Finance*

**Authors:** Xiaoqiao Wang, Jing Xie, Bohui Zhang, and Xiaofeng Zhao

**Release:** Aug 2025

This repository provides materials to reproduce the empirical results for **“Investor Communication and Payout Policy: A Field Experiment.”** The analysis uses **Stata** (for estimation and tables) and **SAS** (only if you wish to rebuild the dataset from CSMAR).

## Paper (SSRN)

The paper is available on SSRN: [https://papers.ssrn.com/sol3/papers.cfm?abstract\_id=4255987](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=4255987)

---

## 🔽 One-file download

All data and code are packaged into a single archive:

**`Data_Code_A_Field_of_Dividend.zip`**

Download this file from the repository, unzip it anywhere on your machine, and work **inside the unzipped folder**.

---

## 🚀 Quick start (no CSMAR access needed)

The archive **includes the final combined dataset**:

* `wxxz_rof_regdata.dta`

With this file, you can reproduce the main results directly in Stata.

1. Open Stata and set the working directory to the unzipped folder:

   ```stata
   cd "path/to/Data_Code_A_Field_of_Dividend"
   ```
2. Reproduce **Tables 2–6** and the **appendix tables**:

   ```stata
   do RoF_Regression_Results.do
   ```
3. Generate **additional online-appendix regressions**:

   ```stata
   do RoF_Regression_OnlineApp.do
   ```

---

## What’s inside the ZIP

* `wxxz_rof_regdata.dta` — analysis-ready Stata dataset (**included**).
* `RoF_Regression_Results.do` — reproduces Tables 2–6 and appendix tables.
* `RoF_Regression_OnlineApp.do` — additional online-appendix regressions.
* (Optional) SAS scripts showing the original construction from CSMAR:

  * `0.N.name.sas` (N = 1,…,8) — clean individual CSMAR files
  * `RoF_1.sas`, `RoF_2.sas`, `RoF_3.sas` — merge and construct final regression dataset
  * `RoF_4.sas` — compute Table 1 and Online Appendix 6 & 8
  * (During development, an intermediate `wxxz_rof_regdata.sas7bdat` was exported to `.dta`)

---

## Software

* **Stata 16+** — to replicate Tables 2–6 and appendix tables using the included dataset.
* **SAS 9.4+** — only if rebuilding the dataset from licensed CSMAR inputs (not required for replication).

---

## Notes

* Variable definitions follow **Appendix 1** of the paper.
* If you move files, adjust the working directory (`cd`) at the top of the `.do` files.

---

## Citation

Please cite:

> Wang, X., Xie, J., Zhang, B., & Zhao, X. (2025). *Investor Communication and Payout Policy: A Field Experiment.* Review of Finance.

For questions, please open an issue in this repository.
