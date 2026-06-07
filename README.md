# 🛒 Olist E-Commerce — EDA & Business Intelligence

![Python](https://img.shields.io/badge/Python-3.12-blue) ![Pandas](https://img.shields.io/badge/Pandas-2.x-green) ![SQLite](https://img.shields.io/badge/SQLite-in--memory-orange) ![Matplotlib](https://img.shields.io/badge/Matplotlib-Seaborn-red)

> Exploratory Data Analysis and Business Intelligence on 100,000+ real Brazilian e-commerce orders from Olist (2016–2018).

---

## 📌 Objective

Uncover patterns, trends, and relationships within the data and develop proficiency in SQL for data extraction and basic dashboarding.

---

## 📁 Dataset

**Source:** [Brazilian E-Commerce Public Dataset by Olist](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce) — Kaggle

| Table | Rows | Description |
|---|---|---|
| orders | 99,441 | Order status and timestamps |
| order_items | 112,650 | Products per order with price |
| order_payments | 103,886 | Payment method and value |
| order_reviews | 99,224 | Customer review scores |
| customers | 99,441 | Customer location |
| sellers | 3,095 | Seller location |
| products | 32,951 | Product details and category |
| geolocation | 1,000,163 | Zip code coordinates |

---

## 🔍 Analysis Steps

### 1. Descriptive Statistics & Univariate Analysis
- Summary statistics for price, freight, payment value, and review score
- Visualizations: price distribution, review score histogram, top product categories, customer states, payment type breakdown

**Key Findings:**
- Average order value: R$120 (median R$74 — heavily right-skewed)
- 73.7% of customers pay by credit card
- São Paulo accounts for ~43% of all orders
- bed/bath/table and health/beauty are the top revenue categories

### 2. SQL Business Questions
Seven business questions answered using SQL on an in-memory SQLite database:

| # | Question | Key Finding |
|---|---|---|
| Q1 | Top categories by revenue | beleza_saude leads at R$1.26M |
| Q2 | Monthly order trend | Orders grew 27x from Oct 2016 to Nov 2017 |
| Q3 | Top states by revenue | SP generates 3x more revenue than RJ |
| Q4 | Best rated categories | Books and luggage score highest |
| Q5 | Payment method analysis | Credit card: R$12.5M total revenue |
| Q6 | Top sellers | Top seller generated R$229K from SP |
| Q7 | Late delivery by state | AL has 23.9% late delivery rate |

### 3. Multivariate Analysis & Correlation
- Correlation heatmap across price, freight, payment value, review score, installments
- Scatter plot: price vs freight value
- Review score vs price range analysis
- Monthly revenue trend (area chart)

**Key Findings:**
- Review score has near-zero correlation with price (-0.00) — customers don't rate based on spend
- Price and payment value are strongly correlated (0.74)
- Review score is flat across all price ranges — satisfaction is delivery/service driven

### 4. KPI Dashboard Mock-up
A static dark-themed dashboard summarizing the most important business KPIs:

| KPI | Value |
|---|---|
| Total Revenue | R$ 20,579,664 |
| Total Orders | 99,441 |
| Avg Review Score | 4.02 / 5 |
| Avg Delivery Time | 12.1 days |
| Total Sellers | 3,095 |
| Total Customers | 99,441 |

---

## 📊 Output Charts

| File | Description |
|---|---|
| `outputs/01_univariate_analysis.png` | Distributions and categorical breakdowns |
| `outputs/02_sql_analysis.png` | SQL business question visualizations |
| `outputs/03_multivariate_analysis.png` | Correlation heatmap and scatter plots |
| `outputs/04_dashboard.png` | KPI dashboard mock-up |

---

## 🛠️ Tech Stack

- **Python 3.12**
- **Pandas** — data loading, cleaning, merging
- **NumPy** — numerical operations
- **Matplotlib / Seaborn** — visualizations
- **SQLite3** — in-memory SQL queries
- **Jupyter Notebook** — analysis environment

---

## 🚀 How to Run

```bash
# Clone the repo
git clone https://github.com/YOUR_USERNAME/olist-eda.git
cd olist-eda

# Install dependencies
pip install pandas numpy matplotlib seaborn jupyter

# Download the dataset from Kaggle and place CSVs in data/
# https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce

# Launch the notebook
jupyter notebook notebooks/eda_analysis.ipynb
```

---

## 📂 Project Structure

```
Task 2/
├── data/                    # Raw CSV files (not tracked in git)
├── notebooks/
│   └── eda_analysis.ipynb   # Main analysis notebook
├── outputs/                 # Saved chart images
└── README.md
```

---

## 💡 Business Recommendations

1. **Focus marketing on SP, RJ, MG** — these 3 states drive 70%+ of revenue
2. **Investigate AL and MA delivery logistics** — 20%+ late delivery rates hurt satisfaction
3. **Review score is not price-driven** — invest in delivery speed, not discounts
4. **health/beauty and watches are high-value categories** — worth dedicated promotions
5. **Credit card installments drive higher order values** — promote installment options

---

*Part of the ApexPlanet Software Internship — Task 2*
