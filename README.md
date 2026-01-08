Project: On_the_Expansion_of_Risk_Pooling
Authors: Michail Anthropelos, Runhuan Feng, Seongyoon Kim

# Purpose
Automatically execute the main Python notebook and save outputs.
Do not start a Jupyter server.
Do not run LaTeX.
Headless, fully automated.

# Input Notebook
analysis/Code_On_the_Expansion_of_Risk_Pooling.ipynb

# Input Data
analysis/CCRIF_TC.csv
analysis/CCRIF_TC_Info.csv
analysis/Health_data.xlsx

# Output Folder
99_logs/
Contains: executed_notebook.ipynb, generated figures, tables

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
3. Install required Python packages using pip
4. Create folder /app/99_logs
5. CMD: Execute notebook automatically using nbconvert:
   jupyter nbconvert --to notebook --execute analysis/Code_On_the_Expansion_of_Risk_Pooling.ipynb --output executed_notebook.ipynb
   Move executed_notebook.ipynb to /app/99_logs/
6. Do NOT expose ports
7. Do NOT start interactive Jupyter server

# Build Docker Image
docker build -t test4-python -f Dockerfile.python .

# Run Container
docker run --rm -v "$(pwd)/99_logs:/app/99_logs" test4-python

# Check Outputs
ls 99_logs/
# Should contain executed_notebook.ipynb and all figures/tables
