Risk Pooling Analysis Project
Overview
This is a Jupyter notebook that runs statistical analysis for our research paper "On the Expansion of Risk Pooling" by Michail Anthropelos, Runhuan Feng, and Seongyoon Kim.
What We Need
We need to run this notebook automatically in Docker - not interactively. The notebook should execute all cells and save the results, then the container should stop. We don't need a Jupyter web interface.
Technical Requirements
Python version: 3.11
Required packages:

notebook
pandas
openpyxl
matplotlib
numpy
scipy
nbconvert

Notebook location: On_the_Expansion_of_Risk_Pooling__MS__For_final_submission/Code_On_the_Expansion_of_Risk_Pooling.ipynb
How to Execute the Notebook
Don't start a Jupyter server. Instead, use nbconvert to execute the notebook in batch mode:
bashjupyter nbconvert --to notebook --execute <notebook_path> --output /app/outputs/executed_notebook.ipynb --ExecutePreprocessor.timeout=600
This runs all cells and saves the executed notebook with outputs.
Docker Setup

Use a standard Python base image like python:3.11-slim (not the jupyter/* Docker images)
Set working directory to /app
Copy files to /app
Create an /app/outputs directory
Install the packages with pip
Run the nbconvert command above (not jupyter notebook or start-notebook.sh)

Don't expose port 8888 - we're not running a server.
Expected Behavior
When you run the container, it should:

Execute the notebook automatically
Save results to /app/outputs/executed_notebook.ipynb
Exit
