---
id: ibyuru62zlbz4rgqpc8q85o
title: Product Admin Experience
desc: ''
updated: 1723636850024
created: 1723636850024
isDir: false
---
Requests - should a product admin be allowed to approve? If so, which ones?

Can only see users who have access to the product.

Identify core screens
Identify core API endpoints

## Product Users List
UI - list screen - as exists but new KPI, use existing API
BE - produce a filtered list

### Create user screen
UI - Hide Platform Admin controls. Groups - only ones with your product
BE - email validation endpoint - update to within account

## User groups
Hide groups that don't have product

## Planning
1. No overview page
### Users list
Limited to only users that have the product, may only see myself. KPI bar limited. 
BE - users API changed - filtered?
BE - KPI API changed - count only product users (configurable), split to user types (see platform admin experience)
UI - KPI - remove unused metrics based on context, split to user types 
UI - Users table - modified to filter
Filters for next stretch
### Create user
Product admin may create net new user. 
UI - An existing user (new concept) - expose to Platform Admin also
1. Check email address
	1. is it in my account?
	2. populate info
	3. say the user exists
	4. link to profile
2. In the user's profile, assign the product
No platform admin assignment available in create user.
UI - use customer UAP for now. Switch to policy service API once available
BE - provide a policy service API with required admin info for a user - Platform Admin, Product Admin, etc.
UI - remove Platform Admin block 
BE - look at permission checks for all create/update APIs
BE - API that checks the email address needs to return user ID if the user exists in the caller's account, only true if it's in another account
### User profile
UI - Hide - delete user, reset mfa, etc.
May edit name/timezone.
May not edit platform admin status
UI - continue use customer level UAP, switch to policy service when available
BE - check permissions on the mutation
### Group assignment
May only assign access to groups that only have your product. You cannot assign access to a group that contains another product that you are not admin for. You will be able to see these, but not assign access.
1. all your products - assignable
2. your product plus some others - restricted access
3. only other products - hidden
UI - reflect the changes above - restricted access flag, info panel
BE - decorate existing groups call to reflect the above
BE - update the mutation APIs with auth checks for this
### Group view
To avoid weird experience - show same as read only state but only edit own product stuff
May only assign product if it's a full view.
UI - reflect restricted
BE - auth check on assignment
Only able to manage group members on full view. All buttons hidden on restricted view.
### Add user to group?
Possible - Add user, enter email address
Possible - just show all users
BE - same API as the create user check, check auth on add user
UI - provide a warning if the user is already assigned
### Assign/manage Individual privileges
BE - only return products the administrator is a product admin for - the user may have other products
UI - No change
### Roles
Create, edit and delete while not assigned
BE - add check for role assignment
Experience not available for products without published features
Custom roles not happening for now
May only see roles linked to their product
### Conflicts
Same concept of access/restricted access/no access?
See conflicts, defer to platform admin
User conflicts only, groups out of scope
Same gist for insufficient access
Basically show conflict, link to user profile
### Access requests
Product access requests for your product only
Closed filtered the same way



