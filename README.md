# TMAE Analysis — Emergency Service Performance in Brazilian Power Distribution

## Overview
This repository presents an empirical analysis of TMAE (Tempo Médio de Atendimento Emergencial) for Brazilian electricity distribution companies, using official open data published by ANEEL (Brazilian Electricity Regulatory Agency).
The study investigates the determinants of emergency service performance, with special emphasis on the relationship between operational capacity (field teams / vehicles) and service response time (TMAE).
In addition, the project explores predictive modeling and risk classification to assess future performance trends among distribution companies.
The analysis is designed to be reproducible, transparent, and methodologically consistent with ANEEL’s regulatory framework.

## Objectives
The main goals of this project are:
* To apply ML and data analytics techniques in a real case
* To analyze the historical behavior of TMAE across Brazilian distribution companies
* To evaluate how field team availability affects emergency response performance
* To compare company performance across years and months
* To quantify correlations between TMAE and operational indicators
* To build predictive models for future TMAE values
* To classify companies into risk categories based on expected performance


## Importance of the Study
Emergency response time is a critical regulatory and operational metric in the Brazilian power sector.
High TMAE values may indicate:

* Insufficient operational capacity
* Inefficient allocation of field teams
* Increased exposure to regulatory penalties
* Lower quality of service to customers

By combining regulatory indicators, field operation data, and machine learning techniques, this study provides:

Evidence-based insights for operational planning
A structured framework for performance benchmarking
A foundation for predictive and risk-based regulatory analysis


## Data Sources
All datasets used in this project are publicly available through ANEEL’s Open Data Portal.

## Methodology
### Data Preparation

* Standardization of column names
* Conversion of date/time fields
* Removal of incomplete or irrelevant records
* Aggregation of KPIs at company–year–month and company–year levels
* Construction of derived indicators, including:

*Formulas:* TMAE = TMP + TMD + TME

### Exploratory Data Analysis (EDA)

* Descriptive statistics
* Histograms and boxplots
* Scatter matrices
* Correlation analysis (Pearson and Spearman)
* Seasonal and interannual comparisons

### Field Team Analysis

* Estimation of average daily field teams per company
* Integration of field capacity with emergency KPIs

### Modeling and Prediction

Lagged feature engineering (up to 5 years)

Regression models:

* Linear Regression
* Ridge
* Lasso
* Elastic Net
* Random Forest
* Gradient Boosting

Cross-validation strategies:

* K-Fold
* GroupKFold
* TimeSeriesSplit

### Risk Classification

* Discretization of TMAE into risk categories
* Logistic Regression with regularization
* Stratified Group Cross-Validation
* Confusion matrix and accuracy evaluation
* Heatmaps of predicted vs actual risk over time


## Key Techniques and Tools

* Python
* Pandas / NumPy — data manipulation
* Matplotlib / Seaborn — visualization
* SciPy — statistical analysis
* Scikit-learn — machine learning and modeling
* Jupyter Notebook — reproducible research environment


## Key Results (High-Level)

* Strong heterogeneity in TMAE performance across companies
* Evidence that field team availability plays an important role in service performance
* Lasso regression provided the best balance between interpretability and predictive accuracy
* Risk classification models successfully identify companies with persistent performance issues


Project Structure

├── notebooks/
│   └── TMAE_Analysis.ipynb
├── images/

│   ├── boxplots
│   ├── histograms


│   ├── scatterplots
│   └── heatmaps
├── README.md
└── requirements.txt


## Disclaimer
This project is an academic and analytical study based exclusively on public data.
All interpretations and conclusions are the responsibility of the author and do not represent official positions of ANEEL or any distribution company.

## Author
Developed as part of a graduate-level research project focused on energy regulation, operational efficiency, and data-driven performance analysis.

## How to Run

### Prerequisites
- Python **3.9+**
- Internet connection (to download ANEEL open datasets)
- Recommended: virtual environment (venv or conda)

---

### 1. Clone the repository
```bash
git clone https://github.com/your-username/tmae-analysis.git
cd tmae-analysis
```

### 2. Create and activate a virtual environment (recommended)
Linux / macOS
Shellpython -m venv venvsource venv/bin/activateMostrar mais linhas
Windows
Shellpython -m venv venvvenv\Scripts\activateMostrar mais linhas

### 3. Install dependencies
All required libraries are standard Python data-science packages.
Shellpip install -r requirements.txtMostrar mais linhas
If you prefer manual installation, the core dependencies are:

- pandas
- numpy
- matplotlib
- seaborn
- scipy
- scikit-learn
- requests


### 4. Run the notebook
Start Jupyter and open the analysis notebook:
Shelljupyter notebookMostrar mais linhas
Then open:
notebooks/TMAE_Analysis.ipynb

Run the cells top to bottom.
The notebook automatically:

* Downloads the latest ANEEL datasets
* Cleans and aggregates the data
* Generates figures and statistical analyses
* Trains regression and classification models
* Saves plots into the images/ folder


### 5. Outputs

All figures are saved in the images/ directory
Key datasets are kept in memory for reproducibility
Results can be exported directly from the notebook if needed


## Notes

The analysis filters companies with NUC > 400,000, following ANEEL’s regulatory relevance criteria.
Data for 2026 is used only for prediction, as it is incomplete.
Execution time may vary depending on internet speed and machine performance.

## License
This project is licensed under the MIT License.
MIT License

Copyright (c) 2026

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.