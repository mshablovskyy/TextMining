# TextMining

## Set up the project

Install [uv](https://docs.astral.sh/uv/getting-started/installation/) and the Python and Jupyter extensions in VS Code. From this repository's root, run:

```bash
uv sync
```

This creates or syncs the project's `.venv` using `pyproject.toml` and `uv.lock`.

## Connect the notebook kernel in VS Code

Open `text_mining.ipynb` and choose **Select Kernel**. If the project environment is missing from the picker, open a terminal at this repository's root and register it:

```bash
uv run python -m ipykernel install --user --name textmining --display-name "Python (TextMining)"
```

Then choose **Select Kernel → Select Another Kernel → Jupyter Kernels → Python (TextMining)**. This kernel uses this repository's `.venv`.

## uv quick reference

Run these commands from the repository root:

| Task | Command |
|---|---|
| Add a dependency | `uv add PACKAGE` |
| Remove a dependency | `uv remove PACKAGE` |
| Sync the environment from the project files | `uv sync` |
| Run a Python script | `uv run python main.py` |
| Upgrade one dependency | `uv lock --upgrade-package PACKAGE`, then `uv sync` |

`uv add` and `uv remove` update `pyproject.toml`, `uv.lock`, and the environment. Commit `pyproject.toml`, `uv.lock`, `.python-version`, `.gitignore`, notebooks, and project data. Do not commit `.venv`.
