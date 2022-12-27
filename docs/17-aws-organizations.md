
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
- SCPs are assigned to management account, member accounts, organizational root & other organizational units (OUs)
- Assigning SCPs directly to the management account it self or to the organization root has no effect on the managment account what so ever
