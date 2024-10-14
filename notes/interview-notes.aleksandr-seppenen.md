---
id: dmt031ot7cssyeap5x696yd
title: Aleksandr Seppenen
desc: ''
updated: 1723636850024
created: 1723636850024
isDir: false
---
Current Lease Deal
Project was confirmed but not being continued. Working on Umbrella for something to do.

Tietoevry - API development, documentation, code review.
On Docker containers - created REST controllers, talking to another web service, DB changes, webflux.  DTO coming in and was deserialized. May have been GET or POST. 

VC - Git, SVN, Azure DevOps portal
JUNIT, Cyprus Test, Cucumber, Mockito, No TestContainers

## Technical Questions

Principles
Started with Clean, Testable, moved to SOLID
Single responsibility, Open/Closed,

Encapsulation - some fields - only accessible from within, exposed through these
Abstraction - started on abstract class - describes object and what it can do
Inheritance - much prompting - defines methods
Polymorphism - 

Implements vs extend - not much clue

### Dependency Injection
Injecting a class to be used, Inversion of Control, via constructor, AutoWired - no opinion on which is better
Default scope is Singleton - created only once

### Design patterns
MVC, DB Layer
Micro Service architecture

MVC - Model view controller - business logic in model, view UI, 

Microservices vs. Monolith
Monolith can be difficult to maintain or to integrate new things into
Microservice can be expensive but is more agile
## Data structures
Hash map - a collection, uses a hashcode, will overwrite, faster than array list
ArrayList - only data
Hash map - key value - hashcode and equals

ArrayList/LinkedList - array list - can find by ID, linked list good for adding

### Caching
Spring or Redis - used for repeated calls but similar answers
Sometimes clean the cache, or ttl

## URL shortening service
Take a long URL and store it in the DB with a short unique ID
Return both of those. 
When the user clicks the shortened like we perform lookup in the db then redirect to 

Controller - one to generate, the other to handle the redirect
Service to generate short ID

Possibility of an ID clash
Maybe same URL

High volume - limit requests, pagination, 

DDOS, sensitive data.

## Debugging scenario
Read the what they wrote, reproduce, start to debug and detect, 
Has used splunk
Normally reports were created by someone else

Browser console, direct calls to the api. 

## Questions
