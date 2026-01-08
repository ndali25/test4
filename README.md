ProjectName: On_the_Expansion_of_Risk_Pooling
Authors: Michail Anthropelos, Runhuan Feng, Seongyoon Kim

ContainerType: python-headless

# Notebook execution
ExecuteNotebook:
  File: analysis/Code_On_the_Expansion_of_Risk_Pooling.ipynb
  Timeout: 600
  OutputNotebook: executed_notebook.ipynb
  OutputFolder: /app/99_logs
  AutoRun: true

# Python packages to install
PythonPackages:
  - numpy
  - pandas
  - matplotlib
  - scipy
  - tqdm
  - jupyter
  - nbconvert
  - openpyxl

# Input data
DataFiles:
  - analysis/CCRIF_TC.csv
  - analysis/CCRIF_TC_Info.csv
  - analysis/Health_data.xlsx

# Instructions for AI Dockerfile generator
# 1. Use base image: python:3.11-slim
# 2. Set WORKDIR to /app
# 3. COPY all project files to /app
# 4. Install listed PythonPackages
# 5. Create OutputFolder if it does not exist
# 6. Run the notebook headlessly using nbconvert with Timeout
# 7. Save executed notebook to OutputFolder
# 8. Do NOT start interactive Jupyter server
