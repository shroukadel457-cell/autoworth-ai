# AutoWorth AI 🚗

Used-car price prediction and "smart deal advisor" built on the UK Used Car dataset (9 manufacturers: Audi, BMW, Ford, Hyundai, Mercedes, Skoda, Toyota, Vauxhall, Volkswagen).

## What the project does
1. Loads and combines the 9 manufacturer CSV files (adds a `Make` column)
2. Cleans the data (invalid years, `engineSize = 0`, bad `mpg`, duplicates, rare categories)
3. Exploratory data analysis
4. 70 / 15 / 15 train / validation / test split
5. Feature engineering + preprocessing pipeline
6. Trains and compares: Linear Regression, Decision Tree, Random Forest, Gradient Boosting, XGBoost
7. Overfitting check + hyperparameter tuning (GridSearchCV)
8. Final evaluation on the test set + model interpretation
9. Smart Deal Advisor (is a listed price a good deal?)
10. Exports `autoworth_model.joblib` and `app_meta.json` for a Streamlit app

## Setup
```bash
git clone https://github.com/<your-username>/autoworth-ai.git
cd autoworth-ai
python -m venv .venv && source .venv/bin/activate   # Windows: .venv\Scripts\activate
pip install -r requirements.txt
```

## Data
Download the UK used car CSV files (`audi.csv`, `bmw.csv`, `ford.csv`, `hyundi.csv`, `merc.csv`, `skoda.csv`, `toyota.csv`, `vauxhall.csv`, `vw.csv`) from Kaggle ("100,000 UK Used Car Data set") and put them in the project root.

## Run
```bash
python autoworth_ai.py
```
The original Colab notebook: https://colab.research.google.com/drive/1ql8P052igrwsdMkDXD_Iz4E_KFuTxWRt

## Output
- `autoworth_model.joblib` – preprocessor + trained model
- `app_meta.json` – models per make, defaults, categories (for the Streamlit app)
