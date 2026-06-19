# Migration and Modernization Questions

Based on candidate reports from Reddit, X, and personal blogs about what they were actually asked in solutions architect interviews.

This section covers cloud migration strategy, application modernization, hybrid cloud, and data migration.


## Format

Typically 45-60 minutes, scenario-based. You receive a description of a customer's existing environment and are asked to design a migration strategy. Interviewers test your ability to assess workloads, select the right migration approach, plan for risks, and handle the human side of organizational change.

Migration questions are among the most common in SA interviews because most enterprise workloads are still on-premises or in early cloud adoption stages.


## Interview Questions

### Migration Strategy and Assessment

Deciding what to migrate, in what order, and using which approach.

- A company has 300 servers running a mix of Windows and Linux workloads. How would you assess which workloads to migrate first and which migration strategy to use for each?
- Walk through the 7 Rs of migration (rehost, replatform, refactor, repurchase, retire, retain, relocate). For each, give a concrete example of when it is the right choice.
- A CTO wants to migrate everything to the cloud in 6 months. The engineering team says it will take 2 years. How do you help them find the right scope and timeline?
- How do you build a business case for cloud migration? What metrics and data points would you include to justify the investment to a CFO?
- A customer has a mainframe running COBOL applications that process 50M transactions per day. What are the realistic options for modernization? What are the risks of each?
- Describe how you would conduct an application dependency mapping exercise for a data center with 500 servers. What tools would you use and what are you looking for?

### Application Modernization

Transforming legacy applications to leverage cloud-native capabilities.

- A customer has a monolithic Java application deployed on WebLogic. They want to containerize it. Walk through the steps from assessment to production deployment on EKS/AKS.
- When does it make sense to re-architect an application vs simply lifting and shifting it? What criteria drive this decision?
- Design a strangler fig pattern migration for a legacy e-commerce platform. How do you route traffic between the old and new systems during the transition?
- A customer wants to move from a self-managed PostgreSQL cluster to a managed database service. What are the risks and how do you mitigate them?
- How would you modernize a batch processing system that runs nightly ETL jobs on a dedicated server? Walk through the options from Lambda to Step Functions to EMR.
- A customer has 50 microservices, each with its own database. They want to migrate from on-premises Kubernetes to EKS. What are the non-obvious challenges?

### Data Migration

Moving databases, file systems, and data pipelines to the cloud.

- Design a data migration strategy for a 20TB Oracle database to Aurora PostgreSQL. The application cannot have more than 2 hours of downtime.
- How would you migrate a 500TB data warehouse from on-premises to Redshift/BigQuery? What are the options for initial load and ongoing sync?
- A customer has 1PB of data on NFS file servers. How would you migrate this to S3/EFS? What tools would you use and how would you validate data integrity?
- Design a real-time data replication pipeline from an on-premises SQL Server to DynamoDB. The schemas are different. How do you handle the transformation?
- What are the most common causes of data migration failure? How do you prevent each one?
- How do you handle schema differences, character encoding issues, and stored procedure migration when moving from Oracle to PostgreSQL?

### Hybrid Cloud Architecture

Designing systems that span on-premises and cloud environments.

- A healthcare company must keep patient data on-premises but wants to run analytics in the cloud. Design the architecture including connectivity, data movement, and security.
- How would you design a hybrid identity solution where users authenticate against on-premises Active Directory but access cloud resources?
- A customer has latency-sensitive manufacturing systems that must stay on-premises. Design a hybrid architecture where the cloud provides analytics, reporting, and disaster recovery.
- Walk through the trade-offs of AWS Outposts, Azure Stack, and Google Anthos for extending cloud services on-premises.
- Design a hybrid networking architecture using Direct Connect/ExpressRoute with VPN failover. How do you handle DNS resolution across environments?
- A customer wants to use the cloud for development and testing but keep production on-premises. How do you design for environment consistency?

### Organizational and Human Factors

The non-technical side of migration that often determines success or failure.

- A customer's engineering team is resistant to cloud migration because they fear job loss. How do you handle this?
- How do you structure a cloud migration program across 10 application teams with different skill levels and priorities?
- What is a Cloud Center of Excellence (CCoE) and how does it accelerate migration? What pitfalls should you avoid when setting one up?
- A migration is 60% complete when a new CTO joins and questions the entire cloud strategy. How do you handle this?
- How do you measure migration success? What metrics beyond "number of workloads migrated" actually matter?
