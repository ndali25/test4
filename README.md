Risk Pooling Analysis - Automated Execution
About
Jupyter notebook for "On the Expansion of Risk Pooling" research paper.
Notebook path: On_the_Expansion_of_Risk_Pooling__MS__For_final_submission/Code_On_the_Expansion_of_Risk_Pooling.ipynb
Requirements
Python 3.11 with these packages:
notebook pandas openpyxl matplotlib numpy scipy nbconvert
Important: Batch Execution Only
This notebook must run in batch mode, not as an interactive server.
Use nbconvert to execute the notebook:
bashjupyter nbconvert --to notebook --execute On_the_Expansion_of_Risk_Pooling__MS__For_final_submission/Code_On_the_Expansion_of_Risk_Pooling.ipynb --output /app/outputs/executed_notebook.ipynb --ExecutePreprocessor.timeout=600
Do not use: jupyter notebook, jupyter lab, or start-notebook.sh - these start servers, we need batch execution.
Dockerfile Requirements

Base image: python:3.11-slim
Working directory: /app
Copy files to /app
Install packages: pip install --no-cache-dir notebook pandas openpyxl matplotlib numpy scipy nbconvert
Create output directory: mkdir -p /app/outputs
Command: Use the jupyter nbconvert --execute command shown above

Do not:

Use jupyter/* Docker images
Expose port 8888
Start a Jupyter server
Use start-notebook.sh

Result
Container executes the notebook and exits. Output saved to /app/outputs/executed_notebook.ipynb.
