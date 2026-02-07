# CLAUDE.md

## Project Overview

This repository contains an educational Jupyter notebook (`admission.ipynb`) that teaches machine learning concepts, specifically **perceptron algorithms** applied to college admission data. It was developed in Google Colab and uses Python 2.

## Repository Structure

```
/
├── admission.ipynb   # Main notebook: perceptron tutorial with visualizations
├── Blah.txt          # Placeholder text file
└── CLAUDE.md         # This file
```

There is no module separation — all code lives in a single notebook organized as 25 sequential cells (10 markdown, 15 code).

## Tech Stack

- **Language:** Python 2 (kernel specification)
- **Environment:** Jupyter Notebook / Google Colab
- **Key libraries:** pandas, numpy, matplotlib

## How to Run

**Option A — Google Colab (recommended):**
Upload `admission.ipynb` to Colab and run all cells sequentially.

**Option B — Local Jupyter:**
```bash
pip install jupyter pandas numpy matplotlib
jupyter notebook admission.ipynb
```

Cells must be executed in order; later cells depend on variables and functions defined in earlier ones.

## External Data

The notebook loads admission data from a remote CSV:
```
https://raw.githubusercontent.com/hackintoshrao/blog-posts/master/Neural%20Nets/Building%20Neural%20Nets%20From%20Scratch/Part%201/code/admission_data.csv
```
An internet connection is required at runtime.

## Notebook Organization

The notebook follows a teaching progression:

1. **Data loading** — Read admission CSV into a pandas DataFrame
2. **Exploration** — Scatter plot visualization of test scores vs. grades
3. **AND gate demo** — Introduce perceptron concept with a simple logic gate
4. **Perceptron implementation** — `find_output()`, `find_score()`, `find_perceptron_prediction()`
5. **Decision boundaries** — Visualize classification boundaries with `get_x1_line_points()`
6. **Misclassification** — Calculate and visualize prediction errors
7. **Loss functions** — `find_loss()` for measuring error
8. **Parameter optimization** — `parameter_optimize()` using gradient descent with learning rate tuning
9. **Convergence visualization** — Plot loss reduction over iterations

## Key Functions

| Function | Purpose |
|----------|---------|
| `find_output(x1, x2, w1, w2, b)` | Compute raw perceptron output |
| `find_score(x1, x2, w1, w2, b)` | Compute classification score |
| `find_perceptron_prediction(x1, x2, w1, w2, b)` | Return 0/1 prediction |
| `get_x1_line_points(w1, w2, b)` | Generate decision boundary points |
| `generate_spaced_points(start, end, num_points)` | Create evenly spaced coordinate arrays |
| `find_loss(actual, predicted)` | Calculate classification error |
| `parameter_optimize(data, learning_rate, num_iterations)` | Optimize weights via gradient descent |

## Code Conventions

- **Variables:** snake_case for descriptive names (`test_scores`, `grades`, `label`)
- **Parameters:** Mathematical notation for model params (`w1`, `w2`, `b`)
- **Functions:** verb-noun pattern (`find_output`, `get_x1_line_points`)
- **Imports:** Standard aliases — `pd` for pandas, `np` for numpy, `plt` for matplotlib.pyplot

## Known Limitations

- **Python 2:** The notebook kernel targets Python 2, which is EOL. Consider migrating to Python 3.
- **Code duplication:** Some functions are redefined across multiple cells rather than being defined once and reused.
- **No tests:** There is no test suite; the notebook is exploratory/educational.
- **No dependency management:** No `requirements.txt`, `Pipfile`, or `pyproject.toml` exists.
- **No CI/CD:** No automated pipelines are configured.

## Development Notes

- No linting, formatting, or type-checking tools are configured.
- No `.gitignore` is present — be careful not to commit notebook output artifacts or virtual environments.
- When modifying the notebook, preserve the sequential teaching flow since cells depend on prior state.
