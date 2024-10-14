---
id: fv2q6w5pf3uensk5khv4rcn
title: Phillip Wilson 17523
desc: ''
updated: 1723636850027
created: 1723636850027
isDir: false
---
Graduated 1996
Software and hardware design with FG Wilson
Nortel - some Java
American Dynamics for about a year - quite chaotic, but fun
ASG - network monitor, managing a network topology Latens - backend work, Java. On demand video, EPG queries. Servlets to handle queries. Java 6
HPE - storage product - REST?
Ammeon - contractors. Writing tests in Python for the CI/CD pipeline. Building micro services from existing free products and making those available to other internal teams.
Anomaly - mostly Python with some Java and shell scripting. Several years since writing serious Java

Some investigative work around AWS Cloudwatch, CloudTrail, ALBs, etc. Working on a log tracer.

Whiteboard session
Working on the Match product. UI with backend, cloud and on-prem. Another database connected with the logs
Correlation engine to match data between logs and the threat database

Debugging Scenarion
1. First steps What is the actual issue? Error screens, 401, wrong info displayed. Good description and screen shots from users. Make and informed decision as to where to go next. Look at traffic between backend and UI. Packet sniffer, quicker to look at logs for errors. Good logging is important. Try to recreate the problem. Look for invalid parameters or garbled payload. Trace back through pathway where that information was built. What sort of transformations need to take place.
2. System is slow Look at resource situation - vm tools, memory, CPU. Look for processes pinning the CPU. Look in the app for a code path that is slow to process. Too much info being pulled back. Look at the database - is it alive or just not responding. Is there a db issue. Networking between FE and BE. Browser developer tools. CURL certain APIs. Postman, etc. Connect to DB.
3. Too much traffic Add a load balancer, scale it up adding extra resources to service additional traffic. Increase the size of the vm. Autoscaling.
4. No response from the backend Are requests getting through? Logs, etc. Is the correct application running? Stack trace.
5. Deadlock Essentially two threads waiting for a resource that cannot be released yet. Use a semaphore.  Locking shared memory. Synchronised in Java. 



Tech take 2

Principles of OO
Inheritance - parent and child classes - same methods and members, initialisation objects. Child can add more.
Abstraction - only allowing access to required data. Hide the implementation
Encapsulation - getters and setters. Data hiding, only access to certain members
Polymorphism - the ability to pass or allow code to work on different types of data. Different methods with the same name to work on different data. Overloading. Overriding parent class/ child class different implementation. Overloading runtime.

Design patterns
Factory - initialisation of various data sources based on passed in config
Singleton - only want one class for config to prevent race conditions, etc.

Interface (Java)
Implemented - interface has no implementation. Implementing class implements those methods.

HashMap
Like a dictionary - key value pair. Easy to search. Fast.


REST APIs
Client talks to server, e.g. web app. 
Retrieve info for UI. Call made. POST, PUT, GET, DELETE, CRUD - create retrieve update delete
POST for create. Call URL - data in payload, encrypted SSL, normally JSON, xml in the olden days

URL Shortening
Gave tinyurl as example
A means to access the functionality - web app - handle requests to the back end
External api and web based api
REST API for web app to talk to BE
BE will need an algorithm to transform the large URL to something small
Database - key is the small string, value is the large url, maybe redis
URL passed in via the interface, button clicked. Info pushed to database along with unique key
Redirect
Performance - network bottle neck, parallel requests. Might need to move to somewhere that provides resources and bandwidth, e.g. containers with more networking. More I/O and processing. More storage - database will grow with popularity. Cluster of DBs. Timeout mechanism on URLs being stored - TTL. Offer a premium service for extended storage.
Archive of older data, slower accessible storage, several levels of response. Limit network access - throttle requests.