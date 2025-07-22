### README.md

```markdown
Amex Personalized Offer Click Prediction

This project addresses the problem of predicting whether a customer will click on a personalized offer using transaction history, offer metadata, and behavioral features.

## Project Structure

amex-click-prediction/
├── data/                  
├── feature_engineering/  
├── src/                  
├── outputs/             
├── requirements.txt     
├── .gitignore            
└── README.md             
```

## Files Overview
- `Feature_Engineering/` contains all feature engineering and training notebooks.
- `src/main.py` is the main orchestration script (can call preprocessing + model).
- `models/` holds `.pkl` or `.cbm` trained models.
- `outputs/` has prediction visualizations and final submission.

## Key Techniques
- Feature engineering from customer event logs
- Offer metadata merging
- XGBoost and CatBoost classifiers
- Feature importance selection
- One-hot encoding + category handling

## Best Model Results
| Model     | Score (AUC or MAP@7) |
|-----------|----------------------|
| XGBoost   | 0.83 (validation)    |
| CatBoost  | 0.84 (validation)    |


## Requirements
```bash
pip install -r requirements.txt
```

## How to Run

### Step 1: Generate Final Train/Test Dataset
Open and run `main.ipynb`

- You **do not need to run the feature engineering notebooks separately**.
- `main.ipynb` automatically calls the functions from:
  - `events_features.ipynb`
  - `offers_features.ipynb`
  - `transaction_features.ipynb`
- It merges the engineered features from all supporting datasets and creates a final processed dataset ready for model training.

---

### Step 2: Train Model
Open and run `model.ipynb`

- This notebook trains an XGBoost or CatBoost model on the processed dataset from `main.ipynb`.
- It includes feature selection, hyperparameters, evaluation, and model saving.

---

### Step 3: Prepare Submission
Open and run `submission.ipynb`

- This notebook loads the trained model.
- It processes the test dataset similarly to the training dataset.
- Then it generates predictions and attaches them to the required submission format (using the columns in `submission_template.csv`).



## Final Output
Check `outputs/final_submission.csv` for predictions ready to be uploaded.

## Author
Astitva Roy | [LinkedIn](https://www.linkedin.com/in/astitva-roy-b40097346/)
```
```

---
