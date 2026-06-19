# Getting Hired

Based on 65+ sources: candidate stories, hiring manager observations, career blogs, and interview guides. These are patterns from what candidates and hiring managers actually report.


## What Interviewers Test

What job postings list (baseline everyone claims):

- AWS/Azure/GCP certifications, Terraform, Kubernetes
- "Experience designing scalable cloud architectures"
- "Familiarity with microservices and serverless patterns"
- Generic "strong communication skills"

What interviewers actually test and value:

- Architecture trade-off reasoning over service name-dropping. "An unsuccessful architecture almost always has the same root cause: the architect optimized for one dimension (performance, cost, simplicity) without explicitly evaluating what they gave up." Every design should articulate what was considered and rejected, with clear rationale.
- Cost and scale reasoning. TCO analysis, data transfer costs, reserved vs on-demand pricing, resource right-sizing. "Design a system for 10K RPS" requires not just the architecture diagram but the cost estimate and the scaling strategy when traffic doubles.
- Customer engagement skills. Not "what is S3?" but "a customer insists on running everything on EC2 instances because that is what they know. How do you guide them toward a better architecture without alienating them?" Empathy and influence matter more than raw technical depth.
- Security-first thinking. Every architecture answer should address IAM, encryption, network segmentation, and compliance without being prompted. Skipping security signals weak production awareness.
- Migration depth. Not just theory - interviewers want to hear about real migrations you have done. The failures are more interesting than the successes. "What went wrong? How did you recover? What would you do differently?"
- Multi-cloud awareness. Even if the company is AWS-only, interviewers want to know you can reason about Azure and GCP alternatives. This signals architecture thinking over vendor lock-in.
- Hands-on credibility. Can you write a Terraform module from memory? Can you debug a VPC configuration? Can you read CloudWatch metrics and diagnose a performance bottleneck? Pure whiteboard architects get filtered out.

What interviewers focus on by seniority:

- Associate/Junior SA - cloud fundamentals, basic architecture patterns, willingness to learn, enthusiasm for the platform
- Mid-level SA - end-to-end architecture design, migration experience, cost optimization, customer communication
- Senior SA - trade-off fluency, multi-service integration, architecture governance, mentoring others
- Principal/Staff SA - architecture strategy, organizational influence, cross-company standards, industry thought leadership


## What Separates Candidates

From 40+ SA interviews at cloud providers and consulting firms:

- The first 5 minutes of the architecture design round decide everything. Start with clarifying questions, not solutions. Ask about scale, budget, compliance, team size, timeline.
- Talk like a builder, not a textbook. "We tried a multi-AZ RDS deployment but the cross-AZ data transfer costs were 3x what we estimated, so we switched to a single-AZ primary with automated snapshots and a standby in a second AZ only for DR" beats "I would use a multi-AZ deployment for high availability."
- Cost awareness is a superpower. One candidate walked through a cost comparison showing that Lambda + DynamoDB was $4K/month for a workload that would cost $18K/month on ECS + RDS, with the same availability guarantees. Got an offer the same week.
- Honesty beats bluffing. "I have not done a multi-region active-active deployment in production, but here is how I would approach it based on what I know about DynamoDB Global Tables and Route 53 health checks" - turned into an offer.
- Real war stories win. Practiced answers about "a time you designed a scalable system" are obvious. Raw stories about migrations that failed, costs that exploded, and security incidents that taught lessons are what interviewers remember.

The 80/20 rule: 80% of interview success comes from how you communicate your architecture thinking. Only 20% is raw technical knowledge. An articulate SA who knows 80% of services beats a silent expert who knows 100%.

For a structured deep-dive with 200+ real interview examples, check out [The 0→1 Solutions Architect Interview Playbook](https://valenx.org/books/sa).


## Portfolio Strategy

See [portfolio project ideas and strategy](../portfolio/README.md) for detailed guidance on project selection, case study writing, and what hiring managers look at.


## Before You Apply

Some companies require more than a resume upfront:

- A portfolio with architecture case studies - cloud providers ask candidates to present a past architecture design with trade-off analysis
- Certifications - AWS SA Associate is near-mandatory for AWS SA roles; Azure Solutions Architect Expert for Azure roles
- A written architecture design - some companies send a take-home scenario (design an architecture for X requirements, 2-4 hour exercise)
- Proof of concepts - HashiCorp asks candidates to build a working proof of concept during the interview process

Resume tips:

- Lead with architecture impact, not service names. "Designed multi-region architecture reducing failover time from 4 hours to 90 seconds" beats "Experience with AWS EC2, S3, RDS, Lambda"
- Include cost savings and performance improvements with numbers
- List certifications prominently - they serve as trust signals even if they do not test real-world skill
- Mention specific industries if you have domain expertise (healthcare, finance, government)


## Common Mistakes

In the interview:

- Jumping to a solution before asking clarifying questions. Always start with requirements gathering.
- Over-engineering the architecture. Adding Kubernetes, service mesh, and event-driven architecture for a system that serves 100 users.
- Ignoring cost. Designing a multi-region active-active deployment for a startup with a $5K/month budget.
- Forgetting security. Not mentioning IAM, encryption, or network segmentation unless explicitly asked.
- Using vendor jargon without understanding the underlying concepts. Knowing what an ALB does is less valuable than understanding when to use it vs a NLB vs CloudFront.
- Not communicating trade-offs. Every architecture decision has downsides. State them before the interviewer asks.

In preparation:

- Studying for certifications without building anything. Certification knowledge and production knowledge are different.
- Only learning one cloud provider. Multi-cloud awareness is expected even for single-cloud roles.
- Memorizing service names without understanding architecture patterns. Services change; patterns are durable.
- Not practicing whiteboard communication. You need to explain your thinking while drawing, not draw silently and present at the end.
