# 📌 **Insurance Risk Analytics – Week 3**

### **10 Academy – AI Mastery Program**

### **Task 1 & Task 2 Completion Summary**

---

## 🚀 **Overview**

This repository contains all work completed for **Week 3** of the 10 Academy AI Mastery Program, focused on:

* **Exploratory Data Analysis (EDA)**
* **Statistical insight generation**
* **Reproducible pipelines with DVC (Data Version Control)**

The project uses a real-world insurance transactional dataset to analyze risk, claims, profitability, and geographic patterns.
DVC is used to ensure full reproducibility, traceability, and compliance — essential for financial/insurance analytics.

---

# 🧠 **Task 1.2 — Exploratory Data Analysis & Statistical Insights**

### ✅ **1. Data Understanding**

* Shape, schema, dtypes, completeness check
* Missing values inspection
* Summary statistics for numeric and categorical features
* Converted date fields, normalized categories & cleaned column names

---

### ✅ **2. Univariate & Bivariate EDA**

Performed analysis on key fields, including:

* **TotalPremium**
* **TotalClaims**
* **LossRatio**
* **VehicleType, Province, Gender, Make, Model**

**Techniques included:**
✔ Histograms
✔ KDE plots
✔ Bar charts
✔ Box plots for outlier detection
✔ Correlation heatmaps
✔ Group-by aggregations
✔ Temporal trendlines

---

### 🔍 **Key Insights**

* Provinces show strong variation in **claim severity & loss ratios**.
* Certain vehicle makes/models have **consistently high claim amounts**.
* Loss ratios vary significantly by **VehicleType** and **Gender**.
* Several numeric variables show **right-skewed distributions** → strong presence of high-value outliers.
* Temporal trends reveal fluctuations in monthly premium vs. claims over 18 months.

---

## 📊 **Core EDA Visualizations**

![Distribution of TotalPremium](images/eda_totalpremium.png)
![Top Provinces by Loss Ratio](images/lossratio_province.png)
![Premium vs Claims Scatter](images/premium_vs_claims.png)
---

# 🗂 **Task 2 — Reproducible Data Pipelines with DVC**

### 🎯 Goal

Ensure the entire project is **auditable**, **version-controlled**, and **reproducible** — matching real insurance industry standards.

---

## ⚙️ **What Was Implemented**

### ✅ **1. DVC Initialization**

```bash
dvc init
```

### ✅ **2. Local Remote Storage Setup**

A storage directory was created and registered as:

```bash
dvc remote add -d localstorage <path-to-storage>
```

### ✅ **3. Dataset Tracking**

```bash
dvc add data/MachineLearningRating_v3.csv
```

This ensures:

* The dataset is **not stored in the Git repo**
* Instead, **metadata (.dvc file)** is tracked
* Actual data is stored in the configured remote

### ✅ **4. Commit DVC files**

All metadata (`.dvc`, `config.dvc`, tracked files) committed to Git.

### ✅ **5. Data pushed to local remote**

```bash
dvc push
```

---

## 📂 **Updated Project Structure**

```
insurance-risk-analytics-week3/
│
├── data/
│   ├── MachineLearningRating_v3.csv.dvc
│   └── (actual data stored in DVC remote)
│
├── notebooks/
│   └── eda_week3.ipynb
│
├── .dvc/
│   ├── config
│   └── cache/
│
├── .github/workflows/
│   └── ci.yml   (coming later for Task 3)
│
├── requirements.txt
├── .gitignore
└── README.md
```

---

# 🧾 **How to Reproduce This Project Locally**

```bash
git clone https://github.com/kal1kidan/insurance-risk-analytics-week3.git
cd insurance-risk-analytics-week3

# create virtual environment
python -m venv .venv
source .venv/Scripts/activate

pip install -r requirements.txt

# retrieve version-controlled data
dvc pull
```

---

# 📝 **Task Status**

| Task                              | Status       | Description                 |
| --------------------------------- | ------------ | --------------------------- |
| **Task 1.2 – EDA & Statistics**   | ✔️ Completed | Full EDA + insights + plots |
| **Task 2 – DVC & Pipeline Setup** | ✔️ Completed | Reproducible data tracking  |

---

# 🎉 **Next Steps (Task 3 Preview)**

Coming next:

* CI/CD pipeline for notebook tests
* Linting, formatting, type checks
* DVC pipeline stages
* Automated report regeneration

---