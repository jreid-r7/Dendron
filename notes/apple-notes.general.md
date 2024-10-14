---
id: ugbi3qxxhen2izonoo06p80
title: General
desc: ''
updated: 1723636850021
created: 1723636850021
isDir: false
---
In terms of PoCs - what do we need that will make things better? Bring us a problem that needs solved.

DB Proxy - chat to Mark Freebairn

1 Instance size down - can we do this wrt to I/o and how much would it save?

**PostgreSQL**
autovacuum_max_workers = GREATEST({DBInstanceClassMemory/64371566592},3)
max_connections = LEAST({DBInstanceClassMemory/9531392},5000)


| Size | vCPU | Memory in GiB | Network | AV workers | Max connections |
| -- | -- | -- | -- | -- | -- |
| db.m6g.large | 2 | 8 | Up to 10Gbps | 3 | 900 |
| db.m6g.xlarge | 4 | 16 | Up to 10Gbps | 3 | 1800 |
| db.m6g.2xlarge | 8 | 32 | Up to 10Gbps | 3 | 3600 |
| db.m6g.4xlarge (current) | 16 | 64 | Up to 10Gbps | 3 | 5000 |





Chat to Ceara about the project plan



Get sign off on API changes and notify product esp. Derek Coetzee



Create a roadmap entry for UAP composer efficiency