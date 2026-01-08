Project: On_the_Expansion_of_Risk_Pooling
Authors: Michail Anthropelos, Runhuan Feng, Seongyoon Kim

# Purpose
Automatically execute the main Python notebook **headlessly**.
Do NOT start a Jupyter server or browser.

# Notebook
File: analysis/Code_On_the_Expansion_of_Risk_Pooling.ipynb

# Data
Files:
- analysis/CCRIF_TC.csv
- analysis/CCRIF_TC_Info.csv
- analysis/Health_data.xlsx

# Output
Folder: 99_logs/
Contains executed_notebook.ipynb, generated figures and tables.

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

# Execution Instructions
1. WORKDIR /app
2. COPY all project files into /app
3. Install Python dependencies
4. Create /app/99_logs folder
5. Run the notebook **headlessly**:
   `jupyter nbconvert --to notebook --execute analysis/Code_On_the_Expansion_of_Risk_Pooling.ipynb --output executed_notebook.ipynb --ExecutePreprocessor.timeout=600`
6. Move executed_notebook.ipynb to /app/99_logs/
7. Do NOT expose ports
8. Do NOT start interactive notebook server
