# Movies Data Analysis

## 📌 Project Overview
An exploratory analysis of a large-scale movie industry dataset (~1M titles spanning 1950–2025), examining how production economics, ratings, and output volume have evolved over 75 years — and whether spending more on a film actually improves its return on investment. The analysis moves from historical trend-lines into a budget/ROI correlation study, genre-level profitability, and director consistency ranking.

> **Dataset note:** The source dataset is synthetically generated (titles, directors, and actor names are procedurally created) and is used here to demonstrate an end-to-end analytical workflow — cleaning, feature engineering, correlation analysis, and insight synthesis — rather than to draw conclusions about the real film industry.

## ❓ Business Questions
1. How have budgets, box-office revenue, ratings, and production volume trended over time?
2. Does a bigger production budget improve return on investment (ROI)?
3. Which genres are the most popular and profitable?
4. Which directors consistently deliver both high ratings and commercial success?

## 🔑 Key Findings
- **Per-film economics have stayed flat for 75 years.** Average budget ($9.3M–$11.0M) and average global box office (~$27–30M) in 2025 are nearly identical to 1950 levels.
- **Industry growth has come entirely from volume**, not per-film performance — production scaled roughly 10x, from 2,432 films in 1950 to 23,809 in 2025.
- **Bigger budgets buy bigger revenue, not better returns.** Budget correlates strongly with absolute box-office revenue (**r = 0.90**) but has virtually no relationship with ROI (**r = -0.001**) — a critical distinction for capital allocation decisions.
- **Drama leads on total profit and volume** ($4.34T cumulative profit, 250K+ titles), but this reflects scale rather than superior quality — average ratings are nearly flat (~6.49–6.50) across every genre.
- **Director quality is tightly clustered.** Even top-ranked directors (filtered to 4+ films to exclude one-hit outliers) top out around a 6.5 average rating, reflecting the dataset's narrow overall rating distribution.

## 🛠️ Methodology
1. **Data Loading & Validation** — Loaded ~1M-row dataset, verified zero missing values before proceeding.
2. **Data Formatting** — Converted `ReleaseDate` to datetime and `Genre` to a categorical type for downstream aggregation efficiency.
3. **Feature Engineering** — Derived `Profit` (Global Box Office − Budget) and `ROI` (%) per title.
4. **Trend Analysis** — Aggregated budget, revenue, rating, and volume by release year to identify long-run patterns.
5. **Correlation Analysis** — Measured Pearson correlation between budget and both revenue and ROI to separate scale effects from efficiency.
6. **Genre & Director Analysis** — Exploded multi-genre records and grouped by genre/director to rank profitability and consistency, applying a minimum-title threshold to avoid small-sample bias.

## 🛠️ Tools & Libraries
- **Python** — pandas
- **Visualization** — Matplotlib
- **Environment** — Jupyter Notebook

## 📁 Repository Structure
```
Movies-Data-Analysis/
├── notebooks/
│   └── Movies_Data_Analysis.ipynb     # Full analysis notebook
├── data/
│   └── movies_dataset.csv             # Source data (or link if too large to version)
├── images/                            # Exported chart screenshots for README
├── requirements.txt                   # Python dependencies
├── .gitignore
└── README.md
```

## 📊 Sample Visuals
*(Export key charts as PNGs from the notebook and reference them here once uploaded)*

```markdown
![Average Budget Over Time](images/avg_budget_over_time.png)
![Budget vs ROI](images/budget_vs_roi.png)
![Genre Profitability](images/genre_profitability.png)
```

## 🚀 Business Value
This workflow demonstrates how a studio or investment team could:
- **Separate scale from efficiency** when evaluating a production slate — a bigger budget is not a proxy for a better return
- **Benchmark genre strategy** on profit contribution *and* volume, not rating alone, since rating differences across genres are marginal
- **Evaluate director track records** using a minimum sample-size threshold, avoiding false signal from one-off breakout films

## Author
Data Analytics Portfolio Project — demonstrating data cleaning, feature engineering, correlation analysis, and business-focused insight synthesis in Python.
