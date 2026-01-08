# Project
On_the_Expansion_of_Risk_Pooling

# Authors
Michail Anthropelos, Runhuan Feng, Seongyoon Kim

# Purpose
Automatically execute the main Python notebook and save all outputs.
No Jupyter server or LaTeX compilation.

# Input Notebook
analysis/Code_On_the_Expansion_of_Risk_Pooling.ipynb

# Input Data
analysis/CCRIF_TC.csv
analysis/CCRIF_TC_Info.csv
analysis/Health_data.xlsx

# Output Folder
99_logs/
- executed_notebook.ipynb
- generated figures and tables

# Dockerfile Requirements
- Base image: python:3.11-slim
- Working directory: /app
- Copy all project files into /app
- Install Python packages:
    numpy, pandas, matplotlib, scipy, tqdm, jupyter, nbconvert
- Create folder /app/99_logs
- CMD: Execute the notebook automatically using nbconvert:
    jupyter nbconvert --to notebook --execute analysis/Code_On_the_Expansion_of_Risk_Pooling.ipynb --output executed_notebook.ipynb && mv executed_notebook.ipynb 99_logs/

# Build Docker Image
docker build -t test4-python -f Dockerfile.python .

# Run Container
docker run --rm -v "$(pwd)/99_logs:/app/99_logs" --name rtest4-run test4-python

# Check Outputs
ls 99_logs/
# executed_notebook.ipynb and all figures/tables should be present
