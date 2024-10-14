---
id: njdjo9pas15vivez9g9ygj5
title: Indirect Product Access Issue
desc: ''
updated: 1723638383151
created: 1723638383151
isDir: false
id_imported: 1ti3hzoc4b14hm75vcw9co0
title_imported: Indirect Product Access Issue
desc_imported: ''
updated_imported: 1723636850018
created_imported: 1723636850018
---
customer id: cd9415c6-278d-4471-bb3d-f21eb8b70a51
group id: 5d6bca88-c0cc-4a0b-92ae-30febcdb1e93
user id: 4c7d3777-3742-44f9-a1c3-259eaae8911a



UserGroupService.removeUsersFromUserGroup
	getBasicUserGroup
		select * from user_group where user_group_uuid = '5d6bca88-c0cc-4a0b-92ae-30febcdb1e93';
		used to get the customer id -- id 11861
	getUserGroupProductMapRecords
		select * from user_group_product_map where user_group_id = 11861
	removeUsersFromUserGroup
		deletes from user_group_user


Loop over users and products (products from user group product map records above)

UserGroupProductService.removeIndirectOrgProductAccess

getUserProductMap
	commonUserProductService.getUserProductMap

getUserGroupProductMap
	userGroupProductRepository.getUserGroupProductMapByUserGroupIdAndProductToken

removeIndirectProductAssociationRecord
	userProductRepository.fetchUserProductAssociationReasonRecordByUserProductId_GroupMembership
	userProductRepository.deleteUserProductAssociationReasonRecord_GroupMembership

removeUserProductAccess
	commonUserProductService.removeUserProductAccess