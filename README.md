# Retail-Sales-Forecasting
End-to-end retail forsacting using Machine Learning, EDA and Business Insights on the Rossmann Store Sales dataset.

# Retail Sales Forecasting

## Project Overview

Retail sales forecasting is critical for inventory planning, workforce allocation, promotional strategy, and revenue optimization. This project analyzes historical sales data from Rossmann stores to identify the key drivers of sales and forecast future store revenue using machine learning models.

The project combines business analysis, exploratory data analysis (EDA), feature engineering, and predictive modeling to support data-driven decision-making.

---

## Business Problem

Retail businesses need accurate sales forecasts to:

- Optimize inventory management
- Improve staffing decisions
- Plan promotional campaigns
- Increase revenue and profitability
- Understand factors influencing store performance

This project aims to answer:

- What factors drive sales?
- Do promotions increase revenue?
- How do holidays affect sales?
- Which store types perform best?
- Can future sales be accurately predicted?

---

## Dataset

**Rossmann Store Sales Dataset**

Source:

https://www.kaggle.com/competitions/rossmann-store-sales

### Files Used

- train.csv
- store.csv

### Dataset Size

| Dataset | Rows | Columns |
|----------|---------|---------|
| Train | 1,017,209 | 9 |
| Store | 1,115 | 10 |

After merging:

| Dataset | Rows | Columns |
|----------|---------|---------|
| Final Dataset | 1,017,209 | 18 |

---

## Data Cleaning

### Missing Values

The following columns contained missing values:

| Feature | Missing Values |
|----------|---------|
| PromoInterval | 508,031 |
| Promo2SinceYear | 508,031 |
| Promo2SinceWeek | 508,031 |
| CompetitionOpenSinceYear | 323,348 |
| CompetitionOpenSinceMonth | 323,348 |
| CompetitionDistance | 2,642 |

Observations:

- Missing Promo2-related values correspond to stores not participating in the Promo2 program.
- Missing competition-related information indicates unavailable competitor data for some stores.

---

## Exploratory Data Analysis

### Sales Distribution

Sales are positively skewed, with most stores generating moderate daily revenue and a smaller number of high-revenue days.

### Promotion Impact

| Promo | Average Sales |
|---------|---------|
| No Promotion | 5,929 |
| Promotion | 8,228 |

**Key Finding**

Promotions increase average sales by approximately **39%**.

---

### Store Type Analysis

| Store Type | Average Sales |
|------------|---------------|
| B | 10,231 |
| C | 6,933 |
| A | 6,925 |
| D | 6,822 |

**Key Finding**

Store Type B significantly outperforms all other store categories.

---

### Assortment Analysis

| Assortment | Average Sales |
|------------|---------------|
| B | 8,639 |
| C | 7,301 |
| A | 6,621 |

**Key Finding**

Assortment B generates the highest average sales.

---

### Monthly Sales Trend

| Month | Average Sales |
|---------|---------|
| December | 8,609 |
| November | 7,189 |
| May | 7,106 |

**Key Finding**

December is the strongest sales month, likely driven by holiday shopping and year-end promotions.

---

### Day of Week Analysis

Highest sales days:

- Sunday
- Monday

Lowest sales day:

- Saturday

---

### Holiday Impact

State holidays produce significantly higher sales than regular days.

School holidays also have a positive impact on revenue.

---

## Feature Engineering

The following features were created:

- Year
- Month

Additional categorical variables were encoded using One-Hot Encoding:

- StateHoliday
- StoreType
- Assortment
- Promo
- SchoolHoliday
- Promo2

---

## Models Evaluated

### Linear Regression

| Metric | Value |
|---------|---------|
| MAE | 2019.31 |
| RMSE | 2766.86 |
| R² | 0.206 |

---

### Decision Tree Regressor

| Metric | Value |
|---------|---------|
| MAE | 1773.87 |
| RMSE | 2437.19 |
| R² | 0.384 |

---

### Gradient Boosting Regressor

| Metric | Value |
|---------|---------|
| MAE | 1819.86 |
| RMSE | 2469.77 |
| R² | 0.367 |

---

### XGBoost Regressor

| Metric | Value |
|---------|---------|
| MAE | 1302.89 |
| RMSE | 1812.86 |
| R² | 0.659 |

---

### Random Forest Regressor

| Metric | Value |
|---------|---------|
| MAE | 740.34 |
| RMSE | 1128.59 |
| R² | 0.868 |

---

## Best Model

🏆 **Random Forest Regressor**

Performance:

- MAE: 740.34
- RMSE: 1128.59
- R²: 0.868

Random Forest significantly outperformed all other models by capturing nonlinear relationships between promotions, holidays, store characteristics, and sales.

---

## Feature Importance

Top sales drivers identified by Random Forest:

1. Store
2. DayOfWeek
3. Promo
4. Month
5. StoreType
6. Year
7. Assortment

Observation:

Store-specific characteristics have a substantial impact on revenue generation.

---

## Key Business Insights

- Promotions increase average sales by approximately 39%.
- Store Type B consistently generates the highest revenue.
- Assortment B outperforms other assortment strategies.
- December is the strongest sales month.
- State holidays significantly boost sales.
- Sales show a positive trend from 2013 to 2015.
- Store-specific factors strongly influence revenue performance.

---

## Business Recommendations

### Promotion Strategy

Deploy promotions strategically during low-demand periods to maximize revenue growth.

### Holiday Planning

Increase inventory and staffing during holiday periods, particularly in November and December.

### Store Optimization

Investigate high-performing Store Type B locations and apply successful practices to other stores.

### Assortment Management

Evaluate expanding Assortment B to additional stores.

### Revenue Growth

Use forecasting outputs to support inventory planning, workforce allocation, and promotional decision-making.

---

## Technologies Used

- Python
- Pandas
- NumPy
- Scikit-learn
- XGBoost
- Matplotlib
- Seaborn

---

## Future Improvements

- Hyperparameter tuning
- Time-series cross validation
- Advanced forecasting techniques
- Deployment using FastAPI and Docker
- Interactive dashboard development using Power BI

---

## Author

**Swarnali Mollick**

Aspiring Data Scientist | Machine Learning Enthusiast | AI Research Student

