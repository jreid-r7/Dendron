---
id: 9ivtk8yzluhtuf0ms1wlw9n
title: Access Management App
desc: ''
updated: 1727336756134
created: 1727276437225
---
[[Europa - Nuking phase 1 of Nuketa|https://rapid7.atlassian.net/wiki/spaces/PlatServ/pages/979927372/Europa+-+Nuking+phase+1+of+Nuketa]]

[[Decommission Access-management and User-role-app|https://rapid7.atlassian.net/wiki/spaces/PlatServ/pages/441489909/Decommission+Access-management+and+User-role-app]]

[[Uses of AccessManagementCustomerClient|https://github.com/search?q=org%3Arapid7+accessmanagementcustomerclient&type=code]]

## Initial look

### access_management database

* Holds relationships between users and customers.
  * user_id - uuid
  * customer_id - uuid
  * platform_admin - 1 or 0
  * oktas_group_id - <Customer Name\>-<customer_id\>
  * okta_admin_group_id - <Customer Name\>-<customer_id\>-PLATFORM-ADMIN
* Holds relationships between users and org product instances.
  * user_id - uuid
  * product_token - typical 20 character string
  * okta_group_id - <Product Code\>_USERS\_<Product Token\>

