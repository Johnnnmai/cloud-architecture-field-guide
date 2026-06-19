# Whiteboard Architecture Challenges

Based on candidate reports from Reddit, X, and personal blogs about what they were actually asked in solutions architect interviews.

This section covers live architecture design sessions: diagramming under pressure, trade-off analysis in real time, and communicating design thinking while drawing.


## Format

Typically 60-90 minutes. You receive a set of business requirements and must design a complete cloud architecture in real time on a whiteboard (in-person) or virtual drawing tool (remote). The interviewer plays the role of a customer or stakeholder, adding constraints as you design.

This is the round where most SA interviews are won or lost. It tests not just what you know, but how you think, how you communicate, and how you handle ambiguity.


## How to Approach Whiteboard Challenges

### Step 1: Clarify Requirements (5-10 minutes)

Before drawing anything, ask:

- What is the business problem? What user outcome are we optimizing for?
- What is the expected scale? Users, requests per second, data volume, growth rate.
- What are the availability and latency requirements? 99.9% vs 99.99%, sub-100ms vs sub-1s.
- What is the budget? This changes everything.
- What compliance requirements exist? HIPAA, PCI-DSS, SOC 2, GDPR.
- What is the team's current skill set? Kubernetes experience? Serverless comfort level?
- What is the timeline? Greenfield vs migration vs incremental improvement.
- Are there existing systems this needs to integrate with?

### Step 2: High-Level Design (10-15 minutes)

Draw the major components:

- User-facing entry points (CDN, load balancers, API gateways)
- Compute layer (containers, serverless, VMs)
- Data layer (databases, caches, queues, object storage)
- Networking boundaries (VPCs, subnets, availability zones, regions)
- External integrations

Explain each component choice as you draw. "I am choosing DynamoDB here because the access pattern is key-value with high throughput and the customer does not need complex joins."

### Step 3: Deep Dive on Critical Paths (15-20 minutes)

The interviewer will pick 2-3 areas to go deeper:

- Data flow: trace a request from the user to the database and back
- Failure scenarios: what happens when this component fails?
- Scaling: how does this handle 10x traffic?
- Security: how are you protecting data and controlling access?
- Cost: what does this architecture cost at the stated scale?

### Step 4: Trade-offs and Alternatives (5-10 minutes)

Proactively discuss what you considered and rejected:

- "I chose RDS over DynamoDB because the query patterns require joins, but the trade-off is that scaling reads requires manual read replicas"
- "A simpler approach would be X, but it would not meet the latency requirement at 10x scale"
- "If budget were the primary constraint, I would replace EKS with Fargate and accept slightly higher per-request costs for zero cluster management overhead"


## Whiteboard Challenge Examples

### Design a Global E-Commerce Platform

Requirements:
- 50K concurrent users, 5K orders per hour during peak
- Multi-region: NA, EU, APAC
- 99.99% availability for checkout flow
- PCI-DSS compliance for payment processing
- Product catalog with 2M SKUs and real-time inventory

Key design decisions to address:
- Global traffic routing (CloudFront + Route 53 or equivalent)
- Multi-region data consistency for inventory and orders
- Payment processing isolation for PCI-DSS scope reduction
- Search infrastructure for product catalog
- Caching strategy for product pages vs real-time inventory


### Design a Real-Time Data Analytics Platform

Requirements:
- Ingest 1M events per second from mobile SDKs
- Sub-10-second query latency for dashboards
- 90-day retention for hot data, 7-year retention for cold data
- Multi-tenant with tenant-level data isolation
- Budget: $50K/month

Key design decisions to address:
- Ingestion pipeline (Kinesis/Kafka, batching strategy)
- Hot vs cold storage tier separation
- Query engine selection for sub-10-second latency
- Tenant isolation (separate tables, row-level security, separate accounts)
- Cost management for high-volume ingestion and storage


### Migrate a Legacy Banking Application

Requirements:
- Monolithic .NET application on Windows Server 2012, 15 years old
- 2TB SQL Server database with 500 stored procedures
- 50 batch jobs running nightly
- Zero tolerance for data loss, 4-hour maximum downtime
- FFIEC and SOC 2 compliance

Key design decisions to address:
- Migration strategy (lift-and-shift first, then modernize, or re-architect directly?)
- Database migration approach for SQL Server with complex stored procedures
- Batch job modernization (Step Functions, Batch, or keep SSIS?)
- Compliance mapping and audit trail continuity
- Rollback strategy and data validation


### Design a Multi-Account AWS Strategy

Requirements:
- 500-person engineering organization, 40 application teams
- Need production, staging, development, and sandbox environments
- Centralized security tooling and cost management
- Team autonomy for development, guardrails for production
- Compliance: SOC 2, HIPAA for some workloads

Key design decisions to address:
- Account structure (per-team, per-environment, per-application?)
- Networking topology (Transit Gateway, centralized egress)
- IAM strategy (SSO, permission boundaries, SCPs)
- Security baseline (GuardDuty, Config, Security Hub deployment)
- Cost allocation and showback model


### Design an AI/ML Inference Platform

Requirements:
- Serve 3 large language models and 10 computer vision models
- 10K inference requests per second across all models
- P99 latency under 500ms for CV models, under 2s for LLMs
- Auto-scaling for variable traffic patterns
- GPU cost under $100K/month

Key design decisions to address:
- GPU instance selection (p4d, g5, inf2 / NCas v3 / A3 Mega)
- Model serving framework (SageMaker, TorchServe, Triton, vLLM)
- Auto-scaling strategy (GPU utilization, request queue depth, custom metrics)
- Model caching and batching for cost optimization
- Monitoring and observability for model performance
