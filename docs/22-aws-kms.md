
# AWS Key Management Service (KMS)

- AWS Public Service
- Regional service
- Mainly two types
    - AWS Owned
    - Customer Owned
        - AWS Managed: Keys rotates by default, once per year, cannot change
        - Customer Managed
            - More customizable, can use to create policies to allow cross account access
            - Keys rotates by default, once per year, can be disabled
- Can access without permisions
- Keys never leaves KMS
- Provides FIPS 140-2 (L2)
- Parts of a Key
    - Id
    - Date
    - Policy
    - Description
    - State
- 4KB of data can be encrypted & decrypted
- Data Encryption Keys (DEK): 
