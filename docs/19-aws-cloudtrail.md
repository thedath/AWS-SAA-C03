# AWS Cloud Trail

- Is a regional service
- Trail can be set to one region or all region
- There are some AWS resources logs events globally (globally === North Virginia Region) Ex: IAM, CFD, STS
- It is not realtime
- Specifically logs API calls or account activities
- CloudTrail Event: Is an activity of AWS account, taken by an user, role or another AWS service
- Stores CloudTrails events for past 90 days by default
- Trails: If it is required the CT events to present more than 90 days
- 3 types of CT events
    - Management
        - AKA controlled plane operations, are management operations performed on AWS resources
        - Ex: Creating & terminating an EC2, Creating a VPC
        - By default only management events are being logged
    - Data: 
        - Resource based operations
        - Ex: Uploading a file to S3, Downloading a file from S3, Invoking a lambda function
        - Needs to explicitly enable
    - Insight:??
