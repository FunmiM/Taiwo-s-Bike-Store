Taiwo's Bike Share Pricing Analysis

Tools: SQL, Power BI
Domain: Business Intelligence / Pricing Strategy


1. Problem Statement

Toman Bike Share wanted to determine whether it could increase ride prices without significantly affecting customer usage or revenue. The main goal of this analysis was to identify the relationship between pricing, ride frequency, and revenue growth to support data-driven pricing decisions.


2. Process / Approach

Step 1: Data Understanding & Requirements

Began with a mock business request to evaluate price sensitivity.

Defined key questions:

How have ride trends changed over time?

How does pricing affect total revenue and ridership?

When are the peak and off-peak usage periods?



Step 2: Data Preparation & SQL Analysis

Imported the company’s historical trip data into SQL Server.

Cleaned and structured the data into relational tables (fact and dimension models).

Wrote SQL queries to calculate:

Total rides and revenue per month

Average fare per ride

Growth and seasonality trends



Step 3: Data Visualization in Power BI

Connected the SQL database to Power BI for reporting.

Used Power Query to transform and model the dataset.

Designed an interactive dashboard displaying key KPIs:

Monthly rides & revenue

Average trip duration

Revenue by day of week and hour of day

Pricing trend analysis



Step 4: Interpretation & Recommendation

Examined visual trends to understand user behavior and price sensitivity.

Derived insights to inform strategic pricing decisions.



3. Tools Used

SQL Server / SSMS – For data cleaning, transformation, and KPI generation.

Power BI – For dashboard creation, visualization, and insight storytelling.

Power Query – For advanced data transformation and modeling.



4. Insights & Results

Seasonal Usage: Ridership peaks during summer months and drops during winter, suggesting strong seasonal demand.

Revenue Growth: Revenue showed consistent growth year-over-year despite minor price adjustments.

Optimal Pricing Range: Analysis indicated that a 5–8% fare increase could be introduced with minimal decline in ride frequency.

Actionable Recommendation: Implement a moderate fare increase during high-demand months, and maintain current pricing during low seasons to balance revenue and customer satisfaction.



Outcome

The final Power BI dashboard provided clear insights into user behavior, seasonality, and pricing impact, allowing Taiwo's Bike Share to make informed, data-backed pricing decisions.


![Taiwo's Bike Store Dashboard](https://github.com/user-attachments/assets/81cf5a62-e4f9-420a-830a-50db67be7640)




# Taiwo-s-Bike-Store
SQL project analyzing multi-year bike share data. Used CTEs to combine datasets, joined cost data, and calculated revenue &amp; profit. Explored seasonal, hourly, and rider-type trends to provide business insights.
with CTE as (
SELECT * FROM bike_share_yr_0
union
SELECT * FROM bike_share_yr_1)


select 
dteday,
season,
a.yr,
weekday,
hr,
rider_type,
riders,
price,
COGS, 
riders*price as Revenue,
riders*(price -COGS) as profit
from CTE a
left join cost_table b
on a.yr = b.yr


![Taiwo's Bike Store Dashboard](https://github.com/user-attachments/assets/81cf5a62-e4f9-420a-830a-50db67be7640)





