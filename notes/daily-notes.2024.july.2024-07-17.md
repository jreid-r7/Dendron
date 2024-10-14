---
id: f4myzez7a8r5g57eso19lqr
title: 2024 07 17
desc: ''
updated: 1723636850033
created: 1723636850033
isDir: false
---
Product access fix-up

e.g.
Ops -> org 1 -> user product map has an association reason - indirect access via user group and entry in association reason table - should be 1:1
Ops -> org 2 -> user product map has an association reason - indirect access via user group and entry in association reason table

We have some with two association reasons covering the two instances of ops, ignoring the org, sort of
removing the user from the group only removed the valid association reason. This left behind association reasons saying there was access to a different product instance via the group and the user isn't in that group anyway.

## step 1
1. We need to find associations reasons mentioning a group and a user where the user isn't in the group.
2. Delete those association reasons
3. Scan the user product map table for mappings with no association reason
4. Delete those mappings
This solves users having access when they shouldn't. Because we are deleting orphaned product maps we need to remove product access in access management and internal user app (pre-existing client call).
## step 2
1. Find associations mentioning a user and a group where the user-product-map product links to a different org product in the association reason (there will be two association reasons, 1 valid and 1 not)
2. Delete those
