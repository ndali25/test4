Risk Pooling Analysis - Interactive Jupyter Notebook
Project Overview
Research notebook for "On the Expansion of Risk Pooling" by Michail Anthropelos, Runhuan Feng, and Seongyoon Kim.
Notebook location: On_the_Expansion_of_Risk_Pooling__MS__For_final_submission/Code_On_the_Expansion_of_Risk_Pooling.ipynb
Requirements

Python 3.11
Jupyter notebook server
Required packages: pandas, openpyxl, matplotlib, numpy, scipy, notebook

Docker Setup
We need an interactive Jupyter notebook environment accessible via web browser.
Configuration
Base image: Use jupyter/scipy-notebook:python-3.11 or similar Jupyter Docker stack
Working directory: /home/jovyan/work
Port: Expose port 8888 for Jupyter server
Packages: Install additional packages if needed:
bashpip install openpyxl
Startup
Start the Jupyter notebook server with:

No authentication token (for easy access)
Listen on all interfaces (0.0.0.0)
Allow root if needed

Use start-notebook.sh or jupyter notebook command.
Running the Container
Build:
bashdocker build -t risk-pooling .
Run:
bashdocker run -p 8888:8888 -v $(pwd):/home/jovyan/work risk-pooling
Access Jupyter at: http://localhost:8888
Usage

Start the container
Open your browser to http://localhost:8888
Navigate to the notebook file
Run cells interactively

The container should keep running so you can work with the notebook through your browser.
