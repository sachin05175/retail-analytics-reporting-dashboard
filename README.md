# Retail Analytics Reporting and Strategic Impact Dashboard

The final stage of a retail analytics project. It turns the results of the [EDA](https://github.com/<your-username>/eda-retail-sales) and [predictive modelling](https://github.com/<your-username>/predictive-retail-analytics) stages into a strategic report, an interactive Plotly Dash dashboard and a presentation storyboard for both technical and non-technical stakeholders.

![Python](https://img.shields.io/badge/Python-3.10%2B-blue)
![Plotly](https://img.shields.io/badge/Plotly-interactive-3f4f75)
![Dash](https://img.shields.io/badge/Dash-dashboard-1f77b4)
![License](https://img.shields.io/badge/License-MIT-green)

> **Note:** the figures in the report are illustrative placeholders. Replace them with your actual results before sharing.

## Table of Contents

- [Project Overview](#project-overview)
- [Key Findings](#key-findings)
- [Strategic Recommendations](#strategic-recommendations)
- [Dashboard Features](#dashboard-features)
- [Project Structure](#project-structure)
- [Installation](#installation)
- [How to Run](#how-to-run)
- [Presentation Structure](#presentation-structure)
- [Communication Strategy](#communication-strategy)
- [Timeline](#timeline)
- [Future Work](#future-work)
- [License](#license)

## Project Overview

A retail business wants to grow revenue without losing profit. This project:

1. Summarizes the analytics process (EDA, then predictive modelling).
2. Converts findings into a clear story with prioritized recommendations.
3. Provides an interactive dashboard that managers can explore without writing code.
4. Plans a presentation tailored to different audiences.

## Key Findings

| # | Finding | Meaning |
|---|---|---|
| 1 | Sales are seasonal with a strong Q4 peak and steady growth | Plan stock and staffing around Q4 |
| 2 | Profit turns negative at high discounts (about 20 to 30%) | Heavy discounting destroys margin |
| 3 | About 20 to 30% of customers generate about 80% of revenue | Protect high-value customers |
| 4 | Some high-revenue sub-categories have thin or negative margins | Review pricing and costs |
| 5 | Forecast model beats the seasonal-naive baseline | Forecasts are reliable enough for planning |
| 6 | Loss-making orders can be flagged with useful recall | Supports a discount-approval rule |

## Strategic Recommendations

| # | Recommendation | KPI |
|---|---|---|
| R1 | Discount-approval rule above the data-supported threshold | Share of loss-making orders, margin |
| R2 | Q4 inventory and staffing plan from the forecast | Forecast MAPE, stock-out rate |
| R3 | Retention program for top customers and high lapse-risk customers | 90-day repeat rate |
| R4 | Pricing and cost review for low-margin, high-revenue sub-categories | Margin by sub-category |
| R5 | Adopt the dashboard and monitor model error monthly | Dashboard usage, model drift |

**Proposed next step:** a 12-week pilot in one region with a control group.

## Dashboard Features

- **KPI tiles:** sales, profit, margin and share of loss-making orders
- **Filters:** region, category and date range update all charts together
- **Trend chart:** monthly sales and profit with hover details
- **Discount analysis:** profit by discount band, showing where losses begin
- **Margin by sub-category:** diverging colors centered on zero
- **Forecast chart:** predictions with an uncertainty band
- **Optional what-if panel:** discount slider showing predicted loss probability

**Design principles:** one message per chart, titles that state the finding, a colorblind-friendly palette, red reserved for risk, and no more than 6 to 8 visuals per page.

## Project Structure

```
retail-analytics-reporting-dashboard/
|-- dashboard/
|   |-- app.py                # Dash layout and callbacks
|   |-- data_prep.py          # data loading and aggregation
|   |-- components.py         # reusable chart functions
|   |-- assets/style.css      # colors and fonts
|   `-- data/                 # cleaned data, forecasts, predictions
|-- notebooks/
|   `-- 01_report_figures.ipynb
|-- reports/
|   |-- final_report.docx
|   |-- kpis.json
|   `-- figures/
|-- presentation/
|   `-- storyboard.md
|-- requirements.txt
|-- README.md
`-- LICENSE
```

## Installation

```bash
# 1. Clone the repository
git clone https://github.com/<your-username>/retail-analytics-reporting-dashboard.git
cd retail-analytics-reporting-dashboard

# 2. Create and activate a virtual environment
python -m venv venv
source venv/bin/activate        # Windows: venv\Scripts\activate

# 3. Install dependencies
pip install -r requirements.txt
```

**requirements.txt**

```
pandas
numpy
plotly
dash
dash-bootstrap-components
kaleido
joblib
scikit-learn
matplotlib
seaborn
jupyter
```

## How to Run

```bash
cd dashboard
python app.py
```

Then open `http://127.0.0.1:8050` in your browser.

To generate report KPIs and static figures, run the notebook in `notebooks/`. Figures can be exported with `fig.write_image('reports/figures/trend.png', scale=3)`.

## Presentation Structure

Narrative arc: **situation, complication, evidence, resolution, action** (about 20 minutes plus questions).

| # | Slide | Message |
|---|---|---|
| 1 | Title and decision needed | We are asking you to approve a pilot |
| 2 | Business context | Revenue is growing, but is profit? |
| 3 | Executive summary | Three findings, three recommendations |
| 4 | Approach | Rigorous method, tested on unseen data |
| 5 | Seasonality and trend | We can plan ahead |
| 6 | Discounts and profit (live demo) | Deep discounts lose money |
| 7 | Products and customers | Revenue is not profit; a few customers matter most |
| 8 | Predictions | Reliable enough to act on, with known limits |
| 9 | Recommendations and impact | Start with quick wins |
| 10 | Pilot plan and risks | A low-risk way to confirm impact |
| 11 | Limitations | What the data cannot tell us |
| 12 | Call to action and Q&A | Approve the pilot and name owners |

## Communication Strategy

- Start with the decision and the audience's question, not the method.
- Translate metrics into outcomes (for example "catches about 2 in 3 loss-making orders").
- Use analogies and plain-language terms, and state uncertainty honestly.
- Use layers: a one-page summary for executives, the report and dashboard for managers, and the notebooks and code for technical readers.

| Audience | Focus |
|---|---|
| Executives | Decisions, money, risk, timeline |
| Business managers | Actions for their area, KPIs, dashboard use |
| Technical team | Validation, reproducibility, limitations |
| Academic reviewers | Hypotheses, rigor, assumptions |

## Timeline

| Phase | Hours |
|---|---|
| Audience and decision framing | 2 |
| Consolidate results | 4 |
| Select findings and recommendations | 3 |
| Draft the report | 6 |
| Static visuals | 3 |
| Dashboard build | 7 |
| Presentation storyboard and slides | 3 |
| Review and testing | 3 |
| Final delivery | 1 |
| **Total** | **32** |

If time is short, a Streamlit or static Plotly HTML dashboard replaces the full Dash app.

## Future Work

- Deploy the dashboard to a cloud service
- Add the model what-if panel and scenario forecasts
- Automate monthly report generation
- Add user authentication and data refresh

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.

## Author

**Your Name**
GitHub: [@your-username](https://github.com/your-username)
