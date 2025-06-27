# Langchain for LLM Application Development



## Setup Instructions

### Creating a Python Virtual Environment

A virtual environment allows you to install packages in an isolated environment without affecting your system Python installation.

### Using `venv`

1. **Create the virtual environment:**

   ```powershell
   python -m venv venv
   ```

2. **Activate the virtual environment:**

   **On Windows (PowerShell):**

   ```powershell
   .\venv\Scripts\Activate.ps1
   ```

   **On Windows (Command Prompt):**

   ```cmd
   .\venv\Scripts\activate.bat
   ```

   **On macOS/Linux:**

   ```bash
   source venv/bin/activate
   ```

3. **Verify activation:**

   ```powershell
   python --version
   pip list
   ```

   You should see `(venv)` at the beginning of your command prompt when activated.

### Installing Dependencies

After activating your virtual environment, install the required packages:

```powershell
pip install -r requirements.txt
```

The installation can appear to be stuck but it actually works in the background. This is a common issue with pip installations, especially when installing large packages like TensorFlow. The installation is likely still progressing. TensorFlow and PyTorch are very large packages (hundreds of MB), so it can take several minutes. Let it run for at least 10-15 minutes.

You can use verbose output to see progress:

```powershell
pip install -r requirements.txt --verbose
```

When `requirements.txt` is updated to include new versions of the package, you can run the following to reinstall them:

```powershell
pip install -r requirements.txt --upgrade
```

### Checking Package Installation

To verify that packages are installed correctly in your virtual environment:

#### Method 1: Check specific package version

```powershell
jupyter --version
python -c "import numpy; print('NumPy version:', numpy.__version__)"
python -c "import langchain; print('LangChain version:', langchain.__version__)"
```

#### Method 2: Check using pip

```powershell
pip show jupyter
pip show numpy
pip show langchain
```

#### Method 3: List all installed packages

```powershell
pip list
```

#### Method 4: Check if package can be imported

```powershell
python -c "import jupyter; print('Jupyter is installed')"
python -c "import langchain; print('LangChain is installed')"
```

**Important:** Always make sure your virtual environment is activated (you should see `(venv)` in your prompt) before checking package installation.

### Deactivating the Virtual Environment

When you're done working, deactivate the virtual environment:

```powershell
deactivate
```

### Managing Dependencies

**Create a requirements.txt file:**

```powershell
pip freeze > requirements.txt
```

**Install from requirements.txt:**

```powershell
pip install -r requirements.txt
```

### Project Structure

```text
langchain_for_llm_app_dev/
├── 01_model_prompts_parsers/
│   └── L1-Model_prompt_parser.ipynb
├── venv/                    # Virtual environment directory
├── requirements.txt         # Package dependencies
└── README.md               # This file
```

### Troubleshooting

**If you get a PowerShell execution policy error:**

```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
```

**If the virtual environment activation fails:**

- Make sure you're in the correct directory
- Try using the full path to the activation script
- Check that the venv directory was created successfully

**If packages are not found:**

- Ensure your virtual environment is activated (look for `(venv)` in your prompt)
- Try reinstalling the package: `pip install --force-reinstall package_name`
- Check if the package is in your requirements.txt file

**To remove and recreate the virtual environment:**

```powershell
Remove-Item -Recurse -Force venv
python -m venv venv
```
