---
id: uvcjfxfog0n96j3jeqhrm1z
title: Manoj Khatri 11523
desc: ''
updated: 1723636850027
created: 1723636850027
isDir: false
---
Automation engineer in QA
Joined AllState - Java, React, JavaScript, Java, SpringBoot

Casualty Centre App for Claim Adjusters
Built for AllState internal

ISAM auth
Front end in React/JS with AllState component library
Talks to micro service
Microservice model, components, repository, service
MySQL DB
BE API may also talk to other APIs, including billing, etc. These may talk to 3rd parties
API to generate reports sent to JMS queue picked up by integration team. This is pushed to another queue picked up by the main CC api
REST calls

Currently a senior role
Coding and looking after graduates
Pairing with them

Git for vc

Deployment - deployed as developed - new features built and deployed. Jenkins
No reviews - all pair programmed

Tough technical
Still working on some of the queueing stuff - getting things set up, had to learn it from scratch

Wouldn’t change anything in the current project. Maybe introduce Kafka


Fell over on closures
BDD - allows non-techs to write the gherkin - prefers this to page object model
React - managing state - use state managed across components as a prop
Sharing state between tabs - state variable passed in callback function passed to next component
Front end libraries (other than internal) - internal handles all that


Four principles - got when prompted
I - yes
P - overriding and overloading
A - abstract class
E - binding data together

Design patterns
Singleton

Synchronous/Asynchronous
S - wait for a process
A - execute and move on
No futures or promises

Process and Thread
Process can have multiple threads

Single responsibility - one task at a time


Debugging
1. First steps on issues Look at the issue to see whether it’s a FE or BE Try to replicate in local env Look at permissions, check IDs, look for roles Ask for exact error Is it only particular users
2. Slow to respond Query may be searching too many records, or returning too many. Look at query. DBAs may have a tool - using JPA, got query from DBA, no indexes Postman,  Check resources on container, memory, CPU
3. Too much load Multiple instances - 
4. Not responding Look at error code - look at debug console DataDog - logs, metrics, etc.
5. Deadlock A query not exiting and another query can’t access

Any Questions for us? No