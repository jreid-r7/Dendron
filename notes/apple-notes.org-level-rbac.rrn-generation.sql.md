---
id: fs9mgmlqvllq3bvexa3114f
title: SQL
desc: ''
updated: 1723636850029
created: 1723636850029
isDir: false
---
select * from resource_set where resource_group_id = (select resource_group_id from resource_group where resource_group_display_name = 'InsightAppSec Apps');

select * from organization;

select * from resource_set join (select organization_id, customer_id
from organization
where customer_id in (select customer_id from organization group by customer_id having *count*(customer_id) = 1)) org
on resource_set.customer_id = org.customer_id
order by resource_set.customer_id asc, resource_set_id asc;

select * from resource_group;

select *count*(*), customer_id from resource_set group by customer_id order by customer_id asc;


select customer_id from organization group by customer_id having *count*(customer_id) = 1 order by customer_id asc;

select customer_id, organization_id from organization where customer_id in (select customer_id from organization group by customer_id having *count*(customer_id) = 1);