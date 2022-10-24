# py-poetry-pre-commit-template
Template for Python code using poetry and pre-commit.


<!-- buttons -->
[![python](https://img.shields.io/badge/python-v3-brightgreen.svg)](https://www.python.org/)
[![Code style: black](https://img.shields.io/badge/code%20style-black-000000.svg)](https://github.com/psf/black)
[![Imports: isort](https://img.shields.io/badge/%20imports-isort-%231674b1?style=flat&labelColor=ef8336)](https://pycqa.github.io/isort/)

## Project structure
```bash
.
├── folder                  # sample folder
│   └── file                # sample file
├── .flake8                 # `flake8` Python style enforcement config file
├── .gitignore              # ignore files that cannot be committed to Git
├── .pre-commit-config.yaml # `pre-commit` hook config file
├── poetry.lock             # lock versions of dependencies managed by poetry
├── pyproject.toml          # build system dependencies
└── README.md               # this file
```

## Environment Setup

### Installing dependencies via Poetry

[`poetry`](https://python-poetry.org/) is a Python packaging and dependency management tool. If you don't already have `poetry`:
```bash
pip install poetry
```

Then install dependencies via `poetry`:
```bash
poetry install
```
*(Note: The remaining commands assume you are in a poetry shell. If you aren't, follow the instructions in the section [Activating the virtual environment](#activating-the-virtual-environment).)*

### Activating the virtual environment

Follow the steps below to [set the interpreter for the project](https://code.visualstudio.com/docs/python/environments#_manually-specify-an-interpreter) in VSCode. This enables the IDE to read Python scripts and Jupyter notebooks.

*(Note: This is a one-time process and need not be repeated afterwards.)*

Create a poetry shell in the project directory:
```bash
poetry shell
```

It should print the path of the `poetry` shell in the format below (I use Python 3.8.10 on Windows 11):
```
Spawning shell within C:\Users\user\AppData\Local\pypoetry\Cache\virtualenvs\{{path depending on project name and python version}}
```

Restart VSCode and open a Jupyter notebook. Click the interpreter.
<!-- ![interpreter_config_1.png](assets/interpreter_config_1.jpg) -->

Choose the path generated above, and the configuration is done.
<!-- ![interpreter_config_2.png](assets/interpreter_config_2.jpg) -->

Exit/deactivate (if needed):
```bash
exit
```

### Pre-commit Hook

After setting up `poetry`, install the `pre-commit` hook:
```bash
pre-commit install
```

You can optionally run the pre-commit hook manually:
```bash
pre-commit run --all-files
```

### Code Style

This project uses:
- [`black`](https://black.readthedocs.io/en/stable/) for Python formatting
- [`flake8`](https://flake8.pycqa.org/en/latest/) for Python code style
- [`isort`](https://pycqa.github.io/isort/) for sorting imports
