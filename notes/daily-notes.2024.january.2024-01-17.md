---
id: oxwsfdzbw51kxtwlhitkfcl
title: 2024 01 17
desc: ''
updated: 1723636850033
created: 1723636850033
isDir: false
---
\#ipims-int
Paul Deardorff request
User: andrew_tran@rapid7.com
Problem was - Attempting to add a new user with an existing email address. Issue communicated back and response received. Issue sorted.

## Tasks
- [x] Check logs for tagged resource set gets - possible omission
- [x] Find out what to do with all the left over tagged resource set apis
- [x] Ticket to rename TaggedResourceSetController to UserTaggedResourceSetController
- [x] Tickets to add V2 pass throughs (or proper org level?) for remaining Tagged Resource Set endpoints - Users
- [x] Tickets to add V2 pass throughs (or proper org level?) for remaining Tagged Resource Set endpoints - User Groups
- [x] PLATSERV-948 V1 tagged resource set modifications - check this covers everything
- [x] Update timeline on Friday's MCE Post Mortem
- [x] Re-organise Resource Set Tasks
- [x] Ticket to deprecate all existing V1 APIs that have a V2 equivalent

## Trivia
RBAC uses the request translation on api keys because it behaves as both class 2 and class 3

## Tagged Resource Set API Usage (last 30 days)
**PUT** - V1 used for users and user groups
**PATCH** - V1 used for users found
**GET** - V1 users and user groups
**DELETE** - Unused last 30 days, possibly ever