# Solutions Architect Responsibilities Analysis

Based on 3,200+ responsibilities extracted from 860+ job descriptions.

Methodology note: I collected all responsibilities into a single file and used AI (Claude) to analyze and categorize them. This is not a quantitative analysis like the [skills analysis](02-skills.md) - it is based on the questions I asked and the patterns Claude identified in the data. It may be less precise, but I believe it is still representative of what is happening in the market.


## Frequency Guide

| Category | Description |
|----------|-------------|
| Very common | Core responsibility - majority of roles |
| Common | Standard responsibility - many roles |
| Uncommon | Secondary responsibility - some roles |
| Rare | Occasional responsibility - few roles |


## Typical Job Titles

Solutions Architects work under various titles. The job title alone does not reliably indicate whether the role is Customer-Facing, Internal, or Specialist.

Customer-Facing titles (working with external clients):

- Solutions Architect - Most common
- Senior Solutions Architect
- Principal Solutions Architect
- Cloud Solutions Architect
- Enterprise Solutions Architect
- Customer Solutions Architect
- Presales Solutions Architect

Internal titles (working with internal engineering teams):

- Technical Architect
- Enterprise Architect
- Staff Solutions Architect
- Architecture Lead
- Platform Architect

Specialist titles (deep domain expertise):

- Security Solutions Architect
- Data Solutions Architect
- Network Architect
- AI/ML Solutions Architect
- Integration Architect


## Problems Solutions Architects Solve

Organized by the problem they address, not the methodology. Ordered by frequency.


## Very Common

### Designing Cloud Architectures

Problem: Organizations need scalable, secure, and cost-effective cloud architectures that meet their business requirements and technical constraints.

What Solutions Architects do:

- Design end-to-end cloud architectures aligned with business objectives and technical requirements
- Select appropriate cloud services based on workload characteristics, cost, and operational needs
- Create reference architectures, architecture decision records, and design documentation
- Evaluate trade-offs between performance, cost, security, and operational complexity
- Design for high availability, disaster recovery, and fault tolerance
- Review and approve architecture proposals from engineering teams

Sub-patterns:

- Greenfield Design - new workloads designed cloud-native from the start
- Modernization - re-architecting existing systems to leverage cloud services
- Hybrid Architecture - designing systems that span on-premises and cloud environments
- Multi-Cloud - architectures that use services from multiple cloud providers

Core challenge: Translating ambiguous business requirements into concrete, implementable cloud architectures that balance cost, performance, security, and operational simplicity.


### Driving Cloud Migration

Problem: Organizations have existing on-premises or legacy infrastructure that needs to move to the cloud. Migration is complex, risky, and requires careful planning to avoid downtime and data loss.

What Solutions Architects do:

- Assess current infrastructure and application portfolios for cloud readiness
- Develop migration strategies (lift-and-shift, re-platform, re-architect, retire, retain)
- Create migration plans with phased timelines, risk mitigation, and rollback procedures
- Design data migration pipelines for databases, file systems, and streaming data
- Lead migration execution, coordinating across engineering, security, and operations teams
- Validate post-migration performance, security, and cost against targets

Core challenge: Moving production workloads without disrupting business operations while meeting compliance, performance, and cost objectives.


## Common

### Customer Engagement and Presales

Problem: Sales teams need technical credibility to close deals. Customers need architectural guidance before committing to a platform or solution.

What Solutions Architects do:

- Lead technical discovery sessions to understand customer requirements
- Design solution architectures for presales proposals and RFP responses
- Build and demonstrate proof of concepts that validate architectural decisions
- Present technical solutions to C-level executives and technical decision-makers
- Serve as a trusted technical advisor throughout the customer lifecycle
- Contribute to technical content (whitepapers, blog posts, case studies)

Core challenge: Balancing technical accuracy with business value communication to help customers make informed platform and architecture decisions.


### Cost Optimization and FinOps

Problem: Cloud costs grow unpredictably. Organizations overprovision, use expensive services when cheaper alternatives exist, and lack visibility into where money goes.

What Solutions Architects do:

- Conduct architecture reviews focused on cost efficiency
- Recommend right-sizing, reserved instances, savings plans, and spot instances
- Design cost-aware architectures that optimize for TCO, not just performance
- Implement cost allocation tagging and showback/chargeback models
- Create cost forecasting models for capacity planning
- Identify and eliminate idle resources, orphaned storage, and over-provisioned compute

Core challenge: Reducing cloud spend without sacrificing reliability, performance, or security.


### Security Architecture and Compliance

Problem: Cloud environments introduce new attack surfaces and compliance requirements. Organizations need architectures that are secure by design, not bolted on after deployment.

What Solutions Architects do:

- Design IAM strategies (least privilege, role-based access, federation)
- Architect network security (VPC design, segmentation, firewall rules, WAF)
- Define encryption strategies for data at rest and in transit
- Map compliance requirements (SOC 2, HIPAA, PCI-DSS, FedRAMP) to technical controls
- Conduct architecture security reviews and threat modeling
- Design zero trust network architectures

Core challenge: Building security into every layer of the architecture without creating friction for development teams or impacting application performance.


## Uncommon

### Architecture Governance and Standards

Problem: Without governance, engineering teams make inconsistent architecture decisions. Technical debt accumulates, and integration becomes increasingly difficult.

What Solutions Architects do:

- Define and maintain architecture standards, patterns, and anti-patterns
- Run architecture review boards and design approval processes
- Create and curate reference architectures and reusable templates
- Establish technology radar (adopt, trial, assess, hold) for the organization
- Mentor engineers on architecture best practices
- Track and reduce architectural technical debt

Core challenge: Setting standards that improve consistency and quality without slowing down engineering velocity.


### Technical Enablement and Training

Problem: Engineering teams need to adopt new cloud services and architecture patterns. Without structured enablement, adoption is slow and teams make avoidable mistakes.

What Solutions Architects do:

- Create training materials, workshops, and hands-on labs
- Run architecture office hours for engineering teams
- Develop self-service architecture blueprints and quick-start templates
- Mentor junior architects and cloud engineers
- Document lessons learned from previous projects

Core challenge: Scaling architecture knowledge across the organization without becoming a bottleneck.
