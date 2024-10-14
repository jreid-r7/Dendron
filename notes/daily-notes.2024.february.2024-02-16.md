---
id: dow9yj1b83vtwqle8o63yky
title: 2024 02 16
desc: ''
updated: 1723636850032
created: 1723636850032
isDir: false
---

## StrongForce UAP Asks
Region can be argued to belong in the UAP
Org display name not so much
- It has nothing to do with auth
- It is mutable data so would require UAP regeneration on every mutation
### Policy service constraints
1. It's a policy service and will eventually be regionalised so it can only access UAP data. This means no joining to other RBAC tables for additional data.
2. Dumping non- auth policy data in the UAP will start to muddy the waters a bit.
### Searching
1. Because of paging this makes the organization table the source table - so we need to filter on orgs the user has access to - which will come from the UAP. This means this needs to be an RBAC API.