
# AWS Organizations

**Master account === Management account === Payer account**

- An organization has only one Management (master) account
- An organization can have zero or more Member accounts
- Organization root: Container within the organization holds the its' management account, the member accounts (Not the AWS account root user) & other organizational units (OUs)
- Organizational Unit: 
- Consolidated billing: Payer account gets to pay the bill, bill is aggregated using other account bills
- Consolidations of reservations and volume discounts

### Service Control Policies (SCPs)
Controls the things each account in the organization can perform
-Don't grant any permissions, just bounderies, control what is allowed & not allowed
- SCPs are assigned to management account, member accounts, organizational root & other organizational units (OUs)
- Assigning SCPs directly to the management account it self or to the organization root has no effect on the managment account what so ever
- Allow List vs Deny List

<img width="1728" alt="image" src="https://user-images.githubusercontent.com/56229135/209659023-05a97477-a92b-48c9-9eb8-5c8e40465c30.png">
