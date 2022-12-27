
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
- Two types of policies
    - Inline policies: To specify special, exceptional allows or denies for an identity
    - Managed policies: Easy to use, reusable, low management overhead
        - AWS Managed Policies
        - Custom Policies

### IAM Users
- Principals: An entity (people, group of people, computers, service, etc.) trying to access a AWS resource

### AWS ARNs
- Amazone Resource Name
- Purpose is to uniquely identify AWS resources within an AWS account
- Can use wild card to reference multiple AWS resources
- 
