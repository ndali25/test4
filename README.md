# On_the_Expansion_of_Risk_Pooling

## Project Metadata
- **Project Name**: On_the_Expansion_of_Risk_Pooling
- **Authors**: Michail Anthropelos, Runhuan Feng, Seongyoon Kim

## CRITICAL: Exact Dockerfile Requirements

### MANDATORY Base Image
```
FROM python:3.11-slim
```
**DO NOT use jupyter/minimal-notebook or any other base image**

### MANDATORY Working Directory
```
WORKDIR /app
```
**DO NOT use /home/jovyan/work or any other directory**

### MANDATORY Copy Command
```
COPY . /app
```

### MANDATORY Package Installation
```
RUN pip install --no-cache-dir notebook pandas openpyxl matplotlib numpy scipy
```
**Install exactly these packages in this order: notebook pandas openpyxl matplotlib numpy scipy**

### MANDATORY Port Exposure
```
EXPOSE 8888
```

### MANDATORY Startup Command
```
CMD ["jupyter", "notebook", "On_the_Expansion_of_Risk_Pooling__MS__For_final_submission/Code_On_the_Expansion_of_Risk_Pooling.ipynb", "--ip=0.0.0.0", "--port=8888", "--no-browser", "--allow-root"]
```

## Complete Dockerfile Structure

The Dockerfile MUST follow this EXACT structure:
```dockerfile
FROM python:3.11-slim

WORKDIR /app

COPY . /app

RUN pip install --no-cache-dir notebook pandas openpyxl matplotlib numpy scipy

EXPOSE 8888

CMD ["jupyter", "notebook", "On_the_Expansion_of_Risk_Pooling__MS__For_final_submission/Code_On_the_Expansion_of_Risk_Pooling.ipynb", "--ip=0.0.0.0", "--port=8888", "--no-browser", "--allow-root"]
```

## Forbidden Instructions

**DO NOT:**
- Use jupyter/minimal-notebook as base image
- Use any USER commands
- Use chown or permission commands
- Use start-notebook.sh
- Use /home/jovyan directory
- Change the working directory from /app
- Modify the CMD command format
- Skip any of the required packages

## Required Packages
1. notebook
2. pandas
3. openpyxl
4. matplotlib
5. numpy
6. scipy

## Notebook Path
```
On_the_Expansion_of_Risk_Pooling__MS__For_final_submission/Code_On_the_Expansion_of_Risk_Pooling.ipynb
```

## Execution Configuration
- Port: 8888
- IP: 0.0.0.0
- No browser launch
- Allow root access
- Direct notebook opening
