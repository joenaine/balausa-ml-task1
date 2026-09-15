# balausa-ml-task1

Practical Task 1: Supervised Learning.

This repository is the submission. It reproduces the lecture's Boston Housing example on a different dataset: California Housing (Pace and Barry, 1997), ordinary least squares, scatter of one input against the target, fitted line over the points.

## What the assignment asked

1. Find and download a supervised-learning dataset.
2. Identify the input features \(X\) and the target \(y\).
3. Load the table in Python and prepare it.
4. Select one or more features and plot the input–target relationship.
5. Train a supervised model that fits the task.
6. Make predictions.
7. Plot predictions with the original data, in the Boston Housing layout (scatter + line).
8. Score the model with an appropriate metric.
9. Write a short conclusion: what the model learned, and how well it did.

## What to submit

| File | Role |
|---|---|
| **[Report.pdf](Report.pdf)** | The report. This is the file to hand in. |
| **[Report.ipynb](Report.ipynb)** | Runnable notebook: code, figures, and the same write-up. Hand this in if the course wants an `.ipynb`. |

## Dataset

- Source: StatLib California Housing archive ([Figshare](https://ndownloader.figshare.com/files/5976036)).
- Prepared table: `data/california_housing.csv` (20,640 census block groups, 1990 US Census).
- \(X\): `MedInc`, `HouseAge`, `AveRooms`, `AveBedrms`, `Population`, `AveOccup`, `Latitude`, `Longitude`.
- \(y\): `MedHouseVal` (median house value, units of $100,000).
- Task: regression.

The one-feature lecture plot uses `MedInc` (correlation with price: 0.69). `AveRooms` is the Boston analogue here and only correlates 0.15 with price.

## How to run the notebook

Python 3.12+. From the repository root:

```bash
uv sync
uv run jupyter notebook Report.ipynb
```

Without `uv`:

```bash
pip install scikit-learn pandas numpy matplotlib jupyter
jupyter notebook Report.ipynb
```

## Result (one-feature OLS, test \(n = 4{,}128\))

\[
\mathrm{MedHouseVal} = 0.445 + 0.419 \times \mathrm{MedInc}
\]

\(R^2 = 0.459\), RMSE \(\approx\) \$84,200. The eight-feature linear model reaches \(R^2 = 0.576\). Details, figures, and limitations are in `Report.pdf`.

## Reference

Pace, R. Kelley, and Ronald Barry. 1997. "Sparse Spatial Autoregressions." *Statistics & Probability Letters* 33: 291–297.
