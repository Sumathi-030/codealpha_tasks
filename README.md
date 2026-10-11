# CodeAlpha Machine Learning Projects

This repository contains two machine learning classification projects developed in Python using Jupyter Notebook. The projects cover data exploration, preprocessing, feature engineering, model training, evaluation, and prediction.

## Projects

### 1. Creditworthiness Prediction

**Notebook:** [Credit_Scoring.ipynb](Credit_Scoring.ipynb)

This project predicts whether a loan applicant is creditworthy based on financial and credit-history information.

**Dataset**
- The notebook is designed around applicant data with features such as age, employment status, income, expenses, credit score, existing loans, debt, payment history, savings, and previous defaults.
- The notebook reports 900 records and 20 original columns.
- The repository includes `train_set.xls`. The notebook currently attempts to load `train_set.csv`; see **Dataset setup** below before running it.

**Workflow**
- Inspect the dataset structure and check for missing values.
- Engineer additional features: savings-to-income, expense-to-income, and loan-to-income ratios.
- Separate input features from the `Creditworthiness` target.
- Encode categorical features using one-hot encoding and scale numerical features.
- Split data into training and testing sets.
- Train and compare Logistic Regression, Decision Tree, and Random Forest classifiers.
- Evaluate models with accuracy, precision, recall, F1-score, ROC-AUC, and confusion matrices.
- Visualize model performance and demonstrate a prediction for a new applicant.

### 2. Breast Cancer Diagnosis Classification

**Notebook:** [Disease_Prediction.ipynb](Disease_Prediction.ipynb)

This project trains classification models on the Wisconsin Diagnostic Breast Cancer dataset to classify tumours as **benign** or **malignant**. It is an educational machine learning exercise and is not a medical diagnostic tool.

**Dataset**
- Retrieved from the UCI Machine Learning Repository using the `ucimlrepo` package (dataset ID 17).
- Contains 569 records and 30 numerical features, with a diagnosis target.
- Features describe cell-nucleus measurements such as radius, texture, perimeter, area, smoothness, compactness, concavity, symmetry, and fractal dimension.

**Workflow**
- Load and inspect the dataset; check for missing and duplicate records.
- Convert diagnosis labels to numerical classes (benign = 0, malignant = 1).
- Explore feature correlations with a heatmap.
- Split the data into training and testing sets and scale features where appropriate.
- Train and compare Logistic Regression, Support Vector Machine (SVM), Random Forest, and XGBoost classifiers.
- Evaluate accuracy, precision, recall, F1-score, and ROC-AUC.
- Visualize model comparison, a confusion matrix, and ROC curves.
- Run stratified 5-fold cross-validation and demonstrate a sample prediction.

## Technologies Used

- Python
- Jupyter Notebook
- NumPy
- pandas
- Matplotlib
- Seaborn
- scikit-learn
- XGBoost
- ucimlrepo

## Repository Structure

```text
codealpha_tasks/
├── Credit_Scoring.ipynb
├── Disease_Prediction.ipynb
├── train_set.xls
├── breast+cancer+wisconsin+diagnostic/
└── README.md
```

## Setup

### 1. Clone the repository

```bash
git clone https://github.com/Sumathi-030/codealpha_tasks.git
cd codealpha_tasks
```

### 2. Create and activate a virtual environment (recommended)

```bash
python -m venv .venv
```

On Windows:

```bash
.venv\\Scripts\\activate
```

On macOS/Linux:

```bash
source .venv/bin/activate
```

### 3. Install dependencies

```bash
python -m pip install numpy pandas matplotlib seaborn scikit-learn jupyter ucimlrepo xgboost xlrd
```

## Dataset Setup

### Credit Scoring notebook

The notebook currently contains:

```python
data_df = pd.read_csv("train_set.csv")
```

However, the repository contains `train_set.xls`, not `train_set.csv`. To use the file already in the repository, replace that line with:

```python
data_df = pd.read_excel("train_set.xls")
```

The `xlrd` package included in the installation command supports reading legacy `.xls` files. Alternatively, convert the spreadsheet to CSV and keep the original notebook line.

### Disease Prediction notebook

The breast cancer dataset is downloaded by the notebook through `ucimlrepo`. An internet connection is required when fetching the dataset for the first time.

## Run the Notebooks

Start Jupyter Notebook from the repository directory:

```bash
jupyter notebook
```

Open either notebook and run the cells from top to bottom:

- `Credit_Scoring.ipynb`
- `Disease_Prediction.ipynb`

Run the Credit Scoring notebook only after completing the dataset setup above. Model results may vary if the dataset or library versions change.

## Evaluation Metrics

| Metric | What it measures |
|---|---|
| Accuracy | Overall proportion of correct predictions |
| Precision | How many predicted positive cases are actually positive |
| Recall | How many actual positive cases the model identifies |
| F1-score | Balance between precision and recall |
| ROC-AUC | How well the model separates the two classes |
| Confusion matrix | Counts of correct and incorrect predictions by class |
| Cross-validation | Model performance across multiple data splits |

## Learning Outcomes

These projects provide practice with:
- Exploratory data analysis and data-quality checks
- Feature engineering and preprocessing pipelines
- Numerical scaling and categorical encoding
- Training and comparing classification algorithms
- Model evaluation and visualisation
- Cross-validation and sample predictions

## Disclaimer

The predictions are for learning and demonstration only. Creditworthiness predictions should not be used as the sole basis for real financial decisions. Breast cancer predictions must not be used for diagnosis, screening, or treatment decisions; consult qualified healthcare professionals.

## Author

**Sumathi**  
GitHub: [Sumathi-030](https://github.com/Sumathi-030)
