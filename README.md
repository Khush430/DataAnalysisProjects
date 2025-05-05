# Customer Churn Prediction for PowerCo

## Project Overview
This repository contains the code and analysis for predicting customer churn at PowerCo, a fictional energy company. The goal of this project is to identify customers who are likely to churn (i.e., stop using PowerCo's services) and understand the key factors driving churn. By leveraging historical customer data and pricing information, we aim to build a predictive model that can help PowerCo reduce churn and retain its customer base.

## Installation
To run this project locally, follow these steps:

1. **Clone the repository**:
   ```bash
   git clone https://github.com/yourusername/powerco-churn-prediction.git
   cd powerco-churn-prediction
   ```

2. **Set up a virtual environment** (optional but recommended):
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

4. **Download the dataset**:
   - The dataset is available in the `data/` directory. If not, download it from [link to dataset] and place it in the `data/` folder.

## Usage
To run the churn prediction model:

1. **Preprocess the data**:
   ```bash
   python scripts/data_preprocessing.py
   ```

2. **Train the model**:
   ```bash
   python scripts/model_training.py
   ```

3. **Evaluate the model**:
   ```bash
   python scripts/model_evaluation.py
   ```

4. **View results**:
   - Visualizations and results are saved in the `results/` directory.

## Dataset
The dataset consists of two main files:
- **client_data.csv**: Contains historical customer information, including demographics, consumption, and churn status.
- **price_data.csv**: Contains historical pricing data for energy and power.

### Key Features
- **Customer Features**: Tenure, consumption patterns, contract details, etc.
- **Pricing Features**: Off-peak, peak, and mid-peak prices for energy and power.
- **Target Variable**: `churn` (binary: 1 if the customer churned, 0 otherwise).

## Feature Engineering
Several feature engineering techniques were applied to enhance model performance:
- **Date Features**: Extracted tenure, days since modification, and days until renewal.
- **Price Differences**: Calculated differences in off-peak, peak, and mid-peak prices over time.
- **Interaction Features**: Created interactions between key price variables.
- **Log Transformations**: Applied to skewed numerical features to normalize distributions.
- **Categorical Encoding**: One-hot encoding for nominal variables and label encoding for binary variables.

## Model Training
We used a **Random Forest Classifier** for churn prediction due to its ability to handle complex interactions and provide feature importance insights. The model was trained on 80% of the data and tested on the remaining 20%.

### Hyperparameters
- `n_estimators=100`
- `random_state=42`

## Evaluation
The model's performance was evaluated using the following metrics:
- **Accuracy**: 85%
- **Precision**: 78%
- **Recall**: 82%
- **F1-Score**: 80%
- **AUC-ROC**: 0.88

Visualizations of the ROC curve and feature importance are available in the `results/` directory.

## Results
- The model successfully identifies customers at risk of churning with high accuracy.
- Key drivers of churn include **tenure**, **price differences**, and **consumption patterns**.
- The feature importance plot highlights the most influential factors in predicting churn.

## Contributing
Contributions are welcome! If you'd like to improve the model or add new features, please follow these steps:
1. Fork the repository.
2. Create a new branch (`git checkout -b feature-branch`).
3. Make your changes and commit (`git commit -m "Add new feature"`).
4. Push to the branch (`git push origin feature-branch`).
5. Open a pull request.
