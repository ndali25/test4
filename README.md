Manuscript: On the Expansion of Risk Pooling
Authors: Michail Anthropelos, Runhuan Feng, Seongyoon Kim

1. Purpose of This Repository

This repository contains data, Python code, and LaTeX files used to reproduce the results of the manuscript On the Expansion of Risk Pooling and its E-companion.

⚠️ Important clarification

Python code is used to generate numerical results and figures based on simulations and data.

LaTeX files are used only to typeset the manuscript and figures, not to run simulations.

The project is not a single executable pipeline.

Docker execution is optional and applies only to LaTeX compilation, not to Python analysis.

2. How to Reproduce the Results (Recommended Workflow)
Step 1 — Run Python Code (Core Analysis)

All simulations, numerical results, and most figures are generated using Python.

Main file:
Code_On_the_Expansion_of_Risk_Pooling.ipynb

This notebook must be run top to bottom, in order, without skipping cells.

It reproduces:

Manuscript: Figures 3 and 4

E-companion: Figures 2–11

⚠️ Monte Carlo simulations are used. Random seeds are not fixed; minor numerical variation is expected but does not affect conclusions.

Step 2 — Compile LaTeX Files (Manuscript Only)

LaTeX files are provided for document preparation, not for computational analysis.

They can be compiled:

locally (TeX Live / Overleaf), or

optionally using Docker (see Section 6)

Key LaTeX Outputs

Manuscript

Figure 1: CAT.tex

Figure 2: TikZ figures (mainthm.tex, exit.tex)

Tables 1–2: defined directly in the manuscript

Figures 5–6: pre-generated image files

E-Companion

All figures and tables: code included in the E-companion LaTeX files

3. Data Availability and Provenance

All data required to reproduce the results are included.

Included Datasets
File	Description	Source
CCRIF_TC.csv	CCRIF disaster payouts	CCRIF (trimmed/rescaled)
CCRIF_TC_Info.csv	Country-level CCRIF info	CCRIF
Health_data.xlsx	Health-share summary statistics	Proprietary (aggregated)

Original CCRIF data can be accessed at https://www.ccrif.org/
.

4. Variable Dictionaries
CCRIF_TC.csv

Type, Name, Month, Year, Country, Payout

CCRIF_TC_Info.csv

Country, GDP, Area, Occurrences, Occurrence_Probability

Health_data.xlsx

Region, Count, Mean_Compensation, Variance_Compensation, sd

5. Computational Requirements (Python)

Language: Python 3

Packages:
numpy, pandas, matplotlib, scipy, math, random, tqdm

Runtime:
Some simulations may take several minutes; total runtime < 30 minutes on standard hardware.
