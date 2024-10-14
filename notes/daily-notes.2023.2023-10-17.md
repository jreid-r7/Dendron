---
id: 7cqbn9ipq8z7vjgv58gzod5
title: 2023 10 17
desc: ''
updated: 1723636850028
created: 1723636850028
isDir: false
---
Are we happy with the level of UAP Composer Optimisation?
*Org level wasn't processed and conflicts are not being generated yet. Jake and David working on that - question over protobuf for the conflicts messages. DataDog monitoring needs to be updated to cover this.*
35 minutes yesterday - celebrate. What was the jump at 11:20? *Scaled up.*
*There will be a task to re-run a full metadata update in the stretch starting end of October. If this succeeds and performance is acceptable then we close the optimisation piece.*

Conflicts - need to review Johnsy's stuff and work out the scope of the next stretch. Also need to review any UX work done on this. I need to review Figma. MVP

Access requests - too much returned. We get open requests plus the full history of closed. What RBAC changes are needed, have a chat with UX. What is the connection to OLR? MVP

UAP Lite - how badly is this still needed - there was talk that a lot of this functionality was going to be covered by the Policy Service - review with Chris/Tom.

Product Admin experience - new - need a sense of what this might involve.

Resource Sets - kinda fundamental - OLR MVP

Get UAP Lambdas - need to be org level - MVP (maybe core only)

Regional caching - is this part of the OLR MVP or is this Operational. I think it's Operational
*Definitely operational - not needed to deliver OLR*

Class 1 - need to review the work involved here and come up with a plan. MVP

Auth bypass - ~~I can't remember what this actually is ...~~
*We currently have three API keys and each responds to a UAP. Technically this doesn't need a UAP and could be simplified. The security filters just need to respond to the key. 
This may also affect the Kong work that Olivia was to look at - currently our Kong gateway stuff is understood incompletely by the team and may not be configured as intended.* Operational

CMS UI - there are a few screens in CMS that are way out of date and use V1 role concepts. Identify these and plan accordingly. MVP or Operational?
*This may be less than expected - these screens operate in an org context already. They will need updated to work with V2 roles.*


