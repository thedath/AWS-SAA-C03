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
- There's limit of 5GB for a single PUT upload
- "Block Public Access": Overrides what resource policy says, blocks the access to the public anonymous identities
- Static Site Hosting
    - `index` & `error` page is mandatory
    - To setup a custom domain, custom domain name & bucket name should match
- Object versioning
    - By default it is disabled
    - Once enabled, cannot disable again btu, can be Suspended
    - Object IDs are set to NULL when versioning is disabled
    - Delete Marker: Is a special marker in object version history added by AWS S3 to refer that object as a deleted object
    - Delete Marker can be deleted and doing so will bring back the last availble version of the object
    - All versions are billed
- MFA Delete
    - MFA is required to change bucket state, delete a version, it required a MFA
