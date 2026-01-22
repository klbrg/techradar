---
title:      "Google Cloud Platform (GCP)"
ring:       trial
quadrant:   platforms-and-operations
tags:       [cloud, gcp, google, infrastructure, platforms, data, ml]
---

## Varför TRIAL?

GCP är en stark cloud platform med specifika styrkor inom data analytics, machine learning och Kubernetes. Moget nog för production workloads, särskilt för data-intensive use cases, men mindre marknadsandel än AWS/Azure gör det till TRIAL istället för ADOPT för generella enterprise workloads.

**Core strengths:**
- **Data & Analytics** - Industry-leading BigQuery, best-in-class data warehouse
- **Machine Learning** - TensorFlow, Vertex AI, cutting-edge ML services
- **Kubernetes** - GKE är gold standard för managed Kubernetes (Google skapade K8s)
- **Developer experience** - Enklare och mer konsekvent än AWS/Azure
- **Networking** - Googles globala nätverk, snabbaste performance
- **Open source-vänlig** - Strong commitment till open source

## Key services att kunna

**Compute:**
- **Compute Engine** - Virtual machines
- **Cloud Run** - Serverless containers (excellent developer experience)
- **GKE** - Google Kubernetes Engine (best managed K8s)
- **Cloud Functions** - Serverless functions

**Data & Analytics:**
- **BigQuery** - Serverless data warehouse (killer feature)
- **Dataflow** - Stream och batch data processing (Apache Beam)
- **Pub/Sub** - Messaging och event streaming
- **Dataproc** - Managed Spark/Hadoop

**Machine Learning:**
- **Vertex AI** - Unified ML platform
- **AutoML** - No-code ML model training
- **TensorFlow** - ML framework (Google-utvecklat)

**Storage & Databases:**
- **Cloud Storage** - Object storage
- **Cloud SQL** - Managed PostgreSQL/MySQL
- **Firestore** - NoSQL document database
- **Spanner** - Globally distributed relational database

**Networking:**
- **Cloud CDN** - Content delivery network
- **Cloud Load Balancing** - Global load balancing
- **Cloud Armor** - DDoS protection och WAF

**Security:**
- **Secret Manager** - Credentials management
- **Security Command Center** - Security posture management
- **Identity-Aware Proxy** - Zero-trust access
- **VPC Service Controls** - Data exfiltration protection

**Observability:**
- **Cloud Monitoring** - Metrics och alerting (f.d. Stackdriver)
- **Cloud Logging** - Centralized logging
- **Cloud Trace** - Distributed tracing
- **Cloud Profiler** - Performance profiling

## Best practices

**Project structure:**
- Använd folder hierarchy i organization
- Shared VPC för networking
- Separate projects per environment/team

**Identity:**
- Cloud Identity för user management
- Service Accounts för workload identity
- Workload Identity för GKE pods

**Infrastructure as Code:**
- Terraform (rekommenderat)
- Cloud Deployment Manager (GCP-native)

**Cost optimization:**
- Committed Use Discounts (motsvarar AWS Reserved Instances)
- Spot VMs för batch workloads (upp till 91% rabatt)
- Sustained use discounts (automatiska rabatter)
- BigQuery slot reservations för stora queries
- Resource quotas och budget alerts

## När välja GCP

✅ **Passar bäst för:**
- **Data analytics & data science** - BigQuery är oslagbart
- **Machine learning workloads** - Vertex AI, TensorFlow
- **Kubernetes-first organizations** - GKE är gold standard
- **Startups med data focus** - Snabb time-to-value
- **Modern cloud-native apps** - Cloud Run excellent för containers

## Utmaningar

⚠️ **Tänk på:**
- Mindre marknadsandel = mindre community/ecosystem
- Färre third-party integrations än AWS
- Viss produktinstabilitet - Google har historik av att sunset:a tjänster
- Enterprise support inte lika moget som AWS/Azure
- Färre regions än konkurrenterna (men växer)

## Migrationsväg

1. **Start small** - Proof of concept med BigQuery eller GKE
2. **Data workloads först** - Migrera analytics/ML pipelines
3. **Hybrid approach** - Kör GCP för specific use cases, AWS/Azure för annat
4. **Multi-cloud** - Använd GCP's styrkor (data/ML), kombinera med primary cloud

## Further reading

- [Google Cloud Architecture Framework](https://cloud.google.com/architecture/framework)
- [BigQuery Documentation](https://cloud.google.com/bigquery/docs)
- [GKE Best Practices](https://cloud.google.com/kubernetes-engine/docs/best-practices)
- [Google Cloud Skills Boost](https://www.cloudskillsboost.google/)
