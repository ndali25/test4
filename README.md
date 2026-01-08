# On_the_Expansion_of_Risk_Pooling

## DOCKERFILE GENERATION INSTRUCTIONS

### STEP 1: Base Image Line
```
FROM python:3.11-slim
```
**RULE: Use ONLY python:3.11-slim. Do NOT use jupyter/minimal-notebook.**

### STEP 2: Working Directory Line
```
WORKDIR /app
```
**RULE: Use ONLY /app. Do NOT use /home/jovyan/work.**

### STEP 3: Copy Files Line
```
COPY . /app
```

### STEP 4: Install Packages Line
```
RUN pip install --no-cache-dir notebook pandas openpyxl matplotlib numpy scipy nbconvert
```
**RULE: Install these exact packages: notebook pandas openpyxl matplotlib numpy scipy nbconvert**

### STEP 5: Create Output Directory Line
```
RUN mkdir -p /app/outputs
```

### STEP 6: Execution Command Line
```
CMD ["jupyter", "nbconvert", "--to", "notebook", "--execute", "On_the_Expansion_of_Risk_Pooling__MS__For_final_submission/Code_On_the_Expansion_of_Risk_Pooling.ipynb", "--output", "/app/outputs/executed_notebook.ipynb", "--ExecutePreprocessor.timeout=600"]
```
**RULE: Use jupyter nbconvert with --execute flag. Do NOT use start-notebook.sh**

## COMPLETE DOCKERFILE - COPY EXACTLY
```dockerfile
FROM python:3.11-slim
WORKDIR /app
COPY . /app
RUN pip install --no-cache-dir notebook pandas openpyxl matplotlib numpy scipy nbconvert
RUN mkdir -p /app/outputs
CMD ["jupyter", "nbconvert", "--to", "notebook", "--execute", "On_the_Expansion_of_Risk_Pooling__MS__For_final_submission/Code_On_the_Expansion_of_Risk_Pooling.ipynb", "--output", "/app/outputs/executed_notebook.ipynb", "--ExecutePreprocessor.timeout=600"]
```

## PROHIBITED COMMANDS - DO NOT USE

❌ FROM jupyter/minimal-notebook
❌ WORKDIR /home/jovyan
❌ USER jovyan
❌ EXPOSE 8888
❌ start-notebook.sh
❌ RUN pip install jupyterlab
❌ --NotebookApp.token

## PROJECT INFORMATION

**Project Name**: On_the_Expansion_of_Risk_Pooling
**Authors**: Michail Anthropelos, Runhuan Feng, Seongyoon Kim
**Notebook Path**: On_the_Expansion_of_Risk_Pooling__MS__For_final_submission/Code_On_the_Expansion_of_Risk_Pooling.ipynb
**Execution Mode**: Headless automatic execution
**Container Type**: Non-interactive batch processing

## PACKAGE REQUIREMENTS

Required packages that MUST be installed:
- notebook (for Jupyter infrastructure)
- pandas (data processing)
- openpyxl (Excel file reading)
- matplotlib (plotting)
- numpy (numerical operations)
- scipy (scientific computing)
- nbconvert (notebook execution - CRITICAL)

## EXECUTION SPECIFICATIONS

- **Method**: nbconvert with --execute flag
- **Timeout**: 600 seconds
- **Output Location**: /app/outputs/executed_notebook.ipynb
- **Behavior**: Execute notebook and exit (no server)
- **Ports**: None (headless execution)

## CONTAINER BEHAVIOR

1. Container starts
2. Runs jupyter nbconvert to execute notebook
3. Saves executed notebook to /app/outputs/
4. Container exits automatically
5. No interactive server runs
