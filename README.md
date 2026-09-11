AWS SAML Federation with Keycloak
Architecture
User → Keycloak (IdP)
          ↓ SAML Assertion
     AWS IAM SAML Provider
          ↓
     IAM Role
          ↓
   STS Temporary Credentials
          ↓
      AWS Console
Key Configuration
Keycloak Realm: natwest-lab
SAML Client: AWS SAML Lab
AWS Provider: NatWestLabIdP
IAM Role: NatWest-SAML-ReadOnly
SAML Binding: HTTP-POST
Signature: RSA-SHA256
NameID: Email
AWS SAML Attributes
https://aws.amazon.com/SAML/Attributes/Role
→ ROLE ARN, SAML PROVIDER ARN

https://aws.amazon.com/SAML/Attributes/RoleSessionName
→ username
Key Concepts
SAML = enterprise federation
Keycloak = IdP
AWS = Service Provider
IAM Role = authorization
STS = temporary credentials
Trust Policy = controls who can assume the role
Permission Policy = controls what the role can access
Troubleshooting
Login failure → Check IdP
SAML failure → Check assertion/signature
AssumeRole failure → Check trust policy
AccessDenied → Check IAM/SCP/resource policy

Lab result: Successfully generated and validated an AWS-compatible SAML assertion with the required Role and RoleSessionName attributes.
└──────────────────────────────────────┘
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/140fb748-fe52-4ccc-b914-f060b315acd4" />

<img width="1776" height="653" alt="image" src="https://github.com/user-attachments/assets/4b6a5815-dd15-473d-9492-cd3bede6b12e" />
