---
id: og17wohxwllqveli8q9shz8
title: Int
desc: ''
updated: 1723636850027
created: 1723636850027
isDir: false
---
Read replica - created

Load Balancers

k8s-default-gatewayp-5889da660e - rules added

-   /api/1/me/session/* -> panda
-   /api/* -> 405
-   /user/* -> 405

k8s-kong-konginte-3d156e3a35 - rules added

-   /class1/* -> 405
-   /api/* -> 405

ipims-int-1-rbacCoreUapALB - rule added

-   /* -> 405

  

Lambdas

ipims-int-1-ipimsupdatel-IpimsUpdateLastLoginLambda

-   removed us-east-1-ipims-int-1-auditevents SNS trigger

ipims-int-1-rbaclambda-IpimsRbacMetadataUpdateLambda

-   removed [rbac-metadata.ipims-int-1.us-east-1.rapid7.com](http://rbac-metadata.ipims-int-1.us-east-1.rapid7.com/) S3 trigger

ipims-int-1-IpimsRbacCoreUapLambda

-   rule in ALB

  

Applications

platformproductregistrationapp

-   deployment removed

platforminternalmanagementapp

-   deployment removed

ipimsrbacuapcomposer

-   deployment removed

ipimsrbacmetadatauapcomposer

-   deployment removed

  

Database

Read replica promoted

Upgrade to 12.11

Renamed

Route 53 checked