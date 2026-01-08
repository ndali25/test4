Project: On_the_Expansion_of_Risk_Pooling
Authors: Michail Anthropelos, Runhuan Feng, Seongyoon Kim

# Purpose
Automatically execute the Python notebook analysis/Code_On_the_Expansion_of_Risk_Pooling.ipynb.
Do not start a Jupyter server.
Do not run LaTeX.
Save outputs in 99_logs/.

# Inputs
Notebook: analysis/Code_On_the_Expansion_of_Risk_Pooling.ipynb
Data: analysis/CCRIF_TC.csv, analysis/CCRIF_TC_Info.csv, analysis/Health_data.xlsx

# Outputs
Folder: 99_logs/
Contains: executed_notebook.ipynb, figures, tables

# Environment
Base image: python:3.11-slim
Packages: numpy, pandas, matplotlib, scipy, tqdm, jupyter, nbconvert

# Instructions for Dockerfile
1. WORKDIR /app
2. COPY all files into /app
3. Install required Python packages (pip install)
4. Create folder /app/99_logs
5. CMD: Execute notebook headlessly using nbconvert:
   jupyter nbconvert --to notebook --execute analysis/Code_On_the_Expansion_of_Risk_Pooling.ipynb --output executed_notebook.ipynb
   Move executed_notebook.ipynb to /app/99_logs/
6. Do NOT expose ports
7. Do NOT start interactive Jupyter server
