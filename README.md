# Music-Mental-Health-Prediction-Model
This project explores the relationship between music listening habits and mental health by building a machine learning pipeline that predicts four conditions: Anxiety, Depression, OCD, and Insomnia. It includes reproducible preprocessing, automated model training, and evaluation with cross-validation, all packaged in a clean and modular repository.

## Features
- Preprocessing pipeline with ordinal encoding for categorical data and mean imputation for missing values  
- Modular training for each mental health target using Random Forest classifiers  
- Cross-validation and holdout evaluation for reliable performance estimates  
- Saved models in `.joblib` format for reuse  
- CLI scripts for preprocessing and training  
- Organized structure with Makefile, tests, and documentation  

## Quickstart

### 1. Setup environment
```bash
python -m venv .venv
source .venv/bin/activate   # Windows: .venv\Scripts\activate
pip install -r requirements.txt
````

### 2. Add the dataset

Place the raw dataset file in the `data/` directory:

```
data/mxmh_survey_results.csv
```

### 3. Preprocess the data

```bash
python scripts/preprocess.py --input data/mxmh_survey_results.csv --output data/preprocessed.csv
```

### 4. Train all models

```bash
python scripts/train_all.py --input data/preprocessed.csv --models_dir models
```

### 5. Train a single target

```bash
python -m mmh_ml.train --input data/preprocessed.csv --target Anxiety --models_dir models
```

### 6. Run tests

```bash
pytest -q
```

## Repository layout

```
music-mental-health-ml/
├── data/                 # raw & processed data (not versioned by default)
├── models/               # saved models (.joblib)
├── notebooks/            # exploratory analysis (optional)
├── scripts/              # CLI scripts
├── src/mmh_ml/           # core library code
├── tests/                # basic tests
├── requirements.txt
├── Makefile
├── README.md
└── LICENSE
```

## Targets

* Anxiety
* Depression
* OCD
* Insomnia

## Notes

* Baseline model: RandomForestClassifier (scikit-learn)
<img width="618" height="987" alt="Screenshot 2025-06-27 175451" src="https://github.com/user-attachments/assets/e3655734-bc23-4f98-9167-57d17d16b633" />

