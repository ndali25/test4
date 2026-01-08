Project: On_the_Expansion_of_Risk_Pooling
Authors: Michail Anthropelos, Runhuan Feng, Seongyoon Kim

# Purpose
Automatically execute the main Python notebook **headlessly** and save outputs.
Do NOT start a Jupyter server or open any browser.

# Input Notebook
analysis/Code_On_the_Expansion_of_Risk_Pooling.ipynb

# Input Data
analysis/CCRIF_TC.csv
analysis/CCRIF_TC_Info.csv
analysis/Health_data.xlsx

# Output Folder
99_logs/
Contains: executed_notebook.ipynb, figures, tables

# Python Environment
Base image: python:3.11-slim
Required packages:
- numpy
- pandas
- matplotlib
- scipy
- tqdm
- jupyter
- nbconvert
- openpyxl

# Dockerfile Instructions
1. WORKDIR /app
2. COPY all files into /app
3. Install all required Python packages
4. Create /app/99_logs folder
5. CMD: **headless execution only**:
   `jupyter nbconvert --to notebook --execute analysis/Code_On_the_Expansion_of_Risk_Pooling.ipynb --output executed_notebook.ipynb --ExecutePreprocessor.timeout=600`
   Move `executed_notebook.ipynb` to `/app/99_logs/`
6. Do NOT expose ports
7. Do NOT start interactive server
