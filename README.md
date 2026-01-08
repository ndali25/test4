# On_the_Expansion_of_Risk_Pooling

## Project Metadata
- **Project Name**: On_the_Expansion_of_Risk_Pooling
- **Authors**: Michail Anthropelos, Runhuan Feng, Seongyoon Kim
- **Execution Type**: Automatic Headless Execution

## CRITICAL: Dockerfile Must Auto-Execute Notebook

This container must AUTOMATICALLY EXECUTE the Jupyter notebook on startup and then exit.
**DO NOT start an interactive Jupyter server.**

## MANDATORY Dockerfile Structure

### Base Image
```
FROM python:3.11-slim
```

### Working Directory
```
WORKDIR /app
```

### Copy All Files
```
COPY . /app
```

### Install ALL Required Packages
```
RUN pip install --no-cache-dir notebook pandas openpyxl matplotlib numpy scipy nbconvert
```

**CRITICAL: Must install nbconvert for headless execution**

### Create Output Directory
```
RUN mkdir -p /app/outputs
```

### Automatic Execution Command
```
CMD ["jupyter", "nbconvert", "--to", "notebook", "--execute", "On_the_Expansion_of_Risk_Pooling__MS__For_final_submission/Code_On_the_Expansion_of_Risk_Pooling.ipynb", "--output", "/app/outputs/executed_notebook.ipynb", "--ExecutePreprocessor.timeout=600"]
```

## Complete Dockerfile (EXACT FORMAT REQUIRED)
```dockerfile
FROM python:3.11-slim

WORKDIR /app

COPY . /app

RUN pip install --no-cache-dir notebook pandas openpyxl matplotlib numpy scipy nbconvert

RUN mkdir -p /app/outputs

CMD ["jupyter", "nbconvert", "--to", "notebook", "--execute", "On_the_Expansion_of_Risk_Pooling__MS__For_final_submission/Code_On_the_Expansion_of_Risk_Pooling.ipynb", "--output", "/app/outputs/executed_notebook.ipynb", "--ExecutePreprocessor.timeout=600"]
```

## Required Python Packages
1. notebook - Jupyter notebook infrastructure
2. pandas - Data manipulation
3. openpyxl - Excel file support
4. matplotlib - Plotting
5. numpy - Numerical computing
6. scipy - Scientific computing
7. nbconvert - **CRITICAL for headless notebook execution**

## Input Notebook
```
On_the_Expansion_of_Risk_Pooling__MS__For_final_submission/Code_On_the_Expansion_of_Risk_Pooling.ipynb
```

## Output Configuration
- **Output Directory**: /app/outputs
- **Output File**: executed_notebook.ipynb
- **Execution Timeout**: 600 seconds

## Execution Behavior
1. Container starts
2. Automatically executes the notebook using nbconvert
3. Saves executed notebook with all outputs to /app/outputs/
4. Container exits after completion

## Forbidden Elements

**DO NOT include:**
- EXPOSE directives (no ports needed)
- Interactive Jupyter server commands
- `jupyter notebook` command (use `jupyter nbconvert` instead)
- USER or permission commands
- start-notebook.sh scripts

## How to Run

**Build:**
```bash
docker build -t risk-pooling-exec .
```

**Run (outputs will be in container):**
```bash
docker run --name risk-pooling-run risk-pooling-exec
```

**Copy outputs to host:**
```bash
docker cp risk-pooling-run:/app/outputs/executed_notebook.ipynb ./
```

**Or run with volume mount:**
```bash
docker run -v $(pwd)/outputs:/app/outputs risk-pooling-exec
```
