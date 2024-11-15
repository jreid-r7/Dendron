---
id: fkuugywqz8nkdkqfz7k61er
title: ACL Workshop
desc: ''
updated: 1729589827996
created: 1729499535753
---

## Day one summary

### ACL Names to product grouping attribute

1. Note the use of "ACL Name" rather than tag
2. Our ACL is *allow list* only - no other permissions will be supported
   1. Consider designing for more in the future
3. Exclusions?
   1. Design for this - there is a use case
4. 1:1 mapping of ACL Name to grouping attribute
5. The ability to merge ACL Names so that they have a 1:many mapping to grouping atttributes
6. Can merging happen on data import?
7. ACL needs to support where clauses in the data mesh
8. We are not unifying any current concepts - we are enabling an ACL to be connected to a current grouping attribute
9.  We are solving ACL - not some universal tagging service
10. A user will be able to audit their ACL
11. They will be able to see how it is applied
12. They will be able to do this in one place

