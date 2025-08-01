# Environment Setup with `uv`

This guide explains how to set up your Python environment for the `inference-journey` project using
[`uv`](https://github.com/astral-sh/uv) — a modern, fast Python package manager and environment tool.

---

## Prerequisites

[`mise`](https://github.com/astral-sh/mise) installed to manage Python versions:

```bash
curl -sSfL https://raw.githubusercontent.com/astral-sh/mise/main/install.sh | sh
```

Python 3.12 (recommended) or later installed via `mise`:

```bash
mise install python@3.12
```

---

## Setup Instructions

Clone the repository:

```bash
git clone https://github.com/akrisanov/inference-journey.git
cd inference-journey
```

Use Python 3.12 for the project:

```bash
mise use python@3.12
pip install --upgrade pip
```

Install [`uv`](https://github.com/astral-sh/uv) to manage virtual environments and packages:

```bash
pip install uv
```

Create and activate a virtual environment:

```bash
uv venv
source .venv/bin/activate  # or .venv/Scripts/activate on Windows
```

Install core dependencies:

```bash
uv pip install jupyterlab fastbook
```

If you are using macOS, you may need to install additional *nix dependencies:

```bash
brew install cmake pkg-config coreutils
```

coreutils gives you gnumake, nproc, and other GNU tools. You may need to run:

```bash
echo 'export PATH="/opt/homebrew/opt/coreutils/libexec/gnubin:$PATH"' >> ~/.zshrc
source ~/.zshrc
```

Linux users with no GPU can leverage CPU-only PyTorch installation:

```bash
uv pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cpu
uv pip install fastbook
```

Run the Jupyter Notebook:

```bash
jupyter lab
```

---

## Project Structure (relevant paths)

- `notebooks/`: Jupyter notebooks, including fastbook
- `notes/`: Markdown notes with learnings and theory
- `setup/`: Environment and tooling instructions

---

## Notes

- VS Code will detect the `.venv` automatically if you open the folder
- You can pin dependencies later using:

```bash
uv pip freeze > requirements.txt
```

---

Happy learning!
