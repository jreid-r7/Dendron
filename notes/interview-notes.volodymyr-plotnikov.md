---
id: 7jk6oglxc97bxdj6663ktcg
title: Volodymyr Plotnikov
desc: ''
updated: 1723636850024
created: 1723636850024
isDir: false
---
International teams - Insurance business in the US - 15 people in the Ukraine
Reporting taxes

Monoltih, Java 17, typical web application, JSP pages. Worked on UI as well. Creating tasks based on user story, code reviews. Sprint 1.5 months. Some small projects - dashboards. Spring-boot, MVC

MySQL - get data from elsewhere. Users manage that from the UI. Create and revise reports. Also submit the report to the government. Also manual submission.

Custom queries, mixture of HQL, LSQL. Has used JDBC template. Should define best approach based on business flow.
JUnit5 and Mockito, Functional testing using a selenium wrapper.

Initial on Tomcat
Moved to AWS

## Technical
Encapsulation, Inheritance, Abstraction, Polymorphism
A - hide implementation details and expose what is needed
I - new classes based on existing classes, logical structure, code reuse
P - expands inheritance, redefine methods
A - 

Dynamic
Overloading - compile time and overriding - runtime
Method - same name, different parameters

Design patterns - factory, abstract factory, facet
Factory pattern - most useable. Interface, implementation of the interface. Factory returns an instance based on parameters.

Singleton pattern - related to Spring-Boot. By default SB creates singletons. We can reference components within other components.
@Prototype for non-singleton
A single instance of the component

Interface - describes behaviour, implement methods and use them. Just one implementation, don't need interface. We can implement multiple interfaces.

REST APIs
Human readable, common interface, use GET, POST, simple, scalable, in general JSON. 

Caching - cache response of service methods using HCACHE.
If the data is fairly constant - prevent redundant db call. Improve performance. Define how often the data changes. When we add something we need to clear the cache.

Async vs. Sync
Async - do some action separate to the main flow
Sync - in step

Sync - may need to wait for a long time
Async - execute in parallel - problems - we may not know how long they may take or if one might fail, time out. Race conditions.

## Debugging
Logs, metrics. Create a task into task manager. All steps should be documented. Get all incoming data, logs, user, steps to reproduce. Try to replicate.

Slow - look at heap, VM monitor, 

Micro services - one has a problem, reboot it, DDOS turn it off, 

With monolith increase memory, CPU

Not responding to all requests, initial data

Deadlock - one thread blocks another on data - implement a good structure - try and avoid
synchronisation 

## Technical interview two
Buckets - based on hash code - linked list
Array - each item there is a linked list
HashMap - some confusion - language? HashCode - can have collision
HashCode collision - slows things down, has to call equals method
Overwrite hashcode method

## Domain Driven Design
Related to OO programming - 
Has used Entities, DTOs, 
Some info not needed or wanted to be shared between the database and the UI, may have calculated fields, 
MySQL, has used JPA for simple queries. Generally writes more complicated queries, Entity Manager - HQL in hibernate. 

### Single responsibility principle
Component executes one item of logic - easier to test, easier to support.

### High availability
Main target is the customer - customer should be satisfied.
Code should be understandable for all team members, code should be covered by tests, good login
Kubernetes, should follow rules based on when things go wrong.
Multiple instances - high load, 
Geography might make sense to have more instance

### Scalability
Vertical scalability - monolith, add memory
Kafka messaging, add additional nodes, 

Microservice advantages, different teams can work with different stacks. API contracts
Disadvantages - http requests between services

Monolith - single request, chain of services within. Good for smaller team.

Microservices, flexible, easy to deploy