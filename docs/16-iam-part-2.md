
# IAM Part 2

### IAM Policies
- It grants or denies access to a AWS resource to any identity (user, user group, role) uses the policy
- AWS uses Policies to authorise, athenticated identities to access AWS resources
- Policy has many **Statements**
- Properties of a policy statement
    - Sid: Optional value given to identify the statement
    - Resource: Which resource or resources this statements is going to get applied upone
    - Action: Which actions of an resource this policy allows or deny
    - Effect: Whether to allow actions for resources
- Priority order of statements
    - Explicit Deny
    - Explicit Allow
    - Implicit Deny (Default)
- Two types of policies base how are the assigned
    - Inline policies: To specify special, exceptional allows or denies for an identity
    - Managed policies: Easy to use, reusable, low management overhead
        - AWS Managed Policies
        - Custom Policies

### IAM Users
- Principals: An entity (people, group of people, computers, service, etc.) trying to access a AWS resource
- Maximum 5,000 users per AWS account
- 1 IAM user can be assigned to 10 IAM groups at maximum

### IAM Groups
- Cannot login to groups
- No credentials for groups
- In AWS there's no all users group out of the box
- Cannot have groups within groups
- 300 groups per account (can be increased)
- Resource policies cannot refer a IAM Group as a pricipal to grant access, but can refer IAM Users

### IAM Roles
- IAM Role is the best candidate over IAM Users, when we don't know the exact number of identities it going to be used by
- Used on temporary basis
- A Role is created for multiple users in the same AWS account & external users, computers/services
- Roles are given permissions and internal/external identities becomes those roles for a short time to use that permissions to access allowed AWS resources and perform allowed actions upone them
- Has two types of IAM Policies get assigned to IAM Roles
    - Trust policies
        - Type of policies specifiy which identities that are allowed to & denied to associate this Role
        - If a certian identity (in the same account, in a different account, identity providers like Facebook, anonymous identities) is allowed, it is given a temporary security credentials
        - These security credentials are created by the AWS service called STS (Security Token Service)
    - Permissions policies
        - Used to grant the access to AWS resources to identities got temporariliy authenticated based on the trust policies
- Can used in
    - AWS Lambda
    - Web ID federation use cases 
    - AWS Organization
- Service-Linked Roles
    - Pre defined Roles that are already attached to a AWS service
    - Might get created during the creation of the service
    - Might request the user to create during the creation process of that service (Ex: Service setup wizard)
    - Can be created withing IAM
    - Main differenece compared to normal Roles is, in order to delete a Service-Linked Role that we should ensure that it is not being used anymore, anywhere
    - Roles passing???

### AWS ARNs
- Amazone Resource Name
- Purpose is to uniquely identify AWS resources within an AWS account
- Can use wild card to reference multiple AWS resources
- `arn:aws:[service]:::[resource name]` !== `arn:aws:[service]:*:*:[resource name]`
