---
id: 9nzlylk7012scc88trv5mu3
title: Org Level Todos
desc: ''
updated: 1723636850028
created: 1723636850028
isDir: false
---
Niall Curry - is there any reason to expect that customer level role names will change in the context of an organization

Are we delivering the correct thing

Integration tests - we MUST have the integration tests done for the refactors before they are released.

Catch up with Jake on EDA refactor - get a sense.
- If we progress from the current package structure to package by feature, would it at that point make it clear where we could refactor out EDA logic. It’s very entangled by its very nature. Until then let’s go with the campground analogy.

~~New APIs - are we going to go by vertical slice or by operation on the implementation of those?~~

~~Catch up with Harvey re. RRN migration~~

Conflicts and access requests storage - make sure this is on the roadmap
- Small gap here. Currently stored at customer level. Conflict work may take a bit of time. Tom’s work creates the reports but they aren’t stored. We need to create equivalent tables to store these at the org level. Further work will be required with the UI to store these.
- Create tickets and meet again with Jake and a UI person

Migration changes need to be absorbed by code crafters if things keep running on
- Matt J to finish analysis and do what he can - rest will go to next sprint
- Ticket session with Matt J around remaining migration work

~~Landing page is an Okta attribute - in order to understand the impact here we will need write a script to page through the Okta users and look at this attribute.~~
 ~~Where does one set the default landing page?~~
- ~~Ticket this ERV investigation~~ - with gatekeepers

Is there a ticket for the back to platform terminology - Platform Home becoming Products and Services?
- Ticket this

We need to reconsider the UAP updated event to make the event regional