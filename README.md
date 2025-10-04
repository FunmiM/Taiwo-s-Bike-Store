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

![Taiwo's Bike Store Dashboard](https://github.com/user-attachments/assets/81cf5a62-e4f9-420a-830a-50db67be7640)




on a.yr = b.yr

