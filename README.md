# King County Housing — Exploratory Data Analysis

An exploratory data analysis of home sales in King County, WA (including Seattle),
built to answer concrete investment questions for a client and presented as a
short briefing.

## Client & Business Question

**Client:** Charles Christensen — *Seller / Investor*
He wants to reinvest for strong returns and has three open questions:

1. Is there a better **time** to buy or sell?
2. Is **renovating** a property before resale worth the money?
3. Does **location** (specifically, distance to Seattle) drive higher returns?

These were translated into three testable hypotheses (see the notebook for full
detail and results):

| # | Hypothesis |
|---|------------|
| H1 | House prices fluctuate depending on season — lower in winter, higher in summer. |
| H2 | Homes located closer to Seattle allow for a higher return on investment. |
| H3 | For homes renovated in the last ~20 years, the price increase from renovation is largest for homes built before 1950. |

## Key Insights & Recommendations

| # | Insight | Recommendation |
|---|---------|-----------------|
| 1 | **Timing:** Spring prices (avg. $552,782) run ~6% above Winter (avg. $519,613); sales volume peaks in May (2,414 sales) and troughs in January (978 sales). | Buy in **Winter**, sell in **Spring**.  |
| 2 | **Renovation:** Homes built 1950+ see a **+32.17%** price/sqft lift from renovation, vs. only **+0.90%** for homes built before 1950. | Prioritize renovation spend on **post-1950 properties**. |
| 3 | **Location (geographic):** Distance to Seattle alone doesn't predict ROI (r = -0.07, not statistically significant), but ROI by geographic grid cluster ranges from ~2% to ~150%. | Target specific **high-ROI neighborhoods** identified via clustering. |

## Repository Structure

```
.
├── README.md                # you are here
├── 01_assignment.md         # original project brief
├── 02_workflow.md           # suggested workflow for the project
├── 03_fetching_the_data_eda.ipynb # short brief on how to import the data
├── 04_eda.ipynb             # main analysis notebook (data cleaning, EDA, hypothesis testing)
├── column_names.md          # data dictionary / column descriptions
├── King_County_Housing_EDA_Presentation.pdf   # client-facing slides (10-min, non-technical)
└── data/                    # raw data (gitignored — not pushed to GitHub)
    └── eda.csv
```

## The Notebook: `04_eda.ipynb`

The notebook is organized so each hypothesis is self-contained (data prep → test →
visualization → conclusion), and closes with a summary of insights and
recommendations:

0. **Setup** — imports, plotting defaults, helper functions
1. **Data Loading, Cleaning & Feature Engineering** — season tags, distance to
   Seattle, geographic grid clusters, and the repeat-sales ("resale") dataset
   used to measure true ROI
2. **Hypothesis 1 — Seasonality** — checked three ways (raw average, outlier-cleaned
   average, and median) to confirm the seasonal trend isn't an artifact of outliers
3. **Hypothesis 2 — Location & Return on Investment**
4. **Hypothesis 3 — Renovation Value by Home Age**
5. **Summary: Key Insights & Recommendations**

## Data

This project uses the **King County Housing Data**, sourced from the course
database (`eda` schema). The raw CSV (`data/eda.csv`) is **not included in this repository** — to reproduce the analysis, export the joined tables from the database and save them to `data/eda.csv` before running the notebook.

## Presentation

The client-facing summary (`King_County_Housing_EDA_Presentation.pdf`) covers
the same three hypotheses at a high level, without code, for a 10-minute
non-technical walkthrough followed by discussion.