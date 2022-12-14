# Elastic Compute Cloud (EC2) - Part 1

- Is a vertual machine runs on AWS insfrastructure
- Is a IAAS from AWS
- Unit of consumption is 'instance'
- Is a private AWS service, which means runs on AWS private zone
- A VPC is required and by default it is assigned to use a single VPC
- Since it is a private service, needs to configure specifically during the EC2 configurations to allow it for public access
- Since VPC has subnets accross AZs and EC2 gets assigned an IP from AZ subnets, EC2s are also AZ resilient AWS services
- Can configure the resources such as compute, memory & storage of an EC2 in its' configurations
- Has two types of storages
    - Local host storage
    - Elastic Block Store
- On-demand billing, calculated per second

### EC2 statuses

- Running
    - CPU - Billed
    - Memory - Billed
    - Storage - Billed
    - Network - Billed
- Stopped
    - CPU - Not Billed
    - Memory - Not Billed
    - **Storage - Billed**
    - Network - Not Billed
- Terminated (All the resources will be erased/terminated)
    - CPU - Not Billed
    - Memory - Not Billed
    - Storage - Not Billed
    - Network - Not Billed

### Amazone Machine Image (AMI)

- Is a image of an EC2 Instance
- Can start a instance using an AMI
- Can take a AMI of an running instance
- Properties of an AMI
    - Permissions
        - Public: Everyone allowed to create instances from this AMI
        - Owner: Only owner of this AMI's account can create instances from this AMI (Implicitly allowed)
        - Explicit: Only specified AWS accounts allowed to create instances from this AMI
    - Root volume: Volume for boot loader to exist
    - Block device mapping: Mapping of other volumes included

*** Notes
- *Connecting to an EC2 instance running on Windows OS using RDP: Port number 3389*
- *Connecting to an EC2 isntance running on Linux OS using Putty: Port number 22*

