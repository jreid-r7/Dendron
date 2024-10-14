---
id: agiq2016lj91cih7i5if4n4
title: 2024 07 01
desc: ''
updated: 1723636850033
created: 1723636850033
isDir: false
---
## Stretch planning
### Product admin experience
Most back end data contains the product token so filtering is easy
Need to implement guards on API endpoints to prevent updating when not allowed
#### Access request BE
1. Filter KPI
2. Filter list
3. Protect Accept/Reject endpoints
### Regional cache lambda

### Something else - EDA?


# TODO
- [ ] Finalise informal mentors for Priyal and Cory
- [ ] Chat to them and get them to organise 1:1s etc.
- [ ] Get Jake to set fortnightlies with Cory
- [ ] Reiterate with the interns to use the technology to reach out - doesn't always have to be someone in the office
- [ ] Involve Nick Barbariyskiy

-- UPDATE external_user_access_request INNER JOIN `user` ON external_user_access_request.okta_user_id = `user`.okta_user_id SET external_user_access_request.user_id = `user`.user_id


-- ALTER TABLE external_user_access_request
--    ADD user_id VARCHAR(64) NULL;

