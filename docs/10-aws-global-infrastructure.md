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
- Global resilient: Needs all the regions in the world to fail for a global failure.
- Region resilient: Needs all the availability zones in a region to fail for complete region to fail.
- AZ resilient: Needs all the hardware to fail for a AZ to fail.
