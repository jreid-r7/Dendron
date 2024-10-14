---
id: 0wkxm1uh7tvxe4r2ex5vswf
title: Update Resource Sets
desc: ''
updated: 1723636850029
created: 1723636850029
isDir: false
---
create or replace function *update_resource_sets*()
returns text as $$
declare
    org_rec record;
    org_cur cursor
        for select customer_id, organization_id
            from organization
            where customer_id in
                  (select customer_id
                   from organization
                   group by customer_id
                   having *count*(customer_id) = 1);
begin

    open org_cur;

    loop
        fetch org_cur into org_rec;
        exit when not found;

        update resource_set
        set organization_id = org_rec.organization_id
        where resource_set.customer_id = org_rec.customer_id;
    end loop;

    close org_cur;

    return 'done';
end; $$
language plpgsql;

begin;
select *update_resource_sets*();
end;

drop function *update_resource_sets*();