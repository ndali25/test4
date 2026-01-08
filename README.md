Project: On_the_Expansion_of_Risk_Pooling
Authors: Michail Anthropelos, Runhuan Feng, Seongyoon Kim

# Purpose
Automatically execute the main Python notebook **headlessly** in a Docker container.
Do NOT start an interactive Jupyter server.

# Notebook to Run
File: analysis/Code_On_the_Expansion_of_Risk_Pooling.ipynb

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

# Execution Instructions for Docker
1. Set WORKDIR to `/app`.
2. Copy all project files into `/app`.
3. Install all Python dependencies.
4. Create folder `/app/99_logs/` **before execution**.
5. Run the notebook headlessly using:
