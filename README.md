# plp-da-a4-student-eda-and-board-report

**PLP Data Analytics · Assignment 4 · Week 4**

---

## Repository Summary

This repository contains two end-to-end analyst engagements submitted as a single deliverable:

| Engagement | Client | Deliverable |
|-----------|--------|-------------|
| **1 · County Education Office** | County Director of Education | Exploratory Data Analysis report (`student_eda.ipynb`) identifying at-risk learners and factors driving performance |
| **2 · Duka Electronics Board** | CEO / Board members | One-page visual report (`board_report.ipynb` → `reports/duka_board_report.png`) and a live Looker Studio dashboard |

---

## How to Run

### Prerequisites

```bash
# 1. Clone the repository
git clone https://github.com/<username>/plp-da-a4-student-eda-and-board-report
cd plp-da-a4-student-eda-and-board-report

# 2. Create and activate a virtual environment (recommended)
python -m venv .venv
# Windows:
.venv\Scripts\activate
# macOS/Linux:
source .venv/bin/activate

# 3. Install dependencies
pip install -r requirements.txt

# 4. (Optional) Regenerate the CSV datasets
python generate_data.py
```

### Run the Notebooks

Open each notebook in Jupyter Lab / Jupyter Notebook / VS Code and **restart the kernel, then run all cells from top to bottom**:

```bash
jupyter lab  # opens jupyter lab in the browser
```

```bash
jupyter notebook  # opens jupyter notebook in the browser
```

| Notebook | Purpose | 
|----------|---------|
| `student_eda.ipynb` | Full EDA for Engagement 1 |
| `board_report.ipynb` | Board report charts + makeover for Engagement 2 |

All outputs (charts, printed tables) are committed to the repository so reviewers can open the notebooks without running them.

---

## Five Key EDA Insights

1. **Attendance is the strongest predictor of academic performance** — the correlation between `attendance_rate` and `average_score` is the highest among all non-subject variables. Improving chronic absenteeism should be the first priority of the support programme.

2. **Each additional hour of study is associated with approximately 2 extra score points** — the `np.polyfit` trend line confirms a positive relationship (R² ≈ 0.14), though the effect is smaller than attendance and cannot be assumed causal.

3. **Private school students outscore public school students by ~6 points on average, and this gap persists across all attendance bands and study-hour quartiles** — pivot table analysis confirms the advantage is not explained by student behaviour alone, suggesting a resource or instruction quality difference.

4. **Turkana has the highest share of "At Risk" learners (scoring below 60)** — geographic targeting of the support budget toward Turkana would address the most concentrated need.

5. **The score distribution is approximately normal with most students in the "Meeting" band (60–75)** — a focused intervention on the At Risk tail (~25% of students) could meaningfully shift the county average without requiring system-wide changes.

---

## Board Report — Duka Electronics H1 2026

The one-page board report is saved at:

```
reports/duka_board_report.png
```

![Duka Electronics H1 2026 Board Report](reports/duka_board_report.png)

---

## Board Summary (150 words)

Duka Electronics closed H1 2026 with 1,000 orders across five branches and three sales channels. The Nairobi branch alone contributed roughly 40% of total revenue, creating a concentration risk the board should address. Laptops account for the majority of revenue despite low order volumes, confirming that high-ticket items are the profit engine. Online ordering delivers the highest average order value of the three channels and warrants accelerated investment. Monthly revenue trended upward from March to June, recovering from a February dip, suggesting Q1 seasonality that the team should plan for in 2027. Mombasa and Kisumu show proportionally higher average order values relative to their order counts, indicating untapped demand in those markets. For H2 2026, the board should approve targeted promotional campaigns in Mombasa and Kisumu, increase the digital marketing budget to grow online share, and consider a Laptop upselling programme across all branches.

---

## Repository Structure

```
plp-da-a4-student-eda-and-board-report/
├── generate_data.py          # Synthetic data generators (seed 55 & 2026)
├── student_performance.csv   # 1,200-student dataset (Engagement 1)
├── duka_sales.csv            # 1,000-order dataset (Engagement 2)
├── student_eda.ipynb         # Full EDA notebook — Engagement 1
├── board_report.ipynb        # Board report notebook — Engagement 2
├── dashboard.md              # Looker Studio link + screenshots
├── requirements.txt          # Python dependencies
├── README.md                 # This file
├── figures/                  # Exported chart images
│   ├── score_hist.png
│   ├── county_bar.png
│   ├── school_boxplot.png
│   ├── trend_study_vs_score.png
│   ├── chart1_monthly_revenue.png
│   ├── chart2_branch_revenue.png
│   ├── chart3_product_revenue.png
│   ├── chart4_channel_revenue.png
│   ├── before.png
│   └── after.png
└── reports/
    └── duka_board_report.png  # One-page board report
```

---

## Libraries Used

- `pandas` — data manipulation and pivot tables
- `numpy` — numerical operations and `np.polyfit` trend line
- `matplotlib` — charting (histograms, bar charts, box plots, scatter plots)
- `seaborn` — correlation heatmap and styled visuals
- `scipy` — statistical tests (t-test, Pearson correlation)

---

*Submitted by: deendiran | PLP Data Analytics Cohort | November 2026*
