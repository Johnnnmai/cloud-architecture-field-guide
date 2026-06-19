# My Vision of the Solutions Architect Role

Based on my experience as an Amazon AI/Robotics Lead PM, working alongside solutions architects who design and deliver cloud infrastructure at scale.

This is my personal vision of the role. To see how it compares with what companies actually look for, I analyzed 860+ job descriptions - the rest of this [role section](README.md) is based on that research.


## Core Responsibility

- Owning the architecture end-to-end: from business requirement to production deployment
- Working with engineering, security, and operations teams through every phase of design, build, and migrate
- Working with customers and stakeholders to understand real technical and business constraints
- Not "this service is trendy, let's use it" - starts from actual workload requirements with real data


## Beyond "Just Draw a Diagram"

Even for a seemingly simple task like migrating a web application to the cloud, professional solutions architecture requires:

1. Requirements gathering - business goals, compliance needs, performance targets, budget constraints
2. Current state assessment - existing infrastructure audit, dependency mapping, data flow analysis
3. Architecture design - service selection, network topology, security controls, disaster recovery strategy
4. Cost modeling - TCO analysis comparing on-premise vs cloud, reserved vs on-demand pricing, data transfer costs
5. Migration planning - phased approach, rollback procedures, downtime windows, data migration strategy
6. Proof of concept - validate critical assumptions before committing the full migration
7. Security review - IAM policies, encryption at rest and in transit, network segmentation, compliance mapping
8. Implementation guidance - IaC templates, deployment pipelines, monitoring and alerting setup
9. Performance testing - load testing, failover testing, latency benchmarks against SLA targets
10. Knowledge transfer - documentation, runbooks, training sessions for the operations team


## Progressive Complexity

- Simple case: single workload migration to the cloud with standard architecture patterns
- Multi-service architecture (~5x harder): add microservices orchestration, cross-region deployment, multi-account strategy, shared services, cost allocation
- Enterprise transformation (~10x harder): add multi-cloud strategy, organizational change management, compliance across jurisdictions, legacy system integration, executive alignment


## How It Compares to Other Roles

### vs Cloud Engineer

- Cloud Engineers implement and operate what SAs design
- SAs own the "what" and "why" of architecture decisions, Cloud Engineers own the "how" of implementation
- Overlap is significant - many SAs started as Cloud Engineers
- Cloud Engineers need to add: client communication, trade-off analysis, business requirement translation

### vs DevOps Engineer

- DevOps focuses on CI/CD pipelines, automation, and operational excellence
- SAs focus on architecture design, service selection, and cross-functional coordination
- Most effort in DevOps goes to deployment automation and monitoring, not greenfield architecture design
- DevOps Engineers need to add: architecture design patterns, presales skills, cost optimization at scale

### vs Platform Engineer

- Platform Engineers build internal developer platforms and tooling
- SAs design the underlying cloud infrastructure those platforms run on
- Overlap happens in IaC and Kubernetes - both work with infrastructure, but at different abstraction layers
- Platform Engineers need to add: client-facing skills, migration planning, multi-cloud architecture

### What Solutions Architects Don't Do

- Write production application code full-time
- Manage day-to-day infrastructure operations
- Own CI/CD pipeline maintenance
- Handle incident response and on-call rotations (typically)

### What Solutions Architects Focus On

- Architecture design and trade-off analysis
- Cloud service selection and integration patterns
- Migration strategy and execution planning
- Cost optimization and capacity planning
- Security architecture and compliance mapping


## In Bigger Organizations

- Architecture responsibilities often split between SAs, Cloud Engineers, DevOps, and Platform Engineers
- Cloud Engineers: infrastructure implementation, automation, day-to-day operations
- DevOps Engineers: CI/CD, deployment pipelines, monitoring, operational tooling
- Platform Engineers: internal developer experience, self-service infrastructure
- Eventually dedicated SAs own each workload domain (data, networking, security, application)
- Not every architecture problem needs an SA - some are pure infrastructure or platform problems
