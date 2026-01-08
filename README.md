README

Manuscript: On the Expansion of Risk Pooling
Authors: Michail Anthropelos, Runhuan Feng, Seongyoon Kim

1. Overview

This repository contains all data and code required to reproduce the results, figures, and tables in the manuscript On the Expansion of Risk Pooling and its E-companion. The main analyses are implemented in Python, with additional figures and tables generated via LaTeX and external tools where noted.

To reproduce the results, users should first review the data files, then run the provided Python notebook in order, and finally consult the manuscript and E-companion for figures and tables generated outside Python.

2. Data Availability and Provenance

All data necessary to reproduce the results are included in this package.

Datasets Used

CCRIF Case Study

CCRIF_TC.csv

CCRIF_TC_Info.csv

Source: Caribbean Catastrophe Risk Insurance Facility (CCRIF), https://www.ccrif.org/

Notes: These datasets are trimmed and rescaled versions of the original CCRIF data.

Health-Share Case Study

Health_data.xlsx

Notes: Original payout-level data are proprietary. The provided dataset contains summary statistics, which are sufficient to reproduce all results in the paper.

Some analyses rely on Monte Carlo simulations rather than empirical data. These simulations may generate minor numerical variation, but such differences are negligible and do not affect the conclusions.

3. Variable Dictionaries
Dataset: CCRIF_TC.csv

Type: Type of disaster

Name: Name of disaster

Month: Month of occurrence

Year: Year of occurrence

Country: Country affected

Payout: Total payout amount by CCRIF

Dataset: CCRIF_TC_Info.csv

Country: Country name

GDP: Gross Domestic Product

Area: Country area

Occurrences: Number of payouts during the sample period

Occurrence_Probability: Relative frequency of payouts

Dataset: Health_data.xlsx

Region: City or region name

Count: Monthly number of payouts

Mean_Compensation: Mean compensation amount

Variance_Compensation: Variance of compensation

sd: Standard deviation of compensation

4. Computational Requirements

Programming language: Python

Required packages:
numpy, pandas, matplotlib, scipy, math, random, tqdm

Monte Carlo simulations are used, and random seeds are not fixed. Stability is achieved by averaging across simulations. Some simulations (e.g., Figure 3 in the manuscript) may take several minutes to run; total runtime should be under 30 minutes on standard hardware (e.g., Google Colab).

5. Programs and Code Execution
Main Code

File: Code_On_the_Expansion_of_Risk_Pooling.ipynb

The notebook should be run top to bottom, in order, without skipping cells.

This notebook reproduces:

Manuscript: Figures 3 and 4

E-companion: Figures 2–11

Other Figures and Tables

Manuscript

Figure 1: CAT.tex

Figure 2: LaTeX/TikZ (mainthm.tex, exit.tex), images in Figures/SC.png and Figures/WC.png

Tables 1–2: Code included in manuscript

Figure 5: Figures/map_CCRIF_corrected.JPG (created externally)

Figure 6: Figures/map_china.JPG (created externally)

Tables 3–5: Code included in E-companion

E-Companion

All figures and tables: Code included in the E-companion files

6. Notes

All code uses relative paths and should run on any standard system.

Minor numerical differences due to simulation randomness are expected and do not affect results.

Code for appendix/E-companion results is included where available.
