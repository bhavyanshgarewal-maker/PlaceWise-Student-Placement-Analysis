# PlaceWise --- Student Placement Analysis

PlaceWise is a Data Warehousing and Mining (DWM) mini project
demonstrating how student placement records can be cleaned, stored,
explored, and analyzed with Python, machine learning, and data-mining
techniques.

> **Academic-project note:** The sample dataset is synthetic. Results
> are for demonstration and coursework only, not validated predictions
> about real students or employers.

## Objectives

-   Clean and prepare placement records through an ETL workflow.
-   Store processed data in SQLite.
-   Explore student and placement patterns.
-   Demonstrate classification, regression, association-rule mining, and
    clustering.
-   Present analytical outputs through a Streamlit interface.

## Algorithms

  -----------------------------------------------------------------------
  Technique                           Purpose
  ----------------------------------- -----------------------------------
  Decision Tree (J48-style)           Placement classification

  Naive Bayes                         Probabilistic placement
                                      classification

  Multiple Linear Regression          Predict a numeric package/salary
                                      target

  Apriori-style association mining    Discover frequent itemsets and
                                      rules

  K-Means                             Group similar records
  -----------------------------------------------------------------------

**Implementation note:** The Python decision tree is described as
*J48-style* because it uses an entropy-based decision tree; it is not
WEKA's own J48 implementation. Describe the association-mining algorithm
according to the implementation in your actual code.

## Technology

-   Python, Streamlit
-   pandas, NumPy, scikit-learn
-   SQLite
-   Matplotlib, if used by the application

See `requirements.txt` for package dependencies.

## Project structure

``` text
PlaceWise-Student-Placement-Analysis/
├── app.py
├── model.py
├── etl.py
├── generate_data.py
├── styles.css
├── requirements.txt
├── README.md
├── RESEARCH_PAPERS.md
└── data/
    ├── placement_data.csv
    ├── placement_data_uncleaned.csv
    └── placewise.db
```

This is the intended layout; update it if the files committed to your
repository differ.

## Run locally

### 1. Clone the repository

``` bash
git clone https://github.com/bhavyanshgarewal-maker/PlaceWise-Student-Placement-Analysis.git
cd PlaceWise-Student-Placement-Analysis
```

### 2. Create and activate a virtual environment

For Windows PowerShell, using a Python version supported by your
dependencies:

``` powershell
py -3.12 -m venv .venv
.\.venv\Scripts\Activate.ps1
```

If PowerShell blocks activation, use Command Prompt:

``` bat
.venv\Scripts\activate.bat
```

### 3. Install dependencies

``` bash
python -m pip install --upgrade pip
pip install -r requirements.txt
```

### 4. Start the app

``` bash
python -m streamlit run app.py
```

Open the local URL printed by Streamlit, usually
`http://localhost:8501`.

Do not commit `.venv/` or `venv/` folders. If the repository does not
yet include `requirements.txt`, create it from the dependencies used by
the actual code.

## ETL workflow

1.  Read the raw placement CSV.
2.  Standardize categorical labels and values.
3.  Handle missing and invalid values as defined in the ETL code.
4.  Remove or resolve duplicate records.
5.  Save processed data and/or load it into SQLite.
6.  Train and evaluate the models using the processed records.

The previously generated demonstration data contained 60,000 synthetic
raw records and 58,161 records after cleaning. Re-run the ETL workflow
before reporting these counts if the committed code or dataset has
changed.

## Evaluation

-   **Classification:** accuracy, precision, recall, and F1-score.
-   **Regression:** R², mean absolute error (MAE), and root mean squared
    error (RMSE).
-   **Clustering:** a metric such as silhouette score; cluster IDs are
    groups, not confirmed real-world categories.
-   **Association rules:** support, confidence, and lift.

Metrics from different task types should not be compared as if they
measure the same thing. Results depend on the dataset, features,
preprocessing, and train/test split.

## Limitations and responsible use

-   Synthetic data may not represent real placement outcomes.
-   Model scores are demonstrations, not guarantees about an individual
    student's future.
-   Use real student data only with appropriate permission and privacy
    safeguards.
-   Models can reflect data bias and should not make high-stakes
    placement decisions automatically.
-   This is an academic demonstration, not a production recruitment
    system.

## Research papers

See [`RESEARCH_PAPERS.md`](RESEARCH_PAPERS.md) for related literature.

## License

No license is specified here. Add a `LICENSE` file only after choosing a
license for your own code and confirming that you have permission to
license all included content and data.
