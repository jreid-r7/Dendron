---
id: y0w0km6gzx95t2gzza967oy
title: Elizaveta Timofeeva
desc: ''
updated: 1723636850024
created: 1723636850024
isDir: false
---
Micro service based - synchronised writes to a single database
Data from Kafka - some python apps, with JSON from there, filters based on various attributes. Needs to look at the Go code or the Python in order to work out what to do in the Kotlin code.
Team reduction in SentinalOne
Excited by Cyber Security, interested more in product

Tough challenge - environment check - checking that everything is up and green. Proud that using backwards engineering could find the issue and fix it. Used an internal tool that monitored the status. Used server logs

## Principles of OO
Abstraction
Encapsulation
Inheritance
Polymorphism

Overload - change arguments
Override - change implementation

Interfaces - decouple business logic from what needs to be done, better architecture. Client doesn't need to know how things are implemented.
Abstract classes - allow both and can have an implementation . Abstract classes can be inherited.

## Dependency Injection
Decouple implementation IoC - inject things into a class so that it can be just used. Spring Bean - object that lives in a container - spring boot manages the life cycle. 

Constructor injection as opposed to Autowired - more control, easier to test

Knows about profiles

## HashMap
KVP - keys are unique, prompted hashcode and equals

## Caching
Lots of data, processing time, memo, 

## Async vs Sync
Could define
Sync can cause blocking can stop other things from running
Async problems - can be difficult to trace, 

## Transactions
Distributed system, data integrity, remediation

## URL shortener
DB Schema
Original URL
Shortened
POST -> take original url, create a short url, store in database, return short
GET -> redirect after matching

Lots of URLs - parallel logic for matching, balance database
Inactive links could be reused, TTL, 

## Debug
Limit traffic, unhappy customers, more resources, 