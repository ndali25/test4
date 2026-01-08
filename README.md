# Project Name
On_the_Expansion_of_Risk_Pooling

# Authors
Michail Anthropelos, Runhuan Feng, Seongyoon Kim

# Execution Workflow

# Step 1: Primary Execution (Python Notebook Only)
dockerfile: Dockerfile.python
execution_order: 1
required: true
description: >
  This Dockerfile executes the main Jupyter notebook located at
  Data/Data/Code_On_the_Expansion_of_Risk_Pooling.ipynb.
  It generates all figures, tables, and numerical results used in the manuscript
  and E-companion.
notes: >
  LaTeX compilation is not included in this workflow.
  Only Python analysis is executed. Monte Carlo simulations are used.
  Random seeds are not fixed, so minor variations are expected but do not
  affect conclusions.

# Dockerfile Naming Rules
# - Dockerfile.python must exist and be used.
# - Do not leave any default Dockerfile or LaTeX-only Dockerfile
#   to prevent automated systems from executing LaTeX first.

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
notes: "Runtime < 30 minutes on standard hardware. No fixed random seed for Monte Carlo simulations."

# Output
main_outputs:
  - executed_notebook.ipynb (from Dockerfile.python)
  - Figures 3-4 (manuscript)
  - Figures 2-11 (E-companion)
  - All outputs saved in 99_logs/

# Important Notes
- **Only Dockerfile.python should be run.**
- **Do not run any LaTeX workflow for now.**
- All outputs (executed notebook and figures) are saved to `99_logs/`.
- This ensures automated systems only execute the Python analysis.
