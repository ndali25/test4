# Project Name
On_the_Expansion_of_Risk_Pooling

# Authors
Michail Anthropelos, Runhuan Feng, Seongyoon Kim

# Execution Workflow

# Step 1: Primary Execution (Python)
language: python
entry_point: Data/Data/Code_On_the_Expansion_of_Risk_Pooling.ipynb
execution_order: top-to-bottom
required: true
description: >
  This notebook generates all figures and numerical results for the manuscript
  and E-companion. Must be executed fully before any LaTeX compilation.
notes: >
  Monte Carlo simulations are used. Random seeds are not fixed. Minor variation
  is expected but does not affect conclusions.

# Step 2: Optional Execution (LaTeX)
language: latex
files:
  - On_the_Expansion_of_Risk_Pooling__MS__For_final_submission/1Revisedmain.tex
  - On_the_Expansion_of_Risk_Pooling__MS__For_final_submission/2Revised_E_companion.tex
purpose: Documentation / manuscript preparation only
optional: true
notes: >
  LaTeX files do not produce scientific results. Can be compiled locally or
  using Docker if desired.

# Step 3: Optional Docker
files:
  - Dockerfile.LaTeX
purpose: Optional, LaTeX-only compilation
optional: true
notes: >
  Docker must not be used for main analysis. Python notebook is the primary workflow.

# Data
included_files:
  - data/CCRIF_TC.csv
  - data/CCRIF_TC_Info.csv
  - data/Health_data.xlsx
provenance:
  CCRIF_TC.csv: "Trimmed/rescaled from CCRIF. Source: https://www.ccrif.org/"
  CCRIF_TC_Info.csv: "Trimmed/rescaled from CCRIF. Source: https://www.ccrif.org/"
  Health_data.xlsx: "Summary statistics only; proprietary payouts not included."

# Computational Requirements
language: python3
packages:
  - numpy
  - pandas
  - matplotlib
  - scipy
  - math
  - random
  - tqdm
notes: "Runtime < 30 minutes on standard hardware."

# Output
main_outputs:
  - Figures 3-4 (manuscript)
  - Figures 2-11 (E-companion)
other_outputs: "Other figures and tables are either pre-generated or included in manuscript/E-companion LaTeX."

# Important Notes
- Python notebook must be executed **first**.
- LaTeX is optional and **must not be interpreted as primary execution**.
- Docker is optional and only for LaTeX compilation.
