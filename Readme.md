# 📱 Google Play Store Market Intelligence

**Exploratory Data Analysis & Business Intelligence on 10,000+ Play Store Apps and 60,000+ User Reviews**

[![Python](https://img.shields.io/badge/Python-3.x-blue.svg)](https://www.python.org/)
[![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458.svg)](https://pandas.pydata.org/)
[![Power BI](https://img.shields.io/badge/Power%20BI-Dashboard-F2C811.svg)](https://powerbi.microsoft.com/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

---

## 📌 Overview

The Google Play Store hosts millions of applications across dozens of categories, making it highly competitive for developers and difficult for businesses to identify what actually drives app success. This project combines **structured app metadata** with **unstructured user review sentiment** to uncover the measurable factors behind ratings, installs, pricing strategy, and user engagement — then translates those findings into an interactive Power BI dashboard for stakeholder reporting.

## 🎯 Problem Statement

Despite the vast availability of Play Store data, developers and businesses often lack clarity on what separates high-performing apps from average ones. Does a higher rating actually drive more installs? How does pricing affect downloads? Which categories dominate the market, and how well does user sentiment align with star ratings? This project transforms raw, duplicate-laden, inconsistently-typed Play Store data into structured insights that answer these questions with evidence, not assumptions.

**Business Objective:** Identify the key factors influencing app success — category, rating, reviews, price, size, and sentiment — to provide data-driven recommendations that help developers optimize pricing, improve user satisfaction, and increase visibility.

---

## 🗂️ Dataset

Two linked datasets were used:

| Dataset | Rows (raw) | Columns | Description |
|---|---|---|---|
| `Play Store Data.csv` | 10,841 | 13 | App-level metadata: category, rating, reviews, size, installs, type, price, content rating, genre, last updated, version info |
| `User Reviews.csv` | 64,295 | 5 | User review text, sentiment label, sentiment polarity, and subjectivity per app |

### Data Quality Issues Identified & Resolved

| Issue | App Data | Review Data |
|---|---|---|
| Duplicate rows | 483 removed | 33,616 removed |
| Missing `Rating` | 1,474 rows | — |
| Missing `Translated_Review` / sentiment fields | — | ~26,860 rows |
| Invalid data (e.g. `Rating` = 19 on a 1–5 scale) | Identified & corrected | — |
| Clean dataset size after processing | **10,358 rows** | **30,679 rows** |

---

## 🛠️ Tech Stack

- **Language:** Python (Pandas, NumPy)
- **Visualization:** Matplotlib, Seaborn
- **Business Intelligence:** Power BI (DAX, Power Query)
- **Environment:** Jupyter / Google Colab

---

## 🔍 Analysis Performed

1. **Data Cleaning** — deduplication, null handling, type correction, invalid-value detection (e.g. out-of-range ratings)
2. **Univariate Analysis** — rating distribution, install segments, free vs. paid split, pricing bands, sentiment distribution
3. **Bivariate Analysis** — rating vs. install segment, rating vs. sentiment polarity, rating vs. review count, price vs. rating
4. **Correlation Analysis** — full correlation matrix and pair plot across ratings, installs, reviews, price, size, and sentiment
5. **Category & Recency Analysis** — top app categories by volume, update recency as an engagement signal

---

## 💡 Key Insights

- **Ratings cluster tightly:** Average rating is **4.19** (median 4.3), with most apps falling between 4.0–4.5 — indicating high competition and minimal differentiation on rating alone.
- **Installs are highly skewed:** A small number of apps dominate total installs while the majority sit at low install counts (long-tail distribution).
- **Pricing follows a clear psychological band:** ~79% of paid apps are priced under $5 (37% Budget <$2, 42% Standard $2–$5), with only ~21% in Premium/High-End tiers ($5+).
- **Reviews strongly predict installs:** Reviews and Installs show the strongest correlation in the dataset (**r = 0.63**), confirming that engagement volume scales with reach.
- **Sentiment moderately aligns with ratings:** Sentiment polarity and star rating correlate at **r ≈ 0.21** — sentiment adds signal but doesn't fully explain rating behavior.
- **Rating alone doesn't explain growth:** Average ratings are similar (~4.0–4.4) across install segments from "Starter" to "Market Leader," meaning marketing, category dominance, and early momentum matter as much as app quality.

## 🧭 Conclusion

Growth on the Google Play Store is driven more by **scalable user acquisition and engagement** than by star ratings in isolation. Review generation and sentiment monitoring are strong secondary signals for sustained performance, but no single metric determines success — it's a combination of pricing strategy, category positioning, and continuous user experience improvement.

---

## 📊 Power BI Dashboard

The cleaned dataset from this EDA feeds an interactive Power BI dashboard featuring:
- DAX measures for category-wise install and rating trends
- Drill-down filters by category, pricing tier, and content rating
- Install-to-rating correlation visuals for business stakeholder reporting

*(Dashboard screenshots in `/docs/screenshots`)*

---

## 📁 Project Structure

```
playstore-market-intelligence/
├── data/
│   ├── Play Store Data.csv
│   └── User Reviews.csv
├── notebooks/
│   └── Playstore_app_analysis.ipynb
├── docs/
│   └── screenshots/
├── dashboard/
│   └── playstore_dashboard.pbix
└── README.md
```

---

## 🚀 How to Run

```bash
git clone https://github.com/suryanshu-g/<repo-name>.git
cd <repo-name>
pip install pandas numpy matplotlib seaborn jupyter
jupyter notebook notebooks/Playstore_app_analysis.ipynb
```

---

## 👤 Author

**Suryanshu Gupta**
[GitHub](https://github.com/suryanshu-g) · [LinkedIn](https://www.linkedin.com/in/suryanshugupta24/)
