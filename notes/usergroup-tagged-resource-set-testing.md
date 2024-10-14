---
id: 4w7cmv61fzozb00gyehpjbg
title: Usergroup Tagged Resource Set Testing
desc: ''
updated: 1723638383152
created: 1723638383152
isDir: false
id_imported: sni7adxevba7nybx01qmm26
title_imported: Usergroup Tagged Resource Set Testing
desc_imported: ''
updated_imported: 1723636850020
created_imported: 1723636850020
---
### Get groups
curl -v -L -X GET 'localhost:8090/rbac/v1/customers/4df71463-8883-44a8-b11a-703be25c1f60/user-groups' -H 'R7-Consumer: IntegrationTests' -H 'R7-Correlation-Id: 864ed9c1-c02a-497d-aaef-d4d65294ec19' -H 'R7-Internal-Service-Key: f90cdf0c-a9ca-46df-ac80-2c750c4b8579'

### Create or update tagged resource set
curl -v -L -X PUT 'localhost:8090/rbac/v1/customers/4df71463-8883-44a8-b11a-703be25c1f60/user-groups/ebc55bee-f993-4090-b354-76d30323dd39/resource-sets/tags/testTag/resources?resourceGroupId=34e703c0-a794-4c10-98ae-4f7a5f7eb626' -d '{"excludedResources": ["test one"],"includedResources": ["excluded one"]}' -H 'R7-Consumer: IntegrationTests' -H 'R7-Correlation-Id: 864ed9c1-c02a-497d-aaef-d4d65294ec19' -H 'R7-Internal-Service-Key: f90cdf0c-a9ca-46df-ac80-2c750c4b8579' -H 'If-Match: 0' -H 'Content-Type: application/json'

### Get tagged resource set resources
curl -X GET 'localhost:8090/rbac/v1/customers/4df71463-8883-44a8-b11a-703be25c1f60/user-groups/ebc55bee-f993-4090-b354-76d30323dd39/resource-sets/tags/testTag/resources' -H 'accept: application/json' -H 'R7-Consumer: IntegrationTests' -H 'R7-Correlation-Id: 864ed9c1-c02a-497d-aaef-d4d65294ec19' -H 'R7-Internal-Service-Key: f90cdf0c-a9ca-46df-ac80-2c750c4b8579'


