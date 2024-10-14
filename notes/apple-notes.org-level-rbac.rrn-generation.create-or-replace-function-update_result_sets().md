---
id: 4d576kcbqfdgm7j67hctlf5
title: Create or Replace Function Update_result_sets()
desc: ''
updated: 1723636850030
created: 1723636850030
isDir: false
---
returns text as $$
declare
    org_rec record;
	cust_id	integer;
    org_cur cursor
        for select customer_id
                   from organization
                   group by customer_id
                   having count(customer_id) = 1; -- single org customers only
begin

    open org_cur;

    loop
        fetch org_cur into cust_id;
        exit when not found;
		
        update resource_set
        set organization_id = (select organization_id
								from organization
								where customer_id = cust_id)
        where resource_set.customer_id = cust_id;
    end loop;

    close org_cur;

    return 'done';
end; $$
    language plpgsql;

begin;
select update_result_sets();
end;

drop function update_result_sets();