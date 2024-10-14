---
id: t2kzexo64spzvotwvze41hd
title: Parity Checks
desc: ''
updated: 1723636850029
created: 1723636850029
isDir: false
---
### Single org customers - no organization id in resource set

select count(*) 
from resource_set 
join (
	select organization_id, customer_id
	from organization
	where customer_id in (
		select customer_id 
		from organization 
		group by customer_id 
		having count(customer_id) = 1
	)
) org
on resource_set.customer_id = org.customer_id
where resource_group_id = (
	select resource_group_id
	from resource_group
	where resource_group_display_name = 'InsightAppSec Apps')
and resource_set.organization_id is not null;  — is null before, is not null after

27618

### Resources belonging to AppSec resource sets with organization id
We will check only resources that have a uuid as the resource id

select count(*) 
from resource r
join resource_set_resource rsr
on r.id = rsr.resource_id
join resource_set rs
on rsr.resource_set_id = rs.resource_set_id
where r.resource_id similar to '[0-9a-f]{8}-[0-9a-f]{4}-[0-9a-f]{4}-[0-9a-f]{4}-[0-9a-f]{12}'
and rs.organization_id is not null
and rs.resource_group_id = (
	select resource_group_id
	from resource_group
	where resource_group_display_name = 'InsightAppSec Apps')
;

4867	23563


select count(*) 
from resource r
join resource_set_resource rsr
on r.id = rsr.resource_id
join resource_set rs
on rsr.resource_set_id = rs.resource_set_id
where r.resource_id like 'rrn:%'
and rs.organization_id is not null
and rs.resource_group_id = (
	select resource_group_id
	from resource_group
	where resource_group_display_name = 'InsightAppSec Apps')
;

165		3963	


### Check of other bad data

select r.resource_id, rs.resource_set_uuid
from resource r
join resource_set_resource rsr
on rsr.resource_id = r.id
join resource_set rs
on rs.resource_set_id = rsr.resource_set_id
where r.resource_id like 'rrn:appsec%'
and r.resource_id not like '%' || rs.resource_set_uuid
;

"0e76ec78-4fa3-4ad3-a6da-a1cc82c68b4f"	"73cce4c2-212c-45d8-aa31-9bdf41690b43"
"a36477b0-30c1-4f6d-9ca5-64390997c2ed"	"73cce4c2-212c-45d8-aa31-9bdf41690b43"