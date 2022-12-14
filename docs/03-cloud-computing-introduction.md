
# Cloud Computing Introduction

### 5 Characteristics of the Cloud

1. **On-Demand Self Service:**
    - Ability to provision capabilities (storage, database, network, computing, security, etc.) for your product/service by user self as needed, "without requiring humen interation".
    - No need to visit vendor.
    - No need to contact support and get your requirement get done.
2. **Broad Network Access:**
    - Ability to use & manage capablities (storage, database, network, computing, security, etc.) over the "network" using "standard machanisams" like http, https, ssh, ftp, vpn, etc.
    - No need of a private link to access your resources.
    - No need to visit your vendor to access your resources.
3. **Resource Pooling:**
    - Resources/capabilities (database, storage, network bandwith) are pooled in large scale.
    - Serve multiple consumers in a multi tenant way, while allocating & disallocating resources according to their demand.
    - Eliminates the sense of actual location of physical hardware so that consumers don't have a control or knowladge on them.
    - Harware & their locations becomes virtual things to consumers.
    - Consumers won't be setting up hardware & maintaining them.
    - For consumers, capacity of the capabilities are limitless.
 4. **Rapid Elasticity:**
     - Provisioning of capabilities (database, storage, computing, networking) should get increased & decreased rapidly (elastically) based on the realtime demand of the resources.
     - To consumer ability to provision the capabilities should appear as unlimited.
4. **Measured Service:** Usage of the consumers' resources should be able to monitred, controlled, reported & billed. (Pay for what you consume)

### Types of Clouds
- **Public Cloud:** Should satisfy the 5 characteristics of the Cloud & available to general public (Ex: AWS, Azure, Google Cloud)
- **Private Cloud:** Should satisfy the 5 characteristics of the Cloud but only dedicated to consumer's business and runs "on premises"
- **Multi Cloud:** Cloud solution that utilizes multiple public clouds of different cloud vendors in one solution. (Ex: AWS + Azure)
- **Hybrid Cloud:** Cloud solution that utilize public cloud and private cloud togather. (Not public cloud + on premises resources)

### Cloud Service Modules (XAAS)
There is *infrastructure stacks* when we build an application/service. There are 5 different types of modules of infrastructure stacks.

1. On-Premises
    - [x] Application
    - [x] Data
    - [x] Runtime
    - [x] Container
    - [x] OS
    - [x] Virtualization
    - [x] Servers
    - [x] Infrastructure
    - [x] Facility
2. Data Center Hosted
    - Unit of Consumption: Facility
    - Available layers
	    - [x] Application
	    - [x] Data
	    - [x] Runtime
	    - [x] Container
	    - [x] OS
	    - [x] Virtualization
	    - [x] Servers
	    - [x] Infrastructure
	    - [ ] ~~Facility~~
 3. IAAS (Infrastructure as a Service)
    - Ex: AWS EC2
    - Unit of Consumption: Virtual Machine
    - Available layers
	    - [x] Application
	    - [x] Data
	    - [x] Runtime
	    - [x] Container
	    - [x] OS
	    - [x] Virtualization (Consumed)
	    - [ ] ~~Servers~~
	    - [ ] ~~Infrastructure~~
	    - [ ] ~~Facility~~
  4. PAAS (Platform as a Service)
     - Ex: Running python code on Cloud
     - Unit of Consumption: Runtime Environment
     - Available layers
	    - [x] Application
	    - [x] Data
	    - [x] Runtime (Consumed)
	    - [ ] ~~Container~~
	    - [ ] ~~OS~~
	    - [ ] ~~Virtualization~~
	    - [ ] ~~Servers~~
	    - [ ] ~~Infrastructure~~
	    - [ ] ~~Facility~~
  5. SAAS (Software as a Service)
     - Ex: Office 365, Figma, etc.
     - Unit of Consumption: Software
     - Available layers
	    - [x] Application (Consumed)
	    - [ ] ~~Data~~
	    - [ ] ~~Runtime~~
	    - [ ] ~~Container~~
	    - [ ] ~~OS~~
	    - [ ] ~~Virtualization~~
	    - [ ] ~~Servers~~
	    - [ ] ~~Infrastructure~~
	    - [ ] ~~Facility~~
