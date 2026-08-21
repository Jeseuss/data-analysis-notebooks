# Data Analysis & Research Notebook

Runnable Jupyter/Google Colab notebook demonstrating **hypothesis testing, regression analysis, and algorithmic performance benchmarks** — the exact skills referenced in my resume under "Built reproducible Jupyter and Google Colab research notebooks."

## Quick start (2 minutes)

**Option A: Google Colab (recommended, zero setup)**
1. Go to https://colab.research.google.com
2. File → Open notebook → GitHub tab
3. Paste this repository URL, select `analysis.ipynb`
4. Runtime → Run all

**Option B: Local Jupyter**
```bash
pip install notebook
jupyter notebook
```
Then open `analysis.ipynb`.

## What the notebook does

| Cell | Task |
|------|------|
| 1-2 | One-command setup, imports, fixed random seed, version printout (reproducibility) |
| 3 | Loads built-in California housing dataset (self-contained, no files needed) |
| 4 | Missing-value check, train/test split, feature normalization |
| 5 | Two-sample t-test (hypothesis testing) with p-value interpretation |
| 6 | Linear vs. Ridge regression, RMSE and R2 on held-out test set |
| 7 | numpy vs. pandas wall-clock benchmark on the same operation |
| 8 | Template cell for swapping in your own CSV |

## Using your own data (3 steps)

1. Save your dataset as `data/my_data.csv` in this repo.
2. Replace cell 3 with:
   ```python
   df = pd.read_csv("data/my_data.csv")
   print("Shape:", df.shape)
   df.head()
   ```
3. In cell 4, set `y = df["your_target_column"]` and `X = df.drop(columns=["your_target_column"])`.

## Reproducibility built in

- Fixed random seed → same results every run
- Package versions printed
- `%pip install` handles dependencies in one cell
- Data lives next to the notebook (no absolute paths)

## Interview talking points

- Why a t-test: comparing two independent groups on a continuous target; p < 0.05 rejects the null hypothesis.
- R2 interpretation: fraction of variance in the target explained by the model.
- Benchmark value: a one-line implementation change (numpy vs. pandas) with a measurable runtime effect.
