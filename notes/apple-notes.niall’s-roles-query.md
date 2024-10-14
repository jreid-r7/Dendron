---
id: 8f6csq2i8af73bm6im4mere
title: Niall’s Roles Query
desc: ''
updated: 1723636850022
created: 1723636850022
isDir: false
---
-- “INSIGHT_IDR_ADMIN” AND (“INSIGHT_OPS_VIEW_AND_CHANGE” OR “INSIGHT_OPS_VIEW_ONLY”)
select role_id from "role" where role_name = 'INSIGHT_IDR_ADMIN'; -- 5112
select role_id from "role" where role_name = 'INSIGHT_OPS_VIEW_AND_CHANGE'; -- 5138
select role_id from "role" where role_name = 'INSIGHT_OPS_VIEW_ONLY'; -- 5140

select external_customer_id from customer
where customer_id in (
select customer_id from "user" where user_id in (select user_id
                                               from (select user_id
                                                     from user_role
                                                     where role_id = 5140 or role_id = 5138
                                                     group by user_id) a
                                               where a.user_id in
                                                     (select user_id from user_role where role_id = 5112 group by user_id)));
-- 26

-- “INSIGHT_IDR_ANALYST” AND (“INSIGHT_OPS_ADMIN” OR “INSIGHT_OPS_VIEW_ONLY”)
select role_id from "role" where role_name = 'INSIGHT_IDR_ANALYST'; -- 5113
select role_id from "role" where role_name = 'INSIGHT_OPS_ADMIN'; -- 5139
select role_id from "role" where role_name = 'INSIGHT_OPS_VIEW_ONLY'; -- 5140

select external_customer_id from customer
where customer_id in (
    select customer_id from "user" where user_id in (select user_id from
    (select user_id from user_role where role_id = 5140 or role_id = 5139 group by user_id) a
where a.user_id in
      (select user_id from user_role where role_id = 5113 group by user_id)));
-- 29

-- “INSIGHT_IDR_VIEWER” AND (“INSIGHT_OPS_ADMIN” OR “INSIGHT_OPS_VIEW_AND_CHANGE”)
select role_id from "role" where role_name = 'INSIGHT_IDR_VIEWER'; -- 5114
select role_id from "role" where role_name = 'INSIGHT_OPS_ADMIN'; -- 5139
select role_id from "role" where role_name = 'INSIGHT_OPS_VIEW_AND_CHANGE'; -- 5138

select external_customer_id from customer
where customer_id in (
    select customer_id from "user" where user_id in (select user_id from
    (select user_id from user_role where role_id = 5139 or role_id = 5138 group by user_id) a
where a.user_id in
      (select user_id from user_role where role_id = 5114 group by user_id)));
-- 33

-- “INSIGHT_OPS_ADMIN” AND (“INSIGHT_IDR_ANALYST” OR “INSIGHT_IDR_VIEWER”)
select role_id from "role" where role_name = 'INSIGHT_OPS_ADMIN'; -- 5139
select role_id from "role" where role_name = 'INSIGHT_IDR_ANALYST'; -- 5113
select role_id from "role" where role_name = 'INSIGHT_IDR_VIEWER'; -- 5114

select external_customer_id from customer
where customer_id in (
    select customer_id from "user" where user_id in (select user_id from
    (select user_id from user_role where role_id = 5113 or role_id = 5114 group by user_id) a
where a.user_id in
      (select user_id from user_role where role_id = 5139 group by user_id)));
-- 29

-- “INSIGHT_OPS_VIEW_AND_CHANGE” AND (“INSIGHT_IDR_ADMIN” OR “INSIGHT_IDR_VIEWER”)
select role_id from "role" where role_name = 'INSIGHT_OPS_VIEW_AND_CHANGE'; -- 5138
select role_id from "role" where role_name = 'INSIGHT_IDR_ADMIN'; -- 5112
select role_id from "role" where role_name = 'INSIGHT_IDR_VIEWER'; -- 5114

select external_customer_id from customer
where customer_id in (
    select customer_id from "user" where user_id in (select user_id from
    (select user_id from user_role where role_id = 5112 or role_id = 5114 group by user_id) a
where a.user_id in
      (select user_id from user_role where role_id = 5138 group by user_id)));
-- 31

-- “INSIGHT_OPS_VIEW_ONLY” AND (“INSIGHT_IDR_ADMIN” OR “INSIGHT_IDR_ANALYST”)
select role_id from "role" where role_name = 'INSIGHT_OPS_VIEW_ONLY'; -- 5140
select role_id from "role" where role_name = 'INSIGHT_IDR_ADMIN'; -- 5112
select role_id from "role" where role_name = 'INSIGHT_IDR_ANALYST'; -- 5113

select external_customer_id from customer
where customer_id in (
    select customer_id from "user" where user_id in (select user_id from
    (select user_id from user_role where role_id = 5112 or role_id = 5113 group by user_id) a
where a.user_id in
      (select user_id from user_role where role_id = 5140 group by user_id)));
-- 30

-- Log Search Admin AND (InsightIDR Analyst OR InsightIDR Viewer OR InsightOps View and Change OR InsightOps View Only)
select role_id from role where role_name = 'LOG_SEARCH_ADMIN'; -- 5051
select role_id from role where role_name = 'INSIGHT_IDR_ANALYST'; -- 5113
select role_id from role where role_name = 'INSIGHT_IDR_VIEWER'; -- 5114
select role_id from role where role_name = 'INSIGHT_OPS_VIEW_AND_CHANGE'; -- 5138
select role_id from role where role_name = 'INSIGHT_OPS_VIEW_ONLY'; -- 5140

select external_customer_id from customer
where customer_id in (
    select customer_id from "user" where user_id in (select user_id
                                                     from (select user_id
                                                           from user_role
                                                           where role_id = 5113 or role_id = 5114 or role_id = 5138 or role_id = 5140
                                                           group by user_id) a
                                                     where a.user_id in
                                                           (select user_id from user_role where role_id = 5051 group by user_id)));


-- Log Search View and Change AND (InsightIDR Admin OR InsightIDR Viewer OR InsightOps Admin OR InsightOps View Only)
select role_id from role where role_name = 'LOG_SEARCH_VIEW_AND_CHANGE'; -- 5050
select role_id from role where role_name = 'INSIGHT_IDR_ADMIN'; -- 5112
select role_id from role where role_name = 'INSIGHT_IDR_VIEWER'; -- 5114
select role_id from role where role_name = 'INSIGHT_OPS_ADMIN'; -- 5139
select role_id from role where role_name = 'INSIGHT_OPS_VIEW_ONLY'; -- 5140

select external_customer_id from customer
where customer_id in (
    select customer_id from "user" where user_id in (select user_id
                                                     from (select user_id
                                                           from user_role
                                                           where role_id = 5112 or role_id = 5114 or role_id = 5139 or role_id = 5140
                                                           group by user_id) a
                                                     where a.user_id in
                                                           (select user_id from user_role where role_id = 5050 group by user_id)));


-- Log Search View Only AND (InsightIDR Admin OR InsightIDR Analyst OR InsightOps Admin OR InsightOps View and Change)
select role_id from role where role_name = 'LOG_SEARCH_VIEW_ONLY'; -- 5050
select role_id from role where role_name = 'INSIGHT_IDR_ADMIN'; -- 5112
select role_id from role where role_name = 'INSIGHT_IDR_ANALYST'; -- 5113
select role_id from role where role_name = 'INSIGHT_OPS_ADMIN'; -- 5139
select role_id from role where role_name = 'INSIGHT_OPS_VIEW_AND_CHANGE'; -- 5138

select external_customer_id from customer
where customer_id in (
    select customer_id from "user" where user_id in (select user_id
                                                     from (select user_id
                                                           from user_role
                                                           where role_id = 5112 or role_id = 5113 or role_id = 5139 or role_id = 5138
                                                           group by user_id) a
                                                     where a.user_id in
                                                           (select user_id from user_role where role_id = 5052 group by user_id)));