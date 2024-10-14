---
id: as7b9q6kibgt3uvrfn9uz80
title: Erv Entitlement Check
desc: ''
updated: 1723636850027
created: 1723636850027
isDir: false
---
Check will be done to subscription management

Currently server side redirect to display the correct landing page. This backend check will be needed to send a user to the correct page. Front end will need to make the check to ensure the page can be rendered (in case of deep link or similar)

UI check - UAP Lite, specific API, other?

Deriving eligibility: see wiki
Two roles - IVM_ERV and ICS_ERV


## For Org Switcher

1. Pass in nothing - getErvEntitlements()
	1. Pass in list of orgs
	2. List of product codes
	3. List of Roles
1. Return a list of org ids that have the entitlemen


Initial thoughts were to have a separate call for the subscription info and then to call RBAC for the rest of the AUTH - product access, roles/features. 

Would it make sense to stick this API in policy service and do all the checks? - Reach out to Tom
 - Not really suited for policy service as it is meant to do API like checks. The RBAC check could be moved to here eventually. Maybe do the one shot check in Panda?