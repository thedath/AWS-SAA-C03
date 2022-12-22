# AWS 3 different network zones

1. Public Internet Zone
2. AWS Private Netwok Zone (VPC)
3. AWS Public Network Zone (Ex: S3)

Note: Resources in AWS Private Zone are can be accessed via public internet if,
- there's a configured VPN
- a direction connection configured
- AWS Internet Gateway is setup & allowed to access (Using a IGW, resources in private zone can access other AWS resources in the AWS public zone not going through the public internet)
