---
id: ca647fv8i12sd92ocqb11j5
title: 2024 01 31
desc: ''
updated: 1723636850033
created: 1723636850033
isDir: false
---
# EDA and Org Level Roles 
Should remain at a customer level - the customer decides whether or not their orgs can have EDA set

## A customer is granular 
For a user we can decide to apply the wildcard from meta data and that wildcard needs to be set on the org.

Current true or false for EDA stored in resource_group_user and resource_group_user_group
These tables will need to be made org level.


### Work needed 
1. Two v2 APIs for resource_group mapping tables - org context
2. UPA Composer updated to add org level wildcards based on the above
- [x] Talk to AppSec about their non-org wildcard scheme - technically incorrect
- [x] Make sure AppSec can handle a wildcard RRN with and org ID

Current AppSec contact - Neal Ward