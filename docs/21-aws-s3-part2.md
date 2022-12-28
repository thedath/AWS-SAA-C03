# Simple Storage Service (S3) - Part 2

Continuing from [Simple Storage Service (S3) - Part 1](./13-aws-s3-part1.md)

- Is private by default
- Access is given through resource policies
    - Identity policies
        - What can be accessed!
        - Attached to identities
        - Can only be assigned to identities in its' account
    - Resource policies
        - Who can access!
        - Attached to resources (Ex: S3)
        - Can reference identities from the same account & external accounts as well
        - Can also ALLOW/DENY anonymous principals
        - Use 'Principal' property in the policy document to define who can access this resource
        - `"Principal": "*"` - Every identity in this account, any identity from any external account, any anonymous identities
- 
