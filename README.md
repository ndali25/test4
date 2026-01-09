Risk Pooling Analysis - Jupyter Notebook Automation
Project Overview
This project contains the computational analysis for the research paper "On the Expansion of Risk Pooling" by Michail Anthropelos, Runhuan Feng, and Seongyoon Kim. The analysis is implemented in a Jupyter notebook that performs statistical computations and generates visualizations.
Project Structure
On_the_Expansion_of_Risk_Pooling/
├── On_the_Expansion_of_Risk_Pooling__MS__For_final_submission/
│   └── Code_On_the_Expansion_of_Risk_Pooling.ipynb
└── README.md
Requirements
The notebook requires Python 3.11 and depends on the following packages:

pandas - for data manipulation and Excel file processing
openpyxl - required by pandas to read .xlsx files
numpy - for numerical computations
scipy - for statistical analysis
matplotlib - for creating plots and visualizations
notebook - Jupyter notebook environment
nbconvert - for programmatic notebook execution

Execution Requirements
We need to run this notebook in an automated, non-interactive mode as part of a batch processing pipeline. The notebook should execute completely without user intervention, and all outputs (including plots and data) should be saved automatically.
Execution Specifications:

The notebook is located at: On_the_Expansion_of_Risk_Pooling__MS__For_final_submission/Code_On_the_Expansion_of_Risk_Pooling.ipynb
Execution should be headless (no browser interface needed)
The executed notebook with all outputs should be saved to an outputs directory
Some cells may take time to complete, so a timeout of at least 600 seconds per cell is recommended
No interactive Jupyter server should remain running after execution

Deployment Notes
This needs to be containerized for reproducible execution across different environments. The container should:

Start up with Python 3.11
Have all the required packages installed
Execute the notebook automatically when the container runs
Save the executed notebook with all outputs to a dedicated output folder
Exit cleanly after execution completes

We prefer a lightweight Python base image rather than pre-built Jupyter Docker stacks, as we don't need the interactive server components.
Expected Output
After execution, there should be a fully executed notebook file named executed_notebook.ipynb in the outputs directory, containing all computed results and generated plots.
Usage Context
This is intended for:

Reproducible research environments
CI/CD pipeline integration
Automated report generation
Batch processing of the analysis

The container will be run with volume mounting to extract the results to the host machine.
