# Virtual Private Nerwork (VPC)

- Is a vertual network inside AWS
- VPCs are regional resources, meaning VPCs are configured regionally
- A VPC is withing a 1 account & 1 region
- IMPORTANT: There's one & only one default VPC per region
- Custom VPC: VPC that user create, has much more flexibility over pre defined default VPC of a particular region
- VPCs cannot comunicate with other VPCs or other AWS resources by default, unless configured otherwise

### Default VPC
- One per every region.
- Always has the same structure.
- Alwasy has the same VPC CIDR range which is **172.31.0.0/16**.
- By default, every AZ under that region is given a subnet based on the CIDR range of the default VPC.
- Includes a Internet Gateway (IGW), Security Group (SG) & NACL.
- Every resource configured under the default VPC is given a public IPv4 (Only for default VPC).
