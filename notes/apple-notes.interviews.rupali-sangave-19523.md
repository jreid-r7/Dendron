---
id: wtl4c9xxhrasbts7pfi333b
title: Rupali Sangave 19523
desc: ''
updated: 1723636850027
created: 1723636850027
isDir: false
---
Recent experience
Working on a project for BT - fault tracking system. Self service fault diagnosis.
Spring MVC, Angular JS, Spring-Boot, REST (moving to micro-services?), MongoDB stores question set. One of the team lead (not completely) designs small features.
BE concentration for her team.

REST over HTTP currently.

Has done analysis on dividing the large application into smaller single responsibility APIs.

Big tech problem - migrating a service from windows to linux. Some .dll files only supported in windows - .so on linux.
Doesn’t know which is which or what they do.

Principles of OO
Encapsulation - hiding variables, getters, setters
Inheritance - parent child relationship, overriding, etc.
Polymorphism - Runtime and compile time. Compile time - two classes related through inheritence - overloading, runtime overriding. - mixed up
Abstraction - user should not know how the thing works

Design patterns - MVC, Singleton. Knows creational, Abstract factory
Singleton - only one instance should be created.
Why?  No idea
Behavioural
Knows names but hasn’t used.

Interface - for full abstraction. Can define methods - public and abstract. Implementor must implement those methods. As a solution for no multiple inheritance.

HashMap
Key value. Stores data in terms of key and value. Uses equals and hashcode. Uses the has to store the value against a key. Equals used to retrieve. Calculate hashcode of the key. Same key, replace the value. New key, new value. Uses linked list for value.

Synchronous/Asynchronous synchronous blocking, asynchronous don’t wait for response.
MDB carries the message. Listen to the queue.

CompleteableFuture. Run method in threads return nothing. Callable interface can return something. Thread only.

Process/Thread 
Process whole application
Thread runs behind the process - lightweight process behind the process
Timeslicing, multi-core

REST - http protocol, JSON or XML, likes JSON better, easier to convert to objects, XML needs a DOM parser

Spring advantages
Principle of IoC, don’t need to worry about dependency management, 
Controller - receive the request and map it and call the service

URL shortener
Encode the url, use unique values, like a key value pair, store key and value in a database
Store the long URL in the database - maybe encode for security

What if this becomes popular?
Needs a domain - we have it
Can’t store unlimited URLs - what could we do? Purge logic on database - e.g. 15 days worth
Could some be stored longer? Active or not.
Service finds long URL and returns
We could count the numbers of times the URL is used? 
Lots of users - move to the cloud for storage,
What else? Responsibility of cloud provider to maintain.
What can cloud provide? Increase instances, ELB
Large traffic - increase instances, time limit?, 

Questions
Feedback