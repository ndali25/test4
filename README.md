# On_the_Expansion_of_Risk_Pooling

## Project Metadata
- **Project Name**: On_the_Expansion_of_Risk_Pooling
- **Authors**: Michail Anthropelos, Runhuan Feng, Seongyoon Kim
- **Container Type**: python-headless
- **Execution Mode**: Non-interactive notebook execution

## Docker Configuration

### Base Image
```
python:3.11-slim
```

### Working Directory
```
/app
```

### System Requirements
- Operating System: Linux (Debian-based)
- Python Version: 3.11
- Execution Environment: Headless (no GUI required)

## Dependencies

### Python Packages (Install via pip)
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

## Project Structure

### Input Data Files (Must be copied to container)
```
analysis/CCRIF_TC.csv
analysis/CCRIF_TC_Info.csv
analysis/Health_data.xlsx
```

### Notebook to Execute
```
File: analysis/Code_On_the_Expansion_of_Risk_Pooling.ipynb
Timeout: 600 seconds
```

### Output Configuration
```
Output Notebook Name: executed_notebook.ipynb
Output Directory: /app/99_logs
Create Output Directory: Yes (if not exists)
```

## Build Instructions

1. **Set base image**: Use `python:3.11-slim`
2. **Set working directory**: `WORKDIR /app`
3. **Copy project files**: Copy all files from host to `/app` in container
4. **Install dependencies**: Run `pip install --no-cache-dir numpy pandas matplotlib scipy tqdm jupyter nbconvert openpyxl`
5. **Create log directory**: Create `/app/99_logs` directory with `mkdir -p /app/99_logs`

## Runtime Instructions

### Command to Execute
```bash
jupyter nbconvert --to notebook --execute analysis/Code_On_the_Expansion_of_Risk_Pooling.ipynb --output=/app/99_logs/executed_notebook.ipynb --ExecutePreprocessor.timeout=600
```

### Execution Details
- **Auto-run on container start**: Yes
- **Execution method**: nbconvert with execute flag
- **Timeout**: 600 seconds (10 minutes)
- **Interactive Jupyter**: No (do not start Jupyter server)
- **Output location**: `/app/99_logs/executed_notebook.ipynb`

## Container Behavior
- Container should execute the notebook automatically on startup
- Container should exit after notebook execution completes
- No interactive services should be running
- All output should be saved to `/app/99_logs/`

## Port Exposure
- **None required** (headless execution only)

## Volume Mounts (Optional)
- Suggested mount point for output retrieval: `/app/99_logs`

## Environment Variables
- None required for basic execution
