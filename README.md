Project: On_the_Expansion_of_Risk_Pooling
Authors: Michail Anthropelos, Runhuan Feng, Seongyoon Kim

# Purpose
Automatically execute the main Python notebook **headlessly** and save outputs in /app/99_logs.
Do NOT start any interactive Jupyter server.

# Notebook Execution Command
Use the following command to run the notebook automatically:
jupyter nbconvert --to notebook --execute analysis/Code_On_the_Expansion_of_Risk_Pooling.ipynb --output executed_notebook.ipynb --ExecutePreprocessor.timeout=600

# Input Data
- analysis/CCRIF_TC.csv
- analysis/CCRIF_TC_Info.csv
- analysis/Health_data.xlsx

# Output Folder
- /app/99_logs/
Contains:
  - executed_notebook.ipynb
  - generated figures and tables

# Python Environment
Base image: python:3.11-slim

Required Python packages:
- numpy
- pandas
- matplotlib
- scipy
- tqdm
- jupyter
- nbconvert
- openpyxl

# Docker Instructions
1. WORKDIR: /app
2. COPY all project files into /app
3. Install all dependencies
4. Create /app/99_logs
5. Execute the notebook using the command above
6. Move executed notebook to /app/99_logs/
7. Do NOT expose ports
8. Do NOT start interactive Jupyter server
