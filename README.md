# Project
On_the_Expansion_of_Risk_Pooling

# Authors
Michail Anthropelos, Runhuan Feng, Seongyoon Kim

# Purpose
This README specifies an automated workflow for executing the Python notebook 
that generates all results for the manuscript and E-companion. 
No LaTeX compilation or browser interaction is included.

# Required Files
analysis/Code_On_the_Expansion_of_Risk_Pooling.ipynb
analysis/CCRIF_TC.csv
analysis/CCRIF_TC_Info.csv
analysis/Health_data.xlsx

# Output Folder
All outputs (executed notebook, figures, tables) are stored in 99_logs/

# Dockerfile Instructions
1. Base image: python:3.11-slim
2. Working directory: /app
3. Copy all files into container
4. Install Python packages: numpy, pandas, matplotlib, scipy, tqdm, jupyter, nbconvert
5. Create folder /app/99_logs
6. Command to run automatically when container starts:
   - Execute notebook:
       jupyter nbconvert --to notebook --execute analysis/Code_On_the_Expansion_of_Risk_Pooling.ipynb
   - Save output as executed_notebook.ipynb in /app/99_logs/

# Build Docker Image
docker build -t test4-python -f Dockerfile.python .

# Run Container (automatic notebook execution)
docker run --rm -v "$(pwd)/99_logs:/app/99_logs" --name rtest4-run test4-python

# Check Results
ls 99_logs/
# Should contain executed_notebook.ipynb and any generated figures/tables

# Notes
- Monte Carlo simulations may produce minor variations in results.
- This workflow is fully automated and headless (no interactive browser needed).
- LaTeX compilation is not included.
