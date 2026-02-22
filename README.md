# Lab 1 - MLOps (IE-7374)

This lab covers setting up a Python project with virtual environments, GitHub version control, unit testing, and CI/CD using GitHub Actions.

## Project Structure
```
github_lab1/
├── src/              # Source code
│   └── calculator.py # Calculator functions (fun1-fun5)
├── test/             # Test files
│   ├── test_pytest.py
│   └── test_unittest.py
├── data/             # Data folder
├── .github/
│   └── workflows/    # GitHub Actions
│       ├── pytest_action.yml
│       └── unittest_action.yml
├── requirements.txt
└── .gitignore
```

## What This Lab Does
Implements a simple calculator with 5 functions:
- `fun1(x, y)` — Addition
- `fun2(x, y)` — Subtraction
- `fun3(x, y)` — Multiplication
- `fun4(x, y, z)` — Adds three numbers
- `fun5(x, y)` — Division (raises `ValueError` if y is 0)

## How to Run Locally

**1. Clone the repo**
```bash
git clone <repo_url>
cd github_lab1
```

**2. Create and activate virtual environment**
```bash
python -m venv github_lab1_env
source github_lab1_env/Scripts/activate  # Git Bash
```

**3. Install dependencies**
```bash
pip install -r requirements.txt
```

**4. Run tests**
```bash
# Pytest
pytest

# Unittest
python -m unittest test.test_unittest
```

## GitHub Actions
Two workflows run automatically on every push to `main`:
- **pytest_action.yml** — runs pytest and uploads XML report as artifact
- **unittest_action.yml** — runs unittest suite