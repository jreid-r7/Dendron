---
id: mts6jwm97y2aaos13lyqih6
title: 2024 03 27
desc: ''
updated: 1723636850034
created: 1723636850034
isDir: false
---
sum:ipims.http.server.requests.count{stack:ipims-prod-0,uri:/rbac/v1/me/uap,!r7-consumer:user_management}.as_count()
sum:ipims.http.server.requests.count{stack:ipims-prod-0,uri:/rbac/v1/customers/_customerid_/users/_userid_/roles,!r7-consumer:user_management}.as_count() 
sum:ipims.http.server.requests.count{stack:ipims-prod-0,uri:/rbac/v1/customers/_customerid_/users/_userid_/resource-sets,!r7-consumer:user_management}.as_count()
sum:ipims.http.server.requests.count{stack:ipims-prod-0,uri:/rbac/v1/customers/_customerid_/users/_userid_/resource-sets/tags/_tagname_/resources,!r7-consumer:user_management}.as_count()
sum:ipims.http.server.requests.count{stack:ipims-prod-0,uri:/rbac/v1/customers/_customerid_/resource-sets/all/resources/_resourceid,!r7-consumer:user_management}.as_count()
sum:ipims.http.server.requests.count{stack:ipims-prod-0,uri:/rbac/v1/customers/_customerid_/resource-sets,!r7-consumer:user_management}.as_count()
sum:ipims.http.server.requests.count{stack:ipims-prod-0,uri:/rbac/v1/customers/_customerid_/resource-sets/_resourcesetid,!r7-consumer:user_management}.as_count()
sum:ipims.http.server.requests.count{stack:ipims-prod-0,uri:/rbac/v1/customers/_customerid_/resource-sets/_resourcesetid_/resources,!r7-consumer:user_management}.as_count()
sum:ipims.http.server.requests.count{stack:ipims-prod-0,uri:/rbac/v1/customers/_customerid_/user-groups/_usergroupid_/resource-sets,!r7-consumer:user_management}.as_count()
sum:ipims.http.server.requests.count{stack:ipims-prod-0,uri:/rbac/v1/customers/_customerid_/users,!r7-consumer:user_management}.as_count()