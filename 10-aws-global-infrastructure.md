# AWS Global Infrastructure

- Region:
    - Full deployment of all aws infrastructure (Storage, DB, Compute, AI, Analytics, etc.)
    - One region is 100% isolated from another region. This helps to archieve fault tolerant solutions.
    - Geopolitical seperation, to address influences of a particular political governence.
    - Location control - Can monitor performances of regions individualy, so that we can decide whcih region we should prioritize or even discard.
- Edge Locations:
    - Edge locations are distributed around the world more, compared to Regions. Mainly for contend delivery services (CDN).
- Availability Zones (AZ): 
    - Isolated infrastructure within a single AWS region.
    - Some services can be placed across AZs.


### Service Resilience
- Global resilient: Need a global outage to happen in order for a outage in a global AWS service (Ex: AWS IAM)
- 
