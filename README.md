# 1Toolkit

A fully browser-based statistical analysis toolkit. No installation, no backend, no data ever leaves your computer. Open the HTML file and start analysing.

**→ [Live Demo](https://github.com/Syed-Faizani/Tredri-Toolkit/blob/main/index.html)** 

---

## What it is

Tredri Toolkit is a single self-contained HTML file that covers the full workflow of an introductory statistics course — from loading raw data to running hypothesis tests and exporting a PDF report. Every calculation runs locally in JavaScript; nothing is sent to a server.

Built as a final project for *Methods and Tools of Data Analysis* at SRH University Leipzig.

---

## Features

### Data Input
- Drag-and-drop CSV import
- Paste directly from Excel or Google Sheets (tab-separated auto-detection)
- Manual cell editing, add/remove rows and columns inline
- One-click load of the built-in **Students Performance in Exams** demo dataset (200 rows, 8 columns)
- Column types: **Metric**, **Ordinal**, **Nominal** — hover over any badge for a definition

### Analysis Pages

| Page | What it does |
|---|---|
| **Data Table** | Import, edit, and type-label your dataset |
| **Descriptive Stats** | Mean, median, mode, std dev, variance, skewness, kurtosis, min/max, Q1/Q3, IQR, CV |
| **Frequency Tables** | Absolute counts, relative %, cumulative % for nominal/ordinal columns |
| **Charts** | Histogram, box plot, bar chart, scatter plot (auto-sampled for large datasets) |
| **Normality Tests** | Shapiro-Wilk statistic, Q-Q plot, histogram overlay, pass/fail verdict |
| **Distributions** | PDF/CDF overlays for Normal, t, χ², F, and Uniform; Central Limit Theorem simulator |
| **Correlation** | Pearson r (metric pairs) and Spearman ρ (ordinal pairs), colour-coded heatmap |
| **Regression** | Simple linear regression: slope, intercept, R², p-value, scatter with fitted line |
| **Hypothesis Tests** | Full parametric and non-parametric suite (see below) |
| **User Guide** | In-app quick-start, feature table, and worked example |

### Hypothesis Tests

**Parametric**
- One-sample t-test
- Independent samples t-test (Welch's)
- Paired t-test
- Chi-square test of independence
- One-way ANOVA (with F-statistic and η² effect size)
- Two-way ANOVA
- One-sample Z-test
- Two-sample Z-test

**Non-Parametric** (tabs inside Hypothesis Tests)
- Mann-Whitney U (with rank-biserial r)
- Wilcoxon Signed-Rank (paired and one-sample modes)
- Kruskal-Wallis H (with ε² effect size)
- Friedman test (with Kendall's W)
- Spearman rank correlation with significance test
- Fisher's Exact test (2×2, exact two-sided p-value)

**Smart normality guidance:** after running a normality test, the hypothesis page automatically marks parametric tabs with ⚠ N/A when data is non-normal, and NP tabs with ✅ N/A when data is normal — so you always run the right test.

### Export
- Print / Save as PDF — exports all analysis pages in sequence as a single document

---

## Demo Dataset

**Students Performance in Exams** — [Kaggle source](https://www.kaggle.com/datasets/spscientist/students-performance-in-exams)

| Column | Type | Description |
|---|---|---|
| Ethnicity Group | Nominal | Race/ethnicity group A–E |
| Gender | Nominal | male / female |
| Lunch | Nominal | standard / free/reduced |
| Test Prep | Nominal | none / completed |
| Parental Education | Ordinal | some high school → master's degree |
| Math Score | Metric | 0–100 |
| Reading Score | Metric | 0–100 |
| Writing Score | Metric | 0–100 |

200 rows loaded (stratified sample from n=1,000 original). Good for: ANOVA across groups, correlation between scores, regression (predict writing from reading), chi-square (gender × test prep).

---

## How to Use

### Option 1 — GitHub Pages (recommended for sharing)

1. Fork or upload this repository
2. Go to **Settings → Pages → Source → main branch → / (root)**
3. Your toolkit is live at `https://your-username.github.io/tredri-toolkit/`

### Option 2 — Run locally

Download `tredri-toolkit.html` and open it in any modern browser. No server needed.

```
git clone https://github.com/your-username/tredri-toolkit.git
cd tredri-toolkit
open tredri-toolkit.html   # macOS
# or double-click the file on Windows/Linux
```

> Requires an internet connection for Chart.js, Tabler Icons, and Google Fonts (loaded from CDN). All statistical computation is local.

---

## Example Analysis Walkthrough

1. **Load data** → Click *Load Students Dataset* on the Data Table page
2. **Set types** → Verify column types (already pre-set: metric scores, nominal/ordinal categories)
3. **Descriptive overview** → Go to Descriptive Stats, select *Math Score*. Note mean ≈ 65, std dev ≈ 15, slight left skew
4. **Check normality** → Normality Tests → select *Math Score* → check Shapiro-Wilk and Q-Q plot
5. **Group comparison** → Hypothesis Tests → One-way ANOVA → metric: *Math Score*, group: *Ethnicity Group* → run. With 5 groups (A–E), ANOVA tests whether mean scores differ significantly
6. **Correlation** → Correlation page → inspect the Pearson matrix for Math/Reading/Writing scores (expect r > 0.8)
7. **Regression** → Regression page → X: *Reading Score*, Y: *Writing Score* → fit the line, check R²
8. **Export** → Print button → Save as PDF

---

## Repository Structure

```
tredri-toolkit/
│
├── tredri-toolkit.html   ← The entire toolkit (single file)
└── README.md
```

Everything — HTML, CSS, and JavaScript — lives in the single `.html` file. There are no build steps, no `node_modules`, no dependencies to install.

---

## Technical Notes

- **Pure vanilla JS** — no frameworks, no bundler
- **Chart.js 4.4.1** for all visualisations
- **Tabler Icons** for the UI icon set
- All statistical functions (Shapiro-Wilk, t-distribution CDF, chi-square p-values, normal distribution approximations) are implemented from scratch in JavaScript
- The scatter plot uses stratified sampling when n > 120 to keep charts readable while preserving distribution shape

---

## Authors

**Syed Marghoobul Hasan Faizani** — 100008160  
**Kavin Ganapathy**  
**Keethana Kumbar**  
**Yasser Bouyaddid**  

SRH University Leipzig · Methods and Tools of Data Analysis · 2025/26

---

## Dataset Credit

Kaggle — [Students Performance in Exams](https://www.kaggle.com/datasets/spscientist/students-performance-in-exams) by spscientist. Public domain.

---

## License
© 2025 Syed Marghoobul Hasan Faizani  
SRH University Leipzig — M.Sc. Big Data and Artificial Intelligence  
All rights reserved. Built as part of coursework for Tools and Methods of Data Analysis.
