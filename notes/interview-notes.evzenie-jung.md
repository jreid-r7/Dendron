---
id: o8y5zxkgmg3po2fh7np2si5
title: Evzenie Jung
desc: ''
updated: 1723636850024
created: 1723636850024
isDir: false
---
Current work - implementing some pages for US Citizen taxes, currently front end in JSF. Repo services, PostgreSQL, component beans

Previous project, two years, implementing two services, Spring and Spring Boot, Apache Kafka, logs saved to PostgreSQL, Hazelcast and Elastic Search. REST endpoints. GET and DELETE endpoints. 

Auth - annotations, microservice for the rights - request made to that service to check auth. Kubernetes.

## Technical
### Principles of OO
Abstraction Inheritance Encapsulation Polymorphism
Abstraction - hiding unnecessary implementation, showing only what the API needs
Encapsulation - secured the data, private variables, public getters and setters
Inheritance - make basic functionality, extend a class to enhance or add functionality. Extending abstract or ordinary classes or implementing interfaces
Polymorphism - overloading, overriding
- overloading - same method, different parameters
- overriding - different implementation

Private, protected, public, default
Knows difference between class and object variables

### Data structures
HashMap - key and value
key - can't be duplicated - uses hash function - hashcode and equals
values - not unique
Mentioned collisions
Keys - set
Values - List

ArrayList - elements in an array
LinkedList - nodes - references next node

### Caching
Knows what it is, speed of access
Helps with load
Consistency of data

### Async/Sync
Async - parallel processing
Sync - chained, end-on-end

Problems - transactions - async, data loss or inconsistency
Async can be faster

### REST
Representational State Transfer - HTTP, GET, POST, PUT, DELETE. JSON, XML, 
HATEOAS - deeper links in response body

Good REST API - secure,

### Spring
Benefits, dependency injection, responsible for lifecycle of the beans

## URL Shortener
convert URLs
Take the initial url - convert
Storage - some map, value is the long one, 

## Debugging
1. Get more information from user, check logs, 
2. Check CPU, what part is slow?, 
3. Scaling