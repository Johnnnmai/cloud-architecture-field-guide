# System Design at Scale Questions

Based on candidate reports from Reddit, X, and personal blogs about what they were actually asked in solutions architect interviews.

This section covers distributed systems design: high availability, scalability, caching, database design, and performance optimization.


## Format

Typically 60-90 minutes. You receive a set of requirements and design a complete system architecture. The interviewer adds constraints incrementally - first you design for the base case, then they add scale, then compliance, then cost targets.

System design questions test your ability to think in layers (compute, storage, networking, security, monitoring), reason about trade-offs at each layer, and communicate your thinking clearly while designing.


## Interview Questions

### High Availability and Disaster Recovery

Designing systems that survive failures at every level - instance, AZ, region, and provider.

- Design a multi-region active-active architecture for a payment processing system. RPO must be under 1 second and RTO under 5 minutes.
- How would you design a system that automatically fails over from one region to another without human intervention? What are the data consistency implications?
- A customer has a single-region deployment and wants to add disaster recovery. Walk through the options from pilot light to warm standby to active-active and the cost/complexity trade-offs of each.
- Design a database architecture that provides strong consistency within a region and eventual consistency across regions. What guarantees can and cannot be made?
- How do you test disaster recovery without disrupting production? Design a DR testing strategy that validates failover quarterly.
- A system has a 99.99% availability SLA. How does this translate to architecture decisions? What changes between 99.9% and 99.99%?

### Scalability and Performance

Designing systems that handle growth gracefully without proportional cost increases.

- Design an image processing pipeline that handles 100K uploads per hour during peak and 5K during off-peak. Optimize for both performance and cost.
- A customer's API gateway is hitting rate limits at 10K RPS. How would you redesign the architecture to handle 100K RPS?
- Design a caching strategy for an e-commerce platform with 10M products, personalized recommendations, and a 95th percentile latency target of 200ms.
- How would you design auto-scaling for a workload with unpredictable traffic patterns? What metrics would you use for scaling decisions beyond CPU and memory?
- A customer's database is the bottleneck at 50K reads per second. Walk through the options: read replicas, caching, sharding, database change. What questions would you ask first?
- Design a content delivery architecture for a video streaming platform serving 1M concurrent viewers across 20 countries.

### Data Architecture

Database selection, data modeling, and data pipeline design for different workload types.

- When would you choose a NoSQL database over a relational database? Walk through three specific use cases with justification.
- Design a data architecture for a multi-tenant SaaS application. How do you handle tenant isolation, performance, and cost allocation?
- A customer needs to process 1M events per second from IoT devices. Design the ingestion, processing, and storage architecture.
- How would you design a data migration from a 5TB Oracle database to PostgreSQL on RDS with near-zero downtime? Walk through the steps, tools, and validation approach.
- Design a data lake architecture that supports both batch analytics (BI dashboards) and real-time analytics (operational dashboards) from the same data source.
- When would you use a message queue (SQS/RabbitMQ) vs an event stream (Kinesis/Kafka) vs a pub/sub system (SNS/Pub/Sub)? What are the durability, ordering, and scaling trade-offs?

### Microservices and Distributed Systems

Decomposition, communication patterns, and operational complexity of distributed architectures.

- A monolithic application is being decomposed into microservices. How do you decide service boundaries? What data consistency patterns would you use across services?
- Design a service mesh architecture for 200 microservices. When is a service mesh justified vs simpler alternatives like API Gateway?
- How do you handle distributed transactions across microservices? Walk through the saga pattern with a concrete example.
- A customer experiences cascading failures when one microservice goes down. Design a resilience strategy with circuit breakers, bulkheads, and graceful degradation.
- Design an API versioning and deprecation strategy for a platform with 500 external API consumers.
- How do you implement observability across 200 microservices? Design the logging, metrics, and tracing architecture.

### Cost Optimization in System Design

Designing for cost efficiency from the start, not as an afterthought.

- A customer is spending $500K/month on AWS. You need to reduce this by 30% without impacting reliability. Walk through your approach.
- Design a compute strategy for a workload that is 60% steady-state and 40% burst. Compare reserved instances, savings plans, spot instances, and serverless.
- How would you design a storage architecture that automatically moves data between tiers based on access patterns? What are the cost and performance trade-offs?
- A customer runs 200 EC2 instances 24/7 for a workload that only has traffic 12 hours per day. Design an architecture that reduces compute costs by 50%+ without affecting availability during business hours.
- Design a cost allocation and showback model for a multi-team engineering organization using a shared AWS account.
