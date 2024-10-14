---
id: hdw7wejqwmc6335c73qq5sk
title: Sajitha Nair 9523
desc: ''
updated: 1723636850027
created: 1723636850027
isDir: false
---
Started in Sybase, scripting, Unix. Last 9 years or so with Citi.
Perl - P&L calculations with a Perl wrapper to set up the environment.

Java - P&L calculation app written in C++ - a bit of a black box for the team. Got a C++ resource to decipher the code and then re-wrote it in Java. This was a micro-service. Reference data.

SFTP trade data and batch processed - sent it downstream via SFTP. PubSub model for the referential data. Ref data was accessed when SFTP - file watcher. MQ.

SVN - Github

Toughest technical challenge
Migration from C++ to Java - lack of expertise and the need to work around another person’s schedules. Matching numbers was a challenge - used doubles and floats.
How was this tested?
Production dumps to test and compared to Java output. User acceptance tested. Lots of manual testing to make sure figures matched also used unix scripts.

JUnit - no
Project lasted 8 months - dev 2 months, the rest was testing

Prior to this - Sybase and scripting
Requirements gathering 3 weeks, test case prep, sort of test driven, coding. Roughly 8 weeks.

Good general knowledge of SDLC

Debugging
1. First steps -  More from users - what sort of issues? Can’t connect? Timeouts? Bad data? Logging - System.out.println - Not used log4j Recreate the issue
2. Response times - is it time from the database? Look there first. Next look at network issues for time to front end. Doesn’t know developer tools in browser Has seen issues at first Monday after month end - has done performance tuning using query plan. Turned out to be a Sybase version issue Run individual queries
3. Add in load balancer - multiple servers. Scale horizontally to add more servers. Horizontal - add more servers Vertical - increase capacity of existing server Reasons for one over the other - she said expense When scaling up the service - scale similarly impacted services - easy with loosely coupled apps. Need to consider tightly coupled systems
4. Look at connections. That there is available data. Look at memory, space, CPU utilisation.
5. Deadlock - one process waiting for a resource that another is using and that one is waiting for something the first is using. May need to kill one process.  In Java make sure threads are synchronised. Downside with performance.

OO principles
Inheritance - common functionality to super class
Abstraction - data hiding
Encapsulation - getters/setters - can add validation here
Polymorphism - use an interface to create abstract methods implemented in implementing classes. Allows different objects to implement methods in a different way e.g. animals may play in different ways.
Static - functionality as just described
Dynamic polymorphism - method overloading
Overloading - signature changes
Overriding - signature the same but method changes

Interfaces and abstract classes
Abstract can’t be instantiated but can have concrete methods. 
Interfaces - all fields are static and final - not necessarily the case with interfaces
Abstract for related classes
Interfaces for disparate. Multiple interfaces can be implemented. Can extend one.

HashMap
Key Value pair. No duplicate keys. Quick to traverse and retrieve. Not indexed - accessed by key. No sorting

Class/Object
Class defines the object
Object is created with new()
Three sections of class - declaration, methods, constructor

No design patterns

Caching - no
Keep data in memory so that it is faster to retrieve. Redis, ElastiCache
Downsides - old data, memory usage

AWS components
EC2, S3, CloudFront, databases
S3 - buckets and keys - keys for access, buckets to store

Scripted code - actual source code - code in .java file
javac transforms that to byte code
JVM transforms to machine code
Perl is interpreted
Really shaky here

Eventual consistency - data not consistent all the time - data processed in memory but updated later
Part of asynchronous processing

CAP theorem
Bit shaky on synchronous/asynchrous