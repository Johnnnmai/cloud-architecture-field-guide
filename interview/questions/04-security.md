# Security and Compliance Questions

Based on candidate reports from Reddit, X, and personal blogs about what they were actually asked in solutions architect interviews.

This section covers cloud security architecture: IAM, encryption, network security, compliance frameworks, and zero trust.


## Format

Typically 45-60 minutes, scenario-based. Security questions can appear as a standalone round or woven into architecture design sessions. When embedded in design rounds, the interviewer expects you to proactively address security without being prompted - treating it as an afterthought is a red flag.


## Interview Questions

### Identity and Access Management

Designing IAM strategies that balance security with developer productivity.

- Design an IAM strategy for a 500-person engineering organization using AWS. How do you handle federation, role assumption, and least privilege at scale?
- A developer needs temporary access to a production database for debugging. Walk through how you would design and implement this without creating long-lived credentials.
- How would you implement cross-account access in a multi-account AWS environment? What are the security implications of different approaches (role chaining, resource policies, AWS RAM)?
- Design an identity architecture for a SaaS application where customers bring their own identity provider (SAML, OIDC). How do you handle tenant isolation?
- A security audit reveals that 40% of IAM policies in the account have wildcard (*) permissions. How would you systematically remediate this without breaking applications?
- How do you implement service-to-service authentication in a microservices architecture? Compare IAM roles, mTLS, OAuth2, and API keys.

### Encryption and Data Protection

Protecting data at rest, in transit, and in use across cloud environments.

- Design an encryption strategy for a healthcare platform that stores PHI. Cover data at rest, in transit, key management, and key rotation.
- When would you use KMS customer-managed keys vs AWS-managed keys vs customer-provided keys (SSE-C)? What are the operational trade-offs?
- A customer needs to encrypt all data at rest across 50 AWS accounts. How would you implement and enforce this at scale?
- Design a secrets management architecture using HashiCorp Vault or AWS Secrets Manager. How do you handle secret rotation for database credentials used by 100 microservices?
- How would you implement envelope encryption for a file storage system? Walk through the key hierarchy and rotation strategy.
- A customer wants to process sensitive data in the cloud without the cloud provider being able to read it. What options exist and what are their limitations?

### Network Security

Designing secure network architectures with defense in depth.

- Design a network security architecture for a three-tier web application: public-facing ALB, private application tier, private database tier. Include security groups, NACLs, and WAF.
- How would you implement network segmentation for a multi-tenant SaaS platform? What are the options and trade-offs between VPC-level, subnet-level, and security-group-level isolation?
- Design a zero trust network architecture for a company migrating from a traditional perimeter-based model. What are the key components and implementation phases?
- A customer wants to inspect all egress traffic from their VPC for data exfiltration prevention. Design the architecture including third-party NGFW integration.
- How do you secure east-west traffic between microservices? Compare security groups, service mesh (Istio/Linkerd), and VPC endpoint policies.
- Design a secure connectivity architecture for a company with 20 branch offices connecting to AWS resources. Include VPN, Direct Connect, and SD-WAN considerations.

### Compliance and Governance

Mapping regulatory requirements to technical controls and automating compliance.

- A healthcare company needs to achieve HIPAA compliance on AWS. Walk through the key architectural controls, BAA requirements, and audit trail design.
- How would you design an architecture that meets PCI-DSS requirements for a payment processing system? Cover network segmentation, encryption, access controls, and logging.
- Design an automated compliance monitoring system that continuously verifies security controls against SOC 2 requirements. What tools would you use?
- A customer operates in both the US and EU. How do you design a data architecture that complies with both GDPR and US regulatory requirements?
- How would you implement a centralized logging and audit trail architecture across 50 AWS accounts that meets regulatory retention requirements?
- A FedRAMP High assessment is required for a government customer. What are the key architectural differences between commercial and GovCloud deployments?

### Incident Response and Security Operations

Designing systems that detect, respond to, and recover from security incidents.

- Design a security monitoring architecture that detects and responds to compromised IAM credentials within 15 minutes.
- A customer discovers unauthorized access to an S3 bucket containing customer PII. Walk through the incident response process from detection to remediation to customer notification.
- How would you design automated remediation for common security misconfigurations (public S3 buckets, open security groups, unencrypted volumes)?
- Design a threat detection architecture using GuardDuty, Security Hub, and custom detection rules. How do you handle alert fatigue?
- A customer wants to implement a security data lake for long-term analysis. Design the architecture for collecting, normalizing, and analyzing security events across cloud and on-premises environments.
