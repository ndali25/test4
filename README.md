ProjectName: On_the_Expansion_of_Risk_Pooling
Authors: Michail Anthropelos, Runhuan Feng, Seongyoon Kim

ContainerType: python-headless

# Notebook execution
ExecuteNotebook: analysis/Code_On_the_Expansion_of_Risk_Pooling.ipynb
NotebookTimeout: 600
OutputNotebookName: executed_notebook.ipynb

# Input data
DataFiles:
- analysis/CCRIF_TC.csv
- analysis/CCRIF_TC_Info.csv
- analysis/Health_data.xlsx

# Output folder
OutputFolder: /app/99_logs

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

# Instructions for generator
# The Dockerfile should:
# 1. Use python:3.11-slim
# 2. Set WORKDIR to /app
# 3. COPY all files
# 4. Install listed PythonPackages
# 5. Create OutputFolder
# 6. Execute notebook headlessly using nbconvert with NotebookTimeout
# 7. Move executed notebook to OutputFolder
# 8. Do NOT start an interactive Jupyter server
