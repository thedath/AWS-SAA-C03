# Simple Storage Service (S3) - Part 1

- Global service
- Regionally recilient
- Data is replicated amoung AZs
- Unlimited data & multi-user access
- S3 contents have two types
    - Objects
        - Can range between zero & 5TB in size
        - Has two properties
            - Key: Name of the object
            - Value: Data of the object
    - Buckets
        - Bucket names needs to be unique globally
        - Bucket names should be all lowercase and 3 to 63 characters long
        - Should start with either lowercase letter or a number
        - Shouldn't be in the format of an IP address (Ex: a.b.c.d.png)
        - Has a soft limit of 100 of buckets per account
        - Has a hard limit of 1000 of buckets per account
        - Cannot srat with `xn-`
        - Can hold unlimited data
        - Has a flat structure, everything is created in the root, no folders & sub folders (but listing a bucket could give folders & sub folders experience)

### S3 Patterns & Anti Patterns

- S3 is not a file or block storage system, it is a object storage system (block: vertual hard disk)
- You cannot browse into a S3 bucket like you would do in a file system
- You can't mount S3 bucket as a mount point or a volume
- Great for offloading
- Most of the time S3 is suitable to accept input data for an AWS resource and as well as output data of an AWS resource
