---
id: 53ms3ikea5owofub8zd9fpf
title: Ops Sla Knowledge Share
desc: ''
updated: 1723638383151
created: 1723638383151
isDir: false
id_imported: xz4upo9zfxil0f7pfvght09
title_imported: Ops Sla Knowledge Share
desc_imported: ''
updated_imported: 1723636850018
created_imported: 1723636850018
---
## State of SRE
Look out for the docs on these

### SLI, SLO, Error Budget
SLI - Service Level Indicator - a metric
SLO - Service Level Objectives
Error Budget - errors burn down your budget over the course of a month e.g. 1 HTTP 500 per 1000 requests - 99.9% Error budget

Company error budget is 99.95% - 21.6 minutes down per month or 1 error per 2000 requests

We need to reduce any repetitive manual work

DataDog has SLO modules
Can alert on things like burn rates, budget exceeded
tf-le-datadog slos terraform module

The service is a poor measure of its own reliability - a down service has no errors. Collect errors from ELBs

Error budget alerts - do several with different windows. You're thinking about the error quantity that you need to know about. 
Start with a generous SLO and Error Budget and work towards the ideal.

SLOs bring a focus onto the quality of your deployments

Start with a high traffic service but don't set up any alerts initially