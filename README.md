# Customer Churn Prediction — PowerCo

Predicting which customers of PowerCo, a fictional energy retailer, are likely to
churn, and identifying the factors that drive it. Built as part of the BCG Data
Science virtual experience programme (Forage).

The goal is not just a score: the feature-importance ranking is read back as
concrete retention levers the business could act on.

---

## Results

Random Forest classifier (100 estimators), 80/20 train/test split:

| Metric | Score |
|---|---|
| Accuracy | 85% |
| Precision | 78% |
| Recall | 82% |
| F1-score | 80% |
| AUC-ROC | 0.88 |

**Key churn drivers:** customer tenure, price differences across periods, and
consumption patterns.

ROC curve and feature-importance plots are generated inside the notebooks.

---

## Contents

| File | What's in it |
|---|---|
| `Feature engineering.ipynb` | Data cleaning and feature construction |
| `Customer_Churn_Analysis.ipynb` | Model training, evaluation and findings |
| `Solution_presentation.pptx` | Results written up for a business audience |

---

## Data

Two files supplied by the Forage programme:

- **`client_data.csv`** — customer demographics, consumption history, contract
  details and churn status (the target)
- **`price_data.csv`** — historical off-peak, peak and mid-peak prices for energy
  and power

> These are **not committed to this repository**. Download them from the virtual
> experience and place them in the repository root before running the notebooks.

---

## Feature engineering

The raw data needed a fair amount of work before it was modellable:

- **Date features** — tenure, days since last contract modification, days until renewal
- **Price differentials** — changes in off-peak, peak and mid-peak prices across periods
- **Interaction features** — combinations of the key price variables
- **Log transforms** — applied to skewed consumption features to normalise their distributions
- **Categorical encoding** — one-hot for nominal variables, label encoding for binary ones

---

## Setup

```bash
git clone https://github.com/Khush430/DataAnalysisProjects.git
cd DataAnalysisProjects

python -m venv venv
source venv/bin/activate        # Windows: venv\Scripts\activate

pip install pandas numpy scikit-learn matplotlib seaborn jupyter
```

## Running it

```bash
jupyter notebook
```

Open `Feature engineering.ipynb` first, then `Customer_Churn_Analysis.ipynb`.

## Built with

Python · pandas · NumPy · scikit-learn · Matplotlib · Seaborn · Jupyter

---

**Khush Joshi** — [GitHub](https://github.com/Khush430) · [LinkedIn](https://www.linkedin.com/in/khush-joshi/)
