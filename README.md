# Project Name
On_the_Expansion_of_Risk_Pooling

# Authors
Michail Anthropelos, Runhuan Feng, Seongyoon Kim

# Execution Workflow

# Step 1: Primary Execution (Python Notebook)
dockerfile: Dockerfile.python
execution_order: 1
required: true
description: >
  This Dockerfile executes the main Jupyter notebook located at
  Data/Data/Code_On_the_Expansion_of_Risk_Pooling.ipynb.
  It generates all figures, tables, and numerical results used in the manuscript
  and E-companion. Outputs are saved in 99_logs/.
notes: >
  Monte Carlo simulations are used. Random seeds are not fixed, so minor
  variations are expected but do not affect conclusions.

# Step 2: Optional Execution (LaTeX Manuscript Compilation)
dockerfile: Dockerfile.latex
execution_order: 2
optional: true
description: >
  This Dockerfile compiles the LaTeX manuscript and E-companion PDFs.
  It requires that the Python notebook has been executed first.
notes: >
  LaTeX files do not produce scientific results. PDFs are saved in 99_logs/.
  This step is only for manuscript preparation.

# Dockerfile Naming Rules
# - Dockerfile.python must exist and be used first
# - Dockerfile.latex is optional and must be used second
# - Do not leave any default 'Dockerfile' that contains only LaTeX instructions
#   to avoid misinterpretation by automated systems.

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
  - 1Revisedmain.pdf (from Dockerfile.latex)
  - 2Revised_E_companion.pdf (from Dockerfile.latex)

# Important Notes
- **Dockerfile.python must always be run first.**
- **Dockerfile.latex is optional and must only be run after the Python notebook.**
- All outputs (executed notebook and PDFs) are saved to `99_logs/`.
- Do **not leave any default Dockerfile** with only LaTeX commands; automated tools may pick it first.
- This structure ensures automated systems execute the primary analysis correctly.
