# Learning Path for Solutions Architects

What to learn and in what order, based on skill demand from 860+ SA job descriptions and real hiring data across cloud providers, consulting firms, and enterprise companies.

For a structured deep-dive with 200+ real interview examples, check out [The 0→1 Solutions Architect Interview Playbook](https://valenx.org/books/sa).


## Core Skills

The most important 20% that accounts for 80% of the work. Based on hiring manager interviews, SA community surveys, and [job market research](../role/02-skills.md).

### Cloud Architecture Fundamentals

- How cloud platforms work - compute, storage, networking, identity at the infrastructure level
- Architecture patterns - multi-tier, microservices, serverless, event-driven, data lake
- Well-Architected Framework - the six pillars and how to apply them in practice
- Service selection - knowing when to use which service and why

### System Design

- High availability and disaster recovery - multi-AZ, multi-region, failover, replication
- Scalability patterns - horizontal scaling, caching, sharding, load balancing
- Distributed systems fundamentals - consistency models, CAP theorem, consensus
- Database design - relational vs NoSQL, when to use each, schema design

Practice projects: design a multi-region web application, build a data pipeline on a cloud platform, create a disaster recovery architecture

### Infrastructure as Code

- Terraform or CloudFormation - declarative infrastructure definition
- Module patterns - reusable, composable infrastructure components
- State management - remote state, locking, import existing resources
- CI/CD for infrastructure - GitOps workflows, automated validation

Practice projects: define a VPC with subnets and security groups in Terraform, build a reusable ECS/EKS module, create a complete environment with Terraform

### Security Architecture

- IAM design - least privilege, role-based access, federation, service accounts
- Network security - VPC design, segmentation, WAF, DDoS protection
- Encryption - KMS, key rotation, envelope encryption, TLS configuration
- Compliance frameworks - SOC 2, HIPAA, PCI-DSS, GDPR requirements

### Client Communication

- Technical presentations - explaining architectures to mixed technical and business audiences
- Architecture workshops - facilitating discovery sessions, requirements gathering
- Whiteboard design - communicating design thinking while diagramming
- Written documentation - architecture decision records, design documents, runbooks

### Migration and Modernization

- Assessment methodologies - application portfolio analysis, migration readiness
- Migration strategies - the 7 Rs, when to use each approach
- Data migration - database migration patterns, validation, cutover planning
- Modernization patterns - strangler fig, decomposition strategies


## Other Skills

Based on the [job market research](../role/02-skills.md). These are not covered in the core path above but frequently appear in job descriptions.

### Cost Optimization and FinOps

- Right-sizing and reserved capacity planning
- Cost allocation and tagging strategy
- FinOps practices - showback, chargeback, budgets, anomaly detection
- TCO analysis for migration business cases

### Networking

- VPC design and CIDR planning
- DNS architecture - Route 53, private hosted zones, hybrid DNS
- Load balancing - ALB, NLB, Global Accelerator
- Connectivity - Direct Connect, VPN, Transit Gateway, peering

### Containers and Orchestration

- Docker fundamentals - building, optimizing, securing container images
- Kubernetes - deployments, services, networking, storage, RBAC
- Managed services - EKS, AKS, GKE differences and trade-offs
- Service mesh - when it is justified, what it solves

### Monitoring and Observability

- CloudWatch, Azure Monitor, Cloud Monitoring
- Distributed tracing - X-Ray, Jaeger, OpenTelemetry
- Custom metrics and alerting strategies
- SRE practices - SLIs, SLOs, error budgets


## Role-Specific Guides

Already have experience in another field? Start from where you are:

- [From Software Engineer](from-software-engineer.md) - application architecture is your edge, 3-4 months
- [From DevOps Engineer](from-devops.md) - infrastructure automation is your superpower, 2-3 months
- [From Network Engineer](from-network-engineer.md) - connectivity and security are your foundation, 3-5 months
- [From Consultant](from-consultant.md) - structured thinking and client management, 2-3 months
- [From Systems Administrator](from-sysadmin.md) - server management and reliability, 3-4 months


## The Typical SA Tool Stack

- Cloud platforms - AWS Console/CLI, Azure Portal/CLI, GCP Console/CLI
- Infrastructure as Code - Terraform, CloudFormation, Pulumi, Bicep
- Containers - Docker, Kubernetes, Helm
- Diagramming - Lucidchart, draw.io, Miro, Excalidraw
- Monitoring - CloudWatch, Datadog, Grafana, Prometheus
- Security - Prowler, ScoutSuite, tfsec, Checkov
- CI/CD - GitHub Actions, GitLab CI, Jenkins, CodePipeline
- Documentation - Confluence, Notion, Architecture Decision Records


## Skills by Priority

### Must have

- At least one cloud platform at depth (AWS, Azure, or GCP)
- System design and architecture patterns
- Infrastructure as Code (Terraform preferred)
- Security fundamentals (IAM, encryption, network security)
- Technical communication and whiteboarding

### High value

- Second cloud platform familiarity
- Kubernetes and container orchestration
- Migration and modernization experience
- Cost optimization and FinOps
- Networking depth (DNS, load balancing, connectivity)
- Compliance frameworks (SOC 2, HIPAA, PCI-DSS)

### Differentiators

- Cloud provider certifications (AWS SA Professional, Azure Expert)
- Deep domain expertise (financial services, healthcare, government)
- AI/ML infrastructure design
- Multi-cloud architecture patterns
- Industry speaking and thought leadership
