

# IAM (Identity & Access Management/Manager)
Globally recilient (of a person or animal, able to withstand or recover quickly from difficult conditions.) service

- Provided for Free, No Cost.
- Is a global database
- Globally recilient
- Unique to, and trusted by only its' associated account.
- An account has single IAM
- An account trust its'  IAM 100%
- So, account trust identities created by its' IAM 100%, like it trust its' IAM.
- Used to create users for a AWS account.
- By default IAM users does not have any access.
- Uses IAM Roles with Groups when creating IAM users to grant necessary access
- Cross account permissions???
- Support identity federation??? (Active directories, web identities like Facebook & Google)
- Support MFA???

## Different types of identity objects in IAM

|||
|-|-|
|Users|People or applications that can access AWS resources in an AWS account|
|Groups|Collection which represents set of IAM users or applications that can access AWS resources in an AWS account|
|Roles|Other AWS resources/services that can access AWS resources in an AWS account. Roles are used to grant access to uncertain number of resources (internal or external) for AWS resorces in your AWS account. Ex: EC2 instances writing to a s3 bucket. |

## IAM Policies

Basically rules which defines whether a certain user, user group or role can access a certain resource or not. IAM policy itself have no meaning untill its' being assigned to a user, user group or role.

## Duties of IAM

1. Manage Identities (IDP, Identity provider)
2. Authenticate IAM Users & Roles
3. Authorise IAM Users & Roles
