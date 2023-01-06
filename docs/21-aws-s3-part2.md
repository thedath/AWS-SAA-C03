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
- Supports Multipart upload
    - Minimum file size is 100MB
    - Maximum 10,000 multiparts
    - Size of one multipart must be between 5MB ~ 5GB
    - The last multipart can be lessthan 5MB
- Accelerated Transfer: Uses AWS Edge locations
    - 2 restrictions for enabling
        - Bucket name cannot contain periods (`.`) 
        - Bucket name should be DNS compatible
    - Creates a different type of S3 URLs
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
- MFA Delete: MFA is required to change bucket state, delete a version, it required a MFA
- Encryption
    - Buckets aren't encrypted, objects in the buckets are encrypted
    - 2 supporting methods (refering to encryption at rest, not in transit)
        - Client side encryption
        - Server side encryption
            - SSE - C (Using a customer provided key) - Not suitable if compute is taking toll
            - SSE - S3 (Using AWS S3 Managed key) - Most of the time this will be the go-to. But, not suitable if needs to handle key rotation, if needs to define a custom key, if need role seperation (Ex: Allowing certain group of people to create buckets, but they cannpt view the encrypted files)
            - SSE - KMS (Suing a key managed by KMS) - Ideal when role seperation needed. Uses AES256 algorithm.

## Object Storage Classes

### Common features
- Redundacy check using MD5 checksum
- Cyclic Redundancy Check (CRC): To check & fix any data curruption
- S3 responds with HTTP1.1 200 status, if a accessing object stored durably
- Once configured, cannot be replaced by a different class
- Stored in at least 3 AZs
- Object durability is '11 nines': 99.999,999,999% per year (1 object loss per 10, 000, 000 year)
- Has a "milliseconds first byte latency"
- Can make publicly available

### S3 Standard Class
- Fees
    - Storing: $x per month, per GB
    - Transfering IN: Free
    - Transfering OUT: $x per GB
    - Requesting: $x per 1,000 requests
    - Retriewing: Free
    - Minimum duration charge: No
    - Minimum size charge: No
  
### S3 Standard - Infrequent Access (IA) Class
- Fees
    - Storing: **Half of S3 Standard**
    - Transfering IN: Free
    - Transfering OUT: **Half of S3 Standard**
    - Requesting: **Half of S3 Standard**
    - Retriewing: **$x per GB**
    - Minimum duration charge: **$x for 30 days**
    - Minimum size charge: **$x for 128KB**
- Ideal for:
    - Longed lived, important data
    - Infrequently accessed data
    - Don't use it for small files
    - Don't use it for temporary data

### S3 One Zone Infrequent Access (IA) Class
- Special Notes
	- **Stored in a one availability zone (AZ) within the region (No multi AZ resiliant mode)**
	- **Object durability is '11 nines': 99.999,999,999% per year, assuing AZ does not failes (1 object loss per 10, 000, 000 year)**
- Fees
    - Storing: **Less than S3 Standard-IA**
    - Transfering IN: Free
    - Transfering OUT: **Less than S3 Standard-IA**
    - Requesting: **Less than S3 Standard-IA**
    - Retriewing: **Less than S3 Standard-IA**
    - Minimum duration charge: **Less than S3 Standard-IA** (30 days)
    - Minimum size charge: **Less than S3 Standard-IA** (128KB)
- Ideal for:
    - Longed lived, non crytical data
    - Infrequently accessed data
    - Storing non-critical data
    - Data that are easily replaceable
    - Cross regional, replicated data
    - Intermediate, temporary data

### S3 Glacier - Instant Retrieval
- Fees
    - Storing: **Less than S3 Standard-IA Standard**
    - Transfering IN: Free
    - Transfering OUT: **Less than S3 Standard-IA Standard**
    - Requesting: **Less than S3 Standard-IA Standard**
    - Retriewing: **Less than S3 Standard-IA Standard**
    - Minimum duration charge: **$x for 90 days**
    - Minimum size charge: **$x for 128KB**
- Ideal for:
    - If you want to access data instantly
    - But not frequently thatn 3 months (quarterly)

### S3 Glacier - Flexible Retrieval
- Special Notes:
    - Data aren't immideately available
    - Data not publicly availble out of the box (Meta data can)
    - By default data are Cold
    - Data will be warmed & delivered on request
    - S3 bucket will store pointers to the actual object
    - 3 retrieval types
        - Experdite: 1- 15 minutes
        - Standard: 3 - 5 hours
        - Bulk: 5 - 12 hours
    - Firs byte to receive latency: minutes to hours 
- Fees
    - Storing: **Less than S3 Standard-IA Standard**
    - Transfering IN: Free
    - Transfering OUT: **Less than S3 Standard-IA Standard**
    - Requesting: **Less than S3 Standard-IA Standard**
    - Retriewing: **Less than S3 Standard-IA Standard**
    - Minimum duration charge: **$x for 90 days**
    - Minimum size charge: **$x for 40KB**
- Ideal for:
    - Best for archival data
    - Data no need to instantly delivered

### S3 Glacier - Deep Archive
- Notes:
    - Same as S3 Glacier - Flexible Retrieval but
    - Data in frozen state
    - Take more time to warm data
    - Cheaper than Glacier Flexible
    - 2 retrieval types
        - Standard: 12 hours
        - Bulk: 24 hours
    - Firs byte to receive latency: hours to days 
- Fees
    - Storing: **Less than S3 Glacier - Flexible Retrieval**
    - Transfering IN: Free
    - Transfering OUT: **Less than S3 Glacier - Flexible Retrieval**
    - Requesting: **Less than S3 Glacier - Flexible Retrieval**
    - Retriewing: **Less than S3 Glacier - Flexible Retrieval**
    - Minimum duration charge: **$x for 180 days**
    - Minimum size charge: **$x for 40KB**
- Ideal for:
    - Best for archival data
    - Data no need to instantly delivered

### S3 Intelligent Tiering
- Special Notes
    - 5 levels
        - Frequent Access
        - Infrequent Access
        - Archive Instance Access
        - Archive Access
        - Deep Archive
    - Tiering is automatically handled

## S3 Lifestyle Configuration
- Set of rules
- "Do this, when this is true"
- Can apply versioned S3 buckets
- Ex:
    - Delete an object after ceratin time period
    - Archive an object after ceratain time period
    - 

## S3 Replication
- Source & destination buckets can be in two seperate accounts
- Cross Region Replication (CRR)
    - Role is being created in the source bucket to grant access to read data on the source bucket for identity going to assume this Role
    - Destination bucket policy is being created to grant access to the role of the source bucket to write replicating data into this bucket
- Same Region Replication (SRR): Source & destination buckets are in the same AWS Account
    - Role is being created in the source bucket to grant access to read data on the source bucket for identity going to assume this Role
    - No need of a destination bucket policy since both buckets are in the same AWS account
- Replication config:
    - All objects or subset of objects, can be specified by using filters
    - Destination storage class: Is the same as the source's storage class by default
    - Ownership: Ownership of the destination bucket
        - Source & Destination buckets created in the same account: Owned by the same account
        - Source & Destination buckets created in two different accounts: By default bucket will be owned by the source account, will not be able to access by destination account. Can be override.
    - Replication Time Control (RTC): By default its a 15 minutes window. Enable when source & destination buckets need to be in sync as closely as possible
    - IMPORTANT
        - Configured between two buckets
        - Only the objects being added/changed after the configuration, are considered for the replication
        - Versioning must be available in the both buckets
        - One way replication: Destination changes won't replicated in the source
        - Replication with Encrption
            - Files encrypted with SSE-S3 are replicated
            - Files encrypted with SSE-KMS are replicated, with additional configurations
            - Files encrypted with SSE-C cannot be replicated
        - Can replicate objects only owned by the source account
        - System events aren't replicated, only user events
        - Buckets of Glacier Flexible Retrieval & Glacier Deep Archive storage classes cannot be replicated
        - Delete markers are not replicated by default
- Why use replication
    - SRR
        - Log aggregation
        - Sync data from PROD to TEST account, or other way around
        - Resilience with strict sovereignty
    - CRR
        - Globally resilience storage solutions
        - Latency reduction
-  S3 Pre-Signed URL: Generated URLs with neccessary credentials embedded granting access to an private object in a S3 bucket for a limited time period
    - It is possible to generate a Pre-Signed URL for an object in a bucket that you don't have the access (you only can generate, cannot access)
    - When accessing a pre-signed URL, it matches the permissions of the identity which created that URL, right now

## S3 Select & S3 Glacier Select
Filtering object selection from the S3 side itself, without getting the whole object to the application's side. Types of object can be filtered: CSV, JSON, Parquet, BZIP2 of CSV & JSON

## S3 Event Notification
Receive nofications on channels like SQS, SNS & Lambda when events occure on a S3 bucket. 

Events
- Put, Post, Copy, CompleteMultiPartUpload
- Delete, DeleteMarkerCreated
- Restore Initiated & Completed: When object beinged retrieved from Archive storages such as Glacier
- Replication: Within Threashold, Beyond Threshold, Failed, Completed

## S3 Logs
Logs (Apache like) are written into a target bucket. 

## S3 Object Lock
- Write-Once Read-Many (WORM): No deletes, No overwrite
- Can only be enabled for new buckets
- To enable for existing buckets, need to contact AWS support
- Requires versioning to be enabled, so eventually object version are being locked
- Can be define for each object version or can be configured as a bucket defaults
- Retention of the locked objects (2 types). An object version an have both of them, one of them or none of them.
    - Retention
        - Specified retention period in days and/or years
        - Compliance mode. For the given retention time period (even for the root user), 
            - Object versions cannot be deleted
            - Object versions cannot be overwritten
            - Retention period cannot be adjusted
            - Retention mode cannot be changed
        - Governance mode. Same like Retention mode, but additionally can grant special permissions so that retention settings can be adjusted
            - Permission: s3:BypassGovernanceRetention
            - HTTP Header: x-amz-bypass-governance-retention: true
            - Use cases: Prevent accidental deletion, as a trial for compliance mode
    - Legal hold
        - Does not have a retention period at all
        - Simply set ON or OFF for legal hold in object version level. No delete or changes allowed when ON
        - Permission: s3PutObjectLegalHold
