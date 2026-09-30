# CreditWise — Loan Approval Prediction

CreditWise is a machine-learning project that explores loan approval prediction using applicant financial, credit, employment, and demographic features. The notebook covers data quality checks, exploratory data analysis (EDA), preprocessing, feature encoding and scaling, baseline model evaluation, and a small feature-engineering experiment.

> **Project scope:** This is an educational analytics project using a dataset named `loan_approval_data.csv`. It is not a production credit-scoring system and should not be used to make real lending decisions.

## Objectives

- Inspect and prepare structured loan-applicant data for analysis.
- Explore relationships between approval outcomes and applicant attributes.
- Build and compare classification models using consistent train/test splits.
- Evaluate results using precision, recall, F1-score, accuracy, and confusion matrices.
- Examine whether engineered features affect model performance.

## Dataset

The notebook reads `loan_approval_data.csv`. The dataset contains 1,000 rows and includes fields such as:

- **Financial:** `Applicant_Income`, `Coapplicant_Income`, `Savings`, `Collateral_Value`, `Loan_Amount`
- **Credit and liabilities:** `Credit_Score`, `Existing_Loans`, `DTI_Ratio`
- **Applicant profile:** `Age`, `Dependents`, `Employment_Status`, `Marital_Status`, `Education_Level`, `Gender`, `Employer_Category`
- **Loan details:** `Loan_Purpose`, `Loan_Term`, `Property_Area`
- **Target:** `Loan_Approved`

The notebook initially identifies missing values and imputes numerical columns with the mean and categorical columns with the most frequent value. The source dataset is not included in this repository by default; add it locally if you have permission to share it.

## Tech Stack

- Python
- pandas and NumPy
- Matplotlib and Seaborn
- scikit-learn
- Jupyter Notebook

## Workflow

1. **Data loading and profiling** — load the CSV and inspect schema, summary statistics, and missing values.
2. **Missing-value treatment** — mean imputation for numeric features and most-frequent imputation for categorical features.
3. **Exploratory data analysis** — inspect the target distribution, income distributions, education categories, and relationships between approval and variables such as credit score, DTI ratio, savings, and income.
4. **Feature preparation** — remove `Applicant_ID`, encode `Education_Level` and `Loan_Approved`, and one-hot encode selected categorical columns.
5. **Correlation analysis** — calculate and visualize correlations between numeric features.
6. **Train/test split and scaling** — use an 80/20 split with `random_state=42`; fit `StandardScaler` on the training set and transform the test set.
7. **Baseline classification** — train Logistic Regression, K-Nearest Neighbors (KNN), and Gaussian Naive Bayes models.
8. **Feature-engineering experiment** — add squared versions of `DTI_Ratio` and `Credit_Score`, remove the original versions in that experiment, and evaluate the models again.


## Run locally

### 1. Clone the repository

```bash
git clone <your-repository-url>
cd <your-repository-folder>
```

### 2. Create and activate a virtual environment (Windows PowerShell)

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install --upgrade pip
```

If PowerShell blocks activation, you can use the environment's Python directly:

```powershell
.\.venv\Scripts\python.exe -m pip install -r requirements.txt
```

### 3. Install dependencies

Create a `requirements.txt` file with:

```text
pandas
numpy
matplotlib
seaborn
scikit-learn
jupyter
ipykernel
```

Then run:

```powershell
python -m pip install -r requirements.txt
```

### 4. Add the dataset

Place `loan_approval_data.csv` in the same directory as the notebook, or update the CSV path in the first data-loading cell.

### 5. Launch Jupyter

```powershell
jupyter notebook
```





This project is for learning and portfolio demonstration only. It is not financial advice, a validated credit-risk model, or a substitute for regulated lending, privacy, fairness, and model-risk review.
