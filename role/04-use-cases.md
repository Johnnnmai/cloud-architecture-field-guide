# Architecture Scenarios Analysis

Based on 2,800+ extracted architecture scenarios from 860+ job descriptions.

Methodology note: I collected all architecture scenarios into a single file and used AI (Claude) to analyze and categorize them. This is not a quantitative analysis like the [skills analysis](02-skills.md) - it is based on the questions I asked and the patterns Claude identified in the data. It may be less precise, but I believe it is still representative of what is happening in the market.

## Summary

The architecture scenarios reveal what companies are actually designing and deploying today. This is the real-world landscape that Solutions Architects work on daily.

Total architecture scenarios extracted: 2,800+

- Customer-Facing roles: 1,568 scenarios (56.0%)
- Internal SA roles: 1,092 scenarios (39.0%)
- Specialist SA roles: 140 scenarios (5.0%)


## Problems Architectures Solve Today

Organized by the business problem, not the technology.


### Migrating Legacy Workloads to the Cloud

812 mentions (29.0%)

Problem: Organizations have decades of on-premises infrastructure - mainframes, physical servers, proprietary databases. Moving to the cloud is high-risk, high-reward, and most teams have never done it before.

Architecture Solution: Phased migration strategies with clear assessment criteria, risk mitigation, and rollback procedures.

Concrete examples:

- Assess 200+ applications for cloud readiness and categorize by migration strategy (rehost, replatform, refactor, retire)
- Design a database migration from Oracle on-premises to Aurora PostgreSQL with zero downtime using DMS and blue-green deployment
- Create a hybrid connectivity architecture using Direct Connect/ExpressRoute with failover to VPN
- Migrate a monolithic .NET application to containerized microservices on EKS/AKS
- Build a phased migration plan for a 50-server data center with dependency mapping and cutover scheduling
- Design a data lake migration from Hadoop on-premises to S3/EMR with data validation pipelines


### Designing for High Availability and Disaster Recovery

476 mentions (17.0%)

Problem: Downtime costs money. Companies need architectures that survive regional outages, hardware failures, and configuration errors without manual intervention.

Architecture Solution: Multi-AZ and multi-region architectures with automated failover, data replication, and recovery testing.

Concrete examples:

- Design a multi-region active-active architecture for a payment processing system with RPO under 1 second
- Architect a disaster recovery strategy with pilot light in a secondary region and automated failover
- Build a global load balancing solution using CloudFront/Front Door with health-check-based routing
- Design database replication across regions for a financial services application with consistency guarantees
- Create runbooks and automated recovery procedures for common failure scenarios
- Implement chaos engineering practices to validate DR readiness


### Optimizing Cloud Costs at Scale

392 mentions (14.0%)

Problem: Cloud bills grow 30-40% year over year at most organizations. Teams overprovision because they fear downtime. Finance wants visibility and accountability.

Architecture Solution: Cost-aware architecture design with right-sizing, commitment-based pricing, and automated cost governance.

Concrete examples:

- Conduct an architecture review that identified $2.4M in annual savings through right-sizing and reserved instances
- Design a spot instance strategy for batch processing workloads with automatic fallback to on-demand
- Implement a cost allocation tagging strategy across 50+ AWS accounts with automated compliance checking
- Architect a serverless-first approach for variable workloads that reduced compute costs by 60%
- Build a FinOps dashboard integrating Cost Explorer, Budgets, and custom anomaly detection
- Design a data lifecycle policy that moved cold data to Glacier/Archive tier, saving $180K annually


### Securing Cloud Environments

364 mentions (13.0%)

Problem: Cloud environments expand the attack surface. Misconfigured IAM policies, open security groups, and unencrypted data stores are the top causes of cloud breaches.

Architecture Solution: Security-by-design architectures with defense in depth, least privilege access, and continuous compliance monitoring.

Concrete examples:

- Design a multi-account AWS strategy with Organizations, SCPs, and centralized security tooling
- Architect a zero trust network with identity-based access, microsegmentation, and encrypted east-west traffic
- Build a secrets management architecture using Vault/Secrets Manager with automatic rotation
- Design a compliance architecture mapping HIPAA controls to AWS services with automated audit evidence collection
- Implement a cloud security posture management (CSPM) solution with automated remediation
- Create an incident response architecture with automated containment and forensic data preservation


### Building Data Platforms and Analytics

280 mentions (10.0%)

Problem: Organizations have data scattered across systems - databases, SaaS applications, log files, IoT devices. They need a unified platform to ingest, transform, store, and analyze data at scale.

Architecture Solution: Modern data platform architectures that separate compute from storage, support multiple analytics workloads, and scale independently.

Concrete examples:

- Design a data lake architecture on S3/ADLS with Delta Lake/Iceberg for ACID transactions
- Architect a real-time streaming pipeline using Kinesis/Event Hubs for IoT sensor data at 1M events/second
- Build a data mesh architecture with domain-owned data products and a federated governance model
- Design a modern data warehouse on Redshift/Synapse/BigQuery with dimensional modeling
- Create an ML feature store architecture for real-time and batch feature serving
- Implement data quality and observability across the data pipeline with automated alerting
