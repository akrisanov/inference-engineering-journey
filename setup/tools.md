# Developer Tools and Utilities

A curated list of tools and extensions I use in this project.

---

## Core CLI Tools

| Tool           | Purpose                                 | Install Command (macOS)               |
|----------------|------------------------------------------|--------------------------------------|
| `uv`           | Fast package & venv manager              | `pip install uv`                     |
| `mise`         | Python version manager                   | `brew install mise`                  |
| `git`          | Version control                          | `brew install git`                   |
| `lazygit`      | TUI for Git with fast navigation         | `brew install lazygit`               |

---

## Build Dependencies (for C/C++-based Python packages)

| Tool           | Purpose                                  | Install Command                      |
|----------------|------------------------------------------|--------------------------------------|
| `cmake`        | Needed for building C++ packages         | `brew install cmake`                 |
| `pkg-config`   | Config for native builds                 | `brew install pkg-config`            |
| `coreutils`    | Adds `nproc` and GNU tools               | `brew install coreutils`             |

---

## ML and Notebook Tools

| Tool           | Purpose                                  | Notes                                |
|----------------|------------------------------------------|--------------------------------------|
| `fastbook`     | fast.ai course package                   | `uv pip install fastbook`            |
| `jupyterlab`   | Interactive notebooks                    | `uv pip install jupyterlab`          |

---

## 🧩 VS Code Extensions

- Python (Microsoft)
- Jupyter (Microsoft)
- Pylance
- EditorConfig
- GitLens

---

## 💡 Notes

- I use Python 3.12 via `mise` to ensure compatibility with fastbook and sentencepiece
- All tools should be installed in a `.venv` using `uv`
