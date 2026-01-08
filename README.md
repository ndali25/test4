# On_the_Expansion_of_Risk_Pooling

## Project Metadata
- **Project Name**: On_the_Expansion_of_Risk_Pooling
- **Authors**: Michail Anthropelos, Runhuan Feng, Seongyoon Kim
- **Container Type**: python-headless-autoexec
- **Execution Mode**: Automatic notebook execution on container start (NO INTERACTIVE SERVER)

## Docker Configuration

### Base Image
```
python:3.11-slim
```

### Working Directory
```
/app
```

## Dependencies

### CRITICAL: Install ALL Python Packages
```
numpy
pandas
matplotlib
scipy
tqdm
jupyter
nbconvert
openpyxl
```

**Installation Command**: `pip install --no-cache-dir numpy pandas matplotlib scipy tqdm jupyter nbconvert openpyxl`

## Project Files to Copy

### COPY ALL files from project root to /app
```
COPY . /app
```

### Required Input Files (must exist in container)
```
analysis/CCRIF_TC.csv
analysis/CCRIF_TC_Info.csv
analysis/Health_data.xlsx
analysis/Code_On_the_Expansion_of_Risk_Pooling.ipynb
```

## Build Steps (RUN commands)

### Step 1: Install all Python packages
```bash
RUN pip install --no-cache-dir numpy pandas matplotlib scipy tqdm jupyter nbconvert openpyxl
```

### Step 2: Create output directory
```bash
RUN mkdir -p /app/99_logs
```

## Runtime Configuration

### DO NOT EXPOSE ANY PORTS
**No EXPOSE directive required** - This is headless execution, not a Jupyter server

### DO NOT START JUPYTER SERVER
**CRITICAL**: Do not use `jupyter notebook` command

### CMD Directive (Container Entry Point)
**Use this exact command to auto-execute the notebook on container start:**
```bash
CMD ["jupyter", "nbconvert", "--to", "notebook", "--execute", "analysis/Code_On_the_Expansion_of_Risk_Pooling.ipynb", "--output", "/app/99_logs/executed_notebook.ipynb", "--ExecutePreprocessor.timeout=600"]
```

## Execution Specifications
- **Execution Method**: nbconvert with --execute flag
- **Input Notebook**: analysis/Code_On_the_Expansion_of_Risk_Pooling.ipynb
- **Output Notebook**: /app/99_logs/executed_notebook.ipynb
- **Timeout**: 600 seconds
- **Auto-Run**: YES - executes immediately when container starts
- **Interactive Mode**: NO - container exits after execution completes

## CRITICAL INSTRUCTIONS FOR DOCKERFILE GENERATION

**MUST DO:**
1. Use `python:3.11-slim` as base image
2. Set WORKDIR to `/app`
3. COPY all project files to `/app`
4. RUN `pip install` with ALL packages: numpy pandas matplotlib scipy tqdm jupyter nbconvert openpyxl
5. RUN `mkdir -p /app/99_logs` to create output directory
6. Use CMD with `jupyter nbconvert --to notebook --execute` to run notebook
7. Set timeout to 600 seconds in nbconvert command
8. Output to `/app/99_logs/executed_notebook.ipynb`

**MUST NOT DO:**
1. DO NOT use EXPOSE directive
2. DO NOT start Jupyter server with `jupyter notebook`
3. DO NOT use interactive mode
4. DO NOT forget any Python packages (especially scipy, tqdm, nbconvert)
5. DO NOT use port 8888 or any port

## Expected Container Behavior
1. Container starts
2. Automatically executes notebook using nbconvert
3. Saves executed notebook to /app/99_logs/
4. Container exits after completion
