---
id: ce19qejngzm8xasor6zlzj7
title: Access Requests
desc: ''
updated: 1723636850024
created: 1723636850024
isDir: false
---

``` mermaid
graph LR
	PA[panda-app] --> IPRA[ipims-product-request-app]
	IPRA --> PA
	IPRA[ipims-product-request-app] --> PCA[platform-customer-app]
	PCA --> IPRA
```

## panda-app
| Controller | End Point | Service |
| ---- | ---- | ---- |
| OpenAccessRequestController | /accessRequests/openUser | productRequestService.getOpenUserAccessRequests(customerId) |
| OpenProductAccessRequestController | /productRequest/openProductAccess | productRequestService.getOpenProductAccessRequests(customerId) |
|  | /productRequest/openTrial | productRequestService.getOpenTrialProductRequests(customerId) |
|  | /ProductRequest/openMultiCustomer | productRequestService.getOpenMultiCustomerProductRequests(customerId) |
### CustomerAccessRequestService

 
### ProductRequestService



## ipims-product-request-app

| Controller | End Point | Service |
| ---- | ---- | ---- |
| OpenCustomerAccessRequestController | /openCustomerAccess/customer/{customerId} | customerAccessRequestService.getOpenCustomerAccessRequests(customerId) |
| OpenProductAccessController | /openProductRequest/customer/{customerId} | productRequestService.getOpenProductRequests(customerId) |
| OpenProductTrialAccessController | /openProductTrialRequest/customer/{customerId} | productTrialRequestService.getOpenTrialProductRequests(customerId) |
| OpenUserAccessRequestController | /openUserRequest/customer/{customerId} | userRequestService.getOpenRequestsForCustomer(customerId) |



 
 
## platform-customer-app

```mermaid
erDiagram
	customer||--|{base_access_request : has
	customer {
		varchar customer_id
		varchar name
		varchar okta_group_id
		varchar okta_group_name
		varchar okta_admin_group_id
		varchar okta_mfa_exclusion_group_id
		int mfa_enabled
		int mfa_exclusion_enabled
		int external_idp
		varchar okta_mfa_inclusion_id
		enum mfa_option
		enum customer_type
		varchar creation_route
	}
	base_access_request||--||external_user_access_request : request_type
	base_access_request||--||multi_customer_product_request : request_type
	base_access_request||--||partner_relationship_request : request_type
	base_access_request||--||product_request : request_type
	base_access_request||--||trial_product_request : request_type
	base_access_request||--||user_request : request_type
	base_access_request {
		int internal_id
		varchar request_id
		varchar customer_id
		enum request_type
		enum action_type
		enum status
	}
	external_user_access_request {
		int request_internal_id
		enum external_user_request_type
		varchar managing_customer_id
		varchar okta_user_id
		int platfomr_admin
		int valid_until
		varchar comment
		varchar user_id
	}
	multi_customer_product_request {
		int request_internal_id
		int user_id
		int org_product_id
		varchar comment
		varchar role
		varchar external_user_access_request_internal_id
	}
	partner_relationship_request {
		int request_internal_id
		varchar partner_customer_id
		int require_approval
		int email_notifications
	}
	product_request {
		int request_internal_id
		int user_id
		int org_product_id
	}
	trial_product_request {
		int request_internal_id
		int user_id
		int org_product_id
		int organization_id
		varchar product_code
	}
	user_request {
		int request_internal_id
		int user_id
		varchar comment
	}
	external_user_access_request||--o{external_user_org_product_access_request : external_user_request_type
	external_user_org_product_access_request {
		int internal_id
		int org_access_request_id
		varchar product_token
	}
	external_user_access_request||--o{external_user_v2_product_access_request : external_user_request_type
	external_user_v2_product_access_request {
		int internal_id
		int org_access_request_id
		varchar product_token
	}	
	external_user_access_request||--o{external_user_v2_role_access_request : external_user_request_type
	external_user_v2_role_access_request {
		int internal_id
		int org_access_request_id
		varchar role_id
	}
	trial_product_request||--o{trial_product_request_custom_data : has
	trial_product_request_custom_data {
		int internal_id
		int request_internal_id
		varchar custom_data_key
		varchar custom_data_value
	}
	
```

Existing request functionality depends upon a request type - `T extends AccessRequest`. These types come from `ipims-access-request-domain`. Each request type is dealt with by a different service select depending on the incoming type.

### General Principles
The DAOs are defined in `ipims-access-request-domain`. The entities are defined in `platform-customer-app`. Customer app also defines a number of converters to convert between the entities and the DAOs.
#### ExternalUserAccessRequestService
Typically returns a list of `ExternalUserRequest` objects. `ExternalUserRequest` extends `AccessRequest`.
`findOpenRequestsByCustomerId(String customerId)` with access request type EXTERNAL_USER_ACCESS_REQUEST
#### MultiCustomerProductAccessRequestService
Typically returns a list of `MutliCustomerProductRequest`. `MutliCustomerProductRequest` extends `AccessRequest`.
`findOpenRequestsByCustomerId(String customerId)` with access request type MULTI_CUSTOMER_PRODUCT_REQUEST
#### PartnerRelationshipAccessRequestService
Typically returns a list of `PartnerRelationshipRequest` objects. `PartnerRelationshipRequest` extends `AccessRequest`.
`findOpenRequestsByCustomerId(String customerId)` with access request type PARTNER_RELATIONSHIP
#### ProductAccessRequestService
Typically returns a list of `ProductRequest`. `ProductRequest` extends `AccessRequest`.
`findOpenRequestsByCustomerId(String customerId)` with access request type PRODUCT_REQUEST
#### TrialProductAccessRequestService
Typically returns a list of `TrialProductRequest` objects. `TrialProductRequest` extends `AccessRequest`.
`findOpenRequestsByCustomerId(String customerId)` with access request type TRIAL_PRODUCT_REQUEST
#### UserAccessRequestService
Typically returns a list of `UserRequest`. `UserRequest` extends `AccessRequest`.
`findOpenRequestsByCustomerId(String customerId)` with access request type USER_REQUEST

### iPIMS Product Request App
#### ipims-access-request-client
Defined:
- `OPEN_PRODUCT_REQUEST_SERVICE_ENDPOINT`
	- http://%s/api/1/openProductRequest
- `OPEN_PRODUCT_TRIAL_REQUEST_SERVICE_ENDPOINT`
	- http://%s/api/1/openProductTrialRequest
- `OPEN_USER_ACCESS_REQUEST_SERVICE_ENDPOINT`
	- http://%s/api/1/openUserRequest
- `OPEN_CUSTOMER_ACCESS_REQUEST_SERVICE_ENDPOINT`
	- http://%s/api/1/openCustomerAccess
All point to `PRODUCT_REQUEST_SERVICE_APP_NAME`

#### ipims-product-request-app
- http://%s/api/1/openProductRequest
	- OpenProductAccessController
	- Calls `productRequestService.getOpenProductRequests()`
	- Request type `PRODUCT_REQUEST`
	- returns `List<UserProductAccessRequestOpen>`
- http://%s/api/1/openProductTrialRequest
	- OpenProductTrialAccessController
	- Calls `productTrialRequestService.getOpenTrialProductRequests()`
	- Request type ``
	- returns `List<TrialProductRequestOpen>`
- http://%s/api/1/openUserRequest
	- OpenUserAccessRequestController
	- Calls `userRequestService.getOpenRequestsForCustomer()`
	- Request type ``
	- returns `List<UserAccessRequest>`
- http://%s/api/1/openCustomerAccess
	- OpenCustomerAccessRequestController
	- Calls `customerAccessRequestService.getOpenCustomerAccessRequests()`
	- Request type ``
	- returns `List<MultiCustomerProductRequestOpen>`
All of these fall through to`CustomerAppProxyService.getOpenProductAccessRequests()` with Customer Id and Request type

#### panda-app
