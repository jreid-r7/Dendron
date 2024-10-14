---
id: cbsiqvh8341ls993f1hwd9u
title: Prod
desc: ''
updated: 1723636850027
created: 1723636850027
isDir: false
---
Read Replica - created
PGs - created

Load Balancers
GatewayALB
* /api/me/session/* -> panda
* /api/* -> 503
* /user/* -> 503
* /rbac/* -> 503

k8s-kong-kongprod-691cd3caed
* /api/* -> 503
* /user/* -> 503
* /rbac/* -> 503
* /class1/* -> 503

C3GatewayALB-ipims-prod-0
* /class1/* -> 503
* /api/* -> 503

Lambdas
ipims-prod-0-ipimsupdatel-IpimsUpdateLastLoginLamb-MKL0C9643WGD
* remove SNS trigger - eu-central-1-ipims-prod-0-auditevents
ipims-prodservices-0-rbaclambda-IpimsRbacInvalidateUapLambda
* remove SQS trigger -  eu-central-1-ipims-prodservices-0-rbac_regional_cache_q
ipims-prod-0-rbaclambda-IpimsRbacMetadataUpdateLambda
* remove S3 trigger - rbac-metadata.ipims-prod-0.eu-central-1.rapid7.com

Apps
* registrationapp-ipims - size 2 -> 0
* internalmanagementapp-ipims - size 2 -> 0
*  deployment ipimsrbacuapcomposer - deleted

Check database
ssh -o "ProxyCommand ssh -A ssh.ipims-prod-0.eu-central-1.ipims.r7ops.com -W 10.198.134.166:22" 10.198.134.166 -L 1260:rbac-rds.resource.local:5432

read replica promoted
upgraded version
resized