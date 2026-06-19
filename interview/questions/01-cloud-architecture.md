# Cloud Architecture Design Questions

Based on candidate reports from Reddit, X, and personal blogs about what they were actually asked in solutions architect interviews.

This section covers cloud-specific architecture questions: service selection, Well-Architected Framework, multi-cloud patterns, and cloud-native design.

## Format

Typically 45-90 minutes, collaborative. The interviewer presents a business scenario and you design an architecture on a whiteboard or virtual drawing tool. There is usually a back-and-forth discussion where the interviewer adds constraints (budget, compliance, scale) as you design.

Cloud architecture questions test your ability to select the right services for the right workload, justify those decisions with clear trade-offs, and demonstrate awareness of cost, security, and operational concerns.


## Interview Questions

Actual questions reported by candidates and interviewers, compiled from blog posts, practitioner guides, and interview experiences.

### Service Selection and Architecture Patterns

Understanding when to use specific cloud services and why, beyond just knowing what they do.

- A startup with $5K/month cloud budget needs a web application that handles 1K concurrent users with spiky traffic patterns. What architecture would you recommend and why?
- When would you choose DynamoDB over RDS for a transactional workload? Walk through the decision criteria including cost, consistency, and query patterns.
- A customer wants to run a batch processing pipeline that processes 10TB of data nightly. Compare and contrast EMR, Glue, and Step Functions + Lambda for this use case.
- Design a notification system that sends 50M push notifications per day. What services would you use and how would you handle failures and retries?
- When would you recommend ECS Fargate over EKS for containerized workloads? What factors drive this decision?
- A company runs a monolithic application on a single large EC2 instance. They want to modernize. Walk through the options from least to most effort and the trade-offs of each.
- How do you decide between API Gateway + Lambda versus ALB + ECS for a REST API? What are the cost and performance implications at different scales?

### Well-Architected Framework

How to apply the six pillars (operational excellence, security, reliability, performance efficiency, cost optimization, sustainability) in practice.

- You inherit an architecture that was designed quickly during a startup phase. How would you conduct a Well-Architected Review and what would you prioritize?
- A customer's architecture passes all six pillars but costs 3x what a simpler design would. How do you handle this trade-off conversation?
- Walk through how you would design for operational excellence in a multi-account AWS environment. What tools, processes, and automation would you put in place?
- How do the Well-Architected pillars conflict with each other? Give an example where optimizing for one pillar degrades another.
- A customer refuses to implement your Well-Architected recommendations because of timeline pressure. How do you document the risk and what is your escalation path?

### Multi-Cloud and Hybrid Architecture

Designing systems that span cloud providers or bridge on-premises and cloud environments.

- A financial services company requires workloads on both AWS and Azure for regulatory reasons. How would you design the networking and identity layer across both clouds?
- Design a hybrid architecture where sensitive data must remain on-premises but analytics workloads run in the cloud. How do you handle data movement and latency?
- A customer is considering a multi-cloud strategy "to avoid vendor lock-in." How would you evaluate whether this adds value or just complexity? What questions would you ask?
- How would you design DNS, load balancing, and certificate management for a service that runs across AWS and GCP?
- A company has workloads in Azure and wants to add an AI/ML pipeline on AWS (SageMaker). How do you design the data flow and networking between the two environments?


### Networking and Connectivity

VPC design, DNS, load balancing, connectivity, and traffic management.

- Design a VPC architecture for a company with 200 microservices, 5 environments (dev, staging, prod, DR, sandbox), and PCI-DSS requirements.
- How would you connect 10 VPCs across 3 regions with centralized egress and inspection? Walk through the trade-offs of Transit Gateway vs VPC peering.
- A customer reports intermittent latency spikes between their application tier and database tier in the same region. How would you diagnose and resolve this?
- Design a DNS architecture for a global application serving users in NA, EU, and APAC with latency-based routing and health checks.
- When would you use a Network Load Balancer vs an Application Load Balancer? What about Gateway Load Balancer for third-party appliances?


### Serverless Architecture

When serverless is the right pattern and when it is not.

- Design a serverless architecture for a document processing pipeline: upload PDF, extract text, classify content, store results, notify users.
- What are the limitations of Lambda that make it unsuitable for certain workloads? Give three specific examples with alternative approaches.
- A customer has a Lambda function that consistently times out at 15 minutes. How would you redesign the architecture?
- How would you design a serverless real-time WebSocket API for a chat application with 50K concurrent connections?
- Compare the cold start characteristics of Lambda, Azure Functions, and Cloud Run. How does this affect architecture decisions for latency-sensitive APIs?
