 Lab 3 – Group-Based Licensing and Dynamic Groups

This lab covered assigning licenses through group membership rather than individually, and creating both regular and dynamic groups.

Exercise 1: Create a security group and add a user

Task 1 – Check if Delia Dennis has access to Office 365
- Signed in as Delia Dennis at Office.com in an InPrivate window.
- Selected Install apps > Microsoft 365 apps, confirming no license was assigned and no apps were available yet.

Task 2 – Create a security group in Microsoft Entra ID
- Created a new security group:
  - Group type: Security
  - Group name: sg-SC300-O365
  - Membership type: Assigned
  - Owner: the administrator account
  - Member: Delia Dennis
- Confirmed the group appeared in the All groups list.

![Group sg-SC300-O365 created](lab3-01-sg-o365-group.png)

Task 3 – Add an Office license to sg-SC300-O365
- In the Microsoft 365 admin center, under Billing > Licenses, selected the Office 365 E3 license and assigned it to the sg-SC300-O365 group.
- Confirmed under Licenses, with sg-SC300-O365 listed as a Group
  with 2/20 licenses assigned.

![License assigned to sg-SC300-O365 group](lab3-06-license-assigned.png)

Task 4 – Confirm the Office 365 license
- Signed in again as Delia Dennis at Office.com.
- Confirmed Microsoft 365 apps (Outlook, Word, Excel, PowerPoint,OneNote, OneDrive, SharePoint, Clipchamp) were now available, with no license warning.

![Delia Dennis apps available after license](lab3-07-delia-apps-available.png)

 Exercise 2: Create a Microsoft 365 group in Microsoft Entra ID

Task 1 – Create the group
- Created a new group:
  - Group type: Microsoft 365
  - Group name: Northwest Sales
  - Membership type: Assigned
  - Owner: the administrator account
  - Members: Alex Wilber and Bianca Pisani
- Confirmed the group appeared in the All groups list.

![Group Northwest Sales created](lab3-02-northwest-sales-group.png)

 Exercise 3: Creating a dynamic group with all users as members

Task 1 – Create the dynamic group
- Created a new security group
  - Group name:SC300-myDynamicGroup
  - Membership type: Dynamic User
  - Dynamic membership rule: `user.objectid -ne null`
- Created the group, which includes both member and guest users.

![SC300-myDynamicGroup created](lab3-03-dynamic-group.png)

Task 2 – Verify the members have been added
- Opened SC300-myDynamicGroup > Members and confirmed 26 group members had populated automatically from the rule.

![SC300-myDynamicGroup members populated](lab3-08-dynamic-group-members.png)

Task 3 – Experiment with alternate rules
- Tested two alternate dynamic membership rules:
  - Guest users only: `(user.objectId -ne null) and (user.userType -eq "Guest")`
  - Member users only: `(user.objectId -ne null) and (user.userType -eq "Member")`

![SC300-GuestUsersGroup1](lab3-04-guest-users-group.png)
![SC300-MemberUsersGroup](lab3-05-member-users-group.png)



 Key takeaways from this lab
- Group-based licensing is the recommended way to manage licenses at scale assigning a license to a group automatically applies it to every current and future member.
- Dynamic groups use membership rules (based on user or device attributes) to stay automatically up to date, unlike static groups which require manual membership management.
- Dynamic membership rules are case-sensitive — `objectId` and`userType` must be typed exactly, or group creation fails.
- Both security groups and Microsoft 365 groups can use dynamic membership rules.
