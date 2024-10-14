---
id: 0dul6ii6yihl149stztvgzt
title: Web Hook Testing
desc: ''
updated: 1723636850023
created: 1723636850023
isDir: false
---
## create webhook
curl --location --request POST 'https://api.ipims-stagsrvs-1.ipims-staging.r7ops.com/webhook/api/1/webhooks/organization/1?webhookType=JOHN_TEST_TYPE&webhookName=JOHN_TEST_NAME' --header 'X-Api-Service-Key: 56023ad5-3d44-4c1d-bb73-8b03bec46285'  --header 'R7-product-name: jreid'  --header 'Content-Type: application/json' --header 'R7-Consumer: jreid-test' --data-raw '{ "metadataField" : "johnTestField" }'


## get webhook
 (use the id at the end of the url returned from the above response)
curl --location --request GET 'https://api.ipims-stagsrvs-1.ipims-staging.r7ops.com/webhook/api/1/webhooks/0d37e07a-243e-46b1-990c-eede8c3467cb' --header 'X-Api-Service-Key: 56023ad5-3d44-4c1d-bb73-8b03bec46285'  --header 'R7-Consumer: jreid-test'