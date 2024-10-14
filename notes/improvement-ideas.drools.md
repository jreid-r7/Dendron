---
id: s973mftgi8xtbaf78tnm5u9
title: Drools
desc: ''
updated: 1724858010413
created: 1723636850023
isDir: false
---
# Facts
## What do we have to work with?
### RBAC
Anything in the UAP
#### Policy service
A couple of clients here. 
### LES
License information
#### LicenseAppProxyService
getLicense - gets a single license for a License Source and a product key. Returns a License object.
#### PlatformLicenceServiceSubscriptionClient
getSubscriptionById
getSubscriptionsByCustomerId
etc. 
Return singles or lists of Subscription objects

## Current request body
1. A Set of organization Ids ```<String>```
2. the platform feature to check ```<String>```

A UserPlatformFeatureAccessRequest object is build from these. This adds the customer ID and the user ID.

### Service method structure
1. Obtain a list of early access features for the user in that customer
2. Check for EV_CRC or EV_DEV exclusively

A PlatformFeatureAccess object mapped from the following json:

PLATFORM_FEATURE_ACCESS json
```json
[
  {
    "feature_name": "executive_view",
    "packages": [
      "CRC-ADV-SUB",
      "CRC-ESS-SUB"
    ],
    "feature_permissions": [
      {
        "feature": "IVM_EXECUTIVE_VIEW",
        "permission": "ADMINISTER"
      },
      {
        "feature": "ICS_EXECUTIVE_VIEW",
        "permission": "ADMINISTER"
      }
    ],
    "product_codes": [
      "IVM",
      "ICS"
    ],
    "v1_roles": [
      {
        "productCode": "IVM",
        "role": "ADMIN",
        "featureToOverride": "IVM_EXECUTIVE_VIEW"
      }
    ]
  }
]
```

#### EV_CRC

For each listed feaature (only one in the above JSON) we go to RBAC to retrieve a list of matching organization IDs. We pass UserPlatformFeatureAccessRequest and the PlatformFeatureAccess objects. The client method then builds a UserOrgAccessSearchRequest object. This contains:

1. Set of organization IDs
2. Set of Product Codes
3. Set of Feature Permissions
4. Set of V1 Roles

Also passes the customer ID and user ID. Calls rbacv2ProxyService.findOrgsWithRequestedUserAccess and the USER_ORG_ACCESS_SEARCH_ENDPOINT. Calls UserAuthService.findOrganizationsWithRequestedUserAccess()

This does a couple of checks including isMigrated.

Then fetches a list of orgs with the supplied feature permission access. Next a list of orgs with the supplied product access. It then returns the orgs which have the product access and those feature/permissions.

#### EV_DEV

This bypasses the RBAC check.
