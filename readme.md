# Retail Sales Performance Analysis & Forecasting — Big Mart Dataset

## 1. Business Context
Retail businesses lose margin and shelf efficiency when they cannot answer a basic question: **which product and store characteristics actually drive sales?**
This project analyzes 8,523 retail transactions across 1,559 SKUs and 10 stores to identify the factors most associated with sales performance, and builds a forecasting model to support data-driven merchandising decisions such as store-tiering and pricing strategy.

## 2. Business Questions
- Which store and product characteristics are most strongly associated with sales performance?
- Can sales be reliably forecast at the SKU–store level using available product and store attributes?
- Where does the underlying data contain quality issues that would mislead merchandising decisions if left unaddressed (e.g., product attributes, display/visibility data)?

## 3. Dataset
- **Source:** Big Mart Sales Prediction Dataset (Kaggle)
- **Scope:** 8,523 records | 1,559 unique SKUs | 10 stores | single year snapshot (no time-series component)
- **Key fields:** Item type, item price (MRP), item weight, display/visibility ratio, fat content, store type, store size, store location tier, store establishment year, sales (target variable)

## 4. Key Insights
- **Store format is the strongest driver of sales performance** — store type showed a substantially larger impact than any single product attribute in the model's feature-importance ranking.
- **Store age and item price (MRP) are the next most influential factors**, indicating that both store maturity and pricing position matter for sales outcomes.
- **Product-level attributes (visibility, fat content) had comparatively low predictive weight**, suggesting sales in this dataset are driven more by *where* and *at what price* a product is sold than by secondary product characteristics.
- **Data quality issues were identified and corrected before analysis**, including:
  - Products recorded with zero display/shelf visibility despite generating sales — logically inconsistent and corrected via identifier- and category-level imputation.
  - Non-consumable items incorrectly carrying a fat-content value — relabeled to reflect accurate product classification.
  - Missing item weight (1,463 records) and store size (2,410 records) — resolved using a tiered imputation approach (exact match → category median).

## 5. Methodology (Summary)
1. Train/test split performed **before** any data cleaning to prevent data leakage.
2. Missing values and logical inconsistencies resolved using business-informed rules (e.g., same SKU → same weight; store type → typical store size).
3. Categorical attributes encoded for model compatibility (One-Hot Encoding).
4. Five regression approaches benchmarked: Linear Regression, Ridge, Lasso, Random Forest, XGBoost.
5. Best-performing model selected based on test-set error (RMSE, MAE) and R², then validated for stability using 5-fold cross-validation.
6. Feature-importance analysis used to identify the top drivers of sales.

*Full technical detail (code, formulas, model tuning) is available in the accompanying notebook and report — see [Files](#7-files) below.*

## 6. Business Recommendations
- **Store-tiering:** Since store type and store age are top sales drivers, allocation and target-setting should account for store format/maturity rather than treating all stores uniformly.
- **Pricing:** The positive relationship between MRP and sales suggests price positioning is a meaningful lever worth testing further at the category level.
- **Data governance:** The visibility and fat-content inconsistencies found here indicate a need for stronger data-entry validation upstream, as these errors would otherwise distort assortment or display-related decisions.

> Note: This project does not yet include category-level revenue contribution, price-band segmentation, or promotion/inventory analysis, as the source dataset does not contain promotion or stock-movement data. These are natural next steps rather than findings claimed here.

## 7. Files
| File | Description |
|---|---|
| `notebook.ipynb` | Full data cleaning, feature engineering, and modeling code |
| `report.pdf` | Detailed write-up of methodology, statistical reasoning, and model evaluation |
| `README.md` | This summary |

## 8. Tools
Python (pandas, numpy, scikit-learn, XGBoost, matplotlib, seaborn)

## 9. Limitations
- Dataset is a single-year cross-section — no seasonality or trend analysis possible.
- No promotion, stock, or transaction-timing data — pricing and demand insights are correlational, not causal.
- Model performance (Test R² = 0.60) indicates useful but imperfect predictive power; large positive outliers in sales remain under-forecast.
