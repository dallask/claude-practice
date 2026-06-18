# Prerequisites

Before working with this repo, ensure the following software is installed:

---

## Node.js

- **Version**: 18 or higher
- **Official docs**: [https://nodejs.org/en/download](https://nodejs.org/en/download)

**macOS**
```bash
# Option 1: Homebrew
brew install node

# Option 2: nvm (Node Version Manager) — recommended for managing multiple versions
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash
nvm install --lts
```

**Windows**
```powershell
# Option 1: winget
winget install OpenJS.NodeJS.LTS

# Option 2: nvm-windows — recommended for managing multiple versions
# Download installer from https://github.com/coreybutler/nvm-windows/releases
nvm install lts
nvm use lts
```

- **Verify**: `node --version` and `npm --version`

---

## Python

- **Version**: 3.10 or higher
- **Official docs**: [https://www.python.org/downloads](https://www.python.org/downloads)

**macOS**
```bash
# Option 1: Homebrew
brew install python

# Option 2: pyenv — recommended for managing multiple versions
brew install pyenv
pyenv install 3.12
pyenv global 3.12
```

**Windows**
```powershell
# Option 1: winget
winget install Python.Python.3.12

# Option 2: Microsoft Store — search "Python 3.12"

# Option 3: pyenv-win — for managing multiple versions
# https://github.com/pyenv-win/pyenv-win#installation
```

- **Verify**: `python3 --version` (macOS/Linux) or `python --version` (Windows)

---

## uv (Python package manager)

`uv` is a fast Python package and project manager used to manage backend dependencies and virtual environments.

### 1.Installation guide
**Official docs**: [https://docs.astral.sh/uv/getting-started/installation](https://docs.astral.sh/uv/getting-started/installation)

**macOS / Linux**
```bash
# Standalone installer
curl -LsSf https://astral.sh/uv/install.sh | sh

# Or via Homebrew
brew install uv
```

**Windows**
```powershell
# Standalone installer (PowerShell)
powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"

# Or via winget
winget install astral-sh.uv
```

### **Verify**
1. run command  `uv --version`
2. expected result:

```pwsh
❯ uv --version 
uv 0.11.21 (Homebrew 2026-06-11 aarch64-apple-darwin)
```

### Prepare & Activate .venv

1. Create python environment `uv venv`
2. Check you repo folder structure, which should have  `.env` folder
3. [optional] Update env name
   1. Open .venv/pyvenv.cfg
   2. Update prompt = <your_env_name> (will be shown in terminal after env is activated)
4. Activate env:
MacOs: `source .venv/bin/activate`
Windows (PowerShell): `.venv\Scripts\Activate.ps1`
5. Install Dependencies: `uv sync`
---

## Git

- **Official docs**: [https://git-scm.com/downloads](https://git-scm.com/downloads)

**macOS**
```bash
# Option 1: Xcode Command Line Tools (usually pre-installed)
git --version  # triggers install prompt if missing

# Option 2: Homebrew
brew install git
```

**Windows**
```powershell
# Option 1: winget
winget install Git.Git

# Option 2: Download installer from https://git-scm.com/download/win
# Includes Git Bash and Git GUI
```

- **Verify**: `git --version`

---

## VS Code + Jupyter Notebook

VS Code is the recommended editor. The Jupyter extension enables running `.ipynb` notebooks directly inside VS Code.

- **VS Code official docs**: [https://code.visualstudio.com/download](https://code.visualstudio.com/download)
- **Jupyter extension**: [https://marketplace.visualstudio.com/items?itemName=ms-toolsai.jupyter](https://marketplace.visualstudio.com/items?itemName=ms-toolsai.jupyter)

### 1. Install VS Code

**macOS**
```bash
# Option 1: Homebrew
brew install --cask visual-studio-code

# Option 2: Download .dmg from https://code.visualstudio.com/download
```

**Windows**
```powershell
# Option 1: winget
winget install Microsoft.VisualStudioCode

# Option 2: Download installer from https://code.visualstudio.com/download
```

### 2. Install the Jupyter Extension

Open VS Code, then install via the Extensions panel (`Ctrl+Shift+X` / `Cmd+Shift+X`) or run in the terminal:

```bash
code --install-extension ms-toolsai.jupyter
```

### 3. Select the Python Kernel

When opening a `.ipynb` file, click **Select Kernel** in the top-right corner and choose the `.venv` interpreter created during the uv setup step.

- **Verify**: Open any `.ipynb` file — VS Code should prompt to select a kernel without errors.

---

## Claude Code (CLI)

Claude Code is the AI-powered CLI used throughout this course.

- **Official docs**: [https://docs.anthropic.com/en/claude-code/overview](https://docs.anthropic.com/en/claude-code/overview)
- **Installation guide**: [https://docs.anthropic.com/en/claude-code/getting-started](https://docs.anthropic.com/en/claude-code/getting-started)

**macOS / Windows / Linux** (requires Node.js 18+)
```bash
npm install -g @anthropic-ai/claude-code
```

- **Verify**: `claude --version`
