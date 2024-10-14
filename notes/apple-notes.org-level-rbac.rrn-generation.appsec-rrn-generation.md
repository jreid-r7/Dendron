---
id: 57ge9jix6a55lchya4c3zex
title: Appsec Rrn Generation
desc: ''
updated: 1723636850029
created: 1723636850029
isDir: false
---
select * from resource where resource_id like 'rrn:appsec%';  
  
select * from resource_set_resource;  
  
select * from resource_set where resource_group_id = 1;  
  
select * from resource_group;  
  
select * from resource join resource_set_resource rsr on resource.id = rsr.resource_id  
join resource_set rs on rsr.resource_set_id = rs.resource_set_id where resource_group_id = 1;  
  
select count(organization_id), o.customer_id from customer join organization o on customer.customer_id = o.customer_id group by o.customer_id having count(organization_id) = 1;  
  
select * from product;  
  
select * from customer;  
  
select * from resource join resource_set_resource rsr on resource.id = rsr.resource_id  
                       join resource_set rs on rsr.resource_set_id = rs.resource_set_id  
         where resource_group_id = 1  
and rs.customer_id in (  
select o.customer_id from customer join organization o on customer.customer_id = o.customer_id group by o.customer_id having count(organization_id) = 1)  
and resource.resource_id like '%-%-%-%-%';-- and resource.resource_id not like 'rrn%';  
  
select * from organization_product;  
  
select * from organization;  
  
select concat('rrn:appsec:', n.region, ':', n.external_organization_id, ':apps:', r.resource_id), * from resource r join resource_set_resource rsr on r.id = rsr.resource_id join resource_set rs on rsr.resource_set_id = rs.resource_set_id join (select o.customer_id, o.organization_id, o.external_organization_id, o.region from customer join organization o on customer.customer_id = o.customer_id group by o.customer_id, organization_id, external_organization_id, region having count(organization_id) = 1) n on rs.customer_id = n.customer_id where rs.resource_group_id = 1 and r.resource_id not like 'rrn%' and rs.organization_id = n.organization_id;  
  
select * from resource join resource_set_resource rsr on resource.id = rsr.resource_id join resource_set rs on rsr.resource_set_id = rs.resource_set_id;

Next steps -
1. Update resource_set with organization_id
2. Ensure rrn generation is once per resource
3. Extract list of resource_id, new rrn
4. Perform update on specific list