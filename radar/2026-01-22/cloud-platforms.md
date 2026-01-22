---
title:      "Cloud Platforms"
ring:       adopt
quadrant:   platforms-and-operations
tags:       [cloud, infrastructure, aws, azure, gcp, platforms]
---

## Varför ADOPT?

Cloud platforms har blivit den fundamentala infrastrukturen för modern mjukvaruutveckling. De tre stora - AWS, Azure och Google Cloud - erbjuder robust, skalbar och kostnadseffektiv infrastruktur som gör det möjligt för organisationer att fokusera på värdeskapande istället för att underhålla fysisk hårdvara.

**Core benefits:**
- **Skalbarhet on-demand** - Elastisk infrastruktur som skalar automatiskt
- **Global räckvidd** - Datacenters över hela världen för låg latens
- **Pay-as-you-go** - Betala bara för vad du använder
- **Managed services** - Färdiga lösningar för databaser, AI/ML, analytics etc
- **Security & compliance** - Enterprise-grade säkerhet och certifieringar
- **Innovation velocity** - Kontinuerliga nya features och tjänster

## Cloud providers

**AWS (Amazon Web Services)**
- Störst marknadsandel och bredast tjänsteutbud
- Bäst för: Startups, tech-företag, bred feature-set
- Nackdel: Komplex prissättning, steep learning curve

**Microsoft Azure**
- Tight integration med Microsoft-ekosystemet
- Bäst för: Enterprise med befintliga Microsoft-investeringar
- Stark i: Hybrid cloud, AD-integration, .NET-utveckling

**Google Cloud Platform (GCP)**
- Ledande inom data analytics och machine learning
- Bäst för: Data-intensive workloads, Kubernetes (GKE)
- Stark i: BigQuery, TensorFlow, open source-vänlighet

## Best practices

**Multi-cloud strategy:**
- Överväg att använda flera providers för resilience
- Undvik vendor lock-in genom att använda cloud-agnostic tools (Kubernetes, Terraform)
- Välj rätt cloud för rätt workload

**Cost management:**
- Implementera tagging och cost allocation
- Använd reserved instances/savings plans för förutsägbara workloads
- Sätt upp budgetar och alerts
- Regelbundet review och optimera resurser

**Security:**
- Följ "shared responsibility model"
- Använd Identity and Access Management (IAM) korrekt
- Aktivera logging och monitoring (CloudTrail, Azure Monitor, Cloud Logging)
- Kryptera data in transit och at rest

**Infrastructure as Code:**
- Terraform/OpenTofu för multi-cloud
- CloudFormation (AWS), ARM/Bicep (Azure), Deployment Manager (GCP)
- Version control all infrastructure

## Use cases

- **Web applications & APIs** - Hosting och skalning
- **Data lakes & analytics** - Lagring och analys av stora datamängder
- **Machine Learning** - Training och deployment av ML-modeller
- **Disaster recovery** - Backup och business continuity
- **Development environments** - Snabba upp dev/test cycles

## Övergång från on-prem

- Börja med "lift and shift" för snabb migration
- Refactor till cloud-native architecture stegvis
- Hybrid cloud som mellansteg
- Focus på cloud foundations först (networking, security, IAM)

## Further reading

- [AWS Well-Architected Framework](https://aws.amazon.com/architecture/well-architected/)
- [Microsoft Azure Architecture Center](https://docs.microsoft.com/en-us/azure/architecture/)
- [Google Cloud Architecture Framework](https://cloud.google.com/architecture/framework)
- [CNCF Cloud Native Landscape](https://landscape.cncf.io/)
