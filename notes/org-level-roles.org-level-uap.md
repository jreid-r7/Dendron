---
id: gfnmdsj8hec6zsopn7u5h4u
title: Org Level Uap
desc: ''
updated: 1723636850024
created: 1723636850024
isDir: false
---
What does finished mean?
1. Org Level UAP contains the same information (except it's org level) as the existing UAP.
   caveat: We can use existing queries that may return more data than required, for now. We could filter this if we thought that was appropriate.
2. For StrongForce we need the region. Product code is TBD.

## Current state
1. The master query is org specific. It fetches users enriched with roles.
2. Resources are added but are customer level. Query needs updated to use the organization id. Currently the org id is passed in but is used to infer the customer id.
3. Products are not filtered on org
4. Admin accessible looks to be org specific
5. Features comes from the roles fetched in the master query

### What could be converted now?
1. Resources dependent on current work - especially backfill. API work needed to maintain that data.
2. Products can be done.

### Other things needing fixed
1. We have a defect around a particular user that blows up the UAP composer
2. New events need added to trigger updates (might be only for conflict reports)
