
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
- Backing keys: Old keys from rotation
- Key material origin: Simply, where the keys is being created and stored securely
- Can create Aliases for keys (regional)
- Can access without permisions
- Keys never leaves KMS
- Provides FIPS 140-2 (L2)
- Parts of a Key
    - Id
    - Date
    - Policy
    - Description
    - State
- Data Encryption Keys (DEK)
    - 4KB of data can be encrypted & decrypted
- Key Policy: Needs to create a policy for a Key to be accessed by an identity, event the identity resides within the same account of the Key
