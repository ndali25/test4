# On_the_Expansion_of_Risk_Pooling

## Project Metadata
- **Project Name**: On_the_Expansion_of_Risk_Pooling
- **Authors**: Michail Anthropelos, Runhuan Feng, Seongyoon Kim
- **Container Type**: python-jupyter
- **Execution Mode**: Interactive Jupyter notebook server

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

### Python Packages (Install via pip)
```
notebook
pandas
openpyxl
matplotlib
numpy
scipy
```

**Installation Command**: `pip install --no-cache-dir notebook pandas openpyxl matplotlib numpy scipy`

## Project Files

### Copy all project files
```
COPY . /app
```

### Main Notebook File
```
On_the_Expansion_of_Risk_Pooling__MS__For_final_submission/Code_On_the_Expansion_of_Risk_Pooling.ipynb
```

## Runtime Configuration

### Port Exposure
```
EXPOSE 8888
```

### Startup Command
```bash
CMD ["jupyter", "notebook", "On_the_Expansion_of_Risk_Pooling__MS__For_final_submission/Code_On_the_Expansion_of_Risk_Pooling.ipynb", "--ip=0.0.0.0", "--port=8888", "--no-browser", "--allow-root"]
```

## Build Instructions for AI

1. Use base image: `python:3.11-slim`
2. Set WORKDIR to `/app`
3. COPY all project files to `/app`
4. Install Python packages: `notebook pandas openpyxl matplotlib numpy scipy`
5. EXPOSE port 8888
6. Set CMD to start Jupyter notebook server with the specific notebook file

## Running the Container

**Build the image:**
```bash
docker build -t risk-pooling .
```

**Run the container with port mapping:**
```bash
docker run -p 8888:8888 risk-pooling
```

**Access Jupyter in browser:**
```
http://localhost:8888/tree?token=<token-from-console>
```

## Execution Details
- **Server Type**: Jupyter Notebook
- **Port**: 8888 (must be mapped with -p 8888:8888)
- **IP Binding**: 0.0.0.0 (accessible from outside container)
- **Browser**: Disabled (--no-browser)
- **Root Access**: Allowed (--allow-root)
- **Direct Notebook**: Opens specific notebook file on startup
