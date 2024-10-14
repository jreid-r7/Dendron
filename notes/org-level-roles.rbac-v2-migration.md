---
id: 38ehompvsfhcasgktgov9pq
title: Rbac V2 Migration
desc: ''
updated: 1723636850024
created: 1723636850024
isDir: false
---
Standard V2 products like AS, IDR and OPS - they use their own scripts using customer level APIs. These products have adopted V2 APIs and actually use RBAC.
Legacy products like IVM, OpenLabs, etc. - we migrate those using our own scripts and APIs. These products do not use RBAC V2. We only do this for single org customers at the moment.

During a migration:
1. add customers and users to the RBAC db
2. assign roles to the users
3. assign products and data access (resources)
4. set the products to V2 so that CMS and panda know they are V2

All single org legacy products were migrated - there may be some left since some had orgs deleted. We'll need new APIs to support org level assignment for these migrations.

We will need controls in place governing access to the new UI org level experience. How simple will this be? Early access and all products on RBAC V2 and some sort of percentage based rollout.

AppSec have an in-product experience where you can assign users to apps.
## API Adoption

razorjobgeneralpurpose - IDR 
- customer level user search. Might return roles. We think there's an org version. Low priority.
ics-ipims-app 
- uses /me/uap
- Also groups - groups ok
mse_batch_provisioning_lambda - IDR
- delete org product from user
pud
- using oaps - calls to delete
- rest is resource sets - should be backwards compatible - we would like these changed - should be do-able now
- method:patch,uri:/rbac/v1/customers/_customerid_/resource-sets/_resourcesetid235.3occurrences0occurrences813occurrences16.94koccurrences340.0occurrences
- method:delete,uri:/rbac/v1/oap/customers/_customerid_/organizations/_organizationid82.0occurrences0occurrences517occurrences5.91koccurrences143.0occurrences
- method:post,uri:/rbac/v1/customers/_customerid_/resource-sets34.1occurrences0occurrences209occurrences2.45koccurrences33.0occurrences
- method:patch,uri:/rbac/v1/customers/_customerid_/resource-sets/_resourcesetid_/resources34.1occurrences0occurrences209occurrences2.45koccurrences33.0occurrences
- method:delete,uri:/rbac/v1/customers/_customerid_/resource-sets/_resourcesetid7.0occurrences0occurrences97occurrences0.51koccurrences0occurrences
- method:get,uri:/rbac/v1/customers/_customerid_/resource-sets
- Also lambda calls for UAP - instructions are in https://rapid7.atlassian.net/wiki/spaces/PlatServ/pages/441489778/Org-Level+RBAC
appsec 
- probably done - check usage of method:patch,uri:/rbac/v1/customers/_customerid_/users/_userid_/resource-groups/resourcegroupid - Does it need to be customer wide or org restricted
  What they are doing is giving one user access to all resources, we think.
- Also lambda calls for UAP - instructions are in https://rapid7.atlassian.net/wiki/spaces/PlatServ/pages/441489778/Org-Level+RBAC
ivm, nexpose-user-blob-processor
- we don't think these are direct calls - find out the calling chain

