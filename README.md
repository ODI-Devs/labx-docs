# LabX Docs

[![Python](https://img.shields.io/badge/python-3.7%2B-blue)](https://www.python.org/)
[![MkDocs](https://img.shields.io/badge/mkdocs-latest-green)](https://www.mkdocs.org/)
[![Material](https://img.shields.io/badge/theme-material-blueviolet)](https://squidfunk.github.io/mkdocs-material/)

Documentation site powered by [MkDocs](https://www.mkdocs.org/) and the [Material theme](https://squidfunk.github.io/mkdocs-material/).

---

## Prerequisites

- **Python 3.7 or higher** installed and accessible via `python` command  
- Basic familiarity with command line / terminal  
- (Optional but recommended) Git installed  
- (Optional) SSH key setup if you want to clone via SSH

---

## Quick Start

### 1. Clone the repository

```bash
git clone https://github.com/ODI-Devs/labx-docs.git
cd labx-docs
```

Or using SSH:
```bash
git clone git@github.com:ODI-Devs/labx-docs.git
cd labx-docs
```



### 2. Setup & activate virtual environment (recommended)
```py
python -m venv venv
```
#### Activate Virtual Environment
- **macOS/Linux:**
```py
source venv/bin/activate
```

- **Windows PowerShell/CMD**
```py
.\venv\Scripts\Activate.ps1
```

Note: If you get an execution policy error on Windows, run PowerShell as admin and execute:
```py
Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass
```

### 3. Install dependencies
```py
pip install mkdocs mkdocs-material
```

Check Installation
```py
pip install mkdocs mkdocs-material
```


### 4. Serve the site locally
Start the MkDocs development server:
```py
mkdocs serve
```
You should see output like:
```py
Serving on http://127.0.0.1:8000/
```


### 5. Project Structure 
labx-docs/
```bash
├── docs/
│   ├── index.md
│   └── other-pages.md
├── mkdocs.yml
```
- docs/: contains Markdown files
- mkdocs.yml: the main configuration file

## LabX Team
[![Project_Manager](https://img.shields.io/badge/John_Matthew_Dino-Project_Manager-blue)]()
[![System Analyst](https://img.shields.io/badge/Josiah_Viernes-System_Analyst-red)]()
[![UI/UX Designer](https://img.shields.io/badge/Armbel_Bernal-UI/UX_Designer-green)]()
[![UI/UX Designer](https://img.shields.io/badge/Jane_Maqui_Segismundo-UI/UX_Designer-green)]()
[![Front End](https://img.shields.io/badge/Rusty_Gunao-Front_End-cyan)]()
[![Front End](https://img.shields.io/badge/Prince_Jules_Corea-Front_End_Dev-cyan)]()
[![Back End](https://img.shields.io/badge/Justine_Lenard_Sabawil-Back_End_Dev-orange)]()
[![Back End](https://img.shields.io/badge/Rolly_Gilos-Back_End_Dev-orange)]()


























