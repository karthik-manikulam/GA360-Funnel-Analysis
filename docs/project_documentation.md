# GA360 Funnel Analysis | Google Merchandise Store

An end-to-end web analytics project using the Google Analytics Sample Dataset in BigQuery, Python/Jupyter Notebook and Power BI. It explores sessions, users, product interactions, traffic channels, conversion behaviour and revenue across **August 2016 to August 2017**.

> **Portfolio note:** Dashboard screenshots are in the [`dashboard/`](dashboard/) folder. The `.pbix` file and raw data exports are intentionally excluded from Git because they are large and may contain data that should not be redistributed.

## Table of Contents

- [Dashboard Preview](#dashboard-preview)
- [Project Objectives](#project-objectives)
- [Dataset](#dataset)
- [Technology Stack](#technology-stack)
- [Workflow](#workflow)
- [Dashboard Highlights](#dashboard-highlights)
- [Business Observations](#business-observations)
- [Recommendations](#recommendations)
- [Limitations](#limitations)
- [Getting Started](#getting-started)
- [Repository Structure](#repository-structure)
- [Security](#security)

 ## Project Objectives

1. Measure the journey from page views and product interactions through checkout and purchase.
2. Understand how conversion performance changes over time.
3. Compare new and returning customer conversion behaviour.
4. Explore traffic acquisition channels and device-level conversion.
5. Identify products that attract interactions but have relatively low purchase rates.
6. Translate the analysis into practical e-commerce recommendations.

## Dataset

The analysis uses the Google Analytics Sample Dataset in BigQuery:

```
bigquery-public-data.google_analytics_sample
```

It represents Google Merchandise Store web analytics data. The project uses session-level and nested hit/product information. See the notebook for the exact tables, fields, date filters and transformations.

## Technology Stack

| Tool / Technology | Purpose |
| --- | --- |
| Google BigQuery | Querying the public Google Analytics sample dataset |
| SQL | Extracting and aggregating sessions, hits and product interactions |
| Python | Data processing and analysis |
| Jupyter Notebook | Reproducible analysis and documentation |
| Pandas / NumPy | Data manipulation |
| Matplotlib / Seaborn | Exploratory visualisation |
| Power BI | Interactive dashboard and business reporting |

## Workflow

1. **Data extraction:** query the public GA sample dataset in BigQuery using SQL.
2. **Data preparation:** select relevant session, hit and product fields; flatten nested records where needed; prepare analysis-ready tables.
3. **Analysis:** explore traffic sources, user behaviour, product interactions, funnel progression and revenue.
4. **Visualisation:** build exploratory charts in Python and interactive report pages in Power BI.
5. **Recommendations:** use observed funnel drop-offs and customer/product patterns to identify areas for investigation and optimisation.


## Dashboard Highlights

Values shown in the supplied dashboard screenshots for the selected report period and filter state:

| Metric | Dashboard value |
| --- | --- |
| Sessions | 904K |
| Unique visitors | 714K |
| Conversion rate | 1.28% |
| Total revenue | $1.54M |
| Average order value | $133 |
| New customer conversion rate | 0.48% |
| Returning customer conversion rate | 7.09% |
| Average session duration | 2m 11s |

> **Important:** Slicers, date ranges, metric definitions and report filters can change these results. Use the Power BI report and notebook as the source of truth for exact calculations.

## Business Observations

- Overall purchase conversion is **1.28%**, so only a small share of sessions reach purchase.
- The funnel shows substantial loss between page view and product click, making product discovery and engagement a useful area to investigate.
- Returning-customer conversion (**7.09%**) is far higher than new-customer conversion (**0.48%**), suggesting an opportunity to study onboarding, trust signals and first-purchase incentives.
- Organic Search is the largest session source in the channel chart.
- The "high interest, low purchase" table highlights products with many interactions but comparatively low purchase percentages, which may warrant review of product pages, pricing, availability and checkout paths.

These are descriptive observations, not proof of causation. Validate them against the notebook's calculations and relevant segments before making business decisions.

## Recommendations

1. Improve product discovery by examining the page-view to product-click drop-off.
2. Lift new-visitor conversion through onboarding, trust signals and first-purchase incentives.
3. Review high-interest, low-purchase products for page, pricing, availability and checkout issues.
4. Compare conversion across traffic channels and device types.
5. Investigate top exit pages and the largest funnel drop-offs.
 

Never commit service-account JSON files, API keys, access tokens, `.env` files or private project configuration. Keep credential files in `.gitignore`, and never paste credentials into notebook cells or outputs.
