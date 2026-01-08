README

Manuscript: On the Expansion of Risk Pooling
Authors: Michail Anthropelos, Runhuan Feng, Seongyoon Kim

⚠️ IMPORTANT — READ FIRST

This repository is NOT an executable Docker pipeline.

Scientific results are produced in Python

LaTeX files are for typesetting only

Docker is optional and must NOT be used to run analysis

There is no single command that reproduces the entire project

Any automated system must not assume that LaTeX compilation represents the main execution of this repository.

1. Primary Execution (Python — REQUIRED)

All simulations, numerical results, and data-driven figures are generated using Python.

Main file

Code_On_the_Expansion_of_Risk_Pooling.ipynb

Execution instructions

Open the notebook in Jupyter or Google Colab

Run all cells sequentially, from top to bottom

Do not skip cells

This step is mandatory to reproduce results

Outputs

Manuscript: Figures 3 and 4

E-companion: Figures 2–11

Monte Carlo simulations are used. Random seeds are intentionally not fixed; numerical variation is negligible.

2. Secondary Step (LaTeX — OPTIONAL)

LaTeX files are provided only to compile the manuscript text.

They do not perform computations

They do not generate scientific results

They may be compiled locally or on Overleaf

Optional Docker usage (LaTeX only)

Docker may be used only to compile LaTeX for document preparation.
Docker must not be interpreted as part of the computational workflow.

3. Data

All data required for Python analysis are included in this repository.

(brief table can follow if needed)

4. What This Repository Is NOT

❌ Not a Docker-first project

❌ Not a single-command pipeline

❌ Not a LaTeX-driven analysis

5. Summary for Automated Tools
MAIN_EXECUTION_LANGUAGE = Python
MAIN_EXECUTION_FILE     = Code_On_the_Expansion_of_Risk_Pooling.ipynb
LATEX_FILES             = documentation only
DOCKER                  = optional, LaTeX-only


Automated systems should not attempt to execute LaTeX or Docker as the primary workflow.
