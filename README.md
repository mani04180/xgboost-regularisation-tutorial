# Taming XGBoost: How Regularisation and Tree Complexity Control Overfitting

A short, reproducible machine-learning tutorial that teaches **one focused skill**: how to
recognise overfitting in XGBoost and control it with the hyperparameters that govern
**tree complexity** and **regularisation** (the bias–variance trade-off).

**Module:** 7PAM2021 — Machine Learning (Individual Tutorial, REF)
**Repository:** `https://github.com/<your-username>/xgboost-regularisation-tutorial`
*(replace `<your-username>` with your real GitHub handle)*

---

## What this teaches

Using the UCI *Concrete Compressive Strength* dataset (1,030 samples, 8 numeric features,
regression target in MPa), the tutorial shows how three groups of parameters move XGBoost
along the bias–variance trade-off:

1. **Tree depth** (`max_depth`) — the main complexity dial.
2. **Learning rate** (`learning_rate` / eta) — shrinks each tree's contribution.
3. **Explicit regularisation** (`reg_lambda`, `gamma`, `min_child_weight`) plus
   **subsampling** and **early stopping**.

The headline result: a regularised, early-stopped model cuts test RMSE from **6.47 to
4.66 MPa** and lifts test R² from **0.84 to 0.92** versus an over-powered, unregularised model.

## Repository structure

| File | Description |
|------|-------------|
| `xgboost_regularisation_tutorial.ipynb` | The full, runnable notebook with all intermediate steps and 7 figures. |
| `XGBoost_Regularisation_Tutorial_Report.pdf` | The written tutorial (< 2000 words) — the main deliverable. |
| `XGBoost_Regularisation_Tutorial_Report.docx` | Editable source of the report. |
| `concrete.csv` | The dataset, shipped so the notebook runs offline. |
| `figures/` | PNG figures exported by the notebook. |
| `requirements.txt` | Pinned package versions. |
| `LICENSE` | MIT licence. |

## How to run

```bash
# 1. Clone the repository
git clone https://github.com/<your-username>/xgboost-regularisation-tutorial.git
cd xgboost-regularisation-tutorial

# 2. (Optional) create a virtual environment
python -m venv .venv
source .venv/bin/activate        # Windows: .venv\Scripts\activate

# 3. Install dependencies
pip install -r requirements.txt

# 4. Launch the notebook and run all cells
jupyter notebook xgboost_regularisation_tutorial.ipynb
```

Running every cell reproduces all seven figures used in the report. A fixed random seed
(`SEED = 42`) makes results identical across runs. If `concrete.csv` is ever missing, the
notebook automatically downloads the dataset from the UCI repository.

## Accessibility

- All figures use the **colour-blind-safe Okabe–Ito palette** plus distinct line styles and
  markers, so they remain readable in greyscale.
- The report PDF is **tagged** (structure tree + language) and every figure carries
  **descriptive alt-text** for screen readers.

## Dataset

Yeh, I-C. (1998). *Modeling of strength of high-performance concrete using artificial neural
networks.* Cement and Concrete Research, 28(12), 1797–1808.
UCI Machine Learning Repository (id 165):
https://archive.ics.uci.edu/dataset/165/concrete+compressive+strength

## References

1. Chen, T. & Guestrin, C. (2016). *XGBoost: A Scalable Tree Boosting System.* KDD '16.
   https://doi.org/10.1145/2939672.2939785
2. XGBoost developers. *XGBoost Documentation — Parameters.*
   https://xgboost.readthedocs.io/en/stable/parameter.html
3. Okabe, M. & Ito, K. *Color Universal Design (colour-blind-safe palette).*
   https://jfly.uni-koeln.de/color/

## Licence

Released under the **MIT Licence** — see [`LICENSE`](LICENSE). You are free to use, modify,
and share this material with attribution.
