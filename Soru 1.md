# Soru 1)

```SQL
SELECT name, car_new.*, manufacture_new.year as manufacture_year,
array(select as struct p.* replace(TIMESTAMP_ADD(p.date, INTERVAL 3 HOUR) as date) from unnest(purchase) as p) as purchase_new
FROM  dsmbootcamp.sample.semi_structured_hw 
CROSS JOIN UNNEST(car) as car_new
JOIN UNNEST(manufacture) as manufacture_new ON car_new.id = manufacture_new.id;
```
