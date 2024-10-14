---
id: apu2iwuxkgw7mm6rucarxsc
title: External Access Request Db Changes
desc: ''
updated: 1723636850024
created: 1723636850024
isDir: false
---
`-- UPDATE external_user_access_request INNER JOIN ``user`` ON external_user_access_request.okta_user_id = ``user``.okta_user_id SET external_user_access_request.user_id = ``user``.user_id


`-- ALTER TABLE external_user_access_request
`--    ADD user_id VARCHAR(64) NULL;`

