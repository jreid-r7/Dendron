---
id: 1pp0chp4vc2quu53g9ofx8s
title: Enable Org Level New Experience
desc: ''
updated: 1731505985409
created: 1723638383151
isDir: false
id_imported: 6v96t20divzrb6yil4myb78
title_imported: Enable Org Level New Experience
desc_imported: ''
updated_imported: 1723636850018
created_imported: 1723636850018
---
```
curl --location --request POST "https://api.ipims-int-1.us-east-1.ipims-staging.r7ops.com/api/rbac/v1/customers/0fa47637-f472-40b2-925f-96e1fd30638a?orgLevelEnabled=true"  --header "R7-Consumer: test"  --header "R7-Correlation-Id: 00cc652e-4de3-4f80-b840-e452ae1bd298"  --header "Content-Type: application/json"  --header "R7-Internal-Service-Key: 8d120fed-ef88-474e-acc9-3b2665a670bf"
```

##Prod:
```
curl --location --request POST 'https://insight.rapid7.com/rbac/v1/customers/b504b767-bdb0-4558-927f-aa358b589b1b?orgLevelEnabled=true' \
--header 'Content-Type: application/json' \
--header 'R7-Consumer: jreid-test' \
--header 'R7-Correlation-Id: jreid-test' \
--header 'R7-Internal-Service-Key: 0b94b1f0-1086-4cfd-81e2-658fbd1229e0'
```

## Org UAP Composer start

```sbrun -Dspring-boot.run.jvmArguments="-Dserver.port=8009 -Drbac.org.uap.enabled=true"```

