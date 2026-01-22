---
title:      "AWS (Amazon Web Services)"
ring:       adopt
quadrant:   platforms-and-operations
tags:       [cloud, aws, infrastructure, platforms]
---

## Varför ADOPT?

AWS är den mest etablerade och omfattande cloud-plattformen med störst marknadsandel. Robust ekosystem, bred tjänsteportfölj och beprövad i produktion hos miljontals företag globalt - från startups till Fortune 500.

**Core strengths:**
- **Bredast tjänsteutbud** - 200+ services för alla tänkbara use cases
- **Global infrastructure** - 30+ regions världen över
- **Ekosystem & community** - Störst community, flest integrationer, rikast med dokumentation
- **Innovation** - Pioneer inom cloud services, driver industry standards
- **Mature tooling** - Välutvecklade CLI, SDKs och Infrastructure as Code-verktyg

## Key services att kunna

**Compute:**
- **EC2** - Virtuella servrar (compute foundation)
- **Lambda** - Serverless functions
- **ECS/EKS** - Container orchestration (Docker, Kubernetes)
- **Fargate** - Serverless containers

**Storage & Databases:**
- **S3** - Object storage (industry standard)
- **RDS** - Managed relational databases (PostgreSQL, MySQL, etc.)
- **DynamoDB** - NoSQL database
- **ElastiCache** - Redis/Memcached caching

**Networking:**
- **VPC** - Virtual Private Cloud
- **Route 53** - DNS service
- **CloudFront** - CDN
- **API Gateway** - API management

**DevOps & Observability:**
- **CloudFormation** - Infrastructure as Code
- **CodePipeline/CodeBuild** - CI/CD
- **CloudWatch** - Monitoring och logging
- **X-Ray** - Distributed tracing

## Best practices

**Well-Architected Framework:**
Följ AWS's fem pelare:
- Operational Excellence
- Security
- Reliability
- Performance Efficiency
- Cost Optimization

**Account strategy:**
- Använd AWS Organizations för multi-account setup
- Separera environments (dev/staging/prod) i olika accounts
- Centraliserad billing och governance

**Security:**
- IAM roles över access keys
- Aktivera MFA för alla användare
- CloudTrail för audit logging
- GuardDuty för threat detection
- Secrets Manager för credentials

**Cost management:**
- Reserved Instances/Savings Plans för steady-state workloads
- Spot Instances för fault-tolerant workloads
- AWS Cost Explorer för analys
- Tagging strategy för cost allocation

## När välja AWS

✅ **Passar bäst för:**
- Tech startups som vill skala snabbt
- Organisations utan legacy Microsoft-investeringar
- Behov av cutting-edge services och innovation
- Global räckvidd och multi-region deployments
- Bred feature-set krävs

## Utmaningar

⚠️ **Tänk på:**
- Komplex prissättning - kräver active cost management
- Steep learning curve - brett utbud kan vara överväldigande
- Vendor lock-in risk - många AWS-specifika services
- Support kan vara kostsamt för mindre företag

## Further reading

- [AWS Well-Architected Framework](https://aws.amazon.com/architecture/well-architected/)
- [AWS Documentation](https://docs.aws.amazon.com/)
- [AWS Skills Builder](https://skillbuilder.aws/)
- [AWS Architecture Center](https://aws.amazon.com/architecture/)
