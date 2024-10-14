---
id: 2sstxy1cgmuhvbujw2cj9b0
title: Mammad Jafarzade
desc: ''
updated: 1723636850024
created: 1723636850024
isDir: false
---
Current work - front end, unusual for him.
Spring boot microservices architecture with service discovery, REST api, requesting data between services.

Worked on a single Spring boot application in AWS, building on Docker locally with mocks. Deployed through Jenkins.
No K8S, TerraForm, etc

Significant technical problem - Investment banking - 14 days worth of data. Removing data that was older took a long time. Implemented sharding/partitions on MSSQL - older than 14 days could be deleted whenever. 50% improvement in deletion performance. 

Used a test db with data

## Technical I
### Principles of OO
Encapsulation - no public variables, control access through getters/setters
Interfaces
Open for extension
Polymorphism - runtime and compile time - overloading and overriding - 
### Design Patterns
MVVM - model view view-model
Builder, Factory

Singleton - single instance of an object - keep using it instead of creating new 
Spring - by default - Prototype, Session
Advantages - performance

### Data structures
HashMap - key/value, keys are hashed, easy fast access, 
hash function - creates a value. Hash clash - there's a linked list backing this, uses equals

ArrayList vs. LinkedList
ArrayList - indexed, fast access by index - good for access, but deleting/inserting in middle expensive
LinkedList - links to previous and next

### Caching
Data needed more often - keep closer to us, it's duplicated, may become inconsistent
Handling inconsistency, updating both at the same time
Good for caching - Data used frequently, that doesn't change often

### Process/Thread
Thread - part of a process. 
Process - can be multiple threads. Starts, ends
Threads need to be started and then return data, a thread may be blocked, 

### REST
some resource, add edit delete etc. Stateless HTTP, GET POST DELETE, etc. JSON most of the time
POST vs. PUT insert, PUT to edit

## URL shortener
URL input, return a new URL and link it to the old URL
API for clients to use

Java stack, Spring


