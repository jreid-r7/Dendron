---
id: n3nw75v96j6prccy7jldceb
title: Alan Mcloughlin 5523
desc: ''
updated: 1723636850027
created: 1723636850027
isDir: false
---
C++ background - has opinions which are good

Working around contactless payments. Using the data stored on the card. Transactions can be reduced to something quite small using the on-chip data. Has been constructing a library to decode and deconstruct that transmitted data. It will run on every transaction - 4,000,000,000TX per year. Needs to be able to scale. Some apps need the data broken down and explained. EMV data - defined by EuroPay and then ignored.

Proud of the codebase - has been able to refactor.

Biggest technical challenge - long pause. Bonus feature thought up - bit off more than expected. Occasionally data gets corrupted - missing or corrupted data. An issue because tags aren’t fixed length. Bits determine tag lengths. Data can’t be stored or masked due to sensitive data.Idea of being able to reconstruct the data was appealing. Never a lot of data to recover when issues so just a do-over.

Had outgrown his last fintech job and has just promised to look occasionally.


Debugging Scenario:
1. You are responsible for a backend service fronted by a web application when you start to get reports of issues from users, what's the first steps you would take?
	1. Look for common themes
	2. Access user reports, reach out through support
	3. Ask others if there is a common thread
	4. Try to reproduce the issue
	5. Pick some of the better user tickets and see what can be done
	6. Logs
	7. Look at the output
	8. Look at the server for load
1. The backend service in a Java application running in a virtual machine; it persists data in a database. The frontend is a React web application that talks to the backend via REST APIs. You've determined that the system is slow to respond - what would you do next?
	1. Look at log timings - if they don’t they will next time.
	2. Tail the logs and run the front end and see what’s happening to narrow down where things are happening
	3. Postman request
	4. Debug tools in the browser
	5. Timings can be compared
	6. Check the database, timings, run sample sample queries
1. So the issue is that the system is receiving too much traffic, it cannot cope with the load - how could you address this?
	1. Scale up with more servers (cloud or standby) based on current load. 
	2. Work out why it might be happening and how long for
	3. Check the load balancer can handle the traffic
	4. Horizontal - do more of the same, vertical do bigger things
1. You have fixed this by scaling up/out as above. Now there is a new problem: it seems the backend service is not replying at all to requests. How do you diagnose it and fix it?
	1. Look for commonality in failures - what is making things drop
	2. When able to reproduce then look through the code where the failure occurs
	3. Local or private instance - debugger, break points
1. So it looks like a deadlock has occurred - can you explain what this is and how it can happen?
	1. Two or more processes trying to grab the same resource. Should back off but can occur when things want multiple resources but say two get one of each. Each has locked half of what they need so they lock.
	2. Expand the lock to more resources
	3. Atomic locks

Tech challenge - understood the problem and how to solve. Got stuck on some syntax