# Project Name
On_the_Expansion_of_Risk_Pooling

# Authors
Michail Anthropelos, Runhuan Feng, Seongyoon Kim

# Main Execution
language: python
entry_point: Code_On_the_Expansion_of_Risk_Pooling.ipynb
execution_order: top-to-bottom
notes: "Run all cells sequentially. This notebook generates all main figures and results."

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
notes: "Monte Carlo simulations used; random seeds not fixed. Runtime < 30 minutes."

# LaTeX / Manuscript
language: latex
files:
  - On_the_Expansion_of_Risk_Pooling__MS__For_final_submission/1Revisedmain.tex
  - On_the_Expansion_of_Risk_Pooling__MS__For_final_submission/2Revised_E_companion.tex
purpose: "Document preparation only; does not produce scientific results."
optional: true

# Docker
files:
  - Dockerfile.LaTeX
purpose: "Optional, LaTeX-only compilation. Not required for main execution."
optional: true

# Output
main_outputs:
  - Figures 3-4 (manuscript)
  - Figures 2-11 (E-companion)
notes: "Other figures/tables are either pre-generated or included in manuscript/E-companion LaTeX."

# Important Notes
- "Do not execute LaTeX or Docker to reproduce results."
- "Python notebook is the primary workflow."
- "Dockerfile.LaTeX exists only for optional compilation."
