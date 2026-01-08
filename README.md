# Project Name
On_the_Expansion_of_Risk_Pooling

# Authors
Michail Anthropelos, Runhuan Feng, Seongyoon Kim

# Purpose
This README is dedicated to executing the Python notebook only. 
The notebook generates all figures, tables, and results used in 
the manuscript and E-companion. LaTeX compilation is explicitly excluded.

# Project Structure
analysis/: Folder containing:
  - Code_On_the_Expansion_of_Risk_Pooling.ipynb (main notebook)
  - CCRIF_TC.csv
  - CCRIF_TC_Info.csv
  - Health_data.xlsx
99_logs/: Output folder (created automatically if not present)

# Execution Workflow
1. Build the Docker image
   - Dockerfile: Dockerfile.python
   - Command: 
       docker build -t test4-python -f Dockerfile.python .

2. Run the container to execute the notebook automatically
   - Command:
       docker run --rm -v "$(pwd)/99_logs:/app/99_logs" --name rtest4-run test4-python
   - Outputs:
       - executed_notebook.ipynb
       - Generated figures and tables
     stored in `99_logs/`

# Data Provenance
- CCRIF_TC.csv: Trimmed/rescaled from CCRIF. Original: https://www.ccrif.org/
- CCRIF_TC_Info.csv: Trimmed/rescaled from CCRIF. Original: https://www.ccrif.org/
- Health_data.xlsx: Summary statistics only; proprietary payouts not included.

# Computational Requirements
- Language: Python 3.11
- Required packages: numpy, pandas, matplotlib, scipy, tqdm, jupyter, nbconvert
- Runtime: < 30 minutes on standard hardware
- Notes: Monte Carlo simulations may produce minor variations

# Notes
- LaTeX compilation is not included in this workflow.
- All outputs are stored in `99_logs/`.
- The notebook runs automatically when the Docker container starts.
