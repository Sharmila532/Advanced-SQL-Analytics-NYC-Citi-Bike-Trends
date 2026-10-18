# Advanced SQL Analytics — NYC Citi Bike Trends

Advanced SQL analysis on NYC's public Citi Bike trip dataset (50M+ records) using
Google BigQuery, visualized in both Python and Power BI, focused on window functions,
CTEs, and ranking logic rather than just descriptive aggregation.

## Business Question
How has ridership trended over time, which stations drive the most volume, and how
does trip duration behavior differ between subscriber and casual riders?

## Dataset
`bigquery-public-data.new_york_citibike.citibike_trips` — a public BigQuery dataset,
queried directly with no download required.

## Tools
Google BigQuery (SQL), Python (BigQuery client, Pandas), Seaborn/Matplotlib, Power BI, Google Colab

## SQL Techniques Demonstrated
- **Window functions** — `LAG()` for month-over-month % change, `RANK()` for station
  leaderboards, `NTILE()` for quartile-based duration segmentation
- **CTEs (`WITH` clauses)** — structuring multi-step logic into readable queries
- **Safe aggregation** — `SAFE_DIVIDE()` to avoid divide-by-zero errors on real data
- **Date truncation & grouping** — `DATE_TRUNC()` for monthly trend analysis

## Workflow
1. Connected to BigQuery's free public dataset via the Python client in Colab
2. Wrote progressively more advanced SQL: basic aggregation → trend analysis with
   window functions → station rankings → rider-segment duration analysis
3. Pulled query results into Pandas for visualization
4. Exported result sets as CSVs and built a Power BI dashboard on top (see build steps above)

## Key Findings
- e.g. Ridership peaks in [month] and drops sharply in winter months
- [Station name] is the busiest start station by a wide margin
- Subscribers take meaningfully shorter trips than casual riders on average

## Repo Structure
