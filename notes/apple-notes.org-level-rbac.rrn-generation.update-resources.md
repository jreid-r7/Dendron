---
id: vyh4zttpod17lzbex36gxee
title: Update Resources
desc: ''
updated: 1723636850030
created: 1723636850030
isDir: false
---
create or replace function *update_resource_to_rrn*()
returns text as $$
declare
    resource_rec record;
    resource_cur cursor
        for select o.region, o.external_organization_id, resource.resource_id, resource.id
            from resource
                     join resource_set_resource rsr
                          on resource.id = rsr.resource_id
                     join resource_set rs
                          on rsr.resource_set_id = rs.resource_set_id
                     join organization o on rs.organization_id = o.organization_id
                and resource_group_id = (
			select resource_group_id 
			from resource_group
			where resource_group_display_name = 'InsightAppSec Apps'
		)
                and resource.resource_id similar to '[0-9a-f]{8}-[0-9a-f]{4}-[0-9a-f]{4}-[0-9a-f]{4}-[0-9a-f]{12}';
begin

    open resource_cur;

    loop
        fetch resource_cur into resource_rec;
        exit when not found;

        update resource
        set resource_id = *concat*('rrn:appsec:', resource_rec.region, ':', resource_rec.external_organization_id, ':apps:', resource_rec.resource_id)
        where id = resource_rec.id;
    end loop;

    close resource_cur;

    return 'done';
end; $$
language plpgsql;

begin;
select *update_resource_to_rrn*();
end;

drop function *update_resource_to_rrn*();